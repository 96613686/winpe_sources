# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x180019898`
- end: `0x180019eef`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1623`
- prototype: `udk::CopilotPlusDetection::details *__fastcall(udk::CopilotPlusDetection::details *this, const struct DXCoreHardwareIDParts *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018008`
- `0x1800181f0`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x1800032a0`
- `0x18000d7f0`
- `0x18000e0b8`
- `0x18000e92c`
- `0x180011918`
- `0x180011cb8`
- `0x180012530`
- `0x18001295c`
- `0x180017ec4`
- `0x180019758`
- `0x180019898`
- `0x18001bf58`
- `0x18001c9c8`
- `0x18001c9e4`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019cbb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019cbb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180019cf4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180019cf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019916`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019972`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001999c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800199c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019916`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019972`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001999c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800199c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800198ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800198ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019bf6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019bf6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180019d1f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180019d1f`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180019d0b`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180019d0b`

## string_xrefs

- `0x1800198e6`: `setupapi.dll`

## pseudocode

```c
udk::CopilotPlusDetection::details *__fastcall udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(
        udk::CopilotPlusDetection::details *this,
        const struct DXCoreHardwareIDParts *a2)
{
  HMODULE Library; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  HMODULE v7; // rbx
  unsigned int v8; // r8d
  const char *v9; // r9
  FARPROC ProcAddress; // r14
  unsigned int v11; // r8d
  const char *v12; // r9
  FARPROC v13; // r15
  unsigned int v14; // r8d
  const char *v15; // r9
  FARPROC v16; // r13
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  __int64 v21; // rax
  __int64 v22; // r12
  unsigned int i; // r14d
  char *v24; // rsi
  unsigned __int64 v25; // rcx
  size_t v26; // rbx
  int v27; // eax
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned __int64 v30; // rsi
  char *trivial_2; // rbx
  char *v32; // rax
  char *v33; // rcx
  const WCHAR *v34; // r8
  const WCHAR *v35; // rcx
  unsigned int v36; // r8d
  const char *v37; // r9
  __int16 v38; // ax
  unsigned __int64 j; // rbx
  _DWORD *v40; // rax
  _DWORD *v41; // r13
  const wchar_t *v42; // r15
  __int16 v43; // ax
  wchar_t *v44; // r14
  unsigned __int64 v45; // rdx
  __int16 v46; // ax
  void *v48; // rdx
  unsigned int v49; // r8d
  const char *v50; // r9
  void *v51[2]; // [rsp+50h] [rbp-138h] BYREF
  __int64 v52; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v54; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v55[2]; // [rsp+78h] [rbp-110h] BYREF
  void (__fastcall *v56)(__int64); // [rsp+88h] [rbp-100h]
  __int64 v57; // [rsp+90h] [rbp-F8h]
  FARPROC v58; // [rsp+98h] [rbp-F0h]
  char v59; // [rsp+A0h] [rbp-E8h]
  FARPROC v60; // [rsp+A8h] [rbp-E0h]
  _DWORD v61[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v64; // [rsp+D8h] [rbp-B0h]
  _OWORD v65[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v67[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v55[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v7 = Library;
  v55[0] = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x86, v5, v6);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x89, v8, v9);
  v13 = GetProcAddress(v7, "SetupDiDestroyDeviceInfoList");
  v56 = (void (__fastcall *)(__int64))v13;
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8B, v11, v12);
  v16 = GetProcAddress(v7, "SetupDiEnumDeviceInfo");
  if ( !v16 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8D, v14, v15);
  EndPtr = (wchar_t *)GetProcAddress(v7, "SetupDiGetDeviceInstanceIdW");
  if ( !EndPtr )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8F, v17, v18);
  v60 = GetProcAddress(v7, "SetupDiGetDevicePropertyW");
  if ( !v60 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x91, v19, v20);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v61[0] = -266691245;
  v61[1] = 1221738486;
  v61[2] = -1480026209;
  v61[3] = 216091392;
  v21 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v61, 0, 0, 2);
  v22 = v21;
  if ( v21 == -1 )
    goto LABEL_58;
  v57 = v21;
  v58 = v13;
  v59 = 1;
  memset(v65, 0, sizeof(v65));
  LODWORD(v65[0]) = 32;
  for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v16)(v22, i, v65); ++i )
  {
    std::vector<_GUID const *>::vector<_GUID const *>(v51);
    v24 = (char *)v51[1];
    v25 = ((char *)v51[1] - (char *)v51[0]) >> 1;
    if ( v25 <= 0xC8 )
    {
      if ( v25 >= 0xC8 )
        goto LABEL_22;
      if ( (unsigned __int64)((signed __int64)(v52 - (unsigned __int64)v51[0]) >> 1) < 0xC8 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v51);
        v24 = (char *)v51[1];
        goto LABEL_22;
      }
      v26 = 2 * (200 - v25);
      memset_0(v51[1], 0, v26);
      v24 += v26;
    }
    else
    {
      v24 = (char *)v51[0] + 400;
    }
    v51[1] = v24;
LABEL_22:
    v27 = ((__int64 (__fastcall *)(__int64, _OWORD *, void *, _QWORD, _QWORD))EndPtr)(
            v22,
            v65,
            v51[0],
            (unsigned int)((v24 - (char *)v51[0]) >> 1),
            0);
    v30 = 0;
    if ( !v27 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAB, v28, v29);
    trivial_2 = (char *)_std_find_trivial_2(v51[0], v51[1], 0);
    v32 = (char *)_std_find_trivial_2(v51[0], trivial_2, 92);
    if ( v32 != v51[1] && trivial_2 != v51[1] )
    {
      v33 = v32 + 2;
      if ( v32 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v33) >> 1) >= *(_QWORD *)cchCount2 )
      {
        v34 = (const WCHAR *)((char *)v51[0] + 2 * ((v33 - (char *)v51[0]) >> 1));
        v35 = (const WCHAR *)lpString1;
        if ( v64 > 7 )
          v35 = lpString1[0];
        if ( CompareStringOrdinal(v35, cchCount2[0], v34, cchCount2[0], 1) == 2 )
        {
          v54 = 0;
          if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v60)(
                  v22,
                  v65,
                  &DEVPKEY_Device_DriverVersion,
                  &v54) )
            wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC2, v36, v37);
          v38 = 0;
          v60 = 0;
          for ( j = 0; j < 4; ++j )
          {
            if ( v30 >= 0x18 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                (const char *)0x80070057LL,
                (int)v67);
            std::wstring::wstring(String, &v67[v30]);
            v40 = (_DWORD *)_o__errno();
            v41 = v40;
            v42 = (const wchar_t *)String;
            if ( String[3] > (wchar_t *)7 )
              v42 = String[0];
            EndPtr = 0;
            *v40 = 0;
            v43 = wcstol(v42, &EndPtr, 10);
            v44 = EndPtr;
            if ( v42 == EndPtr )
              std::_Xinvalid_argument("invalid stoi argument");
            if ( *v41 == 34 )
              std::_Xout_of_range("stoi argument out of range");
            *((_WORD *)&v61[-2] + j) = v43;
            std::wstring::~wstring(String);
            v45 = v44 - v42 + v30;
            v46 = v67[v45];
            if ( j == 3 )
            {
              if ( v46 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v67);
            }
            else
            {
              if ( v46 != 46 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v67);
              v30 = v45 + 1;
            }
            v38 = (__int16)v60;
          }
          *(_WORD *)this = HIWORD(v60);
          *((_WORD *)this + 1) = WORD2(v60);
          *((_WORD *)this + 2) = WORD1(v60);
          *((_WORD *)this + 3) = v38;
          if ( v51[0] )
          {
            std::_Deallocate<16>(v51[0], 2 * ((signed __int64)(v52 - (unsigned __int64)v51[0]) >> 1));
            *(_OWORD *)v51 = 0;
            v52 = 0;
          }
          v56(v22);
          std::wstring::~wstring(lpString1);
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v55);
          return this;
        }
      }
    }
    if ( v51[0] )
      std::_Deallocate<16>(v51[0], 2 * ((signed __int64)(v52 - (unsigned __int64)v51[0]) >> 1));
  }
  if ( GetLastError() != 259 )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v48, v49, v50);
  ((void (__fastcall *)(__int64))v13)(v22);
LABEL_58:
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring(lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v55);
  return this;
}

```

## disassembly

```asm
0x180019898  mov     [rsp+arg_10], rbx
0x18001989d  mov     [rsp+arg_18], rsi
0x1800198a2  push    rdi
0x1800198a3  push    r12
0x1800198a5  push    r13
0x1800198a7  push    r14
0x1800198a9  push    r15
0x1800198ab  sub     rsp, 160h
0x1800198b2  mov     rax, cs:__security_cookie
0x1800198b9  xor     rax, rsp
0x1800198bc  mov     [rsp+188h+var_38], rax
0x1800198c4  mov     rsi, rdx
0x1800198c7  mov     rdi, rcx
0x1800198ca  mov     [rsp+188h+var_108], rcx
0x1800198d2  add     rdx, 4
0x1800198d6  mov     rcx, rsi
0x1800198d9  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x1800198de  xor     edx, edx; hFile
0x1800198e0  mov     r8d, 800h; dwFlags
0x1800198e6  lea     rcx, aSetupapiDll; "setupapi.dll"
0x1800198ed  call    cs:__imp_LoadLibraryExW
0x1800198f3  mov     rbx, rax
0x1800198f6  mov     [rsp+188h+var_110], rax
0x1800198fb  mov     rcx, [rsp+188h]; this
0x180019903  test    rax, rax
0x180019906  jz      loc_180019EAE
0x18001990c  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x180019913  mov     rcx, rax; hModule
0x180019916  call    cs:__imp_GetProcAddress
0x18001991c  mov     r14, rax
0x18001991f  mov     rcx, [rsp+188h]; this
0x180019927  test    rax, rax
0x18001992a  jnz     short loc_180019936
0x18001992c  mov     edx, 89h; void *
0x180019931  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019936  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x18001993d  mov     rcx, rbx; hModule
0x180019940  call    cs:__imp_GetProcAddress
0x180019946  mov     r15, rax
0x180019949  mov     [rsp+188h+var_100], rax
0x180019951  mov     rcx, [rsp+188h]; this
0x180019959  test    rax, rax
0x18001995c  jnz     short loc_180019968
0x18001995e  mov     edx, 8Bh; void *
0x180019963  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019968  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x18001996f  mov     rcx, rbx; hModule
0x180019972  call    cs:__imp_GetProcAddress
0x180019978  mov     r13, rax
0x18001997b  mov     rcx, [rsp+188h]; this
0x180019983  test    rax, rax
0x180019986  jnz     short loc_180019992
0x180019988  mov     edx, 8Dh; void *
0x18001998d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019992  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x180019999  mov     rcx, rbx; hModule
0x18001999c  call    cs:__imp_GetProcAddress
0x1800199a2  mov     [rsp+188h+EndPtr], rax
0x1800199a7  mov     rcx, [rsp+188h]; this
0x1800199af  test    rax, rax
0x1800199b2  jnz     short loc_1800199BE
0x1800199b4  mov     edx, 8Fh; void *
0x1800199b9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800199be  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x1800199c5  mov     rcx, rbx; hModule
0x1800199c8  call    cs:__imp_GetProcAddress
0x1800199ce  mov     [rsp+188h+var_E0], rax
0x1800199d6  mov     rcx, [rsp+188h]; this
0x1800199de  test    rax, rax
0x1800199e1  jnz     short loc_1800199ED
0x1800199e3  mov     edx, 91h; void *
0x1800199e8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800199ed  mov     rdx, rsi
0x1800199f0  lea     rcx, [rsp+188h+lpString1]
0x1800199f8  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x1800199fd  nop
0x1800199fe  mov     [rsp+188h+var_D8], 0F01A9D53h
0x180019a09  mov     [rsp+188h+var_D4], 48D23FF6h
0x180019a14  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x180019a1f  mov     ebx, 0C8h
0x180019a24  xor     esi, esi
0x180019a26  mov     [rsp+188h+var_CC], 0CE14B00h
0x180019a31  lea     r9d, [rsi+2]
0x180019a35  xor     r8d, r8d
0x180019a38  xor     edx, edx
0x180019a3a  lea     rcx, [rsp+188h+var_D8]
0x180019a42  mov     rax, r14
0x180019a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a4a  mov     r12, rax
0x180019a4d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019a51  jz      loc_180019E85
0x180019a57  mov     [rsp+188h+var_F8], rax
0x180019a5f  mov     [rsp+188h+var_F0], r15
0x180019a67  mov     [rsp+188h+var_E8], 1
0x180019a6f  xorps   xmm0, xmm0
0x180019a72  movups  [rsp+188h+var_A8], xmm0
0x180019a7a  movups  [rsp+188h+var_98], xmm0
0x180019a82  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x180019a8d  mov     r14d, esi
0x180019a90  lea     r8, [rsp+188h+var_A8]
0x180019a98  mov     edx, r14d
0x180019a9b  mov     rcx, r12
0x180019a9e  mov     rax, r13
0x180019aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aa6  test    eax, eax
0x180019aa8  jz      loc_180019E5E
0x180019aae  lea     rcx, [rsp+188h+var_138]
0x180019ab3  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x180019ab8  nop
0x180019ab9  mov     rdx, [rsp+188h+var_138]
0x180019abe  mov     rsi, [rsp+188h+var_138+8]
0x180019ac3  mov     rcx, rsi
0x180019ac6  sub     rcx, rdx
0x180019ac9  sar     rcx, 1
0x180019acc  cmp     rcx, rbx
0x180019acf  jbe     short loc_180019ADA
0x180019ad1  lea     rsi, [rdx+190h]
0x180019ad8  jmp     short loc_180019B17
0x180019ada  jnb     short loc_180019B1C
0x180019adc  mov     rax, [rsp+188h+var_128]
0x180019ae1  sub     rax, rdx
0x180019ae4  sar     rax, 1
0x180019ae7  cmp     rax, rbx
0x180019aea  jnb     short loc_180019AFD
0x180019aec  lea     rcx, [rsp+188h+var_138]
0x180019af1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180019af6  mov     rsi, [rsp+188h+var_138+8]
0x180019afb  jmp     short loc_180019B1C
0x180019afd  mov     rax, rbx
0x180019b00  sub     rax, rcx
0x180019b03  lea     rbx, [rax+rax]
0x180019b07  mov     r8, rbx; Size
0x180019b0a  xor     edx, edx; Val
0x180019b0c  mov     rcx, rsi; void *
0x180019b0f  call    memset_0
0x180019b14  add     rsi, rbx
0x180019b17  mov     [rsp+188h+var_138+8], rsi
0x180019b1c  mov     r8, [rsp+188h+var_138]
0x180019b21  sub     rsi, r8
0x180019b24  sar     rsi, 1
0x180019b27  mov     qword ptr [rsp+188h+bIgnoreCase], 0
0x180019b30  mov     r9d, esi
0x180019b33  lea     rdx, [rsp+188h+var_A8]
0x180019b3b  mov     rcx, r12
0x180019b3e  mov     rax, [rsp+188h+EndPtr]
0x180019b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b48  mov     rcx, [rsp+188h]; this
0x180019b50  xor     esi, esi
0x180019b52  test    eax, eax
0x180019b54  jnz     short loc_180019B60
0x180019b56  mov     edx, 0ABh; void *
0x180019b5b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019b60  xor     r8d, r8d
0x180019b63  mov     rdx, [rsp+188h+var_138+8]
0x180019b68  mov     rcx, [rsp+188h+var_138]
0x180019b6d  call    __std_find_trivial_2
0x180019b72  mov     rbx, rax
0x180019b75  mov     r8d, 5Ch ; '\'
0x180019b7b  mov     rdx, rax
0x180019b7e  mov     rcx, [rsp+188h+var_138]
0x180019b83  call    __std_find_trivial_2
0x180019b88  cmp     rax, [rsp+188h+var_138+8]
0x180019b8d  jz      loc_180019E30
0x180019b93  cmp     rbx, [rsp+188h+var_138+8]
0x180019b98  jz      loc_180019E30
0x180019b9e  lea     rcx, [rax+2]
0x180019ba2  cmp     rcx, rbx
0x180019ba5  jz      loc_180019E30
0x180019bab  sub     rbx, rcx
0x180019bae  sar     rbx, 1
0x180019bb1  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x180019bb9  cmp     rbx, rdx
0x180019bbc  jb      loc_180019E30
0x180019bc2  mov     rax, [rsp+188h+var_138]
0x180019bc7  sub     rcx, rax
0x180019bca  sar     rcx, 1
0x180019bcd  lea     r8, [rax+rcx*2]; lpString2
0x180019bd1  lea     rcx, [rsp+188h+lpString1]
0x180019bd9  cmp     [rsp+188h+var_B0], 7
0x180019be2  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x180019beb  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x180019bf3  mov     r9d, edx; cchCount2
0x180019bf6  call    cs:__imp_CompareStringOrdinal
0x180019bfc  cmp     eax, 2
0x180019bff  jnz     loc_180019E30
0x180019c05  mov     [rsp+188h+var_118], esi
0x180019c09  mov     [rsp+188h+var_150], esi
0x180019c0d  mov     [rsp+188h+var_158], rsi
0x180019c12  mov     [rsp+188h+var_160], 30h ; '0'
0x180019c1a  lea     rax, [rsp+188h+var_68]
0x180019c22  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x180019c27  lea     r9, [rsp+188h+var_118]
0x180019c2c  lea     r8, DEVPKEY_Device_DriverVersion
0x180019c33  lea     rdx, [rsp+188h+var_A8]
0x180019c3b  mov     rcx, r12
0x180019c3e  mov     rax, [rsp+188h+var_E0]
0x180019c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c4b  mov     rcx, [rsp+188h]; this
0x180019c53  test    eax, eax
0x180019c55  jnz     short loc_180019C61
0x180019c57  mov     edx, 0C2h; void *
0x180019c5c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180019c61  mov     rax, rsi
0x180019c64  mov     [rsp+188h+var_E0], rax
0x180019c6c  xor     r14d, r14d
0x180019c6f  mov     ebx, r14d
0x180019c72  cmp     rbx, 4
0x180019c76  jnb     loc_180019DAD
0x180019c7c  mov     rcx, [rsp+188h]; this
0x180019c84  cmp     rsi, 18h
0x180019c88  jb      short loc_180019CA1
0x180019c8a  mov     r9d, 80070057h; char *
0x180019c90  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180019c97  mov     edx, 0CBh; void *
0x180019c9c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019ca1  lea     rdx, [rsp+188h+var_68]
0x180019ca9  lea     rdx, [rdx+rsi*2]
0x180019cad  lea     rcx, [rsp+188h+String]
0x180019cb5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019cba  nop
0x180019cbb  call    cs:__imp__o__errno
0x180019cc1  mov     r13, rax
0x180019cc4  lea     r15, [rsp+188h+String]
0x180019ccc  cmp     [rsp+188h+var_70], 7
0x180019cd5  cmova   r15, [rsp+188h+String]
0x180019cde  mov     [rsp+188h+EndPtr], r14
0x180019ce3  mov     [rax], r14d
0x180019ce6  mov     r8d, 0Ah; Radix
0x180019cec  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x180019cf1  mov     rcx, r15; String
0x180019cf4  call    cs:__imp_wcstol
0x180019cfa  mov     r14, [rsp+188h+EndPtr]
0x180019cff  cmp     r15, r14
0x180019d02  jnz     short loc_180019D11
0x180019d04  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x180019d0b  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x180019d11  cmp     dword ptr [r13+0], 22h ; '"'
0x180019d16  jnz     short loc_180019D25
0x180019d18  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x180019d1f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180019d25  sub     r14, r15
0x180019d28  sar     r14, 1
0x180019d2b  mov     word ptr [rsp+rbx*2+188h+var_E0], ax
0x180019d33  lea     rcx, [rsp+188h+String]
0x180019d3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019d40  lea     rdx, [r14+rsi]
0x180019d44  movzx   eax, [rsp+rdx*2+188h+var_68]
0x180019d4c  mov     rcx, [rsp+188h]; this
0x180019d54  cmp     rbx, 3
0x180019d58  jz      short loc_180019D8E
0x180019d5a  cmp     ax, 2Eh ; '.'
0x180019d5e  jz      short loc_180019D77
0x180019d60  mov     r9d, 80070057h; char *
0x180019d66  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180019d6d  mov     edx, 0D3h; void *
0x180019d72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019d77  lea     rsi, [rdx+1]
0x180019d7b  xor     r14d, r14d
0x180019d7e  inc     rbx
0x180019d81  mov     rax, [rsp+188h+var_E0]
0x180019d89  jmp     loc_180019C72
0x180019d8e  xor     r14d, r14d
0x180019d91  test    ax, ax
0x180019d94  jz      short loc_180019D7E
0x180019d96  mov     r9d, 80070057h; char *
0x180019d9c  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x180019da3  mov     edx, 0DBh; void *
0x180019da8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180019dad  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x180019db5  mov     [rdi], cx
0x180019db8  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x180019dc0  mov     [rdi+2], cx
0x180019dc4  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x180019dcc  mov     [rdi+4], cx
0x180019dd0  mov     [rdi+6], ax
0x180019dd4  mov     rcx, [rsp+188h+var_138]
0x180019dd9  test    rcx, rcx
0x180019ddc  jz      short loc_180019DFF
0x180019dde  mov     rdx, [rsp+188h+var_128]
0x180019de3  sub     rdx, rcx
0x180019de6  sar     rdx, 1
0x180019de9  add     rdx, rdx
0x180019dec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019df1  xorps   xmm0, xmm0
0x180019df4  movdqu  xmmword ptr [rsp+188h+var_138], xmm0
0x180019dfa  mov     [rsp+188h+var_128], r14
0x180019dff  mov     rcx, r12
0x180019e02  mov     rax, [rsp+188h+var_100]
0x180019e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e0f  nop
0x180019e10  lea     rcx, [rsp+188h+lpString1]
0x180019e18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019e1d  nop
0x180019e1e  lea     rcx, [rsp+188h+var_110]
0x180019e23  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180019e28  mov     rax, rdi
0x180019e2b  jmp     loc_180019EC1
0x180019e30  inc     r14d
0x180019e33  mov     rcx, [rsp+188h+var_138]
0x180019e38  test    rcx, rcx
  ... truncated ...
```
