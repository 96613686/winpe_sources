# NaturalAuthTimerTask::SetSignalState(ushort *,NA_RULE_STATE)

- ea: `0x18002c98c`
- end: `0x18002ca7f`
- name: `?SetSignalState@NaturalAuthTimerTask@@QEAAXPEAGW4NA_RULE_STATE@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002ca90`

## callees

- `0x18000a7f8`
- `0x18000b5d0`
- `0x18001fb2c`
- `0x18002072c`
- `0x18002b3bc`
- `0x18002c98c`
- `0x18002cdf8`
- `0x18002d62c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c9ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c9ad`

## pseudocode

```c
__int64 __fastcall NaturalAuthTimerTask::SetSignalState(__int64 a1, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rsi
  unsigned int v8; // eax
  unsigned int v9; // edi
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = a1;
  AcquireSRWLockShared(&stru_18005FCC8);
  v11 = &stru_18005FCC8;
  _bstr_t::_bstr_t((_bstr_t *)&v12, a2);
  std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::find(
    v5,
    &v13,
    &v12);
  _bstr_t::_Free((_bstr_t *)&v12);
  v6 = v13;
  if ( v13 != qword_18005F9E0 )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(v13 + 40) + 48LL);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, a3);
    v8 = EvaluateTimeSpec(v7 + 24, a3);
    v9 = v8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, v8);
    GenericPlugin::DefaultSignal::SetState(*(_QWORD *)(v6 + 40), v9);
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
}

```

## disassembly

```asm
0x18002c98c  mov     [rsp+arg_8], rbx
0x18002c991  mov     [rsp+arg_0], rcx
0x18002c996  push    rbp
0x18002c997  push    rsi
0x18002c998  push    rdi
0x18002c999  sub     rsp, 30h
0x18002c99d  mov     edi, r8d
0x18002c9a0  mov     rbx, rdx
0x18002c9a3  lea     rsi, stru_18005FCC8
0x18002c9aa  mov     rcx, rsi; SRWLock
0x18002c9ad  call    cs:__imp_AcquireSRWLockShared
0x18002c9b3  mov     [rsp+48h+var_28], rsi
0x18002c9b8  mov     rdx, rbx; unsigned __int16 *
0x18002c9bb  lea     rcx, [rsp+48h+arg_0]; this
0x18002c9c0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002c9c5  lea     r8, [rsp+48h+arg_0]
0x18002c9ca  lea     rdx, [rsp+48h+arg_18]
0x18002c9cf  call    ?find@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@std@@@std@@@2@AEBV_bstr_t@@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::find(_bstr_t const &)
0x18002c9d4  lea     rcx, [rsp+48h+arg_0]; this
0x18002c9d9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c9de  mov     rbx, [rsp+48h+arg_18]
0x18002c9e3  cmp     rbx, cs:qword_18005F9E0
0x18002c9ea  jz      short loc_18002CA68
0x18002c9ec  mov     rax, [rbx+28h]
0x18002c9f0  mov     rsi, [rax+30h]
0x18002c9f4  lea     rbp, WPP_GLOBAL_Control
0x18002c9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca02  cmp     rcx, rbp
0x18002ca05  jz      short loc_18002CA25
0x18002ca07  test    byte ptr [rcx+1Ch], 4
0x18002ca0b  jz      short loc_18002CA25
0x18002ca0d  mov     edx, 23h ; '#'
0x18002ca12  mov     r9d, edi
0x18002ca15  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002ca1c  mov     rcx, [rcx+10h]
0x18002ca20  call    WPP_SF_d
0x18002ca25  mov     edx, edi
0x18002ca27  lea     rcx, [rsi+18h]
0x18002ca2b  call    EvaluateTimeSpec
0x18002ca30  mov     edi, eax
0x18002ca32  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca39  cmp     rcx, rbp
0x18002ca3c  jz      short loc_18002CA5C
0x18002ca3e  test    byte ptr [rcx+1Ch], 4
0x18002ca42  jz      short loc_18002CA5C
0x18002ca44  mov     edx, 24h ; '$'
0x18002ca49  mov     r9d, eax
0x18002ca4c  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002ca53  mov     rcx, [rcx+10h]
0x18002ca57  call    WPP_SF_d
0x18002ca5c  mov     edx, edi
0x18002ca5e  mov     rcx, [rbx+28h]
0x18002ca62  call    ?SetState@DefaultSignal@GenericPlugin@@QEAAXW4NA_RULE_STATE@@@Z; GenericPlugin::DefaultSignal::SetState(NA_RULE_STATE)
0x18002ca67  nop
0x18002ca68  lea     rcx, [rsp+48h+var_28]
0x18002ca6d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ca72  mov     rbx, [rsp+48h+arg_8]
0x18002ca77  add     rsp, 30h
0x18002ca7b  pop     rdi
0x18002ca7c  pop     rsi
0x18002ca7d  pop     rbp
0x18002ca7e  retn
```
