# Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___

- ea: `0x18000e664`
- end: `0x18000e9b7`
- name: `Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000f0a8`

## callees

- `0x18000208c`
- `0x18000e664`
- `0x18000f160`
- `0x18000f5c8`
- `0x18000fd1c`
- `0x1800101d0`
- `0x180012454`
- `0x180012a20`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18000e937`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18000e937`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358___(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rsi
  __int64 v9; // r13
  _DWORD *v10; // r12
  volatile signed __int32 *v11; // r14
  volatile signed __int32 *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rax
  volatile signed __int32 *v15; // r14
  Concurrency::details::_TaskCreationCallstack *v16; // rax
  char v17; // si
  __int64 i; // rcx
  Concurrency::details::_Task_impl_base *v19; // rsi
  _QWORD *v20; // rdx
  __int64 v21; // rax
  __int128 v23; // [rsp+20h] [rbp-60h] BYREF
  __int64 v24; // [rsp+30h] [rbp-50h]
  __int128 v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+48h] [rbp-38h]
  _BYTE v27[24]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+70h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+38h]

  *a1 = 0;
  a1[1] = 0;
  v25 = 0;
  v6 = *(_QWORD *)(a3 + 8);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  *(_QWORD *)&v25 = *(_QWORD *)a3;
  v7 = *(_QWORD *)(a3 + 8);
  *((_QWORD *)&v25 + 1) = v7;
  v26 = *(_QWORD *)(a3 + 16);
  v8 = *(volatile signed __int32 **)(a3 + 24);
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 2);
    v7 = *((_QWORD *)&v25 + 1);
  }
  v9 = (__int64)v8;
  if ( !v8 )
    v9 = 2;
  *(_OWORD *)v27 = 0;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *(_OWORD *)v27 = v25;
  *(_QWORD *)&v27[16] = v26;
  v10 = operator new(0x1C8u);
  *(_QWORD *)&v23 = v10;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<Concurrency::details::_Task_impl<unsigned char>>::`vftable';
  if ( *(_QWORD *)&v27[8] )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v27[8] + 8LL));
  v23 = *(_OWORD *)v27;
  v24 = *(_QWORD *)&v27[16];
  Concurrency::details::_Task_impl<unsigned char>::_Task_impl<unsigned char>((__int64)(v10 + 4), v9, (__int64 *)&v23);
  v11 = *(volatile signed __int32 **)&v27[8];
  if ( *(_QWORD *)&v27[8] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v27[8] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *a1 = (__int64)(v10 + 4);
  v12 = (volatile signed __int32 *)a1[1];
  a1[1] = (__int64)v10;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v9 != 2 )
  {
    v13 = *a1;
    v23 = 0;
    v14 = a1[1];
    if ( v14 )
    {
      *(_QWORD *)&v23 = v13;
      *((_QWORD *)&v23 + 1) = v14;
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 12));
    }
    Concurrency::details::_Task_impl_base::_RegisterCancellation(v13, (__int64 *)&v23);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  if ( *(_BYTE *)(a3 + 48) )
  {
    v16 = Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
            (Concurrency::details::_TaskCreationCallstack *)&v25,
            (const struct Concurrency::details::_TaskCreationCallstack *)(a3 + 56));
    v17 = 13;
  }
  else
  {
    *(_OWORD *)&v27[8] = 0;
    v28 = 0;
    *(_QWORD *)v27 = retaddr;
    v16 = (Concurrency::details::_TaskCreationCallstack *)v27;
    v17 = 14;
  }
  Concurrency::details::_TaskCreationCallstack::operator=((_QWORD *)(*a1 + 320), v16);
  if ( (v17 & 2) != 0 )
  {
    v17 &= ~2u;
    std::vector<void *>::~vector<void *>((char **)&v27[8]);
  }
  if ( (v17 & 1) != 0 )
    std::vector<void *>::~vector<void *>((char **)&v25 + 1);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *a1 + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352), 0);
  v19 = (Concurrency::details::_Task_impl_base *)*a1;
  v20 = operator new(0x20u);
  *v20 = &off_18001A798;
  v20[1] = 0;
  v20[2] = 0;
  v21 = a1[1];
  if ( v21 )
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
  v20[1] = *a1;
  v20[2] = a1[1];
  *v20 = &off_18001A788;
  v20[3] = a2;
  Concurrency::details::_Task_impl_base::_ScheduleTask(v19, v20, 0);
  return a1;
}

```

## disassembly

```asm
0x18000e664  mov     [rsp-38h+arg_8], rbx
0x18000e669  mov     [rsp-38h+arg_0], rcx
0x18000e66e  push    rbp
0x18000e66f  push    rsi
0x18000e670  push    rdi
0x18000e671  push    r12
0x18000e673  push    r13
0x18000e675  push    r14
0x18000e677  push    r15
0x18000e679  mov     rbp, rsp
0x18000e67c  sub     rsp, 80h
0x18000e683  mov     r15, r8
0x18000e686  mov     rbx, rdx
0x18000e689  mov     rdi, rcx
0x18000e68c  xor     r14d, r14d
0x18000e68f  mov     dword ptr [rbp+arg_10], r14d
0x18000e693  mov     [rcx], r14
0x18000e696  mov     [rcx+8], r14
0x18000e69a  xorps   xmm0, xmm0
0x18000e69d  movdqu  [rbp+var_48], xmm0
0x18000e6a2  mov     rax, [r8+8]
0x18000e6a6  test    rax, rax
0x18000e6a9  jz      short loc_18000E6AF
0x18000e6ab  lock inc dword ptr [rax+8]
0x18000e6af  mov     rax, [r8]
0x18000e6b2  mov     qword ptr [rbp+var_48], rax
0x18000e6b6  mov     rcx, [r8+8]
0x18000e6ba  mov     qword ptr [rbp+var_48+8], rcx
0x18000e6be  mov     rax, [r8+10h]
0x18000e6c2  mov     [rbp+var_38], rax
0x18000e6c6  lea     rax, [rbp+var_48]
0x18000e6ca  mov     [rbp+arg_10], rax
0x18000e6ce  mov     rsi, [r8+18h]
0x18000e6d2  test    rsi, rsi
0x18000e6d5  jz      short loc_18000E6DF
0x18000e6d7  lock inc dword ptr [rsi+8]
0x18000e6db  mov     rcx, qword ptr [rbp+var_48+8]
0x18000e6df  mov     [rbp+arg_18], rsi
0x18000e6e3  mov     r13, rsi
0x18000e6e6  mov     eax, 2
0x18000e6eb  test    rsi, rsi
0x18000e6ee  cmovz   r13, rax
0x18000e6f2  movdqu  [rbp+var_28], xmm0
0x18000e6f7  test    rcx, rcx
0x18000e6fa  jz      short loc_18000E700
0x18000e6fc  lock inc dword ptr [rcx+8]
0x18000e700  movups  xmm0, [rbp+var_48]
0x18000e704  movups  [rbp+var_28], xmm0
0x18000e708  movsd   xmm1, [rbp+var_38]
0x18000e70d  movsd   [rbp+var_18], xmm1
0x18000e712  lea     rax, [rbp+var_28]
0x18000e716  mov     qword ptr [rbp+var_60], rax
0x18000e71a  mov     ecx, 1C8h; Size
0x18000e71f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e724  mov     r12, rax
0x18000e727  mov     qword ptr [rbp+var_60], rax
0x18000e72b  xorps   xmm0, xmm0
0x18000e72e  movups  xmmword ptr [rax], xmm0
0x18000e731  mov     dword ptr [rax+8], 1
0x18000e738  mov     dword ptr [rax+0Ch], 1
0x18000e73f  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_Task_impl<uchar>>::`vftable'
0x18000e746  mov     [r12], rax
0x18000e74a  mov     rcx, qword ptr [rbp+var_28+8]
0x18000e74e  test    rcx, rcx
0x18000e751  jz      short loc_18000E757
0x18000e753  lock inc dword ptr [rcx+8]
0x18000e757  movups  xmm0, [rbp+var_28]
0x18000e75b  movups  [rbp+var_60], xmm0
0x18000e75f  movsd   xmm1, [rbp+var_18]
0x18000e764  movsd   [rbp+var_50], xmm1
0x18000e769  lea     r8, [rbp+var_60]
0x18000e76d  mov     rdx, r13
0x18000e770  lea     rcx, [r12+10h]
0x18000e775  call    ??0?$_Task_impl@E@details@Concurrency@@QEAA@PEAV_CancellationTokenState@12@Uscheduler_ptr@2@@Z; Concurrency::details::_Task_impl<uchar>::_Task_impl<uchar>(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x18000e77a  nop
0x18000e77b  mov     r14, qword ptr [rbp+var_28+8]
0x18000e77f  test    r14, r14
0x18000e782  jz      short loc_18000E7BD
0x18000e784  or      eax, 0FFFFFFFFh
0x18000e787  lock xadd [r14+8], eax
0x18000e78d  cmp     eax, 1
0x18000e790  jnz     short loc_18000E7BD
0x18000e792  mov     rax, [r14]
0x18000e795  mov     rcx, r14
0x18000e798  mov     rax, [rax]
0x18000e79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7a0  or      eax, 0FFFFFFFFh
0x18000e7a3  lock xadd [r14+0Ch], eax
0x18000e7a9  cmp     eax, 1
0x18000e7ac  jnz     short loc_18000E7BD
0x18000e7ae  mov     rax, [r14]
0x18000e7b1  mov     rcx, r14
0x18000e7b4  mov     rax, [rax+8]
0x18000e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7bd  lea     rax, [r12+10h]
0x18000e7c2  mov     [rdi], rax
0x18000e7c5  mov     r14, [rdi+8]
0x18000e7c9  mov     [rdi+8], r12
0x18000e7cd  xor     r12d, r12d
0x18000e7d0  test    r14, r14
0x18000e7d3  jz      short loc_18000E80E
0x18000e7d5  or      eax, 0FFFFFFFFh
0x18000e7d8  lock xadd [r14+8], eax
0x18000e7de  cmp     eax, 1
0x18000e7e1  jnz     short loc_18000E80E
0x18000e7e3  mov     rax, [r14]
0x18000e7e6  mov     rcx, r14
0x18000e7e9  mov     rax, [rax]
0x18000e7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f1  or      eax, 0FFFFFFFFh
0x18000e7f4  lock xadd [r14+0Ch], eax
0x18000e7fa  cmp     eax, 1
0x18000e7fd  jnz     short loc_18000E80E
0x18000e7ff  mov     rax, [r14]
0x18000e802  mov     rcx, r14
0x18000e805  mov     rax, [rax+8]
0x18000e809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e80e  cmp     r13, 2
0x18000e812  jz      short loc_18000E83E
0x18000e814  mov     rcx, [rdi]
0x18000e817  xorps   xmm0, xmm0
0x18000e81a  movdqu  [rbp+var_60], xmm0
0x18000e81f  mov     rax, [rdi+8]
0x18000e823  test    rax, rax
0x18000e826  jz      short loc_18000E834
0x18000e828  mov     qword ptr [rbp+var_60], rcx
0x18000e82c  mov     qword ptr [rbp+var_60+8], rax
0x18000e830  lock inc dword ptr [rax+0Ch]
0x18000e834  lea     rdx, [rbp+var_60]
0x18000e838  call    ?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z; Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)
0x18000e83d  nop
0x18000e83e  mov     r14, qword ptr [rbp+var_48+8]
0x18000e842  or      r13d, 0FFFFFFFFh
0x18000e846  test    r14, r14
0x18000e849  jz      short loc_18000E885
0x18000e84b  mov     eax, r13d
0x18000e84e  lock xadd [r14+8], eax
0x18000e854  add     eax, r13d
0x18000e857  jnz     short loc_18000E885
0x18000e859  mov     rax, [r14]
0x18000e85c  mov     rcx, r14
0x18000e85f  mov     rax, [rax]
0x18000e862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e867  mov     eax, r13d
0x18000e86a  lock xadd [r14+0Ch], eax
0x18000e870  add     eax, r13d
0x18000e873  jnz     short loc_18000E885
0x18000e875  mov     rax, [r14]
0x18000e878  mov     rcx, r14
0x18000e87b  mov     rax, [rax+8]
0x18000e87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e884  nop
0x18000e885  test    rsi, rsi
0x18000e888  jz      short loc_18000E8A7
0x18000e88a  mov     eax, r13d
0x18000e88d  lock xadd [rsi+8], eax
0x18000e892  add     eax, r13d
0x18000e895  jnz     short loc_18000E8A7
0x18000e897  mov     rax, [rsi]
0x18000e89a  mov     rcx, rsi
0x18000e89d  mov     rax, [rax+8]
0x18000e8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a6  nop
0x18000e8a7  cmp     [r15+30h], r12b
0x18000e8ab  jz      short loc_18000E8C2
0x18000e8ad  lea     rdx, [r15+38h]; struct Concurrency::details::_TaskCreationCallstack *
0x18000e8b1  lea     rcx, [rbp+var_48]; this
0x18000e8b5  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18000e8ba  nop
0x18000e8bb  mov     esi, 0Dh
0x18000e8c0  jmp     short loc_18000E8DF
0x18000e8c2  mov     rax, [rbp+38h]
0x18000e8c6  xorps   xmm0, xmm0
0x18000e8c9  movdqu  [rbp+var_28+8], xmm0
0x18000e8ce  mov     [rbp+var_10], r12
0x18000e8d2  mov     qword ptr [rbp+var_28], rax
0x18000e8d6  lea     rax, [rbp+var_28]
0x18000e8da  mov     esi, 0Eh
0x18000e8df  mov     dword ptr [rbp+arg_10], esi
0x18000e8e2  mov     rcx, [rdi]
0x18000e8e5  add     rcx, 140h
0x18000e8ec  mov     rdx, rax
0x18000e8ef  call    ??4_TaskCreationCallstack@details@Concurrency@@QEAAAEAV012@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::operator=(Concurrency::details::_TaskCreationCallstack const &)
0x18000e8f4  nop
0x18000e8f5  test    sil, 2
0x18000e8f9  jz      short loc_18000E908
0x18000e8fb  and     esi, 0FFFFFFFDh
0x18000e8fe  lea     rcx, [rbp+var_28+8]
0x18000e902  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18000e907  nop
0x18000e908  test    sil, 1
0x18000e90c  jz      short loc_18000E917
0x18000e90e  lea     rcx, [rbp+var_48+8]
0x18000e912  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18000e917  mov     rcx, r12
0x18000e91a  mov     rax, [rdi]
0x18000e91d  mov     [rcx+rax+0Ch], r12b
0x18000e922  inc     rcx
0x18000e925  cmp     rcx, 2
0x18000e929  jnz     short loc_18000E91A
0x18000e92b  mov     rcx, [rdi]
0x18000e92e  add     rcx, 160h
0x18000e935  xor     edx, edx
0x18000e937  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18000e93d  mov     rsi, [rdi]
0x18000e940  mov     ecx, 20h ; ' '; Size
0x18000e945  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e94a  mov     rdx, rax
0x18000e94d  mov     [rbp+arg_10], rax
0x18000e951  lea     rax, off_18001A798
0x18000e958  mov     [rdx], rax
0x18000e95b  mov     [rdx+8], r12
0x18000e95f  mov     [rdx+10h], r12
0x18000e963  mov     rax, [rdi+8]
0x18000e967  test    rax, rax
0x18000e96a  jz      short loc_18000E970
0x18000e96c  lock inc dword ptr [rax+8]
0x18000e970  mov     rax, [rdi]
0x18000e973  mov     [rdx+8], rax
0x18000e977  mov     rax, [rdi+8]
0x18000e97b  mov     [rdx+10h], rax
0x18000e97f  lea     rax, off_18001A788
0x18000e986  mov     [rdx], rax
0x18000e989  mov     [rdx+18h], rbx
0x18000e98d  xor     r8d, r8d
0x18000e990  mov     rcx, rsi
0x18000e993  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18000e998  nop
0x18000e999  mov     rax, rdi
0x18000e99c  mov     rbx, [rsp+80h+arg_8]
0x18000e9a4  add     rsp, 80h
0x18000e9ab  pop     r15
0x18000e9ad  pop     r14
0x18000e9af  pop     r13
0x18000e9b1  pop     r12
0x18000e9b3  pop     rdi
0x18000e9b4  pop     rsi
0x18000e9b5  pop     rbp
0x18000e9b6  retn
```
