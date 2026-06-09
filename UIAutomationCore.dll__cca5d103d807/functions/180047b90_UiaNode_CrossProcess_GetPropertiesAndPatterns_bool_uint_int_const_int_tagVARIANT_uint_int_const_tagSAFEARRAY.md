# UiaNode::CrossProcess_GetPropertiesAndPatterns(bool,uint,int const *,int,tagVARIANT *,uint,int const *,tagSAFEARRAY * *)

- ea: `0x180047b90`
- end: `0x180048a33`
- name: `?CrossProcess_GetPropertiesAndPatterns@UiaNode@@UEAAJ_NIPEBHHPEAUtagVARIANT@@I1PEAPEAUtagSAFEARRAY@@@Z`
- size: `3747`
- prototype: `__int64 __fastcall(UiaNode *__hidden this, bool, unsigned int, const int *, int, struct tagVARIANT *, unsigned int, const int *, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800248f0`
- `0x180046be0`

## callees

- `0x180014c64`
- `0x180014d0c`
- `0x180015cd8`
- `0x18001ce34`
- `0x180022548`
- `0x18002f580`
- `0x180032724`
- `0x180033e04`
- `0x180041950`
- `0x1800467ac`
- `0x180047b90`
- `0x180048a3c`
- `0x180048ab0`
- `0x18004a5c0`
- `0x180061314`
- `0x180093850`
- `0x1800bd9fc`
- `0x1800bed0c`
- `0x1800c88bc`
- `0x180133550`
- `0x1801615cc`
- `0x1801a4e68`
- `0x1801af4bc`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047dda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047dda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047e08`
- `OLEAUT32!__imp_VariantInit` at `0x180047c6f`
- `OLEAUT32!__imp_VariantInit` at `0x180047d0c`
- `OLEAUT32!__imp_VariantInit` at `0x180047c6f`
- `OLEAUT32!__imp_VariantInit` at `0x180047d0c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180048290`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800484c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180048290`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800484c4`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800483a2`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800483a2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180048429`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180048429`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180048406`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180048406`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180048461`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180048461`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800484ad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800484ad`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800483c4`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800483c4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004872f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004872f`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800486f0`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800486f0`

## string_xrefs

- `0x180048483`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800487cf`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004886a`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180047cac`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x180047d3d`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800480e4`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800485f1`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x180048854`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004888c`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800488cd`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004896e`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x180048980`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x180048992`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800489a4`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800486a0`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`
- `0x1800486ca`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall UiaNode::CrossProcess_GetPropertiesAndPatterns(
        UiaNode *this,
        bool a2,
        unsigned int a3,
        const int *a4,
        int a5,
        struct tagVARIANT *a6,
        unsigned int a7,
        const int *a8,
        struct tagSAFEARRAY **a9)
{
  unsigned int v10; // edi
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  void *v13; // rax
  const char *v14; // r9
  void *v15; // r14
  unsigned __int64 v16; // rax
  const char *v17; // r9
  void *v18; // r15
  unsigned __int64 v19; // rax
  struct tagVARIANT *v20; // rdx
  VARIANTARG *v21; // rbx
  __int64 v22; // r9
  int v23; // ebx
  unsigned __int64 v24; // rax
  VARIANTARG *v25; // rsi
  unsigned int v26; // r9d
  unsigned int i; // r13d
  unsigned __int64 v28; // rbx
  const int *v29; // r8
  int v30; // edx
  __int64 v31; // rsi
  int v32; // edi
  GUID **v33; // rbx
  unsigned __int64 v34; // rax
  _QWORD *v35; // rsi
  const char *v36; // r9
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  _DWORD *v39; // rdi
  const char *v40; // r9
  __int64 size_of; // rax
  __int64 v42; // rbx
  __int64 *v43; // r8
  __int64 *v44; // r9
  _QWORD *v45; // rcx
  __int64 v46; // rax
  unsigned __int64 v47; // rbx
  __int64 v48; // rcx
  unsigned int j; // r13d
  const struct PatternInfo *PatternInfo; // rax
  unsigned int v51; // r10d
  UiaNode *v52; // rdx
  __int64 v53; // r11
  unsigned int v54; // r13d
  unsigned int v55; // ebx
  unsigned int v56; // ecx
  UiaNode *v57; // rax
  struct tagVARIANT *v58; // r13
  int v59; // eax
  unsigned int v60; // r9d
  unsigned int v61; // edx
  struct tagVARIANT *v62; // r13
  int v63; // ecx
  int v64; // ecx
  unsigned int v65; // r8d
  __int64 v66; // rdx
  VARIANTARG *v67; // r9
  __int64 v68; // rcx
  struct tagSAFEARRAY **v69; // rax
  struct tagSAFEARRAY *v70; // rcx
  const char *v71; // r9
  __int64 result; // rax
  int v73; // edx
  unsigned int v74; // ecx
  VARIANTARG *v75; // r10
  IRecordInfo *pRecInfo; // xmm1_8
  SAFEARRAY *v77; // rcx
  HRESULT Vartype; // eax
  int v79; // ebx
  unsigned int v80; // edx
  unsigned int v81; // r8d
  __int64 v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // rcx
  int v85; // eax
  __int64 v86; // rax
  IErrorInfo *v87; // rax
  IErrorInfo *v88; // rbx
  __int64 v89; // rdx
  int PropertiesAndPatterns; // eax
  __int64 v91; // rdx
  int ProviderInfoString; // eax
  struct UserDefinedPropertyInfo *k; // rbx
  int v94; // [rsp+20h] [rbp-168h]
  int v95; // [rsp+20h] [rbp-168h]
  unsigned int v96; // [rsp+70h] [rbp-118h]
  VARTYPE pvt; // [rsp+74h] [rbp-114h] BYREF
  int v98; // [rsp+78h] [rbp-110h]
  SAFEARRAY *v99; // [rsp+80h] [rbp-108h] BYREF
  unsigned int v100; // [rsp+88h] [rbp-100h]
  unsigned int v101; // [rsp+8Ch] [rbp-FCh] BYREF
  LONG plUbound; // [rsp+90h] [rbp-F8h] BYREF
  LONG plLbound; // [rsp+94h] [rbp-F4h] BYREF
  int v104; // [rsp+98h] [rbp-F0h]
  unsigned int v105; // [rsp+A0h] [rbp-E8h] BYREF
  struct tagVARIANT *v106; // [rsp+A8h] [rbp-E0h]
  __int128 v107; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v108; // [rsp+C0h] [rbp-C8h]
  SAFEARRAY *v109; // [rsp+C8h] [rbp-C0h]
  int v110; // [rsp+D0h] [rbp-B8h]
  void *ppvData; // [rsp+D8h] [rbp-B0h] BYREF
  unsigned int v112; // [rsp+E0h] [rbp-A8h] BYREF
  VARIANTARG *v113; // [rsp+E8h] [rbp-A0h]
  SAFEARRAY *psa; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v115; // [rsp+F8h] [rbp-90h] BYREF
  __int64 v116; // [rsp+108h] [rbp-80h]
  __int64 v117; // [rsp+110h] [rbp-78h]
  __int64 v118; // [rsp+118h] [rbp-70h]
  void *v119; // [rsp+120h] [rbp-68h]
  void *v120; // [rsp+128h] [rbp-60h]
  _QWORD *v121; // [rsp+130h] [rbp-58h]
  _DWORD *v122; // [rsp+138h] [rbp-50h]
  __int64 v123; // [rsp+140h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v10 = 0;
  v11 = a3;
  v12 = 8LL * a3;
  if ( !is_mul_ok(a3, 8u) )
    v12 = -1;
  v13 = operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
  try
  {
    v15 = v13;
    v119 = v13;
    if ( !v13 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x3D4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        v14);
    v16 = 4 * v11;
    if ( !is_mul_ok(v11, 4u) )
      v16 = -1;
    v18 = operator new[](v16, (const struct std::nothrow_t *)std::nothrow);
    v120 = v18;
    if ( !v18 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        v17);
    v105 = 0;
    v19 = 24 * v11;
    if ( !is_mul_ok(v11, 0x18u) )
      v19 = -1;
    v20 = (struct tagVARIANT *)operator new[](v19, (const struct std::nothrow_t *)std::nothrow);
    v106 = v20;
    if ( v20 )
    {
      if ( a3 )
      {
        do
        {
          v21 = &v20[v10];
          VariantInit(v21);
          v21->llVal = 0;
          ++v10;
          v20 = v106;
        }
        while ( v10 < a3 );
      }
      v105 = a3;
      v10 = 0;
      v22 = 0;
      v23 = -2147024882;
    }
    else
    {
      v23 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
        (const char *)0x8007000ELL,
        v94);
      v22 = 2147942414LL;
    }
    if ( (int)v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DA,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)v22,
        v94);
    v112 = 0;
    v24 = 24 * v11;
    if ( !is_mul_ok(v11, 0x18u) )
      v24 = -1;
    v25 = (VARIANTARG *)operator new[](v24, (const struct std::nothrow_t *)std::nothrow);
    v113 = v25;
    if ( v25 )
    {
      if ( a3 )
      {
        do
        {
          VariantInit(&v25[v10]);
          v25[v10++].llVal = 0;
        }
        while ( v10 < a3 );
      }
      v112 = a3;
      v23 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
        (const char *)0x8007000ELL,
        v94);
    }
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DD,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)(unsigned int)v23,
        v94);
    v26 = 0;
    v96 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= a3 )
      {
        v34 = 8LL * a7;
        if ( !is_mul_ok(a7, 8u) )
          v34 = -1;
        v35 = operator new[](v34, (const struct std::nothrow_t *)std::nothrow);
        v121 = v35;
        if ( !v35 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x418,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            v36);
        v37 = 4LL * a7;
        if ( !is_mul_ok(a7, 4u) )
          v37 = -1;
        v39 = operator new[](v37, (const struct std::nothrow_t *)std::nothrow);
        v122 = v39;
        if ( !v39 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x41B,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            v40);
        v107 = 0;
        v108 = 0;
        if ( a7 )
        {
          size_of = std::_Get_size_of_n<8>(a7, v38, 0);
          v42 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
          v44 = (__int64 *)*((_QWORD *)&v107 + 1);
          v43 = (__int64 *)v107;
          v45 = (_QWORD *)v42;
          while ( v43 != v44 )
          {
            v46 = *v43;
            *v43 = 0;
            *v45++ = v46;
            ++v43;
          }
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>>(v45);
          std::vector<wil::com_ptr_t<IA2ProxyTextRange,wil::err_exception_policy>>::_Change_array(&v107, v42, 0, a7);
        }
        v101 = 0;
        v47 = ((unsigned __int64)a7 + 31) >> 5;
        v115 = 0;
        v116 = 0;
        if ( v47 )
        {
          std::vector<unsigned int>::_Buy_nonzero(&v115, ((unsigned __int64)a7 + 31) >> 5, 0);
          v48 = std::_Uninitialized_fill_n<std::allocator<unsigned int>>(v115, ((unsigned __int64)a7 + 31) >> 5, &v101);
          *((_QWORD *)&v115 + 1) = v48;
        }
        else
        {
          v48 = *((_QWORD *)&v115 + 1);
        }
        if ( v47 < (v48 - (__int64)v115) >> 2 && (_QWORD)v115 + 4 * v47 != v48 )
          *((_QWORD *)&v115 + 1) = v115 + 4 * v47;
        v117 = a7;
        if ( (a7 & 0x1F) != 0 )
          *(_DWORD *)(v115 + 4 * v47 - 4) &= (1 << (a7 & 0x1F)) - 1;
        for ( j = 0; j < a7; ++j )
        {
          v39[j] = a8[j];
          PatternInfo = Schema::GetPatternInfo(a8[j]);
          v35[j] = PatternInfo;
          if ( !PatternInfo )
          {
            v99 = 0;
            if ( CreateErrorInfo((ICreateErrorInfo **)&v99) >= 0 )
            {
              (*(void (__fastcall **)(SAFEARRAY *, const wchar_t *))(*(_QWORD *)&v99->cDims + 40LL))(
                v99,
                L"Unknown pattern ID");
              v87 = (IErrorInfo *)QI<IErrorInfo>(v99);
              v88 = v87;
              if ( v87 )
                SetErrorInfo(0, v87);
              if ( v88 )
                ((void (__fastcall *)(IErrorInfo *))v88->lpVtbl->Release)(v88);
            }
            if ( v99 )
              (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v99->cDims + 16LL))(v99);
            std::vector<winrt::Windows::UI::UIAutomation::Core::AutomationRemoteOperationOperandId>::_Tidy(&v115);
            std::vector<wil::com_ptr_t<IUIAutomationProxyFactoryEntry,wil::err_exception_policy>>::_Tidy(&v107);
            operator delete(v39);
            operator delete(v35);
            StructArrayPair<tagVARIANT>::SafeRelease(&v112);
            StructArrayPair<tagVARIANT>::SafeRelease(&v105);
            operator delete(v18);
            operator delete(v15);
            return 2147942487LL;
          }
          if ( *((_QWORD *)&v107 + 1) == v108 )
          {
            std::vector<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>::_Emplace_reallocate<std::nullptr_t>(
              &v107,
              *((_QWORD *)&v107 + 1),
              0);
          }
          else
          {
            **((_QWORD **)&v107 + 1) = 0;
            *((_QWORD *)&v107 + 1) += 8LL;
          }
        }
        v51 = a7;
        v100 = a7;
        v52 = this;
        v53 = *((_QWORD *)this + 27);
        v118 = v53;
        v54 = 0;
        v55 = 0;
        while ( 2 )
        {
          v98 = v55;
          if ( v55 >= *((_DWORD *)v52 + 48) )
            goto LABEL_79;
          if ( v55 )
          {
            v60 = 0;
            v61 = 0;
            if ( v96 )
            {
              v62 = v106;
              do
              {
                if ( !v62[v61].vt )
                {
                  *((_DWORD *)v18 + v60) = *((_DWORD *)v18 + v61);
                  *((_QWORD *)v15 + v60++) = *((_QWORD *)v15 + v61);
                }
                ++v61;
              }
              while ( v61 < v96 );
              v54 = 0;
            }
            v56 = v60;
            v96 = v60;
            v51 = 0;
            v100 = 0;
            if ( a7 )
            {
              do
              {
                v63 = *(_DWORD *)(v115 + 4 * ((unsigned __int64)v54 >> 5));
                if ( !_bittest(&v63, v54 & 0x1F) )
                {
                  v64 = a8[v54];
                  v39[v51] = v64;
                  v35[v51] = Schema::GetPatternInfo(v64);
                  v51 = ++v100;
                }
                ++v54;
              }
              while ( v54 < a7 );
              v55 = v98;
              v53 = v118;
              v56 = v96;
            }
            v52 = this;
          }
          else
          {
            v56 = v96;
          }
          if ( !v56 && !v51 )
          {
LABEL_79:
            v65 = 0;
            if ( a3 )
            {
              v66 = 0;
              v67 = v113;
              do
              {
                v68 = v66;
                *(_OWORD *)&a6[v68].vt = *(_OWORD *)&v67[v66].vt;
                a6[v68].pRecInfo = v67[v66].pRecInfo;
                if ( !a5 && !a6[v66].vt )
                {
                  a6[v66].vt = 13;
                  a6[v66].llVal = (LONGLONG)g_punkNotSupportedValue;
                }
                v67[v66].vt = 0;
                ++v65;
                ++v66;
              }
              while ( v65 < a3 );
            }
            v69 = (struct tagSAFEARRAY **)ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_ec403018b2b048e9b8cca220b05cfc06___(
                                            &psa,
                                            v107,
                                            (__int64)(*((_QWORD *)&v107 + 1) - v107) >> 3);
            v70 = *v69;
            *v69 = 0;
            *a9 = v70;
            if ( psa )
              SafeArrayDestroy(psa);
            std::vector<winrt::Windows::UI::UIAutomation::Core::AutomationRemoteOperationOperandId>::_Tidy(&v115);
            std::vector<wil::com_ptr_t<IUIAutomationProxyFactoryEntry,wil::err_exception_policy>>::_Tidy(&v107);
            operator delete(v39);
            operator delete(v35);
            StructArrayPair<tagVARIANT>::SafeRelease(&v112);
            StructArrayPair<tagVARIANT>::SafeRelease(&v105);
            operator delete(v18);
            operator delete(v15);
            return 0;
          }
          v57 = (UiaNode *)((char *)v52 - 48);
          v99 = 0;
          v58 = v106;
          if ( v53 )
          {
            v95 = v55;
            v59 = InProcClientAPIStub::InvokeInProcAPI(v53, 142, v57, a2);
            if ( v59 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x472,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                (const char *)(unsigned int)v59,
                v55);
          }
          else
          {
            PropertiesAndPatterns = UiaNode::ProviderGetPropertiesAndPatterns(
                                      v57,
                                      a2,
                                      v55,
                                      v56,
                                      (const int *)v18,
                                      (const struct PropertyInfo **)v15,
                                      1,
                                      v106,
                                      v51,
                                      v39,
                                      (const struct PatternInfo **)v35,
                                      &v99);
            if ( PropertiesAndPatterns < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x481,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                (const char *)(unsigned int)PropertiesAndPatterns,
                v95);
          }
          v73 = 0;
          v74 = 0;
          if ( a3 )
          {
            v75 = v113;
            do
            {
              if ( !v75[v74].vt )
              {
                if ( v58[v73].vt )
                {
                  pRecInfo = v58[v73].pRecInfo;
                  *(_OWORD *)&v75[v74].vt = *(_OWORD *)&v58[v73].vt;
                  v75[v74].pRecInfo = pRecInfo;
                  v58[v73].vt = 3;
                }
                ++v73;
              }
              ++v74;
            }
            while ( v74 < a3 );
          }
          v77 = v99;
          v54 = 0;
          if ( !v99 )
            goto LABEL_109;
          v110 = 0;
          ppvData = 0;
          v109 = v99;
          if ( SafeArrayGetDim(v99) == 1 )
          {
            pvt = 0;
            Vartype = SafeArrayGetVartype(v109, &pvt);
            v79 = Vartype;
            if ( Vartype < 0 )
            {
              v91 = 95;
              goto LABEL_147;
            }
            if ( pvt == 13 )
            {
              plLbound = 0;
              plUbound = 0;
              Vartype = SafeArrayGetLBound(v109, 1u, &plLbound);
              v79 = Vartype;
              if ( Vartype < 0 )
              {
                v91 = 111;
              }
              else
              {
                Vartype = SafeArrayGetUBound(v109, 1u, &plUbound);
                v79 = Vartype;
                if ( Vartype < 0 )
                {
                  v91 = 112;
                }
                else
                {
                  v110 = plUbound - plLbound + 1;
                  Vartype = SafeArrayAccessData(v109, &ppvData);
                  v79 = Vartype;
                  if ( Vartype >= 0 )
                  {
                    v79 = 0;
                    goto LABEL_103;
                  }
                  v91 = 115;
                }
              }
LABEL_147:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v91,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)Vartype,
                v95);
LABEL_103:
              if ( v79 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                  (const char *)(unsigned int)v79,
                  v95);
              v80 = v110;
              if ( v110 )
              {
                v81 = 0;
                v101 = 0;
                while ( v54 < a7 )
                {
                  psa = (SAFEARRAY *)((unsigned __int64)v54 >> 5);
                  v104 = 1 << v54;
                  if ( ((1 << v54) & *(_DWORD *)(v115 + 4LL * (_QWORD)psa)) == 0 )
                  {
                    if ( v80 <= v81 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x4AB,
                        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                        (const char *)0x8000FFFFLL,
                        v95);
                    v82 = *((_QWORD *)ppvData + v81);
                    if ( v82 )
                    {
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v82 + 8LL))(*((_QWORD *)ppvData + v81));
                      v123 = 0;
                      v83 = v54;
                      v84 = *(_QWORD *)(v107 + 8LL * v54);
                      *(_QWORD *)(v107 + 8LL * v54) = v82;
                      if ( v84 )
                      {
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                        v83 = v54;
                      }
                      *(_DWORD *)(v115 + 4LL * (_QWORD)psa) |= v104;
                      v85 = UiaNode::EmplacePatternProvider((UiaNode *)((char *)this - 48), a8[v83], v98);
                      if ( v85 < 0 )
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0x4B1,
                          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                          (const char *)(unsigned int)v85,
                          v95);
                      v80 = v110;
                      v81 = v101;
                    }
                    v101 = ++v81;
                  }
                  ++v54;
                }
                v54 = 0;
              }
              if ( v109 )
                SafeArrayUnaccessData(v109);
              v55 = v98;
              v77 = v99;
LABEL_109:
              if ( v77 )
                SafeArrayDestroy(v77);
              ++v55;
              v51 = v100;
              v53 = v118;
              v52 = this;
              continue;
            }
            v89 = 106;
          }
          else
          {
            v89 = 92;
          }
          break;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v89,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)0x80070057LL,
          v95);
        v79 = -2147024809;
        goto LABEL_103;
      }
      v28 = i;
      a6[v28].vt = 13;
      a6[v28].llVal = (LONGLONG)g_punkNotSupportedValue;
      v25[v28].vt = 0;
      v29 = a4;
      v30 = a4[i];
      if ( v30 == 30107 )
      {
        ProviderInfoString = UiaNode::GetProviderInfoString((UiaNode *)((char *)this - 48), &v25[v28].bstrVal);
        if ( ProviderInfoString < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3EE,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            (const char *)(unsigned int)ProviderInfoString,
            v94);
        v25[i].vt = 8;
        v26 = v96;
      }
      else
      {
        if ( v30 == 30008 )
        {
          if ( UiaNode::IsSurrogateOfCrossMachine((UiaNode *)((char *)this - 48)) )
          {
            v25[i].vt = 11;
            v25[i].iVal = 0;
            continue;
          }
        }
        else if ( v30 == 30020 )
        {
          v86 = *((_QWORD *)this + 26);
          if ( v86 )
          {
            if ( *(_BYTE *)(v86 + 60) )
            {
              v25[i].vt = 13;
              v25[i].llVal = (LONGLONG)g_punkNotSupportedValue;
              continue;
            }
          }
        }
        v31 = v26;
        *((_DWORD *)v18 + v26) = v30;
        v32 = v29[i];
        if ( v32 )
        {
          EnterCriticalSection(&_schemaLock);
          if ( (unsigned int)(v32 - 30000) > 0xAF )
          {
            for ( k = g_pUserDefinedProperties; k; k = *(struct UserDefinedPropertyInfo **)k )
            {
              if ( *((_DWORD *)k + 6) == v32 )
              {
                v33 = (GUID **)((char *)k + 16);
                goto LABEL_32;
              }
            }
            v33 = 0;
          }
          else
          {
            v33 = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(v32 - 30000)];
          }
LABEL_32:
          LeaveCriticalSection(&_schemaLock);
          *((_QWORD *)v15 + v31) = v33;
          if ( !v33 )
          {
            Error::SetError(L"Unknown property ID", 0);
            StructArrayPair<tagVARIANT>::SafeRelease(&v112);
            StructArrayPair<tagVARIANT>::SafeRelease(&v105);
            operator delete(v18);
            operator delete(v15);
            return 2147942487LL;
          }
          v26 = v96;
        }
        else
        {
          *((_QWORD *)v15 + v26) = 0;
        }
        v96 = ++v26;
        v25 = v113;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4D2,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                           v71);
  }
  return result;
}

```

## disassembly

```asm
0x180047b90  mov     rax, rsp
0x180047b93  mov     [rax+20h], r9
0x180047b97  mov     [rax+18h], r8d
0x180047b9b  mov     [rax+10h], dl
0x180047b9e  mov     [rax+8], rcx
0x180047ba2  push    rbx
0x180047ba3  push    rsi
0x180047ba4  push    rdi
0x180047ba5  push    r12
0x180047ba7  push    r13
0x180047ba9  push    r14
0x180047bab  push    r15
0x180047bad  sub     rsp, 150h
0x180047bb4  mov     r13d, r8d
0x180047bb7  xor     edi, edi
0x180047bb9  mov     esi, r13d
0x180047bbc  lea     eax, [rdi+8]
0x180047bbf  mul     r13
0x180047bc2  lea     r12, [rdi-1]
0x180047bc6  cmovb   rax, r12
0x180047bca  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180047bd1  mov     rdx, rbx; struct std::nothrow_t *
0x180047bd4  mov     rcx, rax; unsigned __int64
0x180047bd7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047bdc  mov     r14, rax
0x180047bdf  mov     [rsp+188h+var_68], rax
0x180047be7  mov     rcx, [rsp+188h]; this
0x180047bef  test    rax, rax
0x180047bf2  jz      loc_18004896E
0x180047bf8  lea     eax, [rdi+4]
0x180047bfb  mul     rsi
0x180047bfe  cmovb   rax, r12
0x180047c02  mov     rdx, rbx; struct std::nothrow_t *
0x180047c05  mov     rcx, rax; unsigned __int64
0x180047c08  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047c0d  mov     r15, rax
0x180047c10  mov     [rsp+188h+var_60], rax
0x180047c18  mov     rcx, [rsp+188h]; this
0x180047c20  test    rax, rax
0x180047c23  jz      loc_180048980
0x180047c29  mov     [rsp+188h+var_E8], edi
0x180047c30  lea     eax, [rdi+18h]
0x180047c33  mul     rsi
0x180047c36  cmovb   rax, r12
0x180047c3a  mov     rdx, rbx; struct std::nothrow_t *
0x180047c3d  mov     rcx, rax; unsigned __int64
0x180047c40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047c45  mov     rdx, rax
0x180047c48  mov     [rsp+188h+var_E0], rax
0x180047c50  test    rax, rax
0x180047c53  jz      loc_180048690
0x180047c59  lea     r12d, [rdi+1]
0x180047c5d  test    r13d, r13d
0x180047c60  jz      short loc_180047C8D
0x180047c62  mov     eax, edi
0x180047c64  lea     rcx, [rax+rax*2]
0x180047c68  lea     rbx, [rdx+rcx*8]
0x180047c6c  mov     rcx, rbx; pvarg
0x180047c6f  call    cs:__imp_VariantInit
0x180047c75  mov     qword ptr [rbx+8], 0
0x180047c7d  add     edi, r12d
0x180047c80  cmp     edi, r13d
0x180047c83  mov     rdx, [rsp+188h+var_E0]
0x180047c8b  jb      short loc_180047C62
0x180047c8d  mov     [rsp+188h+var_E8], r13d
0x180047c95  xor     edi, edi
0x180047c97  mov     r9d, edi; char *
0x180047c9a  mov     ebx, 8007000Eh
0x180047c9f  mov     rcx, [rsp+188h]; this
0x180047ca7  test    r9d, r9d
0x180047caa  jns     short loc_180047CBD
0x180047cac  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x180047cb3  mov     edx, 3DAh; void *
0x180047cb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047cbd  mov     [rsp+188h+var_A8], edi
0x180047cc4  mov     eax, 18h
0x180047cc9  mul     rsi
0x180047ccc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180047cd3  cmovb   rax, rcx
0x180047cd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180047cde  mov     rcx, rax; unsigned __int64
0x180047ce1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047ce6  mov     rsi, rax
0x180047ce9  mov     [rsp+188h+var_A0], rax
0x180047cf1  test    rax, rax
0x180047cf4  jz      loc_1800486BF
0x180047cfa  test    r13d, r13d
0x180047cfd  jz      short loc_180047D22
0x180047cff  mov     eax, edi
0x180047d01  lea     rcx, [rax+rax*2]
0x180047d05  lea     rbx, [rsi+rcx*8]
0x180047d09  mov     rcx, rbx; pvarg
0x180047d0c  call    cs:__imp_VariantInit
0x180047d12  mov     qword ptr [rbx+8], 0
0x180047d1a  add     edi, r12d
0x180047d1d  cmp     edi, r13d
0x180047d20  jb      short loc_180047CFF
0x180047d22  mov     [rsp+188h+var_A8], r13d
0x180047d2a  xor     edi, edi
0x180047d2c  mov     ebx, edi
0x180047d2e  mov     rcx, [rsp+188h]; this
0x180047d36  test    ebx, ebx
0x180047d38  jns     short loc_180047D4E
0x180047d3a  mov     r9d, ebx; char *
0x180047d3d  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x180047d44  mov     edx, 3DDh; void *
0x180047d49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047d4e  mov     r9d, edi
0x180047d51  mov     [rsp+188h+var_118], edi
0x180047d55  mov     r13d, edi
0x180047d58  mov     r11d, 0Dh
0x180047d5e  cmp     r13d, [rsp+188h+arg_10]
0x180047d66  jnb     loc_180047E40
0x180047d6c  mov     edi, r13d
0x180047d6f  lea     rbx, [rdi+rdi*2]
0x180047d73  mov     rcx, [rsp+188h+arg_28]
0x180047d7b  mov     [rcx+rbx*8], r11w
0x180047d80  mov     rax, cs:?g_punkNotSupportedValue@@3PEAUIUnknown@@EA; IUnknown * g_punkNotSupportedValue
0x180047d87  mov     [rcx+rbx*8+8], rax
0x180047d8c  xor     r10d, r10d
0x180047d8f  mov     [rsi+rbx*8], r10w
0x180047d94  mov     r8, [rsp+188h+arg_18]
0x180047d9c  mov     edx, [r8+rdi*4]
0x180047da0  cmp     edx, 759Bh
0x180047da6  jz      loc_1800488A5
0x180047dac  cmp     edx, 7538h
0x180047db2  jz      loc_180048665
0x180047db8  cmp     edx, 7544h
0x180047dbe  jz      loc_18004862D
0x180047dc4  mov     esi, r9d
0x180047dc7  mov     [r15+rsi*4], edx
0x180047dcb  mov     edi, [r8+rdi*4]
0x180047dcf  test    edi, edi
0x180047dd1  jz      short loc_180047E38
0x180047dd3  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047dda  call    cs:__imp_EnterCriticalSection
0x180047de0  lea     eax, [rdi-7530h]
0x180047de6  cmp     eax, 0AFh
0x180047deb  ja      loc_180048900
0x180047df1  mov     ebx, eax
0x180047df3  shl     rbx, 6
0x180047df7  lea     rax, off_1802DE930
0x180047dfe  add     rbx, rax
0x180047e01  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180047e08  call    cs:__imp_LeaveCriticalSection
0x180047e0e  mov     [r14+rsi*8], rbx
0x180047e12  test    rbx, rbx
0x180047e15  jz      loc_18004891A
0x180047e1b  mov     r9d, [rsp+188h+var_118]
0x180047e20  add     r9d, r12d
0x180047e23  mov     [rsp+188h+var_118], r9d
0x180047e28  mov     rsi, [rsp+188h+var_A0]
0x180047e30  add     r13d, r12d
0x180047e33  jmp     loc_180047D58
0x180047e38  xor     edi, edi
0x180047e3a  mov     [r14+rsi*8], rdi
0x180047e3e  jmp     short loc_180047E20
0x180047e40  mov     r13d, [rsp+188h+arg_30]
0x180047e48  mov     eax, 8
0x180047e4d  mul     r13
0x180047e50  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180047e57  cmovb   rax, rbx
0x180047e5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180047e62  mov     rcx, rax; unsigned __int64
0x180047e65  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047e6a  mov     rsi, rax
0x180047e6d  mov     [rsp+188h+var_58], rax
0x180047e75  mov     rcx, [rsp+188h]; this
0x180047e7d  test    rax, rax
0x180047e80  jz      loc_180048992
0x180047e86  lea     eax, [rbx+5]
0x180047e89  mul     r13
0x180047e8c  cmovb   rax, rbx
0x180047e90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180047e97  mov     rcx, rax; unsigned __int64
0x180047e9a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180047e9f  mov     rdi, rax
0x180047ea2  mov     [rsp+188h+var_50], rax
0x180047eaa  mov     rcx, [rsp+188h]; this
0x180047eb2  xor     r8d, r8d
0x180047eb5  test    rax, rax
0x180047eb8  jz      loc_1800489A4
0x180047ebe  xorps   xmm0, xmm0
0x180047ec1  movdqu  [rsp+188h+var_D8], xmm0
0x180047eca  mov     [rsp+188h+var_C8], r8
0x180047ed2  test    r13, r13
0x180047ed5  jz      short loc_180047F3D
0x180047ed7  mov     ecx, r13d
0x180047eda  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180047edf  mov     rcx, rax
0x180047ee2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180047ee7  mov     rbx, rax
0x180047eea  mov     r8, qword ptr [rsp+188h+var_D8]
0x180047ef2  mov     r9, qword ptr [rsp+188h+var_D8+8]
0x180047efa  mov     rcx, rax
0x180047efd  jmp     short loc_180047F17
0x180047eff  mov     rax, [r8]
0x180047f02  mov     qword ptr [r8], 0
0x180047f09  mov     [rcx], rax
0x180047f0c  mov     eax, 8
0x180047f11  add     rcx, rax
0x180047f14  add     r8, rax
0x180047f17  cmp     r8, r9
0x180047f1a  jnz     short loc_180047EFF
0x180047f1c  mov     rdx, rcx
0x180047f1f  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>>(wil::com_ptr_t<IUnknown,wil::err_exception_policy> *,wil::com_ptr_t<IUnknown,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<IUnknown,wil::err_exception_policy>> &)
0x180047f24  mov     r9, r13
0x180047f27  xor     r8d, r8d
0x180047f2a  mov     rdx, rbx
0x180047f2d  lea     rcx, [rsp+188h+var_D8]
0x180047f35  call    ?_Change_array@?$vector@V?$com_ptr_t@VIA2ProxyTextRange@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VIA2ProxyTextRange@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXQEAV?$com_ptr_t@VIA2ProxyTextRange@@Uerr_exception_policy@wil@@@wil@@_K1@Z; std::vector<wil::com_ptr_t<IA2ProxyTextRange,wil::err_exception_policy>>::_Change_array(wil::com_ptr_t<IA2ProxyTextRange,wil::err_exception_policy> * const,unsigned __int64,unsigned __int64)
0x180047f3a  xor     r8d, r8d
0x180047f3d  mov     [rsp+188h+var_FC], r8d
0x180047f45  lea     rbx, [r13+1Fh]
0x180047f49  shr     rbx, 5
0x180047f4d  xorps   xmm0, xmm0
0x180047f50  movdqu  [rsp+188h+var_90], xmm0
0x180047f59  mov     [rsp+188h+var_80], r8
0x180047f61  test    rbx, rbx
0x180047f64  jnz     loc_1800489B6
0x180047f6a  mov     rcx, qword ptr [rsp+188h+var_90+8]
0x180047f72  mov     rax, rcx
0x180047f75  mov     rdx, qword ptr [rsp+188h+var_90]
0x180047f7d  sub     rax, rdx
0x180047f80  sar     rax, 2
0x180047f84  cmp     rbx, rax
0x180047f87  jb      loc_1800489F1
0x180047f8d  mov     [rsp+188h+var_78], r13
0x180047f95  and     r13d, 1Fh
0x180047f99  jbe     short loc_180047FB2
0x180047f9b  mov     rdx, qword ptr [rsp+188h+var_90]
0x180047fa3  mov     ecx, r13d
0x180047fa6  mov     eax, r12d
0x180047fa9  shl     eax, cl
0x180047fab  sub     eax, r12d
0x180047fae  and     [rdx+rbx*4-4], eax
0x180047fb2  mov     r13d, r8d
0x180047fb5  cmp     r13d, [rsp+188h+arg_30]
0x180047fbd  jnb     short loc_18004800F
0x180047fbf  mov     ebx, r13d
0x180047fc2  mov     rcx, [rsp+188h+arg_38]
0x180047fca  mov     eax, [rcx+rbx*4]
0x180047fcd  mov     [rdi+rbx*4], eax
0x180047fd0  mov     ecx, [rcx+rbx*4]; int
0x180047fd3  call    ?GetPatternInfo@Schema@@SAPEBUPatternInfo@@H@Z; Schema::GetPatternInfo(int)
0x180047fd8  mov     [rsi+rbx*8], rax
0x180047fdc  xor     r8d, r8d
0x180047fdf  test    rax, rax
0x180047fe2  jz      loc_1800486E0
0x180047fe8  mov     rdx, qword ptr [rsp+188h+var_D8+8]
0x180047ff0  cmp     rdx, [rsp+188h+var_C8]
0x180047ff8  jz      loc_180048A0B
0x180047ffe  mov     [rdx], r8
0x180048001  add     qword ptr [rsp+188h+var_D8+8], 8
0x18004800a  add     r13d, r12d
0x18004800d  jmp     short loc_180047FB5
0x18004800f  mov     r10d, [rsp+188h+arg_30]
0x180048017  mov     [rsp+188h+var_100], r10d
0x18004801f  mov     rdx, [rsp+188h+arg_0]
0x180048027  mov     r11, [rdx+0D8h]
0x18004802e  mov     [rsp+188h+var_70], r11
0x180048036  xor     r13d, r13d
0x180048039  mov     ebx, r13d
0x18004803c  mov     [rsp+188h+var_110], ebx
0x180048040  cmp     ebx, [rdx+0C0h]
0x180048046  jnb     loc_1800481DB
0x18004804c  test    ebx, ebx
0x18004804e  jnz     loc_1800480F6
0x180048054  mov     ecx, [rsp+188h+var_118]
0x180048058  test    ecx, ecx
0x18004805a  jz      loc_1800487F3
0x180048060  lea     rax, [rdx-30h]
0x180048064  mov     [rsp+188h+var_108], r13
0x18004806c  lea     rdx, [rsp+188h+var_108]
0x180048074  mov     r13, [rsp+188h+var_E0]
0x18004807c  test    r11, r11
0x18004807f  jz      loc_180048801
0x180048085  movzx   r9d, [rsp+188h+arg_8]
0x18004808e  mov     [rsp+188h+var_120], rdx
0x180048093  mov     [rsp+188h+var_128], rsi
0x180048098  mov     [rsp+188h+var_130], rdi
0x18004809d  mov     dword ptr [rsp+188h+var_138], r10d
0x1800480a2  mov     [rsp+188h+var_140], r13
0x1800480a7  mov     [rsp+188h+var_148], r12d
0x1800480ac  mov     [rsp+188h+var_150], r14
0x1800480b1  mov     qword ptr [rsp+188h+var_158], r15
0x1800480b6  mov     dword ptr [rsp+188h+var_160], ecx
0x1800480ba  mov     dword ptr [rsp+188h+var_168], ebx; int
0x1800480be  mov     r8, rax
0x1800480c1  mov     edx, 8Eh
0x1800480c6  mov     rcx, r11
0x1800480c9  call    ?InvokeInProcAPI@InProcClientAPIStub@@SAJPEAUITargetContextInvoker@@W4Protocol_MethodId@@ZZ; InProcClientAPIStub::InvokeInProcAPI(ITargetContextInvoker *,Protocol_MethodId,...)
0x1800480ce  mov     rcx, [rsp+188h]; this
0x1800480d6  xor     r8d, r8d
0x1800480d9  test    eax, eax
0x1800480db  jns     loc_180048307
0x1800480e1  mov     r9d, eax; char *
0x1800480e4  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800480eb  mov     edx, 472h; void *
0x1800480f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
