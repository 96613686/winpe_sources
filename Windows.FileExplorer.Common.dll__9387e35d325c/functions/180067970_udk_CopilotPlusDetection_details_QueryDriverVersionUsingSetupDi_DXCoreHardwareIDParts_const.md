# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x180067970`
- end: `0x180067fa6`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1590`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180066494`

## callees

- `0x180015fa0`
- `0x180016440`
- `0x1800348e8`
- `0x180037340`
- `0x180037780`
- `0x18005eed0`
- `0x18005f9d4`
- `0x18006031c`
- `0x1800663a0`
- `0x18006786c`
- `0x180067970`
- `0x18006b7d0`
- `0x18006bf78`
- `0x180089010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180067d68`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180067d68`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180067d4e`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180067d4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180067d35`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180067d35`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180067cf7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180067cf7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800679c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800679c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800679ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800679ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e40`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067c46`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180067c46`

## string_xrefs

- `0x1800679be`: `setupapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
udk::CopilotPlusDetection::details *__fastcall udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(
        udk::CopilotPlusDetection::details *this,
        const struct DXCoreHardwareIDParts *a2)
{
  HMODULE Library; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  const char *v7; // r9
  FARPROC ProcAddress; // r14
  const char *v9; // r9
  FARPROC v10; // r13
  const char *v11; // r9
  FARPROC v12; // r12
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned int i; // esi
  const char *v18; // r9
  __int64 trivial_2; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  const WCHAR *v22; // r8
  const WCHAR *v23; // rcx
  const char *v24; // r9
  __int16 v25; // ax
  unsigned __int64 v26; // rsi
  unsigned __int64 j; // rbx
  _DWORD *v28; // rax
  const wchar_t *v29; // r12
  __int16 v30; // cx
  wchar_t *v31; // r14
  __int64 v32; // r14
  __int16 v33; // ax
  const char *v34; // r9
  udk::CopilotPlusDetection::details *result; // rax
  const char *v36; // r9
  wchar_t *EndPtr; // [rsp+50h] [rbp-138h] BYREF
  __int128 v38; // [rsp+58h] [rbp-130h] BYREF
  __int64 v39; // [rsp+68h] [rbp-120h]
  int v40; // [rsp+70h] [rbp-118h] BYREF
  HMODULE v41; // [rsp+78h] [rbp-110h] BYREF
  udk::CopilotPlusDetection::details *v42; // [rsp+80h] [rbp-108h]
  _DWORD *v43; // [rsp+88h] [rbp-100h]
  __int64 v44; // [rsp+90h] [rbp-F8h]
  FARPROC v45; // [rsp+98h] [rbp-F0h]
  char v46; // [rsp+A0h] [rbp-E8h]
  FARPROC v47; // [rsp+A8h] [rbp-E0h]
  _DWORD v48[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v51; // [rsp+D8h] [rbp-B0h]
  _OWORD v52[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v54[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v42 = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  try
  {
    v6 = Library;
    v41 = Library;
    if ( !Library )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v5);
    ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v7);
    v10 = GetProcAddress(v6, "SetupDiDestroyDeviceInfoList");
    if ( !v10 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v9);
    v12 = GetProcAddress(v6, "SetupDiEnumDeviceInfo");
    if ( !v12 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v11);
    EndPtr = (wchar_t *)GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
    if ( !EndPtr )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v13);
    v47 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
    if ( !v47 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v14);
    udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
    v48[0] = -266691245;
    v48[1] = 1221738486;
    v48[2] = -1480026209;
    v48[3] = 216091392;
    v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v48, 0, 0, 2);
    v16 = v15;
    if ( v15 != -1 )
    {
      v44 = v15;
      v45 = v10;
      v46 = 1;
      memset(v52, 0, sizeof(v52));
      LODWORD(v52[0]) = 32;
      for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v16, i, v52); ++i )
      {
        v38 = 0;
        v39 = 0;
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v38);
        if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))EndPtr)(
                v16,
                v52,
                v38,
                (__int64)(*((_QWORD *)&v38 + 1) - v38) >> 1,
                0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
            v18);
        trivial_2 = _std_find_trivial_2(v38, *((_QWORD *)&v38 + 1), 0);
        v20 = _std_find_trivial_2(v38, trivial_2, 92);
        if ( v20 != *((_QWORD *)&v38 + 1) && trivial_2 != *((_QWORD *)&v38 + 1) )
        {
          v21 = v20 + 2;
          if ( v20 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v21) >> 1) >= *(_QWORD *)cchCount2 )
          {
            v22 = (const WCHAR *)(v38 + 2 * ((v21 - (__int64)v38) >> 1));
            v23 = (const WCHAR *)lpString1;
            if ( v51 > 7 )
              v23 = lpString1[0];
            if ( CompareStringOrdinal(v23, cchCount2[0], v22, cchCount2[0], 1) == 2 )
            {
              v40 = 0;
              if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v47)(
                      v16,
                      v52,
                      &DEVPKEY_Device_DriverVersion,
                      &v40) )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0xC2,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  v24);
              v25 = 0;
              v47 = 0;
              v26 = 0;
              for ( j = 0; j < 4; ++j )
              {
                if ( v26 >= 0x18 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xCB,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v54);
                std::wstring::wstring(String, &v54[v26]);
                v28 = (_DWORD *)_o__errno();
                v43 = v28;
                v29 = (const wchar_t *)String;
                if ( String[3] > (wchar_t *)7 )
                  v29 = String[0];
                EndPtr = 0;
                *v28 = 0;
                v30 = wcstol(v29, &EndPtr, 10);
                v31 = EndPtr;
                if ( v29 == EndPtr )
                  std::_Xinvalid_argument("invalid stoi argument");
                if ( *v43 == 34 )
                  std::_Xout_of_range("stoi argument out of range");
                v32 = v31 - v29;
                *((_WORD *)&v48[-2] + j) = v30;
                std::wstring::_Tidy_deallocate(String);
                v33 = v54[v32 + v26];
                if ( j == 3 )
                {
                  if ( v33 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xDB,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v54);
                }
                else
                {
                  if ( v33 != 46 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xD3,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v54);
                  v26 += v32 + 1;
                }
                v25 = (__int16)v47;
              }
              *(_WORD *)this = HIWORD(v47);
              *((_WORD *)this + 1) = WORD2(v47);
              *((_WORD *)this + 2) = WORD1(v47);
              *((_WORD *)this + 3) = v25;
              std::vector<unsigned short>::_Tidy(&v38);
              ((void (__fastcall *)(__int64))v10)(v16);
              std::wstring::_Tidy_deallocate(lpString1);
              wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v41);
              return this;
            }
          }
        }
        std::vector<unsigned short>::_Tidy(&v38);
      }
      if ( GetLastError() != 259 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
          v36);
      ((void (__fastcall *)(__int64))v10)(v16);
    }
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)this = 0;
    std::wstring::_Tidy_deallocate(lpString1);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v41);
    result = this;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v34);
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)v42 = 0;
    return v42;
  }
  return result;
}

```

## disassembly

```asm
0x180067970  mov     [rsp+arg_10], rbx
0x180067975  mov     [rsp+arg_18], rsi
0x18006797a  push    rdi
0x18006797b  push    r12
0x18006797d  push    r13
0x18006797f  push    r14
0x180067981  push    r15
0x180067983  sub     rsp, 160h
0x18006798a  mov     rax, cs:__security_cookie
0x180067991  xor     rax, rsp
0x180067994  mov     [rsp+188h+var_38], rax
0x18006799c  mov     rsi, rdx
0x18006799f  mov     rdi, rcx
0x1800679a2  mov     [rsp+188h+var_108], rcx
0x1800679aa  add     rdx, 4
0x1800679ae  mov     rcx, rsi
0x1800679b1  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x1800679b6  xor     edx, edx; hFile
0x1800679b8  mov     r8d, 800h; dwFlags
0x1800679be  lea     rcx, aSetupapiDll; "setupapi.dll"
0x1800679c5  call    cs:__imp_LoadLibraryExW
0x1800679cb  mov     rbx, rax
0x1800679ce  mov     [rsp+188h+var_110], rax
0x1800679d3  mov     rcx, [rsp+188h]; this
0x1800679db  test    rax, rax
0x1800679de  jz      loc_180067F93
0x1800679e4  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x1800679eb  mov     rcx, rax; hModule
0x1800679ee  call    cs:__imp_GetProcAddress
0x1800679f4  mov     r14, rax
0x1800679f7  mov     rcx, [rsp+188h]; this
0x1800679ff  test    rax, rax
0x180067a02  jz      loc_180067EBB
0x180067a08  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x180067a0f  mov     rcx, rbx; hModule
0x180067a12  call    cs:__imp_GetProcAddress
0x180067a18  mov     r13, rax
0x180067a1b  mov     rcx, [rsp+188h]; this
0x180067a23  test    rax, rax
0x180067a26  jz      loc_180067ECC
0x180067a2c  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x180067a33  mov     rcx, rbx; hModule
0x180067a36  call    cs:__imp_GetProcAddress
0x180067a3c  mov     r12, rax
0x180067a3f  mov     rcx, [rsp+188h]; this
0x180067a47  test    rax, rax
0x180067a4a  jz      loc_180067EDD
0x180067a50  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x180067a57  mov     rcx, rbx; hModule
0x180067a5a  call    cs:__imp_GetProcAddress
0x180067a60  mov     [rsp+188h+EndPtr], rax
0x180067a65  mov     rcx, [rsp+188h]; this
0x180067a6d  test    rax, rax
0x180067a70  jz      loc_180067EEE
0x180067a76  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x180067a7d  mov     rcx, rbx; hModule
0x180067a80  call    cs:__imp_GetProcAddress
0x180067a86  mov     [rsp+188h+var_E0], rax
0x180067a8e  mov     rcx, [rsp+188h]; this
0x180067a96  xor     ebx, ebx
0x180067a98  test    rax, rax
0x180067a9b  jz      loc_180067EFF
0x180067aa1  mov     rdx, rsi
0x180067aa4  lea     rcx, [rsp+188h+lpString1]
0x180067aac  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x180067ab1  nop
0x180067ab2  mov     [rsp+188h+var_D8], 0F01A9D53h
0x180067abd  mov     [rsp+188h+var_D4], 48D23FF6h
0x180067ac8  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x180067ad3  mov     [rsp+188h+var_CC], 0CE14B00h
0x180067ade  mov     r9d, 2
0x180067ae4  xor     r8d, r8d
0x180067ae7  xor     edx, edx
0x180067ae9  lea     rcx, [rsp+188h+var_D8]
0x180067af1  mov     rax, r14
0x180067af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067af9  mov     r15, rax
0x180067afc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067b00  jz      loc_180067E5D
0x180067b06  mov     [rsp+188h+var_F8], rax
0x180067b0e  mov     [rsp+188h+var_F0], r13
0x180067b16  mov     [rsp+188h+var_E8], 1
0x180067b1e  xorps   xmm0, xmm0
0x180067b21  movups  [rsp+188h+var_A8], xmm0
0x180067b29  movups  [rsp+188h+var_98], xmm0
0x180067b31  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x180067b3c  mov     esi, ebx
0x180067b3e  mov     r14, [rsp+188h+EndPtr]
0x180067b43  lea     r8, [rsp+188h+var_A8]
0x180067b4b  mov     edx, esi
0x180067b4d  mov     rcx, r15
0x180067b50  mov     rax, r12
0x180067b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b58  test    eax, eax
0x180067b5a  jz      loc_180067E40
0x180067b60  xorps   xmm0, xmm0
0x180067b63  movdqu  [rsp+188h+var_130], xmm0
0x180067b69  mov     [rsp+188h+var_120], rbx
0x180067b6e  lea     rcx, [rsp+188h+var_130]
0x180067b73  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180067b78  mov     r8, qword ptr [rsp+188h+var_130]
0x180067b7d  mov     r9, qword ptr [rsp+188h+var_130+8]
0x180067b82  sub     r9, r8
0x180067b85  sar     r9, 1
0x180067b88  mov     qword ptr [rsp+188h+bIgnoreCase], rbx
0x180067b8d  lea     rdx, [rsp+188h+var_A8]
0x180067b95  mov     rcx, r15
0x180067b98  mov     rax, r14
0x180067b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ba0  mov     rcx, [rsp+188h]; this
0x180067ba8  test    eax, eax
0x180067baa  jz      loc_180067F11
0x180067bb0  xor     r8d, r8d
0x180067bb3  mov     rdx, qword ptr [rsp+188h+var_130+8]
0x180067bb8  mov     rcx, qword ptr [rsp+188h+var_130]
0x180067bbd  call    __std_find_trivial_2
0x180067bc2  mov     rbx, rax
0x180067bc5  mov     r8d, 5Ch ; '\'
0x180067bcb  mov     rdx, rax
0x180067bce  mov     rcx, qword ptr [rsp+188h+var_130]
0x180067bd3  call    __std_find_trivial_2
0x180067bd8  cmp     rax, qword ptr [rsp+188h+var_130+8]
0x180067bdd  jz      loc_180067E2D
0x180067be3  cmp     rbx, qword ptr [rsp+188h+var_130+8]
0x180067be8  jz      loc_180067E2D
0x180067bee  lea     rcx, [rax+2]
0x180067bf2  cmp     rcx, rbx
0x180067bf5  jz      loc_180067E2D
0x180067bfb  sub     rbx, rcx
0x180067bfe  sar     rbx, 1
0x180067c01  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x180067c09  cmp     rbx, rdx
0x180067c0c  jb      loc_180067E2D
0x180067c12  mov     rax, qword ptr [rsp+188h+var_130]
0x180067c17  sub     rcx, rax
0x180067c1a  sar     rcx, 1
0x180067c1d  lea     r8, [rax+rcx*2]; lpString2
0x180067c21  lea     rcx, [rsp+188h+lpString1]
0x180067c29  cmp     [rsp+188h+var_B0], 7
0x180067c32  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x180067c3b  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180067c43  mov     r9d, edx; cchCount2
0x180067c46  call    cs:__imp_CompareStringOrdinal
0x180067c4c  cmp     eax, 2
0x180067c4f  jnz     loc_180067E2D
0x180067c55  xor     r14d, r14d
0x180067c58  mov     [rsp+188h+var_118], r14d
0x180067c5d  mov     [rsp+188h+var_150], r14d
0x180067c62  mov     [rsp+188h+var_158], r14
0x180067c67  mov     [rsp+188h+var_160], 30h ; '0'
0x180067c6f  lea     rax, [rsp+188h+var_68]
0x180067c77  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x180067c7c  lea     r9, [rsp+188h+var_118]
0x180067c81  lea     r8, DEVPKEY_Device_DriverVersion
0x180067c88  lea     rdx, [rsp+188h+var_A8]
0x180067c90  mov     rcx, r15
0x180067c93  mov     rax, [rsp+188h+var_E0]
0x180067c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ca0  mov     rcx, [rsp+188h]; this
0x180067ca8  test    eax, eax
0x180067caa  jz      loc_180067F22
0x180067cb0  mov     rax, r14
0x180067cb3  mov     [rsp+188h+var_E0], rax
0x180067cbb  mov     rsi, r14
0x180067cbe  mov     rbx, r14
0x180067cc1  cmp     rbx, 4
0x180067cc5  jnb     loc_180067DD2
0x180067ccb  mov     rcx, [rsp+188h]; this
0x180067cd3  cmp     rsi, 18h
0x180067cd7  jnb     loc_180067F33
0x180067cdd  lea     rdx, [rsp+188h+var_68]
0x180067ce5  lea     rdx, [rdx+rsi*2]
0x180067ce9  lea     rcx, [rsp+188h+String]
0x180067cf1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180067cf6  nop
0x180067cf7  call    cs:__imp__o__errno
0x180067cfd  mov     [rsp+188h+var_100], rax
0x180067d05  lea     r12, [rsp+188h+String]
0x180067d0d  cmp     [rsp+188h+var_70], 7
0x180067d16  cmova   r12, [rsp+188h+String]
0x180067d1f  mov     [rsp+188h+EndPtr], r14
0x180067d24  mov     [rax], r14d
0x180067d27  mov     r8d, 0Ah; Radix
0x180067d2d  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x180067d32  mov     rcx, r12; String
0x180067d35  call    cs:__imp_wcstol
0x180067d3b  mov     ecx, eax
0x180067d3d  mov     r14, [rsp+188h+EndPtr]
0x180067d42  cmp     r12, r14
0x180067d45  jnz     short loc_180067D54
0x180067d47  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x180067d4e  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x180067d54  mov     rax, [rsp+188h+var_100]
0x180067d5c  cmp     dword ptr [rax], 22h ; '"'
0x180067d5f  jnz     short loc_180067D6E
0x180067d61  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x180067d68  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180067d6e  sub     r14, r12
0x180067d71  sar     r14, 1
0x180067d74  mov     word ptr [rsp+rbx*2+188h+var_E0], cx
0x180067d7c  lea     rcx, [rsp+188h+String]
0x180067d84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067d89  lea     rdx, [r14+rsi]
0x180067d8d  movzx   eax, [rsp+rdx*2+188h+var_68]
0x180067d95  mov     rcx, [rsp+188h]; this
0x180067d9d  cmp     rbx, 3
0x180067da1  jz      short loc_180067DC4
0x180067da3  cmp     ax, 2Eh ; '.'
0x180067da7  jnz     loc_180067F4A
0x180067dad  lea     rsi, [rdx+1]
0x180067db1  xor     r14d, r14d
0x180067db4  inc     rbx
0x180067db7  mov     rax, [rsp+188h+var_E0]
0x180067dbf  jmp     loc_180067CC1
0x180067dc4  xor     r14d, r14d
0x180067dc7  test    ax, ax
0x180067dca  jnz     loc_180067F61
0x180067dd0  jmp     short loc_180067DB4
0x180067dd2  movzx   edx, word ptr [rsp+188h+var_E0+6]
0x180067dda  mov     [rdi], dx
0x180067ddd  movzx   edx, word ptr [rsp+188h+var_E0+4]
0x180067de5  mov     [rdi+2], dx
0x180067de9  movzx   edx, word ptr [rsp+188h+var_E0+2]
0x180067df1  mov     [rdi+4], dx
0x180067df5  mov     [rdi+6], ax
0x180067df9  lea     rcx, [rsp+188h+var_130]
0x180067dfe  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180067e03  nop
0x180067e04  mov     rcx, r15
0x180067e07  mov     rax, r13
0x180067e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e0f  nop
0x180067e10  lea     rcx, [rsp+188h+lpString1]
0x180067e18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067e1d  nop
0x180067e1e  lea     rcx, [rsp+188h+var_110]
0x180067e23  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180067e28  mov     rax, rdi
0x180067e2b  jmp     short loc_180067E8E
0x180067e2d  inc     esi
0x180067e2f  lea     rcx, [rsp+188h+var_130]
0x180067e34  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180067e39  xor     ebx, ebx
0x180067e3b  jmp     loc_180067B43
0x180067e40  call    cs:__imp_GetLastError
0x180067e46  cmp     eax, 103h
0x180067e4b  jnz     loc_180067F79
0x180067e51  mov     rcx, r15
0x180067e54  mov     rax, r13
0x180067e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e5c  nop
0x180067e5d  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
0x180067e62  mov     qword ptr [rdi], 0
0x180067e69  lea     rcx, [rsp+188h+lpString1]
0x180067e71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067e76  nop
0x180067e77  lea     rcx, [rsp+188h+var_110]
0x180067e7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180067e81  mov     rax, rdi
0x180067e84  jmp     short loc_180067E8E
0x180067e86  mov     rax, [rsp+188h+var_108]
0x180067e8e  mov     rcx, [rsp+188h+var_38]
0x180067e96  xor     rcx, rsp; StackCookie
0x180067e99  call    __security_check_cookie
0x180067e9e  lea     r11, [rsp+188h+var_28]
0x180067ea6  mov     rbx, [r11+40h]
0x180067eaa  mov     rsi, [r11+48h]
0x180067eae  mov     rsp, r11
0x180067eb1  pop     r15
0x180067eb3  pop     r14
0x180067eb5  pop     r13
0x180067eb7  pop     r12
0x180067eb9  pop     rdi
0x180067eba  retn
0x180067ebb  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067ec2  mov     edx, 89h; void *
0x180067ec7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067ecc  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067ed3  mov     edx, 8Bh; void *
0x180067ed8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067edd  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067ee4  mov     edx, 8Dh; void *
0x180067ee9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067eee  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067ef5  mov     edx, 8Fh; void *
0x180067efa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067eff  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067f06  mov     edx, 91h; void *
0x180067f0b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067f11  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067f18  mov     edx, 0ABh; void *
0x180067f1d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067f22  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067f29  mov     edx, 0C2h; void *
0x180067f2e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180067f33  mov     r9d, 80070057h; char *
0x180067f39  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180067f40  mov     edx, 0CBh; void *
0x180067f45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067f4a  mov     r9d, 80070057h; char *
  ... truncated ...
```
