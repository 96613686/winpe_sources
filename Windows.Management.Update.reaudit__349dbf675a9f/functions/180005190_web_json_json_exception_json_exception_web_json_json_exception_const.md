# web::json::json_exception::json_exception(web::json::json_exception const &)

- ea: `0x180005190`
- end: `0x1800052dd`
- name: `??0json_exception@json@web@@QEAA@AEBV012@@Z`
- size: `333`
- prototype: `__int64 __fastcall(web::json::json_exception *__hidden this, const struct web::json::json_exception *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180002cac`
- `0x1800034e6`
- `0x180005190`
- `0x180008de5`
- `0x18001da08`
- `0x18001daa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000528c`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000528c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const struct web::json::json_exception *a2)
{
  _QWORD *v4; // rax
  _OWORD *v5; // rbp
  unsigned __int64 v6; // rsi
  __int64 v7; // rbx
  size_t v8; // rax
  void *v9; // rax
  __int64 v10; // rdx
  void *v11; // rcx

  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0();
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  *(_OWORD *)((char *)this + 24) = 0;
  v4 = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v5 = (_OWORD *)((char *)a2 + 24);
  if ( *((_QWORD *)a2 + 6) > 0xFu )
    v5 = (_OWORD *)*((_QWORD *)a2 + 3);
  v6 = *((_QWORD *)a2 + 5);
  v7 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  *((_QWORD *)this + 6) = 15;
  if ( v6 > 0xF )
  {
    if ( (v6 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = v6 | 0xF;
      if ( (v6 | 0xF) < 0x16 )
        v7 = 22;
      if ( (unsigned __int64)(v7 + 1) < 0x1000 )
      {
        if ( v7 != -1 )
          v4 = operator new(v7 + 1);
        goto LABEL_18;
      }
      v8 = v7 + 40;
      if ( v7 + 40 < (unsigned __int64)(v7 + 1) )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v8 = 0x8000000000000027uLL;
    }
    v9 = operator new(v8);
    v11 = v9;
    if ( !v9 )
    {
      _o__invalid_parameter_noinfo_noreturn(0, v10);
      __debugbreak();
    }
    v4 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v4 - 1) = v11;
LABEL_18:
    *((_QWORD *)this + 3) = v4;
    *((_QWORD *)this + 5) = v6;
    *((_QWORD *)this + 6) = v7;
    memcpy_0(v4, v5, v6 + 1);
    return this;
  }
  *((_QWORD *)this + 5) = v6;
  *(_OWORD *)((char *)this + 24) = *v5;
  return this;
}

```

## disassembly

```asm
0x180005190  mov     [rsp+arg_8], rbx
0x180005195  mov     [rsp+arg_10], rbp
0x18000519a  mov     [rsp+arg_18], rsi
0x18000519f  mov     [rsp+arg_0], rcx
0x1800051a4  push    rdi
0x1800051a5  sub     rsp, 20h
0x1800051a9  mov     rbx, rdx
0x1800051ac  mov     rdi, rcx
0x1800051af  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800051b6  mov     [rcx], rax
0x1800051b9  lea     rdx, [rcx+8]
0x1800051bd  xorps   xmm0, xmm0
0x1800051c0  movups  xmmword ptr [rdx], xmm0
0x1800051c3  lea     rcx, [rbx+8]
0x1800051c7  call    _o___std_exception_copy_0
0x1800051cc  nop
0x1800051cd  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x1800051d4  mov     [rdi], rax
0x1800051d7  xorps   xmm0, xmm0
0x1800051da  movups  xmmword ptr [rdi+18h], xmm0
0x1800051de  xor     eax, eax
0x1800051e0  mov     [rdi+28h], rax
0x1800051e4  mov     [rdi+30h], rax
0x1800051e8  lea     rbp, [rbx+18h]
0x1800051ec  cmp     qword ptr [rbx+30h], 0Fh
0x1800051f1  jbe     short loc_1800051F7
0x1800051f3  mov     rbp, [rbx+18h]
0x1800051f7  mov     rsi, [rbx+28h]
0x1800051fb  mov     rbx, 7FFFFFFFFFFFFFFFh
0x180005205  cmp     rsi, rbx
0x180005208  ja      loc_1800052D1
0x18000520e  mov     qword ptr [rdi+30h], 0Fh
0x180005216  cmp     rsi, 0Fh
0x18000521a  ja      short loc_18000522D
0x18000521c  mov     [rdi+28h], rsi
0x180005220  movups  xmm0, xmmword ptr [rbp+0]
0x180005224  movups  xmmword ptr [rdi+18h], xmm0
0x180005228  jmp     loc_1800052B9
0x18000522d  mov     rcx, rsi
0x180005230  or      rcx, 0Fh
0x180005234  cmp     rcx, rbx
0x180005237  jbe     short loc_180005265
0x180005239  mov     rax, 8000000000000000h
0x180005243  add     rax, 27h ; '''
0x180005247  mov     rcx, rax; Size
0x18000524a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000524f  mov     rcx, rax
0x180005252  test    rax, rax
0x180005255  jz      short loc_18000528C
0x180005257  add     rax, 27h ; '''
0x18000525b  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000525f  mov     [rax-8], rcx
0x180005263  jmp     short loc_18000529D
0x180005265  mov     rbx, rcx
0x180005268  mov     edx, 16h
0x18000526d  cmp     rcx, rdx
0x180005270  cmovb   rbx, rdx
0x180005274  lea     rcx, [rbx+1]; Size
0x180005278  cmp     rcx, 1000h
0x18000527f  jb      short loc_180005293
0x180005281  lea     rax, [rcx+27h]
0x180005285  cmp     rax, rcx
0x180005288  jbe     short loc_1800052D7
0x18000528a  jmp     short loc_180005247
0x18000528c  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005292  int     3; Trap to Debugger
0x180005293  test    rcx, rcx
0x180005296  jz      short loc_18000529D
0x180005298  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000529d  mov     [rdi+18h], rax
0x1800052a1  mov     [rdi+28h], rsi
0x1800052a5  mov     [rdi+30h], rbx
0x1800052a9  lea     r8, [rsi+1]; Size
0x1800052ad  mov     rdx, rbp; Src
0x1800052b0  mov     rcx, rax; void *
0x1800052b3  call    memcpy_0
0x1800052b8  nop
0x1800052b9  mov     rax, rdi
0x1800052bc  mov     rbx, [rsp+28h+arg_8]
0x1800052c1  mov     rbp, [rsp+28h+arg_10]
0x1800052c6  mov     rsi, [rsp+28h+arg_18]
0x1800052cb  add     rsp, 20h
0x1800052cf  pop     rdi
0x1800052d0  retn
0x1800052d1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800052d7  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
