# std::vector<HINSTANCE__ *,std::allocator<HINSTANCE__ *>>::_Emplace_reallocate<HINSTANCE__ * const &>(HINSTANCE__ * * const,HINSTANCE__ * const &)

- ea: `0x180008d3c`
- end: `0x180008ea7`
- name: `??$_Emplace_reallocate@AEBQEAUHINSTANCE__@@@?$vector@PEAUHINSTANCE__@@V?$allocator@PEAUHINSTANCE__@@@std@@@std@@AEAAPEAPEAUHINSTANCE__@@QEAPEAU2@AEBQEAU2@@Z`
- size: `363`
- prototype: `char *__fastcall(_QWORD *, _BYTE *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006544`

## callees

- `0x180008d3c`
- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180008dfb`
- `VCRUNTIME140!memmove` at `0x180008e0f`
- `VCRUNTIME140!memmove` at `0x180008dfb`
- `VCRUNTIME140!memmove` at `0x180008e0f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008e95`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008e95`

## pseudocode

```c
char *__fastcall std::vector<HINSTANCE__ *>::_Emplace_reallocate<HINSTANCE__ * const &>(
        _QWORD *a1,
        _BYTE *a2,
        _QWORD *a3)
{
  __int64 v4; // rbp
  __int64 v6; // rax
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // r12
  char *v12; // rdi
  char *v13; // r14
  _BYTE *v14; // r8
  _QWORD *v15; // rdx
  void *v16; // rcx
  size_t v17; // r8
  unsigned __int64 v18; // rax
  _QWORD *v19; // rcx

  v4 = (__int64)&a2[-*a1] >> 3;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(a1, a2);
  v8 = v6 + 1;
  v9 = (__int64)(a1[2] - *a1) >> 3;
  if ( v9 <= 0x1FFFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v18 = (v9 >> 1) + v9;
    v10 = v8;
    if ( v18 >= v8 )
      v10 = v18;
    if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v10 = 0x1FFFFFFFFFFFFFFFLL;
  }
  _mm_lfence();
  v11 = 8 * v10;
  v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(8 * v10);
  v13 = &v12[8 * v4];
  *(_QWORD *)v13 = *a3;
  v14 = (_BYTE *)a1[1];
  v15 = (_QWORD *)*a1;
  _mm_lfence();
  v16 = v12;
  if ( a2 == v14 )
  {
    v17 = v14 - (_BYTE *)v15;
  }
  else
  {
    memmove(v12, v15, a2 - (_BYTE *)v15);
    v16 = v13 + 8;
    v17 = a1[1] - (_QWORD)a2;
    v15 = a2;
  }
  memmove(v16, v15, v17);
  v19 = (_QWORD *)*a1;
  if ( *a1 )
  {
    if ( ((a1[2] - (_QWORD)v19) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v19 - *(v19 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v19 = (_QWORD *)*(v19 - 1);
    }
    operator delete(v19);
  }
  *a1 = v12;
  a1[1] = &v12[8 * v8];
  a1[2] = &v12[v11];
  _mm_lfence();
  return &v12[8 * v4];
}

```

## disassembly

```asm
0x180008d3c  mov     [rsp+arg_10], rbx
0x180008d41  push    rbp
0x180008d42  push    rsi
0x180008d43  push    rdi
0x180008d44  push    r12
0x180008d46  push    r13
0x180008d48  push    r14
0x180008d4a  push    r15
0x180008d4c  sub     rsp, 30h
0x180008d50  mov     rax, [rcx+8]
0x180008d54  mov     rbp, rdx
0x180008d57  sub     rbp, [rcx]
0x180008d5a  mov     r13, r8
0x180008d5d  sub     rax, [rcx]
0x180008d60  mov     r8, 1FFFFFFFFFFFFFFFh
0x180008d6a  sar     rbp, 3
0x180008d6e  mov     rsi, rdx
0x180008d71  sar     rax, 3
0x180008d75  mov     rbx, rcx
0x180008d78  cmp     rax, r8
0x180008d7b  jz      loc_180008E9C
0x180008d81  mov     rcx, [rcx+10h]
0x180008d85  lea     r15, [rax+1]
0x180008d89  sub     rcx, [rbx]
0x180008d8c  mov     rax, r8
0x180008d8f  sar     rcx, 3
0x180008d93  mov     rdx, rcx
0x180008d96  shr     rdx, 1
0x180008d99  sub     rax, rdx
0x180008d9c  cmp     rcx, rax
0x180008d9f  jbe     short loc_180008DDC
0x180008da1  mov     rcx, r8
0x180008da4  lfence
0x180008da7  lea     r12, ds:0[rcx*8]
0x180008daf  mov     rcx, r12
0x180008db2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008db7  mov     rcx, [r13+0]
0x180008dbb  mov     rdi, rax
0x180008dbe  lea     r14, [rax+rbp*8]
0x180008dc2  mov     [r14], rcx
0x180008dc5  mov     r8, [rbx+8]
0x180008dc9  mov     rdx, [rbx]; Src
0x180008dcc  lfence
0x180008dcf  mov     rcx, rax; void *
0x180008dd2  cmp     rsi, r8
0x180008dd5  jnz     short loc_180008DF5
0x180008dd7  sub     r8, rdx
0x180008dda  jmp     short loc_180008E0F
0x180008ddc  lea     rax, [rdx+rcx]
0x180008de0  mov     rcx, r15
0x180008de3  cmp     rax, r15
0x180008de6  cmovnb  rcx, rax
0x180008dea  cmp     rcx, r8
0x180008ded  ja      loc_180008EA2
0x180008df3  jmp     short loc_180008DA4
0x180008df5  mov     r8, rsi
0x180008df8  sub     r8, rdx; Size
0x180008dfb  call    cs:__imp_memmove
0x180008e01  mov     r8, [rbx+8]
0x180008e05  lea     rcx, [r14+8]; void *
0x180008e09  sub     r8, rsi; Size
0x180008e0c  mov     rdx, rsi; Src
0x180008e0f  call    cs:__imp_memmove
0x180008e15  mov     rcx, [rbx]
0x180008e18  test    rcx, rcx
0x180008e1b  jz      short loc_180008E51
0x180008e1d  mov     rdx, [rbx+10h]
0x180008e21  sub     rdx, rcx
0x180008e24  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180008e28  cmp     rdx, 1000h
0x180008e2f  jb      short loc_180008E4C
0x180008e31  lfence
0x180008e34  mov     rax, [rcx-8]
0x180008e38  add     rdx, 27h ; '''
0x180008e3c  sub     rcx, rax
0x180008e3f  sub     rcx, 8
0x180008e43  cmp     rcx, 1Fh
0x180008e47  ja      short loc_180008E82
0x180008e49  mov     rcx, rax; Block
0x180008e4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008e51  lea     rcx, [rdi+r15*8]
0x180008e55  mov     [rbx], rdi
0x180008e58  mov     [rbx+8], rcx
0x180008e5c  lea     rcx, [r12+rdi]
0x180008e60  mov     [rbx+10h], rcx
0x180008e64  lfence
0x180008e67  mov     rbx, [rsp+68h+arg_10]
0x180008e6f  mov     rax, r14
0x180008e72  add     rsp, 30h
0x180008e76  pop     r15
0x180008e78  pop     r14
0x180008e7a  pop     r13
0x180008e7c  pop     r12
0x180008e7e  pop     rdi
0x180008e7f  pop     rsi
0x180008e80  pop     rbp
0x180008e81  retn
0x180008e82  xor     r9d, r9d; LineNo
0x180008e85  mov     [rsp+68h+Reserved], 0; Reserved
0x180008e8e  xor     r8d, r8d; FileName
0x180008e91  xor     edx, edx; FunctionName
0x180008e93  xor     ecx, ecx; Expression
0x180008e95  call    cs:__imp__invoke_watson
0x180008e9c  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
0x180008ea2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
