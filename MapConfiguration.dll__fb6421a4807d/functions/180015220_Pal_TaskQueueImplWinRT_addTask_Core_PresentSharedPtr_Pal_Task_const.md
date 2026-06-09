# Pal::TaskQueueImplWinRT::addTask(Core::PresentSharedPtr<Pal::Task> const &)

- ea: `0x180015220`
- end: `0x18001533d`
- name: `?addTask@TaskQueueImplWinRT@Pal@@UEAA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@Core@@AEBV?$PresentSharedPtr@VTask@Pal@@@4@@Z`
- size: `285`
- prototype: `__int64 __fastcall(Pal::TaskQueueImplWinRT *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b7fc`
- `0x18000cf40`
- `0x18000f1f0`
- `0x1800111d4`
- `0x180015220`
- `0x1800163c4`
- `0x1800188f0`
- `0x180019c08`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001529a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001529a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015311`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015311`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Pal::TaskQueueImplWinRT::addTask(Pal::TaskQueueImplWinRT *this, __int64 a2, __int64 *a3)
{
  bool v6; // r15
  __int64 v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  _QWORD *v11; // r9
  char *v13; // [rsp+28h] [rbp-40h] BYREF
  __int64 v14; // [rsp+30h] [rbp-38h]

  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 81) )
  {
    Pal::AsyncOperation<Core::DummyType>::createCancelled(a2);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v6 = *((_DWORD *)this + 24) == 1 || !*((_QWORD *)this + 7) && !*((_QWORD *)this + 9);
    if ( *((_QWORD *)this + 9) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("list too long");
    v13 = (char *)this + 64;
    v14 = 0;
    v7 = *((_QWORD *)this + 8);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>::construct<std::shared_ptr<Pal::Task>,std::shared_ptr<Pal::Task> const &>(
      v9,
      (__int64)(v8 + 2),
      (__int64)a3);
    ++*((_QWORD *)this + 9);
    v10 = *(_QWORD **)(v7 + 8);
    *v11 = v7;
    v11[1] = v10;
    v14 = 0;
    *(_QWORD *)(v7 + 8) = v11;
    *v10 = v11;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>((__int64)&v13);
    if ( v6 )
      Pal::TaskQueueImplWinRT::start(this);
    Core::PresentSharedPtr<Pal::Task>::operator<Pal::AsyncOperation<Core::DummyType>,void> Core::PresentSharedPtr<Pal::AsyncOperation<Core::DummyType>>(
      a3,
      a2);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
  return a2;
}

```

## disassembly

```asm
0x180015220  mov     [rsp+arg_8], rbx
0x180015225  mov     [rsp+arg_10], rbp
0x18001522a  push    rsi
0x18001522b  push    rdi
0x18001522c  push    r12
0x18001522e  push    r14
0x180015230  push    r15
0x180015232  sub     rsp, 40h
0x180015236  mov     r12, r8
0x180015239  mov     rsi, rdx
0x18001523c  mov     rdi, rcx
0x18001523f  add     rcx, 51h ; 'Q'
0x180015243  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180015248  test    al, al
0x18001524a  jnz     loc_180015319
0x180015250  lea     rbp, [rdi+8]
0x180015254  mov     [rsp+68h+arg_0], rbp
0x180015259  mov     rcx, rbp; lpCriticalSection
0x18001525c  call    cs:__imp_EnterCriticalSection
0x180015262  nop
0x180015263  cmp     dword ptr [rdi+60h], 1
0x180015267  jz      short loc_18001527C
0x180015269  cmp     qword ptr [rdi+38h], 0
0x18001526e  jnz     short loc_180015277
0x180015270  cmp     qword ptr [rdi+48h], 0
0x180015275  jz      short loc_18001527C
0x180015277  xor     r15b, r15b
0x18001527a  jmp     short loc_18001527F
0x18001527c  mov     r15b, 1
0x18001527f  lea     r14, [rdi+40h]
0x180015283  mov     rax, 7FFFFFFFFFFFFFFh
0x18001528d  cmp     [r14+8], rax
0x180015291  jnz     short loc_1800152A1
0x180015293  lea     rcx, aListTooLong; "list too long"
0x18001529a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800152a1  mov     [rsp+68h+var_40], r14
0x1800152a6  mov     [rsp+68h+var_38], 0
0x1800152af  mov     rbx, [r14]
0x1800152b2  mov     ecx, 20h ; ' '
0x1800152b7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800152bc  mov     r9, rax
0x1800152bf  lea     rdx, [rax+10h]
0x1800152c3  mov     r8, r12
0x1800152c6  call    ??$construct@V?$shared_ptr@VTask@Pal@@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@1@QEAV?$shared_ptr@VTask@Pal@@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>::construct<std::shared_ptr<Pal::Task>,std::shared_ptr<Pal::Task> const &>(std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>> &,std::shared_ptr<Pal::Task> * const,std::shared_ptr<Pal::Task> const &)
0x1800152cb  nop
0x1800152cc  inc     qword ptr [r14+8]
0x1800152d0  mov     rdx, [rbx+8]
0x1800152d4  mov     [r9], rbx
0x1800152d7  mov     [r9+8], rdx
0x1800152db  mov     [rsp+68h+var_38], 0
0x1800152e4  mov     [rbx+8], r9
0x1800152e8  mov     [rdx], r9
0x1800152eb  lea     rcx, [rsp+68h+var_40]
0x1800152f0  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>(void)
0x1800152f5  test    r15b, r15b
0x1800152f8  jz      short loc_180015302
0x1800152fa  mov     rcx, rdi; this
0x1800152fd  call    ?start@TaskQueueImplWinRT@Pal@@AEAA_NXZ; Pal::TaskQueueImplWinRT::start(void)
0x180015302  mov     rdx, rsi
0x180015305  mov     rcx, r12
0x180015308  call    ??$?BV?$AsyncOperation@UDummyType@Core@@@Pal@@X@?$PresentSharedPtr@VTask@Pal@@@Core@@QEBA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@1@XZ; Core::PresentSharedPtr<Pal::Task>::operator<Pal::AsyncOperation<Core::DummyType>,void> Core::PresentSharedPtr<Pal::AsyncOperation<Core::DummyType>>(void)
0x18001530d  nop
0x18001530e  mov     rcx, rbp; lpCriticalSection
0x180015311  call    cs:__imp_LeaveCriticalSection
0x180015317  jmp     short loc_180015321
0x180015319  mov     rcx, rsi
0x18001531c  call    ?createCancelled@?$AsyncOperation@UDummyType@Core@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@Core@@XZ; Pal::AsyncOperation<Core::DummyType>::createCancelled(void)
0x180015321  mov     rax, rsi
0x180015324  lea     r11, [rsp+68h+var_28]
0x180015329  mov     rbx, [r11+38h]
0x18001532d  mov     rbp, [r11+40h]
0x180015331  mov     rsp, r11
0x180015334  pop     r15
0x180015336  pop     r14
0x180015338  pop     r12
0x18001533a  pop     rdi
0x18001533b  pop     rsi
0x18001533c  retn
```
