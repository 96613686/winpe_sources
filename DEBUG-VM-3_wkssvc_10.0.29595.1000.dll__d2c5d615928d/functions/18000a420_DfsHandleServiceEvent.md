# DfsHandleServiceEvent

- ea: `0x18000a420`
- end: `0x18000a5f5`
- name: `DfsHandleServiceEvent`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a1c0`
- `0x18000a270`

## callees

- `0x18000a420`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18000a52c`
- `ntdll!RtlGetNtProductType` at `0x18000a52c`
- `ntdll!NtOpenFile` at `0x18000a487`
- `ntdll!NtOpenFile` at `0x18000a487`
- `ntdll!NtFsControlFile` at `0x18000a4ec`
- `ntdll!NtFsControlFile` at `0x18000a4ec`
- `ntdll!NtClose` at `0x18000a4fe`
- `ntdll!NtClose` at `0x18000a4fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a5ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a5ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cb`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000a56b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000a56b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000a5a1`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000a5a1`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000a584`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000a584`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000a597`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000a597`

## pseudocode

```c
NTSTATUS __fastcall DfsHandleServiceEvent(int a1)
{
  NTSTATUS result; // eax
  NTSTATUS Status; // edi
  int v4; // ebx
  PVOID PolicyHandle; // [rsp+50h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+Fh] BYREF
  int InputBuffer; // [rsp+C8h] [rbp+6Fh] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+D0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  InputBuffer = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)LocalDfsName;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( result >= 0 )
  {
    result = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
    {
      InputBuffer = a1;
      IoStatusBlock = 0;
      Status = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x69FF4u, &InputBuffer, 4u, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
      NtClose(FileHandle);
      if ( !Status )
      {
        ProductType = 0;
        PolicyHandle = 0;
        IoStatusBlock.Pointer = 0;
        memset(&ObjectAttributes, 0, 44);
        if ( !RtlGetNtProductType(&ProductType) )
          goto LABEL_16;
        if ( ProductType == NtProductLanManNt )
          goto LABEL_16;
        ObjectAttributes.Length = 48;
        memset(&ObjectAttributes.RootDirectory, 0, 20);
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( LsaLookupOpenLocalPolicy((PLSA_OBJECT_ATTRIBUTES)&ObjectAttributes, 1u, &PolicyHandle) < 0 )
          goto LABEL_16;
        v4 = 0;
        if ( LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, (PVOID *)&IoStatusBlock) >= 0 )
          LOBYTE(v4) = *((_QWORD *)IoStatusBlock.Pointer + 8) == 0;
        if ( IoStatusBlock.Pointer )
          LsaLookupFreeMemory(IoStatusBlock.Pointer);
        LsaLookupClose(PolicyHandle);
        if ( v4 != 1 )
        {
LABEL_16:
          EnterCriticalSection(&WsDfsTearDownCriticalSection);
          if ( g_WsDomainNameChangeEvent != (HANDLE)-1LL )
            SetEvent(g_WsDomainNameChangeEvent);
          LeaveCriticalSection(&WsDfsTearDownCriticalSection);
        }
      }
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a420  push    rbp
0x18000a422  push    rbx
0x18000a423  push    rsi
0x18000a424  lea     rbp, [rsp-47h]
0x18000a429  sub     rsp, 0A0h
0x18000a430  xor     esi, esi
0x18000a432  mov     [rsp+0B0h+OpenOptions], 20h ; ' '; OpenOptions
0x18000a43a  xorps   xmm0, xmm0
0x18000a43d  mov     [rbp+57h+FileHandle], rsi
0x18000a441  mov     ebx, ecx
0x18000a443  mov     [rbp+57h+arg_8], esi
0x18000a446  lea     rax, LocalDfsName; "\"\""
0x18000a44d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18000a451  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000a455  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a459  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000a45d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a465  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a469  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a471  mov     edx, 100002h; DesiredAccess
0x18000a476  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x18000a47e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000a482  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a487  call    cs:__imp_NtOpenFile
0x18000a48d  test    eax, eax
0x18000a48f  jns     short loc_18000A49C
0x18000a491  add     rsp, 0A0h
0x18000a498  pop     rsi
0x18000a499  pop     rbx
0x18000a49a  pop     rbp
0x18000a49b  retn
0x18000a49c  mov     eax, dword ptr [rbp+57h+IoStatusBlock]
0x18000a49f  test    eax, eax
0x18000a4a1  js      short loc_18000A491
0x18000a4a3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000a4a7  lea     rax, [rbp+57h+arg_8]
0x18000a4ab  mov     [rsp+0B0h+OutputBufferLength], esi; OutputBufferLength
0x18000a4af  xorps   xmm0, xmm0
0x18000a4b2  mov     [rsp+0B0h+OutputBuffer], rsi; OutputBuffer
0x18000a4b7  xor     r9d, r9d; ApcContext
0x18000a4ba  mov     [rsp+0B0h+InputBufferLength], 4; InputBufferLength
0x18000a4c2  xor     r8d, r8d; ApcRoutine
0x18000a4c5  mov     [rsp+0B0h+InputBuffer], rax; InputBuffer
0x18000a4ca  xor     edx, edx; Event
0x18000a4cc  lea     rax, [rbp+57h+IoStatusBlock]
0x18000a4d0  mov     [rsp+0B0h+OpenOptions], 69FF4h; FsControlCode
0x18000a4d8  mov     qword ptr [rsp+0B0h+ShareAccess], rax; IoStatusBlock
0x18000a4dd  mov     [rsp+0B0h+arg_0], rdi
0x18000a4e5  mov     [rbp+57h+arg_8], ebx
0x18000a4e8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000a4ec  call    cs:__imp_NtFsControlFile
0x18000a4f2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000a4f6  test    eax, eax
0x18000a4f8  mov     edi, eax
0x18000a4fa  cmovns  edi, dword ptr [rbp+57h+IoStatusBlock]
0x18000a4fe  call    cs:__imp_NtClose
0x18000a504  test    edi, edi
0x18000a506  jnz     loc_18000A5AC
0x18000a50c  xorps   xmm0, xmm0
0x18000a50f  mov     [rbp+57h+ProductType], esi
0x18000a512  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000a516  xor     eax, eax
0x18000a518  mov     [rbp+57h+PolicyHandle], rsi
0x18000a51c  lea     rcx, [rbp+57h+ProductType]; ProductType
0x18000a520  mov     qword ptr [rbp+57h+IoStatusBlock], rsi
0x18000a524  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000a528  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000a52c  call    cs:__imp_RtlGetNtProductType
0x18000a532  test    al, al
0x18000a534  jz      loc_18000A5C4
0x18000a53a  cmp     [rbp+57h+ProductType], 2
0x18000a53e  jz      loc_18000A5C4
0x18000a544  xorps   xmm0, xmm0
0x18000a547  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a54e  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a552  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18000a556  mov     edx, 1; AccessMask
0x18000a55b  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x18000a55e  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a562  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18000a566  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a56b  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000a571  test    eax, eax
0x18000a573  js      short loc_18000A5C4
0x18000a575  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000a579  lea     r8, [rbp+57h+IoStatusBlock]; DomainInfo
0x18000a57d  mov     edx, 0Ch; DomainInfoClass
0x18000a582  mov     ebx, esi
0x18000a584  call    cs:__imp_LsaLookupGetDomainInfo
0x18000a58a  mov     rcx, qword ptr [rbp+57h+IoStatusBlock]; Buffer
0x18000a58e  test    eax, eax
0x18000a590  jns     short loc_18000A5BB
0x18000a592  test    rcx, rcx
0x18000a595  jz      short loc_18000A59D
0x18000a597  call    cs:__imp_LsaLookupFreeMemory
0x18000a59d  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18000a5a1  call    cs:__imp_LsaLookupClose
0x18000a5a7  cmp     ebx, 1
0x18000a5aa  jnz     short loc_18000A5C4
0x18000a5ac  mov     eax, edi
0x18000a5ae  mov     rdi, [rsp+0B0h+arg_0]
0x18000a5b6  jmp     loc_18000A491
0x18000a5bb  cmp     [rcx+40h], rbx
0x18000a5bf  setz    bl
0x18000a5c2  jmp     short loc_18000A592
0x18000a5c4  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18000a5cb  call    cs:__imp_EnterCriticalSection
0x18000a5d1  mov     rcx, cs:g_WsDomainNameChangeEvent; hEvent
0x18000a5d8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a5dc  jnz     short loc_18000A5ED
0x18000a5de  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18000a5e5  call    cs:__imp_LeaveCriticalSection
0x18000a5eb  jmp     short loc_18000A5AC
0x18000a5ed  call    cs:__imp_SetEvent
0x18000a5f3  jmp     short loc_18000A5DE
```
