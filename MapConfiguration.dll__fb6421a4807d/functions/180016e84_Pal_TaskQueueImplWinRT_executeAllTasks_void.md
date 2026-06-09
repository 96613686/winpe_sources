# Pal::TaskQueueImplWinRT::executeAllTasks(void)

- ea: `0x180016e84`
- end: `0x180016fc5`
- name: `?executeAllTasks@TaskQueueImplWinRT@Pal@@AEAAXXZ`
- size: `321`
- prototype: `void __fastcall(Pal::TaskQueueImplWinRT *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012f80`

## callees

- `0x18000e324`
- `0x180011f04`
- `0x180011f48`
- `0x180013da8`
- `0x180016e84`
- `0x1800188f0`
- `0x18001c1cc`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016eb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016fae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016fae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Pal::TaskQueueImplWinRT::executeAllTasks(Pal::TaskQueueImplWinRT *this)
{
  __int64 *v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rcx
  __int64 v5; // r8
  Pal::Task *v6; // rdx
  __int64 v7; // rdx
  std::_Ref_count_base *v8[2]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v9[2]; // [rsp+30h] [rbp-18h] BYREF

  while ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 80) )
  {
    *(_OWORD *)v8 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( !*((_QWORD *)this + 9) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      return;
    }
    std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(v8, **((_QWORD **)this + 8) + 16LL);
    v2 = (__int64 *)**((_QWORD **)this + 8);
    v3 = *v2;
    --*((_QWORD *)this + 9);
    *(_QWORD *)v2[1] = v3;
    *(_QWORD *)(v3 + 8) = v2[1];
    std::_List_node<std::shared_ptr<Pal::Task>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>(
      v4,
      v2);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( !v8[0] )
      goto LABEL_12;
    if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)v8[0] + 149)
      || (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 81) )
    {
      if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load(v5) )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
LABEL_12:
      if ( v8[1] )
        std::_Ref_count_base::_Decref(v8[1]);
      return;
    }
    Pal::Task::run(v6);
    *(_OWORD *)v9 = 0;
    std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(v8, v9);
    if ( v9[1] )
      std::_Ref_count_base::_Decref(v9[1]);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
  }
}

```

## disassembly

```asm
0x180016e84  mov     [rsp+arg_0], rbx
0x180016e89  mov     [rsp+arg_8], rsi
0x180016e8e  push    rdi
0x180016e8f  sub     rsp, 40h
0x180016e93  mov     rbx, rcx
0x180016e96  lea     rcx, [rbx+50h]
0x180016e9a  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180016e9f  test    al, al
0x180016ea1  jnz     loc_180016FB5
0x180016ea7  xorps   xmm0, xmm0
0x180016eaa  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180016eb0  lea     rdi, [rbx+8]
0x180016eb4  mov     rcx, rdi; lpCriticalSection
0x180016eb7  call    cs:__imp_EnterCriticalSection
0x180016ebd  cmp     qword ptr [rbx+48h], 0
0x180016ec2  jz      loc_180016FAB
0x180016ec8  mov     rax, [rbx+40h]
0x180016ecc  mov     rdx, [rax]
0x180016ecf  add     rdx, 10h
0x180016ed3  lea     rcx, [rsp+48h+var_28]
0x180016ed8  call    ??4?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>> const &)
0x180016edd  mov     rax, [rbx+40h]
0x180016ee1  mov     rdx, [rax]
0x180016ee4  mov     r8, [rdx]
0x180016ee7  dec     qword ptr [rbx+48h]
0x180016eeb  mov     rax, [rdx+8]
0x180016eef  mov     [rax], r8
0x180016ef2  mov     rax, [rdx+8]
0x180016ef6  mov     [r8+8], rax
0x180016efa  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VTask@Pal@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Pal::Task>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Pal::Task>,void *>> &,std::_List_node<std::shared_ptr<Pal::Task>,void *> *)
0x180016eff  mov     rcx, rdi; lpCriticalSection
0x180016f02  call    cs:__imp_LeaveCriticalSection
0x180016f08  mov     rdx, [rsp+48h+var_28]
0x180016f0d  test    rdx, rdx
0x180016f10  jz      loc_180016F9A
0x180016f16  lea     r8, [rdx+95h]
0x180016f1d  mov     rcx, r8
0x180016f20  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180016f25  test    al, al
0x180016f27  jnz     short loc_180016F7E
0x180016f29  lea     rcx, [rbx+51h]
0x180016f2d  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180016f32  test    al, al
0x180016f34  jnz     short loc_180016F7E
0x180016f36  mov     rcx, rdx; this
0x180016f39  call    ?run@Task@Pal@@QEAAXXZ; Pal::Task::run(void)
0x180016f3e  xorps   xmm0, xmm0
0x180016f41  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x180016f47  lea     rdx, [rsp+48h+var_18]
0x180016f4c  lea     rcx, [rsp+48h+var_28]
0x180016f51  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x180016f56  mov     rcx, [rsp+48h+var_18+8]; this
0x180016f5b  test    rcx, rcx
0x180016f5e  jz      short loc_180016F66
0x180016f60  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016f65  nop
0x180016f66  mov     rcx, [rsp+48h+var_28+8]; this
0x180016f6b  test    rcx, rcx
0x180016f6e  jz      loc_180016E96
0x180016f74  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016f79  jmp     loc_180016E96
0x180016f7e  mov     rcx, r8
0x180016f81  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180016f86  test    al, al
0x180016f88  jnz     short loc_180016F9A
0x180016f8a  mov     rax, [rdx]
0x180016f8d  mov     rcx, rdx
0x180016f90  mov     rax, [rax+8]
0x180016f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f99  nop
0x180016f9a  mov     rcx, [rsp+48h+var_28+8]; this
0x180016f9f  test    rcx, rcx
0x180016fa2  jz      short loc_180016FB5
0x180016fa4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016fa9  jmp     short loc_180016FB5
0x180016fab  mov     rcx, rdi; lpCriticalSection
0x180016fae  call    cs:__imp_LeaveCriticalSection
0x180016fb4  nop
0x180016fb5  mov     rbx, [rsp+48h+arg_0]
0x180016fba  mov     rsi, [rsp+48h+arg_8]
0x180016fbf  add     rsp, 40h
0x180016fc3  pop     rdi
0x180016fc4  retn
```
