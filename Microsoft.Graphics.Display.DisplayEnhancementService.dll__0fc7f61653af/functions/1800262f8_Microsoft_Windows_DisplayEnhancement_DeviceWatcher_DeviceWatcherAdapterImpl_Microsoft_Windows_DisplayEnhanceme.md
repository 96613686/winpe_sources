# Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>::RegisterDeviceWatcherCallback(void)

- ea: `0x1800262f8`
- end: `0x1800263a4`
- name: `?RegisterDeviceWatcherCallback@?$DeviceWatcherAdapterImpl@VMonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025284`
- `0x1800253b0`

## callees

- `0x180013138`
- `0x180023b60`
- `0x1800262f8`
- `0x180029080`
- `0x1800298c4`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180026368`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180026368`

## string_xrefs

- `0x18002637a`: `onecoreuap\drivers\mobilepc\DisplayEnhancement\service\common\DeviceWatcherAdapter\lib\DeviceWatcherAdapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl>::RegisterDeviceWatcherCallback(
        __int64 a1)
{
  int ObjectQuery; // eax
  int v4; // [rsp+20h] [rbp-58h]
  _QWORD v5[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapter::GetDeviceFilter(v5);
  wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(
    a1 + 72,
    0);
  v4 = -1227133513 * ((__int64)(v5[1] - v5[0]) >> 3);
  ObjectQuery = DevCreateObjectQuery(1, 1, 0);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\DisplayEnhancement\\service\\common\\DeviceWatcherAdapter\\lib\\Devic"
                    "eWatcherAdapter.cpp",
      (const char *)(unsigned int)ObjectQuery,
      v4);
  return std::vector<_DEVPROP_FILTER_EXPRESSION>::_Tidy(v5);
}

```

## disassembly

```asm
0x1800262f8  mov     [rsp+arg_0], rbx
0x1800262fd  push    rdi
0x1800262fe  sub     rsp, 70h
0x180026302  mov     rdi, rcx
0x180026305  lea     rcx, [rsp+78h+var_28]
0x18002630a  call    ?GetDeviceFilter@MonitorAdapter@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapter::GetDeviceFilter(void)
0x18002630f  nop
0x180026310  lea     rbx, [rdi+48h]
0x180026314  xor     edx, edx
0x180026316  mov     rcx, rbx
0x180026319  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDEVQUERY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(HDEVQUERY__ *)
0x18002631e  mov     rax, [rsp+78h+var_28]
0x180026323  mov     rdx, [rsp+78h+var_20]
0x180026328  sub     rdx, rax
0x18002632b  sar     rdx, 3
0x18002632f  mov     rcx, 6DB6DB6DB6DB6DB7h
0x180026339  imul    rdx, rcx
0x18002633d  mov     [rsp+78h+var_38], rbx
0x180026342  mov     [rsp+78h+var_40], rdi
0x180026347  lea     rcx, ?DevQueryCallbackThunk@?$DeviceWatcherAdapterImpl@VLightSensorAdapter@1DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@KAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter>::DevQueryCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002634e  mov     [rsp+78h+var_48], rcx
0x180026353  mov     [rsp+78h+var_50], rax
0x180026358  mov     [rsp+78h+var_58], edx; int
0x18002635c  xor     r9d, r9d
0x18002635f  xor     r8d, r8d
0x180026362  lea     ecx, [r9+1]
0x180026366  mov     edx, ecx
0x180026368  call    cs:__imp_DevCreateObjectQuery
0x18002636e  mov     rcx, [rsp+78h]; this
0x180026373  test    eax, eax
0x180026375  jns     short loc_18002638C
0x180026377  mov     r9d, eax; char *
0x18002637a  lea     r8, aOnecoreuapDriv_14; "onecoreuap\\drivers\\mobilepc\\DisplayE"...
0x180026381  mov     edx, 29h ; ')'; void *
0x180026386  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002638c  lea     rcx, [rsp+78h+var_28]
0x180026391  call    ?_Tidy@?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@AEAAXXZ; std::vector<_DEVPROP_FILTER_EXPRESSION>::_Tidy(void)
0x180026396  mov     rbx, [rsp+78h+arg_0]
0x18002639e  add     rsp, 70h
0x1800263a2  pop     rdi
0x1800263a3  retn
```
