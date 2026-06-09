# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x180057618`
- end: `0x180057ca9`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1681`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800548b0`

## callees

- `0x18002a2e0`
- `0x18002a718`
- `0x18002a774`
- `0x180034070`
- `0x180034d28`
- `0x18005086c`
- `0x1800513d0`
- `0x1800515ac`
- `0x180051754`
- `0x1800519e4`
- `0x1800547b4`
- `0x180055bc0`
- `0x180057618`
- `0x180058570`
- `0x180058b50`
- `0x180058b6c`
- `0x180059088`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005766a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005766a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057699`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800576c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800576f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057729`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005775e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057699`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800576c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800576f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057729`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005775e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800579eb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800579eb`

## string_xrefs

- `0x180057663`: `setupapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
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
  __int64 v22; // r14
  unsigned int i; // r12d
  char *v24; // rsi
  unsigned __int64 v25; // rcx
  size_t v26; // rbx
  int v27; // eax
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned __int64 v30; // rsi
  char *v31; // rbx
  char *v32; // rax
  const WCHAR *v33; // rcx
  unsigned int v34; // r8d
  const char *v35; // r9
  __int16 v36; // ax
  unsigned __int64 v37; // rbx
  char *v38; // rbx
  void *v40; // rdx
  unsigned int v41; // r8d
  const char *v42; // r9
  char *v43; // [rsp+50h] [rbp-138h] BYREF
  _QWORD v44[2]; // [rsp+58h] [rbp-130h] BYREF
  char *v45; // [rsp+68h] [rbp-120h] BYREF
  FARPROC v46; // [rsp+70h] [rbp-118h]
  __int64 v47; // [rsp+78h] [rbp-110h]
  FARPROC v48; // [rsp+80h] [rbp-108h]
  char v49; // [rsp+88h] [rbp-100h]
  wchar_t String[16]; // [rsp+90h] [rbp-F8h] BYREF
  int v51; // [rsp+B0h] [rbp-D8h] BYREF
  FARPROC v52; // [rsp+B8h] [rbp-D0h]
  void *v53[2]; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-B8h]
  _DWORD v55[4]; // [rsp+D8h] [rbp-B0h] BYREF
  LPCWCH lpString1[2]; // [rsp+E8h] [rbp-A0h] BYREF
  int cchCount2[2]; // [rsp+F8h] [rbp-90h]
  unsigned __int64 v58; // [rsp+100h] [rbp-88h]
  _OWORD v59[2]; // [rsp+108h] [rbp-80h] BYREF
  _WORD v60[24]; // [rsp+128h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v44[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v7 = Library;
  v44[0] = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x86, v5, v6);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x89, v8, v9);
  v13 = GetProcAddress(v7, "SetupDiDestroyDeviceInfoList");
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8B, v11, v12);
  v16 = GetProcAddress(v7, "SetupDiEnumDeviceInfo");
  if ( !v16 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8D, v14, v15);
  v52 = GetProcAddress(v7, "SetupDiGetDeviceInstanceIdW");
  if ( !v52 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8F, v17, v18);
  v46 = GetProcAddress(v7, "SetupDiGetDevicePropertyW");
  if ( !v46 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x91, v19, v20);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v55[0] = -266691245;
  v55[1] = 1221738486;
  v55[2] = -1480026209;
  v55[3] = 216091392;
  v21 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v55, 0, 0, 2);
  v22 = v21;
  if ( v21 == -1 )
    goto LABEL_52;
  v47 = v21;
  v48 = v13;
  v49 = 1;
  memset(v59, 0, sizeof(v59));
  LODWORD(v59[0]) = 32;
  for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v16)(v22, i, v59); ++i )
  {
    std::vector<_GUID const *>::vector<_GUID const *>(v53);
    v24 = (char *)v53[1];
    v25 = ((char *)v53[1] - (char *)v53[0]) >> 1;
    if ( v25 <= 0xC8 )
    {
      if ( v25 >= 0xC8 )
        goto LABEL_22;
      if ( (unsigned __int64)((signed __int64)(v54 - (unsigned __int64)v53[0]) >> 1) < 0xC8 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v53);
        v24 = (char *)v53[1];
        goto LABEL_22;
      }
      v26 = 2 * (200 - v25);
      memset_0(v53[1], 0, v26);
      v24 += v26;
    }
    else
    {
      v24 = (char *)v53[0] + 400;
    }
    v53[1] = v24;
LABEL_22:
    v27 = ((__int64 (__fastcall *)(__int64, _OWORD *, void *, _QWORD, _QWORD))v52)(
            v22,
            v59,
            v53[0],
            (unsigned int)((v24 - (char *)v53[0]) >> 1),
            0);
    v30 = 0;
    if ( !v27 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAB, v28, v29);
    LOWORD(v51) = 0;
    std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>,unsigned short>(
      &v45,
      v53[0],
      v53[1],
      &v51);
    LOWORD(v51) = 92;
    v31 = v45;
    std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>,unsigned short>(
      &v43,
      v53[0],
      v45,
      &v51);
    if ( v43 != v53[1] && v31 != v53[1] )
    {
      v32 = v43 + 2;
      v43 = v32;
      if ( v32 != v31 && (unsigned __int64)((v31 - v32) >> 1) >= *(_QWORD *)cchCount2 )
      {
        v33 = (const WCHAR *)lpString1;
        if ( v58 > 7 )
          v33 = lpString1[0];
        if ( CompareStringOrdinal(v33, cchCount2[0], (LPCWCH)v53[0] + ((v32 - (char *)v53[0]) >> 1), cchCount2[0], 1) == 2 )
        {
          v51 = 0;
          if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v46)(
                  v22,
                  v59,
                  &DEVPKEY_Device_DriverVersion,
                  &v51) )
            wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC2, v34, v35);
          v36 = 0;
          v52 = 0;
          v37 = 0;
          while ( v30 < 4 )
          {
            if ( v37 >= 0x18 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                (const char *)0x80070057LL,
                (int)v60);
            v43 = 0;
            std::wstring::wstring(String, &v60[v37]);
            *((_WORD *)&v53[-1] + v30) = std::stoi(String);
            std::wstring::~wstring((__int64)String);
            if ( v30 == 3 )
            {
              if ( v60[(_QWORD)&v43[v37]] )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v60);
            }
            else
            {
              v38 = &v43[v37];
              if ( v60[(_QWORD)v38] != 46 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v60);
              v37 = (unsigned __int64)(v38 + 1);
            }
            ++v30;
            v36 = (__int16)v52;
          }
          *(_WORD *)this = HIWORD(v52);
          *((_WORD *)this + 1) = WORD2(v52);
          *((_WORD *)this + 2) = WORD1(v52);
          *((_WORD *)this + 3) = v36;
          if ( v53[0] )
          {
            std::_Deallocate<16>(
              v53[0],
              (struct std::nothrow_t *)(2 * ((signed __int64)(v54 - (unsigned __int64)v53[0]) >> 1)));
            *(_OWORD *)v53 = 0;
            v54 = 0;
          }
          ((void (__fastcall *)(__int64))v13)(v22);
          std::wstring::~wstring((__int64)lpString1);
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v44);
          return this;
        }
      }
    }
    if ( v53[0] )
      std::_Deallocate<16>(
        v53[0],
        (struct std::nothrow_t *)(2 * ((signed __int64)(v54 - (unsigned __int64)v53[0]) >> 1)));
  }
  if ( GetLastError() != 259 )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v40, v41, v42);
  ((void (__fastcall *)(__int64))v13)(v22);
LABEL_52:
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring((__int64)lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v44);
  return this;
}

```

## disassembly

```asm
0x180057618  mov     [rsp+arg_10], rbx
0x18005761d  mov     [rsp+arg_18], rsi
0x180057622  push    rdi
0x180057623  push    r12
0x180057625  push    r13
0x180057627  push    r14
0x180057629  push    r15
0x18005762b  sub     rsp, 160h
0x180057632  mov     rax, cs:__security_cookie
0x180057639  xor     rax, rsp
0x18005763c  mov     [rsp+188h+var_30], rax
0x180057644  mov     rsi, rdx
0x180057647  mov     rdi, rcx
0x18005764a  mov     [rsp+188h+var_128], rcx
0x18005764f  add     rdx, 4
0x180057653  mov     rcx, rsi
0x180057656  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x18005765b  xor     edx, edx; hFile
0x18005765d  mov     r8d, 800h; dwFlags
0x180057663  lea     rcx, aSetupapiDll; "setupapi.dll"
0x18005766a  call    cs:__imp_LoadLibraryExW
0x180057671  nop     dword ptr [rax+rax+00h]
0x180057676  mov     rbx, rax
0x180057679  mov     [rsp+188h+var_130], rax
0x18005767e  mov     rcx, [rsp+188h]; this
0x180057686  test    rax, rax
0x180057689  jz      loc_180057C6B
0x18005768f  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x180057696  mov     rcx, rax; hModule
0x180057699  call    cs:__imp_GetProcAddress
0x1800576a0  nop     dword ptr [rax+rax+00h]
0x1800576a5  mov     r14, rax
0x1800576a8  mov     rcx, [rsp+188h]; this
0x1800576b0  test    rax, rax
0x1800576b3  jnz     short loc_1800576BF
0x1800576b5  mov     edx, 89h; void *
0x1800576ba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800576bf  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x1800576c6  mov     rcx, rbx; hModule
0x1800576c9  call    cs:__imp_GetProcAddress
0x1800576d0  nop     dword ptr [rax+rax+00h]
0x1800576d5  mov     r15, rax
0x1800576d8  mov     rcx, [rsp+188h]; this
0x1800576e0  test    rax, rax
0x1800576e3  jnz     short loc_1800576EF
0x1800576e5  mov     edx, 8Bh; void *
0x1800576ea  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800576ef  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x1800576f6  mov     rcx, rbx; hModule
0x1800576f9  call    cs:__imp_GetProcAddress
0x180057700  nop     dword ptr [rax+rax+00h]
0x180057705  mov     r13, rax
0x180057708  mov     rcx, [rsp+188h]; this
0x180057710  test    rax, rax
0x180057713  jnz     short loc_18005771F
0x180057715  mov     edx, 8Dh; void *
0x18005771a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005771f  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x180057726  mov     rcx, rbx; hModule
0x180057729  call    cs:__imp_GetProcAddress
0x180057730  nop     dword ptr [rax+rax+00h]
0x180057735  mov     [rsp+188h+var_D0], rax
0x18005773d  mov     rcx, [rsp+188h]; this
0x180057745  test    rax, rax
0x180057748  jnz     short loc_180057754
0x18005774a  mov     edx, 8Fh; void *
0x18005774f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180057754  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x18005775b  mov     rcx, rbx; hModule
0x18005775e  call    cs:__imp_GetProcAddress
0x180057765  nop     dword ptr [rax+rax+00h]
0x18005776a  mov     [rsp+188h+var_118], rax
0x18005776f  mov     rcx, [rsp+188h]; this
0x180057777  test    rax, rax
0x18005777a  jnz     short loc_180057786
0x18005777c  mov     edx, 91h; void *
0x180057781  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180057786  mov     rdx, rsi
0x180057789  lea     rcx, [rsp+188h+lpString1]
0x180057791  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x180057796  nop
0x180057797  mov     [rsp+188h+var_B0], 0F01A9D53h
0x1800577a2  mov     [rsp+188h+var_AC], 48D23FF6h
0x1800577ad  mov     [rsp+188h+var_A8], 0A7C8979Fh
0x1800577b8  mov     ebx, 0C8h
0x1800577bd  xor     esi, esi
0x1800577bf  mov     [rsp+188h+var_A4], 0CE14B00h
0x1800577ca  lea     r9d, [rsi+2]
0x1800577ce  xor     r8d, r8d
0x1800577d1  xor     edx, edx
0x1800577d3  lea     rcx, [rsp+188h+var_B0]
0x1800577db  mov     rax, r14
0x1800577de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800577e3  mov     r14, rax
0x1800577e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800577ea  jz      loc_180057C42
0x1800577f0  mov     [rsp+188h+var_110], rax
0x1800577f5  mov     [rsp+188h+var_108], r15
0x1800577fd  mov     [rsp+188h+var_100], 1
0x180057805  xorps   xmm0, xmm0
0x180057808  movups  [rsp+188h+var_80], xmm0
0x180057810  movups  [rsp+188h+var_70], xmm0
0x180057818  mov     dword ptr [rsp+188h+var_80], 20h ; ' '
0x180057823  mov     r12d, esi
0x180057826  lea     r8, [rsp+188h+var_80]
0x18005782e  mov     edx, r12d
0x180057831  mov     rcx, r14
0x180057834  mov     rax, r13
0x180057837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005783c  test    eax, eax
0x18005783e  jz      loc_180057C15
0x180057844  lea     rcx, [rsp+188h+var_C8]
0x18005784c  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x180057851  nop
0x180057852  mov     rdx, [rsp+188h+var_C8]
0x18005785a  mov     rsi, [rsp+188h+var_C8+8]
0x180057862  mov     rcx, rsi
0x180057865  sub     rcx, rdx
0x180057868  sar     rcx, 1
0x18005786b  cmp     rcx, rbx
0x18005786e  jbe     short loc_180057879
0x180057870  lea     rsi, [rdx+190h]
0x180057877  jmp     short loc_1800578BF
0x180057879  jnb     short loc_1800578C7
0x18005787b  mov     rax, [rsp+188h+var_B8]
0x180057883  sub     rax, rdx
0x180057886  sar     rax, 1
0x180057889  cmp     rax, rbx
0x18005788c  jnb     short loc_1800578A5
0x18005788e  lea     rcx, [rsp+188h+var_C8]
0x180057896  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005789b  mov     rsi, [rsp+188h+var_C8+8]
0x1800578a3  jmp     short loc_1800578C7
0x1800578a5  mov     rax, rbx
0x1800578a8  sub     rax, rcx
0x1800578ab  lea     rbx, [rax+rax]
0x1800578af  mov     r8, rbx; Size
0x1800578b2  xor     edx, edx; Val
0x1800578b4  mov     rcx, rsi; void *
0x1800578b7  call    memset_0
0x1800578bc  add     rsi, rbx
0x1800578bf  mov     [rsp+188h+var_C8+8], rsi
0x1800578c7  mov     r8, [rsp+188h+var_C8]
0x1800578cf  sub     rsi, r8
0x1800578d2  sar     rsi, 1
0x1800578d5  mov     qword ptr [rsp+188h+bIgnoreCase], 0
0x1800578de  mov     r9d, esi
0x1800578e1  lea     rdx, [rsp+188h+var_80]
0x1800578e9  mov     rcx, r14
0x1800578ec  mov     rax, [rsp+188h+var_D0]
0x1800578f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578f9  mov     rcx, [rsp+188h]; this
0x180057901  xor     esi, esi
0x180057903  test    eax, eax
0x180057905  jnz     short loc_180057911
0x180057907  mov     edx, 0ABh; void *
0x18005790c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180057911  mov     word ptr [rsp+188h+var_D8], si
0x180057919  lea     r9, [rsp+188h+var_D8]
0x180057921  mov     r8, [rsp+188h+var_C8+8]
0x180057929  mov     rdx, [rsp+188h+var_C8]
0x180057931  lea     rcx, [rsp+188h+var_120]
0x180057936  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@G@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@V10@V10@AEBG@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const &)
0x18005793b  mov     eax, 5Ch ; '\'
0x180057940  mov     word ptr [rsp+188h+var_D8], ax
0x180057948  mov     rbx, [rsp+188h+var_120]
0x18005794d  lea     r9, [rsp+188h+var_D8]
0x180057955  mov     r8, rbx
0x180057958  mov     rdx, [rsp+188h+var_C8]
0x180057960  lea     rcx, [rsp+188h+var_138]
0x180057965  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@G@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@0@V10@V10@AEBG@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const &)
0x18005796a  mov     rax, [rsp+188h+var_138]
0x18005796f  cmp     rax, [rsp+188h+var_C8+8]
0x180057977  jz      loc_180057BE1
0x18005797d  cmp     rbx, [rsp+188h+var_C8+8]
0x180057985  jz      loc_180057BE1
0x18005798b  add     rax, 2
0x18005798f  mov     [rsp+188h+var_138], rax
0x180057994  cmp     rax, rbx
0x180057997  jz      loc_180057BE1
0x18005799d  sub     rbx, rax
0x1800579a0  sar     rbx, 1
0x1800579a3  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x1800579ab  cmp     rbx, rdx
0x1800579ae  jb      loc_180057BE1
0x1800579b4  mov     rcx, [rsp+188h+var_C8]
0x1800579bc  sub     rax, rcx
0x1800579bf  sar     rax, 1
0x1800579c2  lea     r8, [rcx+rax*2]; lpString2
0x1800579c6  lea     rcx, [rsp+188h+lpString1]
0x1800579ce  cmp     [rsp+188h+var_88], 7
0x1800579d7  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x1800579e0  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x1800579e8  mov     r9d, edx; cchCount2
0x1800579eb  call    cs:__imp_CompareStringOrdinal
0x1800579f2  nop     dword ptr [rax+rax+00h]
0x1800579f7  cmp     eax, 2
0x1800579fa  jnz     loc_180057BE1
0x180057a00  mov     [rsp+188h+var_D8], esi
0x180057a07  mov     [rsp+188h+var_150], esi
0x180057a0b  mov     [rsp+188h+var_158], rsi
0x180057a10  mov     [rsp+188h+var_160], 30h ; '0'
0x180057a18  lea     rax, [rsp+188h+var_60]
0x180057a20  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x180057a25  lea     r9, [rsp+188h+var_D8]
0x180057a2d  lea     r8, DEVPKEY_Device_DriverVersion
0x180057a34  lea     rdx, [rsp+188h+var_80]
0x180057a3c  mov     rcx, r14
0x180057a3f  mov     rax, [rsp+188h+var_118]
0x180057a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a49  mov     rcx, [rsp+188h]; this
0x180057a51  test    eax, eax
0x180057a53  jnz     short loc_180057A5F
0x180057a55  mov     edx, 0C2h; void *
0x180057a5a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180057a5f  mov     rax, rsi
0x180057a62  mov     [rsp+188h+var_D0], rax
0x180057a6a  mov     rbx, rsi
0x180057a6d  xor     r12d, r12d
0x180057a70  cmp     rsi, 4
0x180057a74  jnb     loc_180057B57
0x180057a7a  mov     rcx, [rsp+188h]; this
0x180057a82  cmp     rbx, 18h
0x180057a86  jb      short loc_180057A9F
0x180057a88  mov     r9d, 80070057h; char *
0x180057a8e  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180057a95  mov     edx, 0CBh; void *
0x180057a9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180057a9f  mov     [rsp+188h+var_138], r12
0x180057aa4  lea     rdx, [rsp+188h+var_60]
0x180057aac  lea     rdx, [rdx+rbx*2]
0x180057ab0  lea     rcx, [rsp+188h+String]
0x180057ab8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180057abd  nop
0x180057abe  lea     rdx, [rsp+188h+var_138]
0x180057ac3  lea     rcx, [rsp+188h+String]; String
0x180057acb  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180057ad0  mov     word ptr [rsp+rsi*2+188h+var_D0], ax
0x180057ad8  lea     rcx, [rsp+188h+String]
0x180057ae0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057ae5  mov     rcx, [rsp+188h]; this
0x180057aed  cmp     rsi, 3
0x180057af1  jz      short loc_180057B2D
0x180057af3  add     rbx, [rsp+188h+var_138]
0x180057af8  cmp     [rsp+rbx*2+188h+var_60], 2Eh ; '.'
0x180057b01  jz      short loc_180057B1A
0x180057b03  mov     r9d, 80070057h; char *
0x180057b09  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180057b10  mov     edx, 0D3h; void *
0x180057b15  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180057b1a  inc     rbx
0x180057b1d  inc     rsi
0x180057b20  mov     rax, [rsp+188h+var_D0]
0x180057b28  jmp     loc_180057A70
0x180057b2d  mov     rdx, [rsp+188h+var_138]
0x180057b32  add     rdx, rbx
0x180057b35  cmp     [rsp+rdx*2+188h+var_60], r12w
0x180057b3e  jz      short loc_180057B1D
0x180057b40  mov     r9d, 80070057h; char *
0x180057b46  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180057b4d  mov     edx, 0DBh; void *
0x180057b52  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180057b57  movzx   ecx, word ptr [rsp+188h+var_D0+6]
0x180057b5f  mov     [rdi], cx
0x180057b62  movzx   ecx, word ptr [rsp+188h+var_D0+4]
0x180057b6a  mov     [rdi+2], cx
0x180057b6e  movzx   ecx, word ptr [rsp+188h+var_D0+2]
0x180057b76  mov     [rdi+4], cx
0x180057b7a  mov     [rdi+6], ax
0x180057b7e  mov     rcx, [rsp+188h+var_C8]
0x180057b86  test    rcx, rcx
0x180057b89  jz      short loc_180057BB5
0x180057b8b  mov     rdx, [rsp+188h+var_B8]
0x180057b93  sub     rdx, rcx
0x180057b96  sar     rdx, 1
0x180057b99  add     rdx, rdx
0x180057b9c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180057ba1  xorps   xmm0, xmm0
0x180057ba4  movdqu  xmmword ptr [rsp+188h+var_C8], xmm0
0x180057bad  mov     [rsp+188h+var_B8], r12
0x180057bb5  mov     rcx, r14
0x180057bb8  mov     rax, r15
0x180057bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bc0  nop
0x180057bc1  lea     rcx, [rsp+188h+lpString1]
0x180057bc9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057bce  nop
0x180057bcf  lea     rcx, [rsp+188h+var_130]
0x180057bd4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180057bd9  mov     rax, rdi
0x180057bdc  jmp     loc_180057C7B
0x180057be1  inc     r12d
0x180057be4  mov     rcx, [rsp+188h+var_C8]
0x180057bec  test    rcx, rcx
0x180057bef  mov     ebx, 0C8h
0x180057bf4  jz      loc_180057826
0x180057bfa  mov     rdx, [rsp+188h+var_B8]
0x180057c02  sub     rdx, rcx
0x180057c05  sar     rdx, 1
0x180057c08  add     rdx, rdx
  ... truncated ...
```
