# UiaNode::ProviderGetPropertyValue(int,int,IRawElementProviderSimple *,int,PropertyInfo const *,tagVARIANT *)

- ea: `0x1800bf960`
- end: `0x1800c0e2a`
- name: `?ProviderGetPropertyValue@UiaNode@@AEAAJHHPEAUIRawElementProviderSimple@@HPEBUPropertyInfo@@PEAUtagVARIANT@@@Z`
- size: `5322`
- prototype: `__int64 __usercall@<rax>(UiaNode *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct IRawElementProviderSimple *@<r9>, int, const struct PropertyInfo *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bed0c`
- `0x1800bf47c`
- `0x1800bf6e0`

## callees

- `0x18000d410`
- `0x18000f680`
- `0x18002f2f0`
- `0x18002f580`
- `0x1800320ec`
- `0x1800b8210`
- `0x1800be9c8`
- `0x1800bf960`
- `0x1800c0e30`
- `0x1800c1080`
- `0x1800c1c70`
- `0x1800c2068`
- `0x1800c20c0`
- `0x1800c20ec`
- `0x1800c3480`
- `0x1800d9490`
- `0x18016df80`
- `0x1801759f0`
- `0x180186cd0`
- `0x180197df8`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x18023bb74`
- `0x18023c8ec`
- `0x18023d2f4`
- `0x18023d3f0`
- `0x18026cec0`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfec6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bfec6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0b0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c04ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c04ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c0242`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c0242`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c0208`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c0208`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bfc47`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bfc47`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bfc5d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bfc5d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bfbc7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bfbc7`
- `OLEAUT32!__imp_VariantInit` at `0x1800bfa3e`
- `OLEAUT32!__imp_VariantInit` at `0x1800bff15`
- `OLEAUT32!__imp_VariantInit` at `0x1800c07b1`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0809`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0b99`
- `OLEAUT32!__imp_VariantInit` at `0x1800bfa3e`
- `OLEAUT32!__imp_VariantInit` at `0x1800bff15`
- `OLEAUT32!__imp_VariantInit` at `0x1800c07b1`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0809`
- `OLEAUT32!__imp_VariantInit` at `0x1800c0b99`
- `OLEAUT32!__imp_VariantClear` at `0x1800bfb86`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0727`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0863`
- `OLEAUT32!__imp_VariantClear` at `0x1800c086f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0bf4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c3d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c4f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c7e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0cc4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0cf6`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d02`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d34`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d40`
- `OLEAUT32!__imp_VariantClear` at `0x1800bfb86`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0727`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0863`
- `OLEAUT32!__imp_VariantClear` at `0x1800c086f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0bf4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c3d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c4f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0c7e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0cc4`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0cf6`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d02`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d34`
- `OLEAUT32!__imp_VariantClear` at `0x1800c0d40`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c0117`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c030e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c03ef`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c0117`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c030e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c03ef`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800bfdd3`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800bfdd3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800bfe49`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800bfe49`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800bfe2a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800bfe2a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800bfe71`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800bfe71`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0107`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c02c6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0679`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0107`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c02c6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c0679`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800bfdf2`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800bfdf2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c0d76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c0d76`

## string_xrefs

- `0x1800c0348`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c0643`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c065a`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800bfb28`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0372`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0473`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c08af`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0a2f`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0b28`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0bdd`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0c26`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0c67`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0cad`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0cdc`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0d1a`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0d8d`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c0ddf`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall UiaNode::ProviderGetPropertyValue(
        UiaNode *this,
        unsigned int a2,
        unsigned int a3,
        struct IRawElementProviderSimple *a4,
        int a5,
        const struct PropertyInfo *a6,
        struct tagVARIANT *pvarg)
{
  __int64 v7; // r12
  __int64 v8; // r8
  unsigned int v10; // ecx
  int v11; // ebx
  unsigned int v12; // ebx
  __int64 *i; // rdx
  const struct ProviderEntryPoint *v14; // r14
  __int16 v15; // si
  struct IUnknown *v16; // r12
  OLECHAR *bstrVal; // rcx
  int v18; // edi
  __int64 result; // rax
  int PointPropertyInScreenCoordinates; // eax
  unsigned int v21; // ebx
  UINT v22; // eax
  BSTR v23; // rdx
  unsigned __int64 v24; // r8
  __int64 v25; // rcx
  BSTR v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rdx
  unsigned int (__fastcall ***v29)(_QWORD, GUID *, LONG *); // rbx
  __int64 v30; // rcx
  int RuntimeIdFromProviderEntryPoint; // eax
  unsigned int RuntimeIdFromPartial; // edi
  int v33; // ecx
  struct IRawElementProviderFragment *v34; // rbx
  int v35; // ecx
  int v36; // edi
  HRESULT Vartype; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned __int64 v40; // rax
  int *v41; // rsi
  GUID **v42; // rbx
  unsigned int v43; // r14d
  __int64 v44; // rdi
  struct IUnknown *v45; // rsi
  int v46; // ecx
  int PropertyForUserRegisteredPattern; // edi
  SAFEARRAY *v48; // rcx
  int v49; // eax
  struct ITableProvider *v50; // rcx
  void (*v51)(int, void *); // rax
  int RuntimeId; // ebx
  SAFEARRAY *v53; // rcx
  struct UiaClientState *v54; // rdx
  LPVOID v56; // rax
  unsigned int v57; // r8d
  LONG j; // edi
  SAFEARRAY *v59; // rcx
  int BoundingRectangleInScreenCoordinates; // eax
  unsigned int v61; // ebx
  __int64 v62; // rdi
  int v63; // ecx
  int v64; // ebx
  LONG CurrentProcessId; // eax
  LPVOID v66; // rsi
  __int64 v67; // rdx
  __int64 v68; // r9
  int v69; // eax
  unsigned int v70; // ebx
  int v71; // eax
  unsigned int v72; // ebx
  int v73; // eax
  unsigned int v74; // ebx
  int PatternProvider_MSAALegacy; // eax
  struct UserDefinedPatternInfo *k; // rax
  int v77; // edi
  int PropertyValue; // eax
  unsigned int v79; // ebx
  int v80; // eax
  unsigned int v81; // ebx
  int v82; // eax
  unsigned int v83; // ebx
  HRESULT v84; // eax
  unsigned int v85; // ebx
  int v86; // eax
  unsigned int v87; // ebx
  int lpString2; // [rsp+20h] [rbp-1C8h]
  int lpString2a; // [rsp+20h] [rbp-1C8h]
  int lpString2g; // [rsp+20h] [rbp-1C8h]
  int lpString2b; // [rsp+20h] [rbp-1C8h]
  int lpString2c; // [rsp+20h] [rbp-1C8h]
  int lpString2d; // [rsp+20h] [rbp-1C8h]
  int lpString2e; // [rsp+20h] [rbp-1C8h]
  int lpString2f; // [rsp+20h] [rbp-1C8h]
  VARTYPE pvt[2]; // [rsp+30h] [rbp-1B8h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-1B0h] BYREF
  unsigned int v98; // [rsp+40h] [rbp-1A8h]
  int v99; // [rsp+44h] [rbp-1A4h]
  VARIANTARG v100; // [rsp+48h] [rbp-1A0h] BYREF
  LONG plLbound[2]; // [rsp+60h] [rbp-188h] BYREF
  __int64 v102; // [rsp+68h] [rbp-180h]
  LONG plUbound[2]; // [rsp+70h] [rbp-178h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-170h] BYREF
  unsigned int v105; // [rsp+80h] [rbp-168h]
  int v106; // [rsp+84h] [rbp-164h]
  VARIANTARG v107; // [rsp+88h] [rbp-160h] BYREF
  WCHAR ClassName[128]; // [rsp+A0h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  try
  {
    ppv = a4;
    v7 = a3;
    v8 = a2;
    *(_DWORD *)pvt = a2;
    *(_QWORD *)&v107.vt = a6;
    pvarg->vt = 0;
    v10 = *((_DWORD *)this + 60);
    if ( (unsigned int)v7 >= v10 || (unsigned int)v7 >= 6 )
      goto LABEL_6;
    if ( *((_DWORD *)this + 6 * v7 + 27) != 6 )
    {
      v8 = a2;
LABEL_6:
      v11 = *((_DWORD *)a6 + 6);
      if ( !v11 )
      {
        v12 = a5;
        if ( a5 == 30001 )
        {
          BoundingRectangleInScreenCoordinates = UiaNode::GetBoundingRectangleInScreenCoordinates(
                                                   this,
                                                   (_DWORD)v8 != 0,
                                                   a4,
                                                   pvarg);
          v61 = BoundingRectangleInScreenCoordinates;
          if ( BoundingRectangleInScreenCoordinates >= 0 )
            return 0;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x935,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            (const char *)(unsigned int)BoundingRectangleInScreenCoordinates,
            lpString2);
          return v61;
        }
        for ( i = UiaUtils::s_pointProperties; i != (__int64 *)L"Chrome_RenderWidgetHostHWND"; ++i )
        {
          if ( *((_DWORD *)i + 1) == a5 )
          {
            LOBYTE(v8) = (_DWORD)v8 != 0;
            PointPropertyInScreenCoordinates = UiaNode::GetPointPropertyInScreenCoordinates(
                                                 this,
                                                 *(unsigned int *)i,
                                                 v8);
            v21 = PointPropertyInScreenCoordinates;
            if ( PointPropertyInScreenCoordinates >= 0 )
              return 0;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x93D,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
              (const char *)(unsigned int)PointPropertyInScreenCoordinates,
              (int)pvarg);
            return v21;
          }
        }
        if ( a5 != 30000 )
          goto LABEL_13;
        ppv = 0;
        if ( (unsigned int)v7 < v10 && (unsigned int)v7 < 6 && (v27 = v7, *((_BYTE *)this + 24 * v7 + 104)) )
        {
          wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(&v107, (char *)this + 24 * v7 + 96);
          v62 = *(_QWORD *)&v107.vt;
          if ( *(_QWORD *)&v107.vt )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v107.vt + 16LL))(*(_QWORD *)&v107.vt);
          if ( v62 )
          {
            RuntimeIdFromPartial = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v62 + 80LL))(v62, &ppv);
            goto LABEL_146;
          }
        }
        else
        {
          v27 = v7;
        }
        if ( (unsigned int)v7 < *((_DWORD *)this + 60) && (unsigned int)v7 < 6 )
        {
          v28 = 24 * v27;
          if ( !*((_BYTE *)this + 24 * v27 + 104) )
          {
            _mm_lfence();
            v29 = (unsigned int (__fastcall ***)(_QWORD, GUID *, LONG *))*((_QWORD *)this + 3 * v27 + 12);
            if ( v29 )
            {
              v30 = *((_QWORD *)this + 32);
              if ( v30
                && !*(_DWORD *)(v30 + 40)
                && *(_DWORD *)((char *)this + v28 + 108)
                && !*(_BYTE *)(v30 + 60)
                && GetClassNameW(*(HWND *)(v30 + 24), ClassName, 128)
                && CompareStringW(0x7Fu, 1u, ClassName, -1, L"Chrome_RenderWidgetHostHWND", -1) == 2 )
              {
                goto LABEL_55;
              }
              LOBYTE(pvt[0]) = 0;
              RuntimeIdFromProviderEntryPoint = UiaNode::TryGetRuntimeIdFromProviderEntryPoint(
                                                  this,
                                                  (struct tagSAFEARRAY **)&ppv,
                                                  (bool *)pvt);
              RuntimeIdFromPartial = RuntimeIdFromProviderEntryPoint;
              if ( RuntimeIdFromProviderEntryPoint < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBB3,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)RuntimeIdFromProviderEntryPoint,
                  lpString2);
                return RuntimeIdFromPartial;
              }
              if ( !LOBYTE(pvt[0]) )
              {
LABEL_55:
                *(_QWORD *)plLbound = 0;
                v34 = (**v29)(v29, &GUID_f7063da8_8359_439c_9297_bbc5299a7d87, plLbound)
                    ? 0LL
                    : *(struct IRawElementProviderFragment **)plLbound;
                *(_QWORD *)&v107.vt = v34;
                if ( v34 )
                {
                  psa = 0;
                  *(_QWORD *)plLbound = L"IRawElementProviderFragment::GetRuntimeId";
                  v102 = 0;
                  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
                    McTemplateU0zqq_EventWriteTransfer(
                      v33,
                      (unsigned int)UiaProviderCallout_Start,
                      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
                      0,
                      0);
                  v36 = ((__int64 (__fastcall *)(struct IRawElementProviderFragment *, SAFEARRAY **))v34->lpVtbl->GetRuntimeId)(
                          v34,
                          &psa);
                  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
                    McTemplateU0zqq_EventWriteTransfer(
                      v35,
                      (unsigned int)UiaProviderCallout_Stop,
                      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
                      0,
                      0);
                  if ( v36 == -2147220991 )
                  {
                    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
                    ((void (__fastcall *)(struct IRawElementProviderFragment *))v34->lpVtbl->Release)(v34);
                    return (unsigned int)-2147220991;
                  }
                  if ( v36 < 0 || !psa )
                  {
                    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
                    ((void (__fastcall *)(struct IRawElementProviderFragment *))v34->lpVtbl->Release)(v34);
                    goto LABEL_132;
                  }
                  v100.lVal = 0;
                  v100.pRecInfo = 0;
                  *(_QWORD *)&v100.vt = psa;
                  if ( SafeArrayGetDim(psa) != 1 )
                  {
                    v68 = 2147942487LL;
                    RuntimeIdFromPartial = -2147024809;
                    v67 = 92;
                    goto LABEL_186;
                  }
                  pvt[0] = 0;
                  Vartype = SafeArrayGetVartype(*(SAFEARRAY **)&v100.vt, pvt);
                  RuntimeIdFromPartial = Vartype;
                  if ( Vartype < 0 )
                  {
                    v67 = 95;
                    v68 = (unsigned int)Vartype;
                    goto LABEL_186;
                  }
                  if ( pvt[0] != 3 && pvt[0] != 22 )
                  {
                    v68 = 2147942487LL;
                    RuntimeIdFromPartial = -2147024809;
                    v67 = 106;
LABEL_186:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v67,
                      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                      (const char *)v68,
                      lpString2);
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x9F,
                      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                      (const char *)RuntimeIdFromPartial,
                      lpString2g);
                    v59 = *(SAFEARRAY **)&v100.vt;
                    if ( !*(_QWORD *)&v100.vt )
                    {
LABEL_149:
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xBD6,
                        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                        (const char *)RuntimeIdFromPartial,
                        lpString2a);
                      operator delete(0);
                      AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
                      ((void (__fastcall *)(struct IRawElementProviderFragment *))v34->lpVtbl->Release)(v34);
                      goto LABEL_146;
                    }
LABEL_187:
                    SafeArrayUnaccessData(v59);
                    goto LABEL_149;
                  }
                  plLbound[0] = 0;
                  plUbound[0] = 0;
                  LBound = SafeArrayGetLBound(*(SAFEARRAY **)&v100.vt, 1u, plLbound);
                  RuntimeIdFromPartial = LBound;
                  if ( LBound < 0 )
                  {
                    v67 = 111;
                  }
                  else
                  {
                    UBound = SafeArrayGetUBound(*(SAFEARRAY **)&v100.vt, 1u, plUbound);
                    RuntimeIdFromPartial = UBound;
                    if ( UBound < 0 )
                    {
                      v67 = 112;
                      v68 = (unsigned int)UBound;
                      goto LABEL_186;
                    }
                    v100.lVal = plUbound[0] - plLbound[0] + 1;
                    LBound = SafeArrayAccessData(*(SAFEARRAY **)&v100.vt, (void **)&v100.pRecInfo);
                    RuntimeIdFromPartial = LBound;
                    if ( LBound >= 0 )
                    {
                      v40 = 4LL * v100.cyVal.Lo;
                      if ( !is_mul_ok(v100.cyVal.Lo, 4u) )
                        v40 = -1;
                      v41 = (int *)operator new[](v40, (const struct std::nothrow_t *)std::nothrow);
                      if ( !v41 )
                      {
                        RuntimeIdFromPartial = -2147024882;
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xA2,
                          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                          (const char *)0x8007000ELL,
                          lpString2);
                        v59 = *(SAFEARRAY **)&v100.vt;
                        if ( !*(_QWORD *)&v100.vt )
                          goto LABEL_149;
                        goto LABEL_187;
                      }
                      v57 = 0;
                      for ( j = v100.lVal; v57 < v100.lVal; j = v100.lVal )
                      {
                        v41[v57] = *((_DWORD *)&v100.pRecInfo->lpVtbl + v57);
                        ++v57;
                      }
                      if ( *(_QWORD *)&v100.vt )
                        SafeArrayUnaccessData(*(SAFEARRAY **)&v100.vt);
                      if ( j )
                      {
                        if ( j != 1 && *v41 == 3 )
                        {
                          RuntimeIdFromPartial = UiaNode::ProviderGetRuntimeIdFromPartial(
                                                   v34,
                                                   v41,
                                                   j,
                                                   (struct tagSAFEARRAY **)&ppv);
                          operator delete(v41);
                          if ( psa )
                          {
                            SafeArrayDestroy(psa);
                            psa = 0;
                          }
                          ((void (__fastcall *)(struct IRawElementProviderFragment *))v34->lpVtbl->Release)(v34);
LABEL_146:
                          if ( (RuntimeIdFromPartial & 0x80000000) != 0 )
                            return RuntimeIdFromPartial;
                          goto LABEL_132;
                        }
                        ppv = psa;
                        psa = 0;
                        operator delete(v41);
                        if ( psa )
                        {
                          SafeArrayDestroy(psa);
                          psa = 0;
                        }
                        ((void (__fastcall *)(struct IRawElementProviderFragment *))v34->lpVtbl->Release)(v34);
                      }
                      else
                      {
                        operator delete(v41);
                        AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
                        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v107);
                      }
                      goto LABEL_132;
                    }
                    v67 = 115;
                  }
                  v68 = (unsigned int)LBound;
                  goto LABEL_186;
                }
              }
            }
          }
        }
LABEL_132:
        v56 = ppv;
        if ( ppv )
        {
          pvarg->vt = 8195;
          pvarg->llVal = (LONGLONG)v56;
        }
        return 0;
      }
      EnterCriticalSection(&_schemaLock);
      if ( (unsigned int)(v11 - 10000) <= 0x23 )
      {
        v42 = &(&off_1802EAA40)[16 * (unsigned __int64)(unsigned int)(v11 - 10000)];
        goto LABEL_79;
      }
      for ( k = g_pUserDefinedPatterns; k; k = *(struct UserDefinedPatternInfo **)k )
      {
        if ( *((_DWORD *)k + 6) == v11 )
        {
          v42 = (GUID **)((char *)k + 16);
LABEL_79:
          LeaveCriticalSection(&_schemaLock);
          if ( v42 )
          {
            memset(&v100, 0, sizeof(v100));
            VariantInit(&v100);
            *(_QWORD *)plLbound = 0;
            v43 = *((_DWORD *)a6 + 6);
            if ( (unsigned int)v7 >= *((_DWORD *)this + 60)
              || (unsigned int)v7 >= 6
              || (v44 = v7, !*((_BYTE *)this + 24 * v7 + 104)) )
            {
              v44 = v7;
              goto LABEL_84;
            }
            wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(&ppv, (char *)this + 24 * v7 + 96);
            v66 = ppv;
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            if ( v66 )
            {
              PropertyForUserRegisteredPattern = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LONG *))(*(_QWORD *)v66 + 72LL))(
                                                   v66,
                                                   v43,
                                                   plLbound);
              *(_DWORD *)pvt = PropertyForUserRegisteredPattern;
              if ( PropertyForUserRegisteredPattern >= 0 )
                goto LABEL_172;
              goto LABEL_173;
            }
LABEL_84:
            if ( (unsigned int)v7 >= *((_DWORD *)this + 60)
              || (unsigned int)v7 >= 6
              || *((_BYTE *)this + 24 * v44 + 104) )
            {
              v45 = 0;
            }
            else
            {
              _mm_lfence();
              v45 = (struct IUnknown *)*((_QWORD *)this + 3 * v44 + 12);
            }
            psa = 0;
            ppv = (LPVOID)L"IRawElementProviderSimple::GetPatternProvider";
            v105 = v43;
            v106 = 0;
            if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
              McTemplateU0zqq_EventWriteTransfer(
                0,
                (unsigned int)UiaProviderCallout_Start,
                (unsigned int)L"IRawElementProviderSimple::GetPatternProvider",
                v43,
                0);
            PropertyForUserRegisteredPattern = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, SAFEARRAY **))v45->lpVtbl[1].AddRef)(
                                                 v45,
                                                 v43,
                                                 &psa);
            if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
              McTemplateU0zqq_EventWriteTransfer(
                v46,
                (unsigned int)UiaProviderCallout_Stop,
                (unsigned int)L"IRawElementProviderSimple::GetPatternProvider",
                v43,
                0);
            if ( PropertyForUserRegisteredPattern < 0 )
            {
              if ( PropertyForUserRegisteredPattern == -2147220988 )
              {
                if ( psa )
                  (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
                *(_DWORD *)pvt = -2147220988;
                goto LABEL_173;
              }
              Error::GeneralProviderError(
                v45,
                L"IRawElementProviderSimple::GetPatternProvider",
                PropertyForUserRegisteredPattern,
                0,
                419,
                0);
            }
            v48 = psa;
            if ( !psa )
            {
              PatternProvider_MSAALegacy = UiaNode::ProviderGetPatternProvider_MSAALegacy(
                                             this,
                                             v7,
                                             (struct IRawElementProviderSimple *)v45,
                                             v43,
                                             (struct IUnknown **)&psa);
              PropertyForUserRegisteredPattern = PatternProvider_MSAALegacy;
              if ( PatternProvider_MSAALegacy < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAF0,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)PatternProvider_MSAALegacy,
                  lpString2d);
                if ( psa )
                  (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
                *(_DWORD *)pvt = PropertyForUserRegisteredPattern;
                goto LABEL_173;
              }
              v48 = psa;
              if ( !psa )
                return 0;
            }
            *(_QWORD *)plUbound = 0;
            v49 = (**(__int64 (__fastcall ***)(SAFEARRAY *, __int64, LONG *))&v48->cDims)(
                    v48,
                    (__int64)(v42 + 3),
                    plUbound);
            if ( v49 >= 0 && (v50 = *(struct ITableProvider **)plUbound) != 0 )
            {
              if ( v43 == 10012 )
              {
                ppv = 0;
                v77 = WrapTableProvider(
                        (struct IRawElementProviderSimple *)v45,
                        *(struct ITableProvider **)plUbound,
                        (struct IExTableProvider **)&ppv);
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plUbound + 16LL))(*(_QWORD *)plUbound);
                v50 = 0;
                *(_QWORD *)plUbound = 0;
                if ( v77 >= 0 )
                {
                  if ( ppv )
                  {
                    v50 = (struct ITableProvider *)ppv;
                    *(_QWORD *)plUbound = ppv;
                  }
                }
              }
              *(_QWORD *)plLbound = v50;
              if ( psa )
              {
                (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
                v50 = *(struct ITableProvider **)plLbound;
              }
              *(_DWORD *)pvt = 0;
            }
            else
            {
              Error::GeneralProviderError(
                (struct IUnknown *)psa,
                L"IUnknown::QueryInterface",
                v49,
                *((const struct ProviderEntryPoint **)this + 32),
                413,
                0);
              if ( psa )
                (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
              *(_DWORD *)pvt = 0;
LABEL_172:
              v50 = *(struct ITableProvider **)plLbound;
            }
            if ( !v50 )
              return 0;
            v51 = *(void (**)(int, void *))(*(_QWORD *)&v107.vt + 32LL);
            if ( v51 == wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy )
            {
              pvarg->vt = 11;
              pvarg->iVal = -1;
              ((void (__fastcall *)(struct ITableProvider *))v50->lpVtbl->Release)(v50);
              return 0;
            }
            v54 = (struct UiaClientState *)*((_QWORD *)this + 10);
            if ( v42[8] )
            {
              PropertyForUserRegisteredPattern = CAutomationPatternInstance::GetPropertyForUserRegisteredPattern(
                                                   (struct IUnknown *)v50,
                                                   v54,
                                                   (const struct PatternInfo *)v42,
                                                   *(const struct PropertyInfo **)&v107.vt,
                                                   &v100);
              *(_DWORD *)pvt = PropertyForUserRegisteredPattern;
            }
            else
            {
              ((void (__fastcall *)(struct ITableProvider *, struct UiaClientState *, VARTYPE *, VARIANTARG *))v51)(
                v50,
                v54,
                pvt,
                &v100);
              PropertyForUserRegisteredPattern = *(_DWORD *)pvt;
            }
            if ( PropertyForUserRegisteredPattern < 0 )
              goto LABEL_173;
            if ( v100.vt == 8 && !v100.llVal )
            {
              PropertyForUserRegisteredPattern = UiaNode::ProvideFallbackPatternPropertyValue(
                                                   this,
                                                   a5,
                                                   *(struct IUnknown **)plLbound,
                                                   &v100);
              *(_DWORD *)pvt = PropertyForUserRegisteredPattern;
            }
            if ( PropertyForUserRegisteredPattern < 0 )
            {
LABEL_173:
              if ( PropertyForUserRegisteredPattern == -2147220988 )
              {
                pvarg->vt = 13;
                pvarg->llVal = (LONGLONG)g_punkNotSupportedValue;
                if ( *(_QWORD *)plLbound )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plLbound + 16LL))(*(_QWORD *)plLbound);
                return 0;
              }
              else
              {
                wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(plLbound);
                return (unsigned int)PropertyForUserRegisteredPattern;
              }
            }
            else
            {
              *pvarg = v100;
              if ( *(_QWORD *)plLbound )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plLbound + 16LL))(*(_QWORD *)plLbound);
              return 0;
            }
          }
          return Error::InternalErrorWorker(L"couldn't find pattern info for specified property");
        }
      }
      LeaveCriticalSection(&_schemaLock);
      return Error::InternalErrorWorker(L"couldn't find pattern info for specified property");
    }
    v12 = a5;
    if ( a5 == 30000 )
    {
      psa = 0;
      RuntimeId = UiaNode::ProviderGetRuntimeId(this, v7, &psa);
      if ( RuntimeId < 0 )
      {
        AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
        return (unsigned int)RuntimeId;
      }
      else
      {
        *(_QWORD *)&v100.vt = 0;
        v100.lVal = 0;
        v100.pRecInfo = 0;
        v53 = psa;
        if ( psa )
        {
          if ( (int)SafeArrayAccessor<int>::Access(&v100, psa) >= 0 && v100.lVal )
          {
            pvarg->vt = 8195;
            pvarg->llVal = (LONGLONG)psa;
            v53 = 0;
            psa = 0;
          }
          else
          {
            v53 = psa;
          }
          if ( *(_QWORD *)&v100.vt )
          {
            SafeArrayUnaccessData(*(SAFEARRAY **)&v100.vt);
            v53 = psa;
          }
        }
        if ( v53 )
          SafeArrayDestroy(v53);
        return 0;
      }
    }
LABEL_13:
    v14 = (const struct ProviderEntryPoint *)*((_QWORD *)this + 32);
    v15 = *((_WORD *)a6 + 20);
    VariantInit(pvarg);
    psa = (SAFEARRAY *)L"IRawElementProviderSimple::GetPropertyValue";
    v98 = v12;
    v99 = 0;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        0,
        (unsigned int)UiaProviderCallout_Start,
        (unsigned int)L"IRawElementProviderSimple::GetPropertyValue",
        v12,
        0);
    v16 = (struct IUnknown *)ppv;
    v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct tagVARIANT *))(*(_QWORD *)ppv + 40LL))(ppv, v12, pvarg);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        (_DWORD)bstrVal,
        (unsigned int)UiaProviderCallout_Stop,
        (unsigned int)L"IRawElementProviderSimple::GetPropertyValue",
        v12,
        0);
    if ( v18 >= 0 )
      goto LABEL_18;
    if ( v18 != -2147023436 && v18 != -2146233083 )
    {
      if ( v18 != -2147220991 )
      {
        if ( v18 == -2147220988 )
        {
          pvarg->vt = 13;
          pvarg->llVal = (LONGLONG)g_punkNotSupportedValue;
          goto LABEL_22;
        }
        Error::GeneralProviderError(
          (struct IUnknown *)ppv,
          L"IRawElementProviderSimple::GetPropertyValue",
          v18,
          v14,
          419,
          0);
        VariantClear(pvarg);
        pvarg->vt = 0;
        v18 = 0;
LABEL_18:
        if ( v15 && pvarg->vt && v15 != pvarg->vt )
        {
          Error::GeneralProviderError(v16, L"IRawElementProviderSimple::GetPropertyValue", v18, v14, 404, 0);
          VariantClear(pvarg);
          pvarg->vt = 0;
          goto LABEL_28;
        }
        if ( pvarg->vt == 8 )
        {
          bstrVal = pvarg->bstrVal;
          if ( bstrVal )
          {
            v22 = SysStringLen(bstrVal);
            v23 = pvarg->bstrVal;
            if ( v23 )
            {
              v24 = v22 + 1;
              if ( v24 <= 0x7FFFFFFF )
              {
                v25 = (unsigned int)v24;
                if ( v22 == -1 )
                {
LABEL_38:
                  bstrVal = 0;
                }
                else
                {
                  while ( *v23 )
                  {
                    ++v23;
                    if ( !--v24 )
                      goto LABEL_38;
                  }
                  bstrVal = (OLECHAR *)(v25 - v24);
                }
                if ( v24 )
                {
                  if ( (unsigned __int64)bstrVal < v22 )
                  {
                    Error::GeneralProviderError(v16, L"IRawElementProviderSimple::GetPropertyValue", 0, v14, 405, 0);
                    v26 = SysAllocString(pvarg->bstrVal);
                    if ( v26 )
                    {
                      SysFreeString(pvarg->bstrVal);
                      pvarg->llVal = (LONGLONG)v26;
                    }
                  }
                }
              }
            }
          }
        }
        if ( !pvarg->vt )
        {
LABEL_28:
          if ( v12 == 30158 )
          {
            VariantInit(&v100);
            v100.llVal = 0;
            PropertyValue = ProviderCallouts::GetPropertyValue(
                              (struct IRawElementProviderSimple *)v16,
                              3u,
                              *((struct ProviderEntryPoint **)this + 32),
                              30157,
                              &v100);
            v79 = PropertyValue;
            if ( PropertyValue < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x97B,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                (const char *)(unsigned int)PropertyValue,
                lpString2e);
              VariantClear(&v100);
              return v79;
            }
            if ( v100.vt == 3 )
            {
              v80 = UiaNode::SetLocalizedLandmarkTypeFromControlType(v100.lVal, pvarg);
              v81 = v80;
              if ( v80 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x980,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)v80,
                  lpString2e);
                VariantClear(&v100);
                return v81;
              }
            }
          }
          else
          {
            if ( v12 != 30004 )
            {
              if ( v12 == 30002 )
              {
                plUbound[0] = 0;
                *(_QWORD *)&v107.vt = L"IRawElementProviderSimple::get_ProviderOptions";
                v107.llVal = 0;
                if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
                  McTemplateU0zqq_EventWriteTransfer(
                    (_DWORD)bstrVal,
                    (unsigned int)UiaProviderCallout_Start,
                    (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
                    0,
                    0);
                v64 = ((__int64 (__fastcall *)(struct IUnknown *, LONG *))v16->lpVtbl[1].QueryInterface)(v16, plUbound);
                if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
                  McTemplateU0zqq_EventWriteTransfer(
                    v63,
                    (unsigned int)UiaProviderCallout_Stop,
                    (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
                    0,
                    0);
                if ( v64 >= 0 )
                {
                  if ( BasicUtils::IsInCrossMachineRemoteSession() )
                  {
                    ppv = 0;
                    v84 = CoCreateInstance(
                            &CLSID_UiaManagerCrossMachineStubFactory,
                            0,
                            4u,
                            &GUID_af0f139e_02d8_43f9_a1ac_1313889041a0,
                            &ppv);
                    v85 = v84;
                    if ( v84 >= 0 )
                    {
                      plLbound[0] = 0;
                      v86 = (*(__int64 (__fastcall **)(LPVOID, LONG *))(*(_QWORD *)ppv + 24LL))(ppv, plLbound);
                      v87 = v86;
                      if ( v86 >= 0 )
                      {
                        pvarg->vt = 3;
                        pvarg->lVal = plLbound[0];
                        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&ppv);
                        return 0;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x9C5,
                          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                          (const char *)(unsigned int)v86,
                          lpString2f);
                        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&ppv);
                        return v87;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x9C2,
                        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                        (const char *)(unsigned int)v84,
                        lpString2f);
                      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&ppv);
                      return v85;
                    }
                  }
                  if ( (plUbound[0] & 2) != 0 )
                  {
                    CurrentProcessId = GetCurrentProcessId();
                    pvarg->vt = 3;
                    pvarg->lVal = CurrentProcessId;
                    return 0;
                  }
                }
              }
              return 0;
            }
            VariantInit(&v100);
            v100.llVal = 0;
            v69 = ProviderCallouts::GetPropertyValue(
                    (struct IRawElementProviderSimple *)v16,
                    8u,
                    *((struct ProviderEntryPoint **)this + 32),
                    30101,
                    &v100);
            v70 = v69;
            if ( v69 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x995,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                (const char *)(unsigned int)v69,
                lpString2b);
              VariantClear(&v100);
              return v70;
            }
            if ( v100.vt == 8 )
            {
              v82 = UiaNode::SetLocalizedControlTypeFromAriaRole(v100.bstrVal, pvarg);
              v83 = v82;
              if ( v82 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x998,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)v82,
                  lpString2b);
                VariantClear(&v100);
                return v83;
              }
            }
            if ( !pvarg->vt )
            {
              VariantInit(&v107);
              v107.llVal = 0;
              v71 = ProviderCallouts::GetPropertyValue(
                      (struct IRawElementProviderSimple *)v16,
                      3u,
                      *((struct ProviderEntryPoint **)this + 32),
                      30003,
                      &v107);
              v72 = v71;
              if ( v71 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9A0,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)v71,
                  lpString2c);
                VariantClear(&v107);
                VariantClear(&v100);
                return v72;
              }
              if ( v107.vt == 3 )
              {
                v73 = UiaNode::SetLocalizedControlTypeFromControlType(v107.lVal, pvarg);
                v74 = v73;
                if ( v73 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x9A5,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                    (const char *)(unsigned int)v73,
                    lpString2c);
                  VariantClear(&v107);
                  VariantClear(&v100);
                  return v74;
                }
              }
              VariantClear(&v107);
            }
          }
          VariantClear(&v100);
          return 0;
        }
LABEL_22:
        a4 = (struct IRawElementProviderSimple *)*(unsigned int *)(*(_QWORD *)&v107.vt + 44LL);
        if ( (unsigned int)((_DWORD)a4 - 5) <= 1 )
          UiaNode::ProviderTransformLogicalToPhysicalCoords(
            this,
            *(_DWORD *)pvt != 0,
            (struct IRawElementProviderSimple *)v16,
            (enum UIAutomationType)a4,
            pvarg);
        if ( pvarg->vt )
        {
          WrapPropertyOnServerSide(*(int *)pvt, *((struct UiaClientState **)this + 10), v12, pvarg);
          return 0;
        }
        goto LABEL_28;
      }
      v18 = -2147220991;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x968,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)(unsigned int)v18,
      lpString2);
    result = (unsigned int)v18;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9D9,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                           (const char *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800bf960  push    rbx
0x1800bf962  push    rsi
0x1800bf963  push    rdi
0x1800bf964  push    r12
0x1800bf966  push    r13
0x1800bf968  push    r14
0x1800bf96a  push    r15
0x1800bf96c  sub     rsp, 1B0h
0x1800bf973  mov     rax, cs:__security_cookie
0x1800bf97a  xor     rax, rsp
0x1800bf97d  mov     [rsp+1E8h+var_48], rax
0x1800bf985  mov     r10, r9
0x1800bf988  mov     [rsp+1E8h+ppv], r9
0x1800bf98d  mov     r12d, r8d
0x1800bf990  mov     r8d, edx
0x1800bf993  mov     dword ptr [rsp+1E8h+pvt], edx
0x1800bf997  mov     r13, rcx
0x1800bf99a  mov     r15, [rsp+1E8h+pvarg]
0x1800bf9a2  mov     rdi, [rsp+1E8h+arg_28]
0x1800bf9aa  mov     qword ptr [rsp+1E8h+var_160], rdi
0x1800bf9b2  xor     r14d, r14d
0x1800bf9b5  mov     [r15], r14w
0x1800bf9b9  mov     ecx, [rcx+0F0h]
0x1800bf9bf  cmp     r12d, ecx
0x1800bf9c2  jnb     short loc_1800BF9DD
0x1800bf9c4  cmp     r12d, 6
0x1800bf9c8  jnb     short loc_1800BF9DD
0x1800bf9ca  lea     r8, [r12+r12*2]
0x1800bf9ce  cmp     dword ptr [r13+r8*8+6Ch], 6
0x1800bf9d4  jz      loc_1800C0078
0x1800bf9da  mov     r8d, edx
0x1800bf9dd  mov     ebx, [rdi+18h]
0x1800bf9e0  test    ebx, ebx
0x1800bf9e2  jnz     loc_1800BFEBF
0x1800bf9e8  mov     ebx, [rsp+1E8h+arg_20]
0x1800bf9ef  cmp     ebx, 7531h
0x1800bf9f5  jz      loc_1800C03A8
0x1800bf9fb  lea     rdx, ?s_pointProperties@UiaUtils@@0V?$ConstKeyMap@W4PointProperty@@H$01@@B; ConstKeyMap<PointProperty,int,2> const UiaUtils::s_pointProperties
0x1800bfa02  lea     rax, aChromeRenderwi; "Chrome_RenderWidgetHostHWND"
0x1800bfa09  nop     dword ptr [rax+00000000h]
0x1800bfa10  cmp     rdx, rax
0x1800bfa13  jz      short loc_1800BFA24
0x1800bfa15  cmp     [rdx+4], ebx
0x1800bfa18  jz      loc_1800BFAFD
0x1800bfa1e  add     rdx, 8
0x1800bfa22  jmp     short loc_1800BFA10
0x1800bfa24  cmp     ebx, 7530h
0x1800bfa2a  jz      loc_1800BFC6C
0x1800bfa30  mov     r14, [r13+100h]
0x1800bfa37  movzx   esi, word ptr [rdi+28h]
0x1800bfa3b  mov     rcx, r15; pvarg
0x1800bfa3e  call    cs:__imp_VariantInit
0x1800bfa44  lea     rax, aIrawelementpro_15; "IRawElementProviderSimple::GetPropertyV"...
0x1800bfa4b  mov     [rsp+1E8h+psa], rax
0x1800bfa50  mov     [rsp+1E8h+var_1A8], ebx
0x1800bfa54  xor     ecx, ecx
0x1800bfa56  mov     [rsp+1E8h+var_1A4], ecx
0x1800bfa5a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bfa61  jnz     loc_1800C0791
0x1800bfa67  mov     r12, [rsp+1E8h+ppv]
0x1800bfa6c  mov     rax, [r12]
0x1800bfa70  mov     r8, r15
0x1800bfa73  mov     edx, ebx
0x1800bfa75  mov     rcx, r12
0x1800bfa78  mov     rax, [rax+28h]
0x1800bfa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa81  mov     edi, eax
0x1800bfa83  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bfa8a  jnz     loc_1800C087C
0x1800bfa90  test    edi, edi
0x1800bfa92  js      loc_1800C06CF
0x1800bfa98  test    si, si
0x1800bfa9b  jz      short loc_1800BFAAA
0x1800bfa9d  movzx   eax, word ptr [r15]
0x1800bfaa1  test    ax, ax
0x1800bfaa4  jnz     loc_1800BFEB1
0x1800bfaaa  cmp     word ptr [r15], 8
0x1800bfaaf  jz      loc_1800BFBBA
0x1800bfab5  cmp     word ptr [r15], 0
0x1800bfaba  jz      loc_1800BFB92
0x1800bfac0  mov     r9, qword ptr [rsp+1E8h+var_160]
0x1800bfac8  mov     r9d, [r9+2Ch]; enum UIAutomationType
0x1800bfacc  lea     eax, [r9-5]
0x1800bfad0  mov     edi, dword ptr [rsp+1E8h+pvt]
0x1800bfad4  cmp     eax, 1
0x1800bfad7  jbe     loc_1800C0B7A
0x1800bfadd  cmp     word ptr [r15], 0
0x1800bfae2  jz      loc_1800BFB92
0x1800bfae8  mov     r9, r15; struct tagVARIANT *
0x1800bfaeb  mov     r8d, ebx; int
0x1800bfaee  mov     rdx, [r13+50h]; struct UiaClientState *
0x1800bfaf2  mov     ecx, edi; int
0x1800bfaf4  call    ?WrapPropertyOnServerSide@@YAXHPEAVUiaClientState@@HPEAUtagVARIANT@@@Z; WrapPropertyOnServerSide(int,UiaClientState *,int,tagVARIANT *)
0x1800bfaf9  xor     eax, eax
0x1800bfafb  jmp     short loc_1800BFB3B
0x1800bfafd  test    r8d, r8d
0x1800bfb00  setnz   r8b
0x1800bfb04  mov     [rsp+1E8h+lpString2], r15; int
0x1800bfb09  mov     edx, [rdx]
0x1800bfb0b  mov     rcx, r13
0x1800bfb0e  call    ?GetPointPropertyInScreenCoordinates@UiaNode@@AEAAJW4PointProperty@@_NPEAUIRawElementProviderSimple@@PEAUtagVARIANT@@@Z; UiaNode::GetPointPropertyInScreenCoordinates(PointProperty,bool,IRawElementProviderSimple *,tagVARIANT *)
0x1800bfb13  mov     ebx, eax
0x1800bfb15  test    eax, eax
0x1800bfb17  jns     loc_1800C0B16
0x1800bfb1d  mov     rcx, [rsp+1E8h]; this
0x1800bfb25  mov     r9d, eax; char *
0x1800bfb28  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800bfb2f  mov     edx, 93Dh; void *
0x1800bfb34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfb39  mov     eax, ebx
0x1800bfb3b  mov     rcx, [rsp+1E8h+var_48]
0x1800bfb43  xor     rcx, rsp; StackCookie
0x1800bfb46  call    __security_check_cookie
0x1800bfb4b  add     rsp, 1B0h
0x1800bfb52  pop     r15
0x1800bfb54  pop     r14
0x1800bfb56  pop     r13
0x1800bfb58  pop     r12
0x1800bfb5a  pop     rdi
0x1800bfb5b  pop     rsi
0x1800bfb5c  pop     rbx
0x1800bfb5d  retn
0x1800bfb5e  mov     [rsp+1E8h+cchCount2], 0; int
0x1800bfb66  mov     dword ptr [rsp+1E8h+lpString2], 194h; int
0x1800bfb6e  mov     r9, r14; struct ProviderEntryPoint *
0x1800bfb71  mov     r8d, edi; int
0x1800bfb74  lea     rdx, aIrawelementpro_15; "IRawElementProviderSimple::GetPropertyV"...
0x1800bfb7b  mov     rcx, r12; struct IUnknown *
0x1800bfb7e  call    ?GeneralProviderError@Error@@CAXPEAUIUnknown@@PEBGJPEBVProviderEntryPoint@@HH@Z; Error::GeneralProviderError(IUnknown *,ushort const *,long,ProviderEntryPoint const *,int,int)
0x1800bfb83  mov     rcx, r15; pvarg
0x1800bfb86  call    cs:__imp_VariantClear
0x1800bfb8c  xor     eax, eax
0x1800bfb8e  mov     [r15], ax
0x1800bfb92  cmp     ebx, 75CEh
0x1800bfb98  jz      loc_1800C0B94
0x1800bfb9e  cmp     ebx, 7534h
0x1800bfba4  jz      loc_1800C07AC
0x1800bfbaa  cmp     ebx, 7532h
0x1800bfbb0  jz      loc_1800C048B
0x1800bfbb6  xor     eax, eax
0x1800bfbb8  jmp     short loc_1800BFB3B
0x1800bfbba  mov     rcx, [r15+8]; pbstr
0x1800bfbbe  test    rcx, rcx
0x1800bfbc1  jz      loc_1800BFAB5
0x1800bfbc7  call    cs:__imp_SysStringLen
0x1800bfbcd  mov     rdx, [r15+8]
0x1800bfbd1  test    rdx, rdx
0x1800bfbd4  jz      loc_1800BFAB5
0x1800bfbda  lea     r8d, [rax+1]
0x1800bfbde  cmp     r8, 7FFFFFFFh
0x1800bfbe5  ja      loc_1800BFAB5
0x1800bfbeb  mov     ecx, r8d
0x1800bfbee  test    r8, r8
0x1800bfbf1  jz      short loc_1800BFC03
0x1800bfbf3  cmp     word ptr [rdx], 0
0x1800bfbf7  jz      short loc_1800BFC07
0x1800bfbf9  add     rdx, 2
0x1800bfbfd  sub     r8, 1
0x1800bfc01  jnz     short loc_1800BFBF3
0x1800bfc03  xor     ecx, ecx
0x1800bfc05  jmp     short loc_1800BFC0A
0x1800bfc07  sub     rcx, r8
0x1800bfc0a  test    r8, r8
0x1800bfc0d  jz      loc_1800BFAB5
0x1800bfc13  mov     eax, eax
0x1800bfc15  cmp     rcx, rax
0x1800bfc18  jnb     loc_1800BFAB5
0x1800bfc1e  mov     [rsp+1E8h+cchCount2], 0; int
0x1800bfc26  mov     dword ptr [rsp+1E8h+lpString2], 195h; int
0x1800bfc2e  mov     r9, r14; struct ProviderEntryPoint *
0x1800bfc31  xor     r8d, r8d; int
0x1800bfc34  lea     rdx, aIrawelementpro_15; "IRawElementProviderSimple::GetPropertyV"...
0x1800bfc3b  mov     rcx, r12; struct IUnknown *
0x1800bfc3e  call    ?GeneralProviderError@Error@@CAXPEAUIUnknown@@PEBGJPEBVProviderEntryPoint@@HH@Z; Error::GeneralProviderError(IUnknown *,ushort const *,long,ProviderEntryPoint const *,int,int)
0x1800bfc43  mov     rcx, [r15+8]; psz
0x1800bfc47  call    cs:__imp_SysAllocString
0x1800bfc4d  mov     rdi, rax
0x1800bfc50  test    rax, rax
0x1800bfc53  jz      loc_1800BFAB5
0x1800bfc59  mov     rcx, [r15+8]; bstrString
0x1800bfc5d  call    cs:__imp_SysFreeString
0x1800bfc63  mov     [r15+8], rdi
0x1800bfc67  jmp     loc_1800BFAB5
0x1800bfc6c  mov     [rsp+1E8h+ppv], r14
0x1800bfc71  cmp     r12d, ecx
0x1800bfc74  jnb     short loc_1800BFC8F
0x1800bfc76  cmp     r12d, 6
0x1800bfc7a  jnb     short loc_1800BFC8F
0x1800bfc7c  mov     rbx, r12
0x1800bfc7f  lea     rax, [r12+r12*2]
0x1800bfc83  cmp     byte ptr [r13+rax*8+68h], 0
0x1800bfc89  jnz     loc_1800C040F
0x1800bfc8f  mov     rbx, r12
0x1800bfc92  cmp     r12d, [r13+0F0h]
0x1800bfc99  jnb     loc_1800C0263
0x1800bfc9f  cmp     r12d, 6
0x1800bfca3  jnb     loc_1800C0263
0x1800bfca9  lea     rax, [rbx+rbx*2]
0x1800bfcad  lea     rdx, ds:0[rax*8]
0x1800bfcb5  cmp     byte ptr [rdx+r13+68h], 0
0x1800bfcbb  jnz     loc_1800C0263
0x1800bfcc1  lfence
0x1800bfcc4  lea     rax, [rbx+rbx*2]
0x1800bfcc8  mov     rbx, [r13+rax*8+60h]
0x1800bfccd  test    rbx, rbx
0x1800bfcd0  jz      loc_1800C0263
0x1800bfcd6  mov     rcx, [r13+100h]
0x1800bfcdd  test    rcx, rcx
0x1800bfce0  jnz     loc_1800C01D6
0x1800bfce6  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800bfced  mov     byte ptr [rsp+1E8h+pvt], 0
0x1800bfcf2  lea     r8, [rsp+1E8h+pvt]; bool *
0x1800bfcf7  lea     rdx, [rsp+1E8h+ppv]; struct tagSAFEARRAY **
0x1800bfcfc  mov     rcx, r13; this
0x1800bfcff  call    ?TryGetRuntimeIdFromProviderEntryPoint@UiaNode@@AEBAJPEAPEAUtagSAFEARRAY@@PEA_N@Z; UiaNode::TryGetRuntimeIdFromProviderEntryPoint(tagSAFEARRAY * *,bool *)
0x1800bfd04  mov     edi, eax
0x1800bfd06  test    eax, eax
0x1800bfd08  js      loc_1800C0B1D
0x1800bfd0e  cmp     byte ptr [rsp+1E8h+pvt], 0
0x1800bfd13  jnz     loc_1800C0263
0x1800bfd19  mov     qword ptr [rsp+1E8h+plLbound], r14
0x1800bfd1e  mov     rax, [rbx]
0x1800bfd21  lea     r8, [rsp+1E8h+plLbound]
0x1800bfd26  lea     rdx, _GUID_f7063da8_8359_439c_9297_bbc5299a7d87
0x1800bfd2d  mov     rcx, rbx
0x1800bfd30  mov     rax, [rax]
0x1800bfd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfd38  test    eax, eax
0x1800bfd3a  jz      loc_1800C076A
0x1800bfd40  mov     rbx, r14
0x1800bfd43  mov     qword ptr [rsp+1E8h+var_160], rbx
0x1800bfd4b  test    rbx, rbx
0x1800bfd4e  jz      loc_1800C0263
0x1800bfd54  mov     [rsp+1E8h+psa], r14
0x1800bfd59  lea     r14, aIrawelementpro_0; "IRawElementProviderFragment::GetRuntime"...
0x1800bfd60  mov     qword ptr [rsp+1E8h+plLbound], r14
0x1800bfd65  xor     r12d, r12d
0x1800bfd68  mov     [rsp+1E8h+var_180], r12
0x1800bfd6d  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bfd74  jnz     loc_1800C0913
0x1800bfd7a  mov     rax, [rbx]
0x1800bfd7d  lea     rdx, [rsp+1E8h+psa]
0x1800bfd82  mov     rcx, rbx
0x1800bfd85  mov     rax, [rax+20h]
0x1800bfd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfd8e  mov     edi, eax
0x1800bfd90  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bfd97  jnz     loc_1800C094A
0x1800bfd9d  cmp     edi, 80040201h
0x1800bfda3  jz      loc_1800C08D0
0x1800bfda9  test    edi, edi
0x1800bfdab  js      loc_1800C01B6
0x1800bfdb1  mov     rcx, [rsp+1E8h+psa]; psa
0x1800bfdb6  test    rcx, rcx
0x1800bfdb9  jz      loc_1800C01B6
0x1800bfdbf  mov     qword ptr [rsp+1E8h+var_1A0], r12
0x1800bfdc4  mov     dword ptr [rsp+1E8h+var_1A0+8], r12d
0x1800bfdc9  mov     qword ptr [rsp+1E8h+var_1A0+10h], r12
0x1800bfdce  mov     qword ptr [rsp+1E8h+var_1A0], rcx
0x1800bfdd3  call    cs:__imp_SafeArrayGetDim
0x1800bfdd9  cmp     eax, 1
0x1800bfddc  jnz     loc_1800C062D
0x1800bfde2  mov     [rsp+1E8h+pvt], r12w
0x1800bfde8  lea     rdx, [rsp+1E8h+pvt]; pvt
0x1800bfded  mov     rcx, qword ptr [rsp+1E8h+var_1A0]; psa
0x1800bfdf2  call    cs:__imp_SafeArrayGetVartype
0x1800bfdf8  mov     edi, eax
0x1800bfdfa  test    eax, eax
0x1800bfdfc  js      loc_1800C06C2
0x1800bfe02  movzx   eax, [rsp+1E8h+pvt]
0x1800bfe07  cmp     ax, 3
0x1800bfe0b  jnz     loc_1800C0993
0x1800bfe11  mov     [rsp+1E8h+plLbound], r12d
0x1800bfe16  mov     [rsp+1E8h+plUbound], r12d
0x1800bfe1b  lea     r8, [rsp+1E8h+plLbound]; plLbound
0x1800bfe20  mov     edx, 1; nDim
0x1800bfe25  mov     rcx, qword ptr [rsp+1E8h+var_1A0]; psa
0x1800bfe2a  call    cs:__imp_SafeArrayGetLBound
0x1800bfe30  mov     edi, eax
0x1800bfe32  test    eax, eax
0x1800bfe34  js      loc_1800C05CF
0x1800bfe3a  lea     r8, [rsp+1E8h+plUbound]; plUbound
0x1800bfe3f  mov     edx, 1; nDim
0x1800bfe44  mov     rcx, qword ptr [rsp+1E8h+var_1A0]; psa
0x1800bfe49  call    cs:__imp_SafeArrayGetUBound
0x1800bfe4f  mov     edi, eax
0x1800bfe51  test    eax, eax
0x1800bfe53  js      loc_1800C0623
0x1800bfe59  mov     eax, [rsp+1E8h+plUbound]
0x1800bfe5d  sub     eax, [rsp+1E8h+plLbound]
0x1800bfe61  inc     eax
0x1800bfe63  mov     dword ptr [rsp+1E8h+var_1A0+8], eax
0x1800bfe67  lea     rdx, [rsp+1E8h+var_1A0+10h]; ppvData
0x1800bfe6c  mov     rcx, qword ptr [rsp+1E8h+var_1A0]; psa
0x1800bfe71  call    cs:__imp_SafeArrayAccessData
0x1800bfe77  mov     edi, eax
0x1800bfe79  test    eax, eax
0x1800bfe7b  js      loc_1800C0989
0x1800bfe81  mov     ecx, dword ptr [rsp+1E8h+var_1A0+8]
0x1800bfe85  mov     eax, 4
  ... truncated ...
```
