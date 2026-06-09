# SignalInfo::UpdateWnfState(_WNF_STATE_NAME,ulong)

- ea: `0x18000c294`
- end: `0x18000c496`
- name: `?UpdateWnfState@SignalInfo@@CAXU_WNF_STATE_NAME@@K@Z`
- size: `514`
- prototype: `void __fastcall(struct _WNF_STATE_NAME, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000b5f0`
- `0x18000b814`
- `0x18000c280`

## callees

- `0x1800045e0`
- `0x18000a7d0`
- `0x18000a7f8`
- `0x18000b55c`
- `0x18000b5d0`
- `0x18000c294`
- `0x18000cb30`
- `0x18000cbbc`
- `0x18000d298`
- `0x18000d2f8`
- `0x180046010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18000c441`
- `ntdll!RtlPublishWnfStateData` at `0x18000c441`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c2bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c2bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SignalInfo::UpdateWnfState(struct _WNF_STATE_NAME a1, int a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  PVOID *v6; // rsi
  __int64 v7; // rbx
  unsigned int v8; // r13d
  __int64 *v9; // r12
  __int64 v10; // r9
  unsigned int v11; // r15d
  _QWORD *v12; // rsi
  _QWORD *i; // rbx
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 StateName; // rax
  int v17; // edx
  int v18; // r8d
  int *v19; // rcx
  unsigned int v20; // eax
  const struct std::nothrow_t *v21; // rdx
  RTL_SRWLOCK *v22; // [rsp+30h] [rbp-18h] BYREF
  struct _WNF_STATE_NAME v23; // [rsp+90h] [rbp+48h] BYREF
  int v24; // [rsp+98h] [rbp+50h] BYREF
  __int64 *v25; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+60h] BYREF

  v24 = a2;
  v23 = a1;
  AcquireSRWLockShared(&SignalInfo::stateToRuleMappingLock);
  v22 = &SignalInfo::stateToRuleMappingLock;
  v25 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_lll(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v5, a1.Data[0], v23.Data[1], v24, v22);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>,0>>::find(
    v4,
    &v26,
    &v23);
  v7 = v26;
  if ( v26 == SignalInfo::stateToRuleMapping || !*(_QWORD *)(v26 + 48) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_(v6[2], 12, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids);
    v9 = `SignalInfo::UpdateWnfState'::`5'::EMPTY_STATE;
    v8 = 24;
  }
  else
  {
    v8 = 16 * *(_DWORD *)(v26 + 48) + 8;
    v9 = (__int64 *)operator new[](v8);
    v25 = v9;
    v10 = *(unsigned int *)(v7 + 48);
    *(_DWORD *)v9 = v10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids, v10);
    v11 = 0;
    v12 = *(_QWORD **)(v7 + 40);
    for ( i = (_QWORD *)*v12; i != v12; i = (_QWORD *)*i )
    {
      v14 = i[2];
      v9[2 * v11 + 1] = *(_QWORD *)(v14 + 8);
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 16) + 8LL))(*(_QWORD *)(v14 + 16));
      LODWORD(v9[2 * v11 + 2]) = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        StateName = getStateName(v15);
        WPP_SF_ls(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v11, StateName);
      }
      ++v11;
    }
  }
  v19 = &v24;
  if ( v24 == -1 )
    v19 = 0;
  v20 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RtlPublishWnfStateData)(a1, 0, v9, v8, v19);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids, v20);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)&v25, v21);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x18000c294  mov     [rsp-40h+arg_8], edx
0x18000c298  mov     [rsp-40h+arg_0], rcx
0x18000c29d  push    rbp
0x18000c29e  push    rbx
0x18000c29f  push    rsi
0x18000c2a0  push    rdi
0x18000c2a1  push    r12
0x18000c2a3  push    r13
0x18000c2a5  push    r14
0x18000c2a7  push    r15
0x18000c2a9  mov     rbp, rsp
0x18000c2ac  sub     rsp, 48h
0x18000c2b0  mov     rdi, rcx
0x18000c2b3  lea     rbx, ?stateToRuleMappingLock@SignalInfo@@0Vsrwlock@wil@@A; wil::srwlock SignalInfo::stateToRuleMappingLock
0x18000c2ba  mov     rcx, rbx; SRWLock
0x18000c2bd  call    cs:__imp_AcquireSRWLockShared
0x18000c2c3  mov     [rbp+var_18], rbx
0x18000c2c7  mov     [rbp+arg_10], 0
0x18000c2cf  lea     r14, WPP_GLOBAL_Control
0x18000c2d6  mov     rsi, cs:WPP_GLOBAL_Control
0x18000c2dd  cmp     rsi, r14
0x18000c2e0  jz      short loc_18000C309
0x18000c2e2  test    byte ptr [rsi+1Ch], 4
0x18000c2e6  jz      short loc_18000C309
0x18000c2e8  mov     eax, [rbp+arg_8]
0x18000c2eb  mov     [rsp+48h+var_20], eax
0x18000c2ef  mov     eax, dword ptr [rbp+arg_0+4]
0x18000c2f2  mov     dword ptr [rsp+48h+var_28], eax
0x18000c2f6  mov     r9d, edi
0x18000c2f9  mov     rcx, [rsi+10h]
0x18000c2fd  call    WPP_SF_lll
0x18000c302  mov     rsi, cs:WPP_GLOBAL_Control
0x18000c309  lea     r8, [rbp+arg_0]
0x18000c30d  lea     rdx, [rbp+arg_18]
0x18000c311  call    ?find@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@UList@SignalInfo@@UWnfStateLessThan@3@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@@std@@@2@AEBU_WNF_STATE_NAME@@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>,0>>::find(_WNF_STATE_NAME const &)
0x18000c316  mov     rbx, [rbp+arg_18]
0x18000c31a  cmp     rbx, cs:?stateToRuleMapping@SignalInfo@@0V?$map@U_WNF_STATE_NAME@@UList@SignalInfo@@UWnfStateLessThan@3@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@@std@@A; std::map<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>> SignalInfo::stateToRuleMapping
0x18000c321  jz      loc_18000C3F6
0x18000c327  cmp     qword ptr [rbx+30h], 0
0x18000c32c  jz      loc_18000C3F6
0x18000c332  mov     r13d, [rbx+30h]
0x18000c336  shl     r13d, 4
0x18000c33a  add     r13d, 8
0x18000c33e  mov     ecx, r13d; unsigned __int64
0x18000c341  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c346  mov     r12, rax
0x18000c349  mov     [rbp+arg_10], rax
0x18000c34d  mov     r9d, [rbx+30h]
0x18000c351  mov     [rax], r9d
0x18000c354  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c35b  cmp     rcx, r14
0x18000c35e  jz      short loc_18000C37B
0x18000c360  test    byte ptr [rcx+1Ch], 4
0x18000c364  jz      short loc_18000C37B
0x18000c366  mov     edx, 0Dh
0x18000c36b  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c372  mov     rcx, [rcx+10h]
0x18000c376  call    WPP_SF_d
0x18000c37b  xor     r15d, r15d
0x18000c37e  mov     rsi, [rbx+28h]
0x18000c382  mov     rbx, [rsi]
0x18000c385  cmp     rbx, rsi
0x18000c388  jz      loc_18000C423
0x18000c38e  mov     rcx, [rbx+10h]
0x18000c392  mov     r14d, r15d
0x18000c395  add     r14, r14
0x18000c398  mov     rax, [rcx+8]
0x18000c39c  mov     [r12+r14*8+8], rax
0x18000c3a1  mov     rcx, [rcx+10h]
0x18000c3a5  mov     rax, [rcx]
0x18000c3a8  mov     rax, [rax+8]
0x18000c3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b1  mov     [r12+r14*8+10h], eax
0x18000c3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3bd  lea     r14, WPP_GLOBAL_Control
0x18000c3c4  cmp     rcx, r14
0x18000c3c7  jz      short loc_18000C3EE
0x18000c3c9  test    byte ptr [rcx+1Ch], 4
0x18000c3cd  jz      short loc_18000C3EE
0x18000c3cf  mov     ecx, eax
0x18000c3d1  call    getStateName
0x18000c3d6  mov     [rsp+48h+var_28], rax
0x18000c3db  mov     r9d, r15d
0x18000c3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3e5  mov     rcx, [rcx+10h]
0x18000c3e9  call    WPP_SF_ls
0x18000c3ee  inc     r15d
0x18000c3f1  mov     rbx, [rbx]
0x18000c3f4  jmp     short loc_18000C385
0x18000c3f6  cmp     rsi, r14
0x18000c3f9  jz      short loc_18000C416
0x18000c3fb  test    byte ptr [rsi+1Ch], 4
0x18000c3ff  jz      short loc_18000C416
0x18000c401  mov     edx, 0Ch
0x18000c406  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c40d  mov     rcx, [rsi+10h]
0x18000c411  call    WPP_SF_
0x18000c416  lea     r12, ?EMPTY_STATE@?4??UpdateWnfState@SignalInfo@@CAXU_WNF_STATE_NAME@@K@Z@4UNA_RULE_WNF_STATE_DATA@@B; NA_RULE_WNF_STATE_DATA const `SignalInfo::UpdateWnfState(_WNF_STATE_NAME,ulong)'::`5'::EMPTY_STATE
0x18000c41d  mov     r13d, 18h
0x18000c423  lea     rcx, [rbp+arg_8]
0x18000c427  xor     eax, eax
0x18000c429  cmp     [rbp+arg_8], 0FFFFFFFFh
0x18000c42d  cmovz   rcx, rax
0x18000c431  mov     [rsp+48h+var_28], rcx
0x18000c436  mov     r9d, r13d
0x18000c439  mov     r8, r12
0x18000c43c  xor     edx, edx
0x18000c43e  mov     rcx, rdi
0x18000c441  call    cs:__imp_RtlPublishWnfStateData
0x18000c447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c44e  cmp     rcx, r14
0x18000c451  jz      short loc_18000C472
0x18000c453  test    byte ptr [rcx+1Ch], 4
0x18000c457  jz      short loc_18000C472
0x18000c459  mov     edx, 0Fh
0x18000c45e  mov     r9d, eax
0x18000c461  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000c468  mov     rcx, [rcx+10h]
0x18000c46c  call    WPP_SF_d
0x18000c471  nop
0x18000c472  lea     rcx, [rbp+arg_10]
0x18000c476  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18000c47b  nop
0x18000c47c  lea     rcx, [rbp+var_18]
0x18000c480  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c485  add     rsp, 48h
0x18000c489  pop     r15
0x18000c48b  pop     r14
0x18000c48d  pop     r13
0x18000c48f  pop     r12
0x18000c491  pop     rdi
0x18000c492  pop     rsi
0x18000c493  pop     rbx
0x18000c494  pop     rbp
0x18000c495  retn
```
