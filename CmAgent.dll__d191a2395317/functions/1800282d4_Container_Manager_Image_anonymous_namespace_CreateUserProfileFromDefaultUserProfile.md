# Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile

- ea: `0x1800282d4`
- end: `0x1800288c6`
- name: `Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile`
- size: `1522`
- prototype: `__int64 __fastcall(__int64, __int64 *, const WCHAR **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027c74`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180007b2c`
- `0x1800091a0`
- `0x18000a768`
- `0x18000adb8`
- `0x18000af30`
- `0x18000bb98`
- `0x18000c200`
- `0x180024d60`
- `0x180028078`
- `0x1800282d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800283b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800283b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002843c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002843c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028450`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002862b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002862b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800287fa`
- `ntdll!RtlAcquirePrivilege` at `0x18002832a`
- `ntdll!RtlAcquirePrivilege` at `0x18002832a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028735`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028735`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800285d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002876e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800285d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002876e`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800287ae`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800287ae`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800285fc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800285fc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002878f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002878f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800284a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800284a2`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180028572`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180028572`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028400`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180028400`

## string_xrefs

- `0x180028341`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile(
        __int64 a1,
        __int64 *a2,
        const WCHAR **a3)
{
  NTSTATUS v5; // eax
  int v6; // eax
  signed int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rsi
  const WCHAR *v11; // r13
  void *v12; // r15
  __int64 v13; // rcx
  unsigned __int64 v14; // r14
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v17; // rdi
  signed int LastError; // eax
  HANDLE v19; // rax
  __int64 v20; // rdx
  const char *v21; // r9
  __int64 v22; // rdx
  HANDLE FileW; // rax
  void *v24; // rbx
  const char *v25; // r9
  signed int v26; // edi
  int v27; // eax
  LPCWSTR *i; // rbx
  DWORD FileAttributesW; // eax
  HANDLE v30; // rdi
  const char *v31; // r9
  const char *v32; // r9
  __int64 v33; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-A9h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-A9h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-A9h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-89h] BYREF
  _WORD v39[8]; // [rsp+50h] [rbp-79h] BYREF
  PVOID ReturnedState; // [rsp+60h] [rbp-69h] BYREF
  __m128i si128; // [rsp+68h] [rbp-61h] BYREF
  __int64 v42; // [rsp+78h] [rbp-51h]
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp-49h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+88h] [rbp-41h] BYREF
  struct _FILETIME CreationTime; // [rsp+90h] [rbp-39h] BYREF
  void *v46[2]; // [rsp+98h] [rbp-31h] BYREF
  _WORD v47[8]; // [rsp+A8h] [rbp-21h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+B8h] [rbp-11h] BYREF
  ULONG Privilege[4]; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  si128.m128i_i64[0] = a1;
  ReturnedState = 0;
  *(__m128i *)Privilege = _mm_load_si128((const __m128i *)&_xmm);
  v5 = RtlAcquirePrivilege(Privilege, 4u, 2u, &ReturnedState);
  if ( v5 < 0 )
  {
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x52,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
           (const char *)(unsigned int)v5,
           dwCreationDisposition);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = (unsigned int)v6;
      v9 = 677;
LABEL_68:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)v8,
        dwCreationDisposition);
LABEL_69:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      return (unsigned int)v7;
    }
  }
  v10 = *a2;
  v11 = *a3;
  v12 = 0;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v10 + 2 * v13) );
  v14 = v13 + 171;
  *(_QWORD *)Privilege = 0;
  v15 = 2 * (v13 + 171);
  if ( is_mul_ok(v13 + 171, 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v17 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v15);
    v7 = -2147024882;
    if ( v17 )
    {
      v7 = StringCchPrintfW(
             v17,
             v14,
             L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FA;;;%s)(A;;0x00100020;;;S-1-15-3-65536-599108337-2355189375-1"
              "353122160-3480128286-3345335107-485756383-4087318168-230526575)",
             v10);
      if ( v7 >= 0 )
      {
        *(_QWORD *)Privilege = 0;
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v17, 1u, (PSECURITY_DESCRIPTOR *)Privilege, 0) )
        {
          v12 = *(void **)Privilege;
          v7 = 0;
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
        }
      }
      v19 = GetProcessHeap();
      if ( !HeapFree(v19, 0, v17) )
        GetLastError();
    }
  }
  else
  {
    v7 = -2147024362;
  }
  if ( v7 < 0
    || (*(_QWORD *)&SecurityAttributes.nLength = 24,
        SecurityAttributes.lpSecurityDescriptor = v12,
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0,
        v7 = CreateNestedDirectory(v11, &SecurityAttributes),
        LocalFree(v12),
        v7 < 0) )
  {
    v8 = (unsigned int)v7;
    v9 = 682;
    goto LABEL_68;
  }
  lpFileName[0] = v39;
  lpFileName[1] = v39;
  v39[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpFileName,
                           *(_QWORD *)si128.m128i_i64[0],
                           (__int64)(*(_QWORD *)(si128.m128i_i64[0] + 8) - *(_QWORD *)si128.m128i_i64[0]) >> 1) )
  {
    v20 = 686;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( lpFileName[0] != v39 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    v7 = -2147024882;
    goto LABEL_69;
  }
  si128.m128i_i64[0] = (__int64)L"Users\\Default";
  si128.m128i_i64[1] = 13;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpFileName) )
  {
    v20 = 687;
    goto LABEL_24;
  }
  if ( !(unsigned int)CopyProfileDirectoryEx2(lpFileName[0], *a3, 32769, 0, 0, 0) )
  {
    v22 = 696;
LABEL_29:
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v22,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
           v21);
LABEL_62:
    if ( lpFileName[0] != v39 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_69;
  }
  CreationTime = 0;
  LastAccessTime = 0;
  LastWriteTime = 0;
  FileW = CreateFileW(lpFileName[0], 1u, 0, 0, 3u, 0x2000080u, 0);
  v24 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v22 = 714;
    goto LABEL_29;
  }
  if ( !GetFileTime(FileW, &CreationTime, &LastAccessTime, &LastWriteTime) )
  {
    v26 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2CF,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            v25);
    if ( v24 )
      CloseHandle(v24);
    if ( lpFileName[0] != v39 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    v7 = v26;
    goto LABEL_69;
  }
  if ( v24 )
    CloseHandle(v24);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v42 = -1;
  v46[0] = v47;
  v46[1] = v47;
  v47[0] = 0;
  v27 = Csl::EnumerateDirectoryInternal((_DWORD)a3, (unsigned int)v46, 15, (unsigned int)&si128, (__int64)L"*");
  v7 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)(unsigned int)v27,
      dwCreationDispositiona);
    if ( v46[0] != v47 )
      operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDispositionb);
LABEL_61:
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
    goto LABEL_62;
  }
  if ( v46[0] != v47 )
    operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
  for ( i = (LPCWSTR *)si128.m128i_i64[0]; i != (LPCWSTR *)si128.m128i_i64[1]; i += 4 )
  {
    FileAttributesW = GetFileAttributesW(*i);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      v30 = CreateFileW(*i, 0x100u, 0, 0, 3u, 0x80u, 0);
      if ( v30 == (HANDLE)-1LL )
      {
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2E8,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
               v31);
        goto LABEL_61;
      }
      if ( !SetFileAttributesW(*i, 0x2002u) )
      {
        v33 = 750;
LABEL_57:
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v33,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
               v32);
        if ( v30 )
          CloseHandle(v30);
        goto LABEL_61;
      }
      if ( !SetFileTime(v30, &CreationTime, &LastAccessTime, &LastWriteTime) )
      {
        v33 = 758;
        goto LABEL_57;
      }
      if ( v30 )
        CloseHandle(v30);
    }
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
  if ( lpFileName[0] != v39 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  return 0;
}

```

## disassembly

```asm
0x1800282d4  mov     [rsp-8+arg_18], rbx
0x1800282d9  push    rbp
0x1800282da  push    rsi
0x1800282db  push    rdi
0x1800282dc  push    r12
0x1800282de  push    r13
0x1800282e0  push    r14
0x1800282e2  push    r15
0x1800282e4  lea     rbp, [rsp-27h]
0x1800282e9  sub     rsp, 0F0h
0x1800282f0  mov     rax, cs:__security_cookie
0x1800282f7  xor     rax, rsp
0x1800282fa  mov     [rbp+57h+var_40], rax
0x1800282fe  mov     r12, r8
0x180028301  mov     rsi, rdx
0x180028304  mov     qword ptr [rbp+57h+var_B8], rcx
0x180028308  xor     edi, edi
0x18002830a  mov     [rbp+57h+ReturnedState], rdi
0x18002830e  movdqa  xmm0, cs:__xmm@00000009000000080000001200000011
0x180028316  movdqu  xmmword ptr [rbp+57h+Privilege], xmm0
0x18002831b  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x18002831f  lea     edx, [rdi+4]; NumPriv
0x180028322  lea     r8d, [rdi+2]; Flags
0x180028326  lea     rcx, [rbp+57h+Privilege]; Privilege
0x18002832a  call    cs:__imp_RtlAcquirePrivilege
0x180028331  nop     dword ptr [rax+rax+00h]
0x180028336  test    eax, eax
0x180028338  jns     short loc_180028363
0x18002833a  mov     rcx, [rbp+5Fh]; this
0x18002833e  mov     r9d, eax; char *
0x180028341  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180028348  lea     edx, [rdi+52h]; void *
0x18002834b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180028350  mov     ebx, eax
0x180028352  test    eax, eax
0x180028354  jns     short loc_180028363
0x180028356  mov     r9d, eax
0x180028359  mov     edx, 2A5h
0x18002835e  jmp     loc_180028883
0x180028363  mov     rsi, [rsi]
0x180028366  mov     r13, [r12]
0x18002836a  mov     r15, rdi
0x18002836d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028371  inc     rcx
0x180028374  cmp     [rsi+rcx*2], di
0x180028378  jnz     short loc_180028371
0x18002837a  lea     r14, [rcx+0ABh]
0x180028381  mov     qword ptr [rbp+57h+Privilege], rdi
0x180028385  mov     eax, 2
0x18002838a  mul     r14
0x18002838d  mov     rbx, rax
0x180028390  test    rdx, rdx
0x180028393  jnz     loc_18002846E
0x180028399  call    cs:__imp_GetProcessHeap
0x1800283a0  nop     dword ptr [rax+rax+00h]
0x1800283a5  mov     rcx, rax; hHeap
0x1800283a8  mov     r8, rbx; dwBytes
0x1800283ab  mov     edx, 8; dwFlags
0x1800283b0  call    cs:__imp_HeapAlloc
0x1800283b7  nop     dword ptr [rax+rax+00h]
0x1800283bc  mov     rdi, rax
0x1800283bf  mov     ebx, 8007000Eh
0x1800283c4  xor     eax, eax
0x1800283c6  test    rdi, rdi
0x1800283c9  cmovnz  ebx, eax
0x1800283cc  jz      loc_180028473
0x1800283d2  mov     r9, rsi
0x1800283d5  lea     r8, aDPaiAOiciFaSyA; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A"...
0x1800283dc  mov     rdx, r14; unsigned __int64
0x1800283df  mov     rcx, rdi; unsigned __int16 *
0x1800283e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800283e7  mov     ebx, eax
0x1800283e9  xor     esi, esi
0x1800283eb  test    eax, eax
0x1800283ed  js      short loc_18002843C
0x1800283ef  mov     qword ptr [rbp+57h+Privilege], rsi
0x1800283f3  xor     r9d, r9d; SecurityDescriptorSize
0x1800283f6  lea     r8, [rbp+57h+Privilege]; SecurityDescriptor
0x1800283fa  lea     edx, [rsi+1]; StringSDRevision
0x1800283fd  mov     rcx, rdi; StringSecurityDescriptor
0x180028400  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028407  nop     dword ptr [rax+rax+00h]
0x18002840c  test    eax, eax
0x18002840e  jz      short loc_180028418
0x180028410  mov     r15, qword ptr [rbp+57h+Privilege]
0x180028414  mov     ebx, esi
0x180028416  jmp     short loc_18002843C
0x180028418  call    cs:__imp_GetLastError
0x18002841f  nop     dword ptr [rax+rax+00h]
0x180028424  mov     ebx, eax
0x180028426  test    eax, eax
0x180028428  jle     short loc_180028433
0x18002842a  movzx   ebx, ax
0x18002842d  or      ebx, 80070000h
0x180028433  test    ebx, ebx
0x180028435  js      short loc_18002843C
0x180028437  mov     ebx, 80004005h
0x18002843c  call    cs:__imp_GetProcessHeap
0x180028443  nop     dword ptr [rax+rax+00h]
0x180028448  mov     rcx, rax; hHeap
0x18002844b  mov     r8, rdi; lpMem
0x18002844e  xor     edx, edx; dwFlags
0x180028450  call    cs:__imp_HeapFree
0x180028457  nop     dword ptr [rax+rax+00h]
0x18002845c  test    eax, eax
0x18002845e  jnz     short loc_180028475
0x180028460  call    cs:__imp_GetLastError
0x180028467  nop     dword ptr [rax+rax+00h]
0x18002846c  jmp     short loc_180028475
0x18002846e  mov     ebx, 80070216h
0x180028473  xor     esi, esi
0x180028475  test    ebx, ebx
0x180028477  js      loc_18002887B
0x18002847d  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x180028485  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r15
0x180028489  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x180028491  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x180028495  mov     rcx, r13; lpPathName
0x180028498  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18002849d  mov     ebx, eax
0x18002849f  mov     rcx, r15; hMem
0x1800284a2  call    cs:__imp_LocalFree
0x1800284a9  nop     dword ptr [rax+rax+00h]
0x1800284ae  test    ebx, ebx
0x1800284b0  js      loc_18002887B
0x1800284b6  lea     rax, [rbp+57h+var_D0]
0x1800284ba  mov     [rsp+120h+lpFileName], rax
0x1800284bf  lea     rax, [rbp+57h+var_D0]
0x1800284c3  mov     [rsp+120h+var_D8], rax
0x1800284c8  mov     [rbp+57h+var_D0], si
0x1800284cc  mov     rax, qword ptr [rbp+57h+var_B8]
0x1800284d0  mov     r8, [rax+8]
0x1800284d4  sub     r8, [rax]
0x1800284d7  sar     r8, 1
0x1800284da  mov     rdx, [rax]
0x1800284dd  lea     rcx, [rsp+120h+lpFileName]
0x1800284e2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800284e7  test    al, al
0x1800284e9  jnz     short loc_1800284F2
0x1800284eb  mov     edx, 2AEh
0x1800284f0  jmp     short loc_18002851C
0x1800284f2  lea     rax, aUsersDefault; "Users\\Default"
0x1800284f9  mov     qword ptr [rbp+57h+var_B8], rax
0x1800284fd  mov     qword ptr [rbp+57h+var_B8+8], 0Dh
0x180028505  lea     rdx, [rbp+57h+var_B8]
0x180028509  lea     rcx, [rsp+120h+lpFileName]; this
0x18002850e  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180028513  test    al, al
0x180028515  jnz     short loc_180028556
0x180028517  mov     edx, 2AFh; void *
0x18002851c  mov     r9d, 8007000Eh; char *
0x180028522  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028529  mov     rcx, [rbp+5Fh]; this
0x18002852d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028532  lea     rax, [rbp+57h+var_D0]
0x180028536  mov     rcx, [rsp+120h+lpFileName]; void *
0x18002853b  cmp     rcx, rax
0x18002853e  jz      short loc_18002854C
0x180028540  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028547  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002854c  mov     ebx, 8007000Eh
0x180028551  jmp     loc_180028893
0x180028556  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rsi
0x18002855b  mov     qword ptr [rsp+120h+dwCreationDisposition], rsi
0x180028560  xor     r9d, r9d
0x180028563  mov     r8d, 8001h
0x180028569  mov     rdx, [r12]
0x18002856d  mov     rcx, [rsp+120h+lpFileName]
0x180028572  call    cs:__imp_CopyProfileDirectoryEx2
0x180028579  nop     dword ptr [rax+rax+00h]
0x18002857e  test    eax, eax
0x180028580  jnz     short loc_18002859E
0x180028582  mov     edx, 2B8h; void *
0x180028587  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x18002858e  mov     rcx, [rbp+5Fh]; this
0x180028592  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028597  mov     ebx, eax
0x180028599  jmp     loc_18002882F
0x18002859e  mov     qword ptr [rbp+57h+CreationTime.dwLowDateTime], rsi
0x1800285a2  mov     qword ptr [rbp+57h+LastAccessTime.dwLowDateTime], rsi
0x1800285a6  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], rsi
0x1800285aa  mov     [rsp+120h+hTemplateFile], rsi; hTemplateFile
0x1800285af  mov     [rsp+120h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800285b7  mov     r14d, 3
0x1800285bd  mov     [rsp+120h+dwCreationDisposition], r14d; dwCreationDisposition
0x1800285c2  xor     r9d, r9d; lpSecurityAttributes
0x1800285c5  xor     r8d, r8d; dwShareMode
0x1800285c8  lea     edx, [r14-2]; dwDesiredAccess
0x1800285cc  mov     rcx, [rsp+120h+lpFileName]; lpFileName
0x1800285d1  call    cs:__imp_CreateFileW
0x1800285d8  nop     dword ptr [rax+rax+00h]
0x1800285dd  mov     rbx, rax
0x1800285e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800285e4  jnz     short loc_1800285ED
0x1800285e6  mov     edx, 2CAh
0x1800285eb  jmp     short loc_180028587
0x1800285ed  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1800285f1  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x1800285f5  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1800285f9  mov     rcx, rbx; hFile
0x1800285fc  call    cs:__imp_GetFileTime
0x180028603  nop     dword ptr [rax+rax+00h]
0x180028608  test    eax, eax
0x18002860a  jnz     short loc_180028658
0x18002860c  mov     rcx, [rbp+5Fh]; this
0x180028610  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180028617  mov     edx, 2CFh; void *
0x18002861c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028621  mov     edi, eax
0x180028623  test    rbx, rbx
0x180028626  jz      short loc_180028637
0x180028628  mov     rcx, rbx; hObject
0x18002862b  call    cs:__imp_CloseHandle
0x180028632  nop     dword ptr [rax+rax+00h]
0x180028637  mov     rcx, [rsp+120h+lpFileName]; void *
0x18002863c  lea     rax, [rbp+57h+var_D0]
0x180028640  cmp     rcx, rax
0x180028643  jz      short loc_180028651
0x180028645  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002864c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028651  mov     ebx, edi
0x180028653  jmp     loc_180028893
0x180028658  test    rbx, rbx
0x18002865b  jz      short loc_18002866C
0x18002865d  mov     rcx, rbx; hObject
0x180028660  call    cs:__imp_CloseHandle
0x180028667  nop     dword ptr [rax+rax+00h]
0x18002866c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180028674  movdqu  [rbp+57h+var_B8], xmm0
0x180028679  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFFh
0x180028681  lea     rax, [rbp+57h+var_78]
0x180028685  mov     [rbp+57h+var_88], rax
0x180028689  lea     rax, [rbp+57h+var_78]
0x18002868d  mov     [rbp+57h+var_80], rax
0x180028691  mov     [rbp+57h+var_78], si
0x180028695  lea     rax, asc_18003FBC4; "*"
0x18002869c  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; int
0x1800286a1  lea     r9, [rbp+57h+var_B8]
0x1800286a5  mov     r8d, 0Fh
0x1800286ab  lea     rdx, [rbp+57h+var_88]
0x1800286af  mov     rcx, r12
0x1800286b2  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x1800286b7  mov     ebx, eax
0x1800286b9  test    eax, eax
0x1800286bb  jns     short loc_18002870B
0x1800286bd  mov     rcx, [rbp+5Fh]; this
0x1800286c1  mov     r9d, eax; char *
0x1800286c4  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800286cb  mov     edx, 30Fh; void *
0x1800286d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286d5  mov     rcx, [rbp+57h+var_88]; void *
0x1800286d9  lea     rax, [rbp+57h+var_78]
0x1800286dd  cmp     rcx, rax
0x1800286e0  jz      short loc_1800286EE
0x1800286e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800286e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800286ee  mov     rcx, [rbp+5Fh]; this
0x1800286f2  mov     r9d, ebx; char *
0x1800286f5  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800286fc  mov     edx, 2D7h; void *
0x180028701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028706  jmp     loc_180028826
0x18002870b  mov     rcx, [rbp+57h+var_88]; void *
0x18002870f  lea     rax, [rbp+57h+var_78]
0x180028713  cmp     rcx, rax
0x180028716  jz      short loc_180028724
0x180028718  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002871f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028724  mov     rbx, qword ptr [rbp+57h+var_B8]
0x180028728  cmp     rbx, qword ptr [rbp+57h+var_B8+8]
0x18002872c  jz      loc_18002884B
0x180028732  mov     rcx, [rbx]; lpFileName
0x180028735  call    cs:__imp_GetFileAttributesW
0x18002873c  nop     dword ptr [rax+rax+00h]
0x180028741  cmp     eax, 0FFFFFFFFh
0x180028744  jz      short loc_18002874E
0x180028746  test    al, 10h
0x180028748  jnz     loc_1800287D2
0x18002874e  mov     [rsp+120h+hTemplateFile], rsi; hTemplateFile
0x180028753  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002875b  mov     [rsp+120h+dwCreationDisposition], r14d; dwCreationDisposition
0x180028760  xor     r9d, r9d; lpSecurityAttributes
0x180028763  xor     r8d, r8d; dwShareMode
0x180028766  mov     edx, 100h; dwDesiredAccess
0x18002876b  mov     rcx, [rbx]; lpFileName
0x18002876e  call    cs:__imp_CreateFileW
0x180028775  nop     dword ptr [rax+rax+00h]
0x18002877a  mov     rdi, rax
0x18002877d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028781  jz      loc_18002880F
0x180028787  mov     edx, 2002h; dwFileAttributes
0x18002878c  mov     rcx, [rbx]; lpFileName
0x18002878f  call    cs:__imp_SetFileAttributesW
0x180028796  nop     dword ptr [rax+rax+00h]
0x18002879b  test    eax, eax
0x18002879d  jz      short loc_180028808
0x18002879f  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1800287a3  lea     r8, [rbp+57h+LastAccessTime]; lpLastAccessTime
0x1800287a7  lea     rdx, [rbp+57h+CreationTime]; lpCreationTime
0x1800287ab  mov     rcx, rdi; hFile
  ... truncated ...
```
