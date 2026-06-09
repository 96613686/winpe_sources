# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x1400230a0`
- end: `0x140023719`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1657`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001e44c`

## callees

- `0x140004f00`
- `0x140005240`
- `0x140008814`
- `0x14000a108`
- `0x14000b058`
- `0x14000cce4`
- `0x14000f290`
- `0x14001e358`
- `0x140021014`
- `0x1400230a0`
- `0x14003178c`
- `0x1400317a8`
- `0x14003376c`
- `0x140070010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14002348a`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14002348a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1400234a4`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1400234a4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140023471`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140023471`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140023433`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140023433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002312a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002314e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140023172`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140023196`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400231bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002312a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002314e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140023172`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140023196`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400231bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140023101`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140023101`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140023382`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140023382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400235b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400235b3`

## string_xrefs

- `0x1400230fa`: `setupapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  unsigned int v17; // esi
  wchar_t *v18; // r14
  const char *v19; // r9
  __int64 trivial_2; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  const WCHAR *v24; // rcx
  const char *v25; // r9
  __int16 v26; // ax
  unsigned __int64 v27; // rsi
  unsigned __int64 i; // rbx
  _DWORD *v29; // rax
  const wchar_t *v30; // r12
  __int16 v31; // cx
  wchar_t *v32; // r14
  unsigned __int64 v33; // rdx
  __int16 v34; // ax
  const char *v35; // r9
  udk::CopilotPlusDetection::details *result; // rax
  const char *v37; // r9
  __int128 v38; // [rsp+50h] [rbp-138h] BYREF
  __int64 v39; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v41; // [rsp+70h] [rbp-118h] BYREF
  HMODULE v42; // [rsp+78h] [rbp-110h] BYREF
  udk::CopilotPlusDetection::details *v43; // [rsp+80h] [rbp-108h]
  _DWORD *v44; // [rsp+88h] [rbp-100h]
  __int64 v45; // [rsp+90h] [rbp-F8h]
  __int64 v46; // [rsp+98h] [rbp-F0h]
  FARPROC v47; // [rsp+A0h] [rbp-E8h]
  char v48; // [rsp+A8h] [rbp-E0h]
  FARPROC v49; // [rsp+B0h] [rbp-D8h]
  _DWORD v50[4]; // [rsp+B8h] [rbp-D0h] BYREF
  LPCWCH lpString1[2]; // [rsp+C8h] [rbp-C0h] BYREF
  int cchCount2[2]; // [rsp+D8h] [rbp-B0h]
  unsigned __int64 v53; // [rsp+E0h] [rbp-A8h]
  _OWORD v54[2]; // [rsp+E8h] [rbp-A0h] BYREF
  wchar_t *String[4]; // [rsp+108h] [rbp-80h] BYREF
  _WORD v56[24]; // [rsp+128h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v45 = -2;
  v43 = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  try
  {
    v6 = Library;
    v42 = Library;
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
    v49 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
    if ( !v49 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v14);
    udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
    v50[0] = -266691245;
    v50[1] = 1221738486;
    v50[2] = -1480026209;
    v50[3] = 216091392;
    v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v50, 0, 0, 2);
    v16 = v15;
    if ( v15 != -1 )
    {
      v46 = v15;
      v47 = v10;
      v48 = 1;
      memset(v54, 0, sizeof(v54));
      LODWORD(v54[0]) = 32;
      v17 = 0;
      v18 = EndPtr;
      while ( ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v16, v17, v54) )
      {
        v38 = 0;
        v39 = 0;
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&v38);
        if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v18)(
                v16,
                v54,
                v38,
                (__int64)(*((_QWORD *)&v38 + 1) - v38) >> 1,
                0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
            v19);
        trivial_2 = _std_find_trivial_2(v38, *((_QWORD *)&v38 + 1), 0);
        v21 = _std_find_trivial_2(v38, trivial_2, 92);
        if ( v21 != *((_QWORD *)&v38 + 1) && trivial_2 != *((_QWORD *)&v38 + 1) )
        {
          v22 = v21 + 2;
          if ( v21 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v22) >> 1) >= *(_QWORD *)cchCount2 )
          {
            v23 = (const WCHAR *)(v38 + 2 * ((v22 - (__int64)v38) >> 1));
            v24 = (const WCHAR *)lpString1;
            if ( v53 > 7 )
              v24 = lpString1[0];
            if ( CompareStringOrdinal(v24, cchCount2[0], v23, cchCount2[0], 1) == 2 )
            {
              v41 = 0;
              if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v49)(
                      v16,
                      v54,
                      &DEVPKEY_Device_DriverVersion,
                      &v41) )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0xC2,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  v25);
              v26 = 0;
              v49 = 0;
              v27 = 0;
              for ( i = 0; i < 4; ++i )
              {
                if ( v27 >= 0x18 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xCB,
                    (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v56);
                std::wstring::wstring(String, &v56[v27]);
                v29 = (_DWORD *)_o__errno();
                v44 = v29;
                v30 = (const wchar_t *)String;
                if ( String[3] > (wchar_t *)7 )
                  v30 = String[0];
                EndPtr = 0;
                *v29 = 0;
                v31 = wcstol(v30, &EndPtr, 10);
                v32 = EndPtr;
                if ( v30 == EndPtr )
                  std::_Xinvalid_argument("invalid stoi argument");
                if ( *v44 == 34 )
                  std::_Xout_of_range("stoi argument out of range");
                *((_WORD *)&v50[-2] + i) = v31;
                std::wstring::_Tidy_deallocate(String);
                v33 = v32 - v30 + v27;
                v34 = v56[v33];
                if ( i == 3 )
                {
                  if ( v34 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xDB,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v56);
                }
                else
                {
                  if ( v34 != 46 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xD3,
                      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                      (const char *)0x80070057LL,
                      (int)v56);
                  v27 = v33 + 1;
                }
                v26 = (__int16)v49;
              }
              *(_WORD *)this = HIWORD(v49);
              *((_WORD *)this + 1) = WORD2(v49);
              *((_WORD *)this + 2) = WORD1(v49);
              *((_WORD *)this + 3) = v26;
              if ( (_QWORD)v38 )
              {
                std::_Deallocate<16>(v38, 2 * ((v39 - (__int64)v38) >> 1));
                v38 = 0;
                v39 = 0;
              }
              ((void (__fastcall *)(__int64))v10)(v16);
              std::wstring::_Tidy_deallocate(lpString1);
              wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
              return this;
            }
          }
        }
        ++v17;
        if ( (_QWORD)v38 )
          std::_Deallocate<16>(v38, 2 * ((v39 - (__int64)v38) >> 1));
      }
      if ( GetLastError() != 259 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
          v37);
      ((void (__fastcall *)(__int64))v10)(v16);
    }
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)this = 0;
    std::wstring::_Tidy_deallocate(lpString1);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
    result = this;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v35);
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
    *(_QWORD *)v43 = 0;
    return v43;
  }
  return result;
}

```

## disassembly

```asm
0x1400230a0  mov     rax, rsp
0x1400230a3  push    rdi
0x1400230a4  push    r12
0x1400230a6  push    r13
0x1400230a8  push    r14
0x1400230aa  push    r15
0x1400230ac  sub     rsp, 160h
0x1400230b3  mov     qword ptr [rax-0F8h], 0FFFFFFFFFFFFFFFEh
0x1400230be  mov     [rax+18h], rbx
0x1400230c2  mov     [rax+20h], rsi
0x1400230c6  mov     rax, cs:__security_cookie
0x1400230cd  xor     rax, rsp
0x1400230d0  mov     [rsp+188h+var_30], rax
0x1400230d8  mov     rsi, rdx
0x1400230db  mov     rdi, rcx
0x1400230de  mov     [rsp+188h+var_108], rcx
0x1400230e6  add     rdx, 4
0x1400230ea  mov     rcx, rsi
0x1400230ed  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x1400230f2  xor     edx, edx; hFile
0x1400230f4  mov     r8d, 800h; dwFlags
0x1400230fa  lea     rcx, aSetupapiDll; "setupapi.dll"
0x140023101  call    cs:__imp_LoadLibraryExW
0x140023107  mov     rbx, rax
0x14002310a  mov     [rsp+188h+var_110], rax
0x14002310f  mov     rcx, [rsp+188h]; this
0x140023117  test    rax, rax
0x14002311a  jz      loc_140023706
0x140023120  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x140023127  mov     rcx, rax; hModule
0x14002312a  call    cs:__imp_GetProcAddress
0x140023130  mov     r14, rax
0x140023133  mov     rcx, [rsp+188h]; this
0x14002313b  test    rax, rax
0x14002313e  jz      loc_14002362E
0x140023144  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x14002314b  mov     rcx, rbx; hModule
0x14002314e  call    cs:__imp_GetProcAddress
0x140023154  mov     r13, rax
0x140023157  mov     rcx, [rsp+188h]; this
0x14002315f  test    rax, rax
0x140023162  jz      loc_14002363F
0x140023168  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x14002316f  mov     rcx, rbx; hModule
0x140023172  call    cs:__imp_GetProcAddress
0x140023178  mov     r12, rax
0x14002317b  mov     rcx, [rsp+188h]; this
0x140023183  test    rax, rax
0x140023186  jz      loc_140023650
0x14002318c  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x140023193  mov     rcx, rbx; hModule
0x140023196  call    cs:__imp_GetProcAddress
0x14002319c  mov     [rsp+188h+EndPtr], rax
0x1400231a1  mov     rcx, [rsp+188h]; this
0x1400231a9  test    rax, rax
0x1400231ac  jz      loc_140023661
0x1400231b2  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x1400231b9  mov     rcx, rbx; hModule
0x1400231bc  call    cs:__imp_GetProcAddress
0x1400231c2  mov     [rsp+188h+var_D8], rax
0x1400231ca  mov     rcx, [rsp+188h]; this
0x1400231d2  xor     ebx, ebx
0x1400231d4  test    rax, rax
0x1400231d7  jz      loc_140023672
0x1400231dd  mov     rdx, rsi
0x1400231e0  lea     rcx, [rsp+188h+lpString1]
0x1400231e8  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x1400231ed  nop
0x1400231ee  mov     [rsp+188h+var_D0], 0F01A9D53h
0x1400231f9  mov     [rsp+188h+var_CC], 48D23FF6h
0x140023204  mov     [rsp+188h+var_C8], 0A7C8979Fh
0x14002320f  mov     [rsp+188h+var_C4], 0CE14B00h
0x14002321a  mov     r9d, 2
0x140023220  xor     r8d, r8d
0x140023223  xor     edx, edx
0x140023225  lea     rcx, [rsp+188h+var_D0]
0x14002322d  mov     rax, r14
0x140023230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023235  mov     r15, rax
0x140023238  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002323c  jz      loc_1400235D0
0x140023242  mov     [rsp+188h+var_F0], rax
0x14002324a  mov     [rsp+188h+var_E8], r13
0x140023252  mov     [rsp+188h+var_E0], 1
0x14002325a  xorps   xmm0, xmm0
0x14002325d  movups  [rsp+188h+var_A0], xmm0
0x140023265  movups  [rsp+188h+var_90], xmm0
0x14002326d  mov     dword ptr [rsp+188h+var_A0], 20h ; ' '
0x140023278  mov     esi, ebx
0x14002327a  mov     r14, [rsp+188h+EndPtr]
0x14002327f  lea     r8, [rsp+188h+var_A0]
0x140023287  mov     edx, esi
0x140023289  mov     rcx, r15
0x14002328c  mov     rax, r12
0x14002328f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023294  test    eax, eax
0x140023296  jz      loc_1400235B3
0x14002329c  xorps   xmm0, xmm0
0x14002329f  movdqu  [rsp+188h+var_138], xmm0
0x1400232a5  mov     [rsp+188h+var_128], rbx
0x1400232aa  lea     rcx, [rsp+188h+var_138]
0x1400232af  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400232b4  mov     r8, qword ptr [rsp+188h+var_138]
0x1400232b9  mov     r9, qword ptr [rsp+188h+var_138+8]
0x1400232be  sub     r9, r8
0x1400232c1  sar     r9, 1
0x1400232c4  mov     qword ptr [rsp+188h+bIgnoreCase], rbx
0x1400232c9  lea     rdx, [rsp+188h+var_A0]
0x1400232d1  mov     rcx, r15
0x1400232d4  mov     rax, r14
0x1400232d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400232dc  mov     rcx, [rsp+188h]; this
0x1400232e4  test    eax, eax
0x1400232e6  jz      loc_140023684
0x1400232ec  xor     r8d, r8d
0x1400232ef  mov     rdx, qword ptr [rsp+188h+var_138+8]
0x1400232f4  mov     rcx, qword ptr [rsp+188h+var_138]
0x1400232f9  call    __std_find_trivial_2
0x1400232fe  mov     rbx, rax
0x140023301  mov     r8d, 5Ch ; '\'
0x140023307  mov     rdx, rax
0x14002330a  mov     rcx, qword ptr [rsp+188h+var_138]
0x14002330f  call    __std_find_trivial_2
0x140023314  cmp     rax, qword ptr [rsp+188h+var_138+8]
0x140023319  jz      loc_140023589
0x14002331f  cmp     rbx, qword ptr [rsp+188h+var_138+8]
0x140023324  jz      loc_140023589
0x14002332a  lea     rcx, [rax+2]
0x14002332e  cmp     rcx, rbx
0x140023331  jz      loc_140023589
0x140023337  sub     rbx, rcx
0x14002333a  sar     rbx, 1
0x14002333d  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x140023345  cmp     rbx, rdx
0x140023348  jb      loc_140023589
0x14002334e  mov     rax, qword ptr [rsp+188h+var_138]
0x140023353  sub     rcx, rax
0x140023356  sar     rcx, 1
0x140023359  lea     r8, [rax+rcx*2]; lpString2
0x14002335d  lea     rcx, [rsp+188h+lpString1]
0x140023365  cmp     [rsp+188h+var_A8], 7
0x14002336e  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x140023377  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x14002337f  mov     r9d, edx; cchCount2
0x140023382  call    cs:__imp_CompareStringOrdinal
0x140023388  cmp     eax, 2
0x14002338b  jnz     loc_140023589
0x140023391  xor     r14d, r14d
0x140023394  mov     [rsp+188h+var_118], r14d
0x140023399  mov     [rsp+188h+var_150], r14d
0x14002339e  mov     [rsp+188h+var_158], r14
0x1400233a3  mov     [rsp+188h+var_160], 30h ; '0'
0x1400233ab  lea     rax, [rsp+188h+var_60]
0x1400233b3  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x1400233b8  lea     r9, [rsp+188h+var_118]
0x1400233bd  lea     r8, DEVPKEY_Device_DriverVersion
0x1400233c4  lea     rdx, [rsp+188h+var_A0]
0x1400233cc  mov     rcx, r15
0x1400233cf  mov     rax, [rsp+188h+var_D8]
0x1400233d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400233dc  mov     rcx, [rsp+188h]; this
0x1400233e4  test    eax, eax
0x1400233e6  jz      loc_140023695
0x1400233ec  mov     rax, r14
0x1400233ef  mov     [rsp+188h+var_D8], rax
0x1400233f7  mov     rsi, r14
0x1400233fa  mov     rbx, r14
0x1400233fd  cmp     rbx, 4
0x140023401  jnb     loc_14002350E
0x140023407  mov     rcx, [rsp+188h]; this
0x14002340f  cmp     rsi, 18h
0x140023413  jnb     loc_1400236A6
0x140023419  lea     rdx, [rsp+188h+var_60]
0x140023421  lea     rdx, [rdx+rsi*2]
0x140023425  lea     rcx, [rsp+188h+String]
0x14002342d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140023432  nop
0x140023433  call    cs:__imp__o__errno
0x140023439  mov     [rsp+188h+var_100], rax
0x140023441  lea     r12, [rsp+188h+String]
0x140023449  cmp     [rsp+188h+var_68], 7
0x140023452  cmova   r12, [rsp+188h+String]
0x14002345b  mov     [rsp+188h+EndPtr], r14
0x140023460  mov     [rax], r14d
0x140023463  mov     r8d, 0Ah; Radix
0x140023469  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x14002346e  mov     rcx, r12; String
0x140023471  call    cs:__imp_wcstol
0x140023477  mov     ecx, eax
0x140023479  mov     r14, [rsp+188h+EndPtr]
0x14002347e  cmp     r12, r14
0x140023481  jnz     short loc_140023490
0x140023483  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x14002348a  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x140023490  mov     rax, [rsp+188h+var_100]
0x140023498  cmp     dword ptr [rax], 22h ; '"'
0x14002349b  jnz     short loc_1400234AA
0x14002349d  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x1400234a4  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1400234aa  sub     r14, r12
0x1400234ad  sar     r14, 1
0x1400234b0  mov     word ptr [rsp+rbx*2+188h+var_D8], cx
0x1400234b8  lea     rcx, [rsp+188h+String]
0x1400234c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400234c5  lea     rdx, [r14+rsi]
0x1400234c9  movzx   eax, [rsp+rdx*2+188h+var_60]
0x1400234d1  mov     rcx, [rsp+188h]; this
0x1400234d9  cmp     rbx, 3
0x1400234dd  jz      short loc_140023500
0x1400234df  cmp     ax, 2Eh ; '.'
0x1400234e3  jnz     loc_1400236BD
0x1400234e9  lea     rsi, [rdx+1]
0x1400234ed  xor     r14d, r14d
0x1400234f0  inc     rbx
0x1400234f3  mov     rax, [rsp+188h+var_D8]
0x1400234fb  jmp     loc_1400233FD
0x140023500  xor     r14d, r14d
0x140023503  test    ax, ax
0x140023506  jnz     loc_1400236D4
0x14002350c  jmp     short loc_1400234F0
0x14002350e  movzx   ecx, word ptr [rsp+188h+var_D8+6]
0x140023516  mov     [rdi], cx
0x140023519  movzx   ecx, word ptr [rsp+188h+var_D8+4]
0x140023521  mov     [rdi+2], cx
0x140023525  movzx   ecx, word ptr [rsp+188h+var_D8+2]
0x14002352d  mov     [rdi+4], cx
0x140023531  mov     [rdi+6], ax
0x140023535  mov     rcx, qword ptr [rsp+188h+var_138]
0x14002353a  test    rcx, rcx
0x14002353d  jz      short loc_140023560
0x14002353f  mov     rdx, [rsp+188h+var_128]
0x140023544  sub     rdx, rcx
0x140023547  sar     rdx, 1
0x14002354a  add     rdx, rdx
0x14002354d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140023552  xorps   xmm0, xmm0
0x140023555  movdqu  [rsp+188h+var_138], xmm0
0x14002355b  mov     [rsp+188h+var_128], r14
0x140023560  mov     rcx, r15
0x140023563  mov     rax, r13
0x140023566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002356b  nop
0x14002356c  lea     rcx, [rsp+188h+lpString1]
0x140023574  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023579  nop
0x14002357a  lea     rcx, [rsp+188h+var_110]
0x14002357f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140023584  mov     rax, rdi
0x140023587  jmp     short loc_140023601
0x140023589  inc     esi
0x14002358b  mov     rcx, qword ptr [rsp+188h+var_138]
0x140023590  xor     ebx, ebx
0x140023592  test    rcx, rcx
0x140023595  jz      loc_14002327F
0x14002359b  mov     rdx, [rsp+188h+var_128]
0x1400235a0  sub     rdx, rcx
0x1400235a3  sar     rdx, 1
0x1400235a6  add     rdx, rdx
0x1400235a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400235ae  jmp     loc_14002327F
0x1400235b3  call    cs:__imp_GetLastError
0x1400235b9  cmp     eax, 103h
0x1400235be  jnz     loc_1400236EC
0x1400235c4  mov     rcx, r15
0x1400235c7  mov     rax, r13
0x1400235ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400235cf  nop
0x1400235d0  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
0x1400235d5  mov     qword ptr [rdi], 0
0x1400235dc  lea     rcx, [rsp+188h+lpString1]
0x1400235e4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400235e9  nop
0x1400235ea  lea     rcx, [rsp+188h+var_110]
0x1400235ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1400235f4  mov     rax, rdi
0x1400235f7  jmp     short loc_140023601
0x1400235f9  mov     rax, [rsp+188h+var_108]
0x140023601  mov     rcx, [rsp+188h+var_30]
0x140023609  xor     rcx, rsp; StackCookie
0x14002360c  call    __security_check_cookie
0x140023611  lea     r11, [rsp+188h+var_28]
0x140023619  mov     rbx, [r11+40h]
0x14002361d  mov     rsi, [r11+48h]
0x140023621  mov     rsp, r11
0x140023624  pop     r15
0x140023626  pop     r14
0x140023628  pop     r13
0x14002362a  pop     r12
0x14002362c  pop     rdi
0x14002362d  retn
0x14002362e  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140023635  mov     edx, 89h; void *
0x14002363a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14002363f  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140023646  mov     edx, 8Bh; void *
0x14002364b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140023650  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x140023657  mov     edx, 8Dh; void *
0x14002365c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140023661  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
  ... truncated ...
```
