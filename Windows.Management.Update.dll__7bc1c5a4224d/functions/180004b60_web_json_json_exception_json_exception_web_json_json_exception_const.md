# web::json::json_exception::json_exception(web::json::json_exception const &)

- ea: `0x180004b60`
- end: `0x180004c98`
- name: `??0json_exception@json@web@@QEAA@AEBV012@@Z`
- size: `312`
- prototype: `web::json::json_exception *__fastcall(web::json::json_exception *this, const struct web::json::json_exception *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180002cfc`
- `0x1800032f6`
- `0x180004b60`
- `0x180008833`
- `0x18001c7f4`
- `0x18001c888`

## pseudocode

```c
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const struct web::json::json_exception *a2)
{
  _OWORD *v4; // rbp
  unsigned __int64 v5; // rsi
  __int64 v6; // rbx
  size_t v7; // rax
  void *v8; // rax
  void *v9; // rcx
  size_t v10; // rcx
  _QWORD *v11; // rax

  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0((char *)a2 + 8, (char *)this + 8);
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( *((_QWORD *)a2 + 6) <= 0xFu )
    v4 = (_OWORD *)((char *)a2 + 24);
  else
    v4 = (_OWORD *)*((_QWORD *)a2 + 3);
  v5 = *((_QWORD *)a2 + 5);
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v5 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( v5 > 0xF )
  {
    if ( (v5 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = 0x8000000000000027uLL;
LABEL_9:
      v8 = operator new(v7);
      v9 = v8;
      if ( !v8 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v9;
      goto LABEL_20;
    }
    v6 = v5 | 0xF;
    if ( (v5 | 0xF) < 0x16 )
      v6 = 22;
    v10 = v6 + 1;
    if ( v6 == -1 )
    {
      v11 = 0;
    }
    else
    {
      if ( v10 >= 0x1000 )
      {
        v7 = v6 + 40;
        if ( v6 + 40 < (unsigned __int64)(v6 + 1) )
          __scrt_throw_std_bad_array_new_length();
        goto LABEL_9;
      }
      v11 = operator new(v10);
    }
LABEL_20:
    *((_QWORD *)this + 3) = v11;
    *((_QWORD *)this + 5) = v5;
    *((_QWORD *)this + 6) = v6;
    memcpy_0(v11, v4, v5 + 1);
    return this;
  }
  *((_QWORD *)this + 5) = v5;
  *((_QWORD *)this + 6) = 15;
  *(_OWORD *)((char *)this + 24) = *v4;
  return this;
}

```

## disassembly

```asm
0x180004b60  mov     [rsp+arg_0], rcx
0x180004b65  push    rbx
0x180004b66  push    rbp
0x180004b67  push    rsi
0x180004b68  push    rdi
0x180004b69  sub     rsp, 28h
0x180004b6d  mov     rbx, rdx
0x180004b70  mov     rdi, rcx
0x180004b73  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180004b7a  mov     [rcx], rax
0x180004b7d  lea     rdx, [rcx+8]
0x180004b81  xorps   xmm0, xmm0
0x180004b84  movups  xmmword ptr [rdx], xmm0
0x180004b87  lea     rcx, [rbx+8]
0x180004b8b  call    _o___std_exception_copy_0
0x180004b90  nop
0x180004b91  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x180004b98  mov     [rdi], rax
0x180004b9b  xorps   xmm0, xmm0
0x180004b9e  movups  xmmword ptr [rdi+18h], xmm0
0x180004ba2  xor     edx, edx
0x180004ba4  mov     [rdi+28h], rdx
0x180004ba8  mov     [rdi+30h], rdx
0x180004bac  cmp     qword ptr [rbx+30h], 0Fh
0x180004bb1  jbe     short loc_180004BB9
0x180004bb3  mov     rbp, [rbx+18h]
0x180004bb7  jmp     short loc_180004BBD
0x180004bb9  lea     rbp, [rbx+18h]
0x180004bbd  mov     rsi, [rbx+28h]
0x180004bc1  mov     rbx, 7FFFFFFFFFFFFFFFh
0x180004bcb  cmp     rsi, rbx
0x180004bce  ja      loc_180004C8C
0x180004bd4  cmp     rsi, 0Fh
0x180004bd8  ja      short loc_180004BF3
0x180004bda  mov     [rdi+28h], rsi
0x180004bde  mov     qword ptr [rdi+30h], 0Fh
0x180004be6  movups  xmm0, xmmword ptr [rbp+0]
0x180004bea  movups  xmmword ptr [rdi+18h], xmm0
0x180004bee  jmp     loc_180004C80
0x180004bf3  mov     rax, rsi
0x180004bf6  or      rax, 0Fh
0x180004bfa  cmp     rax, rbx
0x180004bfd  jbe     short loc_180004C20
0x180004bff  mov     rax, 8000000000000027h
0x180004c09  mov     rcx, rax; Size
0x180004c0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c11  mov     rcx, rax
0x180004c14  test    rax, rax
0x180004c17  jnz     short loc_180004C51
0x180004c19  mov     ecx, 5
0x180004c1e  int     29h; Win8: RtlFailFast(ecx)
0x180004c20  mov     rbx, rax
0x180004c23  mov     ecx, 16h
0x180004c28  cmp     rax, rcx
0x180004c2b  cmovb   rbx, rcx
0x180004c2f  lea     rcx, [rbx+1]; Size
0x180004c33  test    rcx, rcx
0x180004c36  jnz     short loc_180004C3D
0x180004c38  mov     rax, rdx
0x180004c3b  jmp     short loc_180004C64
0x180004c3d  cmp     rcx, 1000h
0x180004c44  jb      short loc_180004C5F
0x180004c46  lea     rax, [rcx+27h]
0x180004c4a  cmp     rax, rcx
0x180004c4d  jbe     short loc_180004C92
0x180004c4f  jmp     short loc_180004C09
0x180004c51  add     rax, 27h ; '''
0x180004c55  and     rax, 0FFFFFFFFFFFFFFE0h
0x180004c59  mov     [rax-8], rcx
0x180004c5d  jmp     short loc_180004C64
0x180004c5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c64  mov     [rdi+18h], rax
0x180004c68  mov     [rdi+28h], rsi
0x180004c6c  mov     [rdi+30h], rbx
0x180004c70  lea     r8, [rsi+1]; Size
0x180004c74  mov     rdx, rbp; Src
0x180004c77  mov     rcx, rax; void *
0x180004c7a  call    memcpy_0
0x180004c7f  nop
0x180004c80  mov     rax, rdi
0x180004c83  add     rsp, 28h
0x180004c87  pop     rdi
0x180004c88  pop     rsi
0x180004c89  pop     rbp
0x180004c8a  pop     rbx
0x180004c8b  retn
0x180004c8c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180004c92  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
