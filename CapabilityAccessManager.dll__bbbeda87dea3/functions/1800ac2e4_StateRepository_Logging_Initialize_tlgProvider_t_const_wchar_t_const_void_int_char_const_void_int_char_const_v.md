# StateRepository::Logging::Initialize(_tlgProvider_t const *,wchar_t const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),StateRepository::Logging::InitializeFlags)

- ea: `0x1800ac2e4`
- end: `0x1800ac4ba`
- name: `?Initialize@Logging@StateRepository@@YAJPEBU_tlgProvider_t@@PEB_WP6AXHPEBD@Z3333P6AXPEAX2@ZP6AX42I@ZW4InitializeFlags@12@@Z`
- size: `470`
- prototype: `int __high(const struct _tlgProvider_t *, const wchar_t *, void (__high *)(int, const char *), void (__high *)(int, const char *), void (__high *)(int, const char *), void (__high *)(int, const char *), void (__high *)(int, const char *), void (__high *)(void *, const char *), void (__high *)(void *, const char *, unsigned int), enum StateRepository::Logging::InitializeFlags)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800a1140`

## callees

- `0x180016944`
- `0x180017098`
- `0x18001ab9c`
- `0x18002f260`
- `0x18005a350`
- `0x1800a0aac`
- `0x1800ac060`
- `0x1800ac2e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac46e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac46e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac31d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac31d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac339`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac339`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800ac347`

## string_xrefs

- `0x1800ac316`: `kernelbase.dll`
- `0x1800ac34e`: `CapabilityAccessManager.log`
- `0x1800ac32f`: `GetTempPath2W`
- `0x1800ac373`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x1800ac3b2`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 StateRepository::Logging::Initialize(__int64 a1, __int64 a2, ...)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  void *ProcAddress; // rdi
  bool v6; // dl
  StateRepository::Logging *v7; // rcx
  const wchar_t *v8; // r14
  int v10; // eax
  unsigned int v11; // esi
  HMODULE v12; // rsi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HMODULE v15; // [rsp+60h] [rbp+40h] BYREF
  va_list va; // [rsp+60h] [rbp+40h]
  const wchar_t *v17; // [rsp+68h] [rbp+48h] BYREF
  va_list va1; // [rsp+68h] [rbp+48h]
  __int64 v19; // [rsp+70h] [rbp+50h]
  __int64 v20; // [rsp+78h] [rbp+58h]
  __int64 v21; // [rsp+80h] [rbp+60h]
  __int64 v22; // [rsp+88h] [rbp+68h]
  __int64 v23; // [rsp+90h] [rbp+70h]
  __int64 v24; // [rsp+98h] [rbp+78h]
  va_list va2; // [rsp+A0h] [rbp+80h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v15 = va_arg(va1, HMODULE);
  va_copy(va2, va1);
  v17 = va_arg(va2, const wchar_t *);
  v19 = va_arg(va2, _QWORD);
  v20 = va_arg(va2, _QWORD);
  v21 = va_arg(va2, _QWORD);
  v22 = va_arg(va2, _QWORD);
  v23 = va_arg(va2, _QWORD);
  v24 = va_arg(va2, _QWORD);
  if ( (v24 & 2) == 0 )
  {
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v4 = Library;
    v15 = Library;
    if ( !Library || (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) == 0 )
      ProcAddress = GetTempPathW;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      (const wchar_t **)va1,
      L"CapabilityAccessManager.log");
    v8 = v17;
    if ( !v17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)0x8007000ELL,
        savedregs);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((const wchar_t **)va1);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
      return 2147942414LL;
    }
    LOBYTE(v7) = 1;
    v10 = StateRepository::Logging::EnableLog(v7, v6);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)(unsigned int)v10,
        savedregs);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((const wchar_t **)va1);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
      return v11;
    }
    qword_180169028 = a1;
    v17 = 0;
    pszSrc = v8;
    qword_180169060 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169068 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169070 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169038 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169040 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169048 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    qword_180169050 = (__int64)tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result;
    v12 = hLibModule;
    if ( hLibModule )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)va);
      FreeLibrary(v12);
      wil::last_error_context::~last_error_context((wil::last_error_context *)va);
    }
    hLibModule = v4;
    v15 = 0;
    qword_180169030 = (__int64)ProcAddress;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((const wchar_t **)va1);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ac2e4  mov     [rsp-28h+arg_0], rbx
0x1800ac2e9  mov     [rsp-28h+arg_18], r9
0x1800ac2ee  mov     [rsp-28h+arg_10], r8
0x1800ac2f3  push    rbp
0x1800ac2f4  push    rsi
0x1800ac2f5  push    rdi
0x1800ac2f6  push    r14
0x1800ac2f8  push    r15; int
0x1800ac2fa  mov     rbp, rsp
0x1800ac2fd  sub     rsp, 20h
0x1800ac301  mov     r15, rcx
0x1800ac304  test    byte ptr [rbp+arg_48], 2
0x1800ac308  jnz     loc_1800AC4A7
0x1800ac30e  xor     edx, edx; hFile
0x1800ac310  mov     r8d, 800h; dwFlags
0x1800ac316  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ac31d  call    cs:__imp_LoadLibraryExW
0x1800ac323  mov     rbx, rax
0x1800ac326  mov     [rbp+arg_10], rax
0x1800ac32a  test    rax, rax
0x1800ac32d  jz      short loc_1800AC347
0x1800ac32f  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800ac336  mov     rcx, rax; hModule
0x1800ac339  call    cs:__imp_GetProcAddress
0x1800ac33f  mov     rdi, rax
0x1800ac342  test    rax, rax
0x1800ac345  jnz     short loc_1800AC34E
0x1800ac347  mov     rdi, cs:__imp_GetTempPathW
0x1800ac34e  lea     rdx, aCapabilityacce_5; "CapabilityAccessManager.log"
0x1800ac355  lea     rcx, [rbp+arg_18]
0x1800ac359  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800ac35e  mov     r14, [rbp+arg_18]
0x1800ac362  test    r14, r14
0x1800ac365  jnz     short loc_1800AC39E
0x1800ac367  mov     rcx, [rbp+28h]; this
0x1800ac36b  mov     ebx, 8007000Eh
0x1800ac370  mov     r9d, ebx; char *
0x1800ac373  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x1800ac37a  lea     edx, [r14+4Ah]; void *
0x1800ac37e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac383  lea     rcx, [rbp+arg_18]
0x1800ac387  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ac38c  nop
0x1800ac38d  lea     rcx, [rbp+arg_10]
0x1800ac391  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800ac396  nop
0x1800ac397  mov     eax, ebx
0x1800ac399  jmp     loc_1800AC4A9
0x1800ac39e  mov     cl, 1; this
0x1800ac3a0  call    ?EnableLog@Logging@StateRepository@@YAJ_N@Z; StateRepository::Logging::EnableLog(bool)
0x1800ac3a5  mov     esi, eax
0x1800ac3a7  test    eax, eax
0x1800ac3a9  jns     short loc_1800AC3DE
0x1800ac3ab  mov     rcx, [rbp+28h]; this
0x1800ac3af  mov     r9d, eax; char *
0x1800ac3b2  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x1800ac3b9  mov     edx, 4Ch ; 'L'; void *
0x1800ac3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac3c3  lea     rcx, [rbp+arg_18]
0x1800ac3c7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ac3cc  nop
0x1800ac3cd  lea     rcx, [rbp+arg_10]
0x1800ac3d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800ac3d6  nop
0x1800ac3d7  mov     eax, esi
0x1800ac3d9  jmp     loc_1800AC4A9
0x1800ac3de  mov     cs:qword_180169028, r15
0x1800ac3e5  mov     [rbp+arg_18], 0
0x1800ac3ed  mov     cs:pszSrc, r14
0x1800ac3f4  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac3fb  mov     cs:qword_180169060, rax
0x1800ac402  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac409  mov     cs:qword_180169068, rax
0x1800ac410  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac417  mov     cs:qword_180169070, rax
0x1800ac41e  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac425  mov     cs:qword_180169038, rax
0x1800ac42c  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac433  mov     cs:qword_180169040, rax
0x1800ac43a  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac441  mov     cs:qword_180169048, rax
0x1800ac448  lea     rax, ?on_result@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::on_result(TipReportingInfo const &)
0x1800ac44f  mov     cs:qword_180169050, rax
0x1800ac456  mov     rsi, cs:hLibModule
0x1800ac45d  test    rsi, rsi
0x1800ac460  jz      short loc_1800AC47D
0x1800ac462  lea     rcx, [rbp+arg_10]; this
0x1800ac466  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ac46b  mov     rcx, rsi; hLibModule
0x1800ac46e  call    cs:__imp_FreeLibrary
0x1800ac474  lea     rcx, [rbp+arg_10]; this
0x1800ac478  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ac47d  mov     cs:hLibModule, rbx
0x1800ac484  mov     [rbp+arg_10], 0
0x1800ac48c  mov     cs:qword_180169030, rdi
0x1800ac493  lea     rcx, [rbp+arg_18]
0x1800ac497  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ac49c  nop
0x1800ac49d  lea     rcx, [rbp+arg_10]
0x1800ac4a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800ac4a6  nop
0x1800ac4a7  xor     eax, eax
0x1800ac4a9  mov     rbx, [rsp+20h+arg_0]
0x1800ac4ae  add     rsp, 20h
0x1800ac4b2  pop     r15
0x1800ac4b4  pop     r14
0x1800ac4b6  pop     rdi
0x1800ac4b7  pop     rsi
0x1800ac4b8  pop     rbp
0x1800ac4b9  retn
```
