# DavGetExtendedError

- ea: `0x180005a70`
- end: `0x180005c75`
- name: `DavGetExtendedError`
- size: `517`
- prototype: `DWORD __stdcall(HANDLE hFile, DWORD *ExtError, LPWSTR ExtErrorString, DWORD *cChSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005a70`
- `0x180005d38`
- `0x1800060d9`
- `0x180006100`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180005b9a`
- `ntdll!NtCreateFile` at `0x180005b9a`
- `ntdll!RtlNtStatusToDosError` at `0x180005ba6`
- `ntdll!RtlNtStatusToDosError` at `0x180005bfc`
- `ntdll!RtlNtStatusToDosError` at `0x180005ba6`
- `ntdll!RtlNtStatusToDosError` at `0x180005bfc`
- `ntdll!NtFsControlFile` at `0x180005bf0`
- `ntdll!NtFsControlFile` at `0x180005bf0`
- `ntdll!NtClose` at `0x180005c43`
- `ntdll!NtClose` at `0x180005c43`
- `ntdll!RtlInitUnicodeString` at `0x180005b2e`
- `ntdll!RtlInitUnicodeString` at `0x180005b2e`

## pseudocode

```c
DWORD __stdcall DavGetExtendedError(HANDLE hFile, DWORD *ExtError, LPWSTR ExtErrorString, DWORD *cChSize)
{
  HANDLE v6; // rbx
  __int64 v9; // rdi
  int v10; // r15d
  int v11; // eax
  ULONG v12; // ebx
  int v13; // eax
  HRESULT v14; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  DWORD OutputBuffer; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszSrc[1030]; // [rsp+C4h] [rbp-3Ch] BYREF

  FileHandle = hFile;
  v6 = hFile;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  memset_0(&OutputBuffer, 0, 0x804u);
  if ( cChSize && ExtErrorString && ExtError )
  {
    if ( *cChSize < 0x400 )
    {
      *cChSize = 1024;
      return 122;
    }
    v9 = -1;
    v10 = 0;
    if ( v6 == (HANDLE)-1LL )
    {
      RtlInitUnicodeString(&DestinationString, L"\\device\\webdavredirector");
      v10 = 1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      IoStatusBlock.Status = 0;
      IoStatusBlock.Information = 0;
      v11 = NtCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0, 0, 0);
      if ( v11 < 0 )
        return RtlNtStatusToDosError(v11);
      v6 = FileHandle;
    }
    v13 = NtFsControlFile(v6, 0, 0, 0, &IoStatusBlock, 0x4000080u, 0, 0, &OutputBuffer, 0x804u);
    if ( v13 >= 0 )
    {
      *ExtError = OutputBuffer;
      v14 = StringCchCopyW(ExtErrorString, 0x400u, pszSrc);
      if ( v14 >= 0 )
      {
        v12 = 0;
        do
          ++v9;
        while ( ExtErrorString[v9] );
        *cChSize = v9 + 1;
      }
      else
      {
        v12 = (unsigned __int16)v14;
      }
    }
    else
    {
      v12 = RtlNtStatusToDosError(v13);
    }
    if ( v10 )
      NtClose(FileHandle);
    return v12;
  }
  return 87;
}

```

## disassembly

```asm
0x180005a70  push    rbp
0x180005a72  push    rbx
0x180005a73  push    rsi
0x180005a74  push    rdi
0x180005a75  push    r12
0x180005a77  push    r13
0x180005a79  push    r14
0x180005a7b  push    r15
0x180005a7d  lea     rbp, [rsp-7E8h]
0x180005a85  sub     rsp, 8E8h
0x180005a8c  mov     rax, cs:__security_cookie
0x180005a93  xor     rax, rsp
0x180005a96  mov     [rbp+820h+var_50], rax
0x180005a9d  xorps   xmm0, xmm0
0x180005aa0  mov     [rsp+920h+FileHandle], rcx
0x180005aa5  mov     r14, r8
0x180005aa8  mov     r12, rdx
0x180005aab  mov     rbx, rcx
0x180005aae  xor     r13d, r13d
0x180005ab1  xor     edx, edx; Val
0x180005ab3  mov     qword ptr [rsp+920h+DestinationString.Length], r13
0x180005ab8  mov     r8d, 804h; Size
0x180005abe  mov     [rsp+920h+DestinationString.Buffer], r13
0x180005ac3  lea     rcx, [rbp+820h+OutputBuffer]; void *
0x180005ac7  mov     rsi, r9
0x180005aca  movups  xmmword ptr [rbp+820h+ObjectAttributes.Length], xmm0
0x180005ace  movups  xmmword ptr [rbp+820h+ObjectAttributes.ObjectName], xmm0
0x180005ad2  movups  xmmword ptr [rbp+820h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005ad6  movups  xmmword ptr [rsp+920h+IoStatusBlock], xmm0
0x180005adb  call    memset_0
0x180005ae0  test    rsi, rsi
0x180005ae3  jz      loc_180005C4D
0x180005ae9  test    r14, r14
0x180005aec  jz      loc_180005C4D
0x180005af2  test    r12, r12
0x180005af5  jz      loc_180005C4D
0x180005afb  cmp     dword ptr [rsi], 400h
0x180005b01  jnb     short loc_180005B12
0x180005b03  mov     dword ptr [rsi], 400h
0x180005b09  lea     eax, [r13+7Ah]
0x180005b0d  jmp     loc_180005C52
0x180005b12  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005b16  mov     r15d, r13d
0x180005b19  cmp     rbx, rdi
0x180005b1c  jnz     loc_180005BB8
0x180005b22  lea     rdx, SourceString; "\\device\\webdavredirector"
0x180005b29  lea     rcx, [rsp+920h+DestinationString]; DestinationString
0x180005b2e  call    cs:__imp_RtlInitUnicodeString
0x180005b34  mov     [rsp+920h+EaLength], r13d; EaLength
0x180005b39  lea     rax, [rsp+920h+DestinationString]
0x180005b3e  mov     [rsp+920h+EaBuffer], r13; EaBuffer
0x180005b43  lea     r15d, [rdi+2]
0x180005b47  mov     [rsp+920h+CreateOptions], r13d; CreateOptions
0x180005b4c  lea     r9, [rsp+920h+IoStatusBlock]; IoStatusBlock
0x180005b51  mov     [rsp+920h+CreateDisposition], r15d; CreateDisposition
0x180005b56  lea     r8, [rbp+820h+ObjectAttributes]; ObjectAttributes
0x180005b5a  mov     [rsp+920h+ShareAccess], 7; ShareAccess
0x180005b62  lea     rcx, [rsp+920h+FileHandle]; FileHandle
0x180005b67  xorps   xmm0, xmm0
0x180005b6a  mov     [rsp+920h+FileAttributes], r13d; FileAttributes
0x180005b6f  mov     edx, 80000000h; DesiredAccess
0x180005b74  mov     [rsp+920h+AllocationSize], r13; AllocationSize
0x180005b79  mov     [rbp+820h+ObjectAttributes.Length], 30h ; '0'
0x180005b80  mov     [rbp+820h+ObjectAttributes.RootDirectory], r13
0x180005b84  mov     [rbp+820h+ObjectAttributes.Attributes], r13d
0x180005b88  mov     [rbp+820h+ObjectAttributes.ObjectName], rax
0x180005b8c  movdqu  xmmword ptr [rbp+820h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005b91  mov     dword ptr [rsp+920h+IoStatusBlock], r13d
0x180005b96  mov     [rbp+820h+IoStatusBlock.Information], r13
0x180005b9a  call    cs:__imp_NtCreateFile
0x180005ba0  test    eax, eax
0x180005ba2  jns     short loc_180005BB3
0x180005ba4  mov     ecx, eax; Status
0x180005ba6  call    cs:__imp_RtlNtStatusToDosError
0x180005bac  mov     ebx, eax
0x180005bae  jmp     loc_180005C49
0x180005bb3  mov     rbx, [rsp+920h+FileHandle]
0x180005bb8  mov     dword ptr [rsp+920h+EaBuffer], 804h; OutputBufferLength
0x180005bc0  lea     rax, [rbp+820h+OutputBuffer]
0x180005bc4  mov     qword ptr [rsp+920h+CreateOptions], rax; OutputBuffer
0x180005bc9  xor     r9d, r9d; ApcContext
0x180005bcc  mov     [rsp+920h+CreateDisposition], r13d; InputBufferLength
0x180005bd1  lea     rax, [rsp+920h+IoStatusBlock]
0x180005bd6  mov     qword ptr [rsp+920h+ShareAccess], r13; InputBuffer
0x180005bdb  xor     r8d, r8d; ApcRoutine
0x180005bde  mov     [rsp+920h+FileAttributes], 4000080h; FsControlCode
0x180005be6  xor     edx, edx; Event
0x180005be8  mov     rcx, rbx; FileHandle
0x180005beb  mov     [rsp+920h+AllocationSize], rax; IoStatusBlock
0x180005bf0  call    cs:__imp_NtFsControlFile
0x180005bf6  test    eax, eax
0x180005bf8  jns     short loc_180005C06
0x180005bfa  mov     ecx, eax; Status
0x180005bfc  call    cs:__imp_RtlNtStatusToDosError
0x180005c02  mov     ebx, eax
0x180005c04  jmp     short loc_180005C39
0x180005c06  mov     eax, [rbp+820h+OutputBuffer]
0x180005c09  lea     r8, [rbp+820h+pszSrc]; pszSrc
0x180005c0d  mov     edx, 400h; cchDest
0x180005c12  mov     [r12], eax
0x180005c16  mov     rcx, r14; pszDest
0x180005c19  call    StringCchCopyW
0x180005c1e  test    eax, eax
0x180005c20  jns     short loc_180005C27
0x180005c22  movzx   ebx, ax
0x180005c25  jmp     short loc_180005C39
0x180005c27  mov     ebx, r13d
0x180005c2a  inc     rdi
0x180005c2d  cmp     [r14+rdi*2], r13w
0x180005c32  jnz     short loc_180005C2A
0x180005c34  lea     eax, [rdi+1]
0x180005c37  mov     [rsi], eax
0x180005c39  test    r15d, r15d
0x180005c3c  jz      short loc_180005C49
0x180005c3e  mov     rcx, [rsp+920h+FileHandle]; Handle
0x180005c43  call    cs:__imp_NtClose
0x180005c49  mov     eax, ebx
0x180005c4b  jmp     short loc_180005C52
0x180005c4d  mov     eax, 57h ; 'W'
0x180005c52  mov     rcx, [rbp+820h+var_50]
0x180005c59  xor     rcx, rsp; StackCookie
0x180005c5c  call    __security_check_cookie
0x180005c61  add     rsp, 8E8h
0x180005c68  pop     r15
0x180005c6a  pop     r14
0x180005c6c  pop     r13
0x180005c6e  pop     r12
0x180005c70  pop     rdi
0x180005c71  pop     rsi
0x180005c72  pop     rbx
0x180005c73  pop     rbp
0x180005c74  retn
```
