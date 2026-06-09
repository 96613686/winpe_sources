# PresentEventConsumer::CompletePresent(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<PresentEventConsumer::PresentData>>>,unsigned __int64)

- ea: `0x180014e64`
- end: `0x180015033`
- name: `?CompletePresent@PresentEventConsumer@@AEAAXV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UPresentData@PresentEventConsumer@@@std@@@std@@@std@@_K@Z`
- size: `463`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d20`
- `0x180014dc0`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x180005c6c`
- `0x18000bbd0`
- `0x18000bcc0`
- `0x18000d7d4`
- `0x18000d8ec`
- `0x180014a64`
- `0x180014aec`
- `0x180014e64`
- `0x1800159dc`
- `0x180015b44`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PresentEventConsumer::CompletePresent(__int64 a1, __int64 **a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  __int64 *v14; // rcx
  __int64 *v15; // rdx
  struct _RTL_CRITICAL_SECTION *v16; // r8
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+20h] [rbp-79h] BYREF
  _QWORD v19[3]; // [rsp+28h] [rbp-71h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v22[3]; // [rsp+70h] [rbp-29h] BYREF
  int v23; // [rsp+88h] [rbp-11h]
  __int64 v24; // [rsp+90h] [rbp-9h]
  int v25; // [rsp+98h] [rbp-1h]
  int v26; // [rsp+9Ch] [rbp+3h]

  *(_DWORD *)(a1 + 164) += *((_DWORD *)a2 + 4) - *(_DWORD *)(a1 + 72);
  *(_QWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
            + 8) = a3;
  memset_0(v22, 0, 0x50u);
  v22[0] = *(_QWORD *)std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2);
  v22[1] = *(_QWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
                     + 8);
  v23 = *(_DWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
                  + 52);
  v25 = *(_DWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
                  + 56);
  v26 = *(_DWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
                  + 60);
  v24 = *(_QWORD *)(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(a2)
                  + 32);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    v18 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    if ( *a2 )
      v6 = **a2;
    else
      v6 = 0;
    v7 = std::_Deque_val<std::_Deque_simple_types<PresentEventConsumer::PresentData>>::_Subscript(v6, a2[2]);
    std::deque<PresentEventConsumer::PresentData>::push_back(a1 + 88, v7);
    v10 = a3 - 500000;
    while ( *(_QWORD *)(a1 + 120) )
    {
      v11 = std::queue<PresentEventConsumer::PresentData>::front(a1 + 88, v8, v10, v9, v18);
      if ( *(_QWORD *)(v11 + 8) >= v13 )
        break;
      std::deque<PresentEventConsumer::PresentData>::pop_front(v12);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
  }
  v14 = *a2;
  v15 = a2[2];
  v19[1] = 0;
  v19[0] = v14;
  v19[2] = (char *)v15 + 1;
  v20[1] = 0;
  v20[0] = v14;
  v20[2] = v15;
  std::deque<PresentEventConsumer::PresentData>::erase(a1 + 48, v21, v20, v19);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
    a1 + 136,
    &v18);
  v16 = v18;
  if ( v18 == *(struct _RTL_CRITICAL_SECTION **)(a1 + 136) )
    v16 = (struct _RTL_CRITICAL_SECTION *)*PresentEventConsumer::AddPresentConsumer((__int64 *)a1, &v18, v24);
  return (**(__int64 (__fastcall ***)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD *))v16[1].DebugInfo)(v16[1].DebugInfo, v22);
}

```

## disassembly

```asm
0x180014e64  mov     [rsp-8+arg_10], rbx
0x180014e69  push    rbp
0x180014e6a  push    rsi
0x180014e6b  push    rdi
0x180014e6c  push    r14
0x180014e6e  push    r15
0x180014e70  lea     rbp, [rsp-37h]
0x180014e75  sub     rsp, 0D0h
0x180014e7c  mov     rax, cs:__security_cookie
0x180014e83  xor     rax, rsp
0x180014e86  mov     [rbp+57h+var_30], rax
0x180014e8a  mov     r14, r8
0x180014e8d  mov     rsi, rdx
0x180014e90  mov     rdi, rcx
0x180014e93  mov     eax, [rdx+10h]
0x180014e96  sub     eax, [rcx+48h]
0x180014e99  add     [rcx+0A4h], eax
0x180014e9f  mov     rcx, rdx
0x180014ea2  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014ea7  mov     [rax+8], r14
0x180014eab  xor     edx, edx; Val
0x180014ead  lea     r8d, [rdx+50h]; Size
0x180014eb1  lea     rcx, [rbp+57h+var_80]; void *
0x180014eb5  call    memset_0
0x180014eba  mov     rcx, rsi
0x180014ebd  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014ec2  mov     rcx, [rax]
0x180014ec5  mov     [rbp+57h+var_80], rcx
0x180014ec9  mov     rcx, rsi
0x180014ecc  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014ed1  mov     rcx, [rax+8]
0x180014ed5  mov     [rbp+57h+var_78], rcx
0x180014ed9  mov     rcx, rsi
0x180014edc  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014ee1  mov     ecx, [rax+34h]
0x180014ee4  mov     [rbp+57h+var_68], ecx
0x180014ee7  mov     rcx, rsi
0x180014eea  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014eef  mov     ecx, [rax+38h]
0x180014ef2  mov     [rbp+57h+var_58], ecx
0x180014ef5  mov     rcx, rsi
0x180014ef8  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014efd  mov     ecx, [rax+3Ch]
0x180014f00  mov     [rbp+57h+var_54], ecx
0x180014f03  mov     rcx, rsi
0x180014f06  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180014f0b  mov     rcx, [rax+20h]
0x180014f0f  mov     [rbp+57h+var_60], rcx
0x180014f13  mov     rax, [rdi]
0x180014f16  mov     rcx, rdi
0x180014f19  mov     rax, [rax+58h]
0x180014f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f22  test    al, al
0x180014f24  jz      short loc_180014F8A
0x180014f26  lea     rbx, [rdi+8]
0x180014f2a  mov     rcx, rbx; lpCriticalSection
0x180014f2d  call    cs:__imp_EnterCriticalSection
0x180014f33  mov     [rbp+57h+var_D0], rbx
0x180014f37  mov     rax, [rsi]
0x180014f3a  test    rax, rax
0x180014f3d  jz      short loc_180014F44
0x180014f3f  mov     rcx, [rax]
0x180014f42  jmp     short loc_180014F46
0x180014f44  xor     ecx, ecx
0x180014f46  mov     rdx, [rsi+10h]
0x180014f4a  call    ?_Subscript@?$_Deque_val@U?$_Deque_simple_types@UPresentData@PresentEventConsumer@@@std@@@std@@QEBAAEBUPresentData@PresentEventConsumer@@_K@Z; std::_Deque_val<std::_Deque_simple_types<PresentEventConsumer::PresentData>>::_Subscript(unsigned __int64)
0x180014f4f  lea     rbx, [rdi+58h]
0x180014f53  mov     rdx, rax
0x180014f56  mov     rcx, rbx
0x180014f59  call    ?push_back@?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAAXAEBUPresentData@PresentEventConsumer@@@Z; std::deque<PresentEventConsumer::PresentData>::push_back(PresentEventConsumer::PresentData const &)
0x180014f5e  lea     r8, [r14-7A120h]
0x180014f65  jmp     short loc_180014F7A
0x180014f67  mov     rcx, rbx
0x180014f6a  call    ?front@?$queue@UPresentData@PresentEventConsumer@@V?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@@std@@QEAAAEAUPresentData@PresentEventConsumer@@XZ; std::queue<PresentEventConsumer::PresentData>::front(void)
0x180014f6f  cmp     [rax+8], r8
0x180014f73  jnb     short loc_180014F81
0x180014f75  call    ?pop_front@?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAAXXZ; std::deque<PresentEventConsumer::PresentData>::pop_front(void)
0x180014f7a  cmp     qword ptr [rdi+78h], 0
0x180014f7f  ja      short loc_180014F67
0x180014f81  lea     rcx, [rbp+57h+var_D0]
0x180014f85  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180014f8a  mov     rcx, [rsi]
0x180014f8d  mov     rdx, [rsi+10h]
0x180014f91  mov     [rbp+57h+var_C0], 0
0x180014f99  mov     [rbp+57h+var_C8], rcx
0x180014f9d  lea     rax, [rdx+1]
0x180014fa1  mov     [rbp+57h+var_B8], rax
0x180014fa5  mov     [rbp+57h+var_A8], 0
0x180014fad  mov     [rbp+57h+var_B0], rcx
0x180014fb1  mov     [rbp+57h+var_A0], rdx
0x180014fb5  lea     r9, [rbp+57h+var_C8]
0x180014fb9  lea     r8, [rbp+57h+var_B0]
0x180014fbd  lea     rdx, [rbp+57h+var_98]
0x180014fc1  lea     rcx, [rdi+30h]
0x180014fc5  call    ?erase@?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UPresentData@PresentEventConsumer@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UPresentData@PresentEventConsumer@@@std@@@std@@@2@0@Z; std::deque<PresentEventConsumer::PresentData>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<PresentEventConsumer::PresentData>>>,std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<PresentEventConsumer::PresentData>>>)
0x180014fca  lea     rbx, [rdi+88h]
0x180014fd1  lea     r8, [rbp+57h+var_60]
0x180014fd5  lea     rdx, [rbp+57h+var_D0]
0x180014fd9  mov     rcx, rbx
0x180014fdc  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x180014fe1  mov     r8, [rbp+57h+var_D0]
0x180014fe5  cmp     r8, [rbx]
0x180014fe8  jnz     short loc_180014FFD
0x180014fea  mov     r8, [rbp+57h+var_60]
0x180014fee  lea     rdx, [rbp+57h+var_D0]
0x180014ff2  mov     rcx, rdi
0x180014ff5  call    ?AddPresentConsumer@PresentEventConsumer@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@@std@@_K@Z; PresentEventConsumer::AddPresentConsumer(unsigned __int64)
0x180014ffa  mov     r8, [rax]
0x180014ffd  mov     rcx, [r8+28h]
0x180015001  mov     rax, [rcx]
0x180015004  lea     rdx, [rbp+57h+var_80]
0x180015008  mov     rax, [rax]
0x18001500b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015010  mov     rcx, [rbp+57h+var_30]
0x180015014  xor     rcx, rsp; StackCookie
0x180015017  call    __security_check_cookie
0x18001501c  mov     rbx, [rsp+0F0h+arg_10]
0x180015024  add     rsp, 0D0h
0x18001502b  pop     r15
0x18001502d  pop     r14
0x18001502f  pop     rdi
0x180015030  pop     rsi
0x180015031  pop     rbp
0x180015032  retn
```
