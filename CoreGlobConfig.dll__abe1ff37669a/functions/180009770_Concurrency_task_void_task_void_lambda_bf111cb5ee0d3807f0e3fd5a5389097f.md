# Concurrency::task_void_::task_void___lambda_bf111cb5ee0d3807f0e3fd5a5389097f___

- ea: `0x180009770`
- end: `0x1800098c9`
- name: `Concurrency::task_void_::task_void___lambda_bf111cb5ee0d3807f0e3fd5a5389097f___`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000e624`

## callees

- `0x18000288c`
- `0x180009770`
- `0x18000f958`
- `0x1800102c4`
- `0x18001030c`
- `0x18001c8bc`
- `0x18001d7a0`
- `0x18001db90`
- `0x18001dbe8`
- `0x18001dd48`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180009872`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180009872`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Concurrency::task_void_::task_void___lambda_bf111cb5ee0d3807f0e3fd5a5389097f___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r8
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdx
  Concurrency::details::_TaskCreationCallstack *v8; // rax
  char v9; // bl
  __int64 v10; // r8
  __int64 i; // rcx
  std::_Ref_count_base *v12; // rbx
  _QWORD *v13; // r9
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v16[8]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+30h] [rbp-30h]
  _BYTE v18[8]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v20; // [rsp+A0h] [rbp+40h]

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v15,
    (_QWORD *)a3);
  v17 = *(_QWORD *)(v5 + 16);
  v6 = *(volatile signed __int32 **)(v5 + 24);
  if ( v6 )
    _InterlockedIncrement(v6 + 2);
  v7 = (__int64)v6;
  if ( !v6 )
    v7 = 2;
  Concurrency::task<unsigned char>::_CreateImpl((std::_Ref_count_base **)a1, v7, &v15);
  if ( v6 )
    Concurrency::details::_RefCounter::_Release((Concurrency::details::_RefCounter *)v6);
  if ( *(_BYTE *)(a3 + 48) )
  {
    v8 = Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
           (Concurrency::details::_TaskCreationCallstack *)v18,
           (const struct Concurrency::details::_TaskCreationCallstack *)(a3 + 56));
    v9 = 1;
  }
  else
  {
    Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v15);
    v15 = v10;
    v8 = (Concurrency::details::_TaskCreationCallstack *)&v15;
    v9 = 2;
  }
  Concurrency::task<unsigned char>::_SetTaskCreationCallstack(a1, v8);
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    std::vector<void *>::_Tidy(v16);
  }
  if ( (v9 & 1) != 0 )
    std::vector<void *>::_Tidy(v19);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *(_QWORD *)a1 + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask(
    (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)a1 + 352LL),
    0);
  v12 = *(std::_Ref_count_base **)a1;
  v20 = operator new(0x20u);
  *v20 = &off_1800263C8;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v20 + 1,
    (_QWORD *)a1);
  *v13 = &off_1800263B8;
  Concurrency::details::_Task_impl_base::_ScheduleTask(v12, v13, 0);
  return a1;
}

```

## disassembly

```asm
0x180009770  mov     byte ptr [rsp-28h+arg_8], dl
0x180009774  mov     [rsp-28h+arg_0], rcx
0x180009779  push    rbp
0x18000977a  push    rbx
0x18000977b  push    rsi
0x18000977c  push    rdi
0x18000977d  push    r15
0x18000977f  mov     rbp, rsp
0x180009782  sub     rsp, 60h
0x180009786  mov     rsi, r8
0x180009789  mov     rdi, rcx
0x18000978c  mov     [rbp+arg_8], 0
0x180009793  mov     qword ptr [rcx], 0
0x18000979a  mov     qword ptr [rcx+8], 0
0x1800097a2  mov     rdx, r8
0x1800097a5  lea     rcx, [rbp+var_40]
0x1800097a9  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800097ae  mov     rcx, [r8+10h]
0x1800097b2  mov     [rbp+var_30], rcx
0x1800097b6  mov     rbx, [r8+18h]
0x1800097ba  test    rbx, rbx
0x1800097bd  jz      short loc_1800097C3
0x1800097bf  lock inc dword ptr [rbx+8]
0x1800097c3  mov     [rbp+arg_10], rbx
0x1800097c7  mov     rdx, rbx
0x1800097ca  mov     r15d, 2
0x1800097d0  test    rbx, rbx
0x1800097d3  cmovz   rdx, r15
0x1800097d7  lea     r8, [rbp+var_40]
0x1800097db  mov     rcx, rdi
0x1800097de  call    ?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<uchar>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x1800097e3  nop
0x1800097e4  test    rbx, rbx
0x1800097e7  jz      short loc_1800097F2
0x1800097e9  mov     rcx, rbx; this
0x1800097ec  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1800097f1  nop
0x1800097f2  cmp     byte ptr [rsi+30h], 0
0x1800097f6  jz      short loc_18000980D
0x1800097f8  lea     rdx, [rsi+38h]; struct Concurrency::details::_TaskCreationCallstack *
0x1800097fc  lea     rcx, [rbp+var_20]; this
0x180009800  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180009805  nop
0x180009806  mov     ebx, 1
0x18000980b  jmp     short loc_180009825
0x18000980d  mov     r8, [rbp+28h]
0x180009811  lea     rcx, [rbp+var_40]; this
0x180009815  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18000981a  mov     [rbp+var_40], r8
0x18000981e  lea     rax, [rbp+var_40]
0x180009822  mov     ebx, r15d
0x180009825  mov     [rbp+arg_8], ebx
0x180009828  mov     rdx, rax
0x18000982b  mov     rcx, rdi
0x18000982e  call    ?_SetTaskCreationCallstack@?$task@E@Concurrency@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; Concurrency::task<uchar>::_SetTaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180009833  nop
0x180009834  test    r15b, bl
0x180009837  jz      short loc_180009846
0x180009839  and     ebx, 0FFFFFFFDh
0x18000983c  lea     rcx, [rbp+var_38]
0x180009840  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180009845  nop
0x180009846  test    bl, 1
0x180009849  jz      short loc_180009854
0x18000984b  lea     rcx, [rbp+var_18]
0x18000984f  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180009854  xor     ecx, ecx
0x180009856  mov     rax, [rdi]
0x180009859  mov     byte ptr [rcx+rax+0Ch], 0
0x18000985e  inc     rcx
0x180009861  cmp     rcx, r15
0x180009864  jnz     short loc_180009856
0x180009866  mov     rcx, [rdi]
0x180009869  add     rcx, 160h
0x180009870  xor     edx, edx
0x180009872  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180009878  mov     rbx, [rdi]
0x18000987b  mov     ecx, 20h ; ' '; Size
0x180009880  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009885  mov     r9, rax
0x180009888  mov     [rbp+arg_10], rax
0x18000988c  lea     rax, off_1800263C8
0x180009893  mov     [r9], rax
0x180009896  lea     rcx, [r9+8]
0x18000989a  mov     rdx, rdi
0x18000989d  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800098a2  lea     rcx, off_1800263B8
0x1800098a9  mov     [r9], rcx
0x1800098ac  xor     r8d, r8d
0x1800098af  mov     rdx, r9
0x1800098b2  mov     rcx, rbx
0x1800098b5  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x1800098ba  nop
0x1800098bb  mov     rax, rdi
0x1800098be  add     rsp, 60h
0x1800098c2  pop     r15
0x1800098c4  pop     rdi
0x1800098c5  pop     rsi
0x1800098c6  pop     rbx
0x1800098c7  pop     rbp
0x1800098c8  retn
```
