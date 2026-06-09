# TimeoutEventHandler::SetTimer(OOBEMonitorEvent)

- ea: `0x1800306d8`
- end: `0x1800307cb`
- name: `?SetTimer@TimeoutEventHandler@@AEAAXW4OOBEMonitorEvent@@@Z`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800301f0`
- `0x180030650`

## callees

- `0x18000876c`
- `0x18000a664`
- `0x18000e2a0`
- `0x18000e2bc`
- `0x18002f370`
- `0x18002fde0`
- `0x1800306d8`
- `0x180030d00`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003078d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003078d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TimeoutEventHandler::SetTimer(__int64 a1, int a2)
{
  __int64 v4; // rax
  const char *v5; // r9
  DWORD DueTime; // [rsp+20h] [rbp-48h]
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char v10; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF
  char v12; // [rsp+80h] [rbp+18h] BYREF

  TimeoutEventHandler::DeleteTimer((TimeoutEventHandler *)a1);
  wil::AcquireSRWLockExclusive(&v10, a1 + 40);
  if ( a2 == 100 || a2 > *(_DWORD *)(a1 + 24) )
  {
    v11 = a2;
    if ( *(_QWORD *)std::_Hash<std::_Umap_traits<enum OOBEMonitorEvent,unsigned long,std::_Uhash_compare<enum OOBEMonitorEvent,std::hash<enum OOBEMonitorEvent>,std::equal_to<enum OOBEMonitorEvent>>,std::allocator<std::pair<enum OOBEMonitorEvent const,unsigned long>>,0>>::find(
                      a1 + 48,
                      &v12,
                      &v11) == *(_QWORD *)(a1 + 56) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
        (const char *)0x80070057LL,
        DueTime);
    v4 = std::_Hash<std::_Umap_traits<enum OOBEMonitorEvent,unsigned long,std::_Uhash_compare<enum OOBEMonitorEvent,std::hash<enum OOBEMonitorEvent>,std::equal_to<enum OOBEMonitorEvent>>,std::allocator<std::pair<enum OOBEMonitorEvent const,unsigned long>>,0>>::_Try_emplace<enum OOBEMonitorEvent const &,>(
           a1 + 48,
           v8,
           &v11);
    if ( !CreateTimerQueueTimer(
            (PHANDLE)(a1 + 16),
            0,
            _lambda_45de2c585ba6cfe8e46cffe7a71e841d_::_lambda_invoker_cdecl_,
            (PVOID)a1,
            *(_DWORD *)(*(_QWORD *)v4 + 20LL),
            0,
            8u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC0,
        (unsigned int)"shell\\oobe\\user\\monitor\\oobemonitoreventhandlers.cpp",
        v5);
    *(_DWORD *)(a1 + 24) = a2;
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x1800306d8  mov     [rsp+arg_18], rbx
0x1800306dd  push    rbp
0x1800306de  push    rsi
0x1800306df  push    rdi
0x1800306e0  sub     rsp, 50h
0x1800306e4  mov     esi, edx
0x1800306e6  mov     rdi, rcx
0x1800306e9  call    ?DeleteTimer@TimeoutEventHandler@@AEAAXXZ; TimeoutEventHandler::DeleteTimer(void)
0x1800306ee  lea     rdx, [rdi+28h]
0x1800306f2  lea     rcx, [rsp+68h+arg_0]
0x1800306f7  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800306fc  nop
0x1800306fd  cmp     esi, 64h ; 'd'
0x180030700  jz      short loc_18003070B
0x180030702  cmp     esi, [rdi+18h]
0x180030705  jle     loc_1800307B1
0x18003070b  mov     [rsp+68h+arg_8], esi
0x18003070f  lea     r8, [rsp+68h+arg_8]
0x180030714  lea     rdx, [rsp+68h+arg_10]
0x18003071c  lea     rcx, [rdi+30h]
0x180030720  call    ?find@?$_Hash@V?$_Umap_traits@W4OOBEMonitorEvent@@KV?$_Uhash_compare@W4OOBEMonitorEvent@@U?$hash@W4OOBEMonitorEvent@@@std@@U?$equal_to@W4OOBEMonitorEvent@@@3@@std@@V?$allocator@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@std@@@std@@@2@AEBW4OOBEMonitorEvent@@@Z; std::_Hash<std::_Umap_traits<OOBEMonitorEvent,ulong,std::_Uhash_compare<OOBEMonitorEvent,std::hash<OOBEMonitorEvent>,std::equal_to<OOBEMonitorEvent>>,std::allocator<std::pair<OOBEMonitorEvent const,ulong>>,0>>::find(OOBEMonitorEvent const &)
0x180030725  mov     rcx, [rdi+38h]
0x180030729  cmp     [rax], rcx
0x18003072c  setnz   al
0x18003072f  mov     rcx, [rsp+68h]; this
0x180030734  test    al, al
0x180030736  jnz     short loc_180030750
0x180030738  mov     r9d, 80070057h; char *
0x18003073e  lea     r8, aShellOobeUserM; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x180030745  mov     edx, 0C7h; void *
0x18003074a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030750  lea     r8, [rsp+68h+arg_8]
0x180030755  lea     rdx, [rsp+68h+var_28]
0x18003075a  lea     rcx, [rdi+30h]
0x18003075e  call    ??$_Try_emplace@AEBW4OOBEMonitorEvent@@$$V@?$_Hash@V?$_Umap_traits@W4OOBEMonitorEvent@@KV?$_Uhash_compare@W4OOBEMonitorEvent@@U?$hash@W4OOBEMonitorEvent@@@std@@U?$equal_to@W4OOBEMonitorEvent@@@3@@std@@V?$allocator@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4OOBEMonitorEvent@@K@std@@PEAX@std@@_N@1@AEBW4OOBEMonitorEvent@@@Z; std::_Hash<std::_Umap_traits<OOBEMonitorEvent,ulong,std::_Uhash_compare<OOBEMonitorEvent,std::hash<OOBEMonitorEvent>,std::equal_to<OOBEMonitorEvent>>,std::allocator<std::pair<OOBEMonitorEvent const,ulong>>,0>>::_Try_emplace<OOBEMonitorEvent const &,>(OOBEMonitorEvent const &)
0x180030763  mov     rax, [rax]
0x180030766  lea     rcx, [rdi+10h]; phNewTimer
0x18003076a  mov     [rsp+68h+Flags], 8; Flags
0x180030772  mov     [rsp+68h+Period], 0; Period
0x18003077a  mov     eax, [rax+14h]
0x18003077d  mov     [rsp+68h+DueTime], eax; DueTime
0x180030781  mov     r9, rdi; Parameter
0x180030784  lea     r8, ?_lambda_invoker_cdecl_@_lambda_45de2c585ba6cfe8e46cffe7a71e841d_@@CA@PEAXE@Z; Callback
0x18003078b  xor     edx, edx; TimerQueue
0x18003078d  call    cs:__imp_CreateTimerQueueTimer
0x180030793  mov     rcx, [rsp+68h]; this
0x180030798  test    eax, eax
0x18003079a  jnz     short loc_1800307AE
0x18003079c  lea     r8, aShellOobeUserM; "shell\\oobe\\user\\monitor\\oobemonitor"...
0x1800307a3  mov     edx, 0C0h; void *
0x1800307a8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800307ae  mov     [rdi+18h], esi
0x1800307b1  lea     rcx, [rsp+68h+arg_0]
0x1800307b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800307bb  mov     rbx, [rsp+68h+arg_18]
0x1800307c3  add     rsp, 50h
0x1800307c7  pop     rdi
0x1800307c8  pop     rsi
0x1800307c9  pop     rbp
0x1800307ca  retn
```
