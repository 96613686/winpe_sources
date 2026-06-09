# Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::PrepareInternal(wil::basic_zstring_view<ushort>,void *,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Event)>,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>,Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::MonitorInterfaceRemovals)

- ea: `0x18001786c`
- end: `0x180017a04`
- name: `?PrepareInternal@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@AEAAXV?$basic_zstring_view@G@wil@@PEAXV?$function@$$A6AXW4Event@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@@Z@std@@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@8@W4MonitorInterfaceRemovals@1234@@Z`
- size: `408`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800177d0`
- `0x18001e034`

## callees

- `0x18000dca8`
- `0x18000e058`
- `0x18000e0c0`
- `0x18000e16c`
- `0x180012f50`
- `0x18001525c`
- `0x180015570`
- `0x18001786c`
- `0x180018d90`
- `0x180019eb4`
- `0x18001a028`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017949`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017949`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::PrepareInternal(
        char *pv,
        __int128 *a2,
        __int64 a3,
        char *a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v11; // rax
  PTP_WORK ThreadpoolWork; // rax
  const char *v13; // r9
  __int64 v14; // rax
  int v16; // [rsp+20h] [rbp-A8h]
  __int128 v17; // [rsp+30h] [rbp-98h] BYREF
  char *v18; // [rsp+40h] [rbp-88h]
  char v19; // [rsp+48h] [rbp-80h]
  _BYTE v20[120]; // [rsp+50h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( !*((_QWORD *)a4 + 7) && !*(_QWORD *)(a5 + 56) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x856,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      (const char *)0x80070057LL,
      v16);
  Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Stop((Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor *)pv);
  v18 = pv;
  v19 = 1;
  if ( *(_QWORD *)(a5 + 56) )
  {
    std::_Optional_destruct_base<Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher,0>::reset(pv + 120);
    v11 = std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(v20);
    Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::PnpCustomNotificationDispatcher(
      pv + 120,
      v11);
    pv[224] = 1;
  }
  if ( a6 == 1 )
    std::wstring::_Assign<unsigned short>(pv + 16);
  if ( *((_QWORD *)a4 + 7) )
  {
    if ( pv + 56 != a4 )
    {
      std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(pv + 56);
      std::_Func_class<void,>::_Reset_move(pv + 56, a4);
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::StateChangeWorkerCallbackThunk,
                       pv,
                       0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      pv + 256,
      ThreadpoolWork);
    if ( !*((_QWORD *)pv + 32) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x871,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
        v13);
  }
  v14 = *(_QWORD *)pv;
  v17 = *a2;
  if ( a3 == -1 )
    (*(void (__fastcall **)(char *, __int128 *, _QWORD))(v14 + 8))(pv, &v17, a6);
  else
    (*(void (__fastcall **)(char *, __int128 *, __int64, _QWORD))(v14 + 16))(pv, &v17, a3, a6);
  *((_QWORD *)pv + 31) = 0;
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(a4);
  return std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(a5);
}

```

## disassembly

```asm
0x18001786c  mov     rax, rsp
0x18001786f  mov     [rax+20h], r9
0x180017873  push    rbx
0x180017874  push    rbp
0x180017875  push    rsi
0x180017876  push    rdi
0x180017877  push    r12
0x180017879  push    r15
0x18001787b  sub     rsp, 98h
0x180017882  mov     rsi, r9
0x180017885  mov     r12, r8
0x180017888  mov     r15, rdx
0x18001788b  mov     rdi, rcx
0x18001788e  mov     rbp, [rax+28h]
0x180017892  cmp     qword ptr [r9+38h], 0
0x180017897  jnz     short loc_1800178A4
0x180017899  cmp     qword ptr [rbp+38h], 0
0x18001789e  jnz     short loc_1800178A4
0x1800178a0  mov     al, 1
0x1800178a2  jmp     short loc_1800178A6
0x1800178a4  xor     al, al
0x1800178a6  mov     rcx, [rsp+0C8h]; this
0x1800178ae  test    al, al
0x1800178b0  jnz     loc_1800179EC
0x1800178b6  mov     rcx, rdi; this
0x1800178b9  call    ?Stop@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::Stop(void)
0x1800178be  mov     [rsp+0C8h+var_88], rdi
0x1800178c3  mov     [rsp+0C8h+var_80], 1
0x1800178c8  cmp     qword ptr [rbp+38h], 0
0x1800178cd  jz      short loc_1800178F8
0x1800178cf  lea     rcx, [rdi+78h]
0x1800178d3  call    ?reset@?$_Optional_destruct_base@VPnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher,0>::reset(void)
0x1800178d8  mov     rdx, rbp
0x1800178db  lea     rcx, [rsp+0C8h+var_78]
0x1800178e0  call    ??0?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@QEAA@$$QEAV01@@Z; std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>(std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)> &&)
0x1800178e5  mov     rdx, rax
0x1800178e8  lea     rcx, [rdi+78h]; pv
0x1800178ec  call    ??0PnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@@Z; Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::PnpCustomNotificationDispatcher(std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>)
0x1800178f1  mov     byte ptr [rdi+0E0h], 1
0x1800178f8  cmp     [rsp+0C8h+arg_28], 1
0x180017900  jnz     short loc_180017912
0x180017902  lea     rcx, [rdi+10h]
0x180017906  mov     r8, [r15+8]
0x18001790a  mov     rdx, [r15]
0x18001790d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180017912  cmp     qword ptr [rsi+38h], 0
0x180017917  jz      short loc_18001796D
0x180017919  lea     rbx, [rdi+38h]
0x18001791d  cmp     rbx, rsi
0x180017920  jz      short loc_180017935
0x180017922  mov     rcx, rbx
0x180017925  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x18001792a  mov     rdx, rsi
0x18001792d  mov     rcx, rbx
0x180017930  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x180017935  lea     rbx, [rdi+100h]
0x18001793c  xor     r8d, r8d; pcbe
0x18001793f  mov     rdx, rdi; pv
0x180017942  lea     rcx, ?StateChangeWorkerCallbackThunk@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180017949  call    cs:__imp_CreateThreadpoolWork
0x18001794f  mov     rdx, rax
0x180017952  mov     rcx, rbx
0x180017955  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001795a  cmp     qword ptr [rbx], 0
0x18001795e  setz    al
0x180017961  mov     rcx, [rsp+0C8h]; this
0x180017969  test    al, al
0x18001796b  jnz     short loc_1800179DA
0x18001796d  mov     rax, [rdi]
0x180017970  movaps  xmm0, xmmword ptr [r15]
0x180017974  lea     rdx, [rsp+0C8h+var_98]
0x180017979  mov     rcx, rdi
0x18001797c  movdqa  [rsp+0C8h+var_98], xmm0
0x180017982  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180017986  jnz     short loc_18001799B
0x180017988  mov     r8d, [rsp+0C8h+arg_28]
0x180017990  mov     rax, [rax+8]
0x180017994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017999  jmp     short loc_1800179AF
0x18001799b  mov     r9d, [rsp+0C8h+arg_28]
0x1800179a3  mov     r8, r12
0x1800179a6  mov     rax, [rax+10h]
0x1800179aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179af  mov     qword ptr [rdi+0F8h], 0
0x1800179ba  mov     rcx, rsi
0x1800179bd  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x1800179c2  nop
0x1800179c3  mov     rcx, rbp
0x1800179c6  add     rsp, 98h
0x1800179cd  pop     r15
0x1800179cf  pop     r12
0x1800179d1  pop     rdi
0x1800179d2  pop     rsi
0x1800179d3  pop     rbp
0x1800179d4  pop     rbx
0x1800179d5  jmp     ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x1800179da  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x1800179e1  mov     edx, 871h; void *
0x1800179e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800179ec  mov     r9d, 80070057h; char *
0x1800179f2  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x1800179f9  mov     edx, 856h; void *
0x1800179fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
