# Common::Deployment::AtomicDeleteFile(ushort const *)

- ea: `0x18018b940`
- end: `0x18018bbfa`
- name: `?AtomicDeleteFile@Deployment@Common@@YAHPEBG@Z`
- size: `698`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800aed10`
- `0x18018b940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18018bade`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18018bade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18018bbc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18018bbc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018bb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018bb3d`
- `ntdll!RtlReleaseRelativeName` at `0x18018ba6d`
- `ntdll!RtlReleaseRelativeName` at `0x18018ba6d`
- `ntdll!RtlFreeHeap` at `0x18018ba8b`
- `ntdll!RtlFreeHeap` at `0x18018ba8b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018bbb9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018bbb9`
- `ntdll!NtOpenFile` at `0x18018ba5a`
- `ntdll!NtOpenFile` at `0x18018ba5a`
- `ntdll!NtClose` at `0x18018baf8`
- `ntdll!NtClose` at `0x18018bb55`
- `ntdll!NtClose` at `0x18018bb93`
- `ntdll!NtClose` at `0x18018bba3`
- `ntdll!NtClose` at `0x18018baf8`
- `ntdll!NtClose` at `0x18018bb55`
- `ntdll!NtClose` at `0x18018bb93`
- `ntdll!NtClose` at `0x18018bba3`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18018b9a6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18018b9a6`
- `ntdll!NtSetInformationFile` at `0x18018bb80`
- `ntdll!NtSetInformationFile` at `0x18018bb80`
- `KERNEL32!DeviceIoControl` at `0x18018bb31`
- `KERNEL32!DeviceIoControl` at `0x18018bb31`

## pseudocode

```c
__int64 __fastcall Common::Deployment::AtomicDeleteFile(Common::Deployment *this, const unsigned __int16 *a2)
{
  int v2; // eax
  ULONG v3; // ecx
  NTSTATUS v4; // ecx
  PVOID v5; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v7; // ebx
  HANDLE EventW; // rax
  void *hEvent; // rcx
  char FileInformation[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD InBuffer[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 OutBuffer; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v20; // [rsp+100h] [rbp+0h]

  FileHandle = 0;
  FileInformation[0] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v2 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(this, P, 0, &RelativeName);
  if ( v2 < 0 )
  {
    if ( v2 != -1073741801 && v2 != -1073741670 )
    {
      v3 = 3;
LABEL_18:
      SetLastError(v3);
      return 0;
    }
    v4 = v2;
LABEL_17:
    v3 = RtlNtStatusToDosErrorNoTeb(v4);
    goto LABEL_18;
  }
  v5 = P[1];
  if ( RelativeName.RelativeName.Length )
  {
    LOWORD(P[0]) = RelativeName.RelativeName.Length;
    *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
    HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
    P[1] = RelativeName.RelativeName.Buffer;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x214040u);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v7 < 0 )
    goto LABEL_16;
  InBuffer[1] = 7;
  InBuffer[0] = 786433;
  InBuffer[2] = 1;
  OutBuffer = 0;
  LODWORD(OutBuffer) = 1572865;
  v20 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  EventW = CreateEventW(0, 1, 0, 0);
  hEvent = FileHandle;
  Overlapped.hEvent = EventW;
  if ( EventW )
  {
    DeviceIoControl(FileHandle, 0x90240u, InBuffer, 0xCu, &OutBuffer, 0x18u, 0, &Overlapped);
    if ( GetLastError() != 997 )
    {
      NtClose(FileHandle);
      hEvent = Overlapped.hEvent;
      goto LABEL_11;
    }
    FileInformation[0] = 1;
    v7 = NtSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
    NtClose(FileHandle);
    NtClose(Overlapped.hEvent);
    if ( v7 >= 0 )
      return 1;
LABEL_16:
    v4 = v7;
    goto LABEL_17;
  }
LABEL_11:
  NtClose(hEvent);
  return 0;
}

```

## disassembly

```asm
0x18018b940  mov     [rsp-8+arg_8], rbx
0x18018b945  mov     [rsp-8+arg_10], rsi
0x18018b94a  push    rbp
0x18018b94b  push    rdi
0x18018b94c  push    r14
0x18018b94e  lea     rbp, [rsp-10h]
0x18018b953  sub     rsp, 110h
0x18018b95a  mov     rax, cs:__security_cookie
0x18018b961  xor     rax, rsp
0x18018b964  mov     [rbp+20h+var_18], rax
0x18018b968  xorps   xmm0, xmm0
0x18018b96b  lea     r9, [rsp+120h+RelativeName]
0x18018b970  xor     esi, esi
0x18018b972  lea     rdx, [rsp+120h+P]
0x18018b977  xorps   xmm1, xmm1
0x18018b97a  mov     [rsp+120h+FileHandle], rsi
0x18018b97f  xor     r8d, r8d
0x18018b982  mov     [rsp+120h+FileInformation], sil
0x18018b987  movups  xmmword ptr [rbp+20h+ObjectAttributes.Length], xmm0
0x18018b98b  movups  xmmword ptr [rbp+20h+ObjectAttributes.ObjectName], xmm0
0x18018b98f  movups  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x18018b993  movups  xmmword ptr [rsp+120h+P], xmm0
0x18018b998  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm1
0x18018b99c  movups  xmmword ptr [rsp+120h+RelativeName.RelativeName.Length], xmm0
0x18018b9a1  movups  xmmword ptr [rsp+120h+RelativeName.ContainingDirectory], xmm0
0x18018b9a6  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18018b9ad  nop     dword ptr [rax+rax+00h]
0x18018b9b2  test    eax, eax
0x18018b9b4  jns     short loc_18018B9D3
0x18018b9b6  cmp     eax, 0C0000017h
0x18018b9bb  jz      short loc_18018B9CC
0x18018b9bd  cmp     eax, 0C000009Ah
0x18018b9c2  jz      short loc_18018B9CC
0x18018b9c4  lea     ecx, [rsi+3]
0x18018b9c7  jmp     loc_18018BBC7
0x18018b9cc  mov     ecx, eax
0x18018b9ce  jmp     loc_18018BBB9
0x18018b9d3  movzx   eax, [rsp+120h+RelativeName.RelativeName.Length]
0x18018b9d8  mov     rdi, [rsp+120h+P+8]
0x18018b9dd  test    ax, ax
0x18018b9e0  jz      short loc_18018BA0A
0x18018b9e2  mov     word ptr [rsp+120h+P], ax
0x18018b9e7  mov     eax, dword ptr [rsp+120h+RelativeName.RelativeName.MaximumLength]
0x18018b9eb  mov     dword ptr [rsp+120h+P+2], eax
0x18018b9ef  movzx   eax, word ptr [rsp+120h+RelativeName.RelativeName+6]
0x18018b9f4  mov     word ptr [rsp+120h+P+6], ax
0x18018b9f9  mov     rax, [rsp+120h+RelativeName.RelativeName.Buffer]
0x18018b9fe  mov     [rsp+120h+P+8], rax
0x18018ba03  mov     rax, [rsp+120h+RelativeName.ContainingDirectory]
0x18018ba08  jmp     short loc_18018BA12
0x18018ba0a  mov     rax, rsi
0x18018ba0d  mov     [rsp+120h+RelativeName.ContainingDirectory], rax
0x18018ba12  mov     [rbp+20h+ObjectAttributes.RootDirectory], rax
0x18018ba16  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x18018ba1a  lea     rax, [rsp+120h+P]
0x18018ba1f  mov     [rsp+120h+OpenOptions], 214040h; OpenOptions
0x18018ba27  xorps   xmm0, xmm0
0x18018ba2a  mov     [rbp+20h+ObjectAttributes.ObjectName], rax
0x18018ba2e  mov     r14d, 7
0x18018ba34  mov     [rbp+20h+ObjectAttributes.Length], 30h ; '0'
0x18018ba3b  lea     r8, [rbp+20h+ObjectAttributes]; ObjectAttributes
0x18018ba3f  mov     [rbp+20h+ObjectAttributes.Attributes], 40h ; '@'
0x18018ba46  mov     edx, 10000h; DesiredAccess
0x18018ba4b  mov     [rsp+120h+ShareAccess], r14d; ShareAccess
0x18018ba50  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x18018ba55  movdqu  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x18018ba5a  call    cs:__imp_NtOpenFile
0x18018ba61  nop     dword ptr [rax+rax+00h]
0x18018ba66  lea     rcx, [rsp+120h+RelativeName]; RelativeName
0x18018ba6b  mov     ebx, eax
0x18018ba6d  call    cs:__imp_RtlReleaseRelativeName
0x18018ba74  nop     dword ptr [rax+rax+00h]
0x18018ba79  mov     rcx, gs:60h
0x18018ba82  mov     r8, rdi; P
0x18018ba85  xor     edx, edx; Flags
0x18018ba87  mov     rcx, [rcx+30h]; HeapHandle
0x18018ba8b  call    cs:__imp_RtlFreeHeap
0x18018ba92  nop     dword ptr [rax+rax+00h]
0x18018ba97  test    ebx, ebx
0x18018ba99  js      loc_18018BBB7
0x18018ba9f  lea     edi, [r14-6]
0x18018baa3  mov     [rbp+20h+var_3C], r14d
0x18018baa7  xorps   xmm0, xmm0
0x18018baaa  mov     [rbp+20h+InBuffer], 0C0001h
0x18018bab1  xor     eax, eax
0x18018bab3  mov     [rbp+20h+var_38], edi
0x18018bab6  movups  [rbp+20h+OutBuffer], xmm0
0x18018baba  mov     edx, edi; bManualReset
0x18018babc  mov     dword ptr [rbp+20h+OutBuffer], 180001h
0x18018bac3  xor     r9d, r9d; lpName
0x18018bac6  mov     [rbp+20h+var_20], rax
0x18018baca  xor     r8d, r8d; bInitialState
0x18018bacd  lea     ebx, [rdi+0Bh]
0x18018bad0  xor     ecx, ecx; lpEventAttributes
0x18018bad2  lea     r14d, [rdi+17h]
0x18018bad6  movups  xmmword ptr [rbp+20h+Overlapped.Internal], xmm0
0x18018bada  movups  xmmword ptr [rbp+20h+Overlapped.10h], xmm0
0x18018bade  call    cs:__imp_CreateEventW
0x18018bae5  nop     dword ptr [rax+rax+00h]
0x18018baea  mov     rcx, [rsp+120h+FileHandle]; hDevice
0x18018baef  mov     [rbp+20h+Overlapped.hEvent], rax
0x18018baf3  test    rax, rax
0x18018baf6  jnz     short loc_18018BB09
0x18018baf8  call    cs:__imp_NtClose
0x18018baff  nop     dword ptr [rax+rax+00h]
0x18018bb04  jmp     loc_18018BBD3
0x18018bb09  lea     rax, [rbp+20h+Overlapped]
0x18018bb0d  mov     r9d, ebx; nInBufferSize
0x18018bb10  mov     [rsp+120h+lpOverlapped], rax; lpOverlapped
0x18018bb15  lea     r8, [rbp+20h+InBuffer]; lpInBuffer
0x18018bb19  mov     [rsp+120h+lpBytesReturned], rsi; lpBytesReturned
0x18018bb1e  lea     rax, [rbp+20h+OutBuffer]
0x18018bb22  mov     [rsp+120h+OpenOptions], r14d; nOutBufferSize
0x18018bb27  mov     edx, 90240h; dwIoControlCode
0x18018bb2c  mov     qword ptr [rsp+120h+ShareAccess], rax; lpOutBuffer
0x18018bb31  call    cs:__imp_DeviceIoControl
0x18018bb38  nop     dword ptr [rax+rax+00h]
0x18018bb3d  call    cs:__imp_GetLastError
0x18018bb44  nop     dword ptr [rax+rax+00h]
0x18018bb49  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x18018bb4e  cmp     eax, 3E5h
0x18018bb53  jz      short loc_18018BB67
0x18018bb55  call    cs:__imp_NtClose
0x18018bb5c  nop     dword ptr [rax+rax+00h]
0x18018bb61  mov     rcx, [rbp+20h+Overlapped.hEvent]
0x18018bb65  jmp     short loc_18018BAF8
0x18018bb67  mov     r9d, edi; Length
0x18018bb6a  mov     [rsp+120h+FileInformation], dil
0x18018bb6f  lea     r8, [rsp+120h+FileInformation]; FileInformation
0x18018bb74  mov     [rsp+120h+ShareAccess], 0Dh; FileInformationClass
0x18018bb7c  lea     rdx, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x18018bb80  call    cs:__imp_NtSetInformationFile
0x18018bb87  nop     dword ptr [rax+rax+00h]
0x18018bb8c  mov     rcx, [rsp+120h+FileHandle]; Handle
0x18018bb91  mov     ebx, eax
0x18018bb93  call    cs:__imp_NtClose
0x18018bb9a  nop     dword ptr [rax+rax+00h]
0x18018bb9f  mov     rcx, [rbp+20h+Overlapped.hEvent]; Handle
0x18018bba3  call    cs:__imp_NtClose
0x18018bbaa  nop     dword ptr [rax+rax+00h]
0x18018bbaf  test    ebx, ebx
0x18018bbb1  js      short loc_18018BBB7
0x18018bbb3  mov     eax, edi
0x18018bbb5  jmp     short loc_18018BBD5
0x18018bbb7  mov     ecx, ebx; Status
0x18018bbb9  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018bbc0  nop     dword ptr [rax+rax+00h]
0x18018bbc5  mov     ecx, eax; dwErrCode
0x18018bbc7  call    cs:__imp_SetLastError
0x18018bbce  nop     dword ptr [rax+rax+00h]
0x18018bbd3  xor     eax, eax
0x18018bbd5  mov     rcx, [rbp+20h+var_18]
0x18018bbd9  xor     rcx, rsp; StackCookie
0x18018bbdc  call    __security_check_cookie
0x18018bbe1  lea     r11, [rsp+120h+var_10]
0x18018bbe9  mov     rbx, [r11+28h]
0x18018bbed  mov     rsi, [r11+30h]
0x18018bbf1  mov     rsp, r11
0x18018bbf4  pop     r14
0x18018bbf6  pop     rdi
0x18018bbf7  pop     rbp
0x18018bbf8  retn
```
