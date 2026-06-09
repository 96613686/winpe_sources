# CMidiClientManager::GetMidiTransform(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &)

- ea: `0x14001a680`
- end: `0x14001b0b6`
- name: `?GetMidiTransform@CMidiClientManager@@AEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@2AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@3@Z`
- size: `2614`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, int, int, int, _QWORD *, wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x1400018e4`
- `0x140001ce8`
- `0x1400054c0`
- `0x1400060d4`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001209c`
- `0x140012f48`
- `0x140013a38`
- `0x1400182d4`
- `0x14001a680`
- `0x14001e990`
- `0x14001ea58`
- `0x14003f730`
- `0x14005a010`

## string_xrefs

- `0x14001a6dc`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001a797`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001a9fb`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001aa1c`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001aaae`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001ac0b`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001acbb`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001ad7d`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001adf1`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001afe4`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001b068`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidiClientManager::GetMidiTransform(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        int a4,
        int a5,
        _QWORD *a6,
        wchar_t *a7)
{
  int v8; // edi
  const wchar_t *v9; // rsi
  unsigned int v11; // ebx
  _DWORD *v13; // rbx
  int v14; // r8d
  int v15; // r9d
  GUID *v16; // rax
  void (*v17)(void); // rax
  _DWORD *v18; // rcx
  int v19; // r8d
  int v20; // r9d
  GUID v21; // xmm0
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  __int64 v26; // rdx
  __int64 *v27; // rbx
  __int64 *i; // rdi
  __int64 *v29; // rsi
  char IsEnabled; // al
  char v31; // al
  __int64 *v32; // rcx
  __int64 v33; // r8
  int EndpointGroupIndex; // eax
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  GUID v38; // xmm0
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  __int64 v42; // rdi
  int v43; // eax
  __int64 *v44; // rbx
  unsigned int v45; // esi
  __int64 *v46; // rsi
  __int64 *v47; // rcx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdi
  _DWORD *v51; // rbx
  int v52; // r8d
  int v53; // r9d
  wchar_t *v54; // rax
  _DWORD *v55; // rcx
  int v56; // r8d
  int v57; // r9d
  _DWORD *v58; // rcx
  int v59; // r8d
  int v60; // r9d
  int v61; // [rsp+20h] [rbp-B1h]
  int v62; // [rsp+20h] [rbp-B1h]
  __int64 *v63; // [rsp+40h] [rbp-91h] BYREF
  char v64; // [rsp+48h] [rbp-89h]
  int v65[2]; // [rsp+50h] [rbp-81h] BYREF
  const wchar_t *v66; // [rsp+58h] [rbp-79h] BYREF
  int v67; // [rsp+60h] [rbp-71h]
  int v68[2]; // [rsp+68h] [rbp-69h] BYREF
  int v69[2]; // [rsp+70h] [rbp-61h] BYREF
  wchar_t *v70; // [rsp+78h] [rbp-59h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-51h] BYREF
  __int64 v72; // [rsp+90h] [rbp-41h]
  __int64 v73; // [rsp+98h] [rbp-39h]
  GUID v74; // [rsp+A0h] [rbp-31h] BYREF
  int v75; // [rsp+B0h] [rbp-21h]
  int v76; // [rsp+B4h] [rbp-1Dh]
  unsigned __int64 v77; // [rsp+B8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v8 = a3;
  v67 = a3;
  v9 = a2;
  v66 = a2;
  v70 = a7;
  if ( !*a6 )
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x80070057LL,
      v61);
    return v11;
  }
  v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v13 > 4u )
  {
    std::wstring::wstring(&v74, *a6 + 16LL);
    v16 = &v74;
    if ( v77 > 7 )
      v16 = *(GUID **)&v74.Data1;
    *(_QWORD *)v68 = v16;
    *(_QWORD *)v69 = L"Enter";
    *(_QWORD *)v65 = a1;
    *(_QWORD *)&Buf1.Data1 = "CMidiClientManager::GetMidiTransform";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v13,
      (unsigned int)&byte_140088387,
      v14,
      v15,
      (__int64)&Buf1,
      (__int64)v65,
      (__int64)v69,
      (__int64)v68);
    std::wstring::~wstring(&v74);
  }
  v63 = 0;
  if ( a4 == a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28A,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x8000FFFFLL,
      v61);
LABEL_10:
    if ( v63 )
    {
      v17 = *(void (**)(void))(*v63 + 16);
LABEL_53:
      v17();
    }
    return 2147549183LL;
  }
  if ( a4 != 2 )
  {
    if ( a4 == 1 && a5 == 2 )
    {
      v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v22 > 4u )
      {
        *(_QWORD *)&Buf1.Data1 = L"Midi2BS2UMPTransform (Bytestream to UMP) required";
        *(_QWORD *)v65 = a1;
        *(_QWORD *)v69 = "CMidiClientManager::GetMidiTransform";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v22,
          (unsigned int)byte_1400881BD,
          v23,
          v24,
          (__int64)v69,
          (__int64)v65,
          (__int64)&Buf1);
      }
      v21 = GUID_a8798c54_6066_45f0_9adb_648bc0641abf;
      goto LABEL_22;
    }
LABEL_131:
    v58 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v58 > 2u )
    {
      v70 = L"Unsupported translation type requested. This is probably an error in specifying data format.";
      v66 = (const wchar_t *)a1;
      *(_QWORD *)&Buf1.Data1 = "CMidiClientManager::GetMidiTransform";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v58,
        (unsigned int)byte_1400876D9,
        v59,
        v60,
        (__int64)&Buf1,
        (__int64)&v66,
        (__int64)&v70);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x8007065ELL,
      v61);
    return 2147944030LL;
  }
  if ( a5 != 1 )
    goto LABEL_131;
  v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v18 > 4u )
  {
    *(_QWORD *)&Buf1.Data1 = L"Midi2UMP2BSTransform (UMP to Bytestream) required";
    *(_QWORD *)v65 = a1;
    *(_QWORD *)v69 = "CMidiClientManager::GetMidiTransform";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v18,
      (unsigned int)byte_140087B63,
      v19,
      v20,
      (__int64)v69,
      (__int64)v65,
      (__int64)&Buf1);
  }
  v21 = GUID_96121591_8d68_479f_9b48_2bf0b90113f7;
LABEL_22:
  Buf1 = v21;
  v25 = memcmp_0(&Buf1, &GUID_a8798c54_6066_45f0_9adb_648bc0641abf, 0x10u);
  v26 = 0;
  if ( v25 )
  {
    v27 = v63;
    goto LABEL_56;
  }
  std::wstring::wstring(&v74, *a6 + 16LL);
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(
    a1 + 104,
    &Buf1,
    &v74);
  std::wstring::~wstring(&v74);
  v27 = v63;
  i = *(__int64 **)&Buf1.Data1;
  v26 = 0;
  while ( 1 )
  {
    v29 = i;
    if ( i == *(__int64 **)Buf1.Data4 )
      break;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                  0);
    v27 = (__int64 *)i[8];
    v26 = 0;
    if ( IsEnabled )
    {
      v31 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
              `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
              0);
      v26 = 0;
      if ( !v31 )
        goto LABEL_41;
      if ( v27[15] != *a6 )
        goto LABEL_41;
      v27 = (__int64 *)i[8];
      if ( v67 != *((_DWORD *)v27 + 14) || a4 != *((_DWORD *)v27 + 12) || a5 != *((_DWORD *)v27 + 13) )
        goto LABEL_41;
      if ( v63 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)0x8000FFFFLL,
          v61);
        goto LABEL_10;
      }
    }
    else
    {
      if ( v67 != *((_DWORD *)v27 + 14) || a4 != *((_DWORD *)v27 + 12) || a5 != *((_DWORD *)v27 + 13) )
      {
LABEL_41:
        v27 = v63;
        goto LABEL_42;
      }
      if ( v63 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E1,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)0x8000FFFFLL,
          v61);
        v17 = *(void (**)(void))(*v63 + 16);
        goto LABEL_53;
      }
    }
    v63 = v27;
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD))(*v27 + 8))(v27, 0);
      v26 = 0;
      v27 = v63;
    }
LABEL_42:
    i = (__int64 *)i[2];
    if ( *((_BYTE *)i + 25) )
    {
      for ( i = (__int64 *)v29[1]; !*((_BYTE *)i + 25) && v29 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v29 = i;
    }
    else
    {
      v32 = (__int64 *)*i;
      if ( !*(_BYTE *)(*i + 25) )
      {
        do
        {
          i = v32;
          v32 = (__int64 *)*v32;
        }
        while ( !*((_BYTE *)v32 + 25) );
      }
    }
  }
  v8 = v67;
  v9 = v66;
LABEL_56:
  if ( v27 )
    goto LABEL_116;
  v64 = 0;
  *(_WORD *)((char *)&v77 + 5) = 0;
  HIBYTE(v77) = 0;
  Buf1 = 0;
  v72 = 0;
  v73 = 0;
  v33 = -1;
  do
    ++v33;
  while ( v9[v33] );
  std::wstring::_Construct<1,unsigned short const *>(&Buf1, v9, v33);
  EndpointGroupIndex = GetEndpointGroupIndex(&Buf1);
  v11 = EndpointGroupIndex;
  if ( EndpointGroupIndex < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F5,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)(unsigned int)EndpointGroupIndex,
      v61);
    if ( v63 )
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    return v11;
  }
  LODWORD(v77) = v8;
  v75 = a4;
  v76 = a5;
  BYTE4(v77) = v64;
  if ( a4 != 2 )
  {
    if ( a5 != 2 )
      goto LABEL_127;
    v39 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v39 > 4u )
    {
      v66 = L"Adding Midi2BS2UMPTransform (Bytestream to UMP)";
      *(_QWORD *)&Buf1.Data1 = a1;
      *(_QWORD *)v65 = "CMidiClientManager::GetMidiTransform";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v39,
        (unsigned int)&byte_1400874EF,
        v40,
        v41,
        (__int64)v65,
        (__int64)&Buf1,
        (__int64)&v66);
    }
    v38 = GUID_a8798c54_6066_45f0_9adb_648bc0641abf;
LABEL_72:
    v74 = v38;
    *(_QWORD *)v68 = 0;
    v42 = *(_QWORD *)(a1 + 40);
    v66 = (const wchar_t *)v42;
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 8LL))(v42);
    *(_QWORD *)v68 = 0;
    v43 = Microsoft::WRL::Details::MakeAndInitialize<CMidiTransformPipe,CMidiTransformPipe,>(v68);
    v11 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32B,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v43,
        v61);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( *(_QWORD *)v68 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v68 + 16LL))(*(_QWORD *)v68);
      if ( v63 )
        (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
      return v11;
    }
    v44 = *(__int64 **)v68;
    std::wstring::wstring(&Buf1, *a6 + 16LL);
    v45 = CMidiTransformPipe::Initialize((int)v44, a1 + 120, v42);
    std::wstring::~wstring(&Buf1);
    if ( (v45 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32D,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)v45,
        v62);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v44 )
        (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
      if ( v63 )
        (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
      return v45;
    }
    v46 = v63;
    v47 = v44;
    v63 = v44;
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64 *))(*v44 + 8))(v44);
      v47 = v63;
    }
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
      v47 = v63;
    }
    if ( v67 )
    {
      v49 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(*v47 + 56))(v47, a6);
      v45 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x337,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)v49,
          v62);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        if ( v44 )
          (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
        if ( v63 )
          (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
        return v45;
      }
    }
    else
    {
      v48 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a6 + 56LL))(*a6, &v63);
      v45 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x333,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)(unsigned int)v48,
          v62);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        if ( v44 )
          (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
        if ( v63 )
          (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
        return v45;
      }
    }
    std::wstring::wstring(&v74, *a6 + 16LL);
    std::multimap<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>::emplace<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy> &>(
      a1 + 104,
      &Buf1,
      &v74,
      v68);
    std::wstring::~wstring(&v74);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v44 )
      (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
    v27 = v63;
LABEL_116:
    v50 = *(_QWORD *)v70;
    *(_QWORD *)v70 = v27;
    if ( v27 )
      (*(void (__fastcall **)(__int64 *, __int64))(*v27 + 8))(v27, v26);
    if ( v50 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 16LL))(v50, v26);
    v51 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v51 > 4u )
    {
      std::wstring::wstring(&v74, *a6 + 16LL);
      v54 = (wchar_t *)&v74;
      if ( v77 > 7 )
        v54 = *(wchar_t **)&v74.Data1;
      v70 = v54;
      v66 = L"Exit";
      *(_QWORD *)&Buf1.Data1 = a1;
      *(_QWORD *)v65 = "CMidiClientManager::GetMidiTransform";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v51,
        (unsigned int)byte_140087F2B,
        v52,
        v53,
        (__int64)v65,
        (__int64)&Buf1,
        (__int64)&v66,
        (__int64)&v70);
      std::wstring::~wstring(&v74);
    }
    if ( v63 )
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    return 0;
  }
  if ( a5 == 1 )
  {
    v35 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v35 > 4u )
    {
      v66 = L"Adding Midi2UMP2BSTransform (UMP to Bytestream)";
      *(_QWORD *)&Buf1.Data1 = a1;
      *(_QWORD *)v65 = "CMidiClientManager::GetMidiTransform";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v35,
        (unsigned int)&word_1400873C6,
        v36,
        v37,
        (__int64)v65,
        (__int64)&Buf1,
        (__int64)&v66);
    }
    v38 = GUID_96121591_8d68_479f_9b48_2bf0b90113f7;
    goto LABEL_72;
  }
LABEL_127:
  v55 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v55 > 2u )
  {
    v66 = L"Unsupported translation type requested. This is probably an error in specifying data format.";
    *(_QWORD *)&Buf1.Data1 = a1;
    *(_QWORD *)v65 = "CMidiClientManager::GetMidiTransform";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v55,
      (unsigned int)byte_140087E49,
      v56,
      v57,
      (__int64)v65,
      (__int64)&Buf1,
      (__int64)&v66);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x325,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
    (const char *)0x8007065ELL,
    v61);
  if ( v63 )
    (*(void (**)(void))(*v63 + 16))();
  return 2147944030LL;
}

```

## disassembly

```asm
0x14001a680  push    rbp
0x14001a682  push    rbx
0x14001a683  push    rsi
0x14001a684  push    rdi
0x14001a685  push    r12
0x14001a687  push    r13
0x14001a689  push    r14
0x14001a68b  push    r15
0x14001a68d  lea     rbp, [rsp-7]
0x14001a692  sub     rsp, 0D8h
0x14001a699  mov     rax, cs:__security_cookie
0x14001a6a0  xor     rax, rsp
0x14001a6a3  mov     [rbp+3Fh+var_50], rax
0x14001a6a7  mov     r15d, r9d
0x14001a6aa  mov     edi, r8d
0x14001a6ad  mov     [rbp+3Fh+var_B0], r8d
0x14001a6b1  mov     rsi, rdx
0x14001a6b4  mov     [rbp+3Fh+var_B8], rdx
0x14001a6b8  mov     r13, rcx
0x14001a6bb  mov     rax, [rbp+3Fh+arg_30]
0x14001a6bf  mov     [rbp+3Fh+var_98], rax
0x14001a6c3  mov     r12, [rbp+3Fh+arg_28]
0x14001a6c7  xor     r14d, r14d
0x14001a6ca  cmp     [r12], r14
0x14001a6ce  jnz     short loc_14001A6F4
0x14001a6d0  mov     rcx, [rbp+47h]; this
0x14001a6d4  mov     ebx, 80070057h
0x14001a6d9  mov     r9d, ebx; char *
0x14001a6dc  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a6e3  mov     edx, 279h; void *
0x14001a6e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a6ed  mov     eax, ebx
0x14001a6ef  jmp     loc_14001B096
0x14001a6f4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001a6f9  mov     rbx, [rax+8]
0x14001a6fd  mov     eax, [rbx]
0x14001a6ff  cmp     eax, 4
0x14001a702  jbe     short loc_14001A77F
0x14001a704  mov     rdx, [r12]
0x14001a708  add     rdx, 10h
0x14001a70c  lea     rcx, [rbp+3Fh+var_70]
0x14001a710  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a715  lea     rax, [rbp+3Fh+var_70]
0x14001a719  cmp     [rbp+3Fh+var_58], 7
0x14001a71e  cmova   rax, qword ptr [rbp+3Fh+var_70]
0x14001a723  mov     qword ptr [rbp+3Fh+var_A8], rax
0x14001a727  lea     rax, aEnter; "Enter"
0x14001a72e  mov     qword ptr [rbp+3Fh+var_A0], rax
0x14001a732  mov     qword ptr [rsp+110h+var_C0], r13
0x14001a737  lea     rax, aCmidiclientman_1; "CMidiClientManager::GetMidiTransform"
0x14001a73e  mov     qword ptr [rbp+3Fh+Buf1], rax
0x14001a742  lea     rax, [rbp+3Fh+var_A8]
0x14001a746  mov     [rsp+110h+var_D8], rax
0x14001a74b  lea     rax, [rbp+3Fh+var_A0]
0x14001a74f  mov     [rsp+110h+var_E0], rax
0x14001a754  lea     rax, [rsp+110h+var_C0]
0x14001a759  mov     [rsp+110h+var_E8], rax
0x14001a75e  lea     rax, [rbp+3Fh+Buf1]
0x14001a762  mov     [rsp+110h+var_F0], rax; int
0x14001a767  lea     rdx, byte_140088387
0x14001a76e  mov     rcx, rbx
0x14001a771  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001a776  lea     rcx, [rbp+3Fh+var_70]; void *
0x14001a77a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a77f  mov     [rsp+110h+var_D0], r14
0x14001a784  mov     r14d, [rbp+3Fh+arg_20]
0x14001a788  cmp     r15d, r14d
0x14001a78b  jnz     short loc_14001A7C3
0x14001a78d  mov     rcx, [rbp+47h]; this
0x14001a791  mov     r9d, 8000FFFFh; char *
0x14001a797  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a79e  mov     edx, 28Ah; void *
0x14001a7a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a7a8  nop
0x14001a7a9  mov     rcx, [rsp+110h+var_D0]
0x14001a7ae  test    rcx, rcx
0x14001a7b1  jz      loc_14001AA45
0x14001a7b7  mov     rax, [rcx]
0x14001a7ba  mov     rax, [rax+10h]
0x14001a7be  jmp     loc_14001AA3F
0x14001a7c3  cmp     r15d, 2
0x14001a7c7  jnz     short loc_14001A82F
0x14001a7c9  cmp     r14d, 1
0x14001a7cd  jnz     loc_14001B00D
0x14001a7d3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001a7d8  mov     rcx, [rax+8]
0x14001a7dc  mov     eax, [rcx]
0x14001a7de  cmp     eax, 4
0x14001a7e1  jbe     short loc_14001A826
0x14001a7e3  lea     rax, aMidi2ump2bstra; "Midi2UMP2BSTransform (UMP to Bytestream"...
0x14001a7ea  mov     qword ptr [rbp+3Fh+Buf1], rax
0x14001a7ee  mov     qword ptr [rsp+110h+var_C0], r13
0x14001a7f3  lea     rax, aCmidiclientman_1; "CMidiClientManager::GetMidiTransform"
0x14001a7fa  mov     qword ptr [rbp+3Fh+var_A0], rax
0x14001a7fe  lea     rax, [rbp+3Fh+Buf1]
0x14001a802  mov     [rsp+110h+var_E0], rax
0x14001a807  lea     rax, [rsp+110h+var_C0]
0x14001a80c  mov     [rsp+110h+var_E8], rax
0x14001a811  lea     rax, [rbp+3Fh+var_A0]
0x14001a815  mov     [rsp+110h+var_F0], rax
0x14001a81a  lea     rdx, byte_140087B63
0x14001a821  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001a826  movups  xmm0, xmmword ptr cs:_GUID_96121591_8d68_479f_9b48_2bf0b90113f7.Data1
0x14001a82d  jmp     short loc_14001A89D
0x14001a82f  cmp     r15d, 1
0x14001a833  jnz     loc_14001B00D
0x14001a839  cmp     r14d, 2
0x14001a83d  jnz     loc_14001B00D
0x14001a843  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001a848  mov     rcx, [rax+8]
0x14001a84c  mov     eax, [rcx]
0x14001a84e  cmp     eax, 4
0x14001a851  jbe     short loc_14001A896
0x14001a853  lea     rax, aMidi2bs2umptra; "Midi2BS2UMPTransform (Bytestream to UMP"...
0x14001a85a  mov     qword ptr [rbp+3Fh+Buf1], rax
0x14001a85e  mov     qword ptr [rsp+110h+var_C0], r13
0x14001a863  lea     rax, aCmidiclientman_1; "CMidiClientManager::GetMidiTransform"
0x14001a86a  mov     qword ptr [rbp+3Fh+var_A0], rax
0x14001a86e  lea     rax, [rbp+3Fh+Buf1]
0x14001a872  mov     [rsp+110h+var_E0], rax
0x14001a877  lea     rax, [rsp+110h+var_C0]
0x14001a87c  mov     [rsp+110h+var_E8], rax
0x14001a881  lea     rax, [rbp+3Fh+var_A0]
0x14001a885  mov     [rsp+110h+var_F0], rax; int
0x14001a88a  lea     rdx, byte_1400881BD
0x14001a891  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001a896  movups  xmm0, xmmword ptr cs:_GUID_a8798c54_6066_45f0_9adb_648bc0641abf.Data1
0x14001a89d  movdqu  [rbp+3Fh+Buf1], xmm0
0x14001a8a2  mov     r8d, 10h; Size
0x14001a8a8  lea     rdx, _GUID_a8798c54_6066_45f0_9adb_648bc0641abf; Buf2
0x14001a8af  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x14001a8b3  call    memcmp_0
0x14001a8b8  xor     edx, edx
0x14001a8ba  test    eax, eax
0x14001a8bc  jz      short loc_14001A8C8
0x14001a8be  mov     rbx, [rsp+110h+var_D0]
0x14001a8c3  jmp     loc_14001AA56
0x14001a8c8  mov     rdx, [r12]
0x14001a8cc  add     rdx, 10h
0x14001a8d0  lea     rcx, [rbp+3Fh+var_70]
0x14001a8d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a8d9  lea     rcx, [r13+68h]
0x14001a8dd  lea     r8, [rbp+3Fh+var_70]
0x14001a8e1  lea     rdx, [rbp+3Fh+Buf1]
0x14001a8e5  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(std::wstring const &)
0x14001a8ea  lea     rcx, [rbp+3Fh+var_70]; void *
0x14001a8ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a8f3  mov     rbx, [rsp+110h+var_D0]
0x14001a8f8  mov     rdi, qword ptr [rbp+3Fh+Buf1]
0x14001a8fc  xor     edx, edx
0x14001a8fe  mov     rsi, rdi
0x14001a901  cmp     rdi, qword ptr [rbp+3Fh+Buf1+8]
0x14001a905  jz      loc_14001AA4F
0x14001a90b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14001a912  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14001a917  mov     rbx, [rdi+40h]
0x14001a91b  xor     edx, edx
0x14001a91d  test    al, al
0x14001a91f  jz      short loc_14001A962
0x14001a921  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14001a928  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14001a92d  xor     edx, edx
0x14001a92f  test    al, al
0x14001a931  jz      short loc_14001A9A3
0x14001a933  mov     rax, [r12]
0x14001a937  cmp     [rbx+78h], rax
0x14001a93b  jnz     short loc_14001A9A3
0x14001a93d  mov     rbx, [rdi+40h]
0x14001a941  mov     eax, [rbp+3Fh+var_B0]
0x14001a944  cmp     eax, [rbx+38h]
0x14001a947  jnz     short loc_14001A9A3
0x14001a949  cmp     r15d, [rbx+30h]
0x14001a94d  jnz     short loc_14001A9A3
0x14001a94f  cmp     r14d, [rbx+34h]
0x14001a953  jnz     short loc_14001A9A3
0x14001a955  cmp     [rsp+110h+var_D0], rdx
0x14001a95a  jnz     loc_14001A9F1
0x14001a960  jmp     short loc_14001A981
0x14001a962  mov     eax, [rbp+3Fh+var_B0]
0x14001a965  cmp     eax, [rbx+38h]
0x14001a968  jnz     short loc_14001A9A3
0x14001a96a  cmp     r15d, [rbx+30h]
0x14001a96e  jnz     short loc_14001A9A3
0x14001a970  cmp     r14d, [rbx+34h]
0x14001a974  jnz     short loc_14001A9A3
0x14001a976  cmp     [rsp+110h+var_D0], rdx
0x14001a97b  jnz     loc_14001AA12
0x14001a981  test    rbx, rbx
0x14001a984  mov     [rsp+110h+var_D0], rbx
0x14001a989  jz      short loc_14001A9A1
0x14001a98b  mov     rax, [rbx]
0x14001a98e  mov     rcx, rbx
0x14001a991  mov     rax, [rax+8]
0x14001a995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a99a  xor     edx, edx
0x14001a99c  mov     rbx, [rsp+110h+var_D0]
0x14001a9a1  jmp     short loc_14001A9A8
0x14001a9a3  mov     rbx, [rsp+110h+var_D0]
0x14001a9a8  mov     rdi, [rdi+10h]
0x14001a9ac  cmp     [rdi+19h], dl
0x14001a9af  jz      short loc_14001A9D2
0x14001a9b1  mov     rdi, [rsi+8]
0x14001a9b5  jmp     short loc_14001A9C8
0x14001a9b7  cmp     rsi, [rdi+10h]
0x14001a9bb  jnz     loc_14001A8FE
0x14001a9c1  mov     rsi, rdi
0x14001a9c4  mov     rdi, [rdi+8]
0x14001a9c8  cmp     [rdi+19h], dl
0x14001a9cb  jz      short loc_14001A9B7
0x14001a9cd  jmp     loc_14001A8FE
0x14001a9d2  mov     rcx, [rdi]
0x14001a9d5  cmp     [rcx+19h], dl
0x14001a9d8  jnz     loc_14001A8FE
0x14001a9de  mov     rdi, rcx
0x14001a9e1  mov     rax, [rcx]
0x14001a9e4  mov     rcx, rax
0x14001a9e7  cmp     [rax+19h], dl
0x14001a9ea  jz      short loc_14001A9DE
0x14001a9ec  jmp     loc_14001A8FE
0x14001a9f1  mov     rcx, [rbp+47h]; this
0x14001a9f5  mov     r9d, 8000FFFFh; char *
0x14001a9fb  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001aa02  mov     edx, 2D7h; void *
0x14001aa07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001aa0c  nop
0x14001aa0d  jmp     loc_14001A7A9
0x14001aa12  mov     rcx, [rbp+47h]; this
0x14001aa16  mov     r9d, 8000FFFFh; char *
0x14001aa1c  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001aa23  mov     edx, 2E1h; void *
0x14001aa28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001aa2d  nop
0x14001aa2e  mov     rcx, [rsp+110h+var_D0]
0x14001aa33  test    rcx, rcx
0x14001aa36  jz      short loc_14001AA45
0x14001aa38  mov     rdx, [rcx]
0x14001aa3b  mov     rax, [rdx+10h]
0x14001aa3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa44  nop
0x14001aa45  mov     eax, 8000FFFFh
0x14001aa4a  jmp     loc_14001B096
0x14001aa4f  mov     edi, [rbp+3Fh+var_B0]
0x14001aa52  mov     rsi, [rbp+3Fh+var_B8]
0x14001aa56  test    rbx, rbx
0x14001aa59  jnz     loc_14001AEAA
0x14001aa5f  mov     [rsp+110h+var_C8], dl
0x14001aa63  mov     word ptr [rbp+3Fh+var_58+5], dx
0x14001aa67  mov     byte ptr [rbp+3Fh+var_58+7], dl
0x14001aa6a  xorps   xmm0, xmm0
0x14001aa6d  movups  [rbp+3Fh+Buf1], xmm0
0x14001aa71  mov     [rbp+3Fh+var_80], rdx
0x14001aa75  mov     [rbp+3Fh+var_78], rdx
0x14001aa79  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001aa7d  inc     r8
0x14001aa80  cmp     [rsi+r8*2], dx
0x14001aa85  jnz     short loc_14001AA7D
0x14001aa87  mov     rdx, rsi
0x14001aa8a  lea     rcx, [rbp+3Fh+Buf1]
0x14001aa8e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001aa93  lea     rdx, [rsp+110h+var_C8]
0x14001aa98  lea     rcx, [rbp+3Fh+Buf1]; void *
0x14001aa9c  call    ?GetEndpointGroupIndex@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAE@Z; GetEndpointGroupIndex(std::wstring,uchar &)
0x14001aaa1  mov     ebx, eax
0x14001aaa3  test    eax, eax
0x14001aaa5  jns     short loc_14001AADC
0x14001aaa7  mov     rcx, [rbp+47h]; this
0x14001aaab  mov     r9d, eax; char *
0x14001aaae  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001aab5  mov     edx, 2F5h; void *
0x14001aaba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001aabf  nop
0x14001aac0  mov     rcx, [rsp+110h+var_D0]
0x14001aac5  test    rcx, rcx
0x14001aac8  jz      short loc_14001AAD7
0x14001aaca  mov     rax, [rcx]
0x14001aacd  mov     rax, [rax+10h]
0x14001aad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aad6  nop
0x14001aad7  jmp     loc_14001A6ED
0x14001aadc  mov     dword ptr [rbp+3Fh+var_58], edi
0x14001aadf  mov     [rbp+3Fh+var_60], r15d
0x14001aae3  mov     [rbp+3Fh+var_5C], r14d
0x14001aae7  mov     al, [rsp+110h+var_C8]
0x14001aaeb  mov     byte ptr [rbp+3Fh+var_58+4], al
0x14001aaee  cmp     r15d, 2
0x14001aaf2  jnz     short loc_14001AB5A
0x14001aaf4  cmp     r14d, 1
0x14001aaf8  jnz     loc_14001AF87
0x14001aafe  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001ab03  mov     rcx, [rax+8]
0x14001ab07  mov     eax, [rcx]
0x14001ab09  cmp     eax, 4
0x14001ab0c  jbe     short loc_14001AB51
0x14001ab0e  lea     rax, aAddingMidi2ump; "Adding Midi2UMP2BSTransform (UMP to Byt"...
0x14001ab15  mov     [rbp+3Fh+var_B8], rax
0x14001ab19  mov     qword ptr [rbp+3Fh+Buf1], r13
0x14001ab1d  lea     rax, aCmidiclientman_1; "CMidiClientManager::GetMidiTransform"
0x14001ab24  mov     qword ptr [rsp+110h+var_C0], rax
0x14001ab29  lea     rax, [rbp+3Fh+var_B8]
0x14001ab2d  mov     [rsp+110h+var_E0], rax
  ... truncated ...
```
