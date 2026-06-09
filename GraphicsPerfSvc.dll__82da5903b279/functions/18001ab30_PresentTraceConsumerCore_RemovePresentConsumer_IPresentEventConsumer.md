# PresentTraceConsumerCore::RemovePresentConsumer(IPresentEventConsumer *)

- ea: `0x18001ab30`
- end: `0x18001ac8c`
- name: `?RemovePresentConsumer@PresentTraceConsumerCore@@UEAA_KPEAUIPresentEventConsumer@@@Z`
- size: `348`
- prototype: `unsigned __int64 __fastcall(PresentTraceConsumerCore *__hidden this, struct IPresentEventConsumer *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180005c6c`
- `0x18000d67c`
- `0x18000fbbc`
- `0x180016ab0`
- `0x180018810`
- `0x18001ab30`
- `0x18001b5cc`
- `0x18002d30c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ab56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PresentTraceConsumerCore::RemovePresentConsumer(
        PresentTraceConsumerCore *this,
        struct IPresentEventConsumer *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 *v5; // r9
  __int64 v6; // rbx
  __int64 *v7; // rdi
  __int64 *v8; // r15
  __int64 *v9; // rsi
  __int64 *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rdx
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rcx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v23; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+60h] [rbp+18h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 160);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
  v24 = v4;
  v5 = (__int64 *)*((_QWORD *)this + 25);
  v6 = *v5;
  v23 = *v5;
LABEL_2:
  if ( (__int64 *)v6 != v5 )
  {
    v7 = *(__int64 **)(v6 + 56);
    v8 = *(__int64 **)(v6 + 64);
    while ( 1 )
    {
      if ( v7 == v8 )
      {
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(&v23);
        v6 = v23;
        goto LABEL_2;
      }
      v9 = v7 + 2;
      if ( (struct IPresentEventConsumer *)*v7 == a2 )
        break;
      v7 += 2;
    }
    v10 = v7;
    while ( v9 != v8 )
    {
      v11 = *v9;
      v12 = v9[1];
      *v9 = 0;
      v9[1] = 0;
      *v10 = v11;
      v13 = (std::_Ref_count_base *)v10[1];
      v10[1] = v12;
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      v10 += 2;
      v9 += 2;
    }
    v14 = *(std::_Ref_count_base **)(*(_QWORD *)(v6 + 64) - 8LL);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    *(_QWORD *)(v6 + 64) -= 16LL;
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*v7 + 152LL))(*v7);
    --*((_DWORD *)this + v15 + 81);
    if ( *(_QWORD *)(v6 + 64) == *(_QWORD *)(v6 + 56) )
    {
      v16 = *(_DWORD *)(v6 + 32);
      v17 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>::_Extract((char *)this + 200);
      std::_Tree_node<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>,void *>>>(
        v18,
        v17);
      --*((_DWORD *)this + 97);
      LOBYTE(v19) = 3;
      LOBYTE(v20) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
        v20,
        v19);
      PMTraceConsumer::RemoveTrackedProcessForFiltering(*((PMTraceConsumer **)this + 33), v16);
    }
  }
  v21 = *((_QWORD *)this + 26);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
  return v21;
}

```

## disassembly

```asm
0x18001ab30  mov     [rsp+arg_8], rbx
0x18001ab35  mov     [rsp+arg_18], rbp
0x18001ab3a  push    rsi
0x18001ab3b  push    rdi
0x18001ab3c  push    r12
0x18001ab3e  push    r14
0x18001ab40  push    r15
0x18001ab42  sub     rsp, 20h
0x18001ab46  mov     r14, rdx
0x18001ab49  mov     rbp, rcx
0x18001ab4c  lea     rbx, [rcx+0A0h]
0x18001ab53  mov     rcx, rbx; lpCriticalSection
0x18001ab56  call    cs:__imp_EnterCriticalSection
0x18001ab5c  mov     [rsp+48h+arg_10], rbx
0x18001ab61  lea     r12, [rbp+0C8h]
0x18001ab68  mov     r9, [r12]
0x18001ab6c  mov     rbx, [r9]
0x18001ab6f  mov     [rsp+48h+arg_0], rbx
0x18001ab74  cmp     rbx, r9
0x18001ab77  jz      loc_18001AC61
0x18001ab7d  mov     rdi, [rbx+38h]
0x18001ab81  mov     r15, [rbx+40h]
0x18001ab85  cmp     rdi, r15
0x18001ab88  jz      short loc_18001AB98
0x18001ab8a  lea     rsi, [rdi+10h]
0x18001ab8e  cmp     [rdi], r14
0x18001ab91  jz      short loc_18001ABA9
0x18001ab93  mov     rdi, rsi
0x18001ab96  jmp     short loc_18001AB85
0x18001ab98  lea     rcx, [rsp+48h+arg_0]
0x18001ab9d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x18001aba2  mov     rbx, [rsp+48h+arg_0]
0x18001aba7  jmp     short loc_18001AB74
0x18001aba9  mov     r14, rdi
0x18001abac  jmp     short loc_18001ABE1
0x18001abae  mov     rax, [rsi]
0x18001abb1  mov     rdx, [rsi+8]
0x18001abb5  mov     qword ptr [rsi], 0
0x18001abbc  mov     qword ptr [rsi+8], 0
0x18001abc4  mov     [r14], rax
0x18001abc7  mov     rcx, [r14+8]; this
0x18001abcb  mov     [r14+8], rdx
0x18001abcf  test    rcx, rcx
0x18001abd2  jz      short loc_18001ABD9
0x18001abd4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001abd9  add     r14, 10h
0x18001abdd  add     rsi, 10h
0x18001abe1  cmp     rsi, r15
0x18001abe4  jnz     short loc_18001ABAE
0x18001abe6  mov     rax, [rbx+40h]
0x18001abea  mov     rcx, [rax-8]; this
0x18001abee  test    rcx, rcx
0x18001abf1  jz      short loc_18001ABF8
0x18001abf3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001abf8  add     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFF0h
0x18001abfd  mov     rcx, [rdi]
0x18001ac00  mov     rax, [rcx]
0x18001ac03  mov     rax, [rax+98h]
0x18001ac0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac0f  movsxd  rdx, eax
0x18001ac12  or      esi, 0FFFFFFFFh
0x18001ac15  add     [rbp+rdx*4+144h], esi
0x18001ac1c  mov     rax, [rbx+40h]
0x18001ac20  cmp     rax, [rbx+38h]
0x18001ac24  jnz     short loc_18001AC61
0x18001ac26  mov     edi, [rbx+20h]
0x18001ac29  mov     rdx, rbx
0x18001ac2c  mov     rcx, r12
0x18001ac2f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>,std::_Iterator_base0>)
0x18001ac34  mov     rdx, rax
0x18001ac37  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>,void *>> &,std::_Tree_node<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>,void *> *)
0x18001ac3c  add     [rbp+184h], esi
0x18001ac42  mov     r8b, 3
0x18001ac45  mov     dl, 1
0x18001ac47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x18001ac4e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ac53  mov     edx, edi; unsigned int
0x18001ac55  mov     rcx, [rbp+108h]; this
0x18001ac5c  call    ?RemoveTrackedProcessForFiltering@PMTraceConsumer@@QEAAXI@Z; PMTraceConsumer::RemoveTrackedProcessForFiltering(uint)
0x18001ac61  mov     rbx, [rbp+0D0h]
0x18001ac68  lea     rcx, [rsp+48h+arg_10]
0x18001ac6d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001ac72  mov     rax, rbx
0x18001ac75  mov     rbx, [rsp+48h+arg_8]
0x18001ac7a  mov     rbp, [rsp+48h+arg_18]
0x18001ac7f  add     rsp, 20h
0x18001ac83  pop     r15
0x18001ac85  pop     r14
0x18001ac87  pop     r12
0x18001ac89  pop     rdi
0x18001ac8a  pop     rsi
0x18001ac8b  retn
```
