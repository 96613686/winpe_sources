# Microsoft::Bluetooth::Foundation::AsyncDeviceWatcher::StartQuery(_DEV_OBJECT_TYPE,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEV_QUERY_PARAMETER const *,ulong,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceWatcher::AsyncDeviceWatcherQuery>)

- ea: `0x180018a28`
- end: `0x180018b3c`
- name: `?StartQuery@AsyncDeviceWatcher@Foundation@Bluetooth@Microsoft@@AEAAXW4_DEV_OBJECT_TYPE@@PEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEVPROPCOMPKEY@@KPEBU_DEV_QUERY_PARAMETER@@KP6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@ZV?$shared_ptr@VAsyncDeviceWatcherQuery@AsyncDeviceWatcher@Foundation@Bluetooth@Microsoft@@@std@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c70`
- `0x180012dc8`
- `0x180050248`
- `0x1800503b0`
- `0x1800504fc`
- `0x180050648`
- `0x180050758`
- `0x180050810`

## callees

- `0x18000de78`
- `0x18000e0c0`
- `0x180018a28`
- `0x180019f2c`
- `0x18001a094`

## import_xrefs

- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180018aa5`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180018aa5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Foundation::AsyncDeviceWatcher::StartQuery(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 *a10)
{
  int ObjectQuery; // eax
  __int64 v13; // rbx
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rcx
  _BYTE v19[8]; // [rsp+60h] [rbp-28h] BYREF
  std::_Ref_count_base *v20; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(
    a1,
    0);
  ObjectQuery = DevCreateObjectQueryEx(a2, 9, a6, a5);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\AsyncDeviceWatcher.h",
      (const char *)(unsigned int)ObjectQuery,
      a4);
  v13 = *a10;
  v14 = (__int64 *)std::enable_shared_from_this<Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider>::shared_from_this(
                     *a10 + 32,
                     v19);
  v15 = *v14;
  v16 = v14[1];
  *v14 = 0;
  v14[1] = 0;
  *(_QWORD *)(v13 + 48) = v15;
  v17 = *(std::_Ref_count_base **)(v13 + 56);
  *(_QWORD *)(v13 + 56) = v16;
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  v18 = (std::_Ref_count_base *)a10[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x180018a28  mov     [rsp+arg_8], rbx
0x180018a2d  mov     [rsp+arg_10], rbp
0x180018a32  push    rsi
0x180018a33  push    rdi
0x180018a34  push    r14
0x180018a36  sub     rsp, 70h
0x180018a3a  mov     esi, r9d
0x180018a3d  mov     rdi, r8
0x180018a40  mov     ebp, edx
0x180018a42  mov     rbx, rcx
0x180018a45  xor     edx, edx
0x180018a47  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDEVQUERY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(HDEVQUERY__ *)
0x180018a4c  mov     [rsp+88h+var_38], rbx
0x180018a51  mov     r14, [rsp+88h+arg_48]
0x180018a59  mov     rax, [r14]
0x180018a5c  mov     [rsp+88h+var_40], rax
0x180018a61  lea     rax, ?s_QueryResultCallback@AsyncDeviceWatcherQuery@AsyncDeviceWatcher@Foundation@Bluetooth@Microsoft@@SAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Bluetooth::Foundation::AsyncDeviceWatcher::AsyncDeviceWatcherQuery::s_QueryResultCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180018a68  mov     [rsp+88h+var_48], rax
0x180018a6d  mov     rax, [rsp+88h+arg_30]
0x180018a75  mov     [rsp+88h+var_50], rax
0x180018a7a  mov     eax, [rsp+88h+arg_38]
0x180018a81  mov     [rsp+88h+var_58], eax
0x180018a85  mov     [rsp+88h+var_60], rdi
0x180018a8a  mov     [rsp+88h+var_68], esi; int
0x180018a8e  mov     r9, [rsp+88h+arg_20]
0x180018a96  mov     r8d, [rsp+88h+arg_28]
0x180018a9e  mov     edx, 9
0x180018aa3  mov     ecx, ebp
0x180018aa5  call    cs:__imp_DevCreateObjectQueryEx
0x180018aab  mov     rcx, [rsp+88h]; this
0x180018ab3  test    eax, eax
0x180018ab5  jns     short loc_180018ACC
0x180018ab7  mov     r9d, eax; char *
0x180018aba  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\bluetooth\\foundation"...
0x180018ac1  mov     edx, 232h; void *
0x180018ac6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018acc  mov     rbx, [r14]
0x180018acf  lea     rcx, [rbx+20h]
0x180018ad3  lea     rdx, [rsp+88h+var_28]
0x180018ad8  call    ?shared_from_this@?$enable_shared_from_this@VAvctpChannelProvider@Avctp@Protocols@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAvctpChannelProvider@Avctp@Protocols@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Protocols::Avctp::AvctpChannelProvider>::shared_from_this(void)
0x180018add  mov     rcx, [rax]
0x180018ae0  mov     rdx, [rax+8]
0x180018ae4  mov     qword ptr [rax], 0
0x180018aeb  mov     qword ptr [rax+8], 0
0x180018af3  mov     [rbx+30h], rcx
0x180018af7  mov     rcx, [rbx+38h]; this
0x180018afb  mov     [rbx+38h], rdx
0x180018aff  test    rcx, rcx
0x180018b02  jz      short loc_180018B09
0x180018b04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b09  mov     rcx, [rsp+88h+var_20]; this
0x180018b0e  test    rcx, rcx
0x180018b11  jz      short loc_180018B19
0x180018b13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b18  nop
0x180018b19  mov     rcx, [r14+8]; this
0x180018b1d  test    rcx, rcx
0x180018b20  jz      short loc_180018B27
0x180018b22  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018b27  lea     r11, [rsp+88h+var_18]
0x180018b2c  mov     rbx, [r11+28h]
0x180018b30  mov     rbp, [r11+30h]
0x180018b34  mov     rsp, r11
0x180018b37  pop     r14
0x180018b39  pop     rdi
0x180018b3a  pop     rsi
0x180018b3b  retn
```
