# sih::Client::impl::GetEngineModule(void)

- ea: `0x14002012c`
- end: `0x140020355`
- name: `?GetEngineModule@impl@Client@sih@@AEAAPEAUHINSTANCE__@@XZ`
- size: `553`
- prototype: `HINSTANCE __fastcall(sih::Client::impl *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting`

## callers

- `0x14002035c`

## callees

- `0x140003de4`
- `0x140005f98`
- `0x1400073f0`
- `0x14000cb54`
- `0x14000e130`
- `0x1400154b4`
- `0x140017934`
- `0x140018394`
- `0x14001b67c`
- `0x14001ed4c`
- `0x14002012c`
- `0x1400215f8`
- `0x1400217d4`
- `0x140023700`
- `0x140023a3c`
- `0x140025f90`
- `0x140026800`
- `0x140045dc0`
- `0x140045de4`
- `0x1400481f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400201f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400202aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400201f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400202aa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400201e5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140020298`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400201e5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140020298`

## string_xrefs

- `0x14002027a`: `\siheng.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HINSTANCE __fastcall sih::Client::impl::GetEngineModule(sih::Client::impl *this)
{
  __int64 RegKeyPath; // rax
  __int64 v3; // rcx
  const WCHAR *v4; // rcx
  HMODULE LibraryW; // rbx
  HMODULE v6; // rcx
  char *v7; // rbx
  const WCHAR *v8; // rcx
  HMODULE v9; // rsi
  HMODULE v10; // rcx
  int LastErrorHr; // eax
  void *v13; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpLibFileName[4]; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR Src[4]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp+1Fh] BYREF

  if ( (unsigned int)AreTestKeysAllowed((bool)this) )
  {
    RegKeyPath = GetRegKeyPath(29);
    if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(v3, RegKeyPath, L"AllowTestEngine", 0) )
    {
      sih::utils::GetTestEngine(lpLibFileName);
      if ( lpLibFileName[2] )
      {
        WUTrace(0, 0, 0x400000, 4, 0, L"GetTestEngine = %ws.");
        v4 = (const WCHAR *)lpLibFileName;
        if ( lpLibFileName[3] > (LPCWSTR)7 )
          v4 = lpLibFileName[0];
        LibraryW = LoadLibraryW(v4);
        v6 = (HMODULE)*((_QWORD *)this + 1);
        if ( v6 )
          FreeLibrary(v6);
        *((_QWORD *)this + 1) = LibraryW;
      }
      std::wstring::~wstring(lpLibFileName);
    }
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v13 = 0;
    sih::Environment::GetEngineMetadata(*(_QWORD *)this, &v13);
    v7 = (char *)v13;
    sih::Environment::GetDeployDirPath(v16);
    std::vector<sih::FileMetadata>::vector<sih::FileMetadata>(lpLibFileName, v7 + 136);
    sih::utils::VerifyPackageFiles(v16, lpLibFileName, 6);
    std::vector<sih::FileMetadata>::_Tidy(lpLibFileName);
    std::wstring::wstring(Src, v16);
    std::wstring::append(Src, L"\\siheng.dll");
    v8 = (const WCHAR *)Src;
    if ( Src[3] > (LPCWSTR)7 )
      v8 = Src[0];
    v9 = LoadLibraryW(v8);
    v10 = (HMODULE)*((_QWORD *)this + 1);
    if ( v10 )
      FreeLibrary(v10);
    *((_QWORD *)this + 1) = v9;
    if ( !v9 )
    {
      LastErrorHr = GetLastErrorHr((int)v10);
      sih::hr_exception::hr_exception((sih::hr_exception *)lpLibFileName, LastErrorHr);
      throw (sih::hr_exception *)lpLibFileName;
    }
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v16);
    if ( v7 )
    {
      std::vector<sih::FileMetadata>::_Tidy(v7 + 136);
      std::wstring::~wstring(v7 + 96);
      std::vector<std::wstring>::_Tidy(v7 + 72);
      std::wstring::~wstring(v7 + 40);
      std::wstring::~wstring(v7 + 8);
      operator delete(v7, (const struct std::nothrow_t *)0xA0);
    }
  }
  return (HINSTANCE)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x14002012c  mov     [rsp-8+arg_8], rbx
0x140020131  mov     [rsp-8+arg_10], rsi
0x140020136  push    rbp
0x140020137  push    rdi
0x140020138  push    r14
0x14002013a  lea     rbp, [rsp-47h]
0x14002013f  sub     rsp, 0B0h
0x140020146  mov     rax, cs:__security_cookie
0x14002014d  xor     rax, rsp
0x140020150  mov     [rbp+57h+var_18], rax
0x140020154  mov     rdi, rcx
0x140020157  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14002015c  test    eax, eax
0x14002015e  jz      loc_14002020A
0x140020164  mov     ecx, 1Dh
0x140020169  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x14002016e  mov     dword ptr [rsp+0C0h+var_98], 0FFFFFFFFh
0x140020176  xor     r9d, r9d
0x140020179  lea     r8, aAllowtestengin; "AllowTestEngine"
0x140020180  mov     rdx, rax
0x140020183  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x140020188  test    eax, eax
0x14002018a  jz      short loc_14002020A
0x14002018c  lea     rcx, [rbp+57h+lpLibFileName]
0x140020190  call    ?GetTestEngine@utils@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; sih::utils::GetTestEngine(void)
0x140020195  cmp     [rbp+57h+var_68], 0
0x14002019a  jz      short loc_140020201
0x14002019c  lea     rax, [rbp+57h+lpLibFileName]
0x1400201a0  cmp     [rbp+57h+var_60], 7
0x1400201a5  cmova   rax, [rbp+57h+lpLibFileName]
0x1400201aa  mov     [rsp+0C0h+var_90], rax
0x1400201af  lea     rax, aGettestengineW; "GetTestEngine = %ws."
0x1400201b6  mov     [rsp+0C0h+var_98], rax
0x1400201bb  mov     [rsp+0C0h+var_A0], 0
0x1400201c4  xor     edx, edx
0x1400201c6  lea     r9d, [rdx+4]
0x1400201ca  mov     r8d, 400000h
0x1400201d0  xor     ecx, ecx
0x1400201d2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400201d7  lea     rcx, [rbp+57h+lpLibFileName]
0x1400201db  cmp     [rbp+57h+var_60], 7
0x1400201e0  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1400201e5  call    cs:__imp_LoadLibraryW
0x1400201eb  mov     rbx, rax
0x1400201ee  mov     rcx, [rdi+8]; hLibModule
0x1400201f2  test    rcx, rcx
0x1400201f5  jz      short loc_1400201FD
0x1400201f7  call    cs:__imp_FreeLibrary
0x1400201fd  mov     [rdi+8], rbx
0x140020201  lea     rcx, [rbp+57h+lpLibFileName]; void *
0x140020205  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002020a  cmp     qword ptr [rdi+8], 0
0x14002020f  jnz     loc_14002030B
0x140020215  mov     [rbp+57h+var_80], 0
0x14002021d  lea     rdx, [rbp+57h+var_80]
0x140020221  mov     rcx, [rdi]
0x140020224  call    ?GetEngineMetadata@Environment@sih@@QEBA?AV?$unique_ptr@VPackageMetadata@sih@@U?$default_delete@VPackageMetadata@sih@@@std@@@std@@XZ; sih::Environment::GetEngineMetadata(void)
0x140020229  nop
0x14002022a  mov     rbx, [rbp+57h+var_80]
0x14002022e  mov     rdx, rbx
0x140020231  lea     rcx, [rbp+57h+var_38]; Src
0x140020235  call    ?GetDeployDirPath@Environment@sih@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVPackageMetadata@2@@Z; sih::Environment::GetDeployDirPath(sih::PackageMetadata const &)
0x14002023a  nop
0x14002023b  lea     r14, [rbx+88h]
0x140020242  mov     rdx, r14
0x140020245  lea     rcx, [rbp+57h+lpLibFileName]
0x140020249  call    ??0?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<sih::FileMetadata>::vector<sih::FileMetadata>(std::vector<sih::FileMetadata> const &)
0x14002024e  nop
0x14002024f  mov     r8d, 6
0x140020255  lea     rdx, [rbp+57h+lpLibFileName]
0x140020259  lea     rcx, [rbp+57h+var_38]
0x14002025d  call    ?VerifyPackageFiles@utils@sih@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@4@W4_SignatureStrengthPolicy@@@Z; sih::utils::VerifyPackageFiles(std::wstring const &,std::vector<sih::FileMetadata> const &,_SignatureStrengthPolicy)
0x140020262  nop
0x140020263  lea     rcx, [rbp+57h+lpLibFileName]
0x140020267  call    ?_Tidy@?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@std@@AEAAXXZ; std::vector<sih::FileMetadata>::_Tidy(void)
0x14002026c  lea     rdx, [rbp+57h+var_38]
0x140020270  lea     rcx, [rbp+57h+Src]
0x140020274  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140020279  nop
0x14002027a  lea     rdx, aSihengDll_0; "\\siheng.dll"
0x140020281  lea     rcx, [rbp+57h+Src]; Src
0x140020285  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14002028a  lea     rcx, [rbp+57h+Src]
0x14002028e  cmp     [rbp+57h+var_40], 7
0x140020293  cmova   rcx, [rbp+57h+Src]; lpLibFileName
0x140020298  call    cs:__imp_LoadLibraryW
0x14002029e  mov     rsi, rax
0x1400202a1  mov     rcx, [rdi+8]; hLibModule
0x1400202a5  test    rcx, rcx
0x1400202a8  jz      short loc_1400202B0
0x1400202aa  call    cs:__imp_FreeLibrary
0x1400202b0  mov     [rdi+8], rsi
0x1400202b4  test    rsi, rsi
0x1400202b7  jz      short loc_140020333
0x1400202b9  lea     rcx, [rbp+57h+Src]; void *
0x1400202bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400202c2  nop
0x1400202c3  lea     rcx, [rbp+57h+var_38]; void *
0x1400202c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400202cc  nop
0x1400202cd  test    rbx, rbx
0x1400202d0  jz      short loc_14002030B
0x1400202d2  mov     rcx, r14
0x1400202d5  call    ?_Tidy@?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@std@@AEAAXXZ; std::vector<sih::FileMetadata>::_Tidy(void)
0x1400202da  lea     rcx, [rbx+60h]; void *
0x1400202de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400202e3  lea     rcx, [rbx+48h]
0x1400202e7  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400202ec  lea     rcx, [rbx+28h]; void *
0x1400202f0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400202f5  lea     rcx, [rbx+8]; void *
0x1400202f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400202fe  mov     edx, 0A0h; struct std::nothrow_t *
0x140020303  mov     rcx, rbx; void *
0x140020306  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002030b  mov     rax, [rdi+8]
0x14002030f  mov     rcx, [rbp+57h+var_18]
0x140020313  xor     rcx, rsp; StackCookie
0x140020316  call    __security_check_cookie
0x14002031b  lea     r11, [rsp+0C0h+var_10]
0x140020323  mov     rbx, [r11+28h]
0x140020327  mov     rsi, [r11+30h]
0x14002032b  mov     rsp, r11
0x14002032e  pop     r14
0x140020330  pop     rdi
0x140020331  pop     rbp
0x140020332  retn
0x140020333  call    ?GetLastErrorHr@@YAJH@Z; GetLastErrorHr(int)
0x140020338  nop
0x140020339  mov     edx, eax; int
0x14002033b  lea     rcx, [rbp+57h+lpLibFileName]; this
0x14002033f  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140020344  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x14002034b  lea     rcx, [rbp+57h+lpLibFileName]; pExceptionObject
0x14002034f  call    _CxxThrowException
```
