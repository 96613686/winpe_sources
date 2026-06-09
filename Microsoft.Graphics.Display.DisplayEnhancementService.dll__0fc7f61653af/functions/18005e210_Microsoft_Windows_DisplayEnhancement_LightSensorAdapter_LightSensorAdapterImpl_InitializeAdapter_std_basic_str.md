# Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeAdapter(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005e210`
- end: `0x18005e32f`
- name: `?InitializeAdapter@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(char)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011704`
- `0x180013578`
- `0x18001ff40`
- `0x18005e210`
- `0x18005e338`
- `0x18005e418`
- `0x18005e704`
- `0x18005f4f4`
- `0x18005f9b0`
- `0x18009830c`

## import_xrefs

- `SensorsNativeApi!SensorOpenByInterface` at `0x18005e246`
- `SensorsNativeApi!SensorOpenByInterface` at `0x18005e246`

## string_xrefs

- `0x18005e267`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`
- `0x18005e31a`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeAdapter(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-58h]
  const char *v10; // [rsp+28h] [rbp-50h]
  _QWORD v11[6]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+62h] [rbp-16h]
  __int16 v14; // [rsp+66h] [rbp-12h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  std::wstring::operator=(a1 + 8);
  Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeEnumerationProperties(a1);
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v4, v5);
  v7 = SensorOpenByInterface(v6);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a1 + 200,
    v7);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
    (const char *)(*(_QWORD *)(a1 + 200) == 0),
    (bool)"Sensor handle was nullptr",
    v10);
  Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeThresholdCollectionList((Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *)a1);
  Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeDataCollectionList((Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl *)a1);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a1 + 200,
    0);
  v13 = 0;
  v14 = 0;
  v11[1] = a1 + 40;
  v11[0] = &Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::c_specification;
  v12 = 257;
  v11[2] = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogMachineExceptionThunk;
  v11[3] = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogEventEnqueueThunk;
  v11[4] = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogTransitionThunk;
  v11[5] = Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtMachineDestroyedThunk;
  result = SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(
             (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v11,
             (struct SmFx::StateMachineEngine::StateMachineEngineImpl **)(a1 + 40));
  if ( (int)result < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
      (const char *)(unsigned int)result,
      v9);
  return result;
}

```

## disassembly

```asm
0x18005e210  mov     [rsp+arg_0], rbx
0x18005e215  push    rdi
0x18005e216  sub     rsp, 70h
0x18005e21a  mov     rdi, rcx
0x18005e21d  mov     rbx, rdx
0x18005e220  add     rcx, 8
0x18005e224  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005e229  mov     rdx, rbx
0x18005e22c  mov     rcx, rdi; char
0x18005e22f  call    ?InitializeEnumerationProperties@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeEnumerationProperties(std::wstring const &)
0x18005e234  mov     rcx, rbx
0x18005e237  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005e23c  mov     rcx, rax
0x18005e23f  lea     rbx, [rdi+0C8h]
0x18005e246  call    cs:__imp_SensorOpenByInterface
0x18005e24c  mov     rdx, rax
0x18005e24f  mov     rcx, rbx
0x18005e252  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SensorClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005e257  cmp     qword ptr [rbx], 0
0x18005e25b  lea     rdx, aSensorHandleWa; "Sensor handle was nullptr"
0x18005e262  mov     rcx, [rsp+78h]; this
0x18005e267  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18005e26e  setz    al
0x18005e271  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18005e276  movzx   r9d, al; char *
0x18005e27a  mov     edx, 90h; void *
0x18005e27f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18005e284  mov     rcx, rdi; this
0x18005e287  call    ?InitializeThresholdCollectionList@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeThresholdCollectionList(void)
0x18005e28c  mov     rcx, rdi; this
0x18005e28f  call    ?InitializeDataCollectionList@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::InitializeDataCollectionList(void)
0x18005e294  xor     edx, edx
0x18005e296  mov     rcx, rbx
0x18005e299  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SensorClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SensorClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005e29e  xor     eax, eax
0x18005e2a0  mov     [rsp+78h+var_16], 0
0x18005e2a8  mov     [rsp+78h+var_12], ax
0x18005e2ad  lea     rdx, [rdi+28h]; struct SmFx::StateMachineEngine::StateMachineEngineImpl **
0x18005e2b1  lea     rax, ?c_specification@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::c_specification
0x18005e2b8  mov     [rsp+78h+var_40], rdx
0x18005e2bd  mov     [rsp+78h+var_48], rax
0x18005e2c2  lea     rcx, [rsp+78h+var_48]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x18005e2c7  lea     rax, ?EvtLogMachineExceptionThunk@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4MachineException@SmFx@@GG@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogMachineExceptionThunk(void *,SmFx::MachineException,ushort,ushort)
0x18005e2ce  mov     [rsp+78h+var_18], 101h
0x18005e2d5  mov     [rsp+78h+var_38], rax
0x18005e2da  lea     rax, ?EvtLogEventEnqueueThunk@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@CAXPEAXG@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogEventEnqueueThunk(void *,ushort)
0x18005e2e1  mov     [rsp+78h+var_30], rax
0x18005e2e6  lea     rax, ?EvtLogTransitionThunk@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4TransitionType@SmFx@@GGG@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtLogTransitionThunk(void *,SmFx::TransitionType,ushort,ushort,ushort)
0x18005e2ed  mov     [rsp+78h+var_28], rax
0x18005e2f2  lea     rax, ?EvtMachineDestroyedThunk@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@CAXPEAX@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::GeneratedStateMachines::SensorAdapterStateMachine<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl>::EvtMachineDestroyedThunk(void *)
0x18005e2f9  mov     [rsp+78h+var_20], rax
0x18005e2fe  call    ?MakeAndInitialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@SAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@PEAPEAV123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &,SmFx::StateMachineEngine::StateMachineEngineImpl * *)
0x18005e303  test    eax, eax
0x18005e305  js      short loc_18005E315
0x18005e307  mov     rbx, [rsp+78h+arg_0]
0x18005e30f  add     rsp, 70h
0x18005e313  pop     rdi
0x18005e314  retn
0x18005e315  mov     rcx, [rsp+78h]; this
0x18005e31a  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18005e321  mov     r9d, eax; char *
0x18005e324  mov     edx, 99h; void *
0x18005e329  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
