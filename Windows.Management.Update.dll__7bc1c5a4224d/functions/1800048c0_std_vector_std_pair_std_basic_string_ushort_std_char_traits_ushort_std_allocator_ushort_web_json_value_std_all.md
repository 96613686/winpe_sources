# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>(std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>> const &)

- ea: `0x1800048c0`
- end: `0x180004a39`
- name: `??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `377`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005a50`

## callees

- `0x180002cfc`
- `0x1800048c0`
- `0x180005860`
- `0x18001c7f4`
- `0x1800210f8`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        __int64 *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdi
  _QWORD *v6; // rbx
  void *v7; // rax
  __int64 v8; // rbp
  __int64 i; // rsi
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+88h] [rbp+10h]
  _QWORD *v15; // [rsp+90h] [rbp+18h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (a2[1] - *a2) / 40;
  if ( v4 )
  {
    if ( v4 > 0x666666666666666LL )
      std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
    v5 = 40 * v4;
    if ( 40 * v4 )
    {
      if ( v5 < 0x1000 )
      {
        v6 = operator new(40 * v4);
      }
      else
      {
        if ( v5 + 39 < v5 )
          __scrt_throw_std_bad_array_new_length();
        v7 = operator new(v5 + 39);
        if ( !v7 )
          __fastfail(5u);
        v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v6 - 1) = v7;
      }
    }
    else
    {
      v6 = 0;
    }
    *a1 = v6;
    a1[1] = v6;
    a1[2] = &v6[v5 / 8];
    v14 = a1;
    v8 = a2[1];
    for ( i = *a2; i != v8; i += 40 )
    {
      v15 = v6;
      std::wstring::wstring(v6, i);
      v10 = (__int64 *)(***(__int64 (__fastcall ****)(_QWORD, __int64 *))(i + 32))(*(_QWORD *)(i + 32), &v13);
      v11 = *v10;
      *v10 = 0;
      v6[4] = v11;
      if ( v13 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 192LL))(v13, 1);
      v6 += 5;
    }
    a1[1] = v6;
  }
  return a1;
}

```

## disassembly

```asm
0x1800048c0  push    rbx
0x1800048c2  push    rbp
0x1800048c3  push    rsi
0x1800048c4  push    rdi
0x1800048c5  push    r14
0x1800048c7  push    r15
0x1800048c9  sub     rsp, 48h
0x1800048cd  mov     rsi, rdx
0x1800048d0  mov     r14, rcx
0x1800048d3  xor     r15d, r15d
0x1800048d6  mov     [rcx], r15
0x1800048d9  mov     [rcx+8], r15
0x1800048dd  mov     [rcx+10h], r15
0x1800048e1  mov     r8, [rdx+8]
0x1800048e5  sub     r8, [rdx]
0x1800048e8  mov     rax, 6666666666666667h
0x1800048f2  imul    r8
0x1800048f5  sar     rdx, 4
0x1800048f9  mov     rax, rdx
0x1800048fc  shr     rax, 3Fh
0x180004900  add     rdx, rax
0x180004903  jz      loc_180004A1D
0x180004909  mov     rax, 666666666666666h
0x180004913  cmp     rdx, rax
0x180004916  ja      loc_180004A33
0x18000491c  lea     rax, [rdx+rdx*4]
0x180004920  lea     rdi, ds:0[rax*8]
0x180004928  test    rdi, rdi
0x18000492b  jnz     short loc_180004932
0x18000492d  mov     ebx, r15d
0x180004930  jmp     short loc_180004972
0x180004932  cmp     rdi, 1000h
0x180004939  jb      short loc_180004967
0x18000493b  lea     rcx, [rdi+27h]; Size
0x18000493f  cmp     rcx, rdi
0x180004942  jbe     loc_180004A2D
0x180004948  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000494d  test    rax, rax
0x180004950  jnz     short loc_180004959
0x180004952  mov     ecx, 5
0x180004957  int     29h; Win8: RtlFailFast(ecx)
0x180004959  lea     rbx, [rax+27h]
0x18000495d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180004961  mov     [rbx-8], rax
0x180004965  jmp     short loc_180004972
0x180004967  mov     rcx, rdi; Size
0x18000496a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000496f  mov     rbx, rax
0x180004972  mov     [r14], rbx
0x180004975  mov     [r14+8], rbx
0x180004979  lea     rax, [rdi+rbx]
0x18000497d  mov     [r14+10h], rax
0x180004981  mov     [rsp+78h+arg_8], r14
0x180004989  mov     rbp, [rsi+8]
0x18000498d  mov     rsi, [rsi]
0x180004990  mov     [rsp+78h+var_58], rbx
0x180004995  mov     [rsp+78h+var_50], rbx
0x18000499a  mov     [rsp+78h+var_48], r14
0x18000499f  cmp     rsi, rbp
0x1800049a2  jz      short loc_180004A19
0x1800049a4  nop     dword ptr [rax+00h]
0x1800049a8  nop     dword ptr [rax+rax+00000000h]
0x1800049b0  mov     [rsp+78h+arg_10], rbx
0x1800049b8  mov     rdx, rsi
0x1800049bb  mov     rcx, rbx
0x1800049be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800049c3  nop
0x1800049c4  mov     rcx, [rsi+20h]
0x1800049c8  mov     rax, [rcx]
0x1800049cb  lea     rdx, [rsp+78h+arg_0]
0x1800049d3  mov     rax, [rax]
0x1800049d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049db  mov     rcx, [rax]
0x1800049de  mov     [rax], r15
0x1800049e1  mov     [rbx+20h], rcx
0x1800049e5  mov     rcx, [rsp+78h+arg_0]
0x1800049ed  test    rcx, rcx
0x1800049f0  jz      short loc_180004A07
0x1800049f2  mov     rax, [rcx]
0x1800049f5  mov     edx, 1
0x1800049fa  mov     rax, [rax+0C0h]
0x180004a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a06  nop
0x180004a07  add     rbx, 28h ; '('
0x180004a0b  mov     [rsp+78h+var_50], rbx
0x180004a10  add     rsi, 28h ; '('
0x180004a14  cmp     rsi, rbp
0x180004a17  jnz     short loc_1800049B0
0x180004a19  mov     [r14+8], rbx
0x180004a1d  mov     rax, r14
0x180004a20  add     rsp, 48h
0x180004a24  pop     r15
0x180004a26  pop     r14
0x180004a28  pop     rdi
0x180004a29  pop     rsi
0x180004a2a  pop     rbp
0x180004a2b  pop     rbx
0x180004a2c  retn
0x180004a2d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180004a33  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
```
