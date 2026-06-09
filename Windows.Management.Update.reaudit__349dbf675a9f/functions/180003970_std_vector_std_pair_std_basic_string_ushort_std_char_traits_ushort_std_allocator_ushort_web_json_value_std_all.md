# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Emplace_reallocate<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> &&)

- ea: `0x180003970`
- end: `0x180003c36`
- name: `??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180005690`

## callees

- `0x180002c74`
- `0x180002cac`
- `0x180003970`
- `0x180004730`
- `0x180005e40`
- `0x18001da08`
- `0x18001da30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180003c23`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180003c23`

## pseudocode

```c
char *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // r14
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r15
  void *v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  char *v16; // r13
  _QWORD *v17; // rbx
  __int64 v18; // rax
  _QWORD *v19; // rdx
  _QWORD *v20; // rcx
  _QWORD *v21; // rbx
  _QWORD *i; // r14
  __int64 v23; // rcx
  _QWORD *v24; // r8
  unsigned __int64 v25; // rdx
  char *v27; // [rsp+20h] [rbp-58h]
  __int64 v28; // [rsp+28h] [rbp-50h]
  unsigned __int64 v30; // [rsp+88h] [rbp+10h]
  __int64 v31; // [rsp+90h] [rbp+18h]
  _QWORD *v32; // [rsp+98h] [rbp+20h]

  v31 = a3;
  v5 = ((__int64)a2 - *a1) / 40;
  v6 = (a1[1] - *a1) / 40LL;
  if ( v6 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v7 = v6 + 1;
  v28 = v6 + 1;
  v8 = (a1[2] - *a1) / 40LL;
  v9 = v8 >> 1;
  if ( v8 > 0x666666666666666LL - (v8 >> 1) )
    goto LABEL_30;
  v10 = v7;
  if ( v9 + v8 >= v7 )
    v10 = v9 + v8;
  if ( v10 > 0x666666666666666LL )
    goto LABEL_30;
  v11 = 40 * v10;
  v30 = v10;
  if ( 40 * v10 < 0x1000 )
  {
    if ( v11 )
    {
      v15 = operator new(40 * v10);
      v32 = v15;
      a3 = v31;
    }
    else
    {
      v15 = 0;
      v32 = 0;
    }
    v30 = v10;
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_30:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_29;
  v15 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v15 - 1) = v12;
  v32 = v15;
  a3 = v31;
LABEL_14:
  v16 = (char *)&v15[5 * v5];
  v17 = v16 + 40;
  try
  {
    *(_OWORD *)v16 = 0;
    *((_QWORD *)v16 + 2) = 0;
    *((_QWORD *)v16 + 3) = 0;
    *(_OWORD *)v16 = *(_OWORD *)a3;
    *((_OWORD *)v16 + 1) = *(_OWORD *)(a3 + 16);
    *(_QWORD *)(a3 + 16) = 0;
    *(_QWORD *)(a3 + 24) = 7;
    *(_WORD *)a3 = 0;
    v18 = *(_QWORD *)(a3 + 32);
    *(_QWORD *)(a3 + 32) = 0;
    *((_QWORD *)v16 + 4) = v18;
    v27 = (char *)&v15[5 * v5];
    v19 = (_QWORD *)a1[1];
    v20 = (_QWORD *)*a1;
    if ( a2 == v19 )
    {
      v17 = v15;
    }
    else
    {
      std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
        v20,
        a2,
        v15,
        a1);
      v27 = (char *)v15;
      v20 = a2;
      v19 = (_QWORD *)a1[1];
    }
    std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
      v20,
      v19,
      v17,
      a1);
  }
  catch ( ... )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,web::json::value>>>(v27, v16 + 40, a1);
    std::allocator<std::pair<std::wstring,web::json::value>>::deallocate(a1, v32, v30);
    throw;
  }
  v21 = (_QWORD *)*a1;
  if ( *a1 )
  {
    for ( i = (_QWORD *)a1[1]; v21 != i; v21 += 5 )
    {
      v23 = v21[4];
      if ( v23 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 192LL))(v23, 1);
      std::wstring::_Tidy_deallocate(v21);
    }
    v24 = (_QWORD *)*a1;
    v25 = 40 * ((a1[2] - *a1) / 40LL);
    if ( v25 < 0x1000 )
      goto LABEL_27;
    v13 = v25 + 39;
    v14 = *(v24 - 1);
    if ( (unsigned __int64)v24 - v14 - 8 <= 0x1F )
    {
      v24 = (_QWORD *)*(v24 - 1);
LABEL_27:
      operator delete(v24);
      goto LABEL_28;
    }
LABEL_29:
    _o__invalid_parameter_noinfo_noreturn(v14, v13);
    __debugbreak();
  }
LABEL_28:
  *a1 = v15;
  a1[1] = &v15[5 * v28];
  a1[2] = &v15[v11 / 8];
  return v16;
}

```

## disassembly

```asm
0x180003970  mov     [rsp+arg_10], r8
0x180003975  mov     [rsp+arg_0], rcx
0x18000397a  push    rbx
0x18000397b  push    rsi
0x18000397c  push    rdi
0x18000397d  push    r12
0x18000397f  push    r13
0x180003981  push    r14
0x180003983  push    r15
0x180003985  sub     rsp, 40h
0x180003989  mov     r12, rdx
0x18000398c  mov     rsi, rcx
0x18000398f  mov     r10, [rcx]
0x180003992  mov     r9, rdx
0x180003995  sub     r9, r10
0x180003998  mov     rbx, 6666666666666667h
0x1800039a2  mov     rax, rbx
0x1800039a5  imul    r9
0x1800039a8  mov     r14, rdx
0x1800039ab  sar     r14, 4
0x1800039af  mov     rax, r14
0x1800039b2  shr     rax, 3Fh
0x1800039b6  add     r14, rax
0x1800039b9  mov     rcx, [rcx+8]
0x1800039bd  sub     rcx, r10
0x1800039c0  mov     rax, rbx
0x1800039c3  imul    rcx
0x1800039c6  sar     rdx, 4
0x1800039ca  mov     rax, rdx
0x1800039cd  shr     rax, 3Fh
0x1800039d1  add     rdx, rax
0x1800039d4  mov     r11, 666666666666666h
0x1800039de  cmp     rdx, r11
0x1800039e1  jz      loc_180003C30
0x1800039e7  lea     r9, [rdx+1]
0x1800039eb  mov     [rsp+78h+var_50], r9
0x1800039f0  mov     rcx, [rsi+10h]
0x1800039f4  sub     rcx, r10
0x1800039f7  mov     rax, rbx
0x1800039fa  imul    rcx
0x1800039fd  sar     rdx, 4
0x180003a01  mov     rax, rdx
0x180003a04  shr     rax, 3Fh
0x180003a08  add     rdx, rax
0x180003a0b  mov     rcx, rdx
0x180003a0e  shr     rcx, 1
0x180003a11  mov     rax, r11
0x180003a14  sub     rax, rcx
0x180003a17  cmp     rdx, rax
0x180003a1a  ja      loc_180003C2A
0x180003a20  lea     rax, [rcx+rdx]
0x180003a24  mov     rbx, r9
0x180003a27  cmp     rax, r9
0x180003a2a  cmovnb  rbx, rax
0x180003a2e  cmp     rbx, r11
0x180003a31  ja      loc_180003C2A
0x180003a37  lea     rax, [rbx+rbx*4]
0x180003a3b  lea     r15, ds:0[rax*8]
0x180003a43  mov     [rsp+78h+arg_8], rbx
0x180003a4b  cmp     r15, 1000h
0x180003a52  jb      short loc_180003A8F
0x180003a54  lea     rcx, [r15+27h]; Size
0x180003a58  cmp     rcx, r15
0x180003a5b  jbe     loc_180003C2A
0x180003a61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a66  test    rax, rax
0x180003a69  jz      loc_180003C23
0x180003a6f  lea     rdi, [rax+27h]
0x180003a73  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180003a77  mov     [rdi-8], rax
0x180003a7b  mov     [rsp+78h+arg_18], rdi
0x180003a83  xor     ecx, ecx
0x180003a85  mov     r8, [rsp+78h+arg_10]
0x180003a8d  jmp     short loc_180003AC7
0x180003a8f  test    r15, r15
0x180003a92  jz      short loc_180003AB3
0x180003a94  mov     rcx, r15; Size
0x180003a97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a9c  mov     rdi, rax
0x180003a9f  mov     [rsp+78h+arg_18], rax
0x180003aa7  xor     ecx, ecx
0x180003aa9  mov     r8, [rsp+78h+arg_10]
0x180003ab1  jmp     short loc_180003ABF
0x180003ab3  xor     ecx, ecx
0x180003ab5  mov     edi, ecx
0x180003ab7  mov     [rsp+78h+arg_18], rcx
0x180003abf  mov     [rsp+78h+arg_8], rbx
0x180003ac7  lea     rax, [r14+r14*4]
0x180003acb  lea     r13, [rdi+rax*8]
0x180003acf  lea     rbx, [r13+28h]
0x180003ad3  mov     [rsp+78h+var_48], rbx
0x180003ad8  xorps   xmm0, xmm0
0x180003adb  movups  xmmword ptr [r13+0], xmm0
0x180003ae0  mov     [r13+10h], rcx
0x180003ae4  mov     [r13+18h], rcx
0x180003ae8  movups  xmm0, xmmword ptr [r8]
0x180003aec  movups  xmmword ptr [r13+0], xmm0
0x180003af1  movups  xmm1, xmmword ptr [r8+10h]
0x180003af6  movups  xmmword ptr [r13+10h], xmm1
0x180003afb  mov     [r8+10h], rcx
0x180003aff  mov     qword ptr [r8+18h], 7
0x180003b07  mov     [r8], cx
0x180003b0b  mov     rax, [r8+20h]
0x180003b0f  mov     [r8+20h], rcx
0x180003b13  mov     [r13+20h], rax
0x180003b17  mov     [rsp+78h+var_58], r13
0x180003b1c  mov     rdx, [rsi+8]
0x180003b20  mov     rcx, [rsi]
0x180003b23  cmp     r12, rdx
0x180003b26  jnz     short loc_180003B2D
0x180003b28  mov     rbx, rdi
0x180003b2b  jmp     short loc_180003B47
0x180003b2d  mov     r9, rsi
0x180003b30  mov     r8, rdi
0x180003b33  mov     rdx, r12
0x180003b36  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x180003b3b  mov     [rsp+78h+var_58], rdi
0x180003b40  mov     rcx, r12
0x180003b43  mov     rdx, [rsi+8]
0x180003b47  mov     r9, rsi
0x180003b4a  mov     r8, rbx
0x180003b4d  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x180003b52  nop
0x180003b53  mov     rbx, [rsi]
0x180003b56  test    rbx, rbx
0x180003b59  jz      loc_180003BF4
0x180003b5f  mov     r14, [rsi+8]
0x180003b63  cmp     rbx, r14
0x180003b66  jz      short loc_180003B9E
0x180003b68  nop     dword ptr [rax+rax+00000000h]
0x180003b70  mov     rcx, [rbx+20h]
0x180003b74  test    rcx, rcx
0x180003b77  jz      short loc_180003B8D
0x180003b79  mov     rax, [rcx]
0x180003b7c  mov     edx, 1
0x180003b81  mov     rax, [rax+0C0h]
0x180003b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8d  mov     rcx, rbx
0x180003b90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003b95  add     rbx, 28h ; '('
0x180003b99  cmp     rbx, r14
0x180003b9c  jnz     short loc_180003B70
0x180003b9e  mov     r8, [rsi]
0x180003ba1  mov     rcx, [rsi+10h]
0x180003ba5  sub     rcx, r8
0x180003ba8  mov     rax, 6666666666666667h
0x180003bb2  imul    rcx
0x180003bb5  sar     rdx, 4
0x180003bb9  mov     rax, rdx
0x180003bbc  shr     rax, 3Fh
0x180003bc0  add     rdx, rax
0x180003bc3  lea     rdx, [rdx+rdx*4]
0x180003bc7  shl     rdx, 3
0x180003bcb  cmp     rdx, 1000h
0x180003bd2  jb      short loc_180003BEC
0x180003bd4  add     rdx, 27h ; '''; unsigned __int64
0x180003bd8  mov     rcx, [r8-8]
0x180003bdc  sub     r8, rcx
0x180003bdf  lea     rax, [r8-8]
0x180003be3  cmp     rax, 1Fh
0x180003be7  ja      short loc_180003C23
0x180003be9  mov     r8, rcx
0x180003bec  mov     rcx, r8; void *
0x180003bef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003bf4  mov     [rsi], rdi
0x180003bf7  mov     rax, [rsp+78h+var_50]
0x180003bfc  lea     rcx, [rax+rax*4]
0x180003c00  lea     rdx, [rdi+rcx*8]
0x180003c04  mov     [rsi+8], rdx
0x180003c08  lea     rcx, [r15+rdi]
0x180003c0c  mov     [rsi+10h], rcx
0x180003c10  mov     rax, r13
0x180003c13  add     rsp, 40h
0x180003c17  pop     r15
0x180003c19  pop     r14
0x180003c1b  pop     r13
0x180003c1d  pop     r12
0x180003c1f  pop     rdi
0x180003c20  pop     rsi
0x180003c21  pop     rbx
0x180003c22  retn
0x180003c23  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180003c29  int     3; Trap to Debugger
0x180003c2a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180003c30  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
```
