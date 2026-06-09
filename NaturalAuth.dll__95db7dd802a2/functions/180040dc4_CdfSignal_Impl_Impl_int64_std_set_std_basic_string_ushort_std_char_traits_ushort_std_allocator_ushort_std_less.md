# CdfSignal::Impl::Impl(__int64,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,ulong)

- ea: `0x180040dc4`
- end: `0x180040e98`
- name: `??0Impl@CdfSignal@@QEAA@_JAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@K@Z`
- size: `212`
- prototype: `char *__fastcall(char *pv, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004101c`

## callees

- `0x18002cc48`
- `0x1800317e8`
- `0x180033134`
- `0x1800376b8`
- `0x180040a74`
- `0x180040da0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040e7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180040e7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040e4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040e4a`

## pseudocode

```c
char *__fastcall CdfSignal::Impl::Impl(char *pv, __int64 a2, __int64 a3, int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp+10h] BYREF

  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(
    pv,
    a3);
  *((_QWORD *)pv + 2) = 0;
  *((_QWORD *)pv + 3) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,enum _CDF_PRESENCE_STATE,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum _CDF_PRESENCE_STATE>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)pv + 4) = 0;
  *((_QWORD *)pv + 5) = 0;
  std::list<GenericPlugin::DefaultSignal::CallbackInfo>::_Alloc_sentinel_and_proxy();
  std::atomic<enum NA_RULE_STATE>::atomic<enum NA_RULE_STATE>(pv + 48);
  *((_QWORD *)pv + 7) = a2;
  std::atomic<bool>::atomic<bool>(pv + 64);
  *((_QWORD *)pv + 9) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(CdfSignal::Impl::InitializationTimerCallback, pv, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    pv + 72,
    ThreadpoolTimer);
  pftDueTime = (struct _FILETIME)-(__int64)(unsigned int)(10000 * a4);
  SetThreadpoolTimer(*((PTP_TIMER *)pv + 9), &pftDueTime, 0, 0);
  return pv;
}

```

## disassembly

```asm
0x180040dc4  mov     [rsp+arg_10], rbx
0x180040dc9  mov     [rsp+arg_18], rsi
0x180040dce  mov     [rsp+arg_0], rcx
0x180040dd3  push    rdi
0x180040dd4  sub     rsp, 30h
0x180040dd8  mov     edi, r9d
0x180040ddb  mov     rbx, rdx
0x180040dde  mov     rsi, rcx
0x180040de1  mov     rdx, r8
0x180040de4  call    ??$?0V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>> const &,std::allocator<std::_Tree_node<std::wstring,void *>> &&)
0x180040de9  nop
0x180040dea  lea     rcx, [rsi+10h]
0x180040dee  mov     qword ptr [rcx], 0
0x180040df5  mov     qword ptr [rcx+8], 0
0x180040dfd  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4_CDF_PRESENCE_STATE@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4_CDF_PRESENCE_STATE@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,_CDF_PRESENCE_STATE,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_CDF_PRESENCE_STATE>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180040e02  nop
0x180040e03  lea     rcx, [rsi+20h]
0x180040e07  mov     qword ptr [rcx], 0
0x180040e0e  mov     qword ptr [rcx+8], 0
0x180040e16  call    ?_Alloc_sentinel_and_proxy@?$list@UCallbackInfo@DefaultSignal@GenericPlugin@@V?$allocator@UCallbackInfo@DefaultSignal@GenericPlugin@@@std@@@std@@AEAAXXZ; std::list<GenericPlugin::DefaultSignal::CallbackInfo>::_Alloc_sentinel_and_proxy(void)
0x180040e1b  nop
0x180040e1c  lea     rcx, [rsi+30h]
0x180040e20  call    ??0?$atomic@W4NA_RULE_STATE@@@std@@QEAA@W4NA_RULE_STATE@@@Z; std::atomic<NA_RULE_STATE>::atomic<NA_RULE_STATE>(NA_RULE_STATE)
0x180040e25  mov     [rsi+38h], rbx
0x180040e29  lea     rcx, [rsi+40h]
0x180040e2d  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x180040e32  lea     rbx, [rsi+48h]
0x180040e36  mov     qword ptr [rbx], 0
0x180040e3d  xor     r8d, r8d; pcbe
0x180040e40  mov     rdx, rsi; pv
0x180040e43  lea     rcx, ?InitializationTimerCallback@Impl@CdfSignal@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180040e4a  call    cs:__imp_CreateThreadpoolTimer
0x180040e50  mov     rdx, rax
0x180040e53  mov     rcx, rbx
0x180040e56  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180040e5b  imul    eax, edi, 2710h
0x180040e61  neg     rax
0x180040e64  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x180040e68  shr     rax, 20h
0x180040e6c  mov     [rsp+38h+pftDueTime.dwHighDateTime], eax
0x180040e70  xor     r9d, r9d; msWindowLength
0x180040e73  xor     r8d, r8d; msPeriod
0x180040e76  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180040e7b  mov     rcx, [rbx]; pti
0x180040e7e  call    cs:__imp_SetThreadpoolTimer
0x180040e84  nop
0x180040e85  mov     rax, rsi
0x180040e88  mov     rbx, [rsp+38h+arg_10]
0x180040e8d  mov     rsi, [rsp+38h+arg_18]
0x180040e92  add     rsp, 30h
0x180040e96  pop     rdi
0x180040e97  retn
```
