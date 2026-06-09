# Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter>::RegisterDeviceWatcherCallback(void)

- ea: `0x18004c720`
- end: `0x18004c7cc`
- name: `?RegisterDeviceWatcherCallback@?$DeviceWatcherAdapterImpl@VLightSensorAdapter@1DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b4c4`
- `0x1800d48c0`

## callees

- `0x180013138`
- `0x180029080`
- `0x1800298c4`
- `0x18004a8a0`
- `0x18004c720`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004c790`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004c790`

## string_xrefs

- `0x18004c7a2`: `onecoreuap\drivers\mobilepc\DisplayEnhancement\service\common\DeviceWatcherAdapter\lib\DeviceWatcherAdapter.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter>::RegisterDeviceWatcherCallback(
        __int64 a1)
{
  int ObjectQuery; // eax
  int v4; // [rsp+20h] [rbp-58h]
  _QWORD v5[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter::GetDeviceFilter(v5);
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
0x18004c720  mov     [rsp+arg_0], rbx
0x18004c725  push    rdi
0x18004c726  sub     rsp, 70h
0x18004c72a  mov     rdi, rcx
0x18004c72d  lea     rcx, [rsp+78h+var_28]
0x18004c732  call    ?GetDeviceFilter@LightSensorAdapter@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter::GetDeviceFilter(void)
0x18004c737  nop
0x18004c738  lea     rbx, [rdi+48h]
0x18004c73c  xor     edx, edx
0x18004c73e  mov     rcx, rbx
0x18004c741  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDEVQUERY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(HDEVQUERY__ *)
0x18004c746  mov     rax, [rsp+78h+var_28]
0x18004c74b  mov     rdx, [rsp+78h+var_20]
0x18004c750  sub     rdx, rax
0x18004c753  sar     rdx, 3
0x18004c757  mov     rcx, 6DB6DB6DB6DB6DB7h
0x18004c761  imul    rdx, rcx
0x18004c765  mov     [rsp+78h+var_38], rbx
0x18004c76a  mov     [rsp+78h+var_40], rdi
0x18004c76f  lea     rcx, ?DevQueryCallbackThunk@?$DeviceWatcherAdapterImpl@VLightSensorAdapter@1DisplayEnhancement@Windows@Microsoft@@@DeviceWatcher@DisplayEnhancement@Windows@Microsoft@@KAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Windows::DisplayEnhancement::DeviceWatcher::DeviceWatcherAdapterImpl<Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapter>::DevQueryCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18004c776  mov     [rsp+78h+var_48], rcx
0x18004c77b  mov     [rsp+78h+var_50], rax
0x18004c780  mov     [rsp+78h+var_58], edx; int
0x18004c784  xor     r9d, r9d
0x18004c787  xor     r8d, r8d
0x18004c78a  lea     ecx, [r9+1]
0x18004c78e  mov     edx, ecx
0x18004c790  call    cs:__imp_DevCreateObjectQuery
0x18004c796  mov     rcx, [rsp+78h]; this
0x18004c79b  test    eax, eax
0x18004c79d  jns     short loc_18004C7B4
0x18004c79f  mov     r9d, eax; char *
0x18004c7a2  lea     r8, aOnecoreuapDriv_14; "onecoreuap\\drivers\\mobilepc\\DisplayE"...
0x18004c7a9  mov     edx, 29h ; ')'; void *
0x18004c7ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c7b4  lea     rcx, [rsp+78h+var_28]
0x18004c7b9  call    ?_Tidy@?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@AEAAXXZ; std::vector<_DEVPROP_FILTER_EXPRESSION>::_Tidy(void)
0x18004c7be  mov     rbx, [rsp+78h+arg_0]
0x18004c7c6  add     rsp, 70h
0x18004c7ca  pop     rdi
0x18004c7cb  retn
```
