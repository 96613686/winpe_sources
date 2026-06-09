# std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::_Delete_this(bool)

- ea: `0x180011bb0`
- end: `0x180011c27`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_f25c37099038263181b5186a3fa41b37_@@X$$V@std@@EEAAX_N@Z`
- size: `119`
- prototype: `void __fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x180011bb0`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::_Delete_this(
        _QWORD *a1,
        char a2)
{
  volatile signed __int32 *v2; // rbx

  v2 = (volatile signed __int32 *)a1[3];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180011bb0  mov     [rsp+arg_0], rbx
0x180011bb5  mov     [rsp+arg_8], rsi
0x180011bba  push    rdi
0x180011bbb  sub     rsp, 20h
0x180011bbf  mov     rbx, [rcx+18h]
0x180011bc3  mov     sil, dl
0x180011bc6  mov     rdi, rcx
0x180011bc9  test    rbx, rbx
0x180011bcc  jz      short loc_180011C05
0x180011bce  or      eax, 0FFFFFFFFh
0x180011bd1  lock xadd [rbx+8], eax
0x180011bd6  cmp     eax, 1
0x180011bd9  jnz     short loc_180011C05
0x180011bdb  mov     rax, [rbx]
0x180011bde  mov     rcx, rbx
0x180011be1  mov     rax, [rax]
0x180011be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011be9  or      eax, 0FFFFFFFFh
0x180011bec  lock xadd [rbx+0Ch], eax
0x180011bf1  cmp     eax, 1
0x180011bf4  jnz     short loc_180011C05
0x180011bf6  mov     rax, [rbx]
0x180011bf9  mov     rcx, rbx
0x180011bfc  mov     rax, [rax+8]
0x180011c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c05  test    sil, sil
0x180011c08  jz      short loc_180011C17
0x180011c0a  mov     edx, 20h ; ' '; unsigned __int64
0x180011c0f  mov     rcx, rdi; void *
0x180011c12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011c17  mov     rbx, [rsp+28h+arg_0]
0x180011c1c  mov     rsi, [rsp+28h+arg_8]
0x180011c21  add     rsp, 20h
0x180011c25  pop     rdi
0x180011c26  retn
```
