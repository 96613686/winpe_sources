# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>(std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>> const &)

- ea: `0x180004ed0`
- end: `0x180005054`
- name: `??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006030`

## callees

- `0x180002cac`
- `0x180004ed0`
- `0x180005e40`
- `0x18001da08`
- `0x1800226b4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004f66`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180004f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        __int64 *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  void *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rdi
  __int64 v10; // rbp
  __int64 i; // rsi
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v16; // [rsp+88h] [rbp+10h]
  _QWORD *v17; // [rsp+90h] [rbp+18h]
  char *v18; // [rsp+98h] [rbp+20h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (a2[1] - *a2) / 40;
  if ( v4 )
  {
    if ( v4 > 0x666666666666666LL )
      std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
    v5 = 40 * v4;
    if ( 40 * v4 < 0x1000 )
    {
      if ( v5 )
        v9 = operator new(40 * v4);
      else
        v9 = 0;
    }
    else
    {
      if ( v5 + 39 < v5 )
        __scrt_throw_std_bad_array_new_length();
      v6 = operator new(v5 + 39);
      if ( !v6 )
      {
        _o__invalid_parameter_noinfo_noreturn(v8, v7);
        __debugbreak();
      }
      v9 = (_QWORD *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v9 - 1) = v6;
    }
    *a1 = v9;
    a1[1] = v9;
    a1[2] = &v9[v5 / 8];
    v16 = a1;
    v10 = a2[1];
    for ( i = *a2; i != v10; i += 40 )
    {
      v17 = v9;
      std::wstring::wstring(v9, i);
      v18 = (char *)(v9 + 4);
      v12 = (__int64 *)(***(__int64 (__fastcall ****)(_QWORD, __int64 *))(i + 32))(*(_QWORD *)(i + 32), &v15);
      v13 = *v12;
      *v12 = 0;
      v9[4] = v13;
      if ( v15 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 192LL))(v15, 1);
      v9 += 5;
    }
    a1[1] = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x180004ed0  push    rbx
0x180004ed2  push    rbp
0x180004ed3  push    rsi
0x180004ed4  push    rdi
0x180004ed5  push    r14
0x180004ed7  push    r15
0x180004ed9  sub     rsp, 48h
0x180004edd  mov     rsi, rdx
0x180004ee0  mov     r14, rcx
0x180004ee3  xor     r15d, r15d
0x180004ee6  mov     [rcx], r15
0x180004ee9  mov     [rcx+8], r15
0x180004eed  mov     [rcx+10h], r15
0x180004ef1  mov     r8, [rdx+8]
0x180004ef5  sub     r8, [rdx]
0x180004ef8  mov     rax, 6666666666666667h
0x180004f02  imul    r8
0x180004f05  sar     rdx, 4
0x180004f09  mov     rax, rdx
0x180004f0c  shr     rax, 3Fh
0x180004f10  add     rdx, rax
0x180004f13  jz      loc_180005038
0x180004f19  mov     rax, 666666666666666h
0x180004f23  cmp     rdx, rax
0x180004f26  ja      loc_18000504E
0x180004f2c  lea     rax, [rdx+rdx*4]
0x180004f30  lea     rbx, ds:0[rax*8]
0x180004f38  cmp     rbx, 1000h
0x180004f3f  jb      short loc_180004F6D
0x180004f41  lea     rcx, [rbx+27h]; Size
0x180004f45  cmp     rcx, rbx
0x180004f48  jbe     loc_180005048
0x180004f4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f53  test    rax, rax
0x180004f56  jz      short loc_180004F66
0x180004f58  lea     rdi, [rax+27h]
0x180004f5c  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180004f60  mov     [rdi-8], rax
0x180004f64  jmp     short loc_180004F82
0x180004f66  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180004f6c  int     3; Trap to Debugger
0x180004f6d  test    rbx, rbx
0x180004f70  jz      short loc_180004F7F
0x180004f72  mov     rcx, rbx; Size
0x180004f75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f7a  mov     rdi, rax
0x180004f7d  jmp     short loc_180004F82
0x180004f7f  mov     rdi, r15
0x180004f82  mov     [r14], rdi
0x180004f85  mov     [r14+8], rdi
0x180004f89  lea     rax, [rbx+rdi]
0x180004f8d  mov     [r14+10h], rax
0x180004f91  mov     [rsp+78h+arg_8], r14
0x180004f99  mov     rbp, [rsi+8]
0x180004f9d  mov     rsi, [rsi]
0x180004fa0  mov     [rsp+78h+var_58], rdi
0x180004fa5  mov     [rsp+78h+var_50], rdi
0x180004faa  mov     [rsp+78h+var_48], r14
0x180004faf  cmp     rsi, rbp
0x180004fb2  jz      loc_180005034
0x180004fb8  nop     dword ptr [rax+rax+00000000h]
0x180004fc0  mov     [rsp+78h+arg_10], rdi
0x180004fc8  mov     rdx, rsi
0x180004fcb  mov     rcx, rdi
0x180004fce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180004fd3  nop
0x180004fd4  lea     rbx, [rdi+20h]
0x180004fd8  mov     [rsp+78h+arg_18], rbx
0x180004fe0  mov     rcx, [rsi+20h]
0x180004fe4  mov     rax, [rcx]
0x180004fe7  lea     rdx, [rsp+78h+arg_0]
0x180004fef  mov     rax, [rax]
0x180004ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff7  mov     rcx, [rax]
0x180004ffa  mov     [rax], r15
0x180004ffd  mov     [rbx], rcx
0x180005000  mov     rcx, [rsp+78h+arg_0]
0x180005008  test    rcx, rcx
0x18000500b  jz      short loc_180005022
0x18000500d  mov     rax, [rcx]
0x180005010  mov     edx, 1
0x180005015  mov     rax, [rax+0C0h]
0x18000501c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005021  nop
0x180005022  add     rdi, 28h ; '('
0x180005026  mov     [rsp+78h+var_50], rdi
0x18000502b  add     rsi, 28h ; '('
0x18000502f  cmp     rsi, rbp
0x180005032  jnz     short loc_180004FC0
0x180005034  mov     [r14+8], rdi
0x180005038  mov     rax, r14
0x18000503b  add     rsp, 48h
0x18000503f  pop     r15
0x180005041  pop     r14
0x180005043  pop     rdi
0x180005044  pop     rsi
0x180005045  pop     rbp
0x180005046  pop     rbx
0x180005047  retn
0x180005048  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18000504e  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
```
