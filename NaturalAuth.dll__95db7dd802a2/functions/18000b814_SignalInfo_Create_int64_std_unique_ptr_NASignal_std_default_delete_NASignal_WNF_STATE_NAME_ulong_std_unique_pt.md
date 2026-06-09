# SignalInfo::Create(__int64,std::unique_ptr<NASignal,std::default_delete<NASignal>> &&,_WNF_STATE_NAME *,ulong,std::unique_ptr<SignalInfo,std::default_delete<SignalInfo>> *)

- ea: `0x18000b814`
- end: `0x18000b961`
- name: `?Create@SignalInfo@@SAJ_J$$QEAV?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@PEAU_WNF_STATE_NAME@@KPEAV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@3@@Z`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000bbe8`

## callees

- `0x18000459c`
- `0x18000a7d0`
- `0x18000afb0`
- `0x18000b5b0`
- `0x18000b5d0`
- `0x18000b7e4`
- `0x18000b814`
- `0x18000c294`
- `0x18000cc58`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b837`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b90c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SignalInfo::Create(void *a1, void **a2, struct _WNF_STATE_NAME *a3, int a4, RTL_SRWLOCK **a5)
{
  __int64 v9; // rcx
  RTL_SRWLOCK *v11; // rbx
  void *v12; // rcx
  RTL_SRWLOCK *v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  RTL_SRWLOCK *v16; // [rsp+20h] [rbp-68h] BYREF
  RTL_SRWLOCK *v17[2]; // [rsp+28h] [rbp-60h] BYREF
  char v18[80]; // [rsp+38h] [rbp-50h] BYREF

  AcquireSRWLockShared(&SignalInfo::stateToRuleMappingLock);
  v16 = &SignalInfo::stateToRuleMappingLock;
  if ( *(_QWORD *)(*(_QWORD *)std::map<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>::_Try_emplace<_WNF_STATE_NAME const &,>(
                                v9,
                                v17,
                                a3)
                 + 48LL) < 0xC8u )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    v11 = (RTL_SRWLOCK *)operator new(0x28u);
    v17[0] = v11;
    v11->Ptr = &SignalInfo::`vftable';
    v11[1].Ptr = a1;
    v12 = *a2;
    *a2 = 0;
    v11[2].Ptr = v12;
    v11[3].Ptr = (PVOID)*a3;
    LODWORD(v11[4].Ptr) = a4;
    (*(void (__fastcall **)(void *, RTL_SRWLOCK *))(*(_QWORD *)v12 + 16LL))(v12, v11);
    v13 = *a5;
    *a5 = v11;
    if ( v13 )
      std::default_delete<SignalInfo>::operator()();
    AcquireSRWLockExclusive(&SignalInfo::stateToRuleMappingLock);
    v17[0] = &SignalInfo::stateToRuleMappingLock;
    v15 = (_QWORD *)std::map<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>::_Try_emplace<_WNF_STATE_NAME const &,>(
                      v14,
                      v18,
                      a3);
    v16 = *a5;
    std::list<SignalInfo *>::push_back(*v15 + 40LL, &v16);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v17);
    SignalInfo::UpdateWnfState(*a3, a4);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    return 3489661081LL;
  }
}

```

## disassembly

```asm
0x18000b814  push    rbx
0x18000b816  push    rbp
0x18000b817  push    rsi
0x18000b818  push    rdi
0x18000b819  push    r14
0x18000b81b  push    r15
0x18000b81d  sub     rsp, 58h
0x18000b821  mov     esi, r9d
0x18000b824  mov     rdi, r8
0x18000b827  mov     r14, rdx
0x18000b82a  mov     rbp, rcx
0x18000b82d  lea     r15, ?stateToRuleMappingLock@SignalInfo@@0Vsrwlock@wil@@A; wil::srwlock SignalInfo::stateToRuleMappingLock
0x18000b834  mov     rcx, r15; SRWLock
0x18000b837  call    cs:__imp_AcquireSRWLockShared
0x18000b83d  mov     [rsp+88h+var_68], r15
0x18000b842  mov     r8, rdi
0x18000b845  lea     rdx, [rsp+88h+var_60]
0x18000b84a  call    ??$_Try_emplace@AEBU_WNF_STATE_NAME@@$$V@?$map@U_WNF_STATE_NAME@@UList@SignalInfo@@UWnfStateLessThan@3@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@PEAX@std@@_N@1@AEBU_WNF_STATE_NAME@@@Z; std::map<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>::_Try_emplace<_WNF_STATE_NAME const &,>(_WNF_STATE_NAME const &)
0x18000b84f  mov     r9, [rax]
0x18000b852  cmp     qword ptr [r9+30h], 0C8h
0x18000b85a  jb      short loc_18000B89F
0x18000b85c  lea     rax, WPP_GLOBAL_Control
0x18000b863  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b86a  cmp     rcx, rax
0x18000b86d  jz      short loc_18000B88B
0x18000b86f  test    byte ptr [rcx+1Ch], 1
0x18000b873  jz      short loc_18000B88B
0x18000b875  mov     edx, 0Ah
0x18000b87a  lea     r8, WPP_e2b6b4cf14243e9ce41376c4a3f62423_Traceguids
0x18000b881  mov     rcx, [rcx+10h]
0x18000b885  call    WPP_SF_
0x18000b88a  nop
0x18000b88b  lea     rcx, [rsp+88h+var_68]
0x18000b890  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b895  mov     eax, 0D0000099h
0x18000b89a  jmp     loc_18000B954
0x18000b89f  lea     rcx, [rsp+88h+var_68]
0x18000b8a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b8a9  mov     ecx, 28h ; '('; Size
0x18000b8ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b8b3  mov     rbx, rax
0x18000b8b6  mov     [rsp+88h+var_60], rax
0x18000b8bb  lea     rax, ??_7SignalInfo@@6B@; const SignalInfo::`vftable'
0x18000b8c2  mov     [rbx], rax
0x18000b8c5  mov     [rbx+8], rbp
0x18000b8c9  mov     rcx, [r14]
0x18000b8cc  mov     qword ptr [r14], 0
0x18000b8d3  mov     [rbx+10h], rcx
0x18000b8d7  mov     rdx, [rdi]
0x18000b8da  mov     [rbx+18h], rdx
0x18000b8de  mov     [rbx+20h], esi
0x18000b8e1  mov     rax, [rcx]
0x18000b8e4  mov     rdx, rbx
0x18000b8e7  mov     rax, [rax+10h]
0x18000b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f0  nop
0x18000b8f1  mov     r14, [rsp+88h+arg_20]
0x18000b8f9  mov     rdx, [r14]
0x18000b8fc  mov     [r14], rbx
0x18000b8ff  test    rdx, rdx
0x18000b902  jz      short loc_18000B909
0x18000b904  call    ??R?$default_delete@VSignalInfo@@@std@@QEBAXPEAVSignalInfo@@@Z; std::default_delete<SignalInfo>::operator()(SignalInfo *)
0x18000b909  mov     rcx, r15; SRWLock
0x18000b90c  call    cs:__imp_AcquireSRWLockExclusive
0x18000b912  mov     [rsp+88h+var_60], r15
0x18000b917  mov     r8, rdi
0x18000b91a  lea     rdx, [rsp+88h+var_50]
0x18000b91f  call    ??$_Try_emplace@AEBU_WNF_STATE_NAME@@$$V@?$map@U_WNF_STATE_NAME@@UList@SignalInfo@@UWnfStateLessThan@3@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_WNF_STATE_NAME@@UList@SignalInfo@@@std@@PEAX@std@@_N@1@AEBU_WNF_STATE_NAME@@@Z; std::map<_WNF_STATE_NAME,SignalInfo::List,SignalInfo::WnfStateLessThan,std::allocator<std::pair<_WNF_STATE_NAME const,SignalInfo::List>>>::_Try_emplace<_WNF_STATE_NAME const &,>(_WNF_STATE_NAME const &)
0x18000b924  mov     rcx, [r14]
0x18000b927  mov     [rsp+88h+var_68], rcx
0x18000b92c  mov     rcx, [rax]
0x18000b92f  add     rcx, 28h ; '('
0x18000b933  lea     rdx, [rsp+88h+var_68]
0x18000b938  call    ?push_back@?$list@PEAVSignalInfo@@V?$allocator@PEAVSignalInfo@@@std@@@std@@QEAAX$$QEAPEAVSignalInfo@@@Z; std::list<SignalInfo *>::push_back(SignalInfo * &&)
0x18000b93d  nop
0x18000b93e  lea     rcx, [rsp+88h+var_60]
0x18000b943  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b948  mov     edx, esi; unsigned int
0x18000b94a  mov     rcx, [rdi]; struct _WNF_STATE_NAME
0x18000b94d  call    ?UpdateWnfState@SignalInfo@@CAXU_WNF_STATE_NAME@@K@Z; SignalInfo::UpdateWnfState(_WNF_STATE_NAME,ulong)
0x18000b952  xor     eax, eax
0x18000b954  add     rsp, 58h
0x18000b958  pop     r15
0x18000b95a  pop     r14
0x18000b95c  pop     rdi
0x18000b95d  pop     rsi
0x18000b95e  pop     rbp
0x18000b95f  pop     rbx
0x18000b960  retn
```
