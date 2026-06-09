# Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)

- ea: `0x18001d6c8`
- end: `0x18001d797`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z`
- size: `207`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c8bc`

## callees

- `0x18000288c`
- `0x18000f608`
- `0x18000faf0`
- `0x180010290`
- `0x180010754`
- `0x18001cc78`
- `0x18001d5c0`
- `0x18001d6c8`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // r8
  int v6; // edx
  __int64 v7; // r8
  struct Concurrency::details::_CancellationTokenRegistration *v8; // r8
  std::_Ref_count_base *v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v11; // [rsp+28h] [rbp-10h]
  _DWORD *v12; // [rsp+40h] [rbp+8h]

  std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(&v10, a2);
  v12 = operator new(0xD0u);
  *(_QWORD *)v12 = &Concurrency::details::_RefCounter::`vftable';
  v12[2] = 1;
  std::atomic<long>::atomic<long>(v12 + 4, 3);
  std::condition_variable::condition_variable((std::condition_variable *)(v4 + 24));
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(v5 + 96), v6);
  *(_BYTE *)(v7 + 176) = 0;
  *(_QWORD *)(v7 + 184) = 0;
  *(_QWORD *)v7 = &Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable';
  std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(
    (_QWORD *)(v7 + 192),
    &v10);
  *(_QWORD *)(a1 + 128) = v8;
  Concurrency::details::_CancellationTokenState::_RegisterCallback(
    *(Concurrency::details::_CancellationTokenState **)(a1 + 120),
    v8);
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
  v9 = (std::_Ref_count_base *)a2[1];
  if ( v9 )
    std::_Ref_count_base::_Decwref(v9);
}

```

## disassembly

```asm
0x18001d6c8  mov     [rsp+arg_10], rbx
0x18001d6cd  mov     [rsp+arg_8], rdx
0x18001d6d2  push    rdi
0x18001d6d3  sub     rsp, 30h
0x18001d6d7  mov     rdi, rdx
0x18001d6da  mov     rbx, rcx
0x18001d6dd  lea     rcx, [rsp+38h+var_18]
0x18001d6e2  call    ??0?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(std::weak_ptr<Concurrency::details::_Task_impl_base> const &)
0x18001d6e7  nop
0x18001d6e8  mov     ecx, 0D0h; Size
0x18001d6ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d6f2  mov     r8, rax
0x18001d6f5  mov     [rsp+38h+arg_0], rax
0x18001d6fa  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x18001d701  mov     [r8], rax
0x18001d704  mov     dword ptr [r8+8], 1
0x18001d70c  lea     rcx, [r8+10h]
0x18001d710  mov     edx, 3
0x18001d715  call    ??0?$atomic@J@std@@QEAA@J@Z; std::atomic<long>::atomic<long>(long)
0x18001d71a  lea     rcx, [r8+18h]; this
0x18001d71e  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x18001d723  lea     rcx, [r8+60h]; this
0x18001d727  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18001d72c  mov     byte ptr [r8+0B0h], 0
0x18001d734  mov     qword ptr [r8+0B8h], 0
0x18001d73f  lea     rax, ??_7?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@6B@; const Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`vftable'
0x18001d746  mov     [r8], rax
0x18001d749  lea     rcx, [r8+0C0h]
0x18001d750  lea     rdx, [rsp+38h+var_18]
0x18001d755  call    ??0?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<Concurrency::details::_Task_impl_base>::weak_ptr<Concurrency::details::_Task_impl_base>(std::weak_ptr<Concurrency::details::_Task_impl_base> const &)
0x18001d75a  mov     [rbx+80h], r8
0x18001d761  mov     rdx, r8; struct Concurrency::details::_CancellationTokenRegistration *
0x18001d764  mov     rcx, [rbx+78h]; this
0x18001d768  call    ?_RegisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z; Concurrency::details::_CancellationTokenState::_RegisterCallback(Concurrency::details::_CancellationTokenRegistration *)
0x18001d76d  nop
0x18001d76e  mov     rcx, [rsp+38h+var_10]; this
0x18001d773  test    rcx, rcx
0x18001d776  jz      short loc_18001D77E
0x18001d778  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001d77d  nop
0x18001d77e  mov     rcx, [rdi+8]; this
0x18001d782  test    rcx, rcx
0x18001d785  jz      short loc_18001D78C
0x18001d787  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001d78c  mov     rbx, [rsp+38h+arg_10]
0x18001d791  add     rsp, 30h
0x18001d795  pop     rdi
0x18001d796  retn
```
