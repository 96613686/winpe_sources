# JobScheduler::WorkContext::Initialize(std::shared_ptr<JobScheduler>,_TP_CALLBACK_PRIORITY)

- ea: `0x18001184c`
- end: `0x1800119c4`
- name: `?Initialize@WorkContext@JobScheduler@@QEAAXV?$shared_ptr@VJobScheduler@@@std@@W4_TP_CALLBACK_PRIORITY@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180011a00`

## callees

- `0x18000fa44`
- `0x18000fa64`
- `0x18000fa88`
- `0x18000fa98`
- `0x18000fb30`
- `0x18001184c`
- `0x18001370c`
- `0x18001af70`
- `0x180022070`
- `0x18002a900`
- `0x18002b92c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800118e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800118e3`

## string_xrefs

- `0x180011904`: `onecoreuap\base\devices\setup\dsm\service\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall JobScheduler::WorkContext::Initialize(char *pv, _QWORD *a2, int a3)
{
  PTP_WORK ThreadpoolWork; // rax
  const char *v6; // r9
  _QWORD *v7; // rax
  std::_Ref_count_base *v8; // rcx
  _BYTE v9[8]; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v10[120]; // [rsp+30h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *(_DWORD *)pv = a3;
  *((_DWORD *)pv + 2) = 3;
  *((_QWORD *)pv + 2) = 0;
  *((_QWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 4) = 0;
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 6) = 0;
  *((_QWORD *)pv + 7) = 0;
  *((_DWORD *)pv + 16) = 0;
  *((_DWORD *)pv + 18) = 72;
  *((_DWORD *)pv + 17) = *(_DWORD *)pv;
  *((_QWORD *)pv + 2) = *(_QWORD *)(*a2 + 16LL);
  ThreadpoolWork = CreateThreadpoolWork(JobScheduler::_RunJobCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 8));
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    pv + 80,
    ThreadpoolWork);
  if ( !*((_QWORD *)pv + 10) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\scheduler.cpp",
      v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids,
      *(unsigned int *)pv);
  }
  v7 = (_QWORD *)lambda_5bb2a98cf85b373dd723daae1fbe55f9_::_lambda_5bb2a98cf85b373dd723daae1fbe55f9_(v9, pv);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_e4d4e52fde46605ad4b445b99412b927__void_(
    v10,
    *v7);
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    pv + 88,
    v10);
  wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(v10);
  std::weak_ptr<JobScheduler>::operator=<JobScheduler,0>(pv + 128, a2);
  v8 = (std::_Ref_count_base *)a2[1];
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
}

```

## disassembly

```asm
0x18001184c  mov     [rsp+arg_10], rbx
0x180011851  mov     [rsp+arg_18], rsi
0x180011856  push    rdi
0x180011857  sub     rsp, 0B0h
0x18001185e  mov     rax, cs:__security_cookie
0x180011865  xor     rax, rsp
0x180011868  mov     [rsp+0B8h+var_10], rax
0x180011870  mov     rsi, rdx
0x180011873  mov     rdi, rcx
0x180011876  mov     [rsp+0B8h+var_98], rdx
0x18001187b  mov     [rcx], r8d
0x18001187e  lea     r8, [rcx+8]; pcbe
0x180011882  mov     dword ptr [r8], 3
0x180011889  mov     qword ptr [r8+8], 0
0x180011891  mov     qword ptr [r8+10h], 0
0x180011899  mov     qword ptr [r8+18h], 0
0x1800118a1  mov     qword ptr [r8+20h], 0
0x1800118a9  mov     qword ptr [r8+28h], 0
0x1800118b1  mov     qword ptr [r8+30h], 0
0x1800118b9  mov     dword ptr [r8+38h], 0
0x1800118c1  mov     dword ptr [r8+40h], 48h ; 'H'
0x1800118c9  mov     eax, [rcx]
0x1800118cb  mov     [rcx+44h], eax
0x1800118ce  mov     rax, [rdx]
0x1800118d1  mov     rcx, [rax+10h]
0x1800118d5  mov     [rdi+10h], rcx
0x1800118d9  mov     rdx, rdi; pv
0x1800118dc  lea     rcx, ?_RunJobCallback@JobScheduler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800118e3  call    cs:__imp_CreateThreadpoolWork
0x1800118e9  mov     rdx, rax
0x1800118ec  lea     rcx, [rdi+50h]
0x1800118f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800118f5  mov     rcx, [rsp+0B8h]; this
0x1800118fd  cmp     qword ptr [rdi+50h], 0
0x180011902  jnz     short loc_180011916
0x180011904  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001190b  mov     edx, 148h; void *
0x180011910  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180011916  lea     rax, WPP_GLOBAL_Control
0x18001191d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011924  cmp     rcx, rax
0x180011927  jz      short loc_18001194D
0x180011929  test    byte ptr [rcx+1Ch], 80h
0x18001192d  jz      short loc_18001194D
0x18001192f  cmp     byte ptr [rcx+19h], 4
0x180011933  jb      short loc_18001194D
0x180011935  mov     edx, 1Dh
0x18001193a  mov     r9d, [rdi]
0x18001193d  lea     r8, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x180011944  mov     rcx, [rcx+10h]
0x180011948  call    WPP_SF_d
0x18001194d  mov     rdx, rdi
0x180011950  lea     rcx, [rsp+0B8h+var_90]
0x180011955  call    _lambda_5bb2a98cf85b373dd723daae1fbe55f9____lambda_5bb2a98cf85b373dd723daae1fbe55f9_
0x18001195a  mov     rdx, [rax]
0x18001195d  lea     rcx, [rsp+0B8h+var_88]
0x180011962  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_e4d4e52fde46605ad4b445b99412b927__void_
0x180011967  nop
0x180011968  lea     rcx, [rdi+58h]
0x18001196c  lea     rdx, [rsp+0B8h+var_88]
0x180011971  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180011976  nop
0x180011977  lea     rcx, [rsp+0B8h+var_88]
0x18001197c  call    ??1?$function@$$A6AXAEBU_DRIVER_RECOVERY_CONTEXT@@@Z@wistd@@QEAA@XZ; wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(void)
0x180011981  lea     rcx, [rdi+80h]
0x180011988  mov     rdx, rsi
0x18001198b  call    ??$?4VJobScheduler@@$0A@@?$weak_ptr@VJobScheduler@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VJobScheduler@@@1@@Z; std::weak_ptr<JobScheduler>::operator=<JobScheduler,0>(std::shared_ptr<JobScheduler> const &)
0x180011990  nop
0x180011991  mov     rcx, [rsi+8]; this
0x180011995  test    rcx, rcx
0x180011998  jz      short loc_18001199F
0x18001199a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001199f  mov     rcx, [rsp+0B8h+var_10]
0x1800119a7  xor     rcx, rsp; StackCookie
0x1800119aa  call    __security_check_cookie
0x1800119af  lea     r11, [rsp+0B8h+var_8]
0x1800119b7  mov     rbx, [r11+20h]
0x1800119bb  mov     rsi, [r11+28h]
0x1800119bf  mov     rsp, r11
0x1800119c2  pop     rdi
0x1800119c3  retn
```
