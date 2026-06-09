# CMonitorManager::Initialize(ulong,unsigned __int64,ulong const *)

- ea: `0x180129be4`
- end: `0x18012a2bb`
- name: `?Initialize@CMonitorManager@@QEAAJK_KPEBK@Z`
- size: `1751`
- prototype: `__int64 __fastcall(CMonitorManager *__hidden this, unsigned int, unsigned __int64, const unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801296f8`

## callees

- `0x180008f40`
- `0x18000ae1c`
- `0x18000cba0`
- `0x18000e284`
- `0x180036368`
- `0x18003840c`
- `0x1800478e0`
- `0x18005c154`
- `0x18006e2fc`
- `0x180071f50`
- `0x1800b205c`
- `0x1800b38d4`
- `0x1800b805c`
- `0x1800bfadc`
- `0x1800e5330`
- `0x1801291c0`
- `0x1801291f4`
- `0x180129be4`
- `0x18012a7f8`
- `0x18012a910`
- `0x18012b830`
- `0x18012bd9c`
- `0x18012be2c`
- `0x18012cbc4`
- `0x18012dbd8`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012a1a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012a1a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129ce7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a09f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a09f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012a116`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMonitorManager::Initialize(CMonitorManager *this, int a2, _BOOL8 a3, const unsigned int *a4)
{
  CMonitorManager::CaptureMonitor *v4; // r14
  HRESULT restarted; // edi
  unsigned int v6; // edx
  unsigned __int64 v7; // r8
  const unsigned int *v8; // r9
  struct IUnknown **v9; // rbx
  struct IUnknown *v10; // rcx
  unsigned int v11; // r12d
  int v12; // eax
  struct IMMDevice *v13; // rdi
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  void *v18; // rcx
  const unsigned __int16 *v19; // r8
  int v20; // edi
  struct CMonitorManager::CaptureMonitor *v21; // rbx
  CMonitor *v22; // rcx
  struct _RTL_CRITICAL_SECTION *v23; // r12
  _QWORD *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rcx
  _QWORD *v27; // rax
  CMonitorManager::CaptureMonitor *v28; // rbx
  ATL::CAtlException *v30; // rbx
  ATL::CAtlException *v31; // rbx
  struct IMMDevice *v32; // [rsp+40h] [rbp-D8h] BYREF
  struct CMonitorManager::CaptureMonitor *v33; // [rsp+48h] [rbp-D0h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-B8h] BYREF
  unsigned int v37; // [rsp+68h] [rbp-B0h] BYREF
  struct IUnknown *v38; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+78h] [rbp-A0h] BYREF
  int v40; // [rsp+80h] [rbp-98h]
  _DWORD *v41; // [rsp+88h] [rbp-90h]
  __int128 v42; // [rsp+90h] [rbp-88h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-78h]
  __int128 v44; // [rsp+A8h] [rbp-70h]
  int v45; // [rsp+B8h] [rbp-60h]
  ATL::CAtlException *v46; // [rsp+C0h] [rbp-58h] BYREF
  ATL::CAtlException *v47; // [rsp+C8h] [rbp-50h] BYREF
  _BYTE v48[72]; // [rsp+D0h] [rbp-48h] BYREF
  CMonitorManager::CaptureMonitor *v49; // [rsp+120h] [rbp+8h] BYREF
  int v50; // [rsp+128h] [rbp+10h] BYREF
  _BOOL8 v51; // [rsp+130h] [rbp+18h]
  const unsigned int *v52; // [rsp+138h] [rbp+20h] BYREF

  v52 = a4;
  v51 = a3;
  v50 = a2;
  v49 = this;
  v4 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
  }
  v39 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 10;
  v38 = 0;
  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v48, (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 16), a3);
  if ( *((_DWORD *)v4 + 14) && *((_DWORD *)v4 + 14) != 3 )
  {
    restarted = -2147024809;
    goto LABEL_68;
  }
  CMonitorManager::InitializeRegistryWatcher(v4);
  restarted = CMonitorManager::InitializeMonitorRestartTimer(v4, v6, v7, v8);
  if ( restarted < 0 )
    goto LABEL_68;
  v9 = (struct IUnknown **)((char *)v4 + 64);
  restarted = CoCreateInstance(
                &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                0,
                0x17u,
                &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                (LPVOID *)v4 + 8);
  if ( restarted < 0 )
    goto LABEL_68;
  v10 = v38;
  if ( v38 != *v9 )
  {
    ATL::AtlComQIPtrAssign(&v38, *v9, &GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0);
    v10 = v38;
  }
  if ( v10 )
    ((void (__fastcall *)(struct IUnknown *, __int64))v10->lpVtbl[3].Release)(v10, 1);
  restarted = ((__int64 (__fastcall *)(struct IUnknown *, CMonitorManager::CaptureMonitor *))(*v9)->lpVtbl[2].QueryInterface)(
                *v9,
                v4);
  if ( restarted < 0
    || (restarted = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64 *))(*v9)->lpVtbl[1].QueryInterface)(
                      *v9,
                      2,
                      1,
                      &v39),
        restarted < 0)
    || (v37 = 0,
        restarted = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 24LL))(v39, &v37),
        restarted < 0) )
  {
LABEL_68:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
        (unsigned int)restarted);
    }
    v26 = *((_QWORD *)v4 + 8);
    if ( v26 )
    {
      (*(void (__fastcall **)(__int64, CMonitorManager::CaptureMonitor *))(*(_QWORD *)v26 + 56LL))(v26, v4);
      ATL::CComPtrBase<IPart>::Release((char *)v4 + 64);
    }
    while ( v43 )
    {
      v27 = (_QWORD *)ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::RemoveHead(
                        &v42,
                        &v52);
      wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
        &v49,
        *v27);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v52);
      v28 = v49;
      CMonitor::StopIfRunning(*((CMonitor **)v49 + 26));
      CMonitorManager::CaptureMonitor::UninitializeSynchronously(v28);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v49);
    }
    CMonitorManager::CleanupMonitorRestartTimer(v4);
    goto LABEL_77;
  }
  v41 = (_DWORD *)((char *)v4 + 56);
  v11 = 0;
  while ( 2 )
  {
    LODWORD(v51) = v11;
    if ( v11 < v37 )
    {
      v32 = 0;
      v36 = 0;
      pv = 0;
      LOBYTE(v50) = 0;
      LODWORD(v52) = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v39 + 32LL))(v39, v11, &v32) < 0
        || ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))v32->lpVtbl->QueryInterface)(
             v32,
             &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
             &v36) < 0
        || (*(int (__fastcall **)(__int64, const unsigned int **))(*(_QWORD *)v36 + 24LL))(v36, &v52) < 0 )
      {
        v18 = 0;
        goto LABEL_62;
      }
      v12 = (int)v52;
      if ( (_DWORD)v52 == 1 )
      {
        if ( CMonitor::IsCaptureMonitorEnabled(v32, (unsigned __int16 **)&pv, (bool *)&v50) )
          goto LABEL_27;
        v12 = (int)v52;
      }
      if ( v12 || !CMonitorManager::IsRenderMirrorEnabled(v4, v32, (unsigned __int16 **)&pv) )
        goto LABEL_34;
LABEL_27:
      v33 = 0;
      v34 = 0;
      v13 = v32;
      GetId = v32->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v34,
        0);
      v15 = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned __int16 **))GetId)(v13, &v34);
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_33;
        }
        v17 = 11;
LABEL_32:
        WPP_SF_d(v16[2], v17, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, (unsigned int)v15);
LABEL_33:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v34);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
LABEL_34:
        v18 = pv;
LABEL_62:
        CoTaskMemFree(v18);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v32);
        goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
      }
      v19 = &LocaleName;
      if ( !(_BYTE)v50 )
        v19 = (const unsigned __int16 *)pv;
      v15 = CMonitorManager::CreateMonitor(v4, v34, v19, 0, 0, 0, &v33);
      v20 = v15;
      v40 = v15;
      if ( v15 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_33;
        }
        v17 = 13;
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v21 = v33;
      }
      else
      {
        v21 = v33;
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
      }
      try
      {
        ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(
          &v42,
          v21);
      }
      catch ( ATL::CAtlException *v46 )
      {
        v30 = v46;
        if ( *(_DWORD *)v46 == -1073741571 )
          _o__resetstkoflw();
        v50 = *(_DWORD *)v30;
        if ( v50 >= 0 )
        {
          v4 = v49;
          v11 = v51;
          v21 = v33;
          v20 = v40;
          goto LABEL_58;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
            (unsigned int)v50);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v34);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
        CoTaskMemFree(pv);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v32);
        v4 = v49;
        v11 = v51;
LABEL_63:
        ++v11;
        continue;
      }
LABEL_58:
      v22 = (CMonitor *)*((_QWORD *)v21 + 26);
      if ( v20 )
        CMonitor::Terminate(v22, 1, 0);
      else
        CMonitor::Start(v22);
      goto LABEL_33;
    }
    break;
  }
  *v41 = 1;
  v23 = (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 72);
  v52 = (const unsigned int *)((char *)v4 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 72));
  restarted = 0;
  v24 = (_QWORD *)v42;
  try
  {
    while ( v24 )
    {
      v25 = v24[2];
      v24 = (_QWORD *)*v24;
      ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(
        (char *)v4 + 112,
        v25);
    }
  }
  catch ( ATL::CAtlException *v47 )
  {
    v31 = v47;
    if ( *(_DWORD *)v47 == -1073741571 )
      _o__resetstkoflw();
    v50 = *(_DWORD *)v31;
    v4 = v49;
    restarted = v50;
    v23 = (struct _RTL_CRITICAL_SECTION *)v52;
  }
  LeaveCriticalSection(v23);
  if ( restarted < 0 )
    goto LABEL_68;
LABEL_77:
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v48);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v38);
  ATL::CAtlList<ATL::CComQIPtr<IPolicyRule,&__s_GUID const _GUID_950f62ca_d61d_43ce_893e_dbf6fe56fbf3>,ATL::CComQIPtrElementTraits<IPolicyRule,&__s_GUID const _GUID_950f62ca_d61d_43ce_893e_dbf6fe56fbf3>>::RemoveAll(&v42);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v39);
  return (unsigned int)restarted;
}

```

## disassembly

```asm
0x180129be4  mov     rax, rsp
0x180129be7  mov     [rax+20h], r9
0x180129beb  mov     [rax+18h], r8
0x180129bef  mov     [rax+10h], edx
0x180129bf2  mov     [rax+8], rcx
0x180129bf6  push    rbx
0x180129bf7  push    rdi
0x180129bf8  push    r12
0x180129bfa  push    r13
0x180129bfc  push    r14
0x180129bfe  push    r15
0x180129c00  sub     rsp, 0E8h
0x180129c07  mov     r14, rcx
0x180129c0a  lea     r15, WPP_GLOBAL_Control
0x180129c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180129c18  cmp     rcx, r15
0x180129c1b  jz      short loc_180129C41
0x180129c1d  test    dword ptr [rcx+1Ch], 800000h
0x180129c24  jz      short loc_180129C41
0x180129c26  cmp     byte ptr [rcx+19h], 4
0x180129c2a  jb      short loc_180129C41
0x180129c2c  mov     edx, 0Ah
0x180129c31  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129c38  mov     rcx, [rcx+10h]
0x180129c3c  call    WPP_SF_
0x180129c41  mov     [rsp+118h+var_A0], 0
0x180129c4a  xorps   xmm0, xmm0
0x180129c4d  movdqu  [rsp+118h+var_88], xmm0
0x180129c56  mov     [rsp+118h+var_78], 0
0x180129c62  xorps   xmm1, xmm1
0x180129c65  movdqu  [rsp+118h+var_70], xmm1
0x180129c6e  mov     [rsp+118h+var_60], 0Ah
0x180129c79  mov     [rsp+118h+var_A8], 0
0x180129c82  lea     rdx, [r14+10h]; struct _RTL_CRITICAL_SECTION *
0x180129c86  lea     rcx, [rsp+118h+var_48]; this
0x180129c8e  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180129c93  nop
0x180129c94  lea     r12, [r14+38h]
0x180129c98  cmp     dword ptr [r12], 0
0x180129c9d  jz      short loc_180129CB0
0x180129c9f  cmp     dword ptr [r12], 3
0x180129ca4  jz      short loc_180129CB0
0x180129ca6  mov     edi, 80070057h
0x180129cab  jmp     loc_18012A1AF
0x180129cb0  mov     rcx, r14; this
0x180129cb3  call    ?InitializeRegistryWatcher@CMonitorManager@@AEAAJXZ; CMonitorManager::InitializeRegistryWatcher(void)
0x180129cb8  mov     rcx, r14; pv
0x180129cbb  call    ?InitializeMonitorRestartTimer@CMonitorManager@@AEAAJK_KPEBK@Z; CMonitorManager::InitializeMonitorRestartTimer(ulong,unsigned __int64,ulong const *)
0x180129cc0  mov     edi, eax
0x180129cc2  test    eax, eax
0x180129cc4  js      loc_18012A1AF
0x180129cca  lea     rbx, [r14+40h]
0x180129cce  mov     [rsp+118h+ppv], rbx; ppv
0x180129cd3  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180129cda  xor     edx, edx; pUnkOuter
0x180129cdc  lea     r8d, [rdx+17h]; dwClsContext
0x180129ce0  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180129ce7  call    cs:__imp_CoCreateInstance
0x180129ced  mov     edi, eax
0x180129cef  test    eax, eax
0x180129cf1  js      loc_18012A1AF
0x180129cf7  mov     rcx, [rsp+118h+var_A8]
0x180129cfc  cmp     rcx, [rbx]
0x180129cff  jz      short loc_180129D1A
0x180129d01  lea     r8, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0; struct _GUID *
0x180129d08  mov     rdx, [rbx]; struct IUnknown *
0x180129d0b  lea     rcx, [rsp+118h+var_A8]; struct IUnknown **
0x180129d10  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180129d15  mov     rcx, [rsp+118h+var_A8]
0x180129d1a  test    rcx, rcx
0x180129d1d  jz      short loc_180129D30
0x180129d1f  mov     rax, [rcx]
0x180129d22  mov     edx, 1
0x180129d27  mov     rax, [rax+58h]
0x180129d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129d30  mov     rcx, [rbx]
0x180129d33  mov     rax, [rcx]
0x180129d36  mov     rdx, r14
0x180129d39  mov     rax, [rax+30h]
0x180129d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129d42  mov     edi, eax
0x180129d44  test    eax, eax
0x180129d46  js      loc_18012A1AF
0x180129d4c  mov     rcx, [rbx]
0x180129d4f  mov     rax, [rcx]
0x180129d52  lea     r9, [rsp+118h+var_A0]
0x180129d57  mov     edx, 2
0x180129d5c  lea     r8d, [rdx-1]
0x180129d60  mov     rax, [rax+18h]
0x180129d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129d69  mov     edi, eax
0x180129d6b  test    eax, eax
0x180129d6d  js      loc_18012A1AF
0x180129d73  mov     [rsp+118h+var_B0], 0
0x180129d7b  mov     rcx, [rsp+118h+var_A0]
0x180129d80  mov     rax, [rcx]
0x180129d83  lea     rdx, [rsp+118h+var_B0]
0x180129d88  mov     rax, [rax+18h]
0x180129d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129d91  mov     edi, eax
0x180129d93  test    eax, eax
0x180129d95  js      loc_18012A1AF
0x180129d9b  mov     [rsp+118h+var_90], r12
0x180129da3  xor     r12d, r12d
0x180129da6  mov     dword ptr [rsp+118h+arg_10], r12d
0x180129dae  cmp     r12d, [rsp+118h+var_B0]
0x180129db3  jnb     loc_18012A13A
0x180129db9  mov     [rsp+118h+var_D8], 0
0x180129dc2  mov     [rsp+118h+var_B8], 0
0x180129dcb  mov     [rsp+118h+pv], 0
0x180129dd4  mov     byte ptr [rsp+118h+arg_8], 0
0x180129ddc  mov     dword ptr [rsp+118h+arg_18], 0
0x180129de7  mov     rcx, [rsp+118h+var_A0]
0x180129dec  mov     rax, [rcx]
0x180129def  lea     r8, [rsp+118h+var_D8]
0x180129df4  mov     edx, r12d
0x180129df7  mov     rax, [rax+20h]
0x180129dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129e00  test    eax, eax
0x180129e02  js      loc_18012A114
0x180129e08  mov     rcx, [rsp+118h+var_D8]
0x180129e0d  mov     rax, [rcx]
0x180129e10  lea     r8, [rsp+118h+var_B8]
0x180129e15  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180129e1c  mov     rax, [rax]
0x180129e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129e24  test    eax, eax
0x180129e26  js      loc_18012A114
0x180129e2c  mov     rcx, [rsp+118h+var_B8]
0x180129e31  mov     rax, [rcx]
0x180129e34  lea     rdx, [rsp+118h+arg_18]
0x180129e3c  mov     rax, [rax+18h]
0x180129e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129e45  test    eax, eax
0x180129e47  js      loc_18012A114
0x180129e4d  mov     eax, dword ptr [rsp+118h+arg_18]
0x180129e54  cmp     eax, 1
0x180129e57  jnz     short loc_180129E7B
0x180129e59  lea     r8, [rsp+118h+arg_8]; bool *
0x180129e61  lea     rdx, [rsp+118h+pv]; unsigned __int16 **
0x180129e66  mov     rcx, [rsp+118h+var_D8]; struct IMMDevice *
0x180129e6b  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x180129e70  test    al, al
0x180129e72  jnz     short loc_180129E9D
0x180129e74  mov     eax, dword ptr [rsp+118h+arg_18]
0x180129e7b  test    eax, eax
0x180129e7d  jnz     loc_180129F25
0x180129e83  lea     r8, [rsp+118h+pv]; unsigned __int16 **
0x180129e88  mov     rdx, [rsp+118h+var_D8]; struct IMMDevice *
0x180129e8d  mov     rcx, r14; this
0x180129e90  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x180129e95  test    al, al
0x180129e97  jz      loc_180129F25
0x180129e9d  mov     [rsp+118h+var_D0], 0
0x180129ea6  mov     [rsp+118h+var_C8], 0
0x180129eaf  mov     rdi, [rsp+118h+var_D8]
0x180129eb4  mov     rax, [rdi]
0x180129eb7  mov     rbx, [rax+28h]
0x180129ebb  xor     edx, edx
0x180129ebd  lea     rcx, [rsp+118h+var_C8]
0x180129ec2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180129ec7  lea     rdx, [rsp+118h+var_C8]
0x180129ecc  mov     rcx, rdi
0x180129ecf  mov     rax, rbx
0x180129ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129ed7  test    eax, eax
0x180129ed9  jns     short loc_180129F2F
0x180129edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180129ee2  cmp     rcx, r15
0x180129ee5  jz      short loc_180129F0F
0x180129ee7  test    dword ptr [rcx+1Ch], 800000h
0x180129eee  jz      short loc_180129F0F
0x180129ef0  cmp     byte ptr [rcx+19h], 2
0x180129ef4  jb      short loc_180129F0F
0x180129ef6  mov     edx, 0Bh
0x180129efb  mov     r9d, eax
0x180129efe  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129f05  mov     rcx, [rcx+10h]
0x180129f09  call    WPP_SF_d
0x180129f0e  nop
0x180129f0f  lea     rcx, [rsp+118h+var_C8]
0x180129f14  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180129f19  nop
0x180129f1a  lea     rcx, [rsp+118h+var_D0]
0x180129f1f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129f24  nop
0x180129f25  mov     rcx, [rsp+118h+pv]
0x180129f2a  jmp     loc_18012A116
0x180129f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180129f36  cmp     rcx, r15
0x180129f39  jz      short loc_180129F5F
0x180129f3b  test    dword ptr [rcx+1Ch], 800000h
0x180129f42  jz      short loc_180129F5F
0x180129f44  cmp     byte ptr [rcx+19h], 4
0x180129f48  jb      short loc_180129F5F
0x180129f4a  mov     edx, 0Ch
0x180129f4f  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129f56  mov     rcx, [rcx+10h]
0x180129f5a  call    WPP_SF_
0x180129f5f  lea     r8, LocaleName
0x180129f66  cmp     byte ptr [rsp+118h+arg_8], 0
0x180129f6e  cmovz   r8, [rsp+118h+pv]; unsigned __int16 *
0x180129f74  lea     rax, [rsp+118h+var_D0]
0x180129f79  mov     [rsp+118h+var_E8], rax; struct CMonitorManager::CaptureMonitor **
0x180129f7e  mov     [rsp+118h+var_F0], 0; struct Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *
0x180129f87  mov     byte ptr [rsp+118h+ppv], 0; bool
0x180129f8c  xor     r9d, r9d; struct StreamConnectionSettings *
0x180129f8f  mov     rdx, [rsp+118h+var_C8]; unsigned __int16 *
0x180129f94  mov     rcx, r14; this
0x180129f97  call    ?CreateMonitor@CMonitorManager@@AEAAJPEBG0PEAUStreamConnectionSettings@@_NPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@PEAPEAVCaptureMonitor@1@@Z; CMonitorManager::CreateMonitor(ushort const *,ushort const *,StreamConnectionSettings *,bool,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *,CMonitorManager::CaptureMonitor * *)
0x180129f9c  mov     edi, eax
0x180129f9e  mov     [rsp+118h+var_98], eax
0x180129fa5  test    eax, eax
0x180129fa7  jns     short loc_180129FDA
0x180129fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180129fb0  cmp     rcx, r15
0x180129fb3  jz      loc_180129F0F
0x180129fb9  test    dword ptr [rcx+1Ch], 800000h
0x180129fc0  jz      loc_180129F0F
0x180129fc6  cmp     byte ptr [rcx+19h], 2
0x180129fca  jb      loc_180129F0F
0x180129fd0  mov     edx, 0Dh
0x180129fd5  jmp     loc_180129EFB
0x180129fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180129fe1  cmp     rcx, r15
0x180129fe4  jz      short loc_18012A020
0x180129fe6  test    dword ptr [rcx+1Ch], 800000h
0x180129fed  jz      short loc_18012A020
0x180129fef  cmp     byte ptr [rcx+19h], 4
0x180129ff3  jb      short loc_18012A020
0x180129ff5  mov     edx, 0Eh
0x180129ffa  mov     rbx, [rsp+118h+var_D0]
0x180129fff  mov     rax, [rbx+0D0h]
0x18012a006  mov     [rsp+118h+ppv], rax
0x18012a00b  mov     r9, rbx
0x18012a00e  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x18012a015  mov     rcx, [rcx+10h]
0x18012a019  call    WPP_SF_qq
0x18012a01e  jmp     short loc_18012A025
0x18012a020  mov     rbx, [rsp+118h+var_D0]
0x18012a025  mov     rdx, rbx
0x18012a028  lea     rcx, [rsp+118h+var_88]
0x18012a030  call    ?AddTail@?$CAtlList@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAAPEAU__POSITION@@PEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(CMonitorManager::CaptureMonitor *)
0x18012a035  nop
0x18012a036  jmp     loc_18012A0F0
0x18012a03b  mov     r9d, [rsp+118h+arg_8]
0x18012a043  test    r9d, r9d
0x18012a046  jns     loc_18012A0CD
0x18012a04c  lea     r15, WPP_GLOBAL_Control
0x18012a053  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a05a  cmp     rcx, r15
0x18012a05d  jz      short loc_18012A084
0x18012a05f  test    dword ptr [rcx+1Ch], 800000h
0x18012a066  jz      short loc_18012A084
0x18012a068  cmp     byte ptr [rcx+19h], 2
0x18012a06c  jb      short loc_18012A084
0x18012a06e  mov     edx, 0Fh
0x18012a073  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x18012a07a  mov     rcx, [rcx+10h]
0x18012a07e  call    WPP_SF_d
0x18012a083  nop
0x18012a084  lea     rcx, [rsp+118h+var_C8]
0x18012a089  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18012a08e  nop
0x18012a08f  lea     rcx, [rsp+118h+var_D0]
0x18012a094  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012a099  nop
0x18012a09a  mov     rcx, [rsp+118h+pv]; pv
0x18012a09f  call    cs:__imp_CoTaskMemFree
0x18012a0a5  nop
0x18012a0a6  lea     rcx, [rsp+118h+var_B8]
0x18012a0ab  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012a0b0  nop
0x18012a0b1  lea     rcx, [rsp+118h+var_D8]
0x18012a0b6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012a0bb  mov     r14, [rsp+118h+arg_0]
0x18012a0c3  mov     r12d, dword ptr [rsp+118h+arg_10]
0x18012a0cb  jmp     short loc_18012A132
0x18012a0cd  lea     r15, WPP_GLOBAL_Control
0x18012a0d4  mov     r14, [rsp+118h+arg_0]
0x18012a0dc  mov     r12d, dword ptr [rsp+118h+arg_10]
0x18012a0e4  mov     rbx, [rsp+118h+var_D0]
0x18012a0e9  mov     edi, [rsp+118h+var_98]
0x18012a0f0  mov     rcx, [rbx+0D0h]; this
0x18012a0f7  test    edi, edi
0x18012a0f9  jnz     short loc_18012A105
0x18012a0fb  call    ?Start@CMonitor@@QEAAJXZ; CMonitor::Start(void)
0x18012a100  jmp     loc_180129F0F
0x18012a105  xor     r8d, r8d; struct _TP_CALLBACK_INSTANCE *
0x18012a108  mov     dl, 1; bool
0x18012a10a  call    ?Terminate@CMonitor@@AEAAX_NPEAU_TP_CALLBACK_INSTANCE@@@Z; CMonitor::Terminate(bool,_TP_CALLBACK_INSTANCE *)
0x18012a10f  jmp     loc_180129F0F
0x18012a114  xor     ecx, ecx; pv
0x18012a116  call    cs:__imp_CoTaskMemFree
0x18012a11c  nop
0x18012a11d  lea     rcx, [rsp+118h+var_B8]
0x18012a122  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012a127  nop
0x18012a128  lea     rcx, [rsp+118h+var_D8]
0x18012a12d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
  ... truncated ...
```
