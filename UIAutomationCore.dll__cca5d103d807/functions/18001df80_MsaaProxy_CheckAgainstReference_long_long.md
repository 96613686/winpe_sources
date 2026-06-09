# MsaaProxy::CheckAgainstReference(long,long)

- ea: `0x18001df80`
- end: `0x18001e8b2`
- name: `?CheckAgainstReference@MsaaProxy@@IEAAHJJ@Z`
- size: `2354`
- prototype: `__int64 __fastcall(MsaaProxy *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800616b8`
- `0x18011d830`

## callees

- `0x18000f680`
- `0x18001df80`
- `0x18001f3b0`
- `0x180020230`
- `0x18002f580`
- `0x1800b9c70`
- `0x1801345f0`
- `0x1801a1438`
- `0x1801e9234`
- `0x1802dd010`

## import_xrefs

- `OLEACC!CreateStdAccessibleObject` at `0x18001e6b0`
- `OLEACC!CreateStdAccessibleObject` at `0x18001e6b0`
- `OLEACC!AccessibleObjectFromWindowTimeout` at `0x18001e28d`
- `OLEACC!AccessibleObjectFromWindowTimeout` at `0x18001e67a`
- `OLEACC!AccessibleObjectFromWindowTimeout` at `0x18001e28d`
- `OLEACC!AccessibleObjectFromWindowTimeout` at `0x18001e67a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e81a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e83b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e81a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e83b`

## string_xrefs

- `0x18001e209`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x18001e6c3`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x18001e5aa`: `onecore\windows\accessibletech\uiautomationcore\proxies\MsaaProxy.h`
- `0x18001e72a`: `onecore\windows\accessibletech\uiautomationcore\proxies\MsaaProxy.h`
- `0x18001e0b0`: `IServiceProvider::QueryService`
- `0x18001e321`: `IServiceProvider::QueryService`
- `0x18001e4fd`: `IServiceProvider::QueryService`
- `0x18001e743`: `IServiceProvider::QueryService`
- `0x18001e766`: `IServiceProvider::QueryService`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MsaaProxy::CheckAgainstReference(MsaaProxy *this, LONG a2, LONG a3)
{
  int v5; // r14d
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  void (__fastcall ***v9)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // r9
  int v11; // eax
  int v12; // ebx
  HWND v13; // rdi
  LONGLONG v14; // rbx
  __int64 v15; // rcx
  void (__fastcall *v16)(LONGLONG, GUID *, GUID *, __int64 *); // r15
  __int64 v17; // rcx
  __int64 v18; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // edi
  unsigned int v22; // ebx
  HWND v23; // r15
  int v24; // eax
  LONGLONG v25; // rbx
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // edi
  __int64 v29; // rax
  _QWORD *v30; // rcx
  BOOL v31; // ebx
  struct IAccessible *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 (__fastcall ***v36)(_QWORD, GUID *, struct IAccessible **); // r9
  int v37; // eax
  unsigned int v38; // ebx
  __int64 v40; // rcx
  void (__fastcall *v41)(LONGLONG, GUID *, GUID *, __int64 *, GUID *, void **); // r12
  __int64 v42; // rcx
  __int64 v43; // rcx
  HRESULT v44; // eax
  __int64 v45; // rdx
  int v46; // [rsp+20h] [rbp-59h]
  GUID *v47; // [rsp+20h] [rbp-59h]
  __int64 v48; // [rsp+30h] [rbp-49h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-41h] BYREF
  void (__fastcall ***v50)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-39h] BYREF
  struct IAccessible *v51; // [rsp+48h] [rbp-31h] BYREF
  _QWORD *v52; // [rsp+50h] [rbp-29h] BYREF
  __int64 v53; // [rsp+58h] [rbp-21h] BYREF
  struct tagVARIANT v54; // [rsp+60h] [rbp-19h] BYREF
  int v55; // [rsp+78h] [rbp-1h]
  int v56; // [rsp+7Ch] [rbp+3h]
  char v57; // [rsp+80h] [rbp+7h]
  HWND v58; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  _QWORD *v60; // [rsp+E0h] [rbp+67h] BYREF
  LONG v61; // [rsp+E8h] [rbp+6Fh]
  LONG idObject; // [rsp+F0h] [rbp+77h]
  unsigned int v63; // [rsp+F8h] [rbp+7Fh] BYREF

  idObject = a3;
  v61 = a2;
  if ( *((_DWORD *)this + 82) != a2 )
    return 0;
  v50 = 0;
  v5 = -2147467259;
  if ( *((_DWORD *)this + 64) )
    goto LABEL_107;
  v50 = 0;
  v6 = *((_QWORD *)this + 33);
  if ( !v6 )
  {
    v7 = *((unsigned int *)this + 70);
    if ( !(_DWORD)v7 && !*((_QWORD *)this + 34) )
      goto LABEL_35;
    v8 = *((_QWORD *)this + 34);
    if ( v8 )
    {
      v9 = 0;
      v50 = 0;
      v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))(v8 + 32);
      if ( !v10 )
      {
        v12 = -2147467259;
LABEL_9:
        if ( v12 >= 0 )
          goto LABEL_10;
LABEL_108:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\MsaaProxy.h",
          (const char *)(unsigned int)v12,
          v46);
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2B,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)v12,
          v46);
        if ( v50 )
          ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v50)[2])(v50);
        return 0;
      }
      v11 = (**v10)(*(_QWORD *)(v8 + 32), &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &v50);
LABEL_8:
      v9 = v50;
      v12 = v11;
      goto LABEL_9;
    }
    if ( (_DWORD)v7 )
    {
      v42 = *((_QWORD *)this + 31);
      if ( v42 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, void (__fastcall ****)(_QWORD, GUID *, _QWORD **)))(*(_QWORD *)v42 + 40LL))(
                v42,
                v7,
                &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
                &v50);
        goto LABEL_8;
      }
    }
LABEL_107:
    v12 = -2147467259;
    goto LABEL_108;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v9 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD **))*((_QWORD *)this + 33);
  v50 = v9;
LABEL_10:
  if ( !v9 )
  {
LABEL_35:
    v12 = -2147467259;
    goto LABEL_36;
  }
  v13 = (HWND)*((_QWORD *)this + 29);
  v58 = v13;
  LODWORD(v60) = 0;
  v53 = 0;
  v52 = 0;
  (**v9)(v9, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v52);
  v14 = (LONGLONG)v52;
  if ( v52 )
  {
    if ( !memcmp_0(&GUID_55f9c234_79cd_4699_89e7_5518fd88bcde, &GUID_00000000_0000_0000_c000_000000000046, 0x10u) )
    {
      v48 = 0;
      *(_QWORD *)&v54.vt = L"IServiceProvider::QueryService";
      v54.llVal = v14;
      v54.pRecInfo = (IRecordInfo *)__PAIR64__(HIDWORD(v58), (unsigned int)v13);
      v55 = 0;
      v56 = 600;
      v57 = 1;
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      {
        McTemplateU0zd_EventWriteTransfer(
          0,
          MsaaProviderCallout_Start,
          L"IServiceProvider::QueryService",
          (unsigned int)v13);
        v14 = (LONGLONG)v52;
      }
      v16 = *(void (__fastcall **)(LONGLONG, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 24LL);
      v48 = 0;
      v16(v14, &GUID_acd46652_829d_41cb_a5fc_17acf43661ac, &GUID_00000000_0000_0000_c000_000000000046, &v48);
      if ( v48 )
      {
        v55 = -2147467259;
        v56 = 610;
        MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v54);
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        v19 = v52;
        if ( !v52 )
          goto LABEL_27;
        v18 = *v52;
        goto LABEL_26;
      }
      MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v54);
      v15 = v48;
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v14 = (LONGLONG)v52;
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(
        v15,
        MsaaProviderCallout_Start,
        L"IServiceProvider::QueryService",
        (unsigned int)v13);
      v14 = (LONGLONG)v52;
    }
    (*(void (__fastcall **)(LONGLONG, __int64 *, GUID *, __int64 *))(*(_QWORD *)v14 + 24LL))(
      v14,
      IIS_AccProxyVersion,
      &GUID_55f9c234_79cd_4699_89e7_5518fd88bcde,
      &v53);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v17,
        MsaaProviderCallout_Stop,
        L"IServiceProvider::QueryService",
        (unsigned int)v13);
    v14 = (LONGLONG)v52;
  }
  if ( v14 )
  {
    v18 = *(_QWORD *)v14;
    v19 = (_QWORD *)v14;
LABEL_26:
    (*(void (__fastcall **)(_QWORD *))(v18 + 16))(v19);
  }
LABEL_27:
  v20 = v53;
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v53 + 24LL))(v53, &v60);
    v20 = v53;
  }
  v21 = (unsigned int)v60;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v50 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v50)[2])(v50);
  v63 = 0;
  if ( (*(int (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 26) + 24LL))((char *)this + 208, &v63) < 0 )
    return 0;
  v22 = v63;
  v23 = (HWND)*((_QWORD *)this + 29);
  v58 = v23;
  ppvObject = 0;
  v47 = &GUID_618736e0_3c3d_11cf_810c_00aa00389b71;
  v24 = AccessibleObjectFromWindowTimeout(v21, v63, v23, (unsigned int)a3);
  if ( v24 < 0 )
  {
    if ( v24 != -2147467259 || !HwndUtils::IsTrident(v23) )
      goto LABEL_104;
    v47 = &GUID_618736e0_3c3d_11cf_810c_00aa00389b71;
    v44 = AccessibleObjectFromWindowTimeout(v21, v22, v23, 4294967292LL);
    if ( v44 < 0 )
    {
      v45 = 333;
LABEL_103:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
        (const char *)(unsigned int)v44,
        (int)v47);
LABEL_104:
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&ppvObject);
      return 0;
    }
  }
  if ( ppvObject )
  {
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( BasicUiaUtils::s_isDesktop && a3 <= 0 )
    {
      v53 = 0;
      v60 = 0;
      (**(void (__fastcall ***)(void *, GUID *, _QWORD **))ppvObject)(
        ppvObject,
        &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
        &v60);
      v25 = (LONGLONG)v60;
      if ( v60 )
      {
        v26 = memcmp_0(&GUID_00000000_0000_0000_c000_000000000046, &GUID_00000000_0000_0000_c000_000000000046, 0x10u);
        v28 = HIDWORD(v58);
        if ( !v26 )
        {
          v40 = 0;
          v48 = 0;
          *(_QWORD *)&v54.vt = L"IServiceProvider::QueryService";
          v54.llVal = v25;
          v54.pRecInfo = (IRecordInfo *)__PAIR64__(HIDWORD(v58), (unsigned int)v23);
          v55 = 0;
          v56 = 600;
          v57 = 1;
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          {
            McTemplateU0zd_EventWriteTransfer(
              0,
              MsaaProviderCallout_Start,
              L"IServiceProvider::QueryService",
              (unsigned int)v23);
            v25 = (LONGLONG)v60;
            v40 = v48;
          }
          v41 = *(void (__fastcall **)(LONGLONG, GUID *, GUID *, __int64 *, GUID *, void **))(*(_QWORD *)v25 + 24LL);
          v48 = 0;
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v41(
            v25,
            &GUID_acd46652_829d_41cb_a5fc_17acf43661ac,
            &GUID_00000000_0000_0000_c000_000000000046,
            &v48,
            &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
            &ppvObject);
          if ( v48 )
          {
            v55 = -2147467259;
            v56 = 610;
            MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v54);
            if ( v48 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            v30 = v60;
            if ( !v60 )
            {
LABEL_54:
              v31 = v53 != 0;
              if ( v53 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
              if ( v31 )
              {
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
                ppvObject = 0;
                v44 = CreateStdAccessibleObject(v23, idObject, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &ppvObject);
                if ( v44 < 0 )
                {
                  v45 = 358;
                  goto LABEL_103;
                }
              }
              goto LABEL_57;
            }
            v29 = *v60;
LABEL_53:
            (*(void (__fastcall **)(_QWORD *))(v29 + 16))(v30);
            goto LABEL_54;
          }
          MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v54);
          v27 = v48;
          if ( v48 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          v25 = (LONGLONG)v60;
        }
        *(_QWORD *)&v54.vt = L"IServiceProvider::QueryService";
        v54.llVal = v25;
        v54.pRecInfo = (IRecordInfo *)__PAIR64__(v28, (unsigned int)v23);
        v56 = 600;
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        {
          McTemplateU0zd_EventWriteTransfer(
            v27,
            MsaaProviderCallout_Start,
            L"IServiceProvider::QueryService",
            (unsigned int)v23);
          v25 = (LONGLONG)v60;
        }
        v55 = (*(__int64 (__fastcall **)(LONGLONG, GUID *, GUID *, __int64 *))(*(_QWORD *)v25 + 24LL))(
                v25,
                &GUID_b96fdb85_7204_4724_842b_c7059dedb9d0,
                &GUID_00000000_0000_0000_c000_000000000046,
                &v53);
        v57 = 0;
        MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v54);
        v25 = (LONGLONG)v60;
      }
      if ( !v25 )
        goto LABEL_54;
      v29 = *(_QWORD *)v25;
      v30 = (_QWORD *)v25;
      goto LABEL_53;
    }
  }
LABEL_57:
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop && !BasicUiaUtils::IsWinPE() && !ppvObject )
    goto LABEL_104;
  v51 = 0;
  if ( *((_DWORD *)this + 64) )
    goto LABEL_85;
  v32 = 0;
  v51 = 0;
  v33 = *((_QWORD *)this + 33);
  if ( !v33 )
  {
    v34 = *((unsigned int *)this + 70);
    if ( !(_DWORD)v34 && !*((_QWORD *)this + 34) )
      goto LABEL_86;
    v35 = *((_QWORD *)this + 34);
    if ( v35 )
    {
      v32 = 0;
      v51 = 0;
      v36 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IAccessible **))(v35 + 32);
      if ( !v36 )
        goto LABEL_67;
      v37 = (**v36)(v36, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &v51);
    }
    else
    {
      if ( !(_DWORD)v34 )
        goto LABEL_85;
      v43 = *((_QWORD *)this + 31);
      if ( !v43 )
        goto LABEL_85;
      v37 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, struct IAccessible **))(*(_QWORD *)v43 + 40LL))(
              v43,
              v34,
              &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
              &v51);
    }
    v32 = v51;
    v5 = v37;
LABEL_67:
    if ( v5 >= 0 )
      goto LABEL_68;
LABEL_85:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\MsaaProxy.h",
      (const char *)(unsigned int)v5,
      (int)v47);
    v32 = v51;
    goto LABEL_86;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 8LL))(*((_QWORD *)this + 33));
  v32 = (struct IAccessible *)*((_QWORD *)this + 33);
  v51 = v32;
LABEL_68:
  if ( !v32 )
  {
LABEL_86:
    if ( v32 )
      ((void (__fastcall *)(struct IAccessible *))v32->lpVtbl->Release)(v32);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    return 0;
  }
  memset(&v54, 0, sizeof(v54));
  v54.vt = 3;
  v54.lVal = v61;
  v38 = AccNavUtils::CompareIAccessibles(
          v32,
          (const struct tagVARIANT *)((char *)this + 320),
          (struct IAccessible *)ppvObject,
          &v54,
          *((HWND *)this + 29));
  if ( v51 )
    ((void (__fastcall *)(struct IAccessible *))v51->lpVtbl->Release)(v51);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  return v38;
}

```

## disassembly

```asm
0x18001df80  mov     [rsp-8+idObject], r8d
0x18001df85  mov     [rsp-8+arg_8], edx
0x18001df89  push    rbp
0x18001df8a  push    rbx
0x18001df8b  push    rsi
0x18001df8c  push    rdi
0x18001df8d  push    r12
0x18001df8f  push    r13
0x18001df91  push    r14
0x18001df93  push    r15
0x18001df95  lea     rbp, [rsp-1Fh]
0x18001df9a  sub     rsp, 98h
0x18001dfa1  mov     r12d, r8d
0x18001dfa4  mov     rsi, rcx
0x18001dfa7  cmp     [rcx+148h], edx
0x18001dfad  jnz     loc_18001E5E7
0x18001dfb3  xor     r15d, r15d
0x18001dfb6  mov     [rbp+57h+var_90], r15
0x18001dfba  lea     r13, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x18001dfc1  mov     r14d, 80004005h
0x18001dfc7  cmp     [rcx+100h], r15d
0x18001dfce  jnz     loc_18001E720
0x18001dfd4  mov     [rbp+57h+var_90], r15
0x18001dfd8  mov     rcx, [rcx+108h]
0x18001dfdf  lea     r13, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x18001dfe6  test    rcx, rcx
0x18001dfe9  jnz     loc_18001E6E5
0x18001dfef  mov     edx, [rsi+118h]
0x18001dff5  test    edx, edx
0x18001dff7  jz      loc_18001E1F2
0x18001dffd  mov     rax, [rsi+110h]
0x18001e004  test    rax, rax
0x18001e007  jz      loc_18001E5EE
0x18001e00d  mov     rcx, r15
0x18001e010  mov     [rbp+57h+var_90], rcx
0x18001e014  mov     r9, [rax+20h]
0x18001e018  test    r9, r9
0x18001e01b  jz      loc_18001E75B
0x18001e021  mov     rax, [r9]
0x18001e024  lea     r8, [rbp+57h+var_90]
0x18001e028  mov     rdx, r13
0x18001e02b  mov     rcx, r9
0x18001e02e  mov     rax, [rax]
0x18001e031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e036  mov     rcx, [rbp+57h+var_90]
0x18001e03a  mov     ebx, eax
0x18001e03c  test    ebx, ebx
0x18001e03e  js      loc_18001E723
0x18001e044  test    rcx, rcx
0x18001e047  jz      loc_18001E1FF
0x18001e04d  mov     rdi, [rsi+0E8h]
0x18001e054  mov     [rbp+57h+var_48], rdi
0x18001e058  mov     dword ptr [rbp+57h+arg_0], r15d
0x18001e05c  mov     [rbp+57h+var_78], r15
0x18001e060  mov     [rbp+57h+var_80], r15
0x18001e064  mov     rax, [rcx]
0x18001e067  lea     r8, [rbp+57h+var_80]
0x18001e06b  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001e072  mov     rax, [rax]
0x18001e075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07a  nop
0x18001e07b  mov     rbx, [rbp+57h+var_80]
0x18001e07f  test    rbx, rbx
0x18001e082  jz      loc_18001E193
0x18001e088  mov     r8d, 10h; Size
0x18001e08e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; Buf2
0x18001e095  lea     rcx, _GUID_55f9c234_79cd_4699_89e7_5518fd88bcde; Buf1
0x18001e09c  call    memcmp_0
0x18001e0a1  test    eax, eax
0x18001e0a3  jnz     loc_18001E153
0x18001e0a9  mov     rcx, r15
0x18001e0ac  mov     [rbp+57h+var_A0], rcx
0x18001e0b0  lea     rdx, aIserviceprovid; "IServiceProvider::QueryService"
0x18001e0b7  mov     qword ptr [rbp+57h+var_70], rdx
0x18001e0bb  mov     qword ptr [rbp+57h+var_70+8], rbx
0x18001e0bf  mov     dword ptr [rbp+57h+var_70+10h], edi
0x18001e0c2  mov     eax, dword ptr [rbp+57h+var_48+4]
0x18001e0c5  mov     dword ptr [rbp+57h+var_70+14h], eax
0x18001e0c8  mov     [rbp+57h+var_58], r15d
0x18001e0cc  mov     [rbp+57h+var_54], 258h
0x18001e0d3  mov     [rbp+57h+var_50], 1
0x18001e0d7  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18001e0de  jnz     loc_18001E857
0x18001e0e4  mov     rax, [rbx]
0x18001e0e7  mov     r15, [rax+18h]
0x18001e0eb  mov     [rbp+57h+var_A0], 0
0x18001e0f3  test    rcx, rcx
0x18001e0f6  jz      short loc_18001E105
0x18001e0f8  mov     rdx, [rcx]
0x18001e0fb  mov     rax, [rdx+10h]
0x18001e0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e104  nop
0x18001e105  lea     r9, [rbp+57h+var_A0]
0x18001e109  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18001e110  lea     rdx, _GUID_acd46652_829d_41cb_a5fc_17acf43661ac
0x18001e117  mov     rcx, rbx
0x18001e11a  mov     rax, r15
0x18001e11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e122  xor     r15d, r15d
0x18001e125  lea     rcx, [rbp+57h+var_70]; this
0x18001e129  cmp     [rbp+57h+var_A0], r15
0x18001e12d  jnz     loc_18001E79D
0x18001e133  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x18001e138  nop
0x18001e139  mov     rcx, [rbp+57h+var_A0]
0x18001e13d  test    rcx, rcx
0x18001e140  jz      short loc_18001E14F
0x18001e142  mov     rax, [rcx]
0x18001e145  mov     rax, [rax+10h]
0x18001e149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e14e  nop
0x18001e14f  mov     rbx, [rbp+57h+var_80]
0x18001e153  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18001e15a  jnz     loc_18001E763
0x18001e160  mov     rax, [rbx]
0x18001e163  lea     r9, [rbp+57h+var_78]
0x18001e167  lea     r8, _GUID_55f9c234_79cd_4699_89e7_5518fd88bcde
0x18001e16e  lea     rdx, IIS_AccProxyVersion
0x18001e175  mov     rcx, rbx
0x18001e178  mov     rax, [rax+18h]
0x18001e17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e181  nop
0x18001e182  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18001e189  jnz     loc_18001E740
0x18001e18f  mov     rbx, [rbp+57h+var_80]
0x18001e193  test    rbx, rbx
0x18001e196  jz      short loc_18001E1A8
0x18001e198  mov     rax, [rbx]
0x18001e19b  mov     rcx, rbx
0x18001e19e  mov     rax, [rax+10h]
0x18001e1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a7  nop
0x18001e1a8  mov     rcx, [rbp+57h+var_78]
0x18001e1ac  test    rcx, rcx
0x18001e1af  jz      short loc_18001E1C5
0x18001e1b1  mov     rax, [rcx]
0x18001e1b4  lea     rdx, [rbp+57h+arg_0]
0x18001e1b8  mov     rax, [rax+18h]
0x18001e1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c1  mov     rcx, [rbp+57h+var_78]
0x18001e1c5  mov     edi, dword ptr [rbp+57h+arg_0]
0x18001e1c8  test    rcx, rcx
0x18001e1cb  jz      short loc_18001E1DA
0x18001e1cd  mov     rax, [rcx]
0x18001e1d0  mov     rax, [rax+10h]
0x18001e1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d9  nop
0x18001e1da  mov     rcx, [rbp+57h+var_90]
0x18001e1de  test    rcx, rcx
0x18001e1e1  jz      short loc_18001E1F0
0x18001e1e3  mov     rax, [rcx]
0x18001e1e6  mov     rax, [rax+10h]
0x18001e1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ef  nop
0x18001e1f0  jmp     short loc_18001E23C
0x18001e1f2  cmp     [rsi+110h], r15
0x18001e1f9  jnz     loc_18001DFFD
0x18001e1ff  mov     ebx, r14d
0x18001e202  mov     rcx, [rbp+5Fh]; this
0x18001e206  mov     r9d, ebx; char *
0x18001e209  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x18001e210  mov     edx, 0F2Bh; void *
0x18001e215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e21a  nop
0x18001e21b  mov     rcx, [rbp+57h+var_90]
0x18001e21f  test    rcx, rcx
0x18001e222  jz      short loc_18001E231
0x18001e224  mov     rax, [rcx]
0x18001e227  mov     rax, [rax+10h]
0x18001e22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e230  nop
0x18001e231  mov     edi, r15d
0x18001e234  test    ebx, ebx
0x18001e236  js      loc_18001E5E7
0x18001e23c  mov     [rbp+57h+arg_18], r15d
0x18001e240  lea     rcx, [rsi+0D0h]
0x18001e247  mov     rax, [rcx]
0x18001e24a  lea     rdx, [rbp+57h+arg_18]
0x18001e24e  mov     rax, [rax+18h]
0x18001e252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e257  test    eax, eax
0x18001e259  js      loc_18001E5E7
0x18001e25f  mov     ebx, [rbp+57h+arg_18]
0x18001e262  mov     r15, [rsi+0E8h]
0x18001e269  mov     [rbp+57h+var_48], r15
0x18001e26d  mov     [rbp+57h+ppvObject], 0
0x18001e275  lea     rax, [rbp+57h+ppvObject]
0x18001e279  mov     [rsp+0D0h+var_A8], rax
0x18001e27e  mov     [rsp+0D0h+var_B0], r13; int
0x18001e283  mov     r9d, r12d
0x18001e286  mov     r8, r15
0x18001e289  mov     edx, ebx
0x18001e28b  mov     ecx, edi
0x18001e28d  call    cs:__imp_AccessibleObjectFromWindowTimeout
0x18001e293  test    eax, eax
0x18001e295  js      loc_18001E64A
0x18001e29b  cmp     [rbp+57h+ppvObject], 0
0x18001e2a0  jz      loc_18001E4EE
0x18001e2a6  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18001e2ac  nop
0x18001e2ad  test    al, al
0x18001e2af  jz      loc_18001E836
0x18001e2b5  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isDesktop
0x18001e2bc  jz      loc_18001E4EE
0x18001e2c2  test    r12d, r12d
0x18001e2c5  jg      loc_18001E4EE
0x18001e2cb  mov     rcx, [rbp+57h+ppvObject]
0x18001e2cf  xor     r12d, r12d
0x18001e2d2  mov     [rbp+57h+var_78], r12
0x18001e2d6  mov     [rbp+57h+arg_0], r12
0x18001e2da  mov     rax, [rcx]
0x18001e2dd  lea     r8, [rbp+57h+arg_0]
0x18001e2e1  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001e2e8  mov     rax, [rax]
0x18001e2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f0  nop
0x18001e2f1  mov     rbx, [rbp+57h+arg_0]
0x18001e2f5  test    rbx, rbx
0x18001e2f8  jz      loc_18001E380
0x18001e2fe  lea     r8d, [r12+10h]; Size
0x18001e303  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; Buf2
0x18001e30a  lea     rcx, _GUID_00000000_0000_0000_c000_000000000046; Buf1
0x18001e311  call    memcmp_0
0x18001e316  mov     edi, dword ptr [rbp+57h+var_48+4]
0x18001e319  test    eax, eax
0x18001e31b  jz      loc_18001E4F6
0x18001e321  lea     rax, aIserviceprovid; "IServiceProvider::QueryService"
0x18001e328  mov     qword ptr [rbp+57h+var_70], rax
0x18001e32c  mov     qword ptr [rbp+57h+var_70+8], rbx
0x18001e330  mov     dword ptr [rbp+57h+var_70+10h], r15d
0x18001e334  mov     dword ptr [rbp+57h+var_70+14h], edi
0x18001e337  mov     [rbp+57h+var_54], 258h
0x18001e33e  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18001e345  jnz     loc_18001E782
0x18001e34b  mov     rax, [rbx]
0x18001e34e  lea     r9, [rbp+57h+var_78]
0x18001e352  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18001e359  lea     rdx, _GUID_b96fdb85_7204_4724_842b_c7059dedb9d0
0x18001e360  mov     rcx, rbx
0x18001e363  mov     rax, [rax+18h]
0x18001e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36c  mov     [rbp+57h+var_58], eax
0x18001e36f  mov     [rbp+57h+var_50], r12b
0x18001e373  lea     rcx, [rbp+57h+var_70]; this
0x18001e377  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x18001e37c  mov     rbx, [rbp+57h+arg_0]
0x18001e380  test    rbx, rbx
0x18001e383  jz      short loc_18001E395
0x18001e385  mov     rax, [rbx]
0x18001e388  mov     rcx, rbx
0x18001e38b  mov     rax, [rax+10h]
0x18001e38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e394  nop
0x18001e395  mov     ebx, r12d
0x18001e398  mov     rcx, [rbp+57h+var_78]
0x18001e39c  test    rcx, rcx
0x18001e39f  setnz   bl
0x18001e3a2  test    rcx, rcx
0x18001e3a5  jz      short loc_18001E3B4
0x18001e3a7  mov     rax, [rcx]
0x18001e3aa  mov     rax, [rax+10h]
0x18001e3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b3  nop
0x18001e3b4  test    ebx, ebx
0x18001e3b6  jnz     loc_18001E68F
0x18001e3bc  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18001e3c2  nop
0x18001e3c3  test    al, al
0x18001e3c5  jz      loc_18001E815
0x18001e3cb  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r12b; bool BasicUiaUtils::s_isDesktop
0x18001e3d2  jz      loc_18001E895
0x18001e3d8  mov     [rbp+57h+var_88], r12
0x18001e3dc  cmp     [rsi+100h], r12d
0x18001e3e3  jnz     loc_18001E5A3
0x18001e3e9  mov     rcx, r12
0x18001e3ec  mov     [rbp+57h+var_88], rcx
0x18001e3f0  mov     rdx, [rsi+108h]
0x18001e3f7  test    rdx, rdx
0x18001e3fa  jnz     loc_18001E701
0x18001e400  mov     edx, [rsi+118h]
0x18001e406  test    edx, edx
0x18001e408  jz      loc_18001E4DC
0x18001e40e  mov     r9, [rsi+110h]
0x18001e415  test    r9, r9
0x18001e418  jz      loc_18001E61E
0x18001e41e  mov     rcx, r12
0x18001e421  mov     [rbp+57h+var_88], rcx
0x18001e425  mov     r9, [r9+20h]
0x18001e429  test    r9, r9
0x18001e42c  jz      short loc_18001E44A
0x18001e42e  mov     rax, [r9]
0x18001e431  lea     r8, [rbp+57h+var_88]
0x18001e435  mov     rdx, r13
0x18001e438  mov     rcx, r9
0x18001e43b  mov     rax, [rax]
0x18001e43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e443  mov     rcx, [rbp+57h+var_88]; struct IAccessible *
0x18001e447  mov     r14d, eax
0x18001e44a  test    r14d, r14d
0x18001e44d  js      loc_18001E5A3
  ... truncated ...
```
