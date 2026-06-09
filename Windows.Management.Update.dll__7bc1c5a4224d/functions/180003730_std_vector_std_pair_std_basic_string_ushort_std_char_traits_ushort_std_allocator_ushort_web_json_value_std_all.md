# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Emplace_reallocate<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> * const,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> &&)

- ea: `0x180003730`
- end: `0x1800039b4`
- name: `??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z`
- size: `644`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800050b0`

## callees

- `0x180002cc0`
- `0x180002cfc`
- `0x180003730`
- `0x180004430`
- `0x180005860`
- `0x18001c7f4`
- `0x18001c81c`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  void *v3; // rbp
  __int64 v7; // r9
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // r15
  bool v12; // cf
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r14
  _QWORD *v15; // rsi
  void *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // r12
  __int64 v19; // rax
  char *v20; // rbp
  __int64 v21; // rax
  _QWORD *v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 i; // rbp
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned __int64 v29; // rdx
  void *v30; // rcx

  v3 = (void *)*a1;
  v7 = (a1[1] - *a1) / 40LL;
  if ( v7 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v8 = (a1[2] - (_QWORD)v3) / 40LL;
  v9 = v8 >> 1;
  if ( v8 > 0x666666666666666LL - (v8 >> 1) )
    goto LABEL_28;
  v10 = v8 + v9;
  v11 = v7 + 1;
  v12 = v8 + v9 < v7 + 1;
  v13 = v7 + 1;
  if ( !v12 )
    v13 = v10;
  if ( v13 > 0x666666666666666LL )
    goto LABEL_28;
  v14 = 40 * v13;
  if ( !(40 * v13) )
  {
    v15 = 0;
    goto LABEL_13;
  }
  if ( v14 < 0x1000 )
  {
    v15 = operator new(40 * v13);
    goto LABEL_13;
  }
  if ( v14 + 39 < v14 )
LABEL_28:
    __scrt_throw_std_bad_array_new_length();
  v16 = operator new(v14 + 39);
  if ( !v16 )
    goto LABEL_23;
  v15 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v15 - 1) = v16;
LABEL_13:
  v17 = a1;
  v18 = (a2 - (__int64)v3) / 40;
  v19 = 5 * v18;
  *(_OWORD *)&v15[v19] = 0;
  v15[v19 + 2] = 0;
  v20 = (char *)&v15[5 * v18];
  *((_QWORD *)v20 + 3) = 0;
  *(_OWORD *)v20 = *(_OWORD *)a3;
  *((_OWORD *)v20 + 1) = *(_OWORD *)(a3 + 16);
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)a3 = 0;
  *(_QWORD *)(a3 + 24) = 7;
  v21 = *(_QWORD *)(a3 + 32);
  *(_QWORD *)(a3 + 32) = 0;
  v22 = v15;
  *((_QWORD *)v20 + 4) = v21;
  v23 = a1[1];
  v24 = *a1;
  if ( a2 != v23 )
  {
    std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
      v24,
      a2,
      v15,
      a1);
    v23 = a1[1];
    v22 = v20 + 40;
    v24 = a2;
    v17 = a1;
  }
  std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(
    v24,
    v23,
    v22,
    v17);
  v25 = *a1;
  if ( *a1 )
  {
    for ( i = a1[1]; v25 != i; v25 += 40 )
    {
      v27 = *(_QWORD *)(v25 + 32);
      if ( v27 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 192LL))(v27, 1);
      std::wstring::_Tidy_deallocate(v25);
    }
    v28 = *a1;
    v29 = 40 * ((a1[2] - *a1) / 40LL);
    if ( v29 < 0x1000 )
    {
      v30 = (void *)*a1;
      goto LABEL_25;
    }
    v30 = *(void **)(v28 - 8);
    if ( (unsigned __int64)(v28 - (_QWORD)v30 - 8) <= 0x1F )
    {
      v29 += 39LL;
LABEL_25:
      operator delete(v30, v29);
      goto LABEL_26;
    }
LABEL_23:
    __fastfail(5u);
  }
LABEL_26:
  *a1 = v15;
  a1[1] = &v15[5 * v11];
  a1[2] = &v15[v14 / 8];
  return (char *)&v15[5 * v18];
}

```

## disassembly

```asm
0x180003730  push    rbx
0x180003732  push    rbp
0x180003733  push    rdi
0x180003734  push    r12
0x180003736  push    r13
0x180003738  sub     rsp, 20h
0x18000373c  mov     rbp, [rcx]
0x18000373f  mov     r12, 6666666666666667h
0x180003749  mov     r9, [rcx+8]
0x18000374d  mov     rax, r12
0x180003750  sub     r9, rbp
0x180003753  mov     rbx, rdx
0x180003756  imul    r9
0x180003759  mov     r13, r8
0x18000375c  mov     rdi, rcx
0x18000375f  mov     r9, rdx
0x180003762  mov     r8, 666666666666666h
0x18000376c  sar     r9, 4
0x180003770  mov     rax, r9
0x180003773  shr     rax, 3Fh
0x180003777  add     r9, rax
0x18000377a  cmp     r9, r8
0x18000377d  jz      loc_1800039A8
0x180003783  mov     rcx, [rcx+10h]
0x180003787  mov     rax, r12
0x18000378a  sub     rcx, rbp
0x18000378d  mov     [rsp+48h+arg_0], rsi
0x180003792  imul    rcx
0x180003795  mov     [rsp+48h+arg_8], r14
0x18000379a  sar     rdx, 4
0x18000379e  mov     rax, rdx
0x1800037a1  mov     [rsp+48h+arg_10], r15
0x1800037a6  shr     rax, 3Fh
0x1800037aa  add     rdx, rax
0x1800037ad  mov     rax, r8
0x1800037b0  mov     rcx, rdx
0x1800037b3  shr     rcx, 1
0x1800037b6  sub     rax, rcx
0x1800037b9  cmp     rdx, rax
0x1800037bc  ja      loc_1800039AE
0x1800037c2  lea     rax, [rdx+rcx]
0x1800037c6  lea     r15, [r9+1]
0x1800037ca  cmp     rax, r15
0x1800037cd  mov     rcx, r15
0x1800037d0  cmovnb  rcx, rax
0x1800037d4  cmp     rcx, r8
0x1800037d7  ja      loc_1800039AE
0x1800037dd  lea     rax, [rcx+rcx*4]
0x1800037e1  xor     r8d, r8d
0x1800037e4  lea     r14, ds:0[rax*8]
0x1800037ec  test    r14, r14
0x1800037ef  jnz     short loc_1800037F6
0x1800037f1  mov     esi, r8d
0x1800037f4  jmp     short loc_180003836
0x1800037f6  cmp     r14, 1000h
0x1800037fd  jb      short loc_180003828
0x1800037ff  lea     rcx, [r14+27h]; Size
0x180003803  cmp     rcx, r14
0x180003806  jbe     loc_1800039AE
0x18000380c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003811  test    rax, rax
0x180003814  jz      loc_18000395F
0x18000381a  lea     rsi, [rax+27h]
0x18000381e  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180003822  mov     [rsi-8], rax
0x180003826  jmp     short loc_180003833
0x180003828  mov     rcx, r14; Size
0x18000382b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003830  mov     rsi, rax
0x180003833  xor     r8d, r8d
0x180003836  mov     rax, r12
0x180003839  xorps   xmm0, xmm0
0x18000383c  mov     rcx, rbx
0x18000383f  mov     r9, rdi
0x180003842  sub     rcx, rbp
0x180003845  imul    rcx
0x180003848  mov     r12, rdx
0x18000384b  sar     r12, 4
0x18000384f  mov     rax, r12
0x180003852  shr     rax, 3Fh
0x180003856  add     r12, rax
0x180003859  lea     rax, [r12+r12*4]
0x18000385d  movups  xmmword ptr [rsi+rax*8], xmm0
0x180003861  mov     [rsi+rax*8+10h], r8
0x180003866  lea     rbp, [rsi+rax*8]
0x18000386a  mov     [rbp+18h], r8
0x18000386e  movups  xmm0, xmmword ptr [r13+0]
0x180003873  movups  xmmword ptr [rbp+0], xmm0
0x180003877  movups  xmm1, xmmword ptr [r13+10h]
0x18000387c  movups  xmmword ptr [rbp+10h], xmm1
0x180003880  mov     [r13+10h], r8
0x180003884  mov     [r13+0], r8w
0x180003889  mov     qword ptr [r13+18h], 7
0x180003891  mov     rax, [r13+20h]
0x180003895  mov     [r13+20h], r8
0x180003899  mov     r8, rsi
0x18000389c  mov     [rbp+20h], rax
0x1800038a0  mov     rdx, [rdi+8]
0x1800038a4  mov     rcx, [rdi]
0x1800038a7  cmp     rbx, rdx
0x1800038aa  jz      short loc_1800038C2
0x1800038ac  mov     rdx, rbx
0x1800038af  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x1800038b4  mov     rdx, [rdi+8]
0x1800038b8  lea     r8, [rbp+28h]
0x1800038bc  mov     rcx, rbx
0x1800038bf  mov     r9, rdi
0x1800038c2  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> *,std::allocator<std::pair<std::wstring,web::json::value>> &)
0x1800038c7  mov     rbx, [rdi]
0x1800038ca  test    rbx, rbx
0x1800038cd  jz      loc_18000396E
0x1800038d3  mov     rbp, [rdi+8]
0x1800038d7  cmp     rbx, rbp
0x1800038da  jz      short loc_18000390E
0x1800038dc  nop     dword ptr [rax+00h]
0x1800038e0  mov     rcx, [rbx+20h]
0x1800038e4  test    rcx, rcx
0x1800038e7  jz      short loc_1800038FD
0x1800038e9  mov     rax, [rcx]
0x1800038ec  mov     edx, 1
0x1800038f1  mov     rax, [rax+0C0h]
0x1800038f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fd  mov     rcx, rbx
0x180003900  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003905  add     rbx, 28h ; '('
0x180003909  cmp     rbx, rbp
0x18000390c  jnz     short loc_1800038E0
0x18000390e  mov     r8, [rdi]
0x180003911  mov     rax, 6666666666666667h
0x18000391b  mov     rcx, [rdi+10h]
0x18000391f  sub     rcx, r8
0x180003922  imul    rcx
0x180003925  sar     rdx, 4
0x180003929  mov     rax, rdx
0x18000392c  shr     rax, 3Fh
0x180003930  add     rdx, rax
0x180003933  lea     rax, [rdx+rdx*4]
0x180003937  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000393f  cmp     rdx, 1000h
0x180003946  jb      short loc_180003966
0x180003948  mov     rcx, [r8-8]
0x18000394c  sub     r8, rcx
0x18000394f  sub     r8, 8
0x180003953  cmp     r8, 1Fh
0x180003957  ja      short loc_18000395F
0x180003959  add     rdx, 27h ; '''
0x18000395d  jmp     short loc_180003969
0x18000395f  mov     ecx, 5
0x180003964  int     29h; Win8: RtlFailFast(ecx)
0x180003966  mov     rcx, r8; void *
0x180003969  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000396e  lea     rax, [r15+r15*4]
0x180003972  mov     [rdi], rsi
0x180003975  mov     r15, [rsp+48h+arg_10]
0x18000397a  lea     rcx, [rsi+rax*8]
0x18000397e  lea     rax, [r14+rsi]
0x180003982  mov     [rdi+8], rcx
0x180003986  mov     r14, [rsp+48h+arg_8]
0x18000398b  mov     [rdi+10h], rax
0x18000398f  lea     rax, [r12+r12*4]
0x180003993  lea     rax, [rsi+rax*8]
0x180003997  mov     rsi, [rsp+48h+arg_0]
0x18000399c  add     rsp, 20h
0x1800039a0  pop     r13
0x1800039a2  pop     r12
0x1800039a4  pop     rdi
0x1800039a5  pop     rbp
0x1800039a6  pop     rbx
0x1800039a7  retn
0x1800039a8  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x1800039ae  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
