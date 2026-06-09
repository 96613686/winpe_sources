# CMonitorManager::DoHandleDefaultDeviceChanged(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ushort const *)

- ea: `0x180036bc8`
- end: `0x18003720a`
- name: `?DoHandleDefaultDeviceChanged@CMonitorManager@@AEAAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEBG@Z`
- size: `1602`
- prototype: `void __fastcall(CMonitorManager *__hidden this, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180129750`

## callees

- `0x180008df0`
- `0x18000accc`
- `0x18000e134`
- `0x18000e324`
- `0x18000e380`
- `0x180036364`
- `0x180036bc8`
- `0x180037210`
- `0x180038264`
- `0x1800382ac`
- `0x180051c00`
- `0x18006c774`
- `0x18006e7fc`
- `0x180072450`
- `0x1800c4ed4`
- `0x1800caf9c`
- `0x1800e5ab0`
- `0x180128eac`
- `0x18012977c`
- `0x18012a954`
- `0x18012c974`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003711d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003711d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800371f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037086`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CMonitorManager::DoHandleDefaultDeviceChanged(
        CMonitorManager *this,
        enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 a2,
        const unsigned __int16 *a3)
{
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v3; // r13d
  CMonitorManager::CaptureMonitor *v4; // r14
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax
  _QWORD *Next; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // r9
  unsigned __int64 i; // rbx
  int v12; // esi
  unsigned int j; // ebx
  int v14; // eax
  int v15; // eax
  int MonitorForCaptureDeviceIfAppropriate; // eax
  unsigned __int16 *v17; // rcx
  const unsigned __int16 *v18; // rbx
  CMonitorManager *v19; // rcx
  ATL::CAtlException *v20; // rbx
  _QWORD *v21; // [rsp+30h] [rbp-B8h] BYREF
  struct IMMDevice *v22; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-A0h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-98h] BYREF
  struct IMMDevice *v26; // [rsp+58h] [rbp-90h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-88h] BYREF
  char v28; // [rsp+68h] [rbp-80h]
  __int64 v29; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int64 v30; // [rsp+78h] [rbp-70h]
  __int64 v31; // [rsp+80h] [rbp-68h]
  int v32; // [rsp+88h] [rbp-60h]
  LPCRITICAL_SECTION v33; // [rsp+90h] [rbp-58h] BYREF
  char v34; // [rsp+98h] [rbp-50h]
  ATL::CAtlException *v35; // [rsp+A0h] [rbp-48h] BYREF
  CMonitorManager::CaptureMonitor *v36; // [rsp+F0h] [rbp+8h] BYREF
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v37; // [rsp+F8h] [rbp+10h]
  const unsigned __int16 *v38; // [rsp+100h] [rbp+18h]
  __int64 v39; // [rsp+108h] [rbp+20h] BYREF

  v38 = a3;
  v37 = a2;
  v36 = this;
  v3 = a2;
  v4 = this;
  v33 = (LPCRITICAL_SECTION)((char *)this + 16);
  v34 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&v33);
  if ( *((_DWORD *)v4 + 14) != 1 )
    goto LABEL_82;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v4 + 72);
  v28 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  v24 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v6 = (unsigned __int16 *)*((_QWORD *)v4 + 14);
  v25 = v6;
  while ( v6 )
  {
    Next = (_QWORD *)ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::GetNext(v5, &v25);
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      &v21,
      *Next);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v9 = v21;
    }
    else
    {
      v9 = v21;
      v10 = v21 + 17;
      if ( v21[20] > 7u )
        v10 = (_QWORD *)*v10;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
        (_DWORD)v10,
        *(_QWORD *)(v21[26] + 96LL));
      v8 = WPP_GLOBAL_Control;
    }
    if ( v3 == eRender && !v9[13] || v3 == eCapture && !v9[9] )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800000) != 0 && *((_BYTE *)v8 + 25) >= 4u )
        WPP_SF_(v8[2], 31, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
      try
      {
        ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::Add(
          &v29,
          v9);
      }
      catch ( ATL::CAtlException *v35 )
      {
        v20 = v35;
        if ( *(_DWORD *)v35 == -1073741571 )
          _o__resetstkoflw();
        LODWORD(v39) = *(_DWORD *)v20;
        v4 = v36;
        v3 = v37;
      }
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
    v6 = v25;
  }
  for ( i = 0; i < v30; ++i )
  {
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      &v36,
      *(_QWORD *)(v29 + 8 * i));
    v39 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
    }
    if ( *((_BYTE *)v36 + 49) )
      CMonitorManager::CaptureMonitor::HandleDefaultDeviceChanges(v36);
    else
      CMonitorManager::RemoveMonitor(v4, v36, 1);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v39);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v36);
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(**((_QWORD **)v4 + 8) + 24LL))(
          *((_QWORD *)v4 + 8),
          2,
          1,
          &v24);
  if ( v12 < 0
    || (v23 = 0, v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v23), v12 < 0) )
  {
    ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::~CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>(&v29);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&lpCriticalSection);
LABEL_78:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
        (unsigned int)v12);
    }
    goto LABEL_82;
  }
  for ( j = 0; j < v23; ++j )
  {
    v22 = 0;
    v21 = 0;
    v25 = 0;
    LOBYTE(v36) = 0;
    LODWORD(v39) = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v24 + 32LL))(v24, j, &v22) < 0 )
    {
      CoTaskMemFree(0);
      if ( v21 )
        (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
LABEL_47:
      if ( v22 )
        ((void (__fastcall *)(struct IMMDevice *))v22->lpVtbl->Release)(v22);
      continue;
    }
    if ( ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, _QWORD **))v22->lpVtbl->QueryInterface)(
           v22,
           &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
           &v21) < 0
      || (*(int (__fastcall **)(_QWORD *, __int64 *))(*v21 + 24LL))(v21, &v39) < 0 )
    {
      v17 = 0;
      goto LABEL_64;
    }
    v14 = v39;
    if ( !(_DWORD)v39 )
    {
      v15 = CMonitorManager::EnableAudioMirroringOnEndpointIfAppropriate(v4, v22, *((unsigned __int16 **)v4 + 42));
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
            (unsigned int)v15);
        }
        CoTaskMemFree(0);
        if ( v21 )
          (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
        goto LABEL_47;
      }
      v14 = v39;
    }
    if ( v14 == 1 )
    {
      if ( CMonitor::IsCaptureMonitorEnabled(v22, &v25, (bool *)&v36) && (_BYTE)v36 )
      {
LABEL_57:
        MonitorForCaptureDeviceIfAppropriate = CMonitorManager::CreateMonitorForCaptureDeviceIfAppropriate(v4, v22);
        if ( MonitorForCaptureDeviceIfAppropriate < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
            (unsigned int)MonitorForCaptureDeviceIfAppropriate);
        }
        goto LABEL_62;
      }
      v14 = v39;
    }
    if ( !v14 && CMonitorManager::IsRenderMirrorEnabled(v4, v22, &v25) )
      goto LABEL_57;
LABEL_62:
    v17 = v25;
LABEL_64:
    CoTaskMemFree(v17);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v22);
  }
  v18 = v38;
  v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, struct IMMDevice **))(**((_QWORD **)v4 + 8) + 40LL))(
          *((_QWORD *)v4 + 8),
          v38,
          &v26);
  if ( v12 < 0 )
  {
    ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::~CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>(&v29);
    if ( v26 )
      ((void (__fastcall *)(struct IMMDevice *))v26->lpVtbl->Release)(v26);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v28 )
      LeaveCriticalSection(lpCriticalSection);
    goto LABEL_78;
  }
  if ( v3 == eRender && !CMonitorManager::IsMonitorMirrorEligible(v19, v26) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v36,
      v18,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      (char *)v4 + 336,
      &v36);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
    if ( !*((_QWORD *)v4 + 42) )
      v12 = -2147024882;
  }
  ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::~CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>(&v29);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&lpCriticalSection);
  if ( v12 < 0 )
    goto LABEL_78;
LABEL_82:
  if ( v34 )
    LeaveCriticalSection(v33);
}

```

## disassembly

```asm
0x180036bc8  mov     r11, rsp
0x180036bcb  mov     [r11+18h], r8
0x180036bcf  mov     [rsp+arg_8], edx
0x180036bd3  mov     [r11+8], rcx
0x180036bd7  push    rbx
0x180036bd8  push    rsi
0x180036bd9  push    rdi
0x180036bda  push    r12
0x180036bdc  push    r13
0x180036bde  push    r14
0x180036be0  sub     rsp, 0B8h
0x180036be7  mov     r13d, edx
0x180036bea  mov     r14, rcx
0x180036bed  lea     rax, [rcx+10h]
0x180036bf1  mov     [r11-58h], rax
0x180036bf5  xor     edi, edi
0x180036bf7  mov     [r11-50h], dil
0x180036bfb  lea     rcx, [r11-58h]; this
0x180036bff  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180036c04  nop
0x180036c05  cmp     dword ptr [r14+38h], 1
0x180036c0a  jnz     loc_1800371E1
0x180036c10  lea     rax, [r14+48h]
0x180036c14  mov     [rsp+0E8h+lpCriticalSection], rax
0x180036c19  mov     [rsp+0E8h+var_80], dil
0x180036c1e  lea     rcx, [rsp+0E8h+lpCriticalSection]; this
0x180036c23  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180036c28  nop
0x180036c29  mov     [rsp+0E8h+var_A0], rdi
0x180036c2e  mov     [rsp+0E8h+var_90], rdi
0x180036c33  mov     [rsp+0E8h+var_78], rdi
0x180036c38  mov     [rsp+0E8h+var_70], rdi
0x180036c3d  mov     [rsp+0E8h+var_68], rdi
0x180036c45  mov     [rsp+0E8h+var_60], edi
0x180036c4c  mov     rax, [r14+70h]
0x180036c50  mov     [rsp+0E8h+var_98], rax
0x180036c55  lea     r12, WPP_GLOBAL_Control
0x180036c5c  jmp     loc_180036D78
0x180036c61  lea     rdx, [rsp+0E8h+var_98]
0x180036c66  call    ?GetNext@?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@QEAAAEAPEAVCVADServer@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::GetNext(__POSITION * &)
0x180036c6b  mov     rdx, [rax]
0x180036c6e  lea     rcx, [rsp+0E8h+var_B8]
0x180036c73  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x180036c78  nop
0x180036c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c80  cmp     rcx, r12
0x180036c83  jz      short loc_180036CD8
0x180036c85  test    dword ptr [rcx+1Ch], 800000h
0x180036c8c  jz      short loc_180036CD8
0x180036c8e  cmp     byte ptr [rcx+19h], 4
0x180036c92  jb      short loc_180036CD8
0x180036c94  mov     rbx, [rsp+0E8h+var_B8]
0x180036c99  mov     rax, [rbx+0D0h]
0x180036ca0  mov     r8, [rax+60h]
0x180036ca4  lea     r9, [rbx+88h]
0x180036cab  cmp     qword ptr [r9+18h], 7
0x180036cb0  jbe     short loc_180036CB5
0x180036cb2  mov     r9, [r9]
0x180036cb5  mov     edx, 1Eh
0x180036cba  mov     [rsp+0E8h+var_C8], r8
0x180036cbf  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036cc6  mov     rcx, [rcx+10h]
0x180036cca  call    WPP_SF_SS
0x180036ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cd6  jmp     short loc_180036CDD
0x180036cd8  mov     rbx, [rsp+0E8h+var_B8]
0x180036cdd  test    r13d, r13d
0x180036ce0  jnz     short loc_180036CE8
0x180036ce2  cmp     [rbx+68h], rdi
0x180036ce6  jz      short loc_180036CF4
0x180036ce8  cmp     r13d, 1
0x180036cec  jnz     short loc_180036D69
0x180036cee  cmp     [rbx+48h], rdi
0x180036cf2  jnz     short loc_180036D69
0x180036cf4  cmp     rcx, r12
0x180036cf7  jz      short loc_180036D1E
0x180036cf9  test    dword ptr [rcx+1Ch], 800000h
0x180036d00  jz      short loc_180036D1E
0x180036d02  cmp     byte ptr [rcx+19h], 4
0x180036d06  jb      short loc_180036D1E
0x180036d08  mov     edx, 1Fh
0x180036d0d  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036d14  mov     rcx, [rcx+10h]
0x180036d18  call    WPP_SF_
0x180036d1d  nop
0x180036d1e  mov     rdx, rbx
0x180036d21  lea     rcx, [rsp+0E8h+var_78]
0x180036d26  call    ?Add@?$CAtlArray@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAA_KPEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::Add(CMonitorManager::CaptureMonitor *)
0x180036d2b  nop
0x180036d2c  jmp     short loc_180036D69
0x180036d2e  xor     edi, edi
0x180036d30  cmp     dword ptr [rsp+0E8h+arg_18], edi
0x180036d37  jge     short loc_180036D52
0x180036d39  lea     r12, WPP_GLOBAL_Control
0x180036d40  mov     r14, [rsp+0E8h+arg_0]
0x180036d48  mov     r13d, [rsp+0E8h+arg_8]
0x180036d50  jmp     short loc_180036D69
0x180036d52  lea     r12, WPP_GLOBAL_Control
0x180036d59  mov     r14, [rsp+0E8h+arg_0]
0x180036d61  mov     r13d, [rsp+0E8h+arg_8]
0x180036d69  lea     rcx, [rsp+0E8h+var_B8]
0x180036d6e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036d73  mov     rax, [rsp+0E8h+var_98]
0x180036d78  test    rax, rax
0x180036d7b  jnz     loc_180036C61
0x180036d81  mov     rbx, rdi
0x180036d84  cmp     [rsp+0E8h+var_70], rdi
0x180036d89  jbe     loc_180036E2B
0x180036d8f  mov     rdx, [rsp+0E8h+var_78]
0x180036d94  mov     rdx, [rdx+rbx*8]
0x180036d98  lea     rcx, [rsp+0E8h+arg_0]
0x180036da0  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x180036da5  nop
0x180036da6  mov     [rsp+0E8h+arg_18], rdi
0x180036dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180036db5  cmp     rcx, r12
0x180036db8  jz      short loc_180036DDE
0x180036dba  test    dword ptr [rcx+1Ch], 800000h
0x180036dc1  jz      short loc_180036DDE
0x180036dc3  cmp     byte ptr [rcx+19h], 4
0x180036dc7  jb      short loc_180036DDE
0x180036dc9  mov     edx, 20h ; ' '
0x180036dce  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036dd5  mov     rcx, [rcx+10h]
0x180036dd9  call    WPP_SF_
0x180036dde  mov     rdx, [rsp+0E8h+arg_0]; struct CMonitorManager::CaptureMonitor *
0x180036de6  cmp     [rdx+31h], dil
0x180036dea  jz      short loc_180036DF6
0x180036dec  mov     rcx, rdx; this
0x180036def  call    ?HandleDefaultDeviceChanges@CaptureMonitor@CMonitorManager@@QEAAJXZ; CMonitorManager::CaptureMonitor::HandleDefaultDeviceChanges(void)
0x180036df4  jmp     short loc_180036E02
0x180036df6  mov     r8b, 1; bool
0x180036df9  mov     rcx, r14; this
0x180036dfc  call    ?RemoveMonitor@CMonitorManager@@AEAAXQEBVCaptureMonitor@1@_N@Z; CMonitorManager::RemoveMonitor(CMonitorManager::CaptureMonitor const * const,bool)
0x180036e01  nop
0x180036e02  lea     rcx, [rsp+0E8h+arg_18]
0x180036e0a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036e0f  nop
0x180036e10  lea     rcx, [rsp+0E8h+arg_0]
0x180036e18  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036e1d  inc     rbx
0x180036e20  cmp     rbx, [rsp+0E8h+var_70]
0x180036e25  jb      loc_180036D8F
0x180036e2b  mov     rcx, [r14+40h]
0x180036e2f  mov     rax, [rcx]
0x180036e32  lea     r9, [rsp+0E8h+var_A0]
0x180036e37  mov     edx, 2
0x180036e3c  lea     r8d, [rdx-1]
0x180036e40  mov     rax, [rax+18h]
0x180036e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e49  mov     esi, eax
0x180036e4b  test    eax, eax
0x180036e4d  jns     short loc_180036E7F
0x180036e4f  lea     rcx, [rsp+0E8h+var_78]
0x180036e54  call    ??1?$CAtlArray@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::~CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>(void)
0x180036e59  nop
0x180036e5a  lea     rcx, [rsp+0E8h+var_90]
0x180036e5f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036e64  nop
0x180036e65  lea     rcx, [rsp+0E8h+var_A0]
0x180036e6a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036e6f  nop
0x180036e70  lea     rcx, [rsp+0E8h+lpCriticalSection]; this
0x180036e75  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180036e7a  jmp     loc_1800371AD
0x180036e7f  mov     [rsp+0E8h+var_A8], edi
0x180036e83  mov     rcx, [rsp+0E8h+var_A0]
0x180036e88  mov     rax, [rcx]
0x180036e8b  lea     rdx, [rsp+0E8h+var_A8]
0x180036e90  mov     rax, [rax+18h]
0x180036e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e99  mov     esi, eax
0x180036e9b  test    eax, eax
0x180036e9d  js      short loc_180036E4F
0x180036e9f  mov     ebx, edi
0x180036ea1  cmp     [rsp+0E8h+var_A8], edi
0x180036ea5  jbe     loc_1800370AE
0x180036eab  mov     [rsp+0E8h+var_B0], rdi
0x180036eb0  mov     [rsp+0E8h+var_B8], rdi
0x180036eb5  mov     [rsp+0E8h+var_98], rdi
0x180036eba  mov     byte ptr [rsp+0E8h+arg_0], dil
0x180036ec2  mov     dword ptr [rsp+0E8h+arg_18], edi
0x180036ec9  mov     rcx, [rsp+0E8h+var_A0]
0x180036ece  mov     rax, [rcx]
0x180036ed1  lea     r8, [rsp+0E8h+var_B0]
0x180036ed6  mov     edx, ebx
0x180036ed8  mov     rax, [rax+20h]
0x180036edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ee1  test    eax, eax
0x180036ee3  jns     short loc_180036F0A
0x180036ee5  xor     ecx, ecx; pv
0x180036ee7  call    cs:__imp_CoTaskMemFree
0x180036eed  nop
0x180036eee  mov     rcx, [rsp+0E8h+var_B8]
0x180036ef3  test    rcx, rcx
0x180036ef6  jz      short loc_180036F05
0x180036ef8  mov     rax, [rcx]
0x180036efb  mov     rax, [rax+10h]
0x180036eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f04  nop
0x180036f05  jmp     loc_180036FCA
0x180036f0a  mov     rcx, [rsp+0E8h+var_B0]
0x180036f0f  mov     rax, [rcx]
0x180036f12  lea     r8, [rsp+0E8h+var_B8]
0x180036f17  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180036f1e  mov     rax, [rax]
0x180036f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f26  test    eax, eax
0x180036f28  js      loc_180037084
0x180036f2e  mov     rcx, [rsp+0E8h+var_B8]
0x180036f33  mov     rax, [rcx]
0x180036f36  lea     rdx, [rsp+0E8h+arg_18]
0x180036f3e  mov     rax, [rax+18h]
0x180036f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f47  test    eax, eax
0x180036f49  js      loc_180037084
0x180036f4f  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x180036f56  test    eax, eax
0x180036f58  jnz     loc_180036FED
0x180036f5e  mov     r8, [r14+150h]; unsigned __int16 *
0x180036f65  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x180036f6a  mov     rcx, r14; this
0x180036f6d  call    ?EnableAudioMirroringOnEndpointIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@PEAG@Z; CMonitorManager::EnableAudioMirroringOnEndpointIfAppropriate(IMMDevice *,ushort *)
0x180036f72  test    eax, eax
0x180036f74  jns     short loc_180036FE6
0x180036f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f7d  cmp     rcx, r12
0x180036f80  jz      short loc_180036FAA
0x180036f82  test    dword ptr [rcx+1Ch], 800000h
0x180036f89  jz      short loc_180036FAA
0x180036f8b  cmp     byte ptr [rcx+19h], 2
0x180036f8f  jb      short loc_180036FAA
0x180036f91  mov     edx, 21h ; '!'
0x180036f96  mov     r9d, eax
0x180036f99  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036fa0  mov     rcx, [rcx+10h]
0x180036fa4  call    WPP_SF_d
0x180036fa9  nop
0x180036faa  xor     ecx, ecx; pv
0x180036fac  call    cs:__imp_CoTaskMemFree
0x180036fb2  nop
0x180036fb3  mov     rcx, [rsp+0E8h+var_B8]
0x180036fb8  test    rcx, rcx
0x180036fbb  jz      short loc_180036FCA
0x180036fbd  mov     rax, [rcx]
0x180036fc0  mov     rax, [rax+10h]
0x180036fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fc9  nop
0x180036fca  mov     rcx, [rsp+0E8h+var_B0]
0x180036fcf  test    rcx, rcx
0x180036fd2  jz      short loc_180036FE1
0x180036fd4  mov     rax, [rcx]
0x180036fd7  mov     rax, [rax+10h]
0x180036fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe0  nop
0x180036fe1  jmp     loc_1800370A2
0x180036fe6  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x180036fed  cmp     eax, 1
0x180036ff0  jnz     short loc_18003701E
0x180036ff2  lea     r8, [rsp+0E8h+arg_0]; bool *
0x180036ffa  lea     rdx, [rsp+0E8h+var_98]; unsigned __int16 **
0x180036fff  mov     rcx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x180037004  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x180037009  test    al, al
0x18003700b  jz      short loc_180037017
0x18003700d  cmp     byte ptr [rsp+0E8h+arg_0], dil
0x180037015  jnz     short loc_180037038
0x180037017  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x18003701e  test    eax, eax
0x180037020  jnz     short loc_18003707D
0x180037022  lea     r8, [rsp+0E8h+var_98]; unsigned __int16 **
0x180037027  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x18003702c  mov     rcx, r14; this
0x18003702f  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x180037034  test    al, al
0x180037036  jz      short loc_18003707D
0x180037038  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x18003703d  mov     rcx, r14; this
0x180037040  call    ?CreateMonitorForCaptureDeviceIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@@Z; CMonitorManager::CreateMonitorForCaptureDeviceIfAppropriate(IMMDevice *)
0x180037045  test    eax, eax
0x180037047  jns     short loc_18003707D
0x180037049  mov     rcx, cs:WPP_GLOBAL_Control
0x180037050  cmp     rcx, r12
0x180037053  jz      short loc_18003707D
0x180037055  test    dword ptr [rcx+1Ch], 800000h
0x18003705c  jz      short loc_18003707D
0x18003705e  cmp     byte ptr [rcx+19h], 2
0x180037062  jb      short loc_18003707D
0x180037064  mov     edx, 22h ; '"'
0x180037069  mov     r9d, eax
0x18003706c  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180037073  mov     rcx, [rcx+10h]
0x180037077  call    WPP_SF_d
0x18003707c  nop
0x18003707d  mov     rcx, [rsp+0E8h+var_98]
0x180037082  jmp     short loc_180037086
0x180037084  xor     ecx, ecx; pv
0x180037086  call    cs:__imp_CoTaskMemFree
0x18003708c  nop
0x18003708d  lea     rcx, [rsp+0E8h+var_B8]
  ... truncated ...
```
