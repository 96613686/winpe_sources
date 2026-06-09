# Concurrency::task_void_::task_void___lambda_b491893a6046e26d34a6ad5978ce944a___

- ea: `0x1400129fc`
- end: `0x140012bda`
- name: `Concurrency::task_void_::task_void___lambda_b491893a6046e26d34a6ad5978ce944a___`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x14001c760`

## callees

- `0x1400017a0`
- `0x1400039b6`
- `0x1400129fc`
- `0x140012fdc`
- `0x140013af4`
- `0x14001471c`
- `0x14001b758`
- `0x14001d290`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *__fastcall Concurrency::task_void_::task_void___lambda_b491893a6046e26d34a6ad5978ce944a___(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  volatile signed __int32 *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  __int64 v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+30h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+28h]

  *a1 = 0;
  a1[1] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::_Resetp<Concurrency::details::_Task_impl<unsigned char>>(a1);
  lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(&string, a2);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  WindowsDeleteString_0(string);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &string,
    a3);
  v15 = a3[2];
  v6 = (volatile signed __int32 *)a3[3];
  if ( v6 )
    _InterlockedIncrement(v6 + 2);
  v7 = (__int64)v6;
  if ( !v6 )
    v7 = 2;
  Concurrency::task<unsigned char>::_CreateImpl(a1, v7, &string);
  if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  *(_QWORD *)(*a1 + 152) = retaddr;
  lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(&string, a2);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  WindowsDeleteString_0(string);
  *(_BYTE *)(*a1 + 20) = 0;
  *(_BYTE *)(*a1 + 22) = 0;
  v8 = *a1;
  v9 = operator new(0x40u);
  if ( v9 )
  {
    *v9 = off_1400494B8;
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v9 + 3,
      a1);
    v9[1] = pplx::details::_UnrealizedChore::_InvokeBridge_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync__pplx::details::_UnrealizedChore___;
    *((_BYTE *)v9 + 16) = 1;
    *v9 = off_1400494B0;
    lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(v9 + 5, a2);
  }
  else
  {
    v9 = 0;
  }
  Concurrency::details::_Task_impl_base::_ScheduleTask(v8, v9, 0);
  v10 = *(_QWORD *)(a2 + 16);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *(_QWORD *)(a2 + 8);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  WindowsDeleteString_0(*(HSTRING *)a2);
  return a1;
}

```

## disassembly

```asm
0x1400129fc  mov     [rsp-28h+arg_8], rdx
0x140012a01  mov     [rsp-28h+arg_0], rcx
0x140012a06  push    rbp
0x140012a07  push    rbx
0x140012a08  push    rsi
0x140012a09  push    rdi
0x140012a0a  push    r14
0x140012a0c  mov     rbp, rsp
0x140012a0f  sub     rsp, 40h
0x140012a13  mov     rsi, r8
0x140012a16  mov     r14, rdx
0x140012a19  mov     rbx, rcx
0x140012a1c  mov     qword ptr [rcx], 0
0x140012a23  mov     qword ptr [rcx+8], 0
0x140012a2b  call    ??$_Resetp@U?$_Task_impl@E@details@Concurrency@@@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@AEAAXPEAU?$_Task_impl@E@details@Concurrency@@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::_Resetp<Concurrency::details::_Task_impl<uchar>>(Concurrency::details::_Task_impl<uchar> *)
0x140012a30  nop
0x140012a31  mov     rdx, r14
0x140012a34  lea     rcx, [rbp+string]
0x140012a38  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x140012a3d  nop
0x140012a3e  mov     rcx, [rbp+var_10]
0x140012a42  test    rcx, rcx
0x140012a45  jz      short loc_140012A53
0x140012a47  mov     rax, [rcx]
0x140012a4a  mov     rax, [rax+10h]
0x140012a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a53  mov     rcx, [rbp+var_18]
0x140012a57  test    rcx, rcx
0x140012a5a  jz      short loc_140012A68
0x140012a5c  mov     rax, [rcx]
0x140012a5f  mov     rax, [rax+10h]
0x140012a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a68  mov     rcx, [rbp+string]; string
0x140012a6c  call    WindowsDeleteString_0
0x140012a71  nop
0x140012a72  mov     rdx, rsi
0x140012a75  lea     rcx, [rbp+string]
0x140012a79  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140012a7e  mov     rax, [rsi+10h]
0x140012a82  mov     [rbp+var_10], rax
0x140012a86  mov     rsi, [rsi+18h]
0x140012a8a  test    rsi, rsi
0x140012a8d  jz      short loc_140012A93
0x140012a8f  lock inc dword ptr [rsi+8]
0x140012a93  mov     [rbp+arg_10], rsi
0x140012a97  mov     rdx, rsi
0x140012a9a  mov     eax, 2
0x140012a9f  test    rsi, rsi
0x140012aa2  cmovz   rdx, rax
0x140012aa6  lea     r8, [rbp+string]
0x140012aaa  mov     rcx, rbx
0x140012aad  call    ?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@pplx@@Uscheduler_ptr@2@@Z; Concurrency::task<uchar>::_CreateImpl(pplx::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x140012ab2  nop
0x140012ab3  test    rsi, rsi
0x140012ab6  jz      short loc_140012AD5
0x140012ab8  or      eax, 0FFFFFFFFh
0x140012abb  lock xadd [rsi+8], eax
0x140012ac0  cmp     eax, 1
0x140012ac3  jnz     short loc_140012AD5
0x140012ac5  mov     rax, [rsi]
0x140012ac8  mov     rcx, rsi
0x140012acb  mov     rax, [rax+8]
0x140012acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ad4  nop
0x140012ad5  mov     rcx, [rbp+28h]
0x140012ad9  mov     rax, [rbx]
0x140012adc  mov     [rax+98h], rcx
0x140012ae3  mov     rdx, r14
0x140012ae6  lea     rcx, [rbp+string]
0x140012aea  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x140012aef  nop
0x140012af0  mov     rcx, [rbp+var_10]
0x140012af4  test    rcx, rcx
0x140012af7  jz      short loc_140012B05
0x140012af9  mov     rax, [rcx]
0x140012afc  mov     rax, [rax+10h]
0x140012b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b05  mov     rcx, [rbp+var_18]
0x140012b09  test    rcx, rcx
0x140012b0c  jz      short loc_140012B1A
0x140012b0e  mov     rax, [rcx]
0x140012b11  mov     rax, [rax+10h]
0x140012b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b1a  mov     rcx, [rbp+string]; string
0x140012b1e  call    WindowsDeleteString_0
0x140012b23  nop
0x140012b24  mov     rax, [rbx]
0x140012b27  mov     byte ptr [rax+14h], 0
0x140012b2b  mov     rax, [rbx]
0x140012b2e  mov     byte ptr [rax+16h], 0
0x140012b32  mov     rsi, [rbx]
0x140012b35  mov     ecx, 40h ; '@'; Size
0x140012b3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012b3f  mov     rdi, rax
0x140012b42  mov     [rbp+arg_10], rax
0x140012b46  test    rax, rax
0x140012b49  jz      short loc_140012B88
0x140012b4b  lea     rax, off_1400494B8
0x140012b52  mov     [rdi], rax
0x140012b55  lea     rcx, [rdi+18h]
0x140012b59  mov     rdx, rbx
0x140012b5c  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140012b61  lea     rax, pplx__details___UnrealizedChore___InvokeBridge_Concurrency__details___PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency__details___TypeSelectorNoAsync__pplx__details___UnrealizedChore___
0x140012b68  mov     [rdi+8], rax
0x140012b6c  mov     byte ptr [rdi+10h], 1
0x140012b70  lea     rax, off_1400494B0
0x140012b77  mov     [rdi], rax
0x140012b7a  lea     rcx, [rdi+28h]
0x140012b7e  mov     rdx, r14
0x140012b81  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x140012b86  jmp     short loc_140012B8A
0x140012b88  xor     edi, edi
0x140012b8a  xor     r8d, r8d
0x140012b8d  mov     rdx, rdi
0x140012b90  mov     rcx, rsi
0x140012b93  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAV_UnrealizedChore@2pplx@@W4_TaskInliningMode@Custom@@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(pplx::details::_UnrealizedChore *,Custom::_TaskInliningMode)
0x140012b98  nop
0x140012b99  mov     rcx, [r14+10h]
0x140012b9d  test    rcx, rcx
0x140012ba0  jz      short loc_140012BAE
0x140012ba2  mov     rax, [rcx]
0x140012ba5  mov     rax, [rax+10h]
0x140012ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bae  mov     rcx, [r14+8]
0x140012bb2  test    rcx, rcx
0x140012bb5  jz      short loc_140012BC3
0x140012bb7  mov     rax, [rcx]
0x140012bba  mov     rax, [rax+10h]
0x140012bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bc3  mov     rcx, [r14]; string
0x140012bc6  call    WindowsDeleteString_0
0x140012bcb  nop
0x140012bcc  mov     rax, rbx
0x140012bcf  add     rsp, 40h
0x140012bd3  pop     r14
0x140012bd5  pop     rdi
0x140012bd6  pop     rsi
0x140012bd7  pop     rbx
0x140012bd8  pop     rbp
0x140012bd9  retn
```
