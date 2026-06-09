# std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2_____

- ea: `0x18000eab0`
- end: `0x18000ec1f`
- name: `std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2_____`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180010fc0`

## callees

- `0x18000e9c0`
- `0x18000eab0`
- `0x18000f0a8`
- `0x180012e78`
- `0x180019010`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18000eb29`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18000eb29`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2_____(
        __int64 a1)
{
  __int64 *v2; // rsi
  __int64 *ambient_scheduler; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 *task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  _BYTE v13[8]; // [rsp+20h] [rbp-39h] BYREF
  volatile signed __int32 *v14; // [rsp+28h] [rbp-31h]
  _QWORD v15[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int128 v18; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+80h] [rbp+27h]
  __int16 v20; // [rsp+88h] [rbp+2Fh]

  std::_Packaged_state_void___cdecl_void__::_Packaged_state_void___cdecl_void___std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____0_();
  *(_QWORD *)a1 = &std::_Task_async_state<void>::`vftable';
  v2 = (__int64 *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  ambient_scheduler = (__int64 *)Concurrency::get_ambient_scheduler();
  v4 = ambient_scheduler[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v5 = *ambient_scheduler;
  v6 = ambient_scheduler[1];
  v15[0] = v5;
  v15[1] = v6;
  v15[2] = v5;
  v15[3] = 0;
  Concurrency::task_continuation_context::task_continuation_context((Concurrency::task_continuation_context *)v16);
  v18 = 0;
  v19 = 0;
  v17 = 0;
  v16[16] = 0;
  v20 = 0;
  task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358 = (__int64 *)Concurrency::create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___(
                                                               v13,
                                                               a1,
                                                               v15);
  if ( v2 != task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358 )
  {
    v8 = *task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358;
    v9 = task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358[1];
    *task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358 = 0;
    task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358[1] = 0;
    *v2 = v8;
    v10 = *(volatile signed __int32 **)(a1 + 280);
    *(_QWORD *)(a1 + 280) = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
  v11 = v14;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *(_BYTE *)(a1 + 194) = 1;
  return a1;
}

```

## disassembly

```asm
0x18000eab0  mov     [rsp-8+arg_0], rcx
0x18000eab5  push    rbp
0x18000eab6  push    rbx
0x18000eab7  push    rsi
0x18000eab8  push    rdi
0x18000eab9  push    r14
0x18000eabb  lea     rbp, [rsp-37h]
0x18000eac0  sub     rsp, 90h
0x18000eac7  mov     rdi, rcx
0x18000eaca  call    std___Packaged_state_void___cdecl_void_____Packaged_state_void___cdecl_void___std___Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____0_
0x18000eacf  nop
0x18000ead0  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x18000ead7  mov     [rdi], rax
0x18000eada  lea     rsi, [rdi+110h]
0x18000eae1  mov     qword ptr [rsi], 0
0x18000eae8  mov     qword ptr [rsi+8], 0
0x18000eaf0  lea     rax, [rbp+57h+var_80]
0x18000eaf4  mov     [rbp+57h+arg_10], rax
0x18000eaf8  call    ?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ; Concurrency::get_ambient_scheduler(void)
0x18000eafd  mov     rcx, [rax+8]
0x18000eb01  test    rcx, rcx
0x18000eb04  jz      short loc_18000EB0A
0x18000eb06  lock inc dword ptr [rcx+8]
0x18000eb0a  mov     rcx, [rax]
0x18000eb0d  mov     rax, [rax+8]
0x18000eb11  mov     [rbp+57h+var_80], rcx
0x18000eb15  mov     [rbp+57h+var_78], rax
0x18000eb19  mov     [rbp+57h+var_70], rcx
0x18000eb1d  mov     [rbp+57h+var_68], 0
0x18000eb25  lea     rcx, [rbp+57h+var_60]
0x18000eb29  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18000eb2f  xorps   xmm0, xmm0
0x18000eb32  movdqu  [rbp+57h+var_40], xmm0
0x18000eb37  mov     [rbp+57h+var_30], 0
0x18000eb3f  mov     [rbp+57h+var_48], 0
0x18000eb47  mov     [rbp+57h+var_50], 0
0x18000eb4b  mov     [rbp+57h+var_28], 0
0x18000eb51  lea     r8, [rbp+57h+var_80]
0x18000eb55  mov     rdx, rdi
0x18000eb58  lea     rcx, [rbp+57h+var_90]
0x18000eb5c  call    Concurrency__create_task__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___
0x18000eb61  or      r14d, 0FFFFFFFFh
0x18000eb65  cmp     rsi, rax
0x18000eb68  jz      short loc_18000EBC7
0x18000eb6a  mov     rcx, [rax]
0x18000eb6d  mov     rdx, [rax+8]
0x18000eb71  mov     qword ptr [rax], 0
0x18000eb78  mov     qword ptr [rax+8], 0
0x18000eb80  mov     [rsi], rcx
0x18000eb83  mov     rbx, [rsi+8]
0x18000eb87  mov     [rsi+8], rdx
0x18000eb8b  test    rbx, rbx
0x18000eb8e  jz      short loc_18000EBC7
0x18000eb90  mov     eax, r14d
0x18000eb93  lock xadd [rbx+8], eax
0x18000eb98  add     eax, r14d
0x18000eb9b  jnz     short loc_18000EBC7
0x18000eb9d  mov     rax, [rbx]
0x18000eba0  mov     rcx, rbx
0x18000eba3  mov     rax, [rax]
0x18000eba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebab  mov     eax, r14d
0x18000ebae  lock xadd [rbx+0Ch], eax
0x18000ebb3  add     eax, r14d
0x18000ebb6  jnz     short loc_18000EBC7
0x18000ebb8  mov     rax, [rbx]
0x18000ebbb  mov     rcx, rbx
0x18000ebbe  mov     rax, [rax+8]
0x18000ebc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebc7  mov     rbx, [rbp+57h+var_88]
0x18000ebcb  test    rbx, rbx
0x18000ebce  jz      short loc_18000EC07
0x18000ebd0  mov     eax, r14d
0x18000ebd3  lock xadd [rbx+8], eax
0x18000ebd8  add     eax, r14d
0x18000ebdb  jnz     short loc_18000EC07
0x18000ebdd  mov     rax, [rbx]
0x18000ebe0  mov     rcx, rbx
0x18000ebe3  mov     rax, [rax]
0x18000ebe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebeb  mov     eax, r14d
0x18000ebee  lock xadd [rbx+0Ch], eax
0x18000ebf3  add     eax, r14d
0x18000ebf6  jnz     short loc_18000EC07
0x18000ebf8  mov     rax, [rbx]
0x18000ebfb  mov     rcx, rbx
0x18000ebfe  mov     rax, [rax+8]
0x18000ec02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec07  mov     byte ptr [rdi+0C2h], 1
0x18000ec0e  mov     rax, rdi
0x18000ec11  add     rsp, 90h
0x18000ec18  pop     r14
0x18000ec1a  pop     rdi
0x18000ec1b  pop     rsi
0x18000ec1c  pop     rbx
0x18000ec1d  pop     rbp
0x18000ec1e  retn
```
