# StateRepository::Logging::Initialize(_tlgProvider_t const *,ushort const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),StateRepository::Logging::InitializeFlags)

- ea: `0x18002703c`
- end: `0x1800271d7`
- name: `?Initialize@Logging@StateRepository@@YAJPEBU_tlgProvider_t@@PEBGP6AXHPEBD@Z3333P6AXPEAX2@ZP6AX42I@ZW4InitializeFlags@12@@Z`
- size: `411`
- prototype: `__int64(__int64, __int64, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180016dcc`

## callees

- `0x180008afc`
- `0x180008d6c`
- `0x18000a3c0`
- `0x18000f3e8`
- `0x1800156d4`
- `0x180026420`
- `0x1800264d4`
- `0x18002703c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027075`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027075`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002718d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002718d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027091`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027091`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002709f`

## string_xrefs

- `0x180027068`: `kernelbase.dll`
- `0x1800270e6`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`
- `0x180027087`: `GetTempPath2W`

## pseudocode

```c
__int64 StateRepository::Logging::Initialize(__int64 a1, __int64 a2, ...)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  void *ProcAddress; // rsi
  bool v6; // dl
  StateRepository::Logging *v7; // rcx
  unsigned __int16 *v8; // r14
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  HMODULE v14; // rdi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HMODULE v17; // [rsp+60h] [rbp+40h] BYREF
  va_list va; // [rsp+60h] [rbp+40h]
  unsigned __int16 *v19; // [rsp+68h] [rbp+48h] BYREF
  va_list va1; // [rsp+68h] [rbp+48h]
  __int64 v21; // [rsp+70h] [rbp+50h]
  __int64 v22; // [rsp+78h] [rbp+58h]
  __int64 v23; // [rsp+80h] [rbp+60h]
  __int64 v24; // [rsp+88h] [rbp+68h]
  __int64 v25; // [rsp+90h] [rbp+70h]
  __int64 v26; // [rsp+98h] [rbp+78h]
  va_list va2; // [rsp+A0h] [rbp+80h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v17 = va_arg(va1, HMODULE);
  va_copy(va2, va1);
  v19 = va_arg(va2, unsigned __int16 *);
  v21 = va_arg(va2, _QWORD);
  v22 = va_arg(va2, _QWORD);
  v23 = va_arg(va2, _QWORD);
  v24 = va_arg(va2, _QWORD);
  v25 = va_arg(va2, _QWORD);
  v26 = va_arg(va2, _QWORD);
  if ( (v26 & 2) == 0 )
  {
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v17 = Library;
    v4 = Library;
    if ( !Library || (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) == 0 )
      ProcAddress = GetTempPathW;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      (unsigned __int16 **)va1,
      L"StateRepository.log");
    v8 = v19;
    if ( !v19 )
    {
      v9 = -2147024882;
      v10 = 74;
      v11 = 2147942414LL;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\logging.cpp",
        (const char *)v11,
        savedregs);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((unsigned __int16 **)va1);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
      return v9;
    }
    LOBYTE(v7) = 1;
    v12 = StateRepository::Logging::EnableLog(v7, v6);
    v9 = v12;
    if ( v12 < 0 )
    {
      v11 = (unsigned int)v12;
      v10 = 76;
      goto LABEL_9;
    }
    v14 = hLibModule;
    qword_18004BFE0 = (__int64)StateRepository::Logging::LoggerCritical;
    qword_18004BFD8 = (__int64)StateRepository::Logging::LoggerError;
    qword_18004BFD0 = (__int64)StateRepository::Logging::LoggerWarning;
    qword_18004BFC8 = (__int64)StateRepository::Logging::LoggerInformation;
    qword_18004BFC0 = (__int64)StateRepository::Logging::LoggerVerbose;
    qword_18004BFB8 = (__int64)StateRepository::Logging::LoggerProfile;
    qword_18004BFB0 = a1;
    v19 = 0;
    qword_18004BFE8 = v8;
    if ( hLibModule )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)va);
      FreeLibrary(v14);
      wil::last_error_context::~last_error_context((wil::last_error_context *)va);
    }
    hLibModule = v4;
    v17 = 0;
    qword_18004BFA8 = (__int64)ProcAddress;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((unsigned __int16 **)va1);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  }
  return 0;
}

```

## disassembly

```asm
0x18002703c  mov     [rsp-28h+arg_0], rbx
0x180027041  mov     [rsp-28h+arg_18], r9
0x180027046  mov     [rsp-28h+arg_10], r8
0x18002704b  push    rbp
0x18002704c  push    rsi
0x18002704d  push    rdi
0x18002704e  push    r14
0x180027050  push    r15; int
0x180027052  mov     rbp, rsp
0x180027055  sub     rsp, 20h
0x180027059  test    byte ptr [rbp+arg_48], 2
0x18002705d  mov     r15, rcx
0x180027060  jnz     loc_1800271C4
0x180027066  xor     edx, edx; hFile
0x180027068  lea     rcx, LibFileName; "kernelbase.dll"
0x18002706f  mov     r8d, 800h; dwFlags
0x180027075  call    cs:__imp_LoadLibraryExW
0x18002707b  mov     [rbp+arg_10], rax
0x18002707f  mov     rbx, rax
0x180027082  test    rax, rax
0x180027085  jz      short loc_18002709F
0x180027087  lea     rdx, ProcName; "GetTempPath2W"
0x18002708e  mov     rcx, rax; hModule
0x180027091  call    cs:__imp_GetProcAddress
0x180027097  mov     rsi, rax
0x18002709a  test    rax, rax
0x18002709d  jnz     short loc_1800270A6
0x18002709f  mov     rsi, cs:__imp_GetTempPathW
0x1800270a6  lea     rdx, aStaterepositor_12; "StateRepository.log"
0x1800270ad  lea     rcx, [rbp+arg_18]
0x1800270b1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800270b6  mov     r14, [rbp+arg_18]
0x1800270ba  test    r14, r14
0x1800270bd  jnz     short loc_1800270CD
0x1800270bf  mov     edi, 8007000Eh
0x1800270c4  lea     edx, [r14+4Ah]
0x1800270c8  mov     r9d, edi
0x1800270cb  jmp     short loc_1800270E2
0x1800270cd  mov     cl, 1; this
0x1800270cf  call    ?EnableLog@Logging@StateRepository@@YAJ_N@Z; StateRepository::Logging::EnableLog(bool)
0x1800270d4  mov     edi, eax
0x1800270d6  test    eax, eax
0x1800270d8  jns     short loc_18002710B
0x1800270da  mov     r9d, eax; char *
0x1800270dd  mov     edx, 4Ch ; 'L'; void *
0x1800270e2  mov     rcx, [rbp+28h]; this
0x1800270e6  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800270ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270f2  lea     rcx, [rbp+arg_18]
0x1800270f6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800270fb  lea     rcx, [rbp+arg_10]
0x1800270ff  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180027104  mov     eax, edi
0x180027106  jmp     loc_1800271C6
0x18002710b  mov     rdi, cs:hLibModule
0x180027112  lea     rax, ?LoggerCritical@Logging@StateRepository@@YAXHPEBD@Z; StateRepository::Logging::LoggerCritical(int,char const *)
0x180027119  mov     cs:qword_18004BFE0, rax
0x180027120  lea     rax, ?LoggerError@Logging@StateRepository@@YAXHPEBD@Z; StateRepository::Logging::LoggerError(int,char const *)
0x180027127  mov     cs:qword_18004BFD8, rax
0x18002712e  lea     rax, ?LoggerWarning@Logging@StateRepository@@YAXHPEBD@Z; StateRepository::Logging::LoggerWarning(int,char const *)
0x180027135  mov     cs:qword_18004BFD0, rax
0x18002713c  lea     rax, ?LoggerInformation@Logging@StateRepository@@YAXHPEBD@Z; StateRepository::Logging::LoggerInformation(int,char const *)
0x180027143  mov     cs:qword_18004BFC8, rax
0x18002714a  lea     rax, ?LoggerVerbose@Logging@StateRepository@@YAXHPEBD@Z; StateRepository::Logging::LoggerVerbose(int,char const *)
0x180027151  mov     cs:qword_18004BFC0, rax
0x180027158  lea     rax, ?LoggerProfile@Logging@StateRepository@@YAXPEAXPEBDI@Z; StateRepository::Logging::LoggerProfile(void *,char const *,uint)
0x18002715f  mov     cs:qword_18004BFB8, rax
0x180027166  mov     cs:qword_18004BFB0, r15
0x18002716d  mov     [rbp+arg_18], 0
0x180027175  mov     cs:qword_18004BFE8, r14
0x18002717c  test    rdi, rdi
0x18002717f  jz      short loc_18002719C
0x180027181  lea     rcx, [rbp+arg_10]; this
0x180027185  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002718a  mov     rcx, rdi; hLibModule
0x18002718d  call    cs:__imp_FreeLibrary
0x180027193  lea     rcx, [rbp+arg_10]; this
0x180027197  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002719c  lea     rcx, [rbp+arg_18]
0x1800271a0  mov     cs:hLibModule, rbx
0x1800271a7  mov     [rbp+arg_10], 0
0x1800271af  mov     cs:qword_18004BFA8, rsi
0x1800271b6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800271bb  lea     rcx, [rbp+arg_10]
0x1800271bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800271c4  xor     eax, eax
0x1800271c6  mov     rbx, [rsp+20h+arg_0]
0x1800271cb  add     rsp, 20h
0x1800271cf  pop     r15
0x1800271d1  pop     r14
0x1800271d3  pop     rdi
0x1800271d4  pop     rsi
0x1800271d5  pop     rbp
0x1800271d6  retn
```
