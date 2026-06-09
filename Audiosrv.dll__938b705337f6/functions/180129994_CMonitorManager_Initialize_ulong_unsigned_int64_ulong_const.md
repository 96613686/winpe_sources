# CMonitorManager::Initialize(ulong,unsigned __int64,ulong const *)

- ea: `0x180129994`
- end: `0x18012a06b`
- name: `?Initialize@CMonitorManager@@QEAAJK_KPEBK@Z`
- size: `1751`
- prototype: `__int64 __fastcall(CMonitorManager *__hidden this, unsigned int, unsigned __int64, const unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801294a8`

## callees

- `0x180008df0`
- `0x18000accc`
- `0x18000ca50`
- `0x18000e134`
- `0x180036208`
- `0x1800382ac`
- `0x180047d70`
- `0x18005c5e4`
- `0x18006e7fc`
- `0x180072450`
- `0x1800b3d4c`
- `0x1800b55c4`
- `0x1800b9bac`
- `0x1800c162c`
- `0x1800e5ab0`
- `0x180128f70`
- `0x180128fa4`
- `0x180129994`
- `0x18012a5a8`
- `0x18012a6c0`
- `0x18012b5e0`
- `0x18012bb4c`
- `0x18012bbdc`
- `0x18012c974`
- `0x18012d988`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180129f07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180129f07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129f51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180129f51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129a97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180129a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129ec6`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
        &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
        WPP_SF_d(v16[2], v17, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, (unsigned int)v15);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
            &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
0x180129994  mov     rax, rsp
0x180129997  mov     [rax+20h], r9
0x18012999b  mov     [rax+18h], r8
0x18012999f  mov     [rax+10h], edx
0x1801299a2  mov     [rax+8], rcx
0x1801299a6  push    rbx
0x1801299a7  push    rdi
0x1801299a8  push    r12
0x1801299aa  push    r13
0x1801299ac  push    r14
0x1801299ae  push    r15
0x1801299b0  sub     rsp, 0E8h
0x1801299b7  mov     r14, rcx
0x1801299ba  lea     r15, WPP_GLOBAL_Control
0x1801299c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801299c8  cmp     rcx, r15
0x1801299cb  jz      short loc_1801299F1
0x1801299cd  test    dword ptr [rcx+1Ch], 800000h
0x1801299d4  jz      short loc_1801299F1
0x1801299d6  cmp     byte ptr [rcx+19h], 4
0x1801299da  jb      short loc_1801299F1
0x1801299dc  mov     edx, 0Ah
0x1801299e1  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1801299e8  mov     rcx, [rcx+10h]
0x1801299ec  call    WPP_SF_
0x1801299f1  mov     [rsp+118h+var_A0], 0
0x1801299fa  xorps   xmm0, xmm0
0x1801299fd  movdqu  [rsp+118h+var_88], xmm0
0x180129a06  mov     [rsp+118h+var_78], 0
0x180129a12  xorps   xmm1, xmm1
0x180129a15  movdqu  [rsp+118h+var_70], xmm1
0x180129a1e  mov     [rsp+118h+var_60], 0Ah
0x180129a29  mov     [rsp+118h+var_A8], 0
0x180129a32  lea     rdx, [r14+10h]; struct _RTL_CRITICAL_SECTION *
0x180129a36  lea     rcx, [rsp+118h+var_48]; this
0x180129a3e  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x180129a43  nop
0x180129a44  lea     r12, [r14+38h]
0x180129a48  cmp     dword ptr [r12], 0
0x180129a4d  jz      short loc_180129A60
0x180129a4f  cmp     dword ptr [r12], 3
0x180129a54  jz      short loc_180129A60
0x180129a56  mov     edi, 80070057h
0x180129a5b  jmp     loc_180129F5F
0x180129a60  mov     rcx, r14; this
0x180129a63  call    ?InitializeRegistryWatcher@CMonitorManager@@AEAAJXZ; CMonitorManager::InitializeRegistryWatcher(void)
0x180129a68  mov     rcx, r14; pv
0x180129a6b  call    ?InitializeMonitorRestartTimer@CMonitorManager@@AEAAJK_KPEBK@Z; CMonitorManager::InitializeMonitorRestartTimer(ulong,unsigned __int64,ulong const *)
0x180129a70  mov     edi, eax
0x180129a72  test    eax, eax
0x180129a74  js      loc_180129F5F
0x180129a7a  lea     rbx, [r14+40h]
0x180129a7e  mov     [rsp+118h+ppv], rbx; ppv
0x180129a83  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180129a8a  xor     edx, edx; pUnkOuter
0x180129a8c  lea     r8d, [rdx+17h]; dwClsContext
0x180129a90  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180129a97  call    cs:__imp_CoCreateInstance
0x180129a9d  mov     edi, eax
0x180129a9f  test    eax, eax
0x180129aa1  js      loc_180129F5F
0x180129aa7  mov     rcx, [rsp+118h+var_A8]
0x180129aac  cmp     rcx, [rbx]
0x180129aaf  jz      short loc_180129ACA
0x180129ab1  lea     r8, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0; struct _GUID *
0x180129ab8  mov     rdx, [rbx]; struct IUnknown *
0x180129abb  lea     rcx, [rsp+118h+var_A8]; struct IUnknown **
0x180129ac0  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180129ac5  mov     rcx, [rsp+118h+var_A8]
0x180129aca  test    rcx, rcx
0x180129acd  jz      short loc_180129AE0
0x180129acf  mov     rax, [rcx]
0x180129ad2  mov     edx, 1
0x180129ad7  mov     rax, [rax+58h]
0x180129adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129ae0  mov     rcx, [rbx]
0x180129ae3  mov     rax, [rcx]
0x180129ae6  mov     rdx, r14
0x180129ae9  mov     rax, [rax+30h]
0x180129aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129af2  mov     edi, eax
0x180129af4  test    eax, eax
0x180129af6  js      loc_180129F5F
0x180129afc  mov     rcx, [rbx]
0x180129aff  mov     rax, [rcx]
0x180129b02  lea     r9, [rsp+118h+var_A0]
0x180129b07  mov     edx, 2
0x180129b0c  lea     r8d, [rdx-1]
0x180129b10  mov     rax, [rax+18h]
0x180129b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129b19  mov     edi, eax
0x180129b1b  test    eax, eax
0x180129b1d  js      loc_180129F5F
0x180129b23  mov     [rsp+118h+var_B0], 0
0x180129b2b  mov     rcx, [rsp+118h+var_A0]
0x180129b30  mov     rax, [rcx]
0x180129b33  lea     rdx, [rsp+118h+var_B0]
0x180129b38  mov     rax, [rax+18h]
0x180129b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129b41  mov     edi, eax
0x180129b43  test    eax, eax
0x180129b45  js      loc_180129F5F
0x180129b4b  mov     [rsp+118h+var_90], r12
0x180129b53  xor     r12d, r12d
0x180129b56  mov     dword ptr [rsp+118h+arg_10], r12d
0x180129b5e  cmp     r12d, [rsp+118h+var_B0]
0x180129b63  jnb     loc_180129EEA
0x180129b69  mov     [rsp+118h+var_D8], 0
0x180129b72  mov     [rsp+118h+var_B8], 0
0x180129b7b  mov     [rsp+118h+pv], 0
0x180129b84  mov     byte ptr [rsp+118h+arg_8], 0
0x180129b8c  mov     dword ptr [rsp+118h+arg_18], 0
0x180129b97  mov     rcx, [rsp+118h+var_A0]
0x180129b9c  mov     rax, [rcx]
0x180129b9f  lea     r8, [rsp+118h+var_D8]
0x180129ba4  mov     edx, r12d
0x180129ba7  mov     rax, [rax+20h]
0x180129bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129bb0  test    eax, eax
0x180129bb2  js      loc_180129EC4
0x180129bb8  mov     rcx, [rsp+118h+var_D8]
0x180129bbd  mov     rax, [rcx]
0x180129bc0  lea     r8, [rsp+118h+var_B8]
0x180129bc5  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180129bcc  mov     rax, [rax]
0x180129bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129bd4  test    eax, eax
0x180129bd6  js      loc_180129EC4
0x180129bdc  mov     rcx, [rsp+118h+var_B8]
0x180129be1  mov     rax, [rcx]
0x180129be4  lea     rdx, [rsp+118h+arg_18]
0x180129bec  mov     rax, [rax+18h]
0x180129bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129bf5  test    eax, eax
0x180129bf7  js      loc_180129EC4
0x180129bfd  mov     eax, dword ptr [rsp+118h+arg_18]
0x180129c04  cmp     eax, 1
0x180129c07  jnz     short loc_180129C2B
0x180129c09  lea     r8, [rsp+118h+arg_8]; bool *
0x180129c11  lea     rdx, [rsp+118h+pv]; unsigned __int16 **
0x180129c16  mov     rcx, [rsp+118h+var_D8]; struct IMMDevice *
0x180129c1b  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x180129c20  test    al, al
0x180129c22  jnz     short loc_180129C4D
0x180129c24  mov     eax, dword ptr [rsp+118h+arg_18]
0x180129c2b  test    eax, eax
0x180129c2d  jnz     loc_180129CD5
0x180129c33  lea     r8, [rsp+118h+pv]; unsigned __int16 **
0x180129c38  mov     rdx, [rsp+118h+var_D8]; struct IMMDevice *
0x180129c3d  mov     rcx, r14; this
0x180129c40  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x180129c45  test    al, al
0x180129c47  jz      loc_180129CD5
0x180129c4d  mov     [rsp+118h+var_D0], 0
0x180129c56  mov     [rsp+118h+var_C8], 0
0x180129c5f  mov     rdi, [rsp+118h+var_D8]
0x180129c64  mov     rax, [rdi]
0x180129c67  mov     rbx, [rax+28h]
0x180129c6b  xor     edx, edx
0x180129c6d  lea     rcx, [rsp+118h+var_C8]
0x180129c72  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180129c77  lea     rdx, [rsp+118h+var_C8]
0x180129c7c  mov     rcx, rdi
0x180129c7f  mov     rax, rbx
0x180129c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129c87  test    eax, eax
0x180129c89  jns     short loc_180129CDF
0x180129c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180129c92  cmp     rcx, r15
0x180129c95  jz      short loc_180129CBF
0x180129c97  test    dword ptr [rcx+1Ch], 800000h
0x180129c9e  jz      short loc_180129CBF
0x180129ca0  cmp     byte ptr [rcx+19h], 2
0x180129ca4  jb      short loc_180129CBF
0x180129ca6  mov     edx, 0Bh
0x180129cab  mov     r9d, eax
0x180129cae  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129cb5  mov     rcx, [rcx+10h]
0x180129cb9  call    WPP_SF_d
0x180129cbe  nop
0x180129cbf  lea     rcx, [rsp+118h+var_C8]
0x180129cc4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180129cc9  nop
0x180129cca  lea     rcx, [rsp+118h+var_D0]
0x180129ccf  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129cd4  nop
0x180129cd5  mov     rcx, [rsp+118h+pv]
0x180129cda  jmp     loc_180129EC6
0x180129cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180129ce6  cmp     rcx, r15
0x180129ce9  jz      short loc_180129D0F
0x180129ceb  test    dword ptr [rcx+1Ch], 800000h
0x180129cf2  jz      short loc_180129D0F
0x180129cf4  cmp     byte ptr [rcx+19h], 4
0x180129cf8  jb      short loc_180129D0F
0x180129cfa  mov     edx, 0Ch
0x180129cff  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129d06  mov     rcx, [rcx+10h]
0x180129d0a  call    WPP_SF_
0x180129d0f  lea     r8, LocaleName
0x180129d16  cmp     byte ptr [rsp+118h+arg_8], 0
0x180129d1e  cmovz   r8, [rsp+118h+pv]; unsigned __int16 *
0x180129d24  lea     rax, [rsp+118h+var_D0]
0x180129d29  mov     [rsp+118h+var_E8], rax; struct CMonitorManager::CaptureMonitor **
0x180129d2e  mov     [rsp+118h+var_F0], 0; struct Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *
0x180129d37  mov     byte ptr [rsp+118h+ppv], 0; bool
0x180129d3c  xor     r9d, r9d; struct StreamConnectionSettings *
0x180129d3f  mov     rdx, [rsp+118h+var_C8]; unsigned __int16 *
0x180129d44  mov     rcx, r14; this
0x180129d47  call    ?CreateMonitor@CMonitorManager@@AEAAJPEBG0PEAUStreamConnectionSettings@@_NPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@PEAPEAVCaptureMonitor@1@@Z; CMonitorManager::CreateMonitor(ushort const *,ushort const *,StreamConnectionSettings *,bool,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *,CMonitorManager::CaptureMonitor * *)
0x180129d4c  mov     edi, eax
0x180129d4e  mov     [rsp+118h+var_98], eax
0x180129d55  test    eax, eax
0x180129d57  jns     short loc_180129D8A
0x180129d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180129d60  cmp     rcx, r15
0x180129d63  jz      loc_180129CBF
0x180129d69  test    dword ptr [rcx+1Ch], 800000h
0x180129d70  jz      loc_180129CBF
0x180129d76  cmp     byte ptr [rcx+19h], 2
0x180129d7a  jb      loc_180129CBF
0x180129d80  mov     edx, 0Dh
0x180129d85  jmp     loc_180129CAB
0x180129d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180129d91  cmp     rcx, r15
0x180129d94  jz      short loc_180129DD0
0x180129d96  test    dword ptr [rcx+1Ch], 800000h
0x180129d9d  jz      short loc_180129DD0
0x180129d9f  cmp     byte ptr [rcx+19h], 4
0x180129da3  jb      short loc_180129DD0
0x180129da5  mov     edx, 0Eh
0x180129daa  mov     rbx, [rsp+118h+var_D0]
0x180129daf  mov     rax, [rbx+0D0h]
0x180129db6  mov     [rsp+118h+ppv], rax
0x180129dbb  mov     r9, rbx
0x180129dbe  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129dc5  mov     rcx, [rcx+10h]
0x180129dc9  call    WPP_SF_qq
0x180129dce  jmp     short loc_180129DD5
0x180129dd0  mov     rbx, [rsp+118h+var_D0]
0x180129dd5  mov     rdx, rbx
0x180129dd8  lea     rcx, [rsp+118h+var_88]
0x180129de0  call    ?AddTail@?$CAtlList@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAAPEAU__POSITION@@PEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(CMonitorManager::CaptureMonitor *)
0x180129de5  nop
0x180129de6  jmp     loc_180129EA0
0x180129deb  mov     r9d, [rsp+118h+arg_8]
0x180129df3  test    r9d, r9d
0x180129df6  jns     loc_180129E7D
0x180129dfc  lea     r15, WPP_GLOBAL_Control
0x180129e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180129e0a  cmp     rcx, r15
0x180129e0d  jz      short loc_180129E34
0x180129e0f  test    dword ptr [rcx+1Ch], 800000h
0x180129e16  jz      short loc_180129E34
0x180129e18  cmp     byte ptr [rcx+19h], 2
0x180129e1c  jb      short loc_180129E34
0x180129e1e  mov     edx, 0Fh
0x180129e23  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180129e2a  mov     rcx, [rcx+10h]
0x180129e2e  call    WPP_SF_d
0x180129e33  nop
0x180129e34  lea     rcx, [rsp+118h+var_C8]
0x180129e39  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180129e3e  nop
0x180129e3f  lea     rcx, [rsp+118h+var_D0]
0x180129e44  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129e49  nop
0x180129e4a  mov     rcx, [rsp+118h+pv]; pv
0x180129e4f  call    cs:__imp_CoTaskMemFree
0x180129e55  nop
0x180129e56  lea     rcx, [rsp+118h+var_B8]
0x180129e5b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129e60  nop
0x180129e61  lea     rcx, [rsp+118h+var_D8]
0x180129e66  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129e6b  mov     r14, [rsp+118h+arg_0]
0x180129e73  mov     r12d, dword ptr [rsp+118h+arg_10]
0x180129e7b  jmp     short loc_180129EE2
0x180129e7d  lea     r15, WPP_GLOBAL_Control
0x180129e84  mov     r14, [rsp+118h+arg_0]
0x180129e8c  mov     r12d, dword ptr [rsp+118h+arg_10]
0x180129e94  mov     rbx, [rsp+118h+var_D0]
0x180129e99  mov     edi, [rsp+118h+var_98]
0x180129ea0  mov     rcx, [rbx+0D0h]; this
0x180129ea7  test    edi, edi
0x180129ea9  jnz     short loc_180129EB5
0x180129eab  call    ?Start@CMonitor@@QEAAJXZ; CMonitor::Start(void)
0x180129eb0  jmp     loc_180129CBF
0x180129eb5  xor     r8d, r8d; struct _TP_CALLBACK_INSTANCE *
0x180129eb8  mov     dl, 1; bool
0x180129eba  call    ?Terminate@CMonitor@@AEAAX_NPEAU_TP_CALLBACK_INSTANCE@@@Z; CMonitor::Terminate(bool,_TP_CALLBACK_INSTANCE *)
0x180129ebf  jmp     loc_180129CBF
0x180129ec4  xor     ecx, ecx; pv
0x180129ec6  call    cs:__imp_CoTaskMemFree
0x180129ecc  nop
0x180129ecd  lea     rcx, [rsp+118h+var_B8]
0x180129ed2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180129ed7  nop
0x180129ed8  lea     rcx, [rsp+118h+var_D8]
0x180129edd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
  ... truncated ...
```
