# Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`scalar deleting destructor'(uint)

- ea: `0x1800104c0`
- end: `0x18001051f`
- name: `??_G?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@UEAAPEAXI@Z`
- size: `95`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x1800104c0`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  volatile signed __int32 *v4; // rcx

  v4 = (volatile signed __int32 *)a1[25];
  if ( v4 && _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  *a1 = &Concurrency::details::_RefCounter::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_0], rbx
0x1800104c5  push    rdi
0x1800104c6  sub     rsp, 20h
0x1800104ca  mov     rbx, rcx
0x1800104cd  mov     edi, edx
0x1800104cf  mov     rcx, [rcx+0C8h]
0x1800104d6  test    rcx, rcx
0x1800104d9  jz      short loc_1800104F4
0x1800104db  or      eax, 0FFFFFFFFh
0x1800104de  lock xadd [rcx+0Ch], eax
0x1800104e3  cmp     eax, 1
0x1800104e6  jnz     short loc_1800104F4
0x1800104e8  mov     rax, [rcx]
0x1800104eb  mov     rax, [rax+8]
0x1800104ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f4  lea     rax, ??_7_RefCounter@details@Concurrency@@6B@; const Concurrency::details::_RefCounter::`vftable'
0x1800104fb  mov     [rbx], rax
0x1800104fe  test    dil, 1
0x180010502  jz      short loc_180010511
0x180010504  mov     edx, 0D0h; unsigned __int64
0x180010509  mov     rcx, rbx; void *
0x18001050c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010511  mov     rax, rbx
0x180010514  mov     rbx, [rsp+28h+arg_0]
0x180010519  add     rsp, 20h
0x18001051d  pop     rdi
0x18001051e  retn
```
