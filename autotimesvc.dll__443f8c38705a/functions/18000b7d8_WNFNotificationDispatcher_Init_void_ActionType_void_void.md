# WNFNotificationDispatcher::Init(void (*)(ActionType,void *),void *)

- ea: `0x18000b7d8`
- end: `0x18000b863`
- name: `?Init@WNFNotificationDispatcher@@QEAAXP6AXW4ActionType@@PEAX@Z1@Z`
- size: `139`
- prototype: `void __fastcall(char *pv, void (__high *)(enum ActionType, void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180007534`

## callees

- `0x180005840`
- `0x18000a658`
- `0x18000b7d8`
- `0x18000bb08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b824`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000b824`

## string_xrefs

- `0x18000b83f`: `onecore\base\time\autotime\timeservice\wnfnotifdispatcher.cpp`

## pseudocode

```c
void __fastcall WNFNotificationDispatcher::Init(char *pv, void (__high *a2)(enum ActionType, void *), void *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+50h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(pv + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 16));
  v10 = v6;
  *((_QWORD *)pv + 1) = a2;
  *((_QWORD *)pv + 9) = a3;
  *(_DWORD *)pv = 0;
  pv[56] = 0;
  if ( !*((_QWORD *)pv + 8) )
  {
    ThreadpoolWork = CreateThreadpoolWork(WNFNotificationDispatcher::_DispatchWNFNotification, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      pv + 64,
      ThreadpoolWork);
    if ( !*((_QWORD *)pv + 8) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wnfnotifdispatcher.cpp",
        v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x18000b7d8  push    rbx
0x18000b7da  push    rsi
0x18000b7db  push    rdi
0x18000b7dc  push    r14
0x18000b7de  sub     rsp, 28h
0x18000b7e2  mov     rsi, r8
0x18000b7e5  mov     rdi, rdx
0x18000b7e8  mov     r14, rcx
0x18000b7eb  lea     rbx, [rcx+10h]
0x18000b7ef  mov     rcx, rbx; lpCriticalSection
0x18000b7f2  call    cs:__imp_EnterCriticalSection
0x18000b7f8  mov     [rsp+48h+arg_0], rbx
0x18000b7fd  mov     [r14+8], rdi
0x18000b801  mov     [r14+48h], rsi
0x18000b805  xor     edi, edi
0x18000b807  mov     [r14], edi
0x18000b80a  mov     [r14+38h], dil
0x18000b80e  lea     rbx, [r14+40h]
0x18000b812  cmp     [rbx], rdi
0x18000b815  jnz     short loc_18000B84F
0x18000b817  xor     r8d, r8d; pcbe
0x18000b81a  mov     rdx, r14; pv
0x18000b81d  lea     rcx, ?_DispatchWNFNotification@WNFNotificationDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000b824  call    cs:__imp_CreateThreadpoolWork
0x18000b82a  mov     rdx, rax
0x18000b82d  mov     rcx, rbx
0x18000b830  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18000b835  mov     rcx, [rsp+48h]; this
0x18000b83a  cmp     [rbx], rdi
0x18000b83d  jnz     short loc_18000B84F
0x18000b83f  lea     r8, aOnecoreBaseTim; "onecore\\base\\time\\autotime\\timeserv"...
0x18000b846  lea     edx, [rdi+7Fh]; void *
0x18000b849  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000b84f  lea     rcx, [rsp+48h+arg_0]
0x18000b854  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b859  add     rsp, 28h
0x18000b85d  pop     r14
0x18000b85f  pop     rdi
0x18000b860  pop     rsi
0x18000b861  pop     rbx
0x18000b862  retn
```
