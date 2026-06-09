# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x180023cdc`
- end: `0x180023db5`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `217`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022df8`

## callees

- `0x180003b84`
- `0x18001d8d4`
- `0x18001da24`
- `0x18001db00`
- `0x18001dcb0`
- `0x180022f38`
- `0x180023bcc`
- `0x180023cdc`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  int v7; // edx
  __int64 v8; // r8
  struct Concurrency::details::_CancellationTokenRegistration *v9; // r8
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v12; // [rsp+28h] [rbp-10h]

  std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(&v11, a2);
  v4 = operator new(0xD0u);
  if ( v4 )
  {
    *(_QWORD *)v4 = &Concurrency::details::_RefCounter::`vftable';
    v4[2] = 1;
    std::atomic<long>::atomic<long>(v4 + 4, 3);
    std::condition_variable::condition_variable((std::condition_variable *)(v5 + 24));
    std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(v6 + 96), v7);
    *(_BYTE *)(v8 + 176) = 0;
    *(_QWORD *)(v8 + 184) = 0;
    *(_QWORD *)v8 = &Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable';
    std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(
      (_QWORD *)(v8 + 192),
      &v11);
  }
  else
  {
    v9 = 0;
  }
  *(_QWORD *)(a1 + 128) = v9;
  Concurrency::details::_CancellationTokenState::_RegisterCallback(
    *(Concurrency::details::_CancellationTokenState **)(a1 + 120),
    v9);
  if ( v12 )
    std::_Ref_count_base::_Decwref(v12);
  v10 = (std::_Ref_count_base *)a2[1];
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
}

```

## disassembly

```asm
0x180023cdc  mov     [rsp+arg_10], rbx
0x180023ce1  mov     [rsp+arg_8], rdx
0x180023ce6  push    rdi
0x180023ce7  sub     rsp, 30h
0x180023ceb  mov     rbx, rdx
0x180023cee  mov     rdi, rcx
0x180023cf1  lea     rcx, [rsp+38h+var_18]
0x180023cf6  call    ??0?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(std::weak_ptr<Concurrency::details::_Task_impl_base> const &)
0x180023cfb  nop
0x180023cfc  mov     ecx, 0D0h; Size
0x180023d01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023d06  mov     r8, rax
0x180023d09  mov     [rsp+38h+arg_0], rax
0x180023d0e  test    rax, rax
0x180023d11  jz      short loc_180023D75
0x180023d13  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x180023d1a  mov     [r8], rax
0x180023d1d  mov     dword ptr [r8+8], 1
0x180023d25  lea     rcx, [r8+10h]
0x180023d29  mov     edx, 3
0x180023d2e  call    ??0?$atomic@J@std@@QEAA@J@Z; std::atomic<long>::atomic<long>(long)
0x180023d33  lea     rcx, [r8+18h]; this
0x180023d37  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x180023d3c  lea     rcx, [r8+60h]; this
0x180023d40  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x180023d45  mov     byte ptr [r8+0B0h], 0
0x180023d4d  mov     qword ptr [r8+0B8h], 0
0x180023d58  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x180023d5f  mov     [r8], rax
0x180023d62  lea     rcx, [r8+0C0h]
0x180023d69  lea     rdx, [rsp+38h+var_18]
0x180023d6e  call    ??0?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(std::weak_ptr<Concurrency::details::_Task_impl_base> const &)
0x180023d73  jmp     short loc_180023D78
0x180023d75  xor     r8d, r8d
0x180023d78  mov     [rdi+80h], r8
0x180023d7f  mov     rdx, r8; struct Concurrency::details::_CancellationTokenRegistration *
0x180023d82  mov     rcx, [rdi+78h]; this
0x180023d86  call    ?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z; Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)
0x180023d8b  nop
0x180023d8c  mov     rcx, [rsp+38h+var_10]; this
0x180023d91  test    rcx, rcx
0x180023d94  jz      short loc_180023D9C
0x180023d96  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180023d9b  nop
0x180023d9c  mov     rcx, [rbx+8]; this
0x180023da0  test    rcx, rcx
0x180023da3  jz      short loc_180023DAA
0x180023da5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180023daa  mov     rbx, [rsp+38h+arg_10]
0x180023daf  add     rsp, 30h
0x180023db3  pop     rdi
0x180023db4  retn
```
