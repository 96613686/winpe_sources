# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x18009a9b8`
- end: `0x18009b01b`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1635`
- prototype: `udk::CopilotPlusDetection::details *__fastcall(udk::CopilotPlusDetection::details *this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180099ce4`

## callees

- `0x180014e08`
- `0x1800641a8`
- `0x1800718e0`
- `0x180071dc0`
- `0x180072cf4`
- `0x180078224`
- `0x180091680`
- `0x180092e40`
- `0x180092e9c`
- `0x180095138`
- `0x180095af0`
- `0x180099bf0`
- `0x18009a758`
- `0x18009a9b8`
- `0x18009c418`
- `0x18009c9d4`
- `0x1800ea010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18009ae2b`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18009ae2b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009ae3f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009ae3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18009ae14`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18009ae14`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18009addb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18009addb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aabc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aa92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aabc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aae8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009aa0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009aa0d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ad16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ad16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af7e`

## string_xrefs

- `0x18009aa06`: `setupapi.dll`

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
  const char *v48; // r9
  void *v49[2]; // [rsp+50h] [rbp-138h] BYREF
  __int64 v50; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v52; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v53[2]; // [rsp+78h] [rbp-110h] BYREF
  void (__fastcall *v54)(__int64); // [rsp+88h] [rbp-100h]
  __int64 v55; // [rsp+90h] [rbp-F8h]
  FARPROC v56; // [rsp+98h] [rbp-F0h]
  char v57; // [rsp+A0h] [rbp-E8h]
  FARPROC v58; // [rsp+A8h] [rbp-E0h]
  _DWORD v59[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v62; // [rsp+D8h] [rbp-B0h]
  _OWORD v63[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v65[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v53[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v7 = Library;
  v53[0] = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x86, v5, v6);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x89, v8, v9);
  v13 = GetProcAddress(v7, "SetupDiDestroyDeviceInfoList");
  v54 = (void (__fastcall *)(__int64))v13;
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8B, v11, v12);
  v16 = GetProcAddress(v7, "SetupDiEnumDeviceInfo");
  if ( !v16 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8D, v14, v15);
  EndPtr = (wchar_t *)GetProcAddress(v7, "SetupDiGetDeviceInstanceIdW");
  if ( !EndPtr )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x8F, v17, v18);
  v58 = GetProcAddress(v7, "SetupDiGetDevicePropertyW");
  if ( !v58 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x91, v19, v20);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v59[0] = -266691245;
  v59[1] = 1221738486;
  v59[2] = -1480026209;
  v59[3] = 216091392;
  v21 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v59, 0, 0, 2);
  v22 = v21;
  if ( v21 == -1 )
    goto LABEL_58;
  v55 = v21;
  v56 = v13;
  v57 = 1;
  memset(v63, 0, sizeof(v63));
  LODWORD(v63[0]) = 32;
  for ( i = 0; ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v16)(v22, i, v63); ++i )
  {
    std::vector<std::wstring>::vector<std::wstring>(v49);
    v24 = (char *)v49[1];
    v25 = ((char *)v49[1] - (char *)v49[0]) >> 1;
    if ( v25 <= 0xC8 )
    {
      if ( v25 >= 0xC8 )
        goto LABEL_22;
      if ( (unsigned __int64)((signed __int64)(v50 - (unsigned __int64)v49[0]) >> 1) < 0xC8 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v49);
        v24 = (char *)v49[1];
        goto LABEL_22;
      }
      v26 = 2 * (200 - v25);
      memset_0(v49[1], 0, v26);
      v24 += v26;
    }
    else
    {
      v24 = (char *)v49[0] + 400;
    }
    v49[1] = v24;
LABEL_22:
    v27 = ((__int64 (__fastcall *)(__int64, _OWORD *, void *, _QWORD, _QWORD))EndPtr)(
            v22,
            v63,
            v49[0],
            (unsigned int)((v24 - (char *)v49[0]) >> 1),
            0);
    v30 = 0;
    if ( !v27 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xAB, v28, v29);
    trivial_2 = (char *)_std_find_trivial_2(v49[0], v49[1], 0);
    v32 = (char *)_std_find_trivial_2(v49[0], trivial_2, 92);
    if ( v32 != v49[1] && trivial_2 != v49[1] )
    {
      v33 = v32 + 2;
      if ( v32 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v33) >> 1) >= *(_QWORD *)cchCount2 )
      {
        v34 = (const WCHAR *)((char *)v49[0] + 2 * ((v33 - (char *)v49[0]) >> 1));
        v35 = (const WCHAR *)lpString1;
        if ( v62 > 7 )
          v35 = lpString1[0];
        if ( CompareStringOrdinal(v35, cchCount2[0], v34, cchCount2[0], 1) == 2 )
        {
          v52 = 0;
          if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v58)(
                  v22,
                  v63,
                  &DEVPKEY_Device_DriverVersion,
                  &v52) )
            wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC2, v36, v37);
          v38 = 0;
          v58 = 0;
          for ( j = 0; j < 4; ++j )
          {
            if ( v30 >= 0x18 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                (const char *)0x80070057LL,
                (int)v65);
            std::wstring::wstring(String, &v65[v30]);
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
            *((_WORD *)&v59[-2] + j) = v43;
            std::wstring::_Tidy_deallocate(String);
            v45 = v44 - v42 + v30;
            v46 = v65[v45];
            if ( j == 3 )
            {
              if ( v46 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v65);
            }
            else
            {
              if ( v46 != 46 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v65);
              v30 = v45 + 1;
            }
            v38 = (__int16)v58;
          }
          *(_WORD *)this = HIWORD(v58);
          *((_WORD *)this + 1) = WORD2(v58);
          *((_WORD *)this + 2) = WORD1(v58);
          *((_WORD *)this + 3) = v38;
          if ( v49[0] )
          {
            std::_Deallocate<16>(v49[0], 2 * ((signed __int64)(v50 - (unsigned __int64)v49[0]) >> 1));
            *(_OWORD *)v49 = 0;
            v50 = 0;
          }
          v54(v22);
          std::wstring::_Tidy_deallocate(lpString1);
          SearchFolderInstance::~SearchFolderInstance((SearchFolderInstance *)v53);
          return this;
        }
      }
    }
    if ( v49[0] )
      std::_Deallocate<16>(v49[0], 2 * ((signed __int64)(v50 - (unsigned __int64)v49[0]) >> 1));
  }
  if ( GetLastError() != 259 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v48);
  ((void (__fastcall *)(__int64))v13)(v22);
LABEL_58:
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::_Tidy_deallocate(lpString1);
  SearchFolderInstance::~SearchFolderInstance((SearchFolderInstance *)v53);
  return this;
}

```

## disassembly

```asm
0x18009a9b8  mov     [rsp+arg_10], rbx
0x18009a9bd  mov     [rsp+arg_18], rsi
0x18009a9c2  push    rdi
0x18009a9c3  push    r12
0x18009a9c5  push    r13
0x18009a9c7  push    r14
0x18009a9c9  push    r15
0x18009a9cb  sub     rsp, 160h
0x18009a9d2  mov     rax, cs:__security_cookie
0x18009a9d9  xor     rax, rsp
0x18009a9dc  mov     [rsp+188h+var_38], rax
0x18009a9e4  mov     rsi, rdx
0x18009a9e7  mov     rdi, rcx
0x18009a9ea  mov     [rsp+188h+var_108], rcx
0x18009a9f2  add     rdx, 4
0x18009a9f6  mov     rcx, rsi
0x18009a9f9  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x18009a9fe  xor     edx, edx; hFile
0x18009aa00  mov     r8d, 800h; dwFlags
0x18009aa06  lea     rcx, aSetupapiDll; "setupapi.dll"
0x18009aa0d  call    cs:__imp_LoadLibraryExW
0x18009aa13  mov     rbx, rax
0x18009aa16  mov     [rsp+188h+var_110], rax
0x18009aa1b  mov     rcx, [rsp+188h]; this
0x18009aa23  test    rax, rax
0x18009aa26  jz      loc_18009AFDA
0x18009aa2c  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x18009aa33  mov     rcx, rax; hModule
0x18009aa36  call    cs:__imp_GetProcAddress
0x18009aa3c  mov     r14, rax
0x18009aa3f  mov     rcx, [rsp+188h]; this
0x18009aa47  test    rax, rax
0x18009aa4a  jnz     short loc_18009AA56
0x18009aa4c  mov     edx, 89h; void *
0x18009aa51  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009aa56  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x18009aa5d  mov     rcx, rbx; hModule
0x18009aa60  call    cs:__imp_GetProcAddress
0x18009aa66  mov     r15, rax
0x18009aa69  mov     [rsp+188h+var_100], rax
0x18009aa71  mov     rcx, [rsp+188h]; this
0x18009aa79  test    rax, rax
0x18009aa7c  jnz     short loc_18009AA88
0x18009aa7e  mov     edx, 8Bh; void *
0x18009aa83  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009aa88  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x18009aa8f  mov     rcx, rbx; hModule
0x18009aa92  call    cs:__imp_GetProcAddress
0x18009aa98  mov     r13, rax
0x18009aa9b  mov     rcx, [rsp+188h]; this
0x18009aaa3  test    rax, rax
0x18009aaa6  jnz     short loc_18009AAB2
0x18009aaa8  mov     edx, 8Dh; void *
0x18009aaad  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009aab2  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x18009aab9  mov     rcx, rbx; hModule
0x18009aabc  call    cs:__imp_GetProcAddress
0x18009aac2  mov     [rsp+188h+EndPtr], rax
0x18009aac7  mov     rcx, [rsp+188h]; this
0x18009aacf  test    rax, rax
0x18009aad2  jnz     short loc_18009AADE
0x18009aad4  mov     edx, 8Fh; void *
0x18009aad9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009aade  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x18009aae5  mov     rcx, rbx; hModule
0x18009aae8  call    cs:__imp_GetProcAddress
0x18009aaee  mov     [rsp+188h+var_E0], rax
0x18009aaf6  mov     rcx, [rsp+188h]; this
0x18009aafe  test    rax, rax
0x18009ab01  jnz     short loc_18009AB0D
0x18009ab03  mov     edx, 91h; void *
0x18009ab08  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009ab0d  mov     rdx, rsi
0x18009ab10  lea     rcx, [rsp+188h+lpString1]
0x18009ab18  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x18009ab1d  nop
0x18009ab1e  mov     [rsp+188h+var_D8], 0F01A9D53h
0x18009ab29  mov     [rsp+188h+var_D4], 48D23FF6h
0x18009ab34  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x18009ab3f  mov     ebx, 0C8h
0x18009ab44  xor     esi, esi
0x18009ab46  mov     [rsp+188h+var_CC], 0CE14B00h
0x18009ab51  lea     r9d, [rsi+2]
0x18009ab55  xor     r8d, r8d
0x18009ab58  xor     edx, edx
0x18009ab5a  lea     rcx, [rsp+188h+var_D8]
0x18009ab62  mov     rax, r14
0x18009ab65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab6a  mov     r12, rax
0x18009ab6d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009ab71  jz      loc_18009AFB1
0x18009ab77  mov     [rsp+188h+var_F8], rax
0x18009ab7f  mov     [rsp+188h+var_F0], r15
0x18009ab87  mov     [rsp+188h+var_E8], 1
0x18009ab8f  xorps   xmm0, xmm0
0x18009ab92  movups  [rsp+188h+var_A8], xmm0
0x18009ab9a  movups  [rsp+188h+var_98], xmm0
0x18009aba2  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x18009abad  mov     r14d, esi
0x18009abb0  lea     r8, [rsp+188h+var_A8]
0x18009abb8  mov     edx, r14d
0x18009abbb  mov     rcx, r12
0x18009abbe  mov     rax, r13
0x18009abc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abc6  test    eax, eax
0x18009abc8  jz      loc_18009AF7E
0x18009abce  lea     rcx, [rsp+188h+var_138]
0x18009abd3  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18009abd8  nop
0x18009abd9  mov     rdx, [rsp+188h+var_138]
0x18009abde  mov     rsi, [rsp+188h+var_138+8]
0x18009abe3  mov     rcx, rsi
0x18009abe6  sub     rcx, rdx
0x18009abe9  sar     rcx, 1
0x18009abec  cmp     rcx, rbx
0x18009abef  jbe     short loc_18009ABFA
0x18009abf1  lea     rsi, [rdx+190h]
0x18009abf8  jmp     short loc_18009AC37
0x18009abfa  jnb     short loc_18009AC3C
0x18009abfc  mov     rax, [rsp+188h+var_128]
0x18009ac01  sub     rax, rdx
0x18009ac04  sar     rax, 1
0x18009ac07  cmp     rax, rbx
0x18009ac0a  jnb     short loc_18009AC1D
0x18009ac0c  lea     rcx, [rsp+188h+var_138]
0x18009ac11  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18009ac16  mov     rsi, [rsp+188h+var_138+8]
0x18009ac1b  jmp     short loc_18009AC3C
0x18009ac1d  mov     rax, rbx
0x18009ac20  sub     rax, rcx
0x18009ac23  lea     rbx, [rax+rax]
0x18009ac27  mov     r8, rbx; Size
0x18009ac2a  xor     edx, edx; Val
0x18009ac2c  mov     rcx, rsi; void *
0x18009ac2f  call    memset_0
0x18009ac34  add     rsi, rbx
0x18009ac37  mov     [rsp+188h+var_138+8], rsi
0x18009ac3c  mov     r8, [rsp+188h+var_138]
0x18009ac41  sub     rsi, r8
0x18009ac44  sar     rsi, 1
0x18009ac47  mov     qword ptr [rsp+188h+bIgnoreCase], 0
0x18009ac50  mov     r9d, esi
0x18009ac53  lea     rdx, [rsp+188h+var_A8]
0x18009ac5b  mov     rcx, r12
0x18009ac5e  mov     rax, [rsp+188h+EndPtr]
0x18009ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac68  mov     rcx, [rsp+188h]; this
0x18009ac70  xor     esi, esi
0x18009ac72  test    eax, eax
0x18009ac74  jnz     short loc_18009AC80
0x18009ac76  mov     edx, 0ABh; void *
0x18009ac7b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009ac80  xor     r8d, r8d
0x18009ac83  mov     rdx, [rsp+188h+var_138+8]
0x18009ac88  mov     rcx, [rsp+188h+var_138]
0x18009ac8d  call    __std_find_trivial_2
0x18009ac92  mov     rbx, rax
0x18009ac95  mov     r8d, 5Ch ; '\'
0x18009ac9b  mov     rdx, rax
0x18009ac9e  mov     rcx, [rsp+188h+var_138]
0x18009aca3  call    __std_find_trivial_2
0x18009aca8  cmp     rax, [rsp+188h+var_138+8]
0x18009acad  jz      loc_18009AF50
0x18009acb3  cmp     rbx, [rsp+188h+var_138+8]
0x18009acb8  jz      loc_18009AF50
0x18009acbe  lea     rcx, [rax+2]
0x18009acc2  cmp     rcx, rbx
0x18009acc5  jz      loc_18009AF50
0x18009accb  sub     rbx, rcx
0x18009acce  sar     rbx, 1
0x18009acd1  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x18009acd9  cmp     rbx, rdx
0x18009acdc  jb      loc_18009AF50
0x18009ace2  mov     rax, [rsp+188h+var_138]
0x18009ace7  sub     rcx, rax
0x18009acea  sar     rcx, 1
0x18009aced  lea     r8, [rax+rcx*2]; lpString2
0x18009acf1  lea     rcx, [rsp+188h+lpString1]
0x18009acf9  cmp     [rsp+188h+var_B0], 7
0x18009ad02  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x18009ad0b  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x18009ad13  mov     r9d, edx; cchCount2
0x18009ad16  call    cs:__imp_CompareStringOrdinal
0x18009ad1c  cmp     eax, 2
0x18009ad1f  jnz     loc_18009AF50
0x18009ad25  mov     [rsp+188h+var_118], esi
0x18009ad29  mov     [rsp+188h+var_150], esi
0x18009ad2d  mov     [rsp+188h+var_158], rsi
0x18009ad32  mov     [rsp+188h+var_160], 30h ; '0'
0x18009ad3a  lea     rax, [rsp+188h+var_68]
0x18009ad42  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x18009ad47  lea     r9, [rsp+188h+var_118]
0x18009ad4c  lea     r8, DEVPKEY_Device_DriverVersion
0x18009ad53  lea     rdx, [rsp+188h+var_A8]
0x18009ad5b  mov     rcx, r12
0x18009ad5e  mov     rax, [rsp+188h+var_E0]
0x18009ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad6b  mov     rcx, [rsp+188h]; this
0x18009ad73  test    eax, eax
0x18009ad75  jnz     short loc_18009AD81
0x18009ad77  mov     edx, 0C2h; void *
0x18009ad7c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18009ad81  mov     rax, rsi
0x18009ad84  mov     [rsp+188h+var_E0], rax
0x18009ad8c  xor     r14d, r14d
0x18009ad8f  mov     ebx, r14d
0x18009ad92  cmp     rbx, 4
0x18009ad96  jnb     loc_18009AECD
0x18009ad9c  mov     rcx, [rsp+188h]; this
0x18009ada4  cmp     rsi, 18h
0x18009ada8  jb      short loc_18009ADC1
0x18009adaa  mov     r9d, 80070057h; char *
0x18009adb0  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009adb7  mov     edx, 0CBh; void *
0x18009adbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009adc1  lea     rdx, [rsp+188h+var_68]
0x18009adc9  lea     rdx, [rdx+rsi*2]
0x18009adcd  lea     rcx, [rsp+188h+String]
0x18009add5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009adda  nop
0x18009addb  call    cs:__imp__o__errno
0x18009ade1  mov     r13, rax
0x18009ade4  lea     r15, [rsp+188h+String]
0x18009adec  cmp     [rsp+188h+var_70], 7
0x18009adf5  cmova   r15, [rsp+188h+String]
0x18009adfe  mov     [rsp+188h+EndPtr], r14
0x18009ae03  mov     [rax], r14d
0x18009ae06  mov     r8d, 0Ah; Radix
0x18009ae0c  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x18009ae11  mov     rcx, r15; String
0x18009ae14  call    cs:__imp_wcstol
0x18009ae1a  mov     r14, [rsp+188h+EndPtr]
0x18009ae1f  cmp     r15, r14
0x18009ae22  jnz     short loc_18009AE31
0x18009ae24  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x18009ae2b  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18009ae31  cmp     dword ptr [r13+0], 22h ; '"'
0x18009ae36  jnz     short loc_18009AE45
0x18009ae38  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x18009ae3f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009ae45  sub     r14, r15
0x18009ae48  sar     r14, 1
0x18009ae4b  mov     word ptr [rsp+rbx*2+188h+var_E0], ax
0x18009ae53  lea     rcx, [rsp+188h+String]
0x18009ae5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ae60  lea     rdx, [r14+rsi]
0x18009ae64  movzx   eax, [rsp+rdx*2+188h+var_68]
0x18009ae6c  mov     rcx, [rsp+188h]; this
0x18009ae74  cmp     rbx, 3
0x18009ae78  jz      short loc_18009AEAE
0x18009ae7a  cmp     ax, 2Eh ; '.'
0x18009ae7e  jz      short loc_18009AE97
0x18009ae80  mov     r9d, 80070057h; char *
0x18009ae86  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009ae8d  mov     edx, 0D3h; void *
0x18009ae92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ae97  lea     rsi, [rdx+1]
0x18009ae9b  xor     r14d, r14d
0x18009ae9e  inc     rbx
0x18009aea1  mov     rax, [rsp+188h+var_E0]
0x18009aea9  jmp     loc_18009AD92
0x18009aeae  xor     r14d, r14d
0x18009aeb1  test    ax, ax
0x18009aeb4  jz      short loc_18009AE9E
0x18009aeb6  mov     r9d, 80070057h; char *
0x18009aebc  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18009aec3  mov     edx, 0DBh; void *
0x18009aec8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009aecd  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x18009aed5  mov     [rdi], cx
0x18009aed8  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x18009aee0  mov     [rdi+2], cx
0x18009aee4  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x18009aeec  mov     [rdi+4], cx
0x18009aef0  mov     [rdi+6], ax
0x18009aef4  mov     rcx, [rsp+188h+var_138]
0x18009aef9  test    rcx, rcx
0x18009aefc  jz      short loc_18009AF1F
0x18009aefe  mov     rdx, [rsp+188h+var_128]
0x18009af03  sub     rdx, rcx
0x18009af06  sar     rdx, 1
0x18009af09  add     rdx, rdx
0x18009af0c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009af11  xorps   xmm0, xmm0
0x18009af14  movdqu  xmmword ptr [rsp+188h+var_138], xmm0
0x18009af1a  mov     [rsp+188h+var_128], r14
0x18009af1f  mov     rcx, r12
0x18009af22  mov     rax, [rsp+188h+var_100]
0x18009af2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af2f  nop
0x18009af30  lea     rcx, [rsp+188h+lpString1]
0x18009af38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009af3d  nop
0x18009af3e  lea     rcx, [rsp+188h+var_110]; this
0x18009af43  call    ??1SearchFolderInstance@@QEAA@XZ; SearchFolderInstance::~SearchFolderInstance(void)
0x18009af48  mov     rax, rdi
0x18009af4b  jmp     loc_18009AFED
0x18009af50  inc     r14d
0x18009af53  mov     rcx, [rsp+188h+var_138]
0x18009af58  test    rcx, rcx
  ... truncated ...
```
