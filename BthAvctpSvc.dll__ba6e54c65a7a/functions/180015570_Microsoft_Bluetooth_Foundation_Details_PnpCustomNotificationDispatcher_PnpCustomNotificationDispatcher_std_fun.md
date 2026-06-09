# Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::PnpCustomNotificationDispatcher(std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>)

- ea: `0x180015570`
- end: `0x180015611`
- name: `??0PnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@@Z`
- size: `161`
- prototype: `char *__fastcall(char *pv, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001786c`

## callees

- `0x18000dca8`
- `0x18000e16c`
- `0x18001525c`
- `0x180015570`
- `0x18001a028`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800155c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800155c3`

## pseudocode

```c
char *__fastcall Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::PnpCustomNotificationDispatcher(
        char *pv,
        __int64 a2)
{
  PTP_WORK ThreadpoolWork; // rax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)pv = 0;
  pv[8] = 0;
  std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(pv + 16);
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 12) = pv + 88;
  *((_QWORD *)pv + 11) = pv + 88;
  ThreadpoolWork = CreateThreadpoolWork(
                     Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::WorkCallbackThunk,
                     pv,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    pv + 80,
    ThreadpoolWork);
  if ( !*((_QWORD *)pv + 10) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x620,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v5);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(a2);
  return pv;
}

```

## disassembly

```asm
0x180015570  mov     rax, rsp
0x180015573  mov     [rax+18h], rbx
0x180015577  mov     [rax+20h], rsi
0x18001557b  mov     [rax+10h], rdx
0x18001557f  mov     [rax+8], rcx
0x180015583  push    rdi
0x180015584  sub     rsp, 20h
0x180015588  mov     rsi, rdx
0x18001558b  mov     rdi, rcx
0x18001558e  xor     eax, eax
0x180015590  mov     [rcx], rax
0x180015593  mov     [rcx+8], al
0x180015596  add     rcx, 10h
0x18001559a  call    ??0?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@QEAA@$$QEAV01@@Z; std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)> &&)
0x18001559f  nop
0x1800155a0  lea     rbx, [rdi+50h]
0x1800155a4  mov     qword ptr [rbx], 0
0x1800155ab  lea     rax, [rdi+58h]
0x1800155af  mov     [rax+8], rax
0x1800155b3  mov     [rax], rax
0x1800155b6  xor     r8d, r8d; pcbe
0x1800155b9  mov     rdx, rdi; pv
0x1800155bc  lea     rcx, ?WorkCallbackThunk@PnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800155c3  call    cs:__imp_CreateThreadpoolWork
0x1800155c9  mov     rdx, rax
0x1800155cc  mov     rcx, rbx
0x1800155cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800155d4  cmp     qword ptr [rbx], 0
0x1800155d8  setz    al
0x1800155db  mov     rcx, [rsp+28h]; this
0x1800155e0  test    al, al
0x1800155e2  jnz     short loc_1800155FF
0x1800155e4  mov     rcx, rsi
0x1800155e7  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x1800155ec  mov     rax, rdi
0x1800155ef  mov     rbx, [rsp+28h+arg_10]
0x1800155f4  mov     rsi, [rsp+28h+arg_18]
0x1800155f9  add     rsp, 20h
0x1800155fd  pop     rdi
0x1800155fe  retn
0x1800155ff  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x180015606  mov     edx, 620h; void *
0x18001560b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
