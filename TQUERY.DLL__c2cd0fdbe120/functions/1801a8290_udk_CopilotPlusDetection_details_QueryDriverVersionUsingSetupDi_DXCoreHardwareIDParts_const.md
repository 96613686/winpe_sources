# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x1801a8290`
- end: `0x1801a888f`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1535`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801a7294`

## callees

- `0x180038f08`
- `0x18006380c`
- `0x18008b084`
- `0x18013e868`
- `0x180147154`
- `0x18017cd40`
- `0x180188d90`
- `0x18018e260`
- `0x1801a1694`
- `0x1801a2bf4`
- `0x1801a43f4`
- `0x1801a71a0`
- `0x1801a8180`
- `0x1801a8290`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801a82e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801a82e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a830e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a8332`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a8356`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a837a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a83a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a830e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a8332`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a8356`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a837a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a83a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8729`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a855e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a855e`

## string_xrefs

- `0x1801a82de`: `setupapi.dll`

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
  FARPROC v10; // r15
  const char *v11; // r9
  FARPROC v12; // r12
  const char *v13; // r9
  const char *v14; // r9
  FARPROC v15; // r13
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned int i; // esi
  const char *v19; // r9
  __int64 trivial_2; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  const WCHAR *v24; // rcx
  const char *v25; // r9
  __int16 v26; // ax
  unsigned __int64 v27; // rbx
  unsigned __int64 j; // rsi
  const char *v29; // r9
  udk::CopilotPlusDetection::details *result; // rax
  const char *v31; // r9
  FARPROC v32; // [rsp+50h] [rbp-128h]
  __int128 v33; // [rsp+58h] [rbp-120h] BYREF
  __int64 v34; // [rsp+68h] [rbp-110h]
  int v35; // [rsp+70h] [rbp-108h] BYREF
  HMODULE v36; // [rsp+78h] [rbp-100h] BYREF
  udk::CopilotPlusDetection::details *v37; // [rsp+80h] [rbp-F8h]
  __int64 v38; // [rsp+88h] [rbp-F0h]
  FARPROC v39; // [rsp+90h] [rbp-E8h]
  char v40; // [rsp+98h] [rbp-E0h]
  __int64 v41; // [rsp+A0h] [rbp-D8h]
  _DWORD v42[4]; // [rsp+A8h] [rbp-D0h] BYREF
  LPCWCH lpString1[2]; // [rsp+B8h] [rbp-C0h] BYREF
  int cchCount2[2]; // [rsp+C8h] [rbp-B0h]
  unsigned __int64 v45; // [rsp+D0h] [rbp-A8h]
  _OWORD v46[2]; // [rsp+D8h] [rbp-A0h] BYREF
  wchar_t String[16]; // [rsp+F8h] [rbp-80h] BYREF
  _WORD v48[24]; // [rsp+118h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v37 = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  try
  {
    v6 = Library;
    v36 = Library;
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
    v32 = GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
    if ( !v32 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v13);
    v15 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
    if ( !v15 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v14);
    udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
    v42[0] = -266691245;
    v42[1] = 1221738486;
    v42[2] = -1480026209;
    v42[3] = 216091392;
    v16 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v42, 0, 0, 2);
    v17 = v16;
    if ( v16 != -1 )
    {
      v38 = v16;
      v39 = v10;
      v40 = 1;
      memset(v46, 0, sizeof(v46));
      LODWORD(v46[0]) = 32;
      for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v17, i, v46); ++i )
      {
        v33 = 0;
        v34 = 0;
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&v33);
        if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v32)(
                v17,
                v46,
                v33,
                (__int64)(*((_QWORD *)&v33 + 1) - v33) >> 1,
                0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
            v19);
        trivial_2 = _std_find_trivial_2(v33, *((_QWORD *)&v33 + 1), 0);
        v21 = _std_find_trivial_2(v33, trivial_2, 92);
        if ( v21 != *((_QWORD *)&v33 + 1) && trivial_2 != *((_QWORD *)&v33 + 1) )
        {
          v22 = v21 + 2;
          if ( v21 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v22) >> 1) >= *(_QWORD *)cchCount2 )
          {
            v23 = (const WCHAR *)(v33 + 2 * ((v22 - (__int64)v33) >> 1));
            v24 = (const WCHAR *)lpString1;
            if ( v45 > 7 )
              v24 = lpString1[0];
            if ( CompareStringOrdinal(v24, cchCount2[0], v23, cchCount2[0], 1) == 2 )
            {
              v35 = 0;
              if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v15)(
                      v17,
                      v46,
                      &DEVPKEY_Device_DriverVersion,
                      &v35) )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0xC2,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  v25);
              v26 = 0;
              v41 = 0;
              v27 = 0;
              for ( j = 0; j < 4; ++j )
              {
                if ( v27 >= 0x18 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xCB,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v48);
                std::wstring::wstring(String, &v48[v27]);
                *((_WORD *)&v42[-2] + j) = std::stoi(String);
                std::wstring::_Tidy_deallocate(String);
                if ( j == 3 )
                {
                  if ( v48[v27] )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xDB,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v48);
                }
                else
                {
                  if ( v48[v27] != 46 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xD3,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v48);
                  ++v27;
                }
                v26 = v41;
              }
              *(_WORD *)this = HIWORD(v41);
              *((_WORD *)this + 1) = WORD2(v41);
              *((_WORD *)this + 2) = WORD1(v41);
              *((_WORD *)this + 3) = v26;
              if ( (_QWORD)v33 )
              {
                std::_Deallocate<16>(v33, 2 * ((v34 - (__int64)v33) >> 1));
                v33 = 0;
                v34 = 0;
              }
              ((void (__fastcall *)(__int64))v10)(v17);
              std::wstring::_Tidy_deallocate(lpString1);
              wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v36);
              return this;
            }
          }
        }
        if ( (_QWORD)v33 )
          std::_Deallocate<16>(v33, 2 * ((v34 - (__int64)v33) >> 1));
      }
      if ( GetLastError() != 259 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
          v31);
      ((void (__fastcall *)(__int64))v10)(v17);
    }
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)this = 0;
    std::wstring::_Tidy_deallocate(lpString1);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v36);
    result = this;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v29);
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)v37 = 0;
    return v37;
  }
  return result;
}

```

## disassembly

```asm
0x1801a8290  mov     [rsp+arg_10], rbx
0x1801a8295  mov     [rsp+arg_18], rsi
0x1801a829a  push    rdi
0x1801a829b  push    r12
0x1801a829d  push    r13
0x1801a829f  push    r14
0x1801a82a1  push    r15
0x1801a82a3  sub     rsp, 150h
0x1801a82aa  mov     rax, cs:__security_cookie
0x1801a82b1  xor     rax, rsp
0x1801a82b4  mov     [rsp+178h+var_30], rax
0x1801a82bc  mov     rsi, rdx
0x1801a82bf  mov     rdi, rcx
0x1801a82c2  mov     [rsp+178h+var_F8], rcx
0x1801a82ca  add     rdx, 4
0x1801a82ce  mov     rcx, rsi
0x1801a82d1  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x1801a82d6  xor     edx, edx; hFile
0x1801a82d8  mov     r8d, 800h; dwFlags
0x1801a82de  lea     rcx, aSetupapiDll; "setupapi.dll"
0x1801a82e5  call    cs:__imp_LoadLibraryExW
0x1801a82eb  mov     rbx, rax
0x1801a82ee  mov     [rsp+178h+var_100], rax
0x1801a82f3  mov     rcx, [rsp+178h]; this
0x1801a82fb  test    rax, rax
0x1801a82fe  jz      loc_1801A887C
0x1801a8304  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x1801a830b  mov     rcx, rax; hModule
0x1801a830e  call    cs:__imp_GetProcAddress
0x1801a8314  mov     r14, rax
0x1801a8317  mov     rcx, [rsp+178h]; this
0x1801a831f  test    rax, rax
0x1801a8322  jz      loc_1801A87A4
0x1801a8328  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x1801a832f  mov     rcx, rbx; hModule
0x1801a8332  call    cs:__imp_GetProcAddress
0x1801a8338  mov     r15, rax
0x1801a833b  mov     rcx, [rsp+178h]; this
0x1801a8343  test    rax, rax
0x1801a8346  jz      loc_1801A87B5
0x1801a834c  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x1801a8353  mov     rcx, rbx; hModule
0x1801a8356  call    cs:__imp_GetProcAddress
0x1801a835c  mov     r12, rax
0x1801a835f  mov     rcx, [rsp+178h]; this
0x1801a8367  test    rax, rax
0x1801a836a  jz      loc_1801A87C6
0x1801a8370  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x1801a8377  mov     rcx, rbx; hModule
0x1801a837a  call    cs:__imp_GetProcAddress
0x1801a8380  mov     [rsp+178h+var_128], rax
0x1801a8385  mov     rcx, [rsp+178h]; this
0x1801a838d  test    rax, rax
0x1801a8390  jz      loc_1801A87D7
0x1801a8396  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x1801a839d  mov     rcx, rbx; hModule
0x1801a83a0  call    cs:__imp_GetProcAddress
0x1801a83a6  mov     r13, rax
0x1801a83a9  mov     rcx, [rsp+178h]; this
0x1801a83b1  xor     ebx, ebx
0x1801a83b3  test    rax, rax
0x1801a83b6  jz      loc_1801A87E8
0x1801a83bc  mov     rdx, rsi
0x1801a83bf  lea     rcx, [rsp+178h+lpString1]
0x1801a83c7  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x1801a83cc  nop
0x1801a83cd  mov     [rsp+178h+var_D0], 0F01A9D53h
0x1801a83d8  mov     [rsp+178h+var_CC], 48D23FF6h
0x1801a83e3  mov     [rsp+178h+var_C8], 0A7C8979Fh
0x1801a83ee  mov     [rsp+178h+var_C4], 0CE14B00h
0x1801a83f9  mov     r9d, 2
0x1801a83ff  xor     r8d, r8d
0x1801a8402  xor     edx, edx
0x1801a8404  lea     rcx, [rsp+178h+var_D0]
0x1801a840c  mov     rax, r14
0x1801a840f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8414  mov     r14, rax
0x1801a8417  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a841b  jz      loc_1801A8746
0x1801a8421  mov     [rsp+178h+var_F0], rax
0x1801a8429  mov     [rsp+178h+var_E8], r15
0x1801a8431  mov     [rsp+178h+var_E0], 1
0x1801a8439  xorps   xmm0, xmm0
0x1801a843c  movups  [rsp+178h+var_A0], xmm0
0x1801a8444  movups  [rsp+178h+var_90], xmm0
0x1801a844c  mov     dword ptr [rsp+178h+var_A0], 20h ; ' '
0x1801a8457  mov     esi, ebx
0x1801a8459  lea     r8, [rsp+178h+var_A0]
0x1801a8461  mov     edx, esi
0x1801a8463  mov     rcx, r14
0x1801a8466  mov     rax, r12
0x1801a8469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a846e  test    eax, eax
0x1801a8470  jz      loc_1801A8729
0x1801a8476  xorps   xmm0, xmm0
0x1801a8479  movdqu  [rsp+178h+var_120], xmm0
0x1801a847f  mov     [rsp+178h+var_110], rbx
0x1801a8484  lea     rcx, [rsp+178h+var_120]
0x1801a8489  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801a848e  mov     r8, qword ptr [rsp+178h+var_120]
0x1801a8493  mov     r9, qword ptr [rsp+178h+var_120+8]
0x1801a8498  sub     r9, r8
0x1801a849b  sar     r9, 1
0x1801a849e  mov     qword ptr [rsp+178h+bIgnoreCase], rbx
0x1801a84a3  lea     rdx, [rsp+178h+var_A0]
0x1801a84ab  mov     rcx, r14
0x1801a84ae  mov     rax, [rsp+178h+var_128]
0x1801a84b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a84b8  mov     rcx, [rsp+178h]; this
0x1801a84c0  test    eax, eax
0x1801a84c2  jz      loc_1801A87FA
0x1801a84c8  xor     r8d, r8d
0x1801a84cb  mov     rdx, qword ptr [rsp+178h+var_120+8]
0x1801a84d0  mov     rcx, qword ptr [rsp+178h+var_120]
0x1801a84d5  call    __std_find_trivial_2
0x1801a84da  mov     rbx, rax
0x1801a84dd  mov     r8d, 5Ch ; '\'
0x1801a84e3  mov     rdx, rax
0x1801a84e6  mov     rcx, qword ptr [rsp+178h+var_120]
0x1801a84eb  call    __std_find_trivial_2
0x1801a84f0  cmp     rax, qword ptr [rsp+178h+var_120+8]
0x1801a84f5  jz      loc_1801A86FF
0x1801a84fb  cmp     rbx, qword ptr [rsp+178h+var_120+8]
0x1801a8500  jz      loc_1801A86FF
0x1801a8506  lea     rcx, [rax+2]
0x1801a850a  cmp     rcx, rbx
0x1801a850d  jz      loc_1801A86FF
0x1801a8513  sub     rbx, rcx
0x1801a8516  sar     rbx, 1
0x1801a8519  mov     rdx, qword ptr [rsp+178h+cchCount2]; cchCount1
0x1801a8521  cmp     rbx, rdx
0x1801a8524  jb      loc_1801A86FF
0x1801a852a  mov     rax, qword ptr [rsp+178h+var_120]
0x1801a852f  sub     rcx, rax
0x1801a8532  sar     rcx, 1
0x1801a8535  lea     r8, [rax+rcx*2]; lpString2
0x1801a8539  lea     rcx, [rsp+178h+lpString1]
0x1801a8541  cmp     [rsp+178h+var_A8], 7
0x1801a854a  cmova   rcx, [rsp+178h+lpString1]; lpString1
0x1801a8553  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x1801a855b  mov     r9d, edx; cchCount2
0x1801a855e  call    cs:__imp_CompareStringOrdinal
0x1801a8564  cmp     eax, 2
0x1801a8567  jnz     loc_1801A86FF
0x1801a856d  xor     r12d, r12d
0x1801a8570  mov     [rsp+178h+var_108], r12d
0x1801a8575  mov     [rsp+178h+var_140], r12d
0x1801a857a  mov     [rsp+178h+var_148], r12
0x1801a857f  mov     [rsp+178h+var_150], 30h ; '0'
0x1801a8587  lea     rax, [rsp+178h+var_60]
0x1801a858f  mov     qword ptr [rsp+178h+bIgnoreCase], rax; int
0x1801a8594  lea     r9, [rsp+178h+var_108]
0x1801a8599  lea     r8, DEVPKEY_Device_DriverVersion
0x1801a85a0  lea     rdx, [rsp+178h+var_A0]
0x1801a85a8  mov     rcx, r14
0x1801a85ab  mov     rax, r13
0x1801a85ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a85b3  mov     rcx, [rsp+178h]; this
0x1801a85bb  test    eax, eax
0x1801a85bd  jz      loc_1801A880B
0x1801a85c3  mov     rax, r12
0x1801a85c6  mov     [rsp+178h+var_D8], rax
0x1801a85ce  mov     rbx, r12
0x1801a85d1  mov     rsi, r12
0x1801a85d4  cmp     rsi, 4
0x1801a85d8  jnb     loc_1801A8684
0x1801a85de  mov     rcx, [rsp+178h]; this
0x1801a85e6  cmp     rbx, 18h
0x1801a85ea  jnb     loc_1801A881C
0x1801a85f0  mov     [rsp+178h+var_128], r12
0x1801a85f5  lea     rdx, [rsp+178h+var_60]
0x1801a85fd  lea     rdx, [rdx+rbx*2]
0x1801a8601  lea     rcx, [rsp+178h+String]
0x1801a8609  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801a860e  nop
0x1801a860f  lea     rdx, [rsp+178h+var_128]
0x1801a8614  lea     rcx, [rsp+178h+String]; String
0x1801a861c  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x1801a8621  mov     word ptr [rsp+rsi*2+178h+var_D8], ax
0x1801a8629  lea     rcx, [rsp+178h+String]
0x1801a8631  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a8636  mov     rcx, [rsp+178h]; this
0x1801a863e  cmp     rsi, 3
0x1801a8642  jz      short loc_1801A866B
0x1801a8644  add     rbx, [rsp+178h+var_128]
0x1801a8649  cmp     [rsp+rbx*2+178h+var_60], 2Eh ; '.'
0x1801a8652  jnz     loc_1801A8833
0x1801a8658  inc     rbx
0x1801a865b  inc     rsi
0x1801a865e  mov     rax, [rsp+178h+var_D8]
0x1801a8666  jmp     loc_1801A85D4
0x1801a866b  mov     rdx, [rsp+178h+var_128]
0x1801a8670  add     rdx, rbx
0x1801a8673  cmp     [rsp+rdx*2+178h+var_60], r12w
0x1801a867c  jnz     loc_1801A884A
0x1801a8682  jmp     short loc_1801A865B
0x1801a8684  movzx   ecx, word ptr [rsp+178h+var_D8+6]
0x1801a868c  mov     [rdi], cx
0x1801a868f  movzx   ecx, word ptr [rsp+178h+var_D8+4]
0x1801a8697  mov     [rdi+2], cx
0x1801a869b  movzx   ecx, word ptr [rsp+178h+var_D8+2]
0x1801a86a3  mov     [rdi+4], cx
0x1801a86a7  mov     [rdi+6], ax
0x1801a86ab  mov     rcx, qword ptr [rsp+178h+var_120]
0x1801a86b0  test    rcx, rcx
0x1801a86b3  jz      short loc_1801A86D6
0x1801a86b5  mov     rdx, [rsp+178h+var_110]
0x1801a86ba  sub     rdx, rcx
0x1801a86bd  sar     rdx, 1
0x1801a86c0  add     rdx, rdx
0x1801a86c3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a86c8  xorps   xmm0, xmm0
0x1801a86cb  movdqu  [rsp+178h+var_120], xmm0
0x1801a86d1  mov     [rsp+178h+var_110], r12
0x1801a86d6  mov     rcx, r14
0x1801a86d9  mov     rax, r15
0x1801a86dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a86e1  nop
0x1801a86e2  lea     rcx, [rsp+178h+lpString1]
0x1801a86ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a86ef  nop
0x1801a86f0  lea     rcx, [rsp+178h+var_100]
0x1801a86f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801a86fa  mov     rax, rdi
0x1801a86fd  jmp     short loc_1801A8777
0x1801a86ff  inc     esi
0x1801a8701  mov     rcx, qword ptr [rsp+178h+var_120]
0x1801a8706  xor     ebx, ebx
0x1801a8708  test    rcx, rcx
0x1801a870b  jz      loc_1801A8459
0x1801a8711  mov     rdx, [rsp+178h+var_110]
0x1801a8716  sub     rdx, rcx
0x1801a8719  sar     rdx, 1
0x1801a871c  add     rdx, rdx
0x1801a871f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801a8724  jmp     loc_1801A8459
0x1801a8729  call    cs:__imp_GetLastError
0x1801a872f  cmp     eax, 103h
0x1801a8734  jnz     loc_1801A8862
0x1801a873a  mov     rcx, r14
0x1801a873d  mov     rax, r15
0x1801a8740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8745  nop
0x1801a8746  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
0x1801a874b  mov     qword ptr [rdi], 0
0x1801a8752  lea     rcx, [rsp+178h+lpString1]
0x1801a875a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a875f  nop
0x1801a8760  lea     rcx, [rsp+178h+var_100]
0x1801a8765  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801a876a  mov     rax, rdi
0x1801a876d  jmp     short loc_1801A8777
0x1801a876f  mov     rax, [rsp+178h+var_F8]
0x1801a8777  mov     rcx, [rsp+178h+var_30]
0x1801a877f  xor     rcx, rsp; StackCookie
0x1801a8782  call    __security_check_cookie
0x1801a8787  lea     r11, [rsp+178h+var_28]
0x1801a878f  mov     rbx, [r11+40h]
0x1801a8793  mov     rsi, [r11+48h]
0x1801a8797  mov     rsp, r11
0x1801a879a  pop     r15
0x1801a879c  pop     r14
0x1801a879e  pop     r13
0x1801a87a0  pop     r12
0x1801a87a2  pop     rdi
0x1801a87a3  retn
0x1801a87a4  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a87ab  mov     edx, 89h; void *
0x1801a87b0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a87b5  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a87bc  mov     edx, 8Bh; void *
0x1801a87c1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a87c6  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a87cd  mov     edx, 8Dh; void *
0x1801a87d2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a87d7  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a87de  mov     edx, 8Fh; void *
0x1801a87e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a87e8  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a87ef  mov     edx, 91h; void *
0x1801a87f4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a87fa  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a8801  mov     edx, 0ABh; void *
0x1801a8806  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a880b  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a8812  mov     edx, 0C2h; void *
0x1801a8817  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a881c  mov     r9d, 80070057h; char *
0x1801a8822  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a8829  mov     edx, 0CBh; void *
0x1801a882e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a8833  mov     r9d, 80070057h; char *
0x1801a8839  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a8840  mov     edx, 0D3h; void *
0x1801a8845  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a884a  mov     r9d, 80070057h; char *
0x1801a8850  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801a8857  mov     edx, 0DBh; void *
0x1801a885c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a8862  mov     rcx, [rsp+178h]; this
  ... truncated ...
```
