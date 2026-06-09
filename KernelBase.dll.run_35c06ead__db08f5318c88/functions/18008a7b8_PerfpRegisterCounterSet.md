# PerfpRegisterCounterSet

- ea: `0x18008a7b8`
- end: `0x18008a9f0`
- name: `PerfpRegisterCounterSet`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18008b2f8`

## callees

- `0x18008a7b8`
- `0x18008a9f8`
- `0x18008aa90`
- `0x180157b28`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18008a8b5`
- `ntdll!RtlInitUnicodeString` at `0x18008a8b5`
- `ntdll!NtOpenFile` at `0x18008a904`
- `ntdll!NtOpenFile` at `0x18008a904`
- `ntdll!RtlNtStatusToDosError` at `0x18008a9a1`
- `ntdll!RtlNtStatusToDosError` at `0x18008a9a1`
- `ntdll!TpAllocIoCompletion` at `0x18008a930`
- `ntdll!TpAllocIoCompletion` at `0x18008a930`
- `ntdll!NtClose` at `0x18008a961`
- `ntdll!NtClose` at `0x18008a999`
- `ntdll!NtClose` at `0x18008a961`
- `ntdll!NtClose` at `0x18008a999`
- `ntdll!TpCancelAsyncIoOperation` at `0x18008a9ac`
- `ntdll!TpCancelAsyncIoOperation` at `0x18008a9ac`
- `ntdll!TpReleaseIoCompletion` at `0x18008a9b5`
- `ntdll!TpReleaseIoCompletion` at `0x18008a9b5`
- `ntdll!TpStartAsyncIoOperation` at `0x18008a93f`
- `ntdll!TpStartAsyncIoOperation` at `0x18008a93f`

## pseudocode

```c
ULONG __fastcall PerfpRegisterCounterSet(__int64 a1)
{
  __int64 v2; // r15
  int v3; // edx
  int v4; // r8d
  int v5; // r9d
  int v6; // r10d
  int v7; // r11d
  int v8; // ebx
  int v9; // edi
  int v10; // esi
  __int64 v11; // r9
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  int v16; // edi
  NTSTATUS v18; // ecx
  int v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v23[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t pszDest[40]; // [rsp+E0h] [rbp-20h] BYREF

  FileHandle = 0;
  v23[0] = 1966108;
  v2 = a1 + 192;
  v3 = *(unsigned __int8 *)(a1 + 205);
  v4 = *(unsigned __int8 *)(a1 + 204);
  v5 = *(unsigned __int8 *)(a1 + 203);
  v6 = *(unsigned __int8 *)(a1 + 202);
  v7 = *(unsigned __int8 *)(a1 + 201);
  v8 = *(unsigned __int8 *)(a1 + 200);
  v9 = *(unsigned __int16 *)(a1 + 198);
  v10 = *(unsigned __int16 *)(a1 + 196);
  v23[1] = L"\\Device\\PcwDrv";
  v21 = *(unsigned __int8 *)(a1 + 207);
  v20 = *(unsigned __int8 *)(a1 + 206);
  v19 = v5;
  v11 = *(unsigned int *)(a1 + 192);
  DestinationString = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  StringCbPrintfW(
    pszDest,
    0x50u,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    v11,
    v10,
    v9,
    v8,
    v7,
    v6,
    v19,
    v4,
    v3,
    v20,
    v21);
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v23;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v12 = NtOpenFile(&FileHandle, 1u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( v12 < 0 )
  {
    if ( v12 == -1073741772 )
    {
      *(_QWORD *)(a1 + 160) = 0;
      *(_QWORD *)(a1 + 168) = 0;
      if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x20) != 0 )
        McTemplateU0jj_EtwEventWriteTransfer(v14, v13, a1 + 208, v2);
      return 0;
    }
    v18 = v12;
  }
  else
  {
    v15 = (_QWORD *)(a1 + 160);
    v16 = TpAllocIoCompletion(a1 + 160, FileHandle, PerfpNotificationCallback, a1, 0);
    if ( v16 < 0 )
    {
      NtClose(FileHandle);
    }
    else
    {
      TpStartAsyncIoOperation(*v15);
      v16 = PcwRegisterCounterSet((PVOID)(a1 + 168));
      NtClose(FileHandle);
      if ( v16 >= 0 )
        return 0;
      TpCancelAsyncIoOperation(*v15);
      TpReleaseIoCompletion(*v15);
    }
    v18 = v16;
  }
  return RtlNtStatusToDosError(v18);
}

```

## disassembly

```asm
0x18008a7b8  push    rbp
0x18008a7ba  push    rbx
0x18008a7bb  push    rsi
0x18008a7bc  push    rdi
0x18008a7bd  push    r14
0x18008a7bf  push    r15
0x18008a7c1  lea     rbp, [rsp-48h]
0x18008a7c6  sub     rsp, 148h
0x18008a7cd  mov     rax, cs:__security_cookie
0x18008a7d4  xor     rax, rsp
0x18008a7d7  mov     [rbp+70h+var_40], rax
0x18008a7db  mov     r14, rcx
0x18008a7de  mov     [rsp+170h+FileHandle], 0
0x18008a7e7  xorps   xmm0, xmm0
0x18008a7ea  mov     [rsp+170h+var_F8], 1E001Ch
0x18008a7f3  lea     r15, [rcx+0C0h]
0x18008a7fa  lea     rax, aDevicePcwdrv; "\\Device\\PcwDrv"
0x18008a801  movzx   edx, byte ptr [r14+0CDh]
0x18008a809  movzx   r8d, byte ptr [r14+0CCh]
0x18008a811  movzx   r9d, byte ptr [r14+0CBh]
0x18008a819  movzx   r10d, byte ptr [r14+0CAh]
0x18008a821  movzx   r11d, byte ptr [r14+0C9h]
0x18008a829  movzx   ebx, byte ptr [r14+0C8h]
0x18008a831  movzx   edi, word ptr [r14+0C6h]
0x18008a839  movzx   esi, word ptr [r14+0C4h]
0x18008a841  mov     [rbp+70h+var_F0], rax
0x18008a845  xor     eax, eax
0x18008a847  movzx   eax, byte ptr [rcx+0CFh]
0x18008a84e  movzx   ecx, byte ptr [rcx+0CEh]
0x18008a855  mov     [rsp+170h+var_108], eax
0x18008a859  mov     [rsp+170h+var_110], ecx
0x18008a85d  lea     rcx, [rbp+70h+pszDest]; pszDest
0x18008a861  mov     [rsp+170h+var_118], edx
0x18008a865  mov     edx, 50h ; 'P'; cbDest
0x18008a86a  mov     [rsp+170h+var_120], r8d
0x18008a86f  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x18008a876  mov     [rsp+170h+var_128], r9d
0x18008a87b  mov     r9d, [r15]
0x18008a87e  mov     [rsp+170h+var_130], r10d
0x18008a883  mov     [rsp+170h+var_138], r11d
0x18008a888  mov     [rsp+170h+var_140], ebx
0x18008a88c  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x18008a890  mov     [rsp+170h+OpenOptions], edi
0x18008a894  mov     [rsp+170h+ShareAccess], esi
0x18008a898  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18008a89c  movups  xmmword ptr [rbp+70h+IoStatusBlock], xmm0
0x18008a8a0  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x18008a8a4  movups  xmmword ptr [rbp+70h+ObjectAttributes+1Ch], xmm0
0x18008a8a8  call    StringCbPrintfW
0x18008a8ad  lea     rdx, [rbp+70h+pszDest]; SourceString
0x18008a8b1  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18008a8b5  call    cs:__imp_RtlInitUnicodeString
0x18008a8bb  lea     rax, [rsp+170h+var_F8]
0x18008a8c0  mov     [rsp+170h+OpenOptions], 0; OpenOptions
0x18008a8c8  xorps   xmm0, xmm0
0x18008a8cb  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x18008a8cf  lea     r9, [rbp+70h+IoStatusBlock]; IoStatusBlock
0x18008a8d3  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x18008a8da  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x18008a8de  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x18008a8e6  mov     edx, 1; DesiredAccess
0x18008a8eb  mov     [rbp+70h+ObjectAttributes.Attributes], 40h ; '@'
0x18008a8f2  lea     rcx, [rsp+170h+FileHandle]; FileHandle
0x18008a8f7  mov     [rsp+170h+ShareAccess], 7; ShareAccess
0x18008a8ff  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a904  call    cs:__imp_NtOpenFile
0x18008a90a  test    eax, eax
0x18008a90c  js      short loc_18008A989
0x18008a90e  mov     rdx, [rsp+170h+FileHandle]
0x18008a913  lea     rbx, [r14+0A0h]
0x18008a91a  mov     rcx, rbx
0x18008a91d  mov     qword ptr [rsp+170h+ShareAccess], 0
0x18008a926  mov     r9, r14
0x18008a929  lea     r8, PerfpNotificationCallback
0x18008a930  call    cs:__imp_TpAllocIoCompletion
0x18008a936  mov     edi, eax
0x18008a938  test    eax, eax
0x18008a93a  js      short loc_18008A994
0x18008a93c  mov     rcx, [rbx]
0x18008a93f  call    cs:__imp_TpStartAsyncIoOperation
0x18008a945  mov     r8, [rsp+170h+FileHandle]
0x18008a94a  lea     rcx, [r14+0A8h]; OutputBuffer
0x18008a951  lea     rdx, [rbp+70h+DestinationString]
0x18008a955  call    PcwRegisterCounterSet
0x18008a95a  mov     rcx, [rsp+170h+FileHandle]; Handle
0x18008a95f  mov     edi, eax
0x18008a961  call    cs:__imp_NtClose
0x18008a967  test    edi, edi
0x18008a969  js      short loc_18008A9A9
0x18008a96b  xor     eax, eax
0x18008a96d  mov     rcx, [rbp+70h+var_40]
0x18008a971  xor     rcx, rsp; StackCookie
0x18008a974  call    __security_check_cookie
0x18008a979  add     rsp, 148h
0x18008a980  pop     r15
0x18008a982  pop     r14
0x18008a984  pop     rdi
0x18008a985  pop     rsi
0x18008a986  pop     rbx
0x18008a987  pop     rbp
0x18008a988  retn
0x18008a989  cmp     eax, 0C0000034h
0x18008a98e  jz      short loc_18008A9BD
0x18008a990  mov     ecx, eax
0x18008a992  jmp     short loc_18008A9A1
0x18008a994  mov     rcx, [rsp+170h+FileHandle]; Handle
0x18008a999  call    cs:__imp_NtClose
0x18008a99f  mov     ecx, edi; Status
0x18008a9a1  call    cs:__imp_RtlNtStatusToDosError
0x18008a9a7  jmp     short loc_18008A96D
0x18008a9a9  mov     rcx, [rbx]
0x18008a9ac  call    cs:__imp_TpCancelAsyncIoOperation
0x18008a9b2  mov     rcx, [rbx]
0x18008a9b5  call    cs:__imp_TpReleaseIoCompletion
0x18008a9bb  jmp     short loc_18008A99F
0x18008a9bd  mov     qword ptr [r14+0A0h], 0
0x18008a9c8  mov     qword ptr [r14+0A8h], 0
0x18008a9d3  test    cs:Microsoft_Windows_Diagnosis_PCWEnableBits, 20h
0x18008a9da  jz      short loc_18008A96B
0x18008a9dc  lea     r8, [r14+0D0h]
0x18008a9e3  mov     r9, r15
0x18008a9e6  call    McTemplateU0jj_EtwEventWriteTransfer
0x18008a9eb  jmp     loc_18008A96B
```
