# AppPlatformFinder::GetGOGApplications(ConfigSettings const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x18010449c`
- end: `0x18010485b`
- name: `?GetGOGApplications@AppPlatformFinder@@CAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `959`
- prototype: `unsigned __int64 __fastcall(struct ConfigSettings *, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180104864`

## callees

- `0x18000d834`
- `0x18000deb4`
- `0x18000eb5c`
- `0x1800118d0`
- `0x180013640`
- `0x1800150ac`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x1800404c4`
- `0x180041ef8`
- `0x180050030`
- `0x180052f28`
- `0x180059920`
- `0x18010449c`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180104544`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010458f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180104544`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010458f`
- `ADVAPI32!RegOpenKeyExW` at `0x1801046bc`
- `ADVAPI32!RegOpenKeyExW` at `0x1801046bc`
- `KERNEL32!GetSystemInfo` at `0x180104631`
- `KERNEL32!GetSystemInfo` at `0x180104631`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
unsigned __int64 __fastcall AppPlatformFinder::GetGOGApplications(struct ConfigSettings *a1, __int64 *a2)
{
  const struct ConfigSettings *v3; // r14
  __int64 v4; // rdx
  unsigned __int64 result; // rax
  unsigned __int64 i; // r13
  __int64 *v7; // rbx
  __int64 v8; // rsi
  _QWORD *v9; // rax
  __int64 *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rax
  char found; // bl
  __int64 v14; // rax
  struct _SYSTEM_INFO *p_SystemInfo; // rcx
  __int64 v16; // rax
  const WCHAR *v17; // rdx
  HKEY phkResult; // [rsp+58h] [rbp-B0h] BYREF
  struct ConfigSettings *v19; // [rsp+60h] [rbp-A8h]
  LPCWSTR v20[4]; // [rsp+68h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+88h] [rbp-80h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v24[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v25[32]; // [rsp+118h] [rbp+10h] BYREF

  v20[3] = (LPCWSTR)-2LL;
  v3 = a1;
  v19 = a1;
  v4 = *a2;
  result = 0xEFBEFBEFBEFBEFBFuLL * ((a2[1] - v4) >> 4);
  if ( result )
  {
    for ( i = 0; i < result; ++i )
    {
      v7 = &AppPlatformFinder::AppPlatformNameGOG;
      if ( (unsigned __int64)qword_180183568 > 7 )
        v7 = (__int64 *)AppPlatformFinder::AppPlatformNameGOG;
      v8 = 1008 * i;
      v9 = (_QWORD *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)(1008 * i + v4 + 16) + 8LL))(1008 * i + v4 + 16);
      if ( v9[3] > 7u )
        v9 = (_QWORD *)*v9;
      if ( (unsigned int)_o__wcsicmp(v9, v7) )
      {
        v10 = &AppPlatformFinder::AppPlatformPublisherGOG;
        if ( (unsigned __int64)qword_180183588 > 7 )
          v10 = (__int64 *)AppPlatformFinder::AppPlatformPublisherGOG;
        v11 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 24LL))(v8 + *a2 + 16);
        if ( v11[3] > 7u )
          v11 = (_QWORD *)*v11;
        if ( !(unsigned int)_o__wcsicmp(v11, v10) )
        {
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 88LL))(v8 + *a2 + 16);
          std::wstring::wstring(v24, v12);
          Utility::GetFileNameFromPath(v23, v24);
          std::wstring::wstring(lpSubKey, L"_");
          found = Utility::FoundSubstring(lpSubKey, v23);
          std::wstring::~wstring(lpSubKey);
          if ( found )
          {
            Utility::Split(v20, v23, 95);
            std::wstring::wstring(lpSubKey);
            memset(&SystemInfo, 0, sizeof(SystemInfo));
            GetSystemInfo(&SystemInfo);
            if ( SystemInfo.wProcessorArchitecture == 9 )
            {
              v14 = std::operator+<unsigned short>(v25, AppPlatformFinder::GOGGamesRegKeyPath64, v20[0]);
              std::wstring::operator=(lpSubKey, v14);
              p_SystemInfo = (struct _SYSTEM_INFO *)v25;
            }
            else
            {
              v16 = std::operator+<unsigned short>(&SystemInfo, AppPlatformFinder::GOGGamesRegKeyPath, v20[0]);
              std::wstring::operator=(lpSubKey, v16);
              p_SystemInfo = &SystemInfo;
            }
            std::wstring::~wstring(p_SystemInfo);
            phkResult = 0;
            v17 = (const WCHAR *)lpSubKey;
            if ( lpSubKey[3] > (LPCWSTR)7 )
              v17 = lpSubKey[0];
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0x20019u, &phkResult) )
            {
              std::wstring::operator=(v8 + *a2 + 336, Application::ApplicationSourceGOG);
              Application::SaveApplicationToCache((Application *)(v8 + *a2), v3);
              (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 64LL))(v8 + *a2 + 16);
              (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 16LL))(v8 + *a2 + 16);
              (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 32LL))(v8 + *a2 + 16);
              (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 24LL))(v8 + *a2 + 16);
              (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + *a2 + 16) + 8LL))(v8 + *a2 + 16);
              AslLogCallPrintf(
                3,
                (unsigned int)"AppPlatformFinder::GetGOGApplications",
                1058,
                (unsigned int)"GOG App - Name: %ws Vendor: %ws Version: %ws ProgramId: %ws Source: %ws");
              v3 = v19;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            std::wstring::~wstring(lpSubKey);
            std::vector<std::wstring>::_Tidy(v20);
          }
          std::wstring::~wstring(v23);
          std::wstring::~wstring(v24);
        }
      }
      v4 = *a2;
      result = 0xEFBEFBEFBEFBEFBFuLL * ((a2[1] - *a2) >> 4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18010449c  mov     rax, rsp
0x18010449f  push    rbp
0x1801044a0  push    rsi
0x1801044a1  push    rdi
0x1801044a2  push    r12
0x1801044a4  push    r13
0x1801044a6  push    r14
0x1801044a8  push    r15
0x1801044aa  lea     rbp, [rax-78h]
0x1801044ae  sub     rsp, 140h
0x1801044b5  mov     qword ptr [rsp+78h], 0FFFFFFFFFFFFFFFEh
0x1801044be  mov     [rax+18h], rbx
0x1801044c2  mov     rax, cs:__security_cookie
0x1801044c9  xor     rax, rsp
0x1801044cc  mov     [rbp+70h+var_40], rax
0x1801044d0  mov     rdi, rdx
0x1801044d3  mov     r14, rcx
0x1801044d6  mov     [rsp+170h+var_118], rcx
0x1801044db  mov     rdx, [rdx]
0x1801044de  mov     rax, [rdi+8]
0x1801044e2  sub     rax, rdx
0x1801044e5  sar     rax, 4
0x1801044e9  mov     r15, 0EFBEFBEFBEFBEFBFh
0x1801044f3  imul    rax, r15
0x1801044f7  test    rax, rax
0x1801044fa  jz      loc_180104834
0x180104500  xor     r13d, r13d
0x180104503  lea     rbx, ?AppPlatformNameGOG@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::AppPlatformNameGOG
0x18010450a  cmp     cs:qword_180183568, 7
0x180104512  cmova   rbx, cs:?AppPlatformNameGOG@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::AppPlatformNameGOG
0x18010451a  imul    rsi, r13, 3F0h
0x180104521  lea     rcx, [rdx+10h]
0x180104525  add     rcx, rsi
0x180104528  mov     rax, [rcx]
0x18010452b  mov     rax, [rax+8]
0x18010452f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104534  cmp     qword ptr [rax+18h], 7
0x180104539  jbe     short loc_18010453E
0x18010453b  mov     rax, [rax]
0x18010453e  mov     rdx, rbx
0x180104541  mov     rcx, rax
0x180104544  call    cs:__imp__o__wcsicmp
0x18010454a  test    eax, eax
0x18010454c  jz      loc_180104816
0x180104552  lea     rbx, ?AppPlatformPublisherGOG@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::AppPlatformPublisherGOG
0x180104559  cmp     cs:qword_180183588, 7
0x180104561  cmova   rbx, cs:?AppPlatformPublisherGOG@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::AppPlatformPublisherGOG
0x180104569  mov     rcx, [rdi]
0x18010456c  add     rcx, 10h
0x180104570  add     rcx, rsi
0x180104573  mov     rax, [rcx]
0x180104576  mov     rax, [rax+18h]
0x18010457a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010457f  cmp     qword ptr [rax+18h], 7
0x180104584  jbe     short loc_180104589
0x180104586  mov     rax, [rax]
0x180104589  mov     rdx, rbx
0x18010458c  mov     rcx, rax
0x18010458f  call    cs:__imp__o__wcsicmp
0x180104595  test    eax, eax
0x180104597  jnz     loc_180104816
0x18010459d  mov     rcx, [rdi]
0x1801045a0  add     rcx, 10h
0x1801045a4  add     rcx, rsi
0x1801045a7  mov     rax, [rcx]
0x1801045aa  mov     rax, [rax+58h]
0x1801045ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801045b3  mov     rdx, rax
0x1801045b6  lea     rcx, [rbp+70h+var_80]
0x1801045ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801045bf  nop
0x1801045c0  lea     rdx, [rbp+70h+var_80]
0x1801045c4  lea     rcx, [rbp+70h+var_A0]
0x1801045c8  call    ?GetFileNameFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetFileNameFromPath(std::wstring const &)
0x1801045cd  nop
0x1801045ce  lea     rdx, asc_18013B8C8; "_"
0x1801045d5  lea     rcx, [rbp+70h+lpSubKey]
0x1801045d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801045de  nop
0x1801045df  lea     rdx, [rbp+70h+var_A0]
0x1801045e3  lea     rcx, [rbp+70h+lpSubKey]
0x1801045e7  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x1801045ec  mov     bl, al
0x1801045ee  lea     rcx, [rbp+70h+lpSubKey]
0x1801045f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801045f7  test    bl, bl
0x1801045f9  jz      loc_180104803
0x1801045ff  mov     r8d, 5Fh ; '_'
0x180104605  lea     rdx, [rbp+70h+var_A0]
0x180104609  lea     rcx, [rsp+60h]
0x18010460e  call    ?Split@Utility@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; Utility::Split(std::wstring &,ushort)
0x180104613  nop
0x180104614  lea     rcx, [rbp+70h+lpSubKey]
0x180104618  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010461d  nop
0x18010461e  xorps   xmm0, xmm0
0x180104621  movups  xmmword ptr [rbp+70h+SystemInfo], xmm0
0x180104625  movups  xmmword ptr [rbp+70h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180104629  movups  xmmword ptr [rbp+70h+SystemInfo.dwNumberOfProcessors], xmm0
0x18010462d  lea     rcx, [rbp+70h+SystemInfo]; lpSystemInfo
0x180104631  call    cs:__imp_GetSystemInfo
0x180104637  mov     r8, [rsp+60h]
0x18010463c  cmp     word ptr [rbp+70h+SystemInfo], 9
0x180104641  jnz     short loc_180104665
0x180104643  lea     rdx, ?GOGGamesRegKeyPath64@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::GOGGamesRegKeyPath64
0x18010464a  lea     rcx, [rbp+70h+var_60]
0x18010464e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180104653  mov     rdx, rax
0x180104656  lea     rcx, [rbp+70h+lpSubKey]
0x18010465a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010465f  lea     rcx, [rbp+70h+var_60]
0x180104663  jmp     short loc_180104685
0x180104665  lea     rdx, ?GOGGamesRegKeyPath@AppPlatformFinder@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppPlatformFinder::GOGGamesRegKeyPath
0x18010466c  lea     rcx, [rbp+70h+SystemInfo]
0x180104670  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180104675  mov     rdx, rax
0x180104678  lea     rcx, [rbp+70h+lpSubKey]
0x18010467c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180104681  lea     rcx, [rbp+70h+SystemInfo]
0x180104685  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010468a  nop
0x18010468b  mov     [rsp+170h+var_120], 0
0x180104694  lea     rdx, [rbp+70h+lpSubKey]
0x180104698  cmp     [rbp+70h+var_D8], 7
0x18010469d  cmova   rdx, [rbp+70h+lpSubKey]; lpSubKey
0x1801046a2  lea     rax, [rsp+170h+var_120]
0x1801046a7  mov     [rsp+170h+phkResult], rax; phkResult
0x1801046ac  mov     r9d, 20019h; samDesired
0x1801046b2  xor     r8d, r8d; ulOptions
0x1801046b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801046bc  call    cs:__imp_RegOpenKeyExW
0x1801046c2  test    eax, eax
0x1801046c4  jnz     loc_1801047E3
0x1801046ca  mov     rcx, [rdi]
0x1801046cd  add     rcx, 150h
0x1801046d4  add     rcx, rsi
0x1801046d7  lea     rdx, ?ApplicationSourceGOG@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceGOG
0x1801046de  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801046e3  mov     rcx, [rdi]
0x1801046e6  add     rcx, rsi; this
0x1801046e9  mov     rdx, r14; struct ConfigSettings *
0x1801046ec  call    ?SaveApplicationToCache@Application@@QEAAXAEBVConfigSettings@@@Z; Application::SaveApplicationToCache(ConfigSettings const &)
0x1801046f1  mov     rcx, [rdi]
0x1801046f4  add     rcx, 10h
0x1801046f8  add     rcx, rsi
0x1801046fb  mov     rax, [rcx]
0x1801046fe  mov     rax, [rax+40h]
0x180104702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104707  mov     r12, rax
0x18010470a  cmp     qword ptr [rax+18h], 7
0x18010470f  jbe     short loc_180104714
0x180104711  mov     r12, [rax]
0x180104714  mov     rcx, [rdi]
0x180104717  add     rcx, 10h
0x18010471b  add     rcx, rsi
0x18010471e  mov     rax, [rcx]
0x180104721  mov     rax, [rax+10h]
0x180104725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010472a  mov     r15, rax
0x18010472d  cmp     qword ptr [rax+18h], 7
0x180104732  jbe     short loc_180104737
0x180104734  mov     r15, [rax]
0x180104737  mov     rcx, [rdi]
0x18010473a  add     rcx, 10h
0x18010473e  add     rcx, rsi
0x180104741  mov     rax, [rcx]
0x180104744  mov     rax, [rax+20h]
0x180104748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010474d  mov     r14, rax
0x180104750  cmp     qword ptr [rax+18h], 7
0x180104755  jbe     short loc_18010475A
0x180104757  mov     r14, [rax]
0x18010475a  mov     rcx, [rdi]
0x18010475d  add     rcx, 10h
0x180104761  add     rcx, rsi
0x180104764  mov     rax, [rcx]
0x180104767  mov     rax, [rax+18h]
0x18010476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104770  mov     rbx, rax
0x180104773  cmp     qword ptr [rax+18h], 7
0x180104778  jbe     short loc_18010477D
0x18010477a  mov     rbx, [rax]
0x18010477d  mov     rcx, [rdi]
0x180104780  add     rcx, 10h
0x180104784  add     rcx, rsi
0x180104787  mov     rax, [rcx]
0x18010478a  mov     rax, [rax+8]
0x18010478e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104793  cmp     qword ptr [rax+18h], 7
0x180104798  jbe     short loc_18010479D
0x18010479a  mov     rax, [rax]
0x18010479d  mov     [rsp+40h], r12
0x1801047a2  mov     [rsp+170h+var_138], r15
0x1801047a7  mov     [rsp+170h+var_140], r14
0x1801047ac  mov     [rsp+170h+var_148], rbx
0x1801047b1  mov     [rsp+170h+phkResult], rax
0x1801047b6  lea     r9, aGogAppNameWsVe; "GOG App - Name: %ws Vendor: %ws Version"...
0x1801047bd  mov     r8d, 422h
0x1801047c3  lea     rdx, aAppplatformfin; "AppPlatformFinder::GetGOGApplications"
0x1801047ca  mov     ecx, 3
0x1801047cf  call    AslLogCallPrintf
0x1801047d4  mov     r14, [rsp+170h+var_118]
0x1801047d9  mov     r15, 0EFBEFBEFBEFBEFBFh
0x1801047e3  lea     rcx, [rsp+170h+var_120]
0x1801047e8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801047ed  nop
0x1801047ee  lea     rcx, [rbp+70h+lpSubKey]
0x1801047f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801047f7  nop
0x1801047f8  lea     rcx, [rsp+60h]
0x1801047fd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180104802  nop
0x180104803  lea     rcx, [rbp+70h+var_A0]
0x180104807  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010480c  nop
0x18010480d  lea     rcx, [rbp+70h+var_80]
0x180104811  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180104816  inc     r13
0x180104819  mov     rdx, [rdi]
0x18010481c  mov     rax, [rdi+8]
0x180104820  sub     rax, rdx
0x180104823  sar     rax, 4
0x180104827  imul    rax, r15
0x18010482b  cmp     r13, rax
0x18010482e  jb      loc_180104503
0x180104834  mov     rcx, [rbp+70h+var_40]
0x180104838  xor     rcx, rsp; StackCookie
0x18010483b  call    __security_check_cookie
0x180104840  mov     rbx, [rsp+170h+arg_10]
0x180104848  add     rsp, 140h
0x18010484f  pop     r15
0x180104851  pop     r14
0x180104853  pop     r13
0x180104855  pop     r12
0x180104857  pop     rdi
0x180104858  pop     rsi
0x180104859  pop     rbp
0x18010485a  retn
```
