# Microsoft::Bluetooth::Foundation::DeviceRetriever::GetDeviceInterfacePaths(_GUID const &)

- ea: `0x1800412d8`
- end: `0x1800414b5`
- name: `?GetDeviceInterfacePaths@DeviceRetriever@Foundation@Bluetooth@Microsoft@@SA?AV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBU_GUID@@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043d98`

## callees

- `0x180001dd0`
- `0x18000994c`
- `0x18000a91c`
- `0x18000e0c0`
- `0x18000e1cc`
- `0x180015afc`
- `0x18003f5e4`
- `0x1800412d8`
- `0x180044eb8`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004141a`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004141a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall Microsoft::Bluetooth::Foundation::DeviceRetriever::GetDeviceInterfacePaths(__int64 *a1)
{
  _QWORD *v2; // rax
  int ObjectQuery; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // rdx
  char v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  wil *v13; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+68h] [rbp-98h] BYREF
  __int128 v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+90h] [rbp-70h]
  DEVPROPKEY v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+ACh] [rbp-54h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  int v20; // [rsp+B8h] [rbp-48h]
  int v21; // [rsp+BCh] [rbp-44h]
  GUID *v22; // [rsp+C0h] [rbp-40h]
  int v23; // [rsp+C8h] [rbp-38h]
  DEVPROPKEY v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+E4h] [rbp-1Ch]
  __int64 v26; // [rsp+E8h] [rbp-18h]
  int v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+F4h] [rbp-Ch]
  char *v29; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  v10 = -1;
  v16 = 2;
  v17 = DEVPKEY_DeviceInterface_ClassGuid;
  v18 = 0;
  v19 = 0;
  v20 = 13;
  v21 = 16;
  v22 = &GUID_BTHPORT_DEVICE_INTERFACE;
  v23 = 2;
  v24 = DEVPKEY_DeviceInterface_Enabled;
  v25 = 0;
  v26 = 0;
  v27 = 17;
  v28 = 1;
  v29 = &v10;
  v12 = 0;
  v11 = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    &v13,
    &v11);
  v14 = 0;
  std::list<std::wstring>::_Alloc_sentinel_and_proxy(&v14);
  v15 = 0;
  v2 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
  *v2 = v2;
  v2[1] = v2;
  *(_QWORD *)&v15 = v2;
  ObjectQuery = DevCreateObjectQuery(1, 1, 0);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"OneCore\\private\\Drivers\\inc\\bluetooth\\foundation\\DeviceInterfaceObserver.h",
      (const char *)(unsigned int)ObjectQuery,
      2);
  wil::handle_wait(v13, v4, v5, v6);
  *a1 = 0;
  a1[1] = 0;
  std::list<std::wstring>::_Alloc_sentinel_and_proxy(a1);
  v7 = *a1;
  *a1 = v14;
  *(_QWORD *)&v14 = v7;
  v8 = a1[1];
  a1[1] = *((_QWORD *)&v14 + 1);
  *((_QWORD *)&v14 + 1) = v8;
  Microsoft::Bluetooth::Foundation::DeviceRetriever::DeviceEnumerationInterfaceContext::~DeviceEnumerationInterfaceContext((Microsoft::Bluetooth::Foundation::DeviceRetriever::DeviceEnumerationInterfaceContext *)&v13);
  wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>(&v12);
  return a1;
}

```

## disassembly

```asm
0x1800412d8  mov     [rsp-8+arg_8], rbx
0x1800412dd  push    rbp
0x1800412de  lea     rbp, [rsp-10h]
0x1800412e3  sub     rsp, 110h
0x1800412ea  mov     rax, cs:__security_cookie
0x1800412f1  xor     rax, rsp
0x1800412f4  mov     [rbp+10h+var_10], rax
0x1800412f8  mov     rbx, rcx
0x1800412fb  mov     [rsp+110h+var_B8], rcx
0x180041300  mov     [rsp+110h+var_C0], 0FFh
0x180041305  mov     [rbp+10h+var_80], 2
0x18004130c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180041313  movups  [rbp+10h+var_78], xmm0
0x180041317  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18004131d  mov     [rbp+10h+var_68], eax
0x180041320  mov     [rbp+10h+var_64], 0
0x180041327  mov     [rbp+10h+var_60], 0
0x18004132f  mov     [rbp+10h+var_58], 0Dh
0x180041336  mov     [rbp+10h+var_54], 10h
0x18004133d  lea     rax, GUID_BTHPORT_DEVICE_INTERFACE
0x180041344  mov     [rbp+10h+var_50], rax
0x180041348  mov     [rbp+10h+var_48], 2
0x18004134f  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180041356  movaps  [rbp+10h+var_40], xmm0
0x18004135a  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180041360  mov     [rbp+10h+var_30], eax
0x180041363  mov     [rbp+10h+var_2C], 0
0x18004136a  mov     [rbp+10h+var_28], 0
0x180041372  mov     [rbp+10h+var_20], 11h
0x180041379  mov     [rbp+10h+var_1C], 1
0x180041380  lea     rax, [rsp+110h+var_C0]
0x180041385  mov     [rbp+10h+var_18], rax
0x180041389  mov     [rsp+110h+var_B8], 0
0x180041392  mov     [rsp+110h+var_BC], 1
0x18004139a  lea     rdx, [rsp+110h+var_BC]
0x18004139f  lea     rcx, [rsp+110h+var_B0]
0x1800413a4  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800413a9  nop
0x1800413aa  xorps   xmm0, xmm0
0x1800413ad  movdqu  [rsp+110h+var_A8], xmm0
0x1800413b3  lea     rcx, [rsp+110h+var_A8]
0x1800413b8  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x1800413bd  nop
0x1800413be  xorps   xmm0, xmm0
0x1800413c1  movdqu  [rsp+110h+var_98], xmm0
0x1800413c7  mov     ecx, 20h ; ' '
0x1800413cc  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800413d1  mov     [rax], rax
0x1800413d4  mov     [rax+8], rax
0x1800413d8  mov     qword ptr [rsp+110h+var_98], rax
0x1800413dd  lea     rax, [rsp+110h+var_B8]
0x1800413e2  mov     [rsp+110h+var_D0], rax
0x1800413e7  lea     rax, [rsp+110h+var_B0]
0x1800413ec  mov     [rsp+110h+var_D8], rax
0x1800413f1  lea     rax, ?s_GetDeviceInterfacePathsCallback@DeviceRetriever@Foundation@Bluetooth@Microsoft@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Bluetooth::Foundation::DeviceRetriever::s_GetDeviceInterfacePathsCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800413f8  mov     [rsp+110h+var_E0], rax
0x1800413fd  lea     rax, [rbp+10h+var_80]
0x180041401  mov     [rsp+110h+var_E8], rax
0x180041406  mov     [rsp+110h+var_F0], 2; int
0x18004140e  xor     r9d, r9d
0x180041411  xor     r8d, r8d
0x180041414  lea     edx, [r9+1]
0x180041418  mov     ecx, edx
0x18004141a  call    cs:__imp_DevCreateObjectQuery
0x180041420  mov     rcx, [rbp+18h]; this
0x180041424  test    eax, eax
0x180041426  js      short loc_1800414A0
0x180041428  mov     rcx, [rsp+110h+var_B0]; this
0x18004142d  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180041432  mov     qword ptr [rbx], 0
0x180041439  mov     qword ptr [rbx+8], 0
0x180041441  mov     rcx, rbx
0x180041444  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x180041449  mov     rdx, [rbx]
0x18004144c  mov     rcx, qword ptr [rsp+110h+var_A8]
0x180041451  mov     [rbx], rcx
0x180041454  mov     qword ptr [rsp+110h+var_A8], rdx
0x180041459  mov     rdx, [rbx+8]
0x18004145d  mov     rcx, qword ptr [rsp+110h+var_A8+8]
0x180041462  mov     [rbx+8], rcx
0x180041466  mov     qword ptr [rsp+110h+var_A8+8], rdx
0x18004146b  lea     rcx, [rsp+110h+var_B0]; this
0x180041470  call    ??1DeviceEnumerationInterfaceContext@DeviceRetriever@Foundation@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Foundation::DeviceRetriever::DeviceEnumerationInterfaceContext::~DeviceEnumerationInterfaceContext(void)
0x180041475  nop
0x180041476  lea     rcx, [rsp+110h+var_B8]
0x18004147b  call    ??1?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>(void)
0x180041480  mov     rax, rbx
0x180041483  mov     rcx, [rbp+10h+var_10]
0x180041487  xor     rcx, rsp; StackCookie
0x18004148a  call    __security_check_cookie
0x18004148f  mov     rbx, [rsp+110h+arg_8]
0x180041497  add     rsp, 110h
0x18004149e  pop     rbp
0x18004149f  retn
0x1800414a0  mov     r9d, eax; char *
0x1800414a3  lea     r8, aOnecorePrivate_3; "OneCore\\private\\Drivers\\inc\\bluetoo"...
0x1800414aa  mov     edx, 0C6h; void *
0x1800414af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
