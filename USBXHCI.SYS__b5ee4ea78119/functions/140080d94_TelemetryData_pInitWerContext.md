# TelemetryData_pInitWerContext

- ea: `0x140080d94`
- end: `0x1400810e0`
- name: `TelemetryData_pInitWerContext`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400809b8`

## callees

- `0x140045064`
- `0x140059970`
- `0x140059a80`
- `0x140059d80`
- `0x140080d94`
- `0x1400812a4`
- `0x1400812cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140080f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080f8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080fbf`
- `ntoskrnl!ExAllocatePool2` at `0x140080f26`
- `ntoskrnl!ExAllocatePool2` at `0x140080f26`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081009`
- `ntoskrnl!RtlInitUnicodeString` at `0x140081009`
- `ntoskrnl!IoCreateFile` at `0x140081089`
- `ntoskrnl!IoCreateFile` at `0x140081089`
- `ntoskrnl!ZwClose` at `0x140080e79`
- `ntoskrnl!ZwClose` at `0x14008109f`
- `ntoskrnl!ZwClose` at `0x140080e79`
- `ntoskrnl!ZwClose` at `0x14008109f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140080ef0`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140080f71`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140080ef0`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140080f71`
- `ntoskrnl!ZwOpenKey` at `0x140080e4c`
- `ntoskrnl!ZwOpenKey` at `0x140080e4c`

## string_xrefs

- `0x140080dd3`: `LiveKernelReportsPath`

## pseudocode

```c
__int64 __fastcall TelemetryData_pInitWerContext(__int64 a1)
{
  int v2; // ebx
  _DWORD *v3; // rbx
  unsigned int v4; // eax
  size_t v5; // r8
  __int64 v6; // rsi
  NTSTATUS PersistedStateLocation; // ebx
  void *Pool2; // rdi
  NTSTATUS v9; // eax
  unsigned int v11; // [rsp+70h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v13; // [rsp+80h] [rbp-80h]
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v15[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES v19; // [rsp+D0h] [rbp-30h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  wchar_t pszDest[264]; // [rsp+130h] [rbp+30h] BYREF

  v15[0] = 2883628;
  *(_QWORD *)&ValueName.Length = 2883628;
  v15[1] = L"LiveKernelReportsPath";
  ValueName.Buffer = L"LiveKernelReportsPath";
  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&v19, 0, sizeof(v19));
  memset(pszDest, 0, 0x208u);
  v11 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0
    && (v13 = 0, v2 = RegRetrieveValueInfo(KeyHandle, &ValueName), ZwClose(KeyHandle), v2 >= 0)
    && (v3 = v13) != 0
    && v13[1] == 1 )
  {
    v4 = v13[2];
    v5 = 518;
    if ( v4 <= 0x206 )
      v5 = v4;
    v6 = a1 + 104;
    memmove((void *)(a1 + 104), v13 + 3, v5);
    RegFreeInfo(v3);
  }
  else
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"LiveKernelReports",
                               0,
                               L"\\SystemRoot\\LiveKernelReports",
                               1,
                               0,
                               0,
                               &v11);
    if ( PersistedStateLocation != -2147483643 || v11 > 0x104 )
      return (unsigned int)PersistedStateLocation;
    Pool2 = (void *)ExAllocatePool2(64, v11, 1952531540);
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"LiveKernelReports",
                               0,
                               L"\\SystemRoot\\LiveKernelReports",
                               1,
                               Pool2,
                               v11,
                               &v11);
    if ( PersistedStateLocation < 0 )
    {
      ExFreePoolWithTag(Pool2, 0x74614454u);
      return (unsigned int)PersistedStateLocation;
    }
    v6 = a1 + 104;
    RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(a1 + 104), 0x208u, L"%ws", Pool2);
    ExFreePoolWithTag(Pool2, 0x74614454u);
  }
  *(_WORD *)(a1 + 622) = 0;
  PersistedStateLocation = RtlStringCbPrintfW(pszDest, 0x208u, L"%ws\\%ws", v6, a1 + 624);
  if ( PersistedStateLocation >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    v19.Length = 48;
    v19.RootDirectory = 0;
    v19.Attributes = 576;
    v19.ObjectName = &DestinationString;
    *(_OWORD *)&v19.SecurityDescriptor = 0;
    v9 = IoCreateFile(
           &FileHandle,
           0x10000000u,
           &v19,
           &IoStatusBlock,
           0,
           0x80u,
           3u,
           2u,
           1u,
           0,
           0,
           CreateFileTypeNone,
           0,
           0x100u);
    PersistedStateLocation = v9;
    if ( v9 < 0 )
    {
      if ( v9 == -1073741771 || IoStatusBlock.Information == 4 )
        return 0;
    }
    else
    {
      ZwClose(FileHandle);
    }
  }
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x140080d94  push    rbp
0x140080d96  push    rbx
0x140080d97  push    rsi
0x140080d98  push    rdi
0x140080d99  push    r14
0x140080d9b  push    r15
0x140080d9d  lea     rbp, [rsp-258h]
0x140080da5  sub     rsp, 358h
0x140080dac  mov     rax, cs:__security_cookie
0x140080db3  xor     rax, rsp
0x140080db6  mov     [rbp+280h+var_40], rax
0x140080dbd  xorps   xmm1, xmm1
0x140080dc0  mov     [rbp+280h+var_2F0], 2C002Ch
0x140080dc8  mov     r14, rcx
0x140080dcb  mov     qword ptr [rbp+280h+ValueName.Length], 2C002Ch
0x140080dd3  lea     rcx, aLivekernelrepo_0; "LiveKernelReportsPath"
0x140080dda  xorps   xmm0, xmm0
0x140080ddd  mov     [rbp+280h+var_2E8], rcx
0x140080de1  xor     r15d, r15d
0x140080de4  mov     [rbp+280h+ValueName.Buffer], rcx
0x140080de8  xor     edx, edx; Val
0x140080dea  lea     rcx, [rbp+280h+pszDest]; void *
0x140080dee  mov     [rbp+280h+FileHandle], r15
0x140080df2  mov     r8d, 208h; Size
0x140080df8  movups  xmmword ptr [rbp+280h+DestinationString.Length], xmm0
0x140080dfc  movups  xmmword ptr [rbp+280h+IoStatusBlock.___u0], xmm0
0x140080e00  movups  xmmword ptr [rbp+280h+var_2B0.Length], xmm1
0x140080e04  movups  xmmword ptr [rbp+280h+var_2B0.ObjectName], xmm1
0x140080e08  movups  xmmword ptr [rbp+280h+var_2B0.SecurityDescriptor], xmm1
0x140080e0c  call    memset
0x140080e11  lea     rax, [rbp+280h+var_2F0]
0x140080e15  mov     [rsp+380h+var_310], r15d
0x140080e1a  xorps   xmm0, xmm0
0x140080e1d  mov     [rbp+280h+ObjectAttributes.ObjectName], rax
0x140080e21  lea     r8, [rbp+280h+ObjectAttributes]; ObjectAttributes
0x140080e25  mov     [rsp+380h+KeyHandle], r15
0x140080e2a  lea     edx, [r15+1]; DesiredAccess
0x140080e2e  mov     qword ptr [rbp+280h+ObjectAttributes.Length], 30h ; '0'
0x140080e36  lea     rcx, [rsp+380h+KeyHandle]; KeyHandle
0x140080e3b  mov     qword ptr [rbp+280h+ObjectAttributes.Attributes], 240h
0x140080e43  movdqu  xmmword ptr [rbp+280h+ObjectAttributes.SecurityDescriptor], xmm0
0x140080e48  mov     [rbp+280h+ObjectAttributes.RootDirectory], r15
0x140080e4c  call    cs:__imp_ZwOpenKey
0x140080e53  nop     dword ptr [rax+rax+00h]
0x140080e58  test    eax, eax
0x140080e5a  js      short loc_140080EC6
0x140080e5c  mov     rcx, [rsp+380h+KeyHandle]; KeyHandle
0x140080e61  lea     r8, [rbp+280h+var_300]
0x140080e65  lea     rdx, [rbp+280h+ValueName]; ValueName
0x140080e69  mov     [rbp+280h+var_300], r15
0x140080e6d  call    RegRetrieveValueInfo
0x140080e72  mov     rcx, [rsp+380h+KeyHandle]; Handle
0x140080e77  mov     ebx, eax
0x140080e79  call    cs:__imp_ZwClose
0x140080e80  nop     dword ptr [rax+rax+00h]
0x140080e85  test    ebx, ebx
0x140080e87  js      short loc_140080EC6
0x140080e89  mov     rbx, [rbp+280h+var_300]
0x140080e8d  test    rbx, rbx
0x140080e90  jz      short loc_140080EC6
0x140080e92  cmp     dword ptr [rbx+4], 1
0x140080e96  jnz     short loc_140080EC6
0x140080e98  mov     eax, [rbx+8]
0x140080e9b  mov     r8d, 206h
0x140080ea1  cmp     eax, r8d
0x140080ea4  ja      short loc_140080EA9
0x140080ea6  mov     r8d, eax; Size
0x140080ea9  lea     rsi, [r14+68h]
0x140080ead  mov     rcx, rsi; void *
0x140080eb0  lea     rdx, [rbx+0Ch]; Src
0x140080eb4  call    memmove
0x140080eb9  mov     rcx, rbx
0x140080ebc  call    RegFreeInfo
0x140080ec1  jmp     loc_140080FCB
0x140080ec6  lea     rax, [rsp+380h+var_310]
0x140080ecb  mov     r9d, 1
0x140080ed1  mov     qword ptr [rsp+380h+ShareAccess], rax
0x140080ed6  lea     r8, aSystemrootLive; "\\SystemRoot\\LiveKernelReports"
0x140080edd  mov     [rsp+380h+FileAttributes], r15d
0x140080ee2  lea     rcx, aLivekernelrepo; "LiveKernelReports"
0x140080ee9  xor     edx, edx
0x140080eeb  mov     [rsp+380h+AllocationSize], r15
0x140080ef0  call    cs:__imp_RtlGetPersistedStateLocation
0x140080ef7  nop     dword ptr [rax+rax+00h]
0x140080efc  mov     ebx, eax
0x140080efe  cmp     eax, 80000005h
0x140080f03  jnz     loc_1400810BE
0x140080f09  cmp     [rsp+380h+var_310], 104h
0x140080f11  ja      loc_1400810BE
0x140080f17  mov     edx, [rsp+380h+var_310]
0x140080f1b  mov     ecx, 40h ; '@'
0x140080f20  mov     r8d, 74614454h
0x140080f26  call    cs:__imp_ExAllocatePool2
0x140080f2d  nop     dword ptr [rax+rax+00h]
0x140080f32  mov     rdi, rax
0x140080f35  test    rax, rax
0x140080f38  jnz     short loc_140080F44
0x140080f3a  mov     ebx, 0C000009Ah
0x140080f3f  jmp     loc_1400810BE
0x140080f44  lea     rax, [rsp+380h+var_310]
0x140080f49  mov     r9d, 1
0x140080f4f  mov     qword ptr [rsp+380h+ShareAccess], rax
0x140080f54  lea     r8, aSystemrootLive; "\\SystemRoot\\LiveKernelReports"
0x140080f5b  mov     eax, [rsp+380h+var_310]
0x140080f5f  lea     rcx, aLivekernelrepo; "LiveKernelReports"
0x140080f66  mov     [rsp+380h+FileAttributes], eax
0x140080f6a  xor     edx, edx
0x140080f6c  mov     [rsp+380h+AllocationSize], rdi
0x140080f71  call    cs:__imp_RtlGetPersistedStateLocation
0x140080f78  nop     dword ptr [rax+rax+00h]
0x140080f7d  mov     ebx, eax
0x140080f7f  test    eax, eax
0x140080f81  jns     short loc_140080F9C
0x140080f83  mov     edx, 74614454h; Tag
0x140080f88  mov     rcx, rdi; P
0x140080f8b  call    cs:__imp_ExFreePoolWithTag
0x140080f92  nop     dword ptr [rax+rax+00h]
0x140080f97  jmp     loc_1400810BE
0x140080f9c  lea     rsi, [r14+68h]
0x140080fa0  mov     r9, rdi
0x140080fa3  mov     rcx, rsi; pszDest
0x140080fa6  lea     r8, aWs; "%ws"
0x140080fad  mov     edx, 208h; cbDest
0x140080fb2  call    RtlStringCbPrintfW
0x140080fb7  mov     edx, 74614454h; Tag
0x140080fbc  mov     rcx, rdi; P
0x140080fbf  call    cs:__imp_ExFreePoolWithTag
0x140080fc6  nop     dword ptr [rax+rax+00h]
0x140080fcb  lea     rax, [r14+270h]
0x140080fd2  mov     [r14+26Eh], r15w
0x140080fda  mov     r9, rsi
0x140080fdd  mov     [rsp+380h+AllocationSize], rax
0x140080fe2  lea     r8, aWsWs; "%ws\\%ws"
0x140080fe9  mov     edx, 208h; cbDest
0x140080fee  lea     rcx, [rbp+280h+pszDest]; pszDest
0x140080ff2  call    RtlStringCbPrintfW
0x140080ff7  mov     ebx, eax
0x140080ff9  test    eax, eax
0x140080ffb  js      loc_1400810BE
0x140081001  lea     rdx, [rbp+280h+pszDest]; SourceString
0x140081005  lea     rcx, [rbp+280h+DestinationString]; DestinationString
0x140081009  call    cs:__imp_RtlInitUnicodeString
0x140081010  nop     dword ptr [rax+rax+00h]
0x140081015  mov     [rsp+380h+Options], 100h; Options
0x14008101d  lea     rax, [rbp+280h+DestinationString]
0x140081021  mov     [rsp+380h+InternalParameters], r15; InternalParameters
0x140081026  lea     r9, [rbp+280h+IoStatusBlock]; IoStatusBlock
0x14008102a  mov     [rsp+380h+CreateFileType], r15d; CreateFileType
0x14008102f  lea     r8, [rbp+280h+var_2B0]; ObjectAttributes
0x140081033  mov     [rsp+380h+EaLength], r15d; EaLength
0x140081038  lea     rcx, [rbp+280h+FileHandle]; FileHandle
0x14008103c  mov     [rsp+380h+EaBuffer], r15; EaBuffer
0x140081041  xorps   xmm0, xmm0
0x140081044  mov     [rsp+380h+CreateOptions], 1; CreateOptions
0x14008104c  mov     edx, 10000000h; DesiredAccess
0x140081051  mov     [rsp+380h+Disposition], 2; Disposition
0x140081059  mov     [rsp+380h+ShareAccess], 3; ShareAccess
0x140081061  mov     [rsp+380h+FileAttributes], 80h; FileAttributes
0x140081069  mov     [rsp+380h+AllocationSize], r15; AllocationSize
0x14008106e  mov     [rbp+280h+var_2B0.Length], 30h ; '0'
0x140081075  mov     [rbp+280h+var_2B0.RootDirectory], r15
0x140081079  mov     [rbp+280h+var_2B0.Attributes], 240h
0x140081080  mov     [rbp+280h+var_2B0.ObjectName], rax
0x140081084  movdqu  xmmword ptr [rbp+280h+var_2B0.SecurityDescriptor], xmm0
0x140081089  call    cs:__imp_IoCreateFile
0x140081090  nop     dword ptr [rax+rax+00h]
0x140081095  mov     ebx, eax
0x140081097  test    eax, eax
0x140081099  js      short loc_1400810AD
0x14008109b  mov     rcx, [rbp+280h+FileHandle]; Handle
0x14008109f  call    cs:__imp_ZwClose
0x1400810a6  nop     dword ptr [rax+rax+00h]
0x1400810ab  jmp     short loc_1400810BE
0x1400810ad  cmp     eax, 0C0000035h
0x1400810b2  jz      short loc_1400810BB
0x1400810b4  cmp     [rbp+280h+IoStatusBlock.Information], 4
0x1400810b9  jnz     short loc_1400810BE
0x1400810bb  mov     ebx, r15d
0x1400810be  mov     eax, ebx
0x1400810c0  mov     rcx, [rbp+280h+var_40]
0x1400810c7  xor     rcx, rsp; StackCookie
0x1400810ca  call    __security_check_cookie
0x1400810cf  add     rsp, 358h
0x1400810d6  pop     r15
0x1400810d8  pop     r14
0x1400810da  pop     rdi
0x1400810db  pop     rsi
0x1400810dc  pop     rbx
0x1400810dd  pop     rbp
0x1400810de  retn
```
