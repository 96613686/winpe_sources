# std::operator+<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const * const)

- ea: `0x18002b2f0`
- end: `0x18002b415`
- name: `??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z`
- size: `293`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002a2a8`

## callees

- `0x180009e00`
- `0x180009e14`
- `0x180009f84`
- `0x18002b2f0`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18002b3aa`
- `VCRUNTIME140!memcpy` at `0x18002b3bf`
- `VCRUNTIME140!memcpy` at `0x18002b3aa`
- `VCRUNTIME140!memcpy` at `0x18002b3bf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b31d`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b31d`

## string_xrefs

- `0x18002b313`: `\DiagnosticsHub.Packaging.dll`
- `0x18002b3b8`: `\DiagnosticsHub.Packaging.dll`

## pseudocode

```c
char *__fastcall std::operator+<unsigned short>(char *a1, _QWORD *Src)
{
  __int64 v2; // r15
  _QWORD *v4; // rsi
  size_t v5; // r12
  unsigned __int64 v6; // rbx
  size_t v7; // rbp
  char *v8; // r14
  __int64 v9; // rcx
  char *result; // rax

  v2 = Src[2];
  v4 = Src;
  v5 = wcslen(L"\\DiagnosticsHub.Packaging.dll");
  if ( 0x7FFFFFFFFFFFFFFELL - v2 < v5 )
    std::_Xlen_string();
  v6 = 7;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  v7 = v5 + v2;
  v8 = a1;
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  if ( v5 + v2 > 7 )
  {
    v6 = v7 | 7;
    if ( (v7 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v6 < 0xA )
        v6 = 10;
      v9 = v6 + 1;
      if ( v6 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        __scrt_throw_std_bad_array_new_length();
    }
    else
    {
      v6 = 0x7FFFFFFFFFFFFFFELL;
      v9 = 0x7FFFFFFFFFFFFFFFLL;
    }
    _mm_lfence();
    v8 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2 * v9);
    *(_QWORD *)a1 = v8;
  }
  _mm_lfence();
  *((_QWORD *)a1 + 3) = v6;
  *((_QWORD *)a1 + 2) = v7;
  memcpy(v8, v4, 2 * v2);
  memcpy(&v8[2 * v2], L"\\DiagnosticsHub.Packaging.dll", 2 * v5);
  result = a1;
  *(_WORD *)&v8[2 * v7] = 0;
  return result;
}

```

## disassembly

```asm
0x18002b2f0  mov     [rsp+arg_10], rbx
0x18002b2f5  push    rbp
0x18002b2f6  push    rsi
0x18002b2f7  push    rdi
0x18002b2f8  push    r12
0x18002b2fa  push    r13
0x18002b2fc  push    r14
0x18002b2fe  push    r15
0x18002b300  sub     rsp, 30h
0x18002b304  mov     r15, [rdx+10h]
0x18002b308  mov     rdi, rcx
0x18002b30b  mov     [rsp+68h+var_40], rcx
0x18002b310  mov     rsi, rdx
0x18002b313  lea     rcx, aDiagnosticshub_2; "\\DiagnosticsHub.Packaging.dll"
0x18002b31a  xor     r13d, r13d
0x18002b31d  call    cs:__imp_wcslen
0x18002b323  mov     r12, rax
0x18002b326  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18002b330  mov     rax, rcx
0x18002b333  sub     rax, r15
0x18002b336  cmp     rax, r12
0x18002b339  jb      loc_18002B409
0x18002b33f  lea     ebx, [r13+7]
0x18002b343  cmp     [rsi+18h], rbx
0x18002b347  jbe     short loc_18002B34C
0x18002b349  mov     rsi, [rsi]
0x18002b34c  xorps   xmm0, xmm0
0x18002b34f  lea     rbp, [r12+r15]
0x18002b353  mov     r14, rdi
0x18002b356  movups  xmmword ptr [rdi], xmm0
0x18002b359  mov     [rdi+10h], r13
0x18002b35d  mov     [rdi+18h], r13
0x18002b361  cmp     rbp, rbx
0x18002b364  jbe     short loc_18002B392
0x18002b366  mov     rax, rbp
0x18002b369  or      rax, rbx
0x18002b36c  mov     rbx, rax
0x18002b36f  cmp     rax, rcx
0x18002b372  jbe     short loc_18002B3E5
0x18002b374  mov     rbx, rcx
0x18002b377  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18002b381  lfence
0x18002b384  add     rcx, rcx
0x18002b387  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002b38c  mov     r14, rax
0x18002b38f  mov     [rdi], rax
0x18002b392  lfence
0x18002b395  mov     [rdi+18h], rbx
0x18002b399  mov     rdx, rsi; Src
0x18002b39c  lea     rbx, [r15+r15]
0x18002b3a0  mov     [rdi+10h], rbp
0x18002b3a4  mov     r8, rbx; Size
0x18002b3a7  mov     rcx, r14; void *
0x18002b3aa  call    cs:__imp_memcpy
0x18002b3b0  lea     r8, [r12+r12]; Size
0x18002b3b4  lea     rcx, [rbx+r14]; void *
0x18002b3b8  lea     rdx, aDiagnosticshub_2; "\\DiagnosticsHub.Packaging.dll"
0x18002b3bf  call    cs:__imp_memcpy
0x18002b3c5  mov     rbx, [rsp+68h+arg_10]
0x18002b3cd  mov     rax, rdi
0x18002b3d0  mov     [r14+rbp*2], r13w
0x18002b3d5  add     rsp, 30h
0x18002b3d9  pop     r15
0x18002b3db  pop     r14
0x18002b3dd  pop     r13
0x18002b3df  pop     r12
0x18002b3e1  pop     rdi
0x18002b3e2  pop     rsi
0x18002b3e3  pop     rbp
0x18002b3e4  retn
0x18002b3e5  mov     eax, 0Ah
0x18002b3ea  cmp     rbx, rax
0x18002b3ed  cmovb   rbx, rax
0x18002b3f1  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002b3fb  lea     rcx, [rbx+1]
0x18002b3ff  cmp     rcx, rax
0x18002b402  ja      short loc_18002B40F
0x18002b404  jmp     loc_18002B381
0x18002b409  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18002b40f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
