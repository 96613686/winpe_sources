# SendMail

- ea: `0x140076bac`
- end: `0x140078e0f`
- name: `SendMail`
- size: `8803`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, OLECHAR *psz, int, int, OLECHAR *, OLECHAR *, HANDLE hToken, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140065504`

## callees

- `0x140001b40`
- `0x140004b30`
- `0x140004b58`
- `0x14007680c`
- `0x140076920`
- `0x1400769d0`
- `0x140076a64`
- `0x140076b34`
- `0x140076bac`
- `0x14007a688`
- `0x14007a69c`
- `0x140085010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x1400787e6`
- `ADVAPI32!RevertToSelf` at `0x1400787e6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140078677`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140078677`
- `KERNEL32!GetLastError` at `0x140078685`
- `KERNEL32!GetLastError` at `0x1400787f0`
- `KERNEL32!GetLastError` at `0x140078685`
- `KERNEL32!GetLastError` at `0x1400787f0`
- `ole32!CoUninitialize` at `0x14007866c`
- `ole32!CoUninitialize` at `0x140078728`
- `ole32!CoUninitialize` at `0x1400787d6`
- `ole32!CoUninitialize` at `0x14007866c`
- `ole32!CoUninitialize` at `0x140078728`
- `ole32!CoUninitialize` at `0x1400787d6`
- `ole32!CoInitializeEx` at `0x140076c23`
- `ole32!CoInitializeEx` at `0x140076c23`
- `ole32!CoCreateInstance` at `0x140076c96`
- `ole32!CoCreateInstance` at `0x140076d2c`
- `ole32!CoCreateInstance` at `0x140076c96`
- `ole32!CoCreateInstance` at `0x140076d2c`
- `ole32!OleRun` at `0x140076ca7`
- `ole32!OleRun` at `0x140076d3d`
- `ole32!OleRun` at `0x140076ca7`
- `ole32!OleRun` at `0x140076d3d`
- `OLEAUT32!__imp_SysAllocString` at `0x140076e19`
- `OLEAUT32!__imp_SysAllocString` at `0x140076f03`
- `OLEAUT32!__imp_SysAllocString` at `0x140076f51`
- `OLEAUT32!__imp_SysAllocString` at `0x140076ffe`
- `OLEAUT32!__imp_SysAllocString` at `0x1400770ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1400771ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1400772c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1400773a9`
- `OLEAUT32!__imp_SysAllocString` at `0x14007748b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400774d9`
- `OLEAUT32!__imp_SysAllocString` at `0x140077586`
- `OLEAUT32!__imp_SysAllocString` at `0x1400775d4`
- `OLEAUT32!__imp_SysAllocString` at `0x140077686`
- `OLEAUT32!__imp_SysAllocString` at `0x140078457`
- `OLEAUT32!__imp_SysAllocString` at `0x140076e19`
- `OLEAUT32!__imp_SysAllocString` at `0x140076f03`
- `OLEAUT32!__imp_SysAllocString` at `0x140076f51`
- `OLEAUT32!__imp_SysAllocString` at `0x140076ffe`
- `OLEAUT32!__imp_SysAllocString` at `0x1400770ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1400771ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1400772c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1400773a9`
- `OLEAUT32!__imp_SysAllocString` at `0x14007748b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400774d9`
- `OLEAUT32!__imp_SysAllocString` at `0x140077586`
- `OLEAUT32!__imp_SysAllocString` at `0x1400775d4`
- `OLEAUT32!__imp_SysAllocString` at `0x140077686`
- `OLEAUT32!__imp_SysAllocString` at `0x140078457`
- `OLEAUT32!__imp_VariantClear` at `0x140076eb3`
- `OLEAUT32!__imp_VariantClear` at `0x140076ee0`
- `OLEAUT32!__imp_VariantClear` at `0x140076fbc`
- `OLEAUT32!__imp_VariantClear` at `0x140076fe9`
- `OLEAUT32!__imp_VariantClear` at `0x1400770ad`
- `OLEAUT32!__imp_VariantClear` at `0x1400770da`
- `OLEAUT32!__imp_VariantClear` at `0x14007718c`
- `OLEAUT32!__imp_VariantClear` at `0x1400771b9`
- `OLEAUT32!__imp_VariantClear` at `0x140077266`
- `OLEAUT32!__imp_VariantClear` at `0x140077293`
- `OLEAUT32!__imp_VariantClear` at `0x140077362`
- `OLEAUT32!__imp_VariantClear` at `0x14007738f`
- `OLEAUT32!__imp_VariantClear` at `0x140077449`
- `OLEAUT32!__imp_VariantClear` at `0x140077476`
- `OLEAUT32!__imp_VariantClear` at `0x140077544`
- `OLEAUT32!__imp_VariantClear` at `0x140077571`
- `OLEAUT32!__imp_VariantClear` at `0x14007763f`
- `OLEAUT32!__imp_VariantClear` at `0x14007766c`
- `OLEAUT32!__imp_VariantClear` at `0x140077720`
- `OLEAUT32!__imp_VariantClear` at `0x14007774d`
- `OLEAUT32!__imp_VariantClear` at `0x140077905`
- `OLEAUT32!__imp_VariantClear` at `0x14007851c`
- `OLEAUT32!__imp_VariantClear` at `0x140078549`
- `OLEAUT32!__imp_VariantClear` at `0x140076eb3`
- `OLEAUT32!__imp_VariantClear` at `0x140076ee0`
- `OLEAUT32!__imp_VariantClear` at `0x140076fbc`
- `OLEAUT32!__imp_VariantClear` at `0x140076fe9`
- `OLEAUT32!__imp_VariantClear` at `0x1400770ad`
- `OLEAUT32!__imp_VariantClear` at `0x1400770da`
- `OLEAUT32!__imp_VariantClear` at `0x14007718c`
- `OLEAUT32!__imp_VariantClear` at `0x1400771b9`
- `OLEAUT32!__imp_VariantClear` at `0x140077266`
- `OLEAUT32!__imp_VariantClear` at `0x140077293`
- `OLEAUT32!__imp_VariantClear` at `0x140077362`
- `OLEAUT32!__imp_VariantClear` at `0x14007738f`
- `OLEAUT32!__imp_VariantClear` at `0x140077449`
- `OLEAUT32!__imp_VariantClear` at `0x140077476`
- `OLEAUT32!__imp_VariantClear` at `0x140077544`
- `OLEAUT32!__imp_VariantClear` at `0x140077571`
- `OLEAUT32!__imp_VariantClear` at `0x14007763f`
- `OLEAUT32!__imp_VariantClear` at `0x14007766c`
- `OLEAUT32!__imp_VariantClear` at `0x140077720`
- `OLEAUT32!__imp_VariantClear` at `0x14007774d`
- `OLEAUT32!__imp_VariantClear` at `0x140077905`
- `OLEAUT32!__imp_VariantClear` at `0x14007851c`
- `OLEAUT32!__imp_VariantClear` at `0x140078549`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400784b4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400784b4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400784bf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400784bf`

## string_xrefs

- `0x14007757f`: `http://schemas.microsoft.com/cdo/configuration/sendpassword`
- `0x140077484`: `http://schemas.microsoft.com/cdo/configuration/sendusername`
- `0x140076e12`: `http://schemas.microsoft.com/cdo/configuration/sendusing`
- `0x1400772c2`: `http://schemas.microsoft.com/cdo/configuration/smtpauthenticate`
- `0x1400773a2`: `http://schemas.microsoft.com/cdo/configuration/smtpauthenticate`
- `0x14007767f`: `http://schemas.microsoft.com/cdo/configuration/smtpauthenticate`
- `0x1400770e8`: `http://schemas.microsoft.com/cdo/configuration/smtpconnectiontimeout`
- `0x140076efc`: `http://schemas.microsoft.com/cdo/configuration/smtpserver`
- `0x140076ff7`: `http://schemas.microsoft.com/cdo/configuration/smtpserverport`
- `0x1400771c7`: `http://schemas.microsoft.com/cdo/configuration/urlgetlatestversion`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
__int64 __fastcall SendMail(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        OLECHAR *psz,
        LONG a9,
        int a10,
        OLECHAR *a11,
        OLECHAR *a12,
        HANDLE hToken)
{
  HRESULT v16; // eax
  unsigned int v17; // ebx
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  HRESULT Instance; // ebx
  HRESULT v21; // ebx
  struct IUnknown *v22; // rbx
  int v23; // eax
  struct IUnknown *v24; // rbx
  struct IUnknown *v25; // rdi
  BSTR v26; // rax
  struct IUnknown *v27; // rbx
  int v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  struct IUnknown *v31; // rbx
  BSTR v32; // rax
  struct IUnknown *v33; // rbx
  BSTR v34; // rax
  int v35; // eax
  HRESULT v36; // eax
  HRESULT v37; // eax
  BSTR v38; // rax
  struct IUnknown *v39; // rbx
  int v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // eax
  BSTR v43; // rax
  struct IUnknown *v44; // rbx
  int v45; // eax
  HRESULT v46; // eax
  HRESULT v47; // eax
  BSTR v48; // rax
  struct IUnknown *v49; // rbx
  int v50; // eax
  HRESULT v51; // eax
  HRESULT v52; // eax
  BSTR v53; // rax
  struct IUnknown *v54; // rbx
  int v55; // eax
  HRESULT v56; // eax
  HRESULT v57; // eax
  BSTR v58; // rax
  struct IUnknown *v59; // rdi
  struct IUnknown *v60; // rbx
  int v61; // eax
  HRESULT v62; // eax
  HRESULT v63; // eax
  BSTR v64; // rax
  struct IUnknown *v65; // rbx
  BSTR v66; // rax
  int v67; // eax
  HRESULT v68; // eax
  HRESULT v69; // eax
  BSTR v70; // rax
  struct IUnknown *v71; // rbx
  BSTR v72; // rax
  int v73; // eax
  HRESULT v74; // eax
  HRESULT v75; // eax
  BSTR v76; // rax
  struct IUnknown *v77; // rbx
  int v78; // eax
  HRESULT v79; // eax
  HRESULT v80; // eax
  struct IUnknown *v81; // rbx
  int v82; // eax
  struct IUnknown *v83; // rbx
  int v84; // eax
  struct IUnknown *v85; // rbx
  _bstr_t *v86; // rdi
  __int64 v87; // rdx
  int v88; // eax
  struct IUnknown *v89; // rbx
  _bstr_t *v90; // rdi
  __int64 v91; // rdx
  int v92; // eax
  struct IUnknown *v93; // rbx
  _bstr_t *v94; // rdi
  __int64 v95; // rdx
  int v96; // eax
  struct IUnknown *v97; // rbx
  int v98; // eax
  HRESULT v99; // eax
  struct IUnknown *v100; // rbx
  int v101; // eax
  struct IUnknown *v102; // rbx
  _bstr_t *v103; // rdi
  __int64 v104; // rdx
  int v105; // eax
  struct IUnknown *v106; // rbx
  int v107; // eax
  struct IUnknown *v108; // rbx
  int v109; // r12d
  _bstr_t *v110; // rax
  _bstr_t *v111; // rdi
  __int64 v112; // rdx
  int v113; // eax
  struct IUnknown *v114; // rdi
  int v115; // ecx
  _bstr_t *v116; // rbx
  __int64 v117; // rdx
  int v118; // eax
  struct IUnknown *v119; // rsi
  struct IUnknown *v120; // r13
  int v121; // eax
  struct IUnknown *v122; // rbx
  struct IUnknown *v123; // r12
  _bstr_t *v124; // rax
  _bstr_t *v125; // rbx
  __int64 v126; // rdx
  int v127; // eax
  _bstr_t *v128; // rax
  _bstr_t *v129; // rbx
  __int64 v130; // rdx
  int v131; // eax
  _bstr_t *v132; // rax
  _bstr_t *v133; // rbx
  __int64 v134; // rdx
  int v135; // eax
  int v136; // eax
  struct IUnknown *v137; // rbx
  _bstr_t *v138; // rax
  _bstr_t *v139; // rbx
  __int64 v140; // rdx
  int v141; // eax
  int v142; // eax
  _bstr_t *v143; // rax
  _bstr_t *v144; // rbx
  __int64 v145; // rdx
  int v146; // eax
  struct IUnknown *v147; // rsi
  struct IUnknown *v148; // r13
  int v149; // eax
  struct IUnknown *v150; // rbx
  struct IUnknown *v151; // r12
  _bstr_t *v152; // rax
  _bstr_t *v153; // rbx
  __int64 v154; // rdx
  int v155; // eax
  _bstr_t *v156; // rax
  _bstr_t *v157; // rbx
  __int64 v158; // rdx
  int v159; // eax
  _bstr_t *v160; // rax
  _bstr_t *v161; // rbx
  __int64 v162; // rdx
  int v163; // eax
  int v164; // eax
  struct IUnknown *v165; // rbx
  _bstr_t *v166; // rax
  _bstr_t *v167; // rbx
  __int64 v168; // rdx
  int v169; // eax
  int v170; // eax
  struct IUnknown *v171; // rsi
  struct IUnknown *v172; // rbx
  _bstr_t *v173; // r13
  _bstr_t *v174; // rax
  _bstr_t *v175; // r12
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r9
  __int64 v177; // r8
  __int64 v178; // rdx
  int v179; // eax
  struct IUnknown *v180; // rbx
  _bstr_t *v181; // rbx
  __int64 v182; // rdx
  int v183; // eax
  _bstr_t *v184; // rbx
  __int64 v185; // rdx
  int v186; // eax
  int v187; // eax
  struct IUnknown *v188; // rbx
  int v189; // eax
  struct IUnknown *v190; // r15
  struct IUnknown **v191; // rax
  __int64 v192; // r15
  __int64 v193; // r15
  BSTR v194; // rax
  struct IUnknown *v195; // r15
  OLECHAR *v196; // r12
  UINT v197; // eax
  BSTR v198; // rax
  int v199; // eax
  HRESULT v200; // eax
  HRESULT v201; // eax
  int v202; // eax
  int v203; // eax
  signed int LastError; // eax
  struct IUnknown *v205; // rbx
  int v206; // eax
  signed int v207; // eax
  OLECHAR **v209; // [rsp+40h] [rbp-118h] BYREF
  struct IUnknown *v210; // [rsp+48h] [rbp-110h] BYREF
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp-108h] BYREF
  struct IUnknown *v212; // [rsp+58h] [rbp-100h] BYREF
  struct IUnknown *v213; // [rsp+60h] [rbp-F8h] BYREF
  struct IUnknown **v214; // [rsp+68h] [rbp-F0h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-E8h] BYREF
  struct IUnknown *v216; // [rsp+88h] [rbp-D0h] BYREF
  VARIANTARG v217; // [rsp+90h] [rbp-C8h] BYREF
  struct IUnknown *v218; // [rsp+A8h] [rbp-B0h] BYREF
  VARIANTARG v219; // [rsp+B0h] [rbp-A8h] BYREF
  char v220[8]; // [rsp+D0h] [rbp-88h] BYREF
  unsigned int v221; // [rsp+D8h] [rbp-80h]
  struct IUnknown *v222; // [rsp+E0h] [rbp-78h]
  struct IUnknown *v223; // [rsp+E8h] [rbp-70h] BYREF
  struct IUnknown *v224; // [rsp+F0h] [rbp-68h] BYREF
  int v225; // [rsp+F8h] [rbp-60h]
  struct IUnknown *v226; // [rsp+100h] [rbp-58h]
  struct IUnknown *v227; // [rsp+108h] [rbp-50h]
  _bstr_t *v228; // [rsp+110h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4b0f9bf04b2337a3602c77c835f6eba7_Traceguids);
  }
  v225 = 0;
  v16 = CoInitializeEx(0, 2u);
  v17 = 0;
  if ( v16 != 1 )
    v17 = v16;
  v221 = v17;
  if ( (v17 & 0x80000000) != 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = 11;
LABEL_314:
      WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_4b0f9bf04b2337a3602c77c835f6eba7_Traceguids, v17);
      return v17;
    }
    return v17;
  }
  v216 = 0;
  pUnknown = 0;
  Instance = CoCreateInstance(
               &GUID_cd000001_8b95_11d1_82db_00c04fb1625d,
               0,
               0x17u,
               &GUID_00000000_0000_0000_c000_000000000046,
               (LPVOID *)&pUnknown);
  if ( Instance >= 0 )
  {
    Instance = OleRun(pUnknown);
    if ( Instance >= 0 )
      Instance = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, struct IUnknown **))pUnknown->lpVtbl->QueryInterface)(
                   pUnknown,
                   &GUID_cd000020_8b95_11d1_82db_00c04fb1625d,
                   &v216);
    ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  }
  if ( (int)(Instance + 0x80000000) >= 0 && Instance != -2147467262 )
    _com_issue_error(Instance);
  v223 = 0;
  pUnknown = 0;
  v21 = CoCreateInstance(
          &GUID_cd000002_8b95_11d1_82db_00c04fb1625d,
          0,
          0x17u,
          &GUID_00000000_0000_0000_c000_000000000046,
          (LPVOID *)&pUnknown);
  if ( v21 >= 0 )
  {
    v21 = OleRun(pUnknown);
    if ( v21 >= 0 )
      v21 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, struct IUnknown **))pUnknown->lpVtbl->QueryInterface)(
              pUnknown,
              &GUID_cd000022_8b95_11d1_82db_00c04fb1625d,
              &v223);
    ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  }
  if ( (int)(v21 + 0x80000000) >= 0 && v21 != -2147467262 )
    _com_issue_error(v21);
  pUnknown = 0;
  v22 = v223;
  if ( !v223 )
    _com_issue_error(-2147467261);
  v213 = 0;
  v23 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v223->lpVtbl[2].AddRef)(v223, &v213);
  if ( v23 < 0 )
    _com_issue_errorex(v23, v22, &GUID_cd000022_8b95_11d1_82db_00c04fb1625d);
  v24 = v213;
  v25 = 0;
  if ( v213 )
  {
    pUnknown = v213;
    ((void (__fastcall *)(struct IUnknown *))v213->lpVtbl->AddRef)(v213);
    v25 = v24;
  }
  if ( v24 )
    ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
  if ( !v25 )
    _com_issue_error(-2147467261);
  v26 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/sendusing");
  if ( !v26 )
    _com_issue_error(-2147024882);
  v217.vt = 8;
  v217.llVal = (LONGLONG)v26;
  v27 = (struct IUnknown *)*Fields15::GetItem(v25, &v209, (__int128 *)&v217);
  if ( !v27 )
    _com_issue_error(-2147467261);
  pvarg.vt = 3;
  pvarg.lVal = 2;
  v219 = pvarg;
  v28 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v27->lpVtbl[4].Release)(v27, &v219);
  if ( v28 < 0 )
    _com_issue_errorex(v28, v27, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
  v29 = VariantClear(&pvarg);
  if ( v29 < 0 )
    _com_issue_error(v29);
  if ( v209 )
    (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
  v30 = VariantClear(&v217);
  if ( v30 < 0 )
    _com_issue_error(v30);
  v31 = pUnknown;
  if ( !pUnknown )
    _com_issue_error(-2147467261);
  v32 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpserver");
  if ( !v32 )
    _com_issue_error(-2147024882);
  v217.vt = 8;
  v217.llVal = (LONGLONG)v32;
  v33 = (struct IUnknown *)*Fields15::GetItem(v31, &v209, (__int128 *)&v217);
  if ( !v33 )
    _com_issue_error(-2147467261);
  v34 = SysAllocString(psz);
  if ( !v34 && psz )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v34;
  v219 = pvarg;
  v35 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v33->lpVtbl[4].Release)(v33, &v219);
  if ( v35 < 0 )
    _com_issue_errorex(v35, v33, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
  v36 = VariantClear(&pvarg);
  if ( v36 < 0 )
    _com_issue_error(v36);
  if ( v209 )
    (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
  v37 = VariantClear(&v217);
  if ( v37 < 0 )
    _com_issue_error(v37);
  v38 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpserverport");
  if ( !v38 )
    _com_issue_error(-2147024882);
  v217.vt = 8;
  v217.llVal = (LONGLONG)v38;
  v39 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
  if ( !v39 )
    _com_issue_error(-2147467261);
  pvarg.vt = 3;
  pvarg.lVal = a9;
  v219 = pvarg;
  v40 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v39->lpVtbl[4].Release)(v39, &v219);
  if ( v40 < 0 )
    _com_issue_errorex(v40, v39, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
  v41 = VariantClear(&pvarg);
  if ( v41 < 0 )
    _com_issue_error(v41);
  if ( v209 )
    (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
  v42 = VariantClear(&v217);
  if ( v42 < 0 )
    _com_issue_error(v42);
  v43 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpconnectiontimeout");
  if ( !v43 )
    _com_issue_error(-2147024882);
  v217.vt = 8;
  v217.llVal = (LONGLONG)v43;
  v44 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
  if ( !v44 )
    _com_issue_error(-2147467261);
  pvarg.vt = 3;
  pvarg.lVal = 10;
  v219 = pvarg;
  v45 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v44->lpVtbl[4].Release)(v44, &v219);
  if ( v45 < 0 )
    _com_issue_errorex(v45, v44, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
  v46 = VariantClear(&pvarg);
  if ( v46 < 0 )
    _com_issue_error(v46);
  if ( v209 )
    (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
  v47 = VariantClear(&v217);
  if ( v47 < 0 )
    _com_issue_error(v47);
  v48 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/urlgetlatestversion");
  if ( !v48 )
    _com_issue_error(-2147024882);
  v217.vt = 8;
  v217.llVal = (LONGLONG)v48;
  v49 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
  if ( !v49 )
    _com_issue_error(-2147467261);
  pvarg.vt = 2;
  pvarg.iVal = -1;
  v219 = pvarg;
  v50 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v49->lpVtbl[4].Release)(v49, &v219);
  if ( v50 < 0 )
    _com_issue_errorex(v50, v49, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
  v51 = VariantClear(&pvarg);
  if ( v51 < 0 )
    _com_issue_error(v51);
  if ( v209 )
    (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
  v52 = VariantClear(&v217);
  if ( v52 < 0 )
    _com_issue_error(v52);
  if ( a10 )
  {
    if ( a10 == 1 )
    {
      v58 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpauthenticate");
      if ( !v58 )
        _com_issue_error(-2147024882);
      v217.vt = 8;
      v217.llVal = (LONGLONG)v58;
      v59 = pUnknown;
      v60 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
      if ( !v60 )
        _com_issue_error(-2147467261);
      pvarg.vt = 3;
      pvarg.lVal = 1;
      v219 = pvarg;
      v61 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v60->lpVtbl[4].Release)(v60, &v219);
      if ( v61 < 0 )
        _com_issue_errorex(v61, v60, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
      v62 = VariantClear(&pvarg);
      if ( v62 < 0 )
        _com_issue_error(v62);
      if ( v209 )
        (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
      v63 = VariantClear(&v217);
      if ( v63 < 0 )
        _com_issue_error(v63);
      v64 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/sendusername");
      if ( !v64 )
        _com_issue_error(-2147024882);
      v217.vt = 8;
      v217.llVal = (LONGLONG)v64;
      v65 = (struct IUnknown *)*Fields15::GetItem(v59, &v209, (__int128 *)&v217);
      if ( !v65 )
        _com_issue_error(-2147467261);
      v66 = SysAllocString(a11);
      if ( !v66 && a11 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v66;
      v219 = pvarg;
      v67 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v65->lpVtbl[4].Release)(v65, &v219);
      if ( v67 < 0 )
        _com_issue_errorex(v67, v65, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
      v68 = VariantClear(&pvarg);
      if ( v68 < 0 )
        _com_issue_error(v68);
      if ( v209 )
        (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
      v69 = VariantClear(&v217);
      if ( v69 < 0 )
        _com_issue_error(v69);
      v70 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/sendpassword");
      if ( !v70 )
        _com_issue_error(-2147024882);
      v217.vt = 8;
      v217.llVal = (LONGLONG)v70;
      v71 = (struct IUnknown *)*Fields15::GetItem(v59, &v209, (__int128 *)&v217);
      if ( !v71 )
        _com_issue_error(-2147467261);
      v72 = SysAllocString(a12);
      if ( !v72 && a12 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v72;
      v219 = pvarg;
      v73 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v71->lpVtbl[4].Release)(v71, &v219);
      if ( v73 < 0 )
        _com_issue_errorex(v73, v71, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
      v74 = VariantClear(&pvarg);
      if ( v74 < 0 )
        _com_issue_error(v74);
      if ( v209 )
        (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
      v75 = VariantClear(&v217);
      if ( v75 < 0 )
        _com_issue_error(v75);
    }
    else if ( a10 == 2 )
    {
      v53 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpauthenticate");
      if ( !v53 )
        _com_issue_error(-2147024882);
      v217.vt = 8;
      v217.llVal = (LONGLONG)v53;
      v54 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
      if ( !v54 )
        _com_issue_error(-2147467261);
      pvarg.vt = 3;
      pvarg.lVal = 2;
      v219 = pvarg;
      v55 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v54->lpVtbl[4].Release)(v54, &v219);
      if ( v55 < 0 )
        _com_issue_errorex(v55, v54, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
      v56 = VariantClear(&pvarg);
      if ( v56 < 0 )
        _com_issue_error(v56);
      if ( v209 )
        (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
      v57 = VariantClear(&v217);
      if ( v57 < 0 )
        _com_issue_error(v57);
    }
  }
  else
  {
    v76 = SysAllocString(L"http://schemas.microsoft.com/cdo/configuration/smtpauthenticate");
    if ( !v76 )
      _com_issue_error(-2147024882);
    v217.vt = 8;
    v217.llVal = (LONGLONG)v76;
    v77 = (struct IUnknown *)*Fields15::GetItem(pUnknown, &v209, (__int128 *)&v217);
    if ( !v77 )
      _com_issue_error(-2147467261);
    pvarg.vt = 3;
    pvarg.lVal = 0;
    v219 = pvarg;
    v78 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v77->lpVtbl[4].Release)(v77, &v219);
    if ( v78 < 0 )
      _com_issue_errorex(v78, v77, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
    v79 = VariantClear(&pvarg);
    if ( v79 < 0 )
      _com_issue_error(v79);
    if ( v209 )
      (*((void (__fastcall **)(OLECHAR **))*v209 + 2))(v209);
    v80 = VariantClear(&v217);
    if ( v80 < 0 )
      _com_issue_error(v80);
  }
  v81 = pUnknown;
  v82 = ((__int64 (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl[4].Release)(pUnknown);
  if ( v82 < 0 )
    _com_issue_errorex(v82, v81, &GUID_00000564_0000_0010_8000_00aa006d2ea4);
  v83 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v84 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *))v216->lpVtbl[14].QueryInterface)(v216, v223);
  if ( v84 < 0 )
    _com_issue_errorex(v84, v83, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  v85 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v86 = _bstr_t::_bstr_t((_bstr_t *)&v209, a2);
  v210 = (struct IUnknown *)v86;
  if ( *(_QWORD *)v86 )
    v87 = **(_QWORD **)v86;
  else
    v87 = 0;
  v88 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v85->lpVtbl[10].Release)(v85, v87);
  if ( v88 < 0 )
    _com_issue_errorex(v88, v85, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v86);
  v89 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v90 = _bstr_t::_bstr_t((_bstr_t *)&v209, a1);
  v210 = (struct IUnknown *)v90;
  if ( *(_QWORD *)v90 )
    v91 = **(_QWORD **)v90;
  else
    v91 = 0;
  v92 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v89->lpVtbl[4].Release)(v89, v91);
  if ( v92 < 0 )
    _com_issue_errorex(v92, v89, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v90);
  v93 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v94 = _bstr_t::_bstr_t((_bstr_t *)&v209, a3);
  v210 = (struct IUnknown *)v94;
  if ( *(_QWORD *)v94 )
    v95 = **(_QWORD **)v94;
  else
    v95 = 0;
  v96 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v93->lpVtbl[10].QueryInterface)(v93, v95);
  if ( v96 < 0 )
    _com_issue_errorex(v96, v93, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v94);
  v97 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v219.vt = 2;
  v219.iVal = -1;
  v98 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v216->lpVtbl[6].QueryInterface)(v216, 0xFFFFFFFFLL);
  if ( v98 < 0 )
    _com_issue_errorex(v98, v97, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  v99 = VariantClear(&v219);
  if ( v99 < 0 )
    _com_issue_error(v99);
  v100 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v213 = 0;
  v101 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v216->lpVtbl[16].QueryInterface)(v216, &v213);
  if ( v101 < 0 )
    _com_issue_errorex(v101, v100, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  v102 = v213;
  v210 = v213;
  if ( !v213 )
    _com_issue_error(-2147467261);
  v103 = _bstr_t::_bstr_t((_bstr_t *)&v209, "utf-8");
  v224 = (struct IUnknown *)v103;
  if ( *(_QWORD *)v103 )
    v104 = **(_QWORD **)v103;
  else
    v104 = 0;
  v105 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v102->lpVtbl[4].Release)(v102, v104);
  if ( v105 < 0 )
    _com_issue_errorex(v105, v102, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v103);
  ((void (__fastcall *)(struct IUnknown *))v102->lpVtbl->Release)(v102);
  v106 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v213 = 0;
  v107 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v216->lpVtbl[16].QueryInterface)(v216, &v213);
  if ( v107 < 0 )
    _com_issue_errorex(v107, v106, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  v108 = v213;
  v210 = v213;
  v109 = 14;
  LODWORD(v213) = 14;
  if ( !v210 )
    _com_issue_error(-2147467261);
  v110 = _bstr_t::_bstr_t((_bstr_t *)&v209, "base64");
  v111 = v110;
  v224 = (struct IUnknown *)v110;
  if ( *(_QWORD *)v110 )
    v112 = **(_QWORD **)v110;
  else
    v112 = 0;
  v113 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v108->lpVtbl[3].QueryInterface)(v108, v112);
  if ( v113 < 0 )
    _com_issue_errorex(v113, v108, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v111);
  ((void (__fastcall *)(struct IUnknown *))v108->lpVtbl->Release)(v108);
  v114 = 0;
  v226 = 0;
  if ( v216 )
  {
    v212 = 0;
    v115 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v216->lpVtbl->QueryInterface)(
             v216,
             &GUID_cd000021_8b95_11d1_82db_00c04fb1625d,
             &v212);
    if ( v115 >= 0 )
    {
      v114 = v212;
      v226 = v212;
    }
    else
    {
      v226 = 0;
    }
  }
  else
  {
    v115 = -2147467262;
  }
  if ( (int)(v115 + 0x80000000) >= 0 && v115 != -2147467262 )
    _com_issue_error(v115);
  if ( !v114 )
    _com_issue_error(-2147467261);
  v116 = _bstr_t::_bstr_t((_bstr_t *)&v209, "multipart/mixed; charset=utf-8");
  v210 = (struct IUnknown *)v116;
  if ( *(_QWORD *)v116 )
    v117 = **(_QWORD **)v116;
  else
    v117 = 0;
  v118 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v114->lpVtbl[3].Release)(v114, v117);
  if ( v118 < 0 )
    _com_issue_errorex(v118, v114, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
  _bstr_t::~_bstr_t(v116);
  if ( a4 )
  {
    v119 = 0;
    v209 = 0;
    v120 = 0;
    v218 = 0;
    v212 = 0;
    v121 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v114->lpVtbl[7].AddRef)(
             v114,
             0xFFFFFFFFLL,
             &v212);
    if ( v121 < 0 )
      _com_issue_errorex(v121, v114, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    v122 = v212;
    v123 = 0;
    if ( v212 )
    {
      v119 = v212;
      v209 = (OLECHAR **)v212;
      ((void (__fastcall *)(struct IUnknown *))v212->lpVtbl->AddRef)(v212);
      v123 = v122;
    }
    if ( v122 )
      ((void (__fastcall *)(struct IUnknown *))v122->lpVtbl->Release)(v122);
    if ( !v123 )
      _com_issue_error(-2147467261);
    v124 = _bstr_t::_bstr_t((_bstr_t *)&v214, "text/plain");
    v125 = v124;
    v210 = (struct IUnknown *)v124;
    if ( *(_QWORD *)v124 )
      v126 = **(_QWORD **)v124;
    else
      v126 = 0;
    v127 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v123->lpVtbl[3].Release)(v123, v126);
    if ( v127 < 0 )
      _com_issue_errorex(v127, v123, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v125);
    v128 = _bstr_t::_bstr_t((_bstr_t *)v220, "utf-8");
    v129 = v128;
    v210 = (struct IUnknown *)v128;
    if ( *(_QWORD *)v128 )
      v130 = **(_QWORD **)v128;
    else
      v130 = 0;
    v131 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v123->lpVtbl[4].Release)(v123, v130);
    if ( v131 < 0 )
      _com_issue_errorex(v131, v123, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v129);
    v132 = _bstr_t::_bstr_t((_bstr_t *)&v214, "base64");
    v133 = v132;
    v210 = (struct IUnknown *)v132;
    if ( *(_QWORD *)v132 )
      v134 = **(_QWORD **)v132;
    else
      v134 = 0;
    v135 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v123->lpVtbl[3].QueryInterface)(v123, v134);
    if ( v135 < 0 )
      _com_issue_errorex(v135, v123, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v133);
    v212 = 0;
    v136 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v123->lpVtbl[8].AddRef)(v123, &v212);
    if ( v136 < 0 )
      _com_issue_errorex(v136, v123, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    v137 = v212;
    v109 = 62;
    LODWORD(v213) = 62;
    if ( v212 )
    {
      v120 = v212;
      v218 = v212;
      ((void (__fastcall *)(struct IUnknown *))v212->lpVtbl->AddRef)(v212);
    }
    if ( v137 )
      ((void (__fastcall *)(struct IUnknown *))v137->lpVtbl->Release)(v137);
    if ( !v120 )
      _com_issue_error(-2147467261);
    v138 = _bstr_t::_bstr_t((_bstr_t *)&v214, a4);
    v139 = v138;
    v210 = (struct IUnknown *)v138;
    if ( *(_QWORD *)v138 )
      v140 = **(_QWORD **)v138;
    else
      v140 = 0;
    v141 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v120->lpVtbl[10].AddRef)(v120, v140, 0);
    if ( v141 < 0 )
      _com_issue_errorex(v141, v120, &GUID_00000565_0000_0010_8000_00aa006d2ea4);
    _bstr_t::~_bstr_t(v139);
    v142 = ((__int64 (__fastcall *)(struct IUnknown *))v120->lpVtbl[9].QueryInterface)(v120);
    if ( v142 < 0 )
      _com_issue_errorex(v142, v120, &GUID_00000565_0000_0010_8000_00aa006d2ea4);
    ((void (__fastcall *)(struct IUnknown *))v120->lpVtbl->Release)(v120);
    if ( v119 )
      ((void (__fastcall *)(struct IUnknown *))v119->lpVtbl->Release)(v119);
  }
  if ( a5 )
  {
    v143 = _bstr_t::_bstr_t((_bstr_t *)&v209, "multipart/alternative; charset=utf-8");
    v144 = v143;
    v210 = (struct IUnknown *)v143;
    if ( *(_QWORD *)v143 )
      v145 = **(_QWORD **)v143;
    else
      v145 = 0;
    v146 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v114->lpVtbl[3].Release)(v114, v145);
    if ( v146 < 0 )
      _com_issue_errorex(v146, v114, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v144);
    v147 = 0;
    v209 = 0;
    v148 = 0;
    v218 = 0;
    v212 = 0;
    v149 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **))v114->lpVtbl[7].AddRef)(
             v114,
             0xFFFFFFFFLL,
             &v212);
    if ( v149 < 0 )
      _com_issue_errorex(v149, v114, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    v150 = v212;
    LODWORD(v213) = v109 | 0x40;
    v151 = 0;
    if ( v212 )
    {
      v147 = v212;
      v209 = (OLECHAR **)v212;
      ((void (__fastcall *)(struct IUnknown *))v212->lpVtbl->AddRef)(v212);
      v151 = v150;
    }
    if ( v150 )
      ((void (__fastcall *)(struct IUnknown *))v150->lpVtbl->Release)(v150);
    if ( !v151 )
      _com_issue_error(-2147467261);
    v152 = _bstr_t::_bstr_t((_bstr_t *)&v214, "text/html");
    v153 = v152;
    v210 = (struct IUnknown *)v152;
    if ( *(_QWORD *)v152 )
      v154 = **(_QWORD **)v152;
    else
      v154 = 0;
    v155 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v151->lpVtbl[3].Release)(v151, v154);
    if ( v155 < 0 )
      _com_issue_errorex(v155, v151, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v153);
    v156 = _bstr_t::_bstr_t((_bstr_t *)v220, "utf-8");
    v157 = v156;
    v210 = (struct IUnknown *)v156;
    if ( *(_QWORD *)v156 )
      v158 = **(_QWORD **)v156;
    else
      v158 = 0;
    v159 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v151->lpVtbl[4].Release)(v151, v158);
    if ( v159 < 0 )
      _com_issue_errorex(v159, v151, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v157);
    v160 = _bstr_t::_bstr_t((_bstr_t *)&v214, "base64");
    v161 = v160;
    v210 = (struct IUnknown *)v160;
    if ( *(_QWORD *)v160 )
      v162 = **(_QWORD **)v160;
    else
      v162 = 0;
    v163 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v151->lpVtbl[3].QueryInterface)(v151, v162);
    if ( v163 < 0 )
      _com_issue_errorex(v163, v151, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v161);
    v212 = 0;
    v164 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v151->lpVtbl[8].AddRef)(v151, &v212);
    if ( v164 < 0 )
      _com_issue_errorex(v164, v151, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    v165 = v212;
    LODWORD(v213) = (unsigned int)v213 | 0x80;
    if ( v212 )
    {
      v148 = v212;
      v218 = v212;
      ((void (__fastcall *)(struct IUnknown *))v212->lpVtbl->AddRef)(v212);
    }
    if ( v165 )
      ((void (__fastcall *)(struct IUnknown *))v165->lpVtbl->Release)(v165);
    if ( !v148 )
      _com_issue_error(-2147467261);
    v166 = _bstr_t::_bstr_t((_bstr_t *)&v214, a5);
    v167 = v166;
    v210 = (struct IUnknown *)v166;
    if ( *(_QWORD *)v166 )
      v168 = **(_QWORD **)v166;
    else
      v168 = 0;
    v169 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, _QWORD))v148->lpVtbl[10].AddRef)(v148, v168, 0);
    if ( v169 < 0 )
      _com_issue_errorex(v169, v148, &GUID_00000565_0000_0010_8000_00aa006d2ea4);
    _bstr_t::~_bstr_t(v167);
    v170 = ((__int64 (__fastcall *)(struct IUnknown *))v148->lpVtbl[9].QueryInterface)(v148);
    if ( v170 < 0 )
      _com_issue_errorex(v170, v148, &GUID_00000565_0000_0010_8000_00aa006d2ea4);
    ((void (__fastcall *)(struct IUnknown *))v148->lpVtbl->Release)(v148);
    if ( v147 )
      ((void (__fastcall *)(struct IUnknown *))v147->lpVtbl->Release)(v147);
  }
  if ( a6 )
  {
    v171 = 0;
    v227 = 0;
    v172 = v216;
    if ( !v216 )
      _com_issue_error(-2147467261);
    v210 = (struct IUnknown *)&v209;
    v218 = (struct IUnknown *)_bstr_t::_bstr_t((_bstr_t *)&v209, &Class);
    v224 = v218;
    v212 = (struct IUnknown *)&v214;
    v173 = _bstr_t::_bstr_t((_bstr_t *)&v214, &Class);
    v228 = v173;
    v174 = _bstr_t::_bstr_t((_bstr_t *)v220, a6);
    v175 = v174;
    v222 = (struct IUnknown *)v174;
    v212 = 0;
    if ( v218->lpVtbl )
      QueryInterface = v218->lpVtbl->QueryInterface;
    else
      QueryInterface = 0;
    if ( *(_QWORD *)v173 )
      v177 = **(_QWORD **)v173;
    else
      v177 = 0;
    if ( *(_QWORD *)v174 )
      v178 = **(_QWORD **)v174;
    else
      v178 = 0;
    v179 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, HRESULT (__stdcall *)(IUnknown *, const IID *const, void **), struct IUnknown **))v172->lpVtbl[18].QueryInterface)(
             v172,
             v178,
             v177,
             QueryInterface,
             &v212);
    if ( v179 < 0 )
      _com_issue_errorex(v179, v172, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
    v180 = v212;
    LODWORD(v213) = (unsigned int)v213 | 0x100;
    _bstr_t::~_bstr_t(v175);
    _bstr_t::~_bstr_t(v173);
    _bstr_t::~_bstr_t((_bstr_t *)v218);
    if ( v180 )
    {
      v171 = v180;
      v227 = v180;
      ((void (__fastcall *)(struct IUnknown *))v180->lpVtbl->AddRef)(v180);
      ((void (__fastcall *)(struct IUnknown *))v180->lpVtbl->Release)(v180);
    }
    if ( !v171 )
      _com_issue_error(-2147467261);
    v181 = _bstr_t::_bstr_t((_bstr_t *)&v209, L"image/tif");
    v222 = (struct IUnknown *)v181;
    if ( *(_QWORD *)v181 )
      v182 = **(_QWORD **)v181;
    else
      v182 = 0;
    v183 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v171->lpVtbl[3].Release)(v171, v182);
    if ( v183 < 0 )
      _com_issue_errorex(v183, v171, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
    _bstr_t::~_bstr_t(v181);
    if ( a5 )
    {
      v184 = _bstr_t::_bstr_t((_bstr_t *)&v209, "multipart/mixed; charset=utf-8");
      v222 = (struct IUnknown *)v184;
      if ( *(_QWORD *)v184 )
        v185 = **(_QWORD **)v184;
      else
        v185 = 0;
      v186 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v114->lpVtbl[3].Release)(v114, v185);
      if ( v186 < 0 )
        _com_issue_errorex(v186, v114, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
      _bstr_t::~_bstr_t(v184);
    }
    if ( a7 )
    {
      v218 = 0;
      v187 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v171->lpVtbl[4].QueryInterface)(
               v171,
               &v218);
      if ( v187 < 0 )
        _com_issue_errorex(v187, v171, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
      v188 = v218;
      v222 = v218;
      v218 = 0;
      v189 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v171->lpVtbl[3].AddRef)(v171, &v218);
      if ( v189 < 0 )
        _com_issue_errorex(v189, v171, &GUID_cd000021_8b95_11d1_82db_00c04fb1625d);
      v190 = v218;
      v191 = (struct IUnknown **)operator new(0x18u);
      v228 = (_bstr_t *)v191;
      if ( v191 )
      {
        v191[1] = 0;
        *((_DWORD *)v191 + 4) = 1;
        *v191 = v190;
      }
      else
      {
        v191 = 0;
      }
      v214 = v191;
      if ( !v191 )
        _com_issue_error(-2147024882);
      _bstr_t::_bstr_t((_bstr_t *)v220, L"; name=\"");
      v192 = _bstr_t::operator+(&v214, &v210, v220);
      _bstr_t::_bstr_t((_bstr_t *)&v213, a7);
      v193 = _bstr_t::operator+(v192, &v224, &v213);
      _bstr_t::_bstr_t((_bstr_t *)&v212, L"\"");
      _bstr_t::operator+(v193, &v209, &v212);
      _bstr_t::~_bstr_t((_bstr_t *)&v212);
      _bstr_t::~_bstr_t((_bstr_t *)&v224);
      _bstr_t::~_bstr_t((_bstr_t *)&v213);
      _bstr_t::~_bstr_t((_bstr_t *)&v210);
      _bstr_t::~_bstr_t((_bstr_t *)v220);
      _bstr_t::~_bstr_t((_bstr_t *)&v214);
      if ( !v188 )
        _com_issue_error(-2147467261);
      v194 = SysAllocString(L"urn:schemas:mailheader:content-type");
      if ( !v194 )
        _com_issue_error(-2147024882);
      v217.vt = 8;
      v217.llVal = (LONGLONG)v194;
      v195 = (struct IUnknown *)*Fields15::GetItem(v188, &v214, (__int128 *)&v217);
      if ( !v195 )
        _com_issue_error(-2147467261);
      if ( v209 )
        v196 = *v209;
      else
        v196 = 0;
      v197 = SysStringByteLen(v196);
      v198 = SysAllocStringByteLen((LPCSTR)v196, v197);
      if ( !v198 )
        _com_issue_error(-2147024882);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v198;
      v219 = pvarg;
      v199 = ((__int64 (__fastcall *)(struct IUnknown *, VARIANTARG *))v195->lpVtbl[4].Release)(v195, &v219);
      if ( v199 < 0 )
        _com_issue_errorex(v199, v195, &GUID_0000054c_0000_0010_8000_00aa006d2ea4);
      v200 = VariantClear(&pvarg);
      if ( v200 < 0 )
        _com_issue_error(v200);
      if ( v214 )
        ((void (__fastcall *)(struct IUnknown **))(*v214)[2].lpVtbl)(v214);
      v201 = VariantClear(&v217);
      if ( v201 < 0 )
        _com_issue_error(v201);
      v202 = ((__int64 (__fastcall *)(struct IUnknown *))v188->lpVtbl[4].Release)(v188);
      if ( v202 < 0 )
        _com_issue_errorex(v202, v188, &GUID_00000564_0000_0010_8000_00aa006d2ea4);
      v203 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v188->lpVtbl[5].QueryInterface)(v188, 2);
      if ( v203 < 0 )
        _com_issue_errorex(v203, v188, &GUID_00000564_0000_0010_8000_00aa006d2ea4);
      _bstr_t::~_bstr_t((_bstr_t *)&v209);
      ((void (__fastcall *)(struct IUnknown *))v188->lpVtbl->Release)(v188);
    }
    ((void (__fastcall *)(struct IUnknown *))v171->lpVtbl->Release)(v171);
  }
  if ( a10 == 2 )
  {
    if ( !hToken )
    {
      v17 = -2147024809;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_4b0f9bf04b2337a3602c77c835f6eba7_Traceguids,
          2147942487LL);
      }
      ((void (__fastcall *)(struct IUnknown *))v114->lpVtbl->Release)(v114);
      ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
      if ( v223 )
        ((void (__fastcall *)(struct IUnknown *))v223->lpVtbl->Release)(v223);
      if ( v216 )
        ((void (__fastcall *)(struct IUnknown *))v216->lpVtbl->Release)(v216);
LABEL_286:
      CoUninitialize();
      return v17;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_4b0f9bf04b2337a3602c77c835f6eba7_Traceguids, v17);
      }
      ((void (__fastcall *)(struct IUnknown *))v114->lpVtbl->Release)(v114);
      ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
      if ( v223 )
        ((void (__fastcall *)(struct IUnknown *))v223->lpVtbl->Release)(v223);
      if ( v216 )
        ((void (__fastcall *)(struct IUnknown *))v216->lpVtbl->Release)(v216);
      goto LABEL_286;
    }
    v225 = 1;
  }
  v205 = v216;
  if ( !v216 )
    _com_issue_error(-2147467261);
  v206 = ((__int64 (__fastcall *)(struct IUnknown *))v216->lpVtbl[20].AddRef)(v216);
  if ( v206 < 0 )
    _com_issue_errorex(v206, v205, &GUID_cd000020_8b95_11d1_82db_00c04fb1625d);
  ((void (__fastcall *)(struct IUnknown *))v114->lpVtbl->Release)(v114);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  if ( v223 )
    ((void (__fastcall *)(struct IUnknown *))v223->lpVtbl->Release)(v223);
  if ( v216 )
    ((void (__fastcall *)(struct IUnknown *))v216->lpVtbl->Release)(v216);
  v17 = v221;
  CoUninitialize();
  if ( v225 && !RevertToSelf() )
  {
    v207 = GetLastError();
    v17 = v207;
    if ( v207 > 0 )
      v17 = (unsigned __int16)v207 | 0x80070000;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = 15;
      goto LABEL_314;
    }
  }
  return v17;
}

```

## disassembly

```asm
0x140076bac  mov     [rsp+arg_18], r9
0x140076bb1  mov     [rsp+arg_10], r8
0x140076bb6  mov     [rsp+arg_8], rdx
0x140076bbb  push    rbx
0x140076bbc  push    rsi
0x140076bbd  push    rdi
0x140076bbe  push    r12
0x140076bc0  push    r13
0x140076bc2  push    r14
0x140076bc4  push    r15
0x140076bc6  sub     rsp, 120h
0x140076bcd  mov     r15, r8
0x140076bd0  mov     rsi, rdx
0x140076bd3  mov     r12, rcx
0x140076bd6  xor     r14d, r14d
0x140076bd9  mov     [rsp+158h+arg_68], r14d
0x140076be1  lea     r13, WPP_GLOBAL_Control
0x140076be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140076bef  lea     edi, [r14+2]
0x140076bf3  cmp     rcx, r13
0x140076bf6  jz      short loc_140076C17
0x140076bf8  test    [rcx+1Ch], dil
0x140076bfc  jz      short loc_140076C17
0x140076bfe  cmp     byte ptr [rcx+19h], 5
0x140076c02  jb      short loc_140076C17
0x140076c04  lea     edx, [rdi+8]
0x140076c07  lea     r8, WPP_4b0f9bf04b2337a3602c77c835f6eba7_Traceguids
0x140076c0e  mov     rcx, [rcx+10h]
0x140076c12  call    WPP_SF_
0x140076c17  mov     [rsp+158h+var_60], r14d
0x140076c1f  mov     edx, edi; dwCoInit
0x140076c21  xor     ecx, ecx; pvReserved
0x140076c23  call    cs:__imp_CoInitializeEx
0x140076c29  mov     ebx, r14d
0x140076c2c  cmp     eax, 1
0x140076c2f  cmovnz  ebx, eax
0x140076c32  mov     [rsp+158h+var_80], ebx
0x140076c39  test    ebx, ebx
0x140076c3b  jns     short loc_140076C6B
0x140076c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c44  cmp     rcx, r13
0x140076c47  jz      loc_140078835
0x140076c4d  test    [rcx+1Ch], dil
0x140076c51  jz      loc_140078835
0x140076c57  cmp     [rcx+19h], dil
0x140076c5b  jb      loc_140078835
0x140076c61  mov     edx, 0Bh
0x140076c66  jmp     loc_140078822
0x140076c6b  mov     [rsp+158h+var_D0], r14
0x140076c73  mov     [rsp+158h+pUnknown], r14
0x140076c78  lea     rax, [rsp+158h+pUnknown]
0x140076c7d  mov     [rsp+158h+ppv], rax; ppv
0x140076c82  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140076c89  xor     edx, edx; pUnkOuter
0x140076c8b  lea     r8d, [rdx+17h]; dwClsContext
0x140076c8f  lea     rcx, _GUID_cd000001_8b95_11d1_82db_00c04fb1625d; rclsid
0x140076c96  call    cs:__imp_CoCreateInstance
0x140076c9c  mov     ebx, eax
0x140076c9e  test    eax, eax
0x140076ca0  js      short loc_140076CE6
0x140076ca2  mov     rcx, [rsp+158h+pUnknown]; pUnknown
0x140076ca7  call    cs:__imp_OleRun
0x140076cad  mov     ebx, eax
0x140076caf  test    eax, eax
0x140076cb1  js      short loc_140076CD4
0x140076cb3  mov     rcx, [rsp+158h+pUnknown]
0x140076cb8  mov     rax, [rcx]
0x140076cbb  lea     r8, [rsp+158h+var_D0]
0x140076cc3  lea     rdx, _GUID_cd000020_8b95_11d1_82db_00c04fb1625d
0x140076cca  mov     rax, [rax]
0x140076ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076cd2  mov     ebx, eax
0x140076cd4  mov     rcx, [rsp+158h+pUnknown]
0x140076cd9  mov     rax, [rcx]
0x140076cdc  mov     rax, [rax+10h]
0x140076ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076ce5  nop
0x140076ce6  mov     ecx, 80000000h
0x140076ceb  lea     eax, [rbx+rcx]
0x140076cee  mov     r13d, 80004002h
0x140076cf4  test    ecx, eax
0x140076cf6  jnz     short loc_140076D01
0x140076cf8  cmp     ebx, r13d
0x140076cfb  jnz     loc_14007884A
0x140076d01  mov     [rsp+158h+var_70], r14
0x140076d09  mov     [rsp+158h+pUnknown], r14
0x140076d0e  lea     rax, [rsp+158h+pUnknown]
0x140076d13  mov     [rsp+158h+ppv], rax; ppv
0x140076d18  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140076d1f  xor     edx, edx; pUnkOuter
0x140076d21  lea     r8d, [rdx+17h]; dwClsContext
0x140076d25  lea     rcx, _GUID_cd000002_8b95_11d1_82db_00c04fb1625d; rclsid
0x140076d2c  call    cs:__imp_CoCreateInstance
0x140076d32  mov     ebx, eax
0x140076d34  test    eax, eax
0x140076d36  js      short loc_140076D7C
0x140076d38  mov     rcx, [rsp+158h+pUnknown]; pUnknown
0x140076d3d  call    cs:__imp_OleRun
0x140076d43  mov     ebx, eax
0x140076d45  test    eax, eax
0x140076d47  js      short loc_140076D6A
0x140076d49  mov     rcx, [rsp+158h+pUnknown]
0x140076d4e  mov     rax, [rcx]
0x140076d51  lea     r8, [rsp+158h+var_70]
0x140076d59  lea     rdx, _GUID_cd000022_8b95_11d1_82db_00c04fb1625d
0x140076d60  mov     rax, [rax]
0x140076d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076d68  mov     ebx, eax
0x140076d6a  mov     rcx, [rsp+158h+pUnknown]
0x140076d6f  mov     rax, [rcx]
0x140076d72  mov     rax, [rax+10h]
0x140076d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076d7b  nop
0x140076d7c  mov     ecx, 80000000h
0x140076d81  lea     eax, [rbx+rcx]
0x140076d84  test    ecx, eax
0x140076d86  jnz     short loc_140076D91
0x140076d88  cmp     ebx, r13d
0x140076d8b  jnz     loc_140078852
0x140076d91  mov     [rsp+158h+pUnknown], r14
0x140076d96  mov     rbx, [rsp+158h+var_70]
0x140076d9e  test    rbx, rbx
0x140076da1  jz      loc_14007885A
0x140076da7  mov     [rsp+158h+var_F8], r14
0x140076dac  mov     rax, [rbx]
0x140076daf  lea     rdx, [rsp+158h+var_F8]
0x140076db4  mov     rcx, rbx
0x140076db7  mov     rax, [rax+38h]
0x140076dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076dc0  test    eax, eax
0x140076dc2  js      loc_140078864
0x140076dc8  mov     rbx, [rsp+158h+var_F8]
0x140076dcd  mov     [rsp+158h+arg_68], edi
0x140076dd4  mov     rdi, r14
0x140076dd7  test    rbx, rbx
0x140076dda  jz      short loc_140076DF4
0x140076ddc  mov     [rsp+158h+pUnknown], rbx
0x140076de1  mov     rax, [rbx]
0x140076de4  mov     rcx, rbx
0x140076de7  mov     rax, [rax+8]
0x140076deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076df0  nop
0x140076df1  mov     rdi, rbx
0x140076df4  test    rbx, rbx
0x140076df7  jz      short loc_140076E09
0x140076df9  mov     rax, [rbx]
0x140076dfc  mov     rcx, rbx
0x140076dff  mov     rax, [rax+10h]
0x140076e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076e08  nop
0x140076e09  test    rdi, rdi
0x140076e0c  jz      loc_140078875
0x140076e12  lea     rcx, psz; "http://schemas.microsoft.com/cdo/config"...
0x140076e19  call    cs:__imp_SysAllocString
0x140076e1f  test    rax, rax
0x140076e22  jz      loc_14007887F
0x140076e28  mov     ecx, 8
0x140076e2d  mov     word ptr [rsp+158h+var_C8], cx
0x140076e35  mov     qword ptr [rsp+158h+var_C8+8], rax
0x140076e3d  lea     r8, [rsp+158h+var_C8]
0x140076e45  lea     rdx, [rsp+158h+var_118]
0x140076e4a  mov     rcx, rdi; struct IUnknown *
0x140076e4d  call    ?GetItem@Fields15@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UField@@$1?_GUID_00000569_0000_0010_8000_00aa006d2ea4@@3U__s_GUID@@B@@@@AEBV_variant_t@@@Z; Fields15::GetItem(_variant_t const &)
0x140076e52  nop
0x140076e53  mov     rbx, [rax]
0x140076e56  test    rbx, rbx
0x140076e59  jz      loc_14007888A
0x140076e5f  mov     eax, 3
0x140076e64  mov     word ptr [rsp+158h+pvarg], ax
0x140076e69  lea     edi, [rax-1]
0x140076e6c  mov     dword ptr [rsp+158h+pvarg+8], edi
0x140076e70  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x140076e75  movaps  xmmword ptr [rsp+158h+var_A8], xmm0
0x140076e7d  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x140076e86  movsd   qword ptr [rsp+158h+var_A8+10h], xmm1
0x140076e8f  mov     rax, [rbx]
0x140076e92  lea     rdx, [rsp+158h+var_A8]
0x140076e9a  mov     rcx, rbx
0x140076e9d  mov     rax, [rax+70h]
0x140076ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076ea6  test    eax, eax
0x140076ea8  js      loc_140078895
0x140076eae  lea     rcx, [rsp+158h+pvarg]; pvarg
0x140076eb3  call    cs:__imp_VariantClear
0x140076eb9  test    eax, eax
0x140076ebb  js      loc_1400788A7
0x140076ec1  mov     rcx, [rsp+158h+var_118]
0x140076ec6  test    rcx, rcx
0x140076ec9  jz      short loc_140076ED8
0x140076ecb  mov     rax, [rcx]
0x140076ece  mov     rax, [rax+10h]
0x140076ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076ed7  nop
0x140076ed8  lea     rcx, [rsp+158h+var_C8]; pvarg
0x140076ee0  call    cs:__imp_VariantClear
0x140076ee6  test    eax, eax
0x140076ee8  js      loc_1400788AF
0x140076eee  mov     rbx, [rsp+158h+pUnknown]
0x140076ef3  test    rbx, rbx
0x140076ef6  jz      loc_1400788B7
0x140076efc  lea     rcx, aHttpSchemasMic_0; "http://schemas.microsoft.com/cdo/config"...
0x140076f03  call    cs:__imp_SysAllocString
0x140076f09  test    rax, rax
0x140076f0c  jz      loc_1400788C1
0x140076f12  mov     ecx, 8
0x140076f17  mov     word ptr [rsp+158h+var_C8], cx
0x140076f1f  mov     qword ptr [rsp+158h+var_C8+8], rax
0x140076f27  lea     r8, [rsp+158h+var_C8]
0x140076f2f  lea     rdx, [rsp+158h+var_118]
0x140076f34  mov     rcx, rbx; struct IUnknown *
0x140076f37  call    ?GetItem@Fields15@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UField@@$1?_GUID_00000569_0000_0010_8000_00aa006d2ea4@@3U__s_GUID@@B@@@@AEBV_variant_t@@@Z; Fields15::GetItem(_variant_t const &)
0x140076f3c  nop
0x140076f3d  mov     rbx, [rax]
0x140076f40  test    rbx, rbx
0x140076f43  jz      loc_1400788CC
0x140076f49  mov     rcx, [rsp+158h+psz]; psz
0x140076f51  call    cs:__imp_SysAllocString
0x140076f57  test    rax, rax
0x140076f5a  jnz     short loc_140076F6A
0x140076f5c  cmp     [rsp+158h+psz], r14
0x140076f64  jnz     loc_1400788D6
0x140076f6a  mov     ecx, 8
0x140076f6f  mov     word ptr [rsp+158h+pvarg], cx
0x140076f74  mov     qword ptr [rsp+158h+pvarg+8], rax
0x140076f79  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x140076f7e  movaps  xmmword ptr [rsp+158h+var_A8], xmm0
0x140076f86  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x140076f8f  movsd   qword ptr [rsp+158h+var_A8+10h], xmm1
0x140076f98  mov     rax, [rbx]
0x140076f9b  lea     rdx, [rsp+158h+var_A8]
0x140076fa3  mov     rcx, rbx
0x140076fa6  mov     rax, [rax+70h]
0x140076faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076faf  test    eax, eax
0x140076fb1  js      loc_1400788E1
0x140076fb7  lea     rcx, [rsp+158h+pvarg]; pvarg
0x140076fbc  call    cs:__imp_VariantClear
0x140076fc2  test    eax, eax
0x140076fc4  js      loc_1400788F3
0x140076fca  mov     rcx, [rsp+158h+var_118]
0x140076fcf  test    rcx, rcx
0x140076fd2  jz      short loc_140076FE1
0x140076fd4  mov     rax, [rcx]
0x140076fd7  mov     rax, [rax+10h]
0x140076fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076fe0  nop
0x140076fe1  lea     rcx, [rsp+158h+var_C8]; pvarg
0x140076fe9  call    cs:__imp_VariantClear
0x140076fef  test    eax, eax
0x140076ff1  js      loc_1400788FB
0x140076ff7  lea     rcx, aHttpSchemasMic_6; "http://schemas.microsoft.com/cdo/config"...
0x140076ffe  call    cs:__imp_SysAllocString
0x140077004  test    rax, rax
0x140077007  jz      loc_140078903
0x14007700d  mov     ecx, 8
0x140077012  mov     word ptr [rsp+158h+var_C8], cx
0x14007701a  mov     qword ptr [rsp+158h+var_C8+8], rax
0x140077022  lea     r8, [rsp+158h+var_C8]
0x14007702a  lea     rdx, [rsp+158h+var_118]
0x14007702f  mov     rcx, [rsp+158h+pUnknown]; struct IUnknown *
0x140077034  call    ?GetItem@Fields15@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UField@@$1?_GUID_00000569_0000_0010_8000_00aa006d2ea4@@3U__s_GUID@@B@@@@AEBV_variant_t@@@Z; Fields15::GetItem(_variant_t const &)
0x140077039  nop
0x14007703a  mov     rbx, [rax]
0x14007703d  test    rbx, rbx
0x140077040  jz      loc_14007890E
0x140077046  mov     eax, 3
0x14007704b  mov     word ptr [rsp+158h+pvarg], ax
0x140077050  movzx   eax, word ptr [rsp+158h+arg_40]
0x140077058  mov     word ptr [rsp+158h+pvarg+8], ax
0x14007705d  movzx   eax, word ptr [rsp+158h+arg_40+2]
0x140077065  mov     word ptr [rsp+158h+pvarg+0Ah], ax
0x14007706a  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x14007706f  movaps  xmmword ptr [rsp+158h+var_A8], xmm0
0x140077077  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x140077080  movsd   qword ptr [rsp+158h+var_A8+10h], xmm1
0x140077089  mov     rax, [rbx]
0x14007708c  lea     rdx, [rsp+158h+var_A8]
0x140077094  mov     rcx, rbx
0x140077097  mov     rax, [rax+70h]
0x14007709b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400770a0  test    eax, eax
0x1400770a2  js      loc_140078919
0x1400770a8  lea     rcx, [rsp+158h+pvarg]; pvarg
0x1400770ad  call    cs:__imp_VariantClear
0x1400770b3  test    eax, eax
0x1400770b5  js      loc_14007892B
0x1400770bb  mov     rcx, [rsp+158h+var_118]
0x1400770c0  test    rcx, rcx
0x1400770c3  jz      short loc_1400770D2
0x1400770c5  mov     rax, [rcx]
0x1400770c8  mov     rax, [rax+10h]
0x1400770cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400770d1  nop
0x1400770d2  lea     rcx, [rsp+158h+var_C8]; pvarg
0x1400770da  call    cs:__imp_VariantClear
0x1400770e0  test    eax, eax
0x1400770e2  js      loc_140078933
0x1400770e8  lea     rcx, aHttpSchemasMic_2; "http://schemas.microsoft.com/cdo/config"...
0x1400770ef  call    cs:__imp_SysAllocString
0x1400770f5  test    rax, rax
  ... truncated ...
```
