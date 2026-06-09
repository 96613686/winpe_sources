# win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)

- ea: `0x1800560b8`
- end: `0x18005665c`
- name: `?CreateFileInternal@OpcObjectModelFactoryImplementation@win_dox@@AEBAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KK@Z`
- size: `1444`
- prototype: `HANDLE __fastcall(win_dox::OpcObjectModelFactoryImplementation *this, const wchar_t *, DWORD, DWORD, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD, DWORD dwFlagsAndAttributes)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180055e0c`

## callees

- `0x180015a68`
- `0x180015af4`
- `0x18001a810`
- `0x1800460f0`
- `0x1800517a0`
- `0x1800560b8`
- `0x1800654b0`
- `0x180079ca0`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1800d078c`
- `0x1800d07fc`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18005622a`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18005622a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800562a8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005643f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800562a8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005643f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005640b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005640b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800564a8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180056564`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800564a8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180056564`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180056420`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180056466`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800564c4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180056420`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180056466`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800564c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056175`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180056175`

## string_xrefs

- `0x1800561c9`: `Call to ::CreateFile failed with HResult 0x%X.`
- `0x1800562ec`: `Call to ::LoadLibraryEx failed with HResult 0x%X.`
- `0x180056416`: `SetDefaultDllDirectories`
- `0x180056404`: `api-ms-win-core-libraryloader-l1-1-0.dll`
- `0x1800564ba`: `CreateFile2`
- `0x180056604`: `Call to ::CreateFile2 failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
HANDLE __fastcall win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal(
        win_dox::OpcObjectModelFactoryImplementation *this,
        const wchar_t *a2,
        DWORD a3,
        DWORD a4,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD a6,
        DWORD dwFlagsAndAttributes)
{
  struct _SECURITY_ATTRIBUTES *v10; // rbx
  DWORD dwCreationDisposition; // edi
  HANDLE result; // rax
  win_musl::detail *v13; // rcx
  unsigned int v14; // edi
  HMODULE v15; // rax
  HMODULE v16; // rcx
  unsigned int LastErrorAsFailHR; // ebx
  win_musl::Formatter *v18; // rcx
  struct win_musl::TStringEllipseBase *v19; // rax
  HMODULE ModuleHandleW; // rax
  DWORD v21; // r14d
  HMODULE Library; // rax
  HMODULE v23; // rbx
  FARPROC ProcAddress; // rax
  int v25; // eax
  win_musl::detail *v26; // rcx
  unsigned int v27; // ebx
  int v28; // edi
  win_musl::detail *v29; // rcx
  unsigned int v30; // ebx
  __int64 v31; // [rsp+48h] [rbp-C0h] BYREF
  const char *v32; // [rsp+50h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES *v33; // [rsp+58h] [rbp-B0h]
  __int64 v34; // [rsp+60h] [rbp-A8h]
  _DWORD v35[3]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-94h]
  __int128 v37; // [rsp+78h] [rbp-90h]
  wchar_t pExceptionObject[12]; // [rsp+98h] [rbp-70h] BYREF
  _DWORD v39[2]; // [rsp+B0h] [rbp-58h] BYREF
  const char *v40; // [rsp+B8h] [rbp-50h]
  _BYTE v41[56]; // [rsp+C0h] [rbp-48h] BYREF
  GUID v42; // [rsp+F8h] [rbp-10h]
  int v43; // [rsp+120h] [rbp+18h]
  wchar_t v44[512]; // [rsp+498h] [rbp+390h] BYREF

  v34 = -2;
  v10 = lpSecurityAttributes;
  v33 = lpSecurityAttributes;
  dwCreationDisposition = a6;
  if ( dword_1801C5380 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801C5380);
    if ( dword_1801C5380 == -1 )
    {
      atexit(win_dox::OpcObjectModelFactoryImplementation::CreateFileInternal_::_2_::_dynamic_atexit_destructor_for__s_hmoduleKernelBase__);
      Init_thread_footer(&dword_1801C5380);
    }
  }
  if ( !byte_1801C5100 )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-libraryloader-l1-1-0.dll");
    if ( ModuleHandleW )
      ModuleHandleW = (HMODULE)GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
    v21 = ModuleHandleW != 0 ? 0x800 : 0;
    Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-l1-1-0", 0, v21);
    v23 = Library;
    if ( Library )
    {
      v32 = (const char *)Library;
      ProcAddress = GetProcAddress(Library, "GetCurrentPackageId");
      if ( ProcAddress )
      {
        HIDWORD(v31) = 0;
        v25 = ((__int64 (__fastcall *)(char *, _QWORD))ProcAddress)((char *)&v31 + 4, 0);
        v28 = v25;
        if ( v25 == 122 )
        {
          v15 = LoadLibraryExW(L"kernelbase", 0, v21);
          v16 = hLibModule;
          hLibModule = v15;
          if ( v16 )
          {
            FreeLibrary(v16);
            v15 = hLibModule;
          }
          if ( !v15 )
          {
            LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR((win_musl::detail *)v16);
            memset_0(v44, 0, sizeof(v44));
            StringCchPrintfW(v44, 0x200u, L"Call to ::LoadLibraryEx failed with HResult 0x%X.", LastErrorAsFailHR);
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::TSystemException *)pExceptionObject,
              0x4Fu,
              LastErrorAsFailHR,
              (struct win_musl::TStringEllipseBase *)v44);
            throw (SplException::THResultException *)pExceptionObject;
          }
          hTemplateFile = GetProcAddress(v15, "CreateFile2");
          if ( !hTemplateFile )
          {
            v27 = win_musl::detail::GetLastErrorAsFailHR(v26);
            memset_0(v44, 0, sizeof(v44));
            StringCchPrintfW(v44, 0x200u, L"Call to ::GetProcAddress failed with HResult 0x%X.", v27);
            win_musl::detail::ThrowBuilder<SplException::THResultException>(
              (SplException::TSystemException *)pExceptionObject,
              0x52u,
              v27,
              (struct win_musl::TStringEllipseBase *)v44);
            throw (SplException::THResultException *)pExceptionObject;
          }
        }
        else if ( v25 != 15700 )
        {
          std::wstring::wstring(v35, L"::GetCurrentPackageId failed");
          v18 = (win_musl::Formatter *)win_musl::Formatter::Formatter(pExceptionObject, v35);
          v19 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v18);
          if ( v28 > 0 )
            v28 = (unsigned __int16)v28 | 0x80070000;
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)v44,
            0x58u,
            v28,
            v19);
          throw (SplException::THResultException *)v44;
        }
        dwCreationDisposition = a6;
      }
    }
    else
    {
      v32 = 0;
    }
    byte_1801C5100 = 1;
    if ( v23 )
      FreeLibrary(v23);
    v10 = v33;
  }
  if ( hTemplateFile )
  {
    v35[0] = 32;
    v36 = 0;
    v37 = 0;
    v35[1] = (unsigned __int16)dwFlagsAndAttributes;
    v35[2] = dwFlagsAndAttributes & 0xFFF80000;
    if ( (dwFlagsAndAttributes & 0x100000) != 0 )
      v36 = dwFlagsAndAttributes & 0x1F0000;
    else
      v36 = 0;
    *(_QWORD *)&v37 = v10;
    result = (HANDLE)((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD *))hTemplateFile)(
                       a2,
                       a3,
                       a4,
                       dwCreationDisposition,
                       v35);
    if ( result == (HANDLE)-1LL )
    {
      v30 = win_musl::detail::GetLastErrorAsFailHR(v29);
      memset_0(pExceptionObject, 0, 0x400u);
      StringCchPrintfW(pExceptionObject, 0x200u, L"Call to ::CreateFile2 failed with HResult 0x%X.", v30);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v44,
        0x7Au,
        v30,
        (struct win_musl::TStringEllipseBase *)pExceptionObject);
      throw (SplException::THResultException *)v44;
    }
  }
  else
  {
    result = CreateFileW(a2, a3, a4, v10, dwCreationDisposition, dwFlagsAndAttributes, 0);
    if ( result == (HANDLE)-1LL )
    {
      v14 = win_musl::detail::GetLastErrorAsFailHR(v13);
      memset_0(v44, 0, sizeof(v44));
      StringCchPrintfW(v44, 0x200u, L"Call to ::CreateFile failed with HResult 0x%X.", v14);
      win_musl::DebugLogHelper("(no filename)", &word_18013A0B6, 105, 1024, v14, v44);
      v32 = "Unexpected HRESULT returned by API";
      exception::exception((exception *)pExceptionObject, &v32);
      memset_0(v41, 0, 0x68u);
      v40 = "(no filename)";
      v39[1] = 105;
      v43 = -1;
      *(_QWORD *)pExceptionObject = &SplException::THResultException::`vftable';
      v39[0] = -2147467259;
      if ( v14 )
        v39[0] = v14;
      v42 = GUID_NULL;
      if ( SplException::Functions )
        v43 = SplException::Functions(v39);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800560b8  mov     rax, rsp
0x1800560bb  push    rbp
0x1800560bc  push    rsi
0x1800560bd  push    rdi
0x1800560be  push    r12
0x1800560c0  push    r13
0x1800560c2  push    r14
0x1800560c4  push    r15
0x1800560c6  lea     rbp, [rax-7D8h]
0x1800560cd  sub     rsp, 8A0h
0x1800560d4  mov     qword ptr [rsp+8D0h+var_878], 0FFFFFFFFFFFFFFFEh
0x1800560dd  mov     [rax+8], rbx
0x1800560e1  mov     rax, cs:__security_cookie
0x1800560e8  xor     rax, rsp
0x1800560eb  mov     [rbp+7D0h+var_40], rax
0x1800560f2  mov     r13d, r9d
0x1800560f5  mov     r12d, r8d
0x1800560f8  mov     r15, rdx
0x1800560fb  mov     rbx, [rbp+7D0h+lpSecurityAttributes]
0x180056102  mov     [rsp+8D0h+var_880], rbx
0x180056107  mov     edi, [rbp+7D0h+arg_28]
0x18005610d  mov     dword ptr [rsp+8D0h+var_890], edi
0x180056111  mov     esi, [rbp+7D0h+arg_30]
0x180056117  mov     ecx, cs:_tls_index
0x18005611d  mov     rax, gs:58h
0x180056126  mov     edx, 4
0x18005612b  mov     rax, [rax+rcx*8]
0x18005612f  mov     eax, [rdx+rax]
0x180056132  cmp     cs:dword_1801C5380, eax
0x180056138  jg      loc_1800563CE
0x18005613e  mov     al, cs:byte_1801C5100
0x180056144  test    al, al
0x180056146  jz      loc_180056404
0x18005614c  mov     rax, cs:hTemplateFile
0x180056153  test    rax, rax
0x180056156  jnz     loc_180056577
0x18005615c  mov     [rsp+30h], rax; hTemplateFile
0x180056161  mov     [rsp+8D0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180056165  mov     [rsp+8D0h+dwCreationDisposition], edi; dwCreationDisposition
0x180056169  mov     r9, rbx; lpSecurityAttributes
0x18005616c  mov     r8d, r13d; dwShareMode
0x18005616f  mov     edx, r12d; dwDesiredAccess
0x180056172  mov     rcx, r15; lpFileName
0x180056175  call    cs:__imp_CreateFileW
0x18005617b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005617f  jz      short loc_1800561AB
0x180056181  mov     rcx, [rbp+7D0h+var_40]
0x180056188  xor     rcx, rsp; StackCookie
0x18005618b  call    __security_check_cookie
0x180056190  mov     rbx, [rsp+8D0h+arg_0]
0x180056198  add     rsp, 8A0h
0x18005619f  pop     r15
0x1800561a1  pop     r14
0x1800561a3  pop     r13
0x1800561a5  pop     r12
0x1800561a7  pop     rdi
0x1800561a8  pop     rsi
0x1800561a9  pop     rbp
0x1800561aa  retn
0x1800561ab  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800561b0  mov     edi, eax
0x1800561b2  xor     edx, edx; Val
0x1800561b4  mov     r8d, 400h; Size
0x1800561ba  lea     rcx, [rbp+7D0h+var_440]; void *
0x1800561c1  call    memset_0
0x1800561c6  mov     r9d, edi
0x1800561c9  lea     r8, aCallToCreatefi; "Call to ::CreateFile failed with HResul"...
0x1800561d0  mov     edx, 200h; unsigned __int64
0x1800561d5  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x1800561dc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800561e1  lea     rax, [rbp+7D0h+var_440]
0x1800561e8  mov     qword ptr [rsp+8D0h+dwFlagsAndAttributes], rax
0x1800561ed  mov     [rsp+8D0h+dwCreationDisposition], edi
0x1800561f1  mov     esi, 69h ; 'i'
0x1800561f6  mov     r9d, 400h
0x1800561fc  mov     r8d, esi
0x1800561ff  lea     rdx, word_18013A0B6
0x180056206  lea     rbx, aNoFilename; "(no filename)"
0x18005620d  mov     rcx, rbx
0x180056210  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x180056215  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x18005621c  mov     [rsp+8D0h+var_888], rax
0x180056221  lea     rdx, [rsp+8D0h+var_888]
0x180056226  lea     rcx, [rbp+7D0h+pExceptionObject]
0x18005622a  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180056230  xor     edx, edx; Val
0x180056232  lea     r8d, [rsi-1]; Size
0x180056236  lea     rcx, [rbp+7D0h+var_818]; void *
0x18005623a  call    memset_0
0x18005623f  mov     [rbp+7D0h+var_820], rbx
0x180056243  mov     [rbp+7D0h+var_824], esi
0x180056246  mov     [rbp+7D0h+var_7B8], 0FFFFFFFFh
0x18005624d  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x180056254  mov     qword ptr [rbp+7D0h+pExceptionObject], rax
0x180056258  mov     [rbp+7D0h+var_828], 80004005h
0x18005625f  test    edi, edi
0x180056261  jnz     loc_18005656F
0x180056267  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18005626e  movdqu  [rbp+7D0h+var_7E0], xmm0
0x180056273  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18005627a  test    rax, rax
0x18005627d  jz      short loc_18005628B
0x18005627f  lea     rcx, [rbp+7D0h+var_828]
0x180056283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056288  mov     [rbp+7D0h+var_7B8], eax
0x18005628b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180056292  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x180056296  call    _CxxThrowException_0
0x18005629c  mov     r8d, r14d; dwFlags
0x18005629f  xor     edx, edx; hFile
0x1800562a1  lea     rcx, LibFileName; "kernelbase"
0x1800562a8  call    cs:__imp_LoadLibraryExW
0x1800562ae  mov     rcx, cs:hLibModule; this
0x1800562b5  mov     cs:hLibModule, rax
0x1800562bc  test    rcx, rcx
0x1800562bf  jnz     loc_1800564A8
0x1800562c5  test    rax, rax
0x1800562c8  jnz     loc_1800564BA
0x1800562ce  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800562d3  mov     ebx, eax
0x1800562d5  xor     edx, edx; Val
0x1800562d7  mov     r8d, 400h; Size
0x1800562dd  lea     rcx, [rbp+7D0h+var_440]; void *
0x1800562e4  call    memset_0
0x1800562e9  mov     r9d, ebx
0x1800562ec  lea     r8, aCallToLoadlibr; "Call to ::LoadLibraryEx failed with HRe"...
0x1800562f3  mov     edx, 200h; unsigned __int64
0x1800562f8  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x1800562ff  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180056304  lea     rax, [rbp+7D0h+var_440]
0x18005630b  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180056310  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x180056314  mov     [rsp+8D0h+dwCreationDisposition], 4Fh ; 'O'; unsigned int
0x18005631c  lea     r9, word_18013A0B6
0x180056323  lea     r8, aNoFilename; "(no filename)"
0x18005632a  lea     rcx, [rbp+7D0h+pExceptionObject]; this
0x18005632e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180056333  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18005633a  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x18005633e  call    _CxxThrowException_0
0x180056344  mov     cs:byte_1801C5100, 1
0x18005634b  test    rbx, rbx
0x18005634e  jnz     loc_180056561
0x180056354  mov     rbx, [rsp+8D0h+var_880]
0x180056359  jmp     loc_18005614C
0x18005635e  lea     rdx, aGetcurrentpack; "::GetCurrentPackageId failed"
0x180056365  lea     rcx, [rsp+8D0h+var_874+4]
0x18005636a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005636f  nop
0x180056370  lea     rdx, [rsp+8D0h+var_874+4]
0x180056375  lea     rcx, [rbp+7D0h+pExceptionObject]
0x180056379  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18005637e  nop
0x18005637f  mov     rcx, rax; this
0x180056382  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x180056387  test    edi, edi
0x180056389  jg      loc_180056553
0x18005638f  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180056394  mov     [rsp+8D0h+dwFlagsAndAttributes], edi; unsigned int
0x180056398  mov     [rsp+8D0h+dwCreationDisposition], 58h ; 'X'; unsigned int
0x1800563a0  lea     r9, word_18013A0B6
0x1800563a7  lea     r8, aNoFilename; "(no filename)"
0x1800563ae  lea     rcx, [rbp+7D0h+var_440]; this
0x1800563b5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800563ba  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800563c1  lea     rcx, [rbp+7D0h+var_440]; pExceptionObject
0x1800563c8  call    _CxxThrowException_0
0x1800563ce  lea     rcx, dword_1801C5380
0x1800563d5  call    _Init_thread_header
0x1800563da  cmp     cs:dword_1801C5380, 0FFFFFFFFh
0x1800563e1  jnz     loc_18005613E
0x1800563e7  lea     rcx, _win_dox__OpcObjectModelFactoryImplementation__CreateFileInternal____2____dynamic_atexit_destructor_for__s_hmoduleKernelBase__; void (__cdecl *)()
0x1800563ee  call    atexit
0x1800563f3  lea     rcx, dword_1801C5380
0x1800563fa  call    _Init_thread_footer
0x1800563ff  jmp     loc_18005613E
0x180056404  lea     rcx, ModuleName; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x18005640b  call    cs:__imp_GetModuleHandleW
0x180056411  test    rax, rax
0x180056414  jz      short loc_180056426
0x180056416  lea     rdx, ProcName; "SetDefaultDllDirectories"
0x18005641d  mov     rcx, rax; hModule
0x180056420  call    cs:__imp_GetProcAddress
0x180056426  neg     rax
0x180056429  sbb     r14d, r14d
0x18005642c  and     r14d, 800h
0x180056433  mov     r8d, r14d; dwFlags
0x180056436  xor     edx, edx; hFile
0x180056438  lea     rcx, aApiMsWinAppmod; "api-ms-win-appmodel-runtime-l1-1-0"
0x18005643f  call    cs:__imp_LoadLibraryExW
0x180056445  mov     rbx, rax
0x180056448  test    rax, rax
0x18005644b  jnz     short loc_180056457
0x18005644d  mov     [rsp+8D0h+var_888], rax
0x180056452  jmp     loc_180056344
0x180056457  mov     [rsp+8D0h+var_888], rax
0x18005645c  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageId"
0x180056463  mov     rcx, rax; hModule
0x180056466  call    cs:__imp_GetProcAddress
0x18005646c  test    rax, rax
0x18005646f  jz      loc_180056344
0x180056475  mov     dword ptr [rsp+8D0h+var_890+4], 0
0x18005647d  xor     edx, edx
0x18005647f  lea     rcx, [rsp+8D0h+var_890+4]
0x180056484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056489  mov     edi, eax
0x18005648b  cmp     eax, 7Ah ; 'z'
0x18005648e  jz      loc_18005629C
0x180056494  cmp     eax, 3D54h
0x180056499  jnz     loc_18005635E
0x18005649f  mov     edi, dword ptr [rsp+8D0h+var_890]
0x1800564a3  jmp     loc_180056344
0x1800564a8  call    cs:__imp_FreeLibrary
0x1800564ae  mov     rax, cs:hLibModule
0x1800564b5  jmp     loc_1800562C5
0x1800564ba  lea     rdx, aCreatefile2; "CreateFile2"
0x1800564c1  mov     rcx, rax; hModule
0x1800564c4  call    cs:__imp_GetProcAddress
0x1800564ca  mov     cs:hTemplateFile, rax
0x1800564d1  mov     rax, cs:hTemplateFile
0x1800564d8  test    rax, rax
0x1800564db  jnz     short loc_18005649F
0x1800564dd  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800564e2  mov     ebx, eax
0x1800564e4  xor     edx, edx; Val
0x1800564e6  mov     r8d, 400h; Size
0x1800564ec  lea     rcx, [rbp+7D0h+var_440]; void *
0x1800564f3  call    memset_0
0x1800564f8  mov     r9d, ebx
0x1800564fb  lea     r8, aCallToGetproca; "Call to ::GetProcAddress failed with HR"...
0x180056502  mov     edx, 200h; unsigned __int64
0x180056507  lea     rcx, [rbp+7D0h+var_440]; wchar_t *
0x18005650e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180056513  lea     rax, [rbp+7D0h+var_440]
0x18005651a  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18005651f  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x180056523  mov     [rsp+8D0h+dwCreationDisposition], 52h ; 'R'; unsigned int
0x18005652b  lea     r9, word_18013A0B6
0x180056532  lea     r8, aNoFilename; "(no filename)"
0x180056539  lea     rcx, [rbp+7D0h+pExceptionObject]; this
0x18005653d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180056542  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180056549  lea     rcx, [rbp+7D0h+pExceptionObject]; pExceptionObject
0x18005654d  call    _CxxThrowException_0
0x180056553  movzx   edi, di
0x180056556  or      edi, 80070000h
0x18005655c  jmp     loc_18005638F
0x180056561  mov     rcx, rbx; hLibModule
0x180056564  call    cs:__imp_FreeLibrary
0x18005656a  jmp     loc_180056354
0x18005656f  mov     [rbp+7D0h+var_828], edi
0x180056572  jmp     loc_180056267
0x180056577  mov     dword ptr [rsp+8D0h+var_874+4], 20h ; ' '
0x18005657f  xorps   xmm0, xmm0
0x180056582  movups  [rsp+8D0h+var_874+8], xmm0
0x180056587  movups  [rsp+8D0h+var_860], xmm0
0x18005658c  movzx   eax, si
0x18005658f  mov     dword ptr [rsp+8D0h+var_874+8], eax
0x180056593  mov     eax, esi
0x180056595  and     eax, 0FFF80000h
0x18005659a  mov     dword ptr [rsp+8D0h+var_874+0Ch], eax
0x18005659e  bt      esi, 14h
0x1800565a2  jnb     short loc_1800565B0
0x1800565a4  and     esi, 1F0000h
0x1800565aa  mov     [rsp+8D0h+var_864], esi
0x1800565ae  jmp     short loc_1800565B8
0x1800565b0  mov     [rsp+8D0h+var_864], 0
0x1800565b8  mov     qword ptr [rsp+8D0h+var_860], rbx
0x1800565bd  mov     rax, cs:hTemplateFile
0x1800565c4  lea     rcx, [rsp+8D0h+var_874+4]
0x1800565c9  mov     qword ptr [rsp+8D0h+dwCreationDisposition], rcx
0x1800565ce  mov     r9d, edi
0x1800565d1  mov     r8d, r13d
0x1800565d4  mov     edx, r12d
0x1800565d7  mov     rcx, r15
0x1800565da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800565e3  jnz     loc_180056181
0x1800565e9  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800565ee  mov     ebx, eax
0x1800565f0  xor     edx, edx; Val
0x1800565f2  mov     r8d, 400h; Size
0x1800565f8  lea     rcx, [rbp+7D0h+pExceptionObject]; void *
0x1800565fc  call    memset_0
0x180056601  mov     r9d, ebx
0x180056604  lea     r8, aCallToCreatefi_0; "Call to ::CreateFile2 failed with HResu"...
0x18005660b  mov     edx, 200h; unsigned __int64
0x180056610  lea     rcx, [rbp+7D0h+pExceptionObject]; wchar_t *
0x180056614  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180056619  lea     rax, [rbp+7D0h+pExceptionObject]
0x18005661d  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180056622  mov     [rsp+8D0h+dwFlagsAndAttributes], ebx; unsigned int
0x180056626  mov     [rsp+8D0h+dwCreationDisposition], 7Ah ; 'z'; unsigned int
0x18005662e  lea     r9, word_18013A0B6
0x180056635  lea     r8, aNoFilename; "(no filename)"
0x18005663c  lea     rcx, [rbp+7D0h+var_440]; this
0x180056643  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180056648  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18005664f  lea     rcx, [rbp+7D0h+var_440]; pExceptionObject
0x180056656  call    _CxxThrowException_0
  ... truncated ...
```
