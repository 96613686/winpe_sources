# Concurrency::task<uchar>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)

- ea: `0x18001c8bc`
- end: `0x18001c9b6`
- name: `?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z`
- size: `250`
- prototype: `void __fastcall(std::_Ref_count_base **, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180009770`
- `0x18000da9c`

## callees

- `0x18000288c`
- `0x18000c964`
- `0x18000f958`
- `0x18001c8bc`
- `0x18001cc40`
- `0x18001d6c8`

## pseudocode

```c
void __fastcall Concurrency::task<unsigned char>::_CreateImpl(std::_Ref_count_base **a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // r8
  std::_Ref_count_base **v7; // rdi
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  volatile signed __int32 *v10; // rax
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+30h] [rbp-10h]
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  std::_Ref_count_base **v15; // [rsp+78h] [rbp+38h]
  _QWORD *v16; // [rsp+80h] [rbp+40h]

  v16 = a3;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v12,
    a3);
  v13 = *(_QWORD *)(v6 + 16);
  v15 = v12;
  v14 = a2;
  v7 = (std::_Ref_count_base **)operator new(0x1C8u);
  v15 = v7;
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *v7 = (std::_Ref_count_base *)&std::_Ref_count_obj2<Concurrency::details::_Task_impl<unsigned char>>::`vftable';
  std::_Construct_in_place<Concurrency::details::_Task_impl<unsigned char>,Concurrency::details::_CancellationTokenState * &,Concurrency::scheduler_ptr &>(
    v7 + 2,
    (__int64)&v14,
    (__int64)v12);
  if ( v12[1] )
    std::_Ref_count_base::_Decref(v12[1]);
  *a1 = (std::_Ref_count_base *)(v7 + 2);
  v8 = a1[1];
  a1[1] = (std::_Ref_count_base *)v7;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  if ( a2 != 2 )
  {
    v9 = *a1;
    *(_OWORD *)v12 = 0;
    v10 = (volatile signed __int32 *)a1[1];
    if ( v10 )
    {
      v12[0] = v9;
      v12[1] = (std::_Ref_count_base *)v10;
      _InterlockedIncrement(v10 + 3);
    }
    Concurrency::details::_Task_impl_base::_RegisterCancellation(v9, v12);
  }
  v11 = (std::_Ref_count_base *)a3[1];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x18001c8bc  mov     [rsp-28h+arg_18], rbx
0x18001c8c1  mov     [rsp-28h+arg_10], r8
0x18001c8c6  push    rbp
0x18001c8c7  push    rsi
0x18001c8c8  push    rdi
0x18001c8c9  push    r14
0x18001c8cb  push    r15
0x18001c8cd  mov     rbp, rsp
0x18001c8d0  sub     rsp, 40h
0x18001c8d4  mov     rsi, r8
0x18001c8d7  mov     r14, rdx
0x18001c8da  mov     rbx, rcx
0x18001c8dd  mov     rdx, r8
0x18001c8e0  lea     rcx, [rbp+var_20]
0x18001c8e4  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001c8e9  mov     r8, [r8+10h]
0x18001c8ed  mov     [rbp+var_10], r8
0x18001c8f1  lea     rax, [rbp+var_20]
0x18001c8f5  mov     [rbp+arg_8], rax
0x18001c8f9  mov     [rbp+arg_0], r14
0x18001c8fd  mov     ecx, 1C8h; Size
0x18001c902  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c907  mov     rdi, rax
0x18001c90a  mov     [rbp+arg_8], rax
0x18001c90e  xorps   xmm0, xmm0
0x18001c911  movups  xmmword ptr [rax], xmm0
0x18001c914  mov     dword ptr [rax+8], 1
0x18001c91b  mov     dword ptr [rax+0Ch], 1
0x18001c922  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_Task_impl<uchar>>::`vftable'
0x18001c929  mov     [rdi], rax
0x18001c92c  lea     r15, [rdi+10h]
0x18001c930  lea     r8, [rbp+var_20]
0x18001c934  lea     rdx, [rbp+arg_0]
0x18001c938  mov     rcx, r15
0x18001c93b  call    ??$_Construct_in_place@U?$_Task_impl@E@details@Concurrency@@AEAPEAV_CancellationTokenState@23@AEAUscheduler_ptr@3@@std@@YAXAEAU?$_Task_impl@E@details@Concurrency@@AEAPEAV_CancellationTokenState@23@AEAUscheduler_ptr@3@@Z; std::_Construct_in_place<Concurrency::details::_Task_impl<uchar>,Concurrency::details::_CancellationTokenState * &,Concurrency::scheduler_ptr &>(Concurrency::details::_Task_impl<uchar> &,Concurrency::details::_CancellationTokenState * &,Concurrency::scheduler_ptr &)
0x18001c940  nop
0x18001c941  mov     rcx, [rbp+var_20+8]; this
0x18001c945  test    rcx, rcx
0x18001c948  jz      short loc_18001C94F
0x18001c94a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c94f  mov     [rbx], r15
0x18001c952  mov     rcx, [rbx+8]; this
0x18001c956  mov     [rbx+8], rdi
0x18001c95a  test    rcx, rcx
0x18001c95d  jz      short loc_18001C964
0x18001c95f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c964  cmp     r14, 2
0x18001c968  jz      short loc_18001C994
0x18001c96a  mov     rcx, [rbx]
0x18001c96d  xorps   xmm0, xmm0
0x18001c970  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001c975  mov     rax, [rbx+8]
0x18001c979  test    rax, rax
0x18001c97c  jz      short loc_18001C98A
0x18001c97e  mov     [rbp+var_20], rcx
0x18001c982  mov     [rbp+var_20+8], rax
0x18001c986  lock inc dword ptr [rax+0Ch]
0x18001c98a  lea     rdx, [rbp+var_20]
0x18001c98e  call    ?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXV?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@@Z; Concurrency::details::_Task_impl_base::_RegisterCancellation(std::weak_ptr<Concurrency::details::_Task_impl_base>)
0x18001c993  nop
0x18001c994  mov     rcx, [rsi+8]; this
0x18001c998  test    rcx, rcx
0x18001c99b  jz      short loc_18001C9A2
0x18001c99d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c9a2  mov     rbx, [rsp+40h+arg_18]
0x18001c9aa  add     rsp, 40h
0x18001c9ae  pop     r15
0x18001c9b0  pop     r14
0x18001c9b2  pop     rdi
0x18001c9b3  pop     rsi
0x18001c9b4  pop     rbp
0x18001c9b5  retn
```
