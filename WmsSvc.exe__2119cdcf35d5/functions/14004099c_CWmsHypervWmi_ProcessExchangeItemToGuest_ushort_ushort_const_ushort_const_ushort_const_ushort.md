# CWmsHypervWmi::ProcessExchangeItemToGuest(ushort *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x14004099c`
- end: `0x14004163b`
- name: `?ProcessExchangeItemToGuest@CWmsHypervWmi@@AEAAJPEAGPEBG11PEAPEAG@Z`
- size: `3231`
- prototype: `__int64 __usercall@<rax>(CWmsHypervWmi *__hidden this@<rcx>, unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003c400`
- `0x1400404f0`
- `0x140040640`
- `0x140041650`
- `0x1400423c0`
- `0x14004257c`

## callees

- `0x14003c6e0`
- `0x14003edb8`
- `0x14003f918`
- `0x14004099c`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140040b48`
- `KERNEL32!IsDebuggerPresent` at `0x140040c32`
- `KERNEL32!IsDebuggerPresent` at `0x140040e21`
- `KERNEL32!IsDebuggerPresent` at `0x140040ea9`
- `KERNEL32!IsDebuggerPresent` at `0x140040f45`
- `KERNEL32!IsDebuggerPresent` at `0x140040fba`
- `KERNEL32!IsDebuggerPresent` at `0x140041038`
- `KERNEL32!IsDebuggerPresent` at `0x1400410d8`
- `KERNEL32!IsDebuggerPresent` at `0x140041197`
- `KERNEL32!IsDebuggerPresent` at `0x14004127d`
- `KERNEL32!IsDebuggerPresent` at `0x14004130c`
- `KERNEL32!IsDebuggerPresent` at `0x140041388`
- `KERNEL32!IsDebuggerPresent` at `0x140041420`
- `KERNEL32!IsDebuggerPresent` at `0x1400414ca`
- `KERNEL32!IsDebuggerPresent` at `0x140040b48`
- `KERNEL32!IsDebuggerPresent` at `0x140040c32`
- `KERNEL32!IsDebuggerPresent` at `0x140040e21`
- `KERNEL32!IsDebuggerPresent` at `0x140040ea9`
- `KERNEL32!IsDebuggerPresent` at `0x140040f45`
- `KERNEL32!IsDebuggerPresent` at `0x140040fba`
- `KERNEL32!IsDebuggerPresent` at `0x140041038`
- `KERNEL32!IsDebuggerPresent` at `0x1400410d8`
- `KERNEL32!IsDebuggerPresent` at `0x140041197`
- `KERNEL32!IsDebuggerPresent` at `0x14004127d`
- `KERNEL32!IsDebuggerPresent` at `0x14004130c`
- `KERNEL32!IsDebuggerPresent` at `0x140041388`
- `KERNEL32!IsDebuggerPresent` at `0x140041420`
- `KERNEL32!IsDebuggerPresent` at `0x1400414ca`
- `OLEAUT32!__imp_SysAllocString` at `0x140040aeb`
- `OLEAUT32!__imp_SysAllocString` at `0x140040e55`
- `OLEAUT32!__imp_SysAllocString` at `0x140040fe7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400413c9`
- `OLEAUT32!__imp_SysAllocString` at `0x140040aeb`
- `OLEAUT32!__imp_SysAllocString` at `0x140040e55`
- `OLEAUT32!__imp_SysAllocString` at `0x140040fe7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400413c9`
- `OLEAUT32!__imp_SysFreeString` at `0x14004150e`
- `OLEAUT32!__imp_SysFreeString` at `0x140041517`
- `OLEAUT32!__imp_SysFreeString` at `0x14004150e`
- `OLEAUT32!__imp_SysFreeString` at `0x140041517`
- `OLEAUT32!__imp_SysStringLen` at `0x140041340`
- `OLEAUT32!__imp_SysStringLen` at `0x140041340`
- `OLEAUT32!__imp_VariantInit` at `0x140040a3d`
- `OLEAUT32!__imp_VariantInit` at `0x140040a47`
- `OLEAUT32!__imp_VariantInit` at `0x140040a51`
- `OLEAUT32!__imp_VariantInit` at `0x140040a5b`
- `OLEAUT32!__imp_VariantInit` at `0x140040a65`
- `OLEAUT32!__imp_VariantInit` at `0x140040a6f`
- `OLEAUT32!__imp_VariantInit` at `0x140040a79`
- `OLEAUT32!__imp_VariantInit` at `0x140040a3d`
- `OLEAUT32!__imp_VariantInit` at `0x140040a47`
- `OLEAUT32!__imp_VariantInit` at `0x140040a51`
- `OLEAUT32!__imp_VariantInit` at `0x140040a5b`
- `OLEAUT32!__imp_VariantInit` at `0x140040a65`
- `OLEAUT32!__imp_VariantInit` at `0x140040a6f`
- `OLEAUT32!__imp_VariantInit` at `0x140040a79`
- `OLEAUT32!__imp_VariantClear` at `0x140041521`
- `OLEAUT32!__imp_VariantClear` at `0x14004152b`
- `OLEAUT32!__imp_VariantClear` at `0x140041535`
- `OLEAUT32!__imp_VariantClear` at `0x14004153f`
- `OLEAUT32!__imp_VariantClear` at `0x140041549`
- `OLEAUT32!__imp_VariantClear` at `0x140041553`
- `OLEAUT32!__imp_VariantClear` at `0x14004155d`
- `OLEAUT32!__imp_VariantClear` at `0x140041521`
- `OLEAUT32!__imp_VariantClear` at `0x14004152b`
- `OLEAUT32!__imp_VariantClear` at `0x140041535`
- `OLEAUT32!__imp_VariantClear` at `0x14004153f`
- `OLEAUT32!__imp_VariantClear` at `0x140041549`
- `OLEAUT32!__imp_VariantClear` at `0x140041553`
- `OLEAUT32!__imp_VariantClear` at `0x14004155d`
- `PROPSYS!VariantToInt32` at `0x140040d51`
- `PROPSYS!VariantToInt32` at `0x140040d51`

## string_xrefs

- `0x140040cc0`: `__PATH`
- `0x140040dc4`: `__PATH`
- `0x140040ae4`: `Msvm_VirtualSystemManagementService`
- `0x140040b08`: `bstrClassPath`
- `0x140040b50`: `bstrClassPath`
- `0x140040bca`: `Failed to get Msvm_VirtualSystemManagementService class`
- `0x140040c6c`: `Failed to get Hyper-V service object`
- `0x1400411bb`: `CWmsHypervWmi::ProcessExchangeItemToGuest - Msvm_VirtualSystemManagementService class path: '%s'\n`

## pseudocode

```c
__int64 __fastcall CWmsHypervWmi::ProcessExchangeItemToGuest(
        CWmsHypervWmi *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  struct IWbemClassObject *v6; // r13
  int TargetComputer; // ebx
  OLECHAR *v12; // r14
  const unsigned __int16 *v13; // r15
  unsigned int v14; // r12d
  __int64 v15; // r9
  __int64 v16; // r8
  CWmsHypervWmi *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned __int16 *v24; // rax
  int v25; // eax
  const unsigned __int16 *v27; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v28; // [rsp+28h] [rbp-D8h]
  int v29[2]; // [rsp+28h] [rbp-D8h]
  int v30[2]; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  BSTR v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  struct IWbemServices *v36; // [rsp+60h] [rbp-A0h] BYREF
  LONG plRet; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  struct IWbemClassObject *v42; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v45; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v46; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v47; // [rsp+E8h] [rbp-18h] BYREF
  VARIANTARG varIn; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG v49; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG v50; // [rsp+130h] [rbp+30h] BYREF

  v36 = 0;
  v6 = 0;
  v42 = 0;
  v40 = 0;
  v38 = 0;
  v35 = 0;
  plRet = 0;
  bstrString = 0;
  memset(&v45, 0, sizeof(v45));
  memset(&varIn, 0, sizeof(varIn));
  memset(&v47, 0, sizeof(v47));
  memset(&v46, 0, sizeof(v46));
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v50, 0, sizeof(v50));
  memset(&v49, 0, sizeof(v49));
  v39 = 0;
  v41 = 0;
  VariantInit(&pvarg);
  VariantInit(&v46);
  VariantInit(&v47);
  VariantInit(&varIn);
  VariantInit(&v45);
  VariantInit(&v49);
  VariantInit(&v50);
  TargetComputer = CWmsHypervWmi::GetTargetComputer((__int64)this, 1, a2, (IUnknown **)&v36, &v39);
  if ( TargetComputer < 0 )
  {
    v12 = 0;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - ERROR 0x%08X: %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      1711,
      L"CWmsHypervWmi::ProcessExchangeItemToGuest",
      TargetComputer,
      L"Failed to get target VM object\n");
    goto LABEL_82;
  }
  v34 = SysAllocString(L"Msvm_VirtualSystemManagementService");
  if ( v34 )
  {
    TargetComputer = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))v36->lpVtbl->GetObjectA)(
                       v36,
                       v34,
                       0,
                       0,
                       &v41,
                       0);
    if ( TargetComputer < 0 )
    {
      v14 = 1718;
      v29[0] = TargetComputer;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - ERROR 0x%08X: %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        1718,
        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
        *(_QWORD *)v29,
        L"Failed to get Msvm_VirtualSystemManagementService class");
      v13 = L"CHRLA";
LABEL_12:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v14,
        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
        v13,
        L"hr",
        TargetComputer);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v33) = TargetComputer;
        v32 = L"hr";
        goto LABEL_6;
      }
      LODWORD(v31) = TargetComputer;
      v28 = L"hr";
      goto LABEL_9;
    }
    TargetComputer = CWmsHypervWmi::GetHyperVService(v17, v36, &v42);
    if ( TargetComputer < 0 )
    {
      v29[0] = TargetComputer;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - ERROR 0x%08X: %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        1721,
        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
        *(_QWORD *)v29,
        L"Failed to get Hyper-V service object");
      v6 = v42;
      goto LABEL_81;
    }
    v6 = v42;
    TargetComputer = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v42->lpVtbl->Get)(
                       v42,
                       L"__PATH",
                       0,
                       &v46,
                       0,
                       0);
    if ( TargetComputer < 0 )
    {
      v14 = 1725;
LABEL_19:
      v13 = L"CHRA";
      goto LABEL_12;
    }
    TargetComputer = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v39 + 32LL))(
                       v39,
                       L"EnabledState",
                       0,
                       &varIn,
                       0,
                       0);
    if ( TargetComputer < 0 )
    {
      v14 = 1729;
      goto LABEL_19;
    }
    TargetComputer = VariantToInt32(&varIn, &plRet);
    if ( TargetComputer < 0 )
    {
      v14 = 1732;
      goto LABEL_19;
    }
    if ( plRet != 2 )
    {
      TargetComputer = -2147024875;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        1733,
        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
        L"VM is disabled");
      goto LABEL_81;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v39 + 32LL))(
            v39,
            L"__PATH",
            0,
            &v47,
            0,
            0);
    TargetComputer = v18;
    if ( v18 >= 0 )
    {
      bstrString = SysAllocString(a3);
      if ( !bstrString )
      {
        v13 = L"CPR";
        TargetComputer = -2147024882;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
          0x6CCu,
          L"CWmsHypervWmi::ProcessExchangeItemToGuest",
          L"CPR",
          L"bstrMethodName",
          -2147024882);
        if ( !IsDebuggerPresent() )
        {
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
            1740,
            L"CWmsHypervWmi::ProcessExchangeItemToGuest",
            L"CPR",
            L"bstrMethodName",
            -2147024882);
          goto LABEL_81;
        }
        LODWORD(v33) = -2147024882;
        v15 = 1740;
        v32 = L"bstrMethodName";
        goto LABEL_30;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v41 + 152LL))(
              v41,
              bstrString,
              0,
              &v40,
              0);
      TargetComputer = v19;
      if ( v19 >= 0 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 120LL))(v40, 0, &v35);
        TargetComputer = v20;
        if ( v20 >= 0 )
        {
          v45.vt = 8;
          v45.llVal = (LONGLONG)SysAllocString(v47.bstrVal);
          if ( !v45.llVal )
          {
            v13 = L"CPR";
            TargetComputer = -2147024882;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
              0x6D7u,
              L"CWmsHypervWmi::ProcessExchangeItemToGuest",
              L"CPR",
              L"varTargetSystem.bstrVal",
              -2147024882);
            if ( !IsDebuggerPresent() )
            {
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                1751,
                L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                L"CPR",
                L"varTargetSystem.bstrVal",
                -2147024882);
              goto LABEL_81;
            }
            LODWORD(v33) = -2147024882;
            v15 = 1751;
            v32 = L"varTargetSystem.bstrVal";
            goto LABEL_30;
          }
          v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v35 + 40LL))(
                  v35,
                  L"TargetSystem",
                  0,
                  &v45,
                  0);
          TargetComputer = v21;
          if ( v21 >= 0 )
          {
            DEBUGMSG(L"CWmsHypervWmi::ProcessExchangeItemToGuest - TargetSystem: '%s'\n", v45.llVal);
            TargetComputer = CWmsHypervWmi::CreateDataExchangeItemArrayVariant(this, v36, a4, a5, &v49);
            if ( TargetComputer < 0 )
              goto LABEL_81;
            v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v35 + 40LL))(
                    v35,
                    L"DataItems",
                    0,
                    &v49,
                    0);
            TargetComputer = v22;
            if ( v22 >= 0 )
            {
              DEBUGMSG(
                L"CWmsHypervWmi::ProcessExchangeItemToGuest - Msvm_VirtualSystemManagementService class path: '%s'\n",
                v46.llVal);
              TargetComputer = ((__int64 (__fastcall *)(struct IWbemServices *, LONGLONG, BSTR, _QWORD, _QWORD, __int64, __int64 *, _QWORD))v36->lpVtbl->ExecMethod)(
                                 v36,
                                 v46.llVal,
                                 bstrString,
                                 0,
                                 0,
                                 v35,
                                 &v38,
                                 0);
              if ( TargetComputer >= 0 )
              {
                v23 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v38 + 32LL))(
                        v38,
                        CWmsHypervWmi::s_bstrJob,
                        0,
                        &pvarg,
                        0,
                        0);
                TargetComputer = v23;
                if ( v23 >= 0 )
                {
                  if ( pvarg.vt != 8 )
                  {
                    TargetComputer = -2147418113;
                    goto LABEL_81;
                  }
                  if ( !SysStringLen(pvarg.bstrVal) )
                  {
                    TargetComputer = -2147418113;
                    LOGASSERTHR(
                      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                      0x6ECu,
                      L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                      L"CBRAEx",
                      L"cchJob > 0",
                      -2147418113);
                    if ( !IsDebuggerPresent() )
                    {
                      LODWORD(v31) = -2147418113;
                      DEBUGMSGBOX(
                        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                        1772,
                        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                        L"CBRAEx",
                        L"cchJob > 0",
                        v31);
                      goto LABEL_81;
                    }
                    LODWORD(v33) = -2147418113;
                    v15 = 1772;
                    v32 = L"cchJob > 0";
                    v27 = L"CBRAEx";
                    goto LABEL_7;
                  }
                  v24 = SysAllocString(pvarg.bstrVal);
                  *a6 = v24;
                  if ( !v24 )
                  {
                    v13 = L"CPR";
                    TargetComputer = -2147024882;
                    LOGASSERTHR(
                      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                      0x6F0u,
                      L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                      L"CPR",
                      L"*pbstrMsvm_ConcreteJob",
                      -2147024882);
                    if ( !IsDebuggerPresent() )
                    {
                      LODWORD(v31) = -2147024882;
                      DEBUGMSGBOX(
                        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                        1776,
                        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                        L"CPR",
                        L"*pbstrMsvm_ConcreteJob",
                        v31);
                      goto LABEL_81;
                    }
                    LODWORD(v33) = -2147024882;
                    v15 = 1776;
                    v32 = L"*pbstrMsvm_ConcreteJob";
                    goto LABEL_30;
                  }
                  v25 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v38 + 32LL))(
                          v38,
                          CWmsHypervWmi::s_bstrReturnValue,
                          0,
                          &v50,
                          0,
                          0);
                  TargetComputer = v25;
                  if ( v25 >= 0 )
                    goto LABEL_81;
                  v13 = L"CHRA";
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                    0x6F3u,
                    L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                    L"CHRA",
                    L"hr",
                    v25);
                  if ( IsDebuggerPresent() )
                  {
                    v15 = 1779;
                    goto LABEL_29;
                  }
                  v16 = 1779;
                }
                else
                {
                  v13 = L"CHRA";
                  LOGASSERTHR(
                    L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                    0x6E9u,
                    L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                    L"CHRA",
                    L"hr",
                    v23);
                  if ( IsDebuggerPresent() )
                  {
                    v15 = 1769;
                    goto LABEL_29;
                  }
                  v16 = 1769;
                }
              }
              else
              {
                v30[0] = TargetComputer;
                DEBUGMSGLEVEL(
                  4u,
                  L"%s(%d) - %s - ERROR 0x%08X: %s\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                  1766,
                  L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                  *(_QWORD *)v30,
                  L"Failed to execute method");
                v13 = L"CHRLA";
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                  0x6E6u,
                  L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                  L"CHRLA",
                  L"hr",
                  TargetComputer);
                if ( IsDebuggerPresent() )
                {
                  v15 = 1766;
                  goto LABEL_29;
                }
                v16 = 1766;
              }
            }
            else
            {
              v13 = L"CHRA";
              LOGASSERTHR(
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
                0x6E1u,
                L"CWmsHypervWmi::ProcessExchangeItemToGuest",
                L"CHRA",
                L"hr",
                v22);
              if ( IsDebuggerPresent() )
              {
                v15 = 1761;
                goto LABEL_29;
              }
              v16 = 1761;
            }
          }
          else
          {
            v13 = L"CHRA";
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
              0x6D9u,
              L"CWmsHypervWmi::ProcessExchangeItemToGuest",
              L"CHRA",
              L"hr",
              v21);
            if ( IsDebuggerPresent() )
            {
              v15 = 1753;
              goto LABEL_29;
            }
            v16 = 1753;
          }
        }
        else
        {
          v13 = L"CHRA";
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
            0x6D2u,
            L"CWmsHypervWmi::ProcessExchangeItemToGuest",
            L"CHRA",
            L"hr",
            v20);
          if ( IsDebuggerPresent() )
          {
            v15 = 1746;
            goto LABEL_29;
          }
          v16 = 1746;
        }
      }
      else
      {
        v13 = L"CHRA";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
          0x6CFu,
          L"CWmsHypervWmi::ProcessExchangeItemToGuest",
          L"CHRA",
          L"hr",
          v19);
        if ( IsDebuggerPresent() )
        {
          v15 = 1743;
          goto LABEL_29;
        }
        v16 = 1743;
      }
    }
    else
    {
      v13 = L"CHRA";
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        0x6C9u,
        L"CWmsHypervWmi::ProcessExchangeItemToGuest",
        L"CHRA",
        L"hr",
        v18);
      if ( IsDebuggerPresent() )
      {
        v15 = 1737;
LABEL_29:
        LODWORD(v33) = TargetComputer;
        v32 = L"hr";
LABEL_30:
        v27 = v13;
        goto LABEL_7;
      }
      v16 = 1737;
    }
    LODWORD(v31) = TargetComputer;
    v28 = L"hr";
    goto LABEL_80;
  }
  v13 = L"CPR";
  v14 = 1715;
  TargetComputer = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
    0x6B3u,
    L"CWmsHypervWmi::ProcessExchangeItemToGuest",
    L"CPR",
    L"bstrClassPath",
    -2147024882);
  if ( !IsDebuggerPresent() )
  {
    LODWORD(v31) = -2147024882;
    v28 = L"bstrClassPath";
LABEL_9:
    v16 = v14;
LABEL_80:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      v16,
      L"CWmsHypervWmi::ProcessExchangeItemToGuest",
      v13,
      v28,
      v31);
    goto LABEL_81;
  }
  LODWORD(v33) = -2147024882;
  v32 = L"bstrClassPath";
LABEL_6:
  v27 = v13;
  v15 = v14;
LABEL_7:
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
    v15,
    L"CWmsHypervWmi::ProcessExchangeItemToGuest",
    v27,
    v32,
    v33);
LABEL_81:
  v12 = v34;
LABEL_82:
  SysFreeString(bstrString);
  SysFreeString(v12);
  VariantClear(&pvarg);
  VariantClear(&v46);
  VariantClear(&v45);
  VariantClear(&v47);
  VariantClear(&varIn);
  VariantClear(&v49);
  VariantClear(&v50);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IWbemClassObject *))v6->lpVtbl->Release)(v6);
  if ( v36 )
    ((void (__fastcall *)(struct IWbemServices *))v36->lpVtbl->Release)(v36);
  return (unsigned int)TargetComputer;
}

```

## disassembly

```asm
0x14004099c  push    rbp
0x14004099e  push    rbx
0x14004099f  push    rsi
0x1400409a0  push    rdi
0x1400409a1  push    r12
0x1400409a3  push    r13
0x1400409a5  push    r14
0x1400409a7  push    r15
0x1400409a9  lea     rbp, [rsp-58h]
0x1400409ae  sub     rsp, 158h
0x1400409b5  xor     eax, eax
0x1400409b7  mov     [rsp+190h+var_130], 0
0x1400409c0  xor     r13d, r13d
0x1400409c3  mov     qword ptr [rbp+90h+var_D8+10h], rax
0x1400409c7  xorps   xmm0, xmm0
0x1400409ca  mov     [rbp+90h+var_100], r13
0x1400409ce  xorps   xmm1, xmm1
0x1400409d1  mov     [rbp+90h+var_110], r13
0x1400409d5  mov     rsi, rcx
0x1400409d8  mov     [rsp+190h+var_120], r13
0x1400409dd  lea     rcx, [rbp+90h+pvarg]; pvarg
0x1400409e1  mov     [rsp+190h+var_138], r13
0x1400409e6  mov     [rsp+190h+plRet], r13d
0x1400409eb  mov     r14, r9
0x1400409ee  mov     [rbp+90h+bstrString], r13
0x1400409f2  mov     rdi, r8
0x1400409f5  movups  xmmword ptr [rbp+90h+var_D8], xmm0
0x1400409f9  mov     qword ptr [rbp+90h+varIn+10h], rax
0x1400409fd  mov     rbx, rdx
0x140040a00  movups  xmmword ptr [rbp+90h+varIn], xmm1
0x140040a04  mov     qword ptr [rbp+90h+var_A8+10h], rax
0x140040a08  movups  xmmword ptr [rbp+90h+var_A8], xmm0
0x140040a0c  mov     qword ptr [rbp+90h+var_C0+10h], rax
0x140040a10  movups  xmmword ptr [rbp+90h+var_C0], xmm1
0x140040a14  mov     qword ptr [rbp+90h+pvarg+10h], rax
0x140040a18  movups  xmmword ptr [rbp+90h+pvarg], xmm0
0x140040a1c  mov     qword ptr [rbp+90h+var_60+10h], rax
0x140040a20  movups  xmmword ptr [rbp+90h+var_60], xmm1
0x140040a24  mov     qword ptr [rbp+90h+var_78+10h], rax
0x140040a28  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x140040a2c  mov     [rsp+190h+var_118], 0
0x140040a35  mov     [rbp+90h+var_108], 0
0x140040a3d  call    cs:__imp_VariantInit
0x140040a43  lea     rcx, [rbp+90h+var_C0]; pvarg
0x140040a47  call    cs:__imp_VariantInit
0x140040a4d  lea     rcx, [rbp+90h+var_A8]; pvarg
0x140040a51  call    cs:__imp_VariantInit
0x140040a57  lea     rcx, [rbp+90h+varIn]; pvarg
0x140040a5b  call    cs:__imp_VariantInit
0x140040a61  lea     rcx, [rbp+90h+var_D8]; pvarg
0x140040a65  call    cs:__imp_VariantInit
0x140040a6b  lea     rcx, [rbp+90h+var_78]; pvarg
0x140040a6f  call    cs:__imp_VariantInit
0x140040a75  lea     rcx, [rbp+90h+var_60]; pvarg
0x140040a79  call    cs:__imp_VariantInit
0x140040a7f  lea     rax, [rsp+190h+var_118]
0x140040a84  mov     r8, rbx
0x140040a87  lea     r9, [rsp+190h+var_130]
0x140040a8c  mov     [rsp+190h+var_170], rax
0x140040a91  lea     edx, [r13+1]
0x140040a95  mov     rcx, rsi
0x140040a98  call    ?GetTargetComputer@CWmsHypervWmi@@AEAAJW4GetTargetComputerSearchMethod@1@PEAGPEAPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z; CWmsHypervWmi::GetTargetComputer(CWmsHypervWmi::GetTargetComputerSearchMethod,ushort *,IWbemServices * *,IWbemClassObject * *)
0x140040a9d  mov     ebx, eax
0x140040a9f  test    eax, eax
0x140040aa1  jns     short loc_140040AE4
0x140040aa3  lea     rax, aFailedToGetTar; "Failed to get target VM object\n"
0x140040aaa  xor     r14d, r14d
0x140040aad  mov     [rsp+190h+var_160], rax
0x140040ab2  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040ab9  mov     [rsp+190h+var_168], ebx
0x140040abd  lea     r8, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040ac4  mov     r9d, 6AFh
0x140040aca  mov     [rsp+190h+var_170], rsi
0x140040acf  lea     rdx, aSDSError0x08xS; "%s(%d) - %s - ERROR 0x%08X: %s\n"
0x140040ad6  lea     ecx, [r13+4]; unsigned __int8
0x140040ada  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140040adf  jmp     loc_14004150A
0x140040ae4  lea     rcx, aMsvmVirtualsys; "Msvm_VirtualSystemManagementService"
0x140040aeb  call    cs:__imp_SysAllocString
0x140040af1  mov     [rsp+190h+var_140], rax
0x140040af6  mov     rdx, rax
0x140040af9  test    rax, rax
0x140040afc  jnz     loc_140040B9B
0x140040b02  mov     r14d, 8007000Eh
0x140040b08  lea     rax, aBstrclasspath; "bstrClassPath"
0x140040b0f  lea     r15, aCpr; "CPR"
0x140040b16  mov     [rsp+190h+var_168], r14d; int
0x140040b1b  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040b22  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x140040b27  mov     r12d, 6B3h
0x140040b2d  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040b34  mov     r9, r15; unsigned __int16 *
0x140040b37  mov     r8, rsi; unsigned __int16 *
0x140040b3a  mov     edx, r12d; unsigned int
0x140040b3d  mov     rcx, rdi; unsigned __int16 *
0x140040b40  mov     ebx, r14d
0x140040b43  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140040b48  call    cs:__imp_IsDebuggerPresent
0x140040b4e  test    eax, eax
0x140040b50  lea     rax, aBstrclasspath; "bstrClassPath"
0x140040b57  jz      short loc_140040B89
0x140040b59  mov     dword ptr [rsp+190h+var_158], r14d
0x140040b5e  mov     [rsp+190h+var_160], rax
0x140040b63  mov     qword ptr [rsp+190h+var_168], r15
0x140040b68  mov     r9d, r12d
0x140040b6b  mov     ecx, 2; unsigned __int8
0x140040b70  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140040b77  mov     [rsp+190h+var_170], rsi
0x140040b7c  mov     r8, rdi
0x140040b7f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140040b84  jmp     loc_140041505
0x140040b89  mov     dword ptr [rsp+190h+var_160], r14d
0x140040b8e  mov     qword ptr [rsp+190h+var_168], rax
0x140040b93  mov     r8d, r12d
0x140040b96  jmp     loc_1400414EE
0x140040b9b  mov     rcx, [rsp+190h+var_130]
0x140040ba0  lea     r8, [rbp+90h+var_108]
0x140040ba4  mov     qword ptr [rsp+190h+var_168], r13
0x140040ba9  xor     r9d, r9d
0x140040bac  mov     [rsp+190h+var_170], r8
0x140040bb1  xor     r8d, r8d
0x140040bb4  mov     rax, [rcx]
0x140040bb7  mov     rax, [rax+30h]
0x140040bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040bc0  mov     ebx, eax
0x140040bc2  test    eax, eax
0x140040bc4  jns     loc_140040C58
0x140040bca  lea     rax, aFailedToGetMsv; "Failed to get Msvm_VirtualSystemManagem"...
0x140040bd1  mov     r12d, 6B6h
0x140040bd7  mov     [rsp+190h+var_160], rax
0x140040bdc  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040be3  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040bea  mov     [rsp+190h+var_168], ebx
0x140040bee  mov     r9d, r12d
0x140040bf1  mov     [rsp+190h+var_170], rsi
0x140040bf6  mov     r8, rdi
0x140040bf9  lea     rdx, aSDSError0x08xS; "%s(%d) - %s - ERROR 0x%08X: %s\n"
0x140040c00  mov     ecx, 4; unsigned __int8
0x140040c05  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140040c0a  lea     r15, aChrla; "CHRLA"
0x140040c11  lea     r14, aHr; "hr"
0x140040c18  mov     [rsp+190h+var_168], ebx; int
0x140040c1c  mov     r8, rsi; unsigned __int16 *
0x140040c1f  mov     [rsp+190h+var_170], r14; unsigned __int16 *
0x140040c24  mov     r9, r15; unsigned __int16 *
0x140040c27  mov     edx, r12d; unsigned int
0x140040c2a  mov     rcx, rdi; unsigned __int16 *
0x140040c2d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140040c32  call    cs:__imp_IsDebuggerPresent
0x140040c38  test    eax, eax
0x140040c3a  jz      short loc_140040C4A
0x140040c3c  mov     dword ptr [rsp+190h+var_158], ebx
0x140040c40  mov     [rsp+190h+var_160], r14
0x140040c45  jmp     loc_140040B63
0x140040c4a  mov     dword ptr [rsp+190h+var_160], ebx
0x140040c4e  mov     qword ptr [rsp+190h+var_168], r14
0x140040c53  jmp     loc_140040B93
0x140040c58  mov     rdx, [rsp+190h+var_130]; struct IWbemServices *
0x140040c5d  lea     r8, [rbp+90h+var_100]; struct IWbemClassObject **
0x140040c61  call    ?GetHyperVService@CWmsHypervWmi@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z; CWmsHypervWmi::GetHyperVService(IWbemServices *,IWbemClassObject * *)
0x140040c66  mov     ebx, eax
0x140040c68  test    eax, eax
0x140040c6a  jns     short loc_140040CAF
0x140040c6c  lea     rax, aFailedToGetHyp; "Failed to get Hyper-V service object"
0x140040c73  mov     r9d, 6B9h
0x140040c79  mov     [rsp+190h+var_160], rax
0x140040c7e  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040c85  mov     [rsp+190h+var_168], ebx
0x140040c89  lea     r8, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040c90  lea     rdx, aSDSError0x08xS; "%s(%d) - %s - ERROR 0x%08X: %s\n"
0x140040c97  mov     [rsp+190h+var_170], rsi
0x140040c9c  mov     ecx, 4; unsigned __int8
0x140040ca1  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140040ca6  mov     r13, [rbp+90h+var_100]
0x140040caa  jmp     loc_140041505
0x140040caf  mov     r13, [rbp+90h+var_100]
0x140040cb3  lea     r9, [rbp+90h+var_C0]
0x140040cb7  mov     qword ptr [rsp+190h+var_168], 0
0x140040cc0  lea     rdx, aPath; "__PATH"
0x140040cc7  xor     r8d, r8d
0x140040cca  mov     [rsp+190h+var_170], 0
0x140040cd3  mov     rcx, r13
0x140040cd6  mov     rax, [r13+0]
0x140040cda  mov     rax, [rax+20h]
0x140040cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040ce3  mov     ebx, eax
0x140040ce5  test    eax, eax
0x140040ce7  jns     short loc_140040D09
0x140040ce9  mov     r12d, 6BDh
0x140040cef  lea     r15, aChra; "CHRA"
0x140040cf6  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040cfd  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040d04  jmp     loc_140040C11
0x140040d09  mov     rcx, [rsp+190h+var_118]
0x140040d0e  lea     r9, [rbp+90h+varIn]
0x140040d12  mov     qword ptr [rsp+190h+var_168], 0
0x140040d1b  lea     rdx, aEnabledstate; "EnabledState"
0x140040d22  xor     r8d, r8d
0x140040d25  mov     [rsp+190h+var_170], 0
0x140040d2e  mov     rax, [rcx]
0x140040d31  mov     rax, [rax+20h]
0x140040d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040d3a  mov     ebx, eax
0x140040d3c  test    eax, eax
0x140040d3e  jns     short loc_140040D48
0x140040d40  mov     r12d, 6C1h
0x140040d46  jmp     short loc_140040CEF
0x140040d48  lea     rdx, [rsp+190h+plRet]; plRet
0x140040d4d  lea     rcx, [rbp+90h+varIn]; varIn
0x140040d51  call    cs:__imp_VariantToInt32
0x140040d57  mov     ebx, eax
0x140040d59  test    eax, eax
0x140040d5b  jns     short loc_140040D65
0x140040d5d  mov     r12d, 6C4h
0x140040d63  jmp     short loc_140040CEF
0x140040d65  mov     r12d, 2
0x140040d6b  cmp     [rsp+190h+plRet], r12d
0x140040d70  jz      short loc_140040DB2
0x140040d72  lea     rax, aVmIsDisabled; "VM is disabled"
0x140040d79  mov     r9d, 6C5h
0x140040d7f  mov     qword ptr [rsp+190h+var_168], rax
0x140040d84  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040d8b  lea     r8, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040d92  mov     [rsp+190h+var_170], rsi
0x140040d97  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140040d9e  mov     ebx, 80070015h
0x140040da3  lea     ecx, [r12+2]; unsigned __int8
0x140040da8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140040dad  jmp     loc_140041505
0x140040db2  mov     rcx, [rsp+190h+var_118]
0x140040db7  lea     r9, [rbp+90h+var_A8]
0x140040dbb  mov     qword ptr [rsp+190h+var_168], 0
0x140040dc4  lea     rdx, aPath; "__PATH"
0x140040dcb  xor     r8d, r8d
0x140040dce  mov     [rsp+190h+var_170], 0
0x140040dd7  mov     rax, [rcx]
0x140040dda  mov     rax, [rax+20h]
0x140040dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040de3  mov     ebx, eax
0x140040de5  test    eax, eax
0x140040de7  jns     short loc_140040E52
0x140040de9  mov     [rsp+190h+var_168], eax; int
0x140040ded  lea     r15, aChra; "CHRA"
0x140040df4  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040dfb  mov     r9, r15; unsigned __int16 *
0x140040dfe  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040e05  mov     r8, rsi; unsigned __int16 *
0x140040e08  lea     r14, aHr; "hr"
0x140040e0f  mov     rcx, rdi; unsigned __int16 *
0x140040e12  mov     edx, 6C9h; unsigned int
0x140040e17  mov     [rsp+190h+var_170], r14; unsigned __int16 *
0x140040e1c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140040e21  call    cs:__imp_IsDebuggerPresent
0x140040e27  test    eax, eax
0x140040e29  jz      short loc_140040E47
0x140040e2b  mov     r9d, 6C9h
0x140040e31  mov     dword ptr [rsp+190h+var_158], ebx
0x140040e35  mov     [rsp+190h+var_160], r14
0x140040e3a  mov     qword ptr [rsp+190h+var_168], r15
0x140040e3f  mov     ecx, r12d
0x140040e42  jmp     loc_140040B70
0x140040e47  mov     r8d, 6C9h
0x140040e4d  jmp     loc_1400414E5
0x140040e52  mov     rcx, rdi; psz
0x140040e55  call    cs:__imp_SysAllocString
0x140040e5b  mov     [rbp+90h+bstrString], rax
0x140040e5f  mov     rdx, rax
0x140040e62  test    rax, rax
0x140040e65  jnz     short loc_140040EE4
0x140040e67  mov     r14d, 8007000Eh
0x140040e6d  lea     rax, aBstrmethodname; "bstrMethodName"
0x140040e74  lea     r15, aCpr; "CPR"
0x140040e7b  mov     [rsp+190h+var_168], r14d; int
0x140040e80  lea     rsi, aCwmshypervwmiP; "CWmsHypervWmi::ProcessExchangeItemToGue"...
0x140040e87  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x140040e8c  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140040e93  mov     r9, r15; unsigned __int16 *
0x140040e96  mov     r8, rsi; unsigned __int16 *
0x140040e99  mov     rcx, rdi; unsigned __int16 *
0x140040e9c  mov     edx, 6CCh; unsigned int
0x140040ea1  mov     ebx, r14d
0x140040ea4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140040ea9  call    cs:__imp_IsDebuggerPresent
0x140040eaf  test    eax, eax
0x140040eb1  lea     rax, aBstrmethodname; "bstrMethodName"
0x140040eb8  jz      short loc_140040ECF
0x140040eba  mov     dword ptr [rsp+190h+var_158], r14d
0x140040ebf  mov     r9d, 6CCh
0x140040ec5  mov     [rsp+190h+var_160], rax
0x140040eca  jmp     loc_140040E3A
0x140040ecf  mov     dword ptr [rsp+190h+var_160], r14d
0x140040ed4  mov     r8d, 6CCh
0x140040eda  mov     qword ptr [rsp+190h+var_168], rax
0x140040edf  jmp     loc_1400414EE
0x140040ee4  mov     rcx, [rbp+90h+var_108]
0x140040ee8  lea     r9, [rbp+90h+var_110]
0x140040eec  xor     r8d, r8d
0x140040eef  mov     [rsp+190h+var_170], 0
0x140040ef8  mov     rax, [rcx]
0x140040efb  mov     rax, [rax+98h]
  ... truncated ...
```
