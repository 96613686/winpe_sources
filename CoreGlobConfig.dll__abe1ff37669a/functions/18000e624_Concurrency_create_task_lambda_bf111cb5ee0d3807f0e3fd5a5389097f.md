# Concurrency::create_task__lambda_bf111cb5ee0d3807f0e3fd5a5389097f___

- ea: `0x18000e624`
- end: `0x18000e6a7`
- name: `Concurrency::create_task__lambda_bf111cb5ee0d3807f0e3fd5a5389097f___`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001b34c`

## callees

- `0x180009770`
- `0x18000c4f4`
- `0x18000e624`
- `0x18001030c`
- `0x1800120a4`
- `0x18001dd48`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::create_task__lambda_bf111cb5ee0d3807f0e3fd5a5389097f___(
        __int64 a1,
        __int64 a2,
        Concurrency::task_options *a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v9; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v10[5]; // [rsp+30h] [rbp-28h] BYREF

  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v9);
  v9 = v6;
  *(_BYTE *)(v5 + 48) = 1;
  *(_QWORD *)(v5 + 56) = v6;
  if ( (_QWORD *)(v5 + 64) != v10 )
    std::vector<void *>::_Assign_counted_range<void * *>(v5 + 64, v10[0], (__int64)(v10[1] - v10[0]) >> 3);
  std::vector<void *>::_Tidy(v10);
  Concurrency::task_void_::task_void___lambda_bf111cb5ee0d3807f0e3fd5a5389097f___(a1, v7, (__int64)a3);
  Concurrency::task_options::~task_options(a3);
  return a1;
}

```

## disassembly

```asm
0x18000e624  mov     [rsp+arg_0], rbx
0x18000e629  mov     [rsp+arg_10], r8
0x18000e62e  push    rdi
0x18000e62f  sub     rsp, 50h
0x18000e633  mov     rbx, r8
0x18000e636  mov     rdi, rcx
0x18000e639  mov     r9, [rsp+58h]
0x18000e63e  lea     rcx, [rsp+58h+var_30]; this
0x18000e643  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18000e648  mov     [rsp+58h+var_30], r9
0x18000e64d  mov     byte ptr [r8+30h], 1
0x18000e652  mov     [r8+38h], r9
0x18000e656  lea     rcx, [r8+40h]
0x18000e65a  lea     rax, [rsp+58h+var_28]
0x18000e65f  cmp     rcx, rax
0x18000e662  jz      short loc_18000E67B
0x18000e664  mov     rdx, [rsp+58h+var_28]
0x18000e669  mov     r8, [rsp+58h+var_20]
0x18000e66e  sub     r8, rdx
0x18000e671  sar     r8, 3
0x18000e675  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x18000e67a  nop
0x18000e67b  lea     rcx, [rsp+58h+var_28]
0x18000e680  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18000e685  mov     r8, rbx
0x18000e688  mov     rcx, rdi
0x18000e68b  call    Concurrency__task_void___task_void___lambda_bf111cb5ee0d3807f0e3fd5a5389097f___
0x18000e690  nop
0x18000e691  mov     rcx, rbx; this
0x18000e694  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x18000e699  mov     rax, rdi
0x18000e69c  mov     rbx, [rsp+58h+arg_0]
0x18000e6a1  add     rsp, 50h
0x18000e6a5  pop     rdi
0x18000e6a6  retn
```
