# OpenFileRelativeToParent

- ea: `0x1400129b8`
- end: `0x140012c51`
- name: `OpenFileRelativeToParent`
- size: `665`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64, unsigned __int8, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012c58`
- `0x140013a18`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14001093c`
- `0x1400129b8`
- `0x140014104`
- `0x140014cd0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x140012bba`
- `ntdll!NtCreateFile` at `0x140012bba`

## string_xrefs

- `0x140012a09`: `No path specified`
- `0x140012ae7`: `Invalid path specified`
- `0x140012be6`: `Failed to open {}`

## pseudocode

```c
int __fastcall OpenFileRelativeToParent(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned __int8 a5, _QWORD *a6)
{
  int v6; // edx
  __int64 v7; // rdx
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // r9
  void **v12; // r10
  void *v13; // r11
  int v14; // edx
  NTSTATUS v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // ebx
  int v18; // edx
  int AllocationSize; // [rsp+20h] [rbp-69h]
  int AllocationSizea; // [rsp+20h] [rbp-69h]
  int v21[2]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v22[2]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v23; // [rsp+78h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  int v25; // [rsp+B0h] [rbp+27h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v23 = a2;
  if ( !a2 )
  {
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      *(_QWORD *)v21 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v7 = 967;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      AllocationSize);
    return -2147024809;
  }
  if ( !a6 )
  {
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file handle specified");
      *(_QWORD *)v21 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v7 = 968;
    goto LABEL_5;
  }
  *a6 = -1;
  v10 = FileFromPath(a2);
  if ( !v10 )
  {
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid path specified");
      *(_QWORD *)v21 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v7 = 973;
    goto LABEL_5;
  }
  v22[0] = 0;
  v22[1] = v10;
  do
    ++v11;
  while ( *(_WORD *)(v10 + 2 * v11) );
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v22;
  LOWORD(v22[0]) = 2 * v11;
  WORD1(v22[0]) = 2 * v11 + 2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = v13;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v15 = NtCreateFile(
          v12,
          0x110180u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          7u,
          1u,
          ((a5 ^ 1) << 21) + 16416,
          0,
          0);
  v17 = v15;
  if ( v15 >= 0 )
    return 0;
  v25 = v15;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to open {}",
      (__int64)&v23);
    *(_QWORD *)v21 = &v25;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v18,
      3,
      (unsigned int)": {}",
      (__int64)v21);
  }
  return wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x3EB, v16, (const char *)v17, AllocationSizea);
}

```

## disassembly

```asm
0x1400129b8  mov     [rsp-8+arg_10], rbx
0x1400129bd  mov     [rsp-8+arg_18], rdi
0x1400129c2  push    rbp
0x1400129c3  lea     rbp, [rsp-47h]
0x1400129c8  sub     rsp, 0D0h
0x1400129cf  mov     rax, cs:__security_cookie
0x1400129d6  xor     rax, rsp
0x1400129d9  mov     [rbp+47h+var_8], rax
0x1400129dd  mov     r10, [rbp+47h+arg_28]
0x1400129e1  xor     edi, edi
0x1400129e3  mov     [rbp+47h+var_58], rdx
0x1400129e7  mov     r11, rcx
0x1400129ea  test    rdx, rdx
0x1400129ed  jnz     short loc_140012A5B
0x1400129ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400129f6  mov     ebx, 80070057h
0x1400129fb  mov     [rbp+47h+var_20], ebx
0x1400129fe  test    rcx, rcx
0x140012a01  jz      short loc_140012A3C
0x140012a03  lea     edi, [rdx+3]
0x140012a06  mov     r8d, edi
0x140012a09  lea     r9, aNoPathSpecifie; "No path specified"
0x140012a10  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012a15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012a1c  lea     rax, [rbp+47h+var_20]
0x140012a20  mov     qword ptr [rbp+47h+var_70], rax
0x140012a24  lea     r9, asc_140030534; ": {}"
0x140012a2b  lea     rax, [rbp+47h+var_70]
0x140012a2f  mov     r8d, edi
0x140012a32  mov     [rsp+0D0h+AllocationSize], rax; int
0x140012a37  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012a3c  mov     edx, 3C7h; void *
0x140012a41  mov     rcx, [rbp+4Fh]; this
0x140012a45  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140012a4c  mov     r9d, ebx; char *
0x140012a4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a54  mov     eax, ebx
0x140012a56  jmp     loc_140012C30
0x140012a5b  test    r10, r10
0x140012a5e  jnz     short loc_140012AB7
0x140012a60  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012a67  mov     ebx, 80070057h
0x140012a6c  mov     [rbp+47h+var_20], ebx
0x140012a6f  test    rcx, rcx
0x140012a72  jz      short loc_140012AB0
0x140012a74  lea     edi, [r10+3]
0x140012a78  xor     edx, edx
0x140012a7a  mov     r8d, edi
0x140012a7d  lea     r9, aNoFileHandleSp; "No file handle specified"
0x140012a84  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012a89  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012a90  lea     rax, [rbp+47h+var_20]
0x140012a94  mov     qword ptr [rbp+47h+var_70], rax
0x140012a98  lea     r9, asc_140030534; ": {}"
0x140012a9f  lea     rax, [rbp+47h+var_70]
0x140012aa3  mov     r8d, edi
0x140012aa6  mov     [rsp+0D0h+AllocationSize], rax
0x140012aab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012ab0  mov     edx, 3C8h
0x140012ab5  jmp     short loc_140012A41
0x140012ab7  or      r9, 0FFFFFFFFFFFFFFFFh
0x140012abb  mov     rcx, rdx
0x140012abe  mov     [r10], r9
0x140012ac1  call    FileFromPath
0x140012ac6  test    rax, rax
0x140012ac9  jnz     short loc_140012B24
0x140012acb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012ad2  mov     ebx, 80070057h
0x140012ad7  mov     [rbp+47h+var_20], ebx
0x140012ada  test    rcx, rcx
0x140012add  jz      short loc_140012B1A
0x140012adf  lea     edi, [rax+3]
0x140012ae2  xor     edx, edx
0x140012ae4  mov     r8d, edi
0x140012ae7  lea     r9, aInvalidPathSpe; "Invalid path specified"
0x140012aee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012af3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012afa  lea     rax, [rbp+47h+var_20]
0x140012afe  mov     qword ptr [rbp+47h+var_70], rax
0x140012b02  lea     r9, asc_140030534; ": {}"
0x140012b09  lea     rax, [rbp+47h+var_70]
0x140012b0d  mov     r8d, edi
0x140012b10  mov     [rsp+0D0h+AllocationSize], rax
0x140012b15  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012b1a  mov     edx, 3CDh
0x140012b1f  jmp     loc_140012A41
0x140012b24  mov     [rbp+47h+var_68], rdi
0x140012b28  mov     [rbp+47h+var_60], rax
0x140012b2c  inc     r9
0x140012b2f  cmp     [rax+r9*2], di
0x140012b34  jnz     short loc_140012B2C
0x140012b36  mov     [rsp+0D0h+EaLength], edi; EaLength
0x140012b3a  lea     rax, [rbp+47h+var_68]
0x140012b3e  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x140012b42  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x140012b46  movzx   eax, [rbp+47h+arg_20]
0x140012b4a  add     r9w, r9w
0x140012b4e  mov     [rsp+0D0h+EaBuffer], rdi; EaBuffer
0x140012b53  xor     eax, 1
0x140012b56  mov     word ptr [rbp+47h+var_68], r9w
0x140012b5b  xorps   xmm0, xmm0
0x140012b5e  add     r9w, 2
0x140012b63  shl     eax, 15h
0x140012b66  add     eax, 4020h
0x140012b6b  mov     word ptr [rbp+47h+var_68+2], r9w
0x140012b70  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x140012b74  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x140012b78  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x140012b80  mov     edx, 110180h; DesiredAccess
0x140012b85  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x140012b8d  mov     rcx, r10; FileHandle
0x140012b90  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x140012b98  mov     [rsp+0D0h+AllocationSize], rdi; AllocationSize
0x140012b9d  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x140012ba5  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x140012bad  mov     [rbp+47h+ObjectAttributes.RootDirectory], r11
0x140012bb1  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x140012bb6  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x140012bba  call    cs:__imp_NtCreateFile
0x140012bc0  mov     ebx, eax
0x140012bc2  test    eax, eax
0x140012bc4  jns     short loc_140012C2E
0x140012bc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012bcd  mov     [rbp+47h+var_20], eax
0x140012bd0  test    rcx, rcx
0x140012bd3  jz      short loc_140012C1B
0x140012bd5  lea     rax, [rbp+47h+var_58]
0x140012bd9  mov     edi, 3
0x140012bde  mov     r8d, edi
0x140012be1  mov     [rsp+0D0h+AllocationSize], rax
0x140012be6  lea     r9, aFailedToOpen; "Failed to open {}"
0x140012bed  xor     edx, edx
0x140012bef  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140012bf4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012bfb  lea     rax, [rbp+47h+var_20]
0x140012bff  mov     qword ptr [rbp+47h+var_70], rax
0x140012c03  lea     r9, asc_140030534; ": {}"
0x140012c0a  lea     rax, [rbp+47h+var_70]
0x140012c0e  mov     r8d, edi
0x140012c11  mov     [rsp+0D0h+AllocationSize], rax; int
0x140012c16  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140012c1b  mov     rcx, [rbp+4Fh]; this
0x140012c1f  mov     r9d, ebx; char *
0x140012c22  mov     edx, 3EBh; void *
0x140012c27  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140012c2c  jmp     short loc_140012C30
0x140012c2e  xor     eax, eax
0x140012c30  mov     rcx, [rbp+47h+var_8]
0x140012c34  xor     rcx, rsp; StackCookie
0x140012c37  call    __security_check_cookie
0x140012c3c  lea     r11, [rsp+0D0h+var_s0]
0x140012c44  mov     rbx, [r11+20h]
0x140012c48  mov     rdi, [r11+28h]
0x140012c4c  mov     rsp, r11
0x140012c4f  pop     rbp
0x140012c50  retn
```
