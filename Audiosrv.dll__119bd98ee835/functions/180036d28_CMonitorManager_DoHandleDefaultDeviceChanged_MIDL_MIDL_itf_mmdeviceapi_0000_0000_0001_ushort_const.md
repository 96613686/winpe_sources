# CMonitorManager::DoHandleDefaultDeviceChanged(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ushort const *)

- ea: `0x180036d28`
- end: `0x18003736a`
- name: `?DoHandleDefaultDeviceChanged@CMonitorManager@@AEAAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEBG@Z`
- size: `1602`
- prototype: `void __fastcall(CMonitorManager *__hidden this, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801299a0`

## callees

- `0x180008f40`
- `0x18000ae1c`
- `0x18000e284`
- `0x18000e474`
- `0x18000e4d0`
- `0x1800364c4`
- `0x180036d28`
- `0x180037370`
- `0x1800383c4`
- `0x18003840c`
- `0x180051770`
- `0x18006c2e4`
- `0x18006e2fc`
- `0x180071f50`
- `0x1800c3384`
- `0x1800c8fb0`
- `0x1800e5330`
- `0x1801290fc`
- `0x1801299cc`
- `0x18012aba4`
- `0x18012cbc4`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003727d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037353`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003727d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003710c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003710c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371e6`

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
        (unsigned int)WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
        (_DWORD)v10,
        *(_QWORD *)(v21[26] + 96LL));
      v8 = WPP_GLOBAL_Control;
    }
    if ( v3 == eRender && !v9[13] || v3 == eCapture && !v9[9] )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x800000) != 0 && *((_BYTE *)v8 + 25) >= 4u )
        WPP_SF_(v8[2], 31, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
        WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
            WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
            WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
0x180036d28  mov     r11, rsp
0x180036d2b  mov     [r11+18h], r8
0x180036d2f  mov     [rsp+arg_8], edx
0x180036d33  mov     [r11+8], rcx
0x180036d37  push    rbx
0x180036d38  push    rsi
0x180036d39  push    rdi
0x180036d3a  push    r12
0x180036d3c  push    r13
0x180036d3e  push    r14
0x180036d40  sub     rsp, 0B8h
0x180036d47  mov     r13d, edx
0x180036d4a  mov     r14, rcx
0x180036d4d  lea     rax, [rcx+10h]
0x180036d51  mov     [r11-58h], rax
0x180036d55  xor     edi, edi
0x180036d57  mov     [r11-50h], dil
0x180036d5b  lea     rcx, [r11-58h]; this
0x180036d5f  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180036d64  nop
0x180036d65  cmp     dword ptr [r14+38h], 1
0x180036d6a  jnz     loc_180037341
0x180036d70  lea     rax, [r14+48h]
0x180036d74  mov     [rsp+0E8h+lpCriticalSection], rax
0x180036d79  mov     [rsp+0E8h+var_80], dil
0x180036d7e  lea     rcx, [rsp+0E8h+lpCriticalSection]; this
0x180036d83  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180036d88  nop
0x180036d89  mov     [rsp+0E8h+var_A0], rdi
0x180036d8e  mov     [rsp+0E8h+var_90], rdi
0x180036d93  mov     [rsp+0E8h+var_78], rdi
0x180036d98  mov     [rsp+0E8h+var_70], rdi
0x180036d9d  mov     [rsp+0E8h+var_68], rdi
0x180036da5  mov     [rsp+0E8h+var_60], edi
0x180036dac  mov     rax, [r14+70h]
0x180036db0  mov     [rsp+0E8h+var_98], rax
0x180036db5  lea     r12, WPP_GLOBAL_Control
0x180036dbc  jmp     loc_180036ED8
0x180036dc1  lea     rdx, [rsp+0E8h+var_98]
0x180036dc6  call    ?GetNext@?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@QEAAAEAPEAVCVADServer@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::GetNext(__POSITION * &)
0x180036dcb  mov     rdx, [rax]
0x180036dce  lea     rcx, [rsp+0E8h+var_B8]
0x180036dd3  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x180036dd8  nop
0x180036dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036de0  cmp     rcx, r12
0x180036de3  jz      short loc_180036E38
0x180036de5  test    dword ptr [rcx+1Ch], 800000h
0x180036dec  jz      short loc_180036E38
0x180036dee  cmp     byte ptr [rcx+19h], 4
0x180036df2  jb      short loc_180036E38
0x180036df4  mov     rbx, [rsp+0E8h+var_B8]
0x180036df9  mov     rax, [rbx+0D0h]
0x180036e00  mov     r8, [rax+60h]
0x180036e04  lea     r9, [rbx+88h]
0x180036e0b  cmp     qword ptr [r9+18h], 7
0x180036e10  jbe     short loc_180036E15
0x180036e12  mov     r9, [r9]
0x180036e15  mov     edx, 1Eh
0x180036e1a  mov     [rsp+0E8h+var_C8], r8
0x180036e1f  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036e26  mov     rcx, [rcx+10h]
0x180036e2a  call    WPP_SF_SS
0x180036e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e36  jmp     short loc_180036E3D
0x180036e38  mov     rbx, [rsp+0E8h+var_B8]
0x180036e3d  test    r13d, r13d
0x180036e40  jnz     short loc_180036E48
0x180036e42  cmp     [rbx+68h], rdi
0x180036e46  jz      short loc_180036E54
0x180036e48  cmp     r13d, 1
0x180036e4c  jnz     short loc_180036EC9
0x180036e4e  cmp     [rbx+48h], rdi
0x180036e52  jnz     short loc_180036EC9
0x180036e54  cmp     rcx, r12
0x180036e57  jz      short loc_180036E7E
0x180036e59  test    dword ptr [rcx+1Ch], 800000h
0x180036e60  jz      short loc_180036E7E
0x180036e62  cmp     byte ptr [rcx+19h], 4
0x180036e66  jb      short loc_180036E7E
0x180036e68  mov     edx, 1Fh
0x180036e6d  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036e74  mov     rcx, [rcx+10h]
0x180036e78  call    WPP_SF_
0x180036e7d  nop
0x180036e7e  mov     rdx, rbx
0x180036e81  lea     rcx, [rsp+0E8h+var_78]
0x180036e86  call    ?Add@?$CAtlArray@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAA_KPEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::Add(CMonitorManager::CaptureMonitor *)
0x180036e8b  nop
0x180036e8c  jmp     short loc_180036EC9
0x180036e8e  xor     edi, edi
0x180036e90  cmp     dword ptr [rsp+0E8h+arg_18], edi
0x180036e97  jge     short loc_180036EB2
0x180036e99  lea     r12, WPP_GLOBAL_Control
0x180036ea0  mov     r14, [rsp+0E8h+arg_0]
0x180036ea8  mov     r13d, [rsp+0E8h+arg_8]
0x180036eb0  jmp     short loc_180036EC9
0x180036eb2  lea     r12, WPP_GLOBAL_Control
0x180036eb9  mov     r14, [rsp+0E8h+arg_0]
0x180036ec1  mov     r13d, [rsp+0E8h+arg_8]
0x180036ec9  lea     rcx, [rsp+0E8h+var_B8]
0x180036ece  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036ed3  mov     rax, [rsp+0E8h+var_98]
0x180036ed8  test    rax, rax
0x180036edb  jnz     loc_180036DC1
0x180036ee1  mov     rbx, rdi
0x180036ee4  cmp     [rsp+0E8h+var_70], rdi
0x180036ee9  jbe     loc_180036F8B
0x180036eef  mov     rdx, [rsp+0E8h+var_78]
0x180036ef4  mov     rdx, [rdx+rbx*8]
0x180036ef8  lea     rcx, [rsp+0E8h+arg_0]
0x180036f00  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x180036f05  nop
0x180036f06  mov     [rsp+0E8h+arg_18], rdi
0x180036f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f15  cmp     rcx, r12
0x180036f18  jz      short loc_180036F3E
0x180036f1a  test    dword ptr [rcx+1Ch], 800000h
0x180036f21  jz      short loc_180036F3E
0x180036f23  cmp     byte ptr [rcx+19h], 4
0x180036f27  jb      short loc_180036F3E
0x180036f29  mov     edx, 20h ; ' '
0x180036f2e  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180036f35  mov     rcx, [rcx+10h]
0x180036f39  call    WPP_SF_
0x180036f3e  mov     rdx, [rsp+0E8h+arg_0]; struct CMonitorManager::CaptureMonitor *
0x180036f46  cmp     [rdx+31h], dil
0x180036f4a  jz      short loc_180036F56
0x180036f4c  mov     rcx, rdx; this
0x180036f4f  call    ?HandleDefaultDeviceChanges@CaptureMonitor@CMonitorManager@@QEAAJXZ; CMonitorManager::CaptureMonitor::HandleDefaultDeviceChanges(void)
0x180036f54  jmp     short loc_180036F62
0x180036f56  mov     r8b, 1; bool
0x180036f59  mov     rcx, r14; this
0x180036f5c  call    ?RemoveMonitor@CMonitorManager@@AEAAXQEBVCaptureMonitor@1@_N@Z; CMonitorManager::RemoveMonitor(CMonitorManager::CaptureMonitor const * const,bool)
0x180036f61  nop
0x180036f62  lea     rcx, [rsp+0E8h+arg_18]
0x180036f6a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036f6f  nop
0x180036f70  lea     rcx, [rsp+0E8h+arg_0]
0x180036f78  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036f7d  inc     rbx
0x180036f80  cmp     rbx, [rsp+0E8h+var_70]
0x180036f85  jb      loc_180036EEF
0x180036f8b  mov     rcx, [r14+40h]
0x180036f8f  mov     rax, [rcx]
0x180036f92  lea     r9, [rsp+0E8h+var_A0]
0x180036f97  mov     edx, 2
0x180036f9c  lea     r8d, [rdx-1]
0x180036fa0  mov     rax, [rax+18h]
0x180036fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fa9  mov     esi, eax
0x180036fab  test    eax, eax
0x180036fad  jns     short loc_180036FDF
0x180036faf  lea     rcx, [rsp+0E8h+var_78]
0x180036fb4  call    ??1?$CAtlArray@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::~CAtlArray<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>(void)
0x180036fb9  nop
0x180036fba  lea     rcx, [rsp+0E8h+var_90]
0x180036fbf  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036fc4  nop
0x180036fc5  lea     rcx, [rsp+0E8h+var_A0]
0x180036fca  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180036fcf  nop
0x180036fd0  lea     rcx, [rsp+0E8h+lpCriticalSection]; this
0x180036fd5  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180036fda  jmp     loc_18003730D
0x180036fdf  mov     [rsp+0E8h+var_A8], edi
0x180036fe3  mov     rcx, [rsp+0E8h+var_A0]
0x180036fe8  mov     rax, [rcx]
0x180036feb  lea     rdx, [rsp+0E8h+var_A8]
0x180036ff0  mov     rax, [rax+18h]
0x180036ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ff9  mov     esi, eax
0x180036ffb  test    eax, eax
0x180036ffd  js      short loc_180036FAF
0x180036fff  mov     ebx, edi
0x180037001  cmp     [rsp+0E8h+var_A8], edi
0x180037005  jbe     loc_18003720E
0x18003700b  mov     [rsp+0E8h+var_B0], rdi
0x180037010  mov     [rsp+0E8h+var_B8], rdi
0x180037015  mov     [rsp+0E8h+var_98], rdi
0x18003701a  mov     byte ptr [rsp+0E8h+arg_0], dil
0x180037022  mov     dword ptr [rsp+0E8h+arg_18], edi
0x180037029  mov     rcx, [rsp+0E8h+var_A0]
0x18003702e  mov     rax, [rcx]
0x180037031  lea     r8, [rsp+0E8h+var_B0]
0x180037036  mov     edx, ebx
0x180037038  mov     rax, [rax+20h]
0x18003703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037041  test    eax, eax
0x180037043  jns     short loc_18003706A
0x180037045  xor     ecx, ecx; pv
0x180037047  call    cs:__imp_CoTaskMemFree
0x18003704d  nop
0x18003704e  mov     rcx, [rsp+0E8h+var_B8]
0x180037053  test    rcx, rcx
0x180037056  jz      short loc_180037065
0x180037058  mov     rax, [rcx]
0x18003705b  mov     rax, [rax+10h]
0x18003705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037064  nop
0x180037065  jmp     loc_18003712A
0x18003706a  mov     rcx, [rsp+0E8h+var_B0]
0x18003706f  mov     rax, [rcx]
0x180037072  lea     r8, [rsp+0E8h+var_B8]
0x180037077  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x18003707e  mov     rax, [rax]
0x180037081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037086  test    eax, eax
0x180037088  js      loc_1800371E4
0x18003708e  mov     rcx, [rsp+0E8h+var_B8]
0x180037093  mov     rax, [rcx]
0x180037096  lea     rdx, [rsp+0E8h+arg_18]
0x18003709e  mov     rax, [rax+18h]
0x1800370a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370a7  test    eax, eax
0x1800370a9  js      loc_1800371E4
0x1800370af  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x1800370b6  test    eax, eax
0x1800370b8  jnz     loc_18003714D
0x1800370be  mov     r8, [r14+150h]; unsigned __int16 *
0x1800370c5  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x1800370ca  mov     rcx, r14; this
0x1800370cd  call    ?EnableAudioMirroringOnEndpointIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@PEAG@Z; CMonitorManager::EnableAudioMirroringOnEndpointIfAppropriate(IMMDevice *,ushort *)
0x1800370d2  test    eax, eax
0x1800370d4  jns     short loc_180037146
0x1800370d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370dd  cmp     rcx, r12
0x1800370e0  jz      short loc_18003710A
0x1800370e2  test    dword ptr [rcx+1Ch], 800000h
0x1800370e9  jz      short loc_18003710A
0x1800370eb  cmp     byte ptr [rcx+19h], 2
0x1800370ef  jb      short loc_18003710A
0x1800370f1  mov     edx, 21h ; '!'
0x1800370f6  mov     r9d, eax
0x1800370f9  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x180037100  mov     rcx, [rcx+10h]
0x180037104  call    WPP_SF_d
0x180037109  nop
0x18003710a  xor     ecx, ecx; pv
0x18003710c  call    cs:__imp_CoTaskMemFree
0x180037112  nop
0x180037113  mov     rcx, [rsp+0E8h+var_B8]
0x180037118  test    rcx, rcx
0x18003711b  jz      short loc_18003712A
0x18003711d  mov     rax, [rcx]
0x180037120  mov     rax, [rax+10h]
0x180037124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037129  nop
0x18003712a  mov     rcx, [rsp+0E8h+var_B0]
0x18003712f  test    rcx, rcx
0x180037132  jz      short loc_180037141
0x180037134  mov     rax, [rcx]
0x180037137  mov     rax, [rax+10h]
0x18003713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037140  nop
0x180037141  jmp     loc_180037202
0x180037146  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x18003714d  cmp     eax, 1
0x180037150  jnz     short loc_18003717E
0x180037152  lea     r8, [rsp+0E8h+arg_0]; bool *
0x18003715a  lea     rdx, [rsp+0E8h+var_98]; unsigned __int16 **
0x18003715f  mov     rcx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x180037164  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x180037169  test    al, al
0x18003716b  jz      short loc_180037177
0x18003716d  cmp     byte ptr [rsp+0E8h+arg_0], dil
0x180037175  jnz     short loc_180037198
0x180037177  mov     eax, dword ptr [rsp+0E8h+arg_18]
0x18003717e  test    eax, eax
0x180037180  jnz     short loc_1800371DD
0x180037182  lea     r8, [rsp+0E8h+var_98]; unsigned __int16 **
0x180037187  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x18003718c  mov     rcx, r14; this
0x18003718f  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x180037194  test    al, al
0x180037196  jz      short loc_1800371DD
0x180037198  mov     rdx, [rsp+0E8h+var_B0]; struct IMMDevice *
0x18003719d  mov     rcx, r14; this
0x1800371a0  call    ?CreateMonitorForCaptureDeviceIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@@Z; CMonitorManager::CreateMonitorForCaptureDeviceIfAppropriate(IMMDevice *)
0x1800371a5  test    eax, eax
0x1800371a7  jns     short loc_1800371DD
0x1800371a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371b0  cmp     rcx, r12
0x1800371b3  jz      short loc_1800371DD
0x1800371b5  test    dword ptr [rcx+1Ch], 800000h
0x1800371bc  jz      short loc_1800371DD
0x1800371be  cmp     byte ptr [rcx+19h], 2
0x1800371c2  jb      short loc_1800371DD
0x1800371c4  mov     edx, 22h ; '"'
0x1800371c9  mov     r9d, eax
0x1800371cc  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800371d3  mov     rcx, [rcx+10h]
0x1800371d7  call    WPP_SF_d
0x1800371dc  nop
0x1800371dd  mov     rcx, [rsp+0E8h+var_98]
0x1800371e2  jmp     short loc_1800371E6
0x1800371e4  xor     ecx, ecx; pv
0x1800371e6  call    cs:__imp_CoTaskMemFree
0x1800371ec  nop
0x1800371ed  lea     rcx, [rsp+0E8h+var_B8]
  ... truncated ...
```
