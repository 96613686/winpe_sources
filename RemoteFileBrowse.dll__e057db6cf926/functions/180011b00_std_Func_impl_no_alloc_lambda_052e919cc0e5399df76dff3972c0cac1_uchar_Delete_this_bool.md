# std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::_Delete_this(bool)

- ea: `0x180011b00`
- end: `0x180011b5e`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@EEAAX_N@Z`
- size: `94`
- prototype: `void __fastcall(char *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002054`
- `0x180011b00`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::_Delete_this(
        char *a1,
        __int64 a2)
{
  char *v2; // rdi
  char *v4; // rcx
  char v5; // si

  v2 = a1 + 8;
  v4 = (char *)*((_QWORD *)a1 + 8);
  v5 = a2;
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v2;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *((_QWORD *)v2 + 7) = 0;
  }
  if ( v5 )
    operator delete(a1);
}

```

## disassembly

```asm
0x180011b00  mov     [rsp+arg_0], rbx
0x180011b05  mov     [rsp+arg_8], rsi
0x180011b0a  push    rdi
0x180011b0b  sub     rsp, 20h
0x180011b0f  lea     rdi, [rcx+8]
0x180011b13  mov     rbx, rcx
0x180011b16  mov     rcx, [rdi+38h]
0x180011b1a  mov     sil, dl
0x180011b1d  test    rcx, rcx
0x180011b20  jz      short loc_180011B3C
0x180011b22  mov     rax, [rcx]
0x180011b25  cmp     rcx, rdi
0x180011b28  setnz   dl
0x180011b2b  mov     rax, [rax+20h]
0x180011b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b34  mov     qword ptr [rdi+38h], 0
0x180011b3c  test    sil, sil
0x180011b3f  jz      short loc_180011B4E
0x180011b41  mov     edx, 48h ; 'H'; unsigned __int64
0x180011b46  mov     rcx, rbx; void *
0x180011b49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011b4e  mov     rbx, [rsp+28h+arg_0]
0x180011b53  mov     rsi, [rsp+28h+arg_8]
0x180011b58  add     rsp, 20h
0x180011b5c  pop     rdi
0x180011b5d  retn
```
