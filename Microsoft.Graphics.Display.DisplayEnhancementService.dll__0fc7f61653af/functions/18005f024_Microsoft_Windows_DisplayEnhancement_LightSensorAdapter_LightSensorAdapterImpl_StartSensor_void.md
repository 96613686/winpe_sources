# Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::StartSensor(void)

- ea: `0x18005f024`
- end: `0x18005f301`
- name: `?StartSensor@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `733`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f308`
- `0x18005f348`

## callees

- `0x180005860`
- `0x180009a84`
- `0x18000f778`
- `0x18000fa0c`
- `0x1800121d0`
- `0x180013578`
- `0x18005bde0`
- `0x18005be10`
- `0x18005e7d0`
- `0x18005f024`
- `0x18005f8b0`
- `0x18005f9b0`

## import_xrefs

- `SensorsNativeApi!SensorOpenByInterface` at `0x18005f078`
- `SensorsNativeApi!SensorOpenByInterface` at `0x18005f078`
- `SensorsNativeApi!SensorStartCollection` at `0x18005f2b3`
- `SensorsNativeApi!SensorStartCollection` at `0x18005f2b3`
- `SensorsNativeApi!SensorSetAlsWithColorThresholds` at `0x18005f236`
- `SensorsNativeApi!SensorSetAlsWithColorThresholds` at `0x18005f236`
- `SensorsUtilsV2!InitPropVariantFromFloat` at `0x18005f275`
- `SensorsUtilsV2!InitPropVariantFromFloat` at `0x18005f275`
- `SensorsUtilsV2!PropKeyFindKeySetPropVariant` at `0x18005f290`
- `SensorsUtilsV2!PropKeyFindKeySetPropVariant` at `0x18005f290`

## string_xrefs

- `0x18005f247`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`
- `0x18005f2c4`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::StartSensor(
        Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  _QWORD *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // edx
  int v8; // r9d
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // r10
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rcx
  unsigned int v17; // eax
  unsigned int started; // eax
  unsigned __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20[2]; // [rsp+20h] [rbp-E0h]
  _DWORD v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v24[5]; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+80h] [rbp-80h]
  char v26; // [rsp+84h] [rbp-7Ch]
  Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *v27; // [rsp+88h] [rbp-78h]
  _QWORD *v28; // [rsp+90h] [rbp-70h]
  _QWORD v29[2]; // [rsp+98h] [rbp-68h] BYREF
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+ACh] [rbp-54h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  char v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  _QWORD *v36; // [rsp+D0h] [rbp-30h]
  PROPVARIANT ppropvar[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v38[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v39; // [rsp+F8h] [rbp-8h]
  char v40; // [rsp+FCh] [rbp-4h]
  void (__fastcall *v41)(Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *__hidden, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr); // [rsp+108h] [rbp+8h]
  int v42; // [rsp+110h] [rbp+10h]
  int v43; // [rsp+114h] [rbp+14h]
  _QWORD v44[2]; // [rsp+118h] [rbp+18h] BYREF
  char v45; // [rsp+128h] [rbp+28h]
  __int64 v46; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v23,
    (Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *)((char *)this + 96));
  v4 = (_QWORD *)((char *)this + 200);
  if ( !*((_QWORD *)this + 25) )
  {
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8, v2, v3);
    v6 = SensorOpenByInterface(v5);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (char *)this + 200,
      v6);
    *(_QWORD *)&v22.Data1 = this;
    v41 = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::OnAlsHandleReopen;
    v42 = 0;
    v43 = HIDWORD(ppropvar[1]);
    std::tuple<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1>,_GUID>::tuple<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1>,_GUID>(
      (unsigned int)v44,
      v7,
      (unsigned int)&v22,
      v8,
      (__int64)&GUID_SensorType_AmbientLight);
    ppropvar[0] = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::OnAlsRemoved;
    LODWORD(ppropvar[1]) = 0;
    std::tuple<std::_Ph<1>,std::_Ph<2>,_GUID>::tuple<std::_Ph<1>,std::_Ph<2>,_GUID>(
      (unsigned int)v38,
      v9,
      v10,
      v11,
      v12);
    v24[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::*)(void *,bool,_GUID),Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1> const &,std::_Ph<2> const &,_GUID const &>,void,void *,bool>::`vftable';
    v24[1] = ppropvar[0];
    v24[2] = ppropvar[1];
    v24[3] = v38[0];
    v24[4] = v38[1];
    v25 = v39;
    v26 = v40;
    v27 = this;
    v28 = v24;
    v29[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::*)(_GUID,_GUID),Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1> const &,_GUID const &>,void,_GUID>::`vftable';
    v29[1] = v41;
    v30 = v42;
    v31 = v43;
    v32 = v44[0];
    v33 = v44[1];
    v34 = v45;
    v35 = v46;
    v36 = v29;
    v22 = GUID_SensorType_AmbientLight;
    v13 = (__int64 *)PnpDeviceInstance::MakeAndInitialize(
                       (unsigned int)ppropvar,
                       (unsigned int)&v22,
                       *v4,
                       (unsigned int)v29,
                       (__int64)v24);
    v14 = *v13;
    v15 = v13[1];
    *v13 = 0;
    v13[1] = 0;
    *((_QWORD *)this + 26) = v14;
    v16 = (std::_Ref_count_base *)*((_QWORD *)this + 27);
    *((_QWORD *)this + 27) = v15;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( ppropvar[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)ppropvar[1]);
  }
  *((_BYTE *)this + 133) = 1;
  v21[0] = 0;
  v19 = (unsigned __int64)v21 & -(__int64)(*((_BYTE *)this + 124) != 0);
  v17 = SensorSetAlsWithColorThresholds(*v4, *((_QWORD *)this + 17), v21, 0);
  if ( v17 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
      (const char *)v17,
      v19);
  if ( *((_BYTE *)this + 116) )
  {
    *(_OWORD *)ppropvar = 0;
    v38[0] = 0;
    InitPropVariantFromFloat(*((FLOAT *)this + 28), ppropvar);
    PropKeyFindKeySetPropVariant(
      *((SENSOR_COLLECTION_LIST **)this + 17),
      &PKEY_SensorData_LightLevel_Lux_Threshold_AbsoluteDifference,
      1u,
      ppropvar);
  }
  *(_QWORD *)v20 = *((_QWORD *)this + 17);
  started = SensorStartCollection(
              *v4,
              Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::DataCallbackShim,
              this,
              *((unsigned int *)this + 26));
  if ( started )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
      (const char *)started,
      v20[0]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v23);
}

```

## disassembly

```asm
0x18005f024  mov     [rsp-8+arg_8], rbx
0x18005f029  mov     [rsp-8+arg_10], rdi
0x18005f02e  push    rbp
0x18005f02f  lea     rbp, [rsp-40h]
0x18005f034  sub     rsp, 140h
0x18005f03b  mov     rax, cs:__security_cookie
0x18005f042  xor     rax, rsp
0x18005f045  mov     [rbp+40h+var_8], rax
0x18005f049  mov     rbx, rcx
0x18005f04c  lea     rdx, [rcx+60h]; struct wil::srwlock *
0x18005f050  lea     rcx, [rsp+140h+var_F0]; this
0x18005f055  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18005f05a  nop
0x18005f05b  lea     rdi, [rbx+0C8h]
0x18005f062  cmp     qword ptr [rdi], 0
0x18005f066  jnz     loc_18005F1E8
0x18005f06c  lea     rcx, [rbx+8]
0x18005f070  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005f075  mov     rcx, rax
0x18005f078  call    cs:__imp_SensorOpenByInterface
0x18005f07e  mov     rdx, rax
0x18005f081  mov     rcx, rdi
0x18005f084  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SensorClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005f089  mov     qword ptr [rsp+140h+var_100], rbx
0x18005f08e  lea     rax, ?OnAlsHandleReopen@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXU_GUID@@0@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::OnAlsHandleReopen(_GUID,_GUID)
0x18005f095  mov     [rbp+40h+var_38], rax
0x18005f099  mov     [rbp+40h+var_30], 0
0x18005f0a0  mov     eax, dword ptr [rbp+40h+ppropvar+0Ch]
0x18005f0a3  mov     [rbp+40h+var_2C], eax
0x18005f0a6  lea     r10, GUID_SensorType_AmbientLight
0x18005f0ad  mov     qword ptr [rsp+140h+var_120], r10
0x18005f0b2  lea     r8, [rsp+140h+var_100]
0x18005f0b7  lea     rcx, [rbp+40h+var_28]
0x18005f0bb  call    ??$?0U_Exact_args_t@std@@PEAVLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEBU?$_Ph@$00@1@AEBU_GUID@@$0A@@?$tuple@PEAVLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@U?$_Ph@$00@std@@U_GUID@@@std@@QEAA@U_Exact_args_t@1@$$QEAPEAVLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEBU?$_Ph@$00@1@AEBU_GUID@@@Z; std::tuple<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1>,_GUID>::tuple<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1>,_GUID>(std::_Exact_args_t,Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl * &&,std::_Ph<1> const &,_GUID const &)
0x18005f0c0  lea     rcx, ?OnAlsRemoved@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXQEAX_NU_GUID@@@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::OnAlsRemoved(void * const,bool,_GUID)
0x18005f0c7  mov     [rbp+40h+ppropvar], rcx
0x18005f0cb  mov     dword ptr [rbp+40h+ppropvar+8], 0
0x18005f0d2  mov     eax, dword ptr [rbp+40h+ppropvar+0Ch]
0x18005f0d5  mov     dword ptr [rbp+40h+ppropvar+0Ch], eax
0x18005f0d8  mov     qword ptr [rsp+140h+var_120], r10
0x18005f0dd  lea     rcx, [rbp+40h+var_58]
0x18005f0e1  call    ??$?0U_Exact_args_t@std@@AEBU?$_Ph@$00@1@AEBU?$_Ph@$01@1@AEBU_GUID@@$0A@@?$tuple@U?$_Ph@$00@std@@U?$_Ph@$01@2@U_GUID@@@std@@QEAA@U_Exact_args_t@1@AEBU?$_Ph@$00@1@AEBU?$_Ph@$01@1@AEBU_GUID@@@Z; std::tuple<std::_Ph<1>,std::_Ph<2>,_GUID>::tuple<std::_Ph<1>,std::_Ph<2>,_GUID>(std::_Exact_args_t,std::_Ph<1> const &,std::_Ph<2> const &,_GUID const &)
0x18005f0e6  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@EAAXPEAX_NU_GUID@@@ZPEAV34567@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@AEBU8@@std@@XPEAX_N@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::*)(void *,bool,_GUID),Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1> const &,std::_Ph<2> const &,_GUID const &>,void,void *,bool>::`vftable'
0x18005f0ed  mov     [rsp+140h+var_E8], rax
0x18005f0f2  mov     rax, [rbp+40h+ppropvar]
0x18005f0f6  mov     [rsp+140h+var_E0], rax
0x18005f0fb  mov     eax, dword ptr [rbp+40h+ppropvar+8]
0x18005f0fe  mov     dword ptr [rsp+140h+var_D8], eax
0x18005f102  mov     eax, dword ptr [rbp+40h+ppropvar+0Ch]
0x18005f105  mov     dword ptr [rsp+140h+var_D8+4], eax
0x18005f109  mov     rax, [rbp+40h+var_58]
0x18005f10d  mov     [rsp+140h+var_D0], rax
0x18005f112  mov     rax, [rbp+40h+var_50]
0x18005f116  mov     [rsp+140h+var_C8], rax
0x18005f11b  mov     al, [rbp+40h+var_48]
0x18005f11e  mov     [rbp+40h+var_C0], al
0x18005f121  mov     al, [rbp+40h+var_44]
0x18005f124  mov     [rbp+40h+var_BC], al
0x18005f127  mov     [rbp+40h+var_B8], rbx
0x18005f12b  lea     rax, [rsp+140h+var_E8]
0x18005f130  mov     [rbp+40h+var_B0], rax
0x18005f134  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@EAAXU_GUID@@0@ZPEAV34567@AEBU?$_Ph@$00@2@AEBU8@@std@@XU_GUID@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::*)(_GUID,_GUID),Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *,std::_Ph<1> const &,_GUID const &>,void,_GUID>::`vftable'
0x18005f13b  mov     [rbp+40h+var_A8], rax
0x18005f13f  mov     rax, [rbp+40h+var_38]
0x18005f143  mov     [rbp+40h+var_A0], rax
0x18005f147  mov     eax, [rbp+40h+var_30]
0x18005f14a  mov     [rbp+40h+var_98], eax
0x18005f14d  mov     eax, [rbp+40h+var_2C]
0x18005f150  mov     [rbp+40h+var_94], eax
0x18005f153  mov     rax, [rbp+40h+var_28]
0x18005f157  mov     [rbp+40h+var_90], rax
0x18005f15b  mov     rax, [rbp+40h+var_20]
0x18005f15f  mov     [rbp+40h+var_88], rax
0x18005f163  mov     al, [rbp+40h+var_18]
0x18005f166  mov     [rbp+40h+var_80], al
0x18005f169  mov     rax, [rbp+40h+var_10]
0x18005f16d  mov     [rbp+40h+var_78], rax
0x18005f171  lea     rax, [rbp+40h+var_A8]
0x18005f175  mov     [rbp+40h+var_70], rax
0x18005f179  movups  xmm0, xmmword ptr cs:GUID_SensorType_AmbientLight.Data1
0x18005f180  movdqu  [rsp+140h+var_100], xmm0
0x18005f186  lea     rax, [rsp+140h+var_E8]
0x18005f18b  mov     qword ptr [rsp+140h+var_120], rax
0x18005f190  lea     r9, [rbp+40h+var_A8]
0x18005f194  mov     r8, [rdi]
0x18005f197  lea     rdx, [rsp+140h+var_100]
0x18005f19c  lea     rcx, [rbp+40h+ppropvar]
0x18005f1a0  call    ?MakeAndInitialize@PnpDeviceInstance@@SA?AV?$shared_ptr@VPnpDeviceInstance@@@std@@U_GUID@@PEAXV?$function@$$A6AXU_GUID@@@Z@3@V?$function@$$A6AXPEAX_N@Z@3@@Z; PnpDeviceInstance::MakeAndInitialize(_GUID,void *,std::function<void (_GUID)>,std::function<void (void *,bool)>)
0x18005f1a5  mov     rcx, [rax]
0x18005f1a8  mov     rdx, [rax+8]
0x18005f1ac  mov     qword ptr [rax], 0
0x18005f1b3  mov     qword ptr [rax+8], 0
0x18005f1bb  mov     [rbx+0D0h], rcx
0x18005f1c2  mov     rcx, [rbx+0D8h]; this
0x18005f1c9  mov     [rbx+0D8h], rdx
0x18005f1d0  test    rcx, rcx
0x18005f1d3  jz      short loc_18005F1DA
0x18005f1d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f1da  mov     rcx, [rbp+40h+ppropvar+8]; this
0x18005f1de  test    rcx, rcx
0x18005f1e1  jz      short loc_18005F1E8
0x18005f1e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f1e8  mov     byte ptr [rbx+85h], 1
0x18005f1ef  mov     [rsp+140h+var_110], 0
0x18005f1f7  mov     al, [rbx+84h]
0x18005f1fd  neg     al
0x18005f1ff  sbb     rdx, rdx
0x18005f202  lea     rax, [rsp+140h+var_110]
0x18005f207  and     rdx, rax
0x18005f20a  mov     al, [rbx+7Ch]
0x18005f20d  neg     al
0x18005f20f  sbb     rcx, rcx
0x18005f212  lea     rax, [rsp+140h+var_110]
0x18005f217  and     rcx, rax
0x18005f21a  mov     [rsp+140h+var_118], rdx
0x18005f21f  mov     qword ptr [rsp+140h+var_120], rcx; unsigned int
0x18005f224  xor     r9d, r9d
0x18005f227  lea     r8, [rsp+140h+var_110]
0x18005f22c  mov     rdx, [rbx+88h]
0x18005f233  mov     rcx, [rdi]
0x18005f236  call    cs:__imp_SensorSetAlsWithColorThresholds
0x18005f23c  mov     rcx, [rbp+48h]; this
0x18005f240  test    eax, eax
0x18005f242  jz      short loc_18005F259
0x18005f244  mov     r9d, eax; char *
0x18005f247  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18005f24e  mov     edx, 296h; void *
0x18005f253  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005f259  cmp     byte ptr [rbx+74h], 0
0x18005f25d  jz      short loc_18005F296
0x18005f25f  xorps   xmm0, xmm0
0x18005f262  xor     eax, eax
0x18005f264  movups  xmmword ptr [rbp+40h+ppropvar], xmm0
0x18005f268  mov     [rbp+40h+var_58], rax
0x18005f26c  lea     rdx, [rbp+40h+ppropvar]; ppropvar
0x18005f270  movss   xmm0, dword ptr [rbx+70h]; fltVal
0x18005f275  call    cs:__imp_InitPropVariantFromFloat
0x18005f27b  lea     r9, [rbp+40h+ppropvar]; pValue
0x18005f27f  mov     r8b, 1; TypeCheck
0x18005f282  lea     rdx, PKEY_SensorData_LightLevel_Lux_Threshold_AbsoluteDifference; pKey
0x18005f289  mov     rcx, [rbx+88h]; pList
0x18005f290  call    cs:__imp_PropKeyFindKeySetPropVariant
0x18005f296  mov     rax, [rbx+88h]
0x18005f29d  mov     qword ptr [rsp+140h+var_120], rax; unsigned int
0x18005f2a2  mov     r9d, [rbx+68h]
0x18005f2a6  mov     r8, rbx
0x18005f2a9  lea     rdx, ?DataCallbackShim@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@CAXPEAX0@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::DataCallbackShim(void *,void *)
0x18005f2b0  mov     rcx, [rdi]
0x18005f2b3  call    cs:__imp_SensorStartCollection
0x18005f2b9  mov     rcx, [rbp+48h]; this
0x18005f2bd  test    eax, eax
0x18005f2bf  jz      short loc_18005F2D6
0x18005f2c1  mov     r9d, eax; char *
0x18005f2c4  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18005f2cb  mov     edx, 2AAh; void *
0x18005f2d0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005f2d5  nop
0x18005f2d6  lea     rcx, [rsp+140h+var_F0]
0x18005f2db  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005f2e0  mov     rcx, [rbp+40h+var_8]
0x18005f2e4  xor     rcx, rsp; StackCookie
0x18005f2e7  call    __security_check_cookie
0x18005f2ec  lea     r11, [rsp+140h+var_s0]
0x18005f2f4  mov     rbx, [r11+18h]
0x18005f2f8  mov     rdi, [r11+20h]
0x18005f2fc  mov     rsp, r11
0x18005f2ff  pop     rbp
0x18005f300  retn
```
