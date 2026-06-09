# wil::details::make_wnf_subscription_state<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload>(_WNF_STATE_NAME const &,wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)> &&,ulong,wil::details::wnf_subscription_state<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload> * *)

- ea: `0x180025564`
- end: `0x18002573f`
- name: `??$make_wnf_subscription_state@UScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@UScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@01@@Z`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002550c`

## callees

- `0x180004cd0`
- `0x18000be1c`
- `0x18001f2e8`
- `0x1800203e8`
- `0x180020548`
- `0x180020940`
- `0x1800233fc`
- `0x180025564`
- `0x180035010`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800256de`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800256de`
- `ntdll!NtQueryWnfStateData` at `0x180025643`
- `ntdll!NtQueryWnfStateData` at `0x180025643`

## pseudocode

```c
__int64 __fastcall wil::details::make_wnf_subscription_state<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        wil::details::wnf_subscription_state_base **a4)
{
  wil::details::wnf_subscription_state_base *v6; // rax
  wil::details::wnf_subscription_state_base *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // ebx
  void *v13; // rdx
  unsigned int v14; // r8d
  int v16; // [rsp+20h] [rbp-48h]
  int v17; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v18[32]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v17 = 0;
  *a4 = 0;
  v6 = (wil::details::wnf_subscription_state_base *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    wil::details::wnf_subscription_state_base::wnf_subscription_state_base(v6);
    *(_QWORD *)v7 = &wil::details::wnf_subscription_state<unsigned int>::`vftable';
    if ( *(_QWORD *)(a2 + 112) )
    {
      *((_QWORD *)v7 + 16) = (char *)v7 + 24;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 112) + 16LL))(*(_QWORD *)(a2 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 112) + 24LL))(*(_QWORD *)(a2 + 112));
      *(_QWORD *)(a2 + 112) = 0;
    }
    else
    {
      *((_QWORD *)v7 + 16) = 0;
    }
    if ( v17 != -1
      || (v8 = NtQueryWnfStateData(&WNF_EOA_NARRATOR_FOCUS_CHANGE, 0, 0, &v17) | 0x10000000, (int)(v8 + 0x80000000) < 0)
      || v8 == -805306333 )
    {
      v9 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>(
             v18,
             (char *)v7 + 8);
      v10 = wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>::operator _WNF_USER_SUBSCRIPTION * *(v9);
      v12 = RtlSubscribeWnfStateChangeNotification(
              v10,
              WNF_EOA_NARRATOR_FOCUS_CHANGE,
              v11,
              _lambda_8057ce1500eb099f30e0be6d78e6e64e_::_lambda_invoker_cdecl_);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>(v18);
      if ( v12 >= 0 )
      {
        *a4 = v7;
        return 0;
      }
      v8 = wil::details::in1diag3::Return_NtStatus(retaddr, v13, v14, (const char *)(unsigned int)v12, (int)v7);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)v8,
        0);
    }
    (**(void (__fastcall ***)(wil::details::wnf_subscription_state_base *, __int64))v7)(v7, 1);
  }
  else
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)0x8007000ELL,
      v16);
  }
  return v8;
}

```

## disassembly

```asm
0x180025564  mov     rax, rsp
0x180025567  mov     [rax+8], rbx
0x18002556b  mov     [rax+10h], rsi
0x18002556f  mov     [rax+18h], r8d
0x180025573  push    rdi
0x180025574  sub     rsp, 60h
0x180025578  mov     rsi, r9
0x18002557b  mov     rbx, rdx
0x18002557e  mov     dword ptr [rax-28h], 0
0x180025585  mov     qword ptr [r9], 0
0x18002558c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025593  mov     ecx, 88h; unsigned __int64
0x180025598  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002559d  mov     rdi, rax
0x1800255a0  test    rax, rax
0x1800255a3  jz      loc_18002570F
0x1800255a9  mov     rcx, rax; this
0x1800255ac  call    ??0wnf_subscription_state_base@details@wil@@QEAA@XZ; wil::details::wnf_subscription_state_base::wnf_subscription_state_base(void)
0x1800255b1  lea     r8, ??_7?$wnf_subscription_state@I@details@wil@@6B@; const wil::details::wnf_subscription_state<uint>::`vftable'
0x1800255b8  mov     [rdi], r8
0x1800255bb  cmp     qword ptr [rbx+70h], 0
0x1800255c0  jnz     short loc_1800255CF
0x1800255c2  mov     qword ptr [rdi+80h], 0
0x1800255cd  jmp     short loc_180025602
0x1800255cf  lea     rdx, [rdi+18h]
0x1800255d3  mov     [rdi+80h], rdx
0x1800255da  mov     rcx, [rbx+70h]
0x1800255de  mov     rax, [rcx]
0x1800255e1  mov     rax, [rax+10h]
0x1800255e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255ea  mov     rcx, [rbx+70h]
0x1800255ee  mov     rax, [rcx]
0x1800255f1  mov     rax, [rax+18h]
0x1800255f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255fa  mov     qword ptr [rbx+70h], 0
0x180025602  mov     r8d, [rsp+68h+var_28]
0x180025607  cmp     r8d, 0FFFFFFFFh
0x18002560b  jnz     loc_180025699
0x180025611  mov     [rsp+68h+arg_10], 0
0x18002561c  lea     rax, [rsp+68h+arg_10]
0x180025624  mov     [rsp+68h+var_40], rax
0x180025629  mov     qword ptr [rsp+68h+var_48], 0; int
0x180025632  lea     r9, [rsp+68h+var_28]
0x180025637  xor     r8d, r8d
0x18002563a  xor     edx, edx
0x18002563c  lea     rcx, WNF_EOA_NARRATOR_FOCUS_CHANGE
0x180025643  call    cs:__imp_NtQueryWnfStateData
0x180025649  mov     ebx, eax
0x18002564b  bts     ebx, 1Ch
0x18002564f  mov     ecx, 80000000h
0x180025654  lea     eax, [rbx+rcx]
0x180025657  test    ecx, eax
0x180025659  jnz     short loc_180025694
0x18002565b  cmp     ebx, 0D0000023h
0x180025661  jz      short loc_180025694
0x180025663  mov     rcx, [rsp+68h]; this
0x180025668  mov     r9d, ebx; char *
0x18002566b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180025672  mov     edx, 3B8h; void *
0x180025677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002567c  mov     rcx, [rdi]
0x18002567f  mov     rax, [rcx]
0x180025682  mov     edx, 1
0x180025687  mov     rcx, rdi
0x18002568a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002568f  jmp     loc_18002572D
0x180025694  mov     r8d, [rsp+68h+var_28]
0x180025699  lea     rdx, [rdi+8]
0x18002569d  lea     rcx, [rsp+68h+var_20]
0x1800256a2  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>> &)
0x1800256a7  mov     rcx, rax
0x1800256aa  call    ??B?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAU_WNF_USER_SUBSCRIPTION@@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>::operator _WNF_USER_SUBSCRIPTION * *(void)
0x1800256af  mov     rcx, rax
0x1800256b2  mov     [rsp+68h+var_30], 0
0x1800256ba  mov     [rsp+68h+var_38], 0
0x1800256c2  mov     [rsp+68h+var_40], 0
0x1800256cb  mov     qword ptr [rsp+68h+var_48], rdi; int
0x1800256d0  lea     r9, ?_lambda_invoker_cdecl_@_lambda_8057ce1500eb099f30e0be6d78e6e64e_@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; _lambda_8057ce1500eb099f30e0be6d78e6e64e_::_lambda_invoker_cdecl_(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800256d7  mov     rdx, cs:WNF_EOA_NARRATOR_FOCUS_CHANGE
0x1800256de  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800256e4  mov     ebx, eax
0x1800256e6  lea     rcx, [rsp+68h+var_20]
0x1800256eb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>>>(void)
0x1800256f0  test    ebx, ebx
0x1800256f2  jns     short loc_180025708
0x1800256f4  mov     rcx, [rsp+68h]; this
0x1800256f9  mov     r9d, ebx; char *
0x1800256fc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025701  mov     ebx, eax
0x180025703  jmp     loc_18002567C
0x180025708  mov     [rsi], rdi
0x18002570b  xor     eax, eax
0x18002570d  jmp     short loc_18002572F
0x18002570f  mov     rcx, [rsp+68h]; this
0x180025714  mov     ebx, 8007000Eh
0x180025719  mov     r9d, ebx; char *
0x18002571c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180025723  mov     edx, 3B1h; void *
0x180025728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002572d  mov     eax, ebx
0x18002572f  mov     rbx, [rsp+68h+arg_0]
0x180025734  mov     rsi, [rsp+68h+arg_8]
0x180025739  add     rsp, 60h
0x18002573d  pop     rdi
0x18002573e  retn
```
