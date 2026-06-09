# web::json::object::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800050b0`
- end: `0x1800052c6`
- name: `??Aobject@json@web@@QEAAAEAVvalue@12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `534`
- prototype: `char *__fastcall(wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180006600`

## callees

- `0x1800028f0`
- `0x180002cfc`
- `0x180003590`
- `0x180003730`
- `0x1800039c0`
- `0x1800050b0`
- `0x180005ff0`
- `0x18001c81c`
- `0x1800210f8`
- `0x180023098`
- `0x18002a010`

## pseudocode

```c
char *__fastcall web::json::object::operator[](wchar_t *a1, __int64 a2)
{
  char *v4; // rbx
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rcx
  size_t v7; // r8
  bool v8; // cl
  wchar_t *v9; // rdi
  __m128i *v10; // r8
  wchar_t *v11; // r14
  __int8 *v12; // rdx
  __int64 v13; // rax
  wchar_t *S2[2]; // [rsp+20h] [rbp-39h] BYREF
  _OWORD v16[2]; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v17; // [rsp+50h] [rbp-9h]
  __m128i v18; // [rsp+58h] [rbp-1h] BYREF
  __m128i si128; // [rsp+68h] [rbp+Fh]
  wchar_t *v20; // [rsp+78h] [rbp+1Fh]

  web::json::object::find_insert_location(a1, S2, a2);
  v4 = (char *)S2[0];
  if ( S2[0] == *((wchar_t **)a1 + 1)
    || (*((_QWORD *)S2[0] + 3) <= 7u ? (v5 = S2[0]) : (v5 = *(const wchar_t **)S2[0]),
        *(_QWORD *)(a2 + 24) <= 7u ? (v6 = (const wchar_t *)a2) : (v6 = *(const wchar_t **)a2),
        (v7 = *(_QWORD *)(a2 + 16), v7 == *((_QWORD *)S2[0] + 2))
      ? (v7
       ? (v8 = wmemcmp(v6, v5, v7) != 0)
       : (v8 = 0))
      : (v8 = 1),
        v8) )
  {
    v9 = (wchar_t *)operator new(8u);
    S2[0] = v9;
    if ( v9 )
      *(_QWORD *)v9 = &web::json::details::_Null::`vftable';
    else
      v9 = 0;
    S2[0] = v9;
    std::wstring::wstring(&v18, a2);
    S2[0] = 0;
    v20 = v9;
    v10 = (__m128i *)*((_QWORD *)a1 + 1);
    if ( v10 == *((__m128i **)a1 + 2) )
    {
      v4 = std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
             a1,
             (__int64)v4,
             (__int64)&v18);
      v11 = v20;
    }
    else
    {
      v11 = 0;
      v20 = 0;
      if ( v4 == (char *)v10 )
      {
        *v10 = v18;
        v10[1] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v18.m128i_i16[0] = 0;
        v10[2].m128i_i64[0] = (__int64)v9;
        *((_QWORD *)a1 + 1) += 40LL;
      }
      else
      {
        S2[1] = a1;
        v16[0] = v18;
        v16[1] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v18.m128i_i16[0] = 0;
        v17 = v9;
        v12 = &v10[-3].m128i_i8[8];
        *v10 = *(__m128i *)((char *)v10 - 40);
        v10[1] = *(__m128i *)((char *)&v10[-2] + 8);
        *((_QWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 3) = 7;
        *(_WORD *)v12 = 0;
        v13 = v10[-1].m128i_i64[1];
        *((_QWORD *)v12 + 4) = 0;
        v10[2].m128i_i64[0] = v13;
        *((_QWORD *)a1 + 1) += 40LL;
        std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(
          (__int64)v4,
          (__int64)&v10[-3].m128i_i64[1],
          v10);
        std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(
          v4,
          (__int64)v16);
        if ( v17 )
          (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v17 + 192LL))(v17, 1);
        std::wstring::_Tidy_deallocate(v16);
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v11 + 192LL))(v11, 1);
    std::wstring::_Tidy_deallocate(&v18);
  }
  return v4 + 32;
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp-8+arg_10], rbx
0x1800050b5  push    rbp
0x1800050b6  push    rsi
0x1800050b7  push    rdi
0x1800050b8  push    r14
0x1800050ba  push    r15
0x1800050bc  lea     rbp, [rsp-37h]
0x1800050c1  sub     rsp, 90h
0x1800050c8  mov     rax, cs:__security_cookie
0x1800050cf  xor     rax, rsp
0x1800050d2  mov     [rbp+57h+var_30], rax
0x1800050d6  mov     r14, rdx
0x1800050d9  mov     rsi, rcx
0x1800050dc  xor     r15d, r15d
0x1800050df  mov     r8, rdx
0x1800050e2  lea     rdx, [rbp+57h+S2]
0x1800050e6  call    ?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; web::json::object::find_insert_location(std::wstring const &)
0x1800050eb  mov     rbx, [rbp+57h+S2]
0x1800050ef  cmp     rbx, [rsi+8]
0x1800050f3  jz      short loc_180005140
0x1800050f5  cmp     qword ptr [rbx+18h], 7
0x1800050fa  jbe     short loc_180005101
0x1800050fc  mov     rdx, [rbx]
0x1800050ff  jmp     short loc_180005104
0x180005101  mov     rdx, rbx; S2
0x180005104  cmp     qword ptr [r14+18h], 7
0x180005109  jbe     short loc_180005110
0x18000510b  mov     rcx, [r14]
0x18000510e  jmp     short loc_180005113
0x180005110  mov     rcx, r14; S1
0x180005113  mov     r8, [r14+10h]; N
0x180005117  cmp     r8, [rbx+10h]
0x18000511b  jz      short loc_180005124
0x18000511d  mov     ecx, 1
0x180005122  jmp     short loc_180005138
0x180005124  test    r8, r8
0x180005127  jnz     short loc_18000512E
0x180005129  mov     ecx, r15d
0x18000512c  jmp     short loc_180005138
0x18000512e  call    wmemcmp
0x180005133  test    eax, eax
0x180005135  setnz   cl
0x180005138  test    cl, cl
0x18000513a  jz      loc_18000529F
0x180005140  mov     ecx, 8; Size
0x180005145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000514a  mov     rdi, rax
0x18000514d  mov     [rbp+57h+S2], rax
0x180005151  test    rax, rax
0x180005154  jz      short loc_180005162
0x180005156  lea     rax, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18000515d  mov     [rdi], rax
0x180005160  jmp     short loc_180005165
0x180005162  mov     rdi, r15
0x180005165  mov     [rbp+57h+S2], rdi
0x180005169  mov     rdx, r14
0x18000516c  lea     rcx, [rbp+57h+var_58]
0x180005170  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180005175  mov     [rbp+57h+S2], r15
0x180005179  mov     [rbp+57h+var_38], rdi
0x18000517d  mov     r8, [rsi+8]
0x180005181  cmp     r8, [rsi+10h]
0x180005185  jz      loc_180005263
0x18000518b  mov     r14, r15
0x18000518e  mov     [rbp+57h+var_38], r15
0x180005192  cmp     rbx, r8
0x180005195  jnz     short loc_1800051C8
0x180005197  movups  xmm0, [rbp+57h+var_58]
0x18000519b  movups  xmmword ptr [r8], xmm0
0x18000519f  movups  xmm1, [rbp+57h+var_48]
0x1800051a3  movups  xmmword ptr [r8+10h], xmm1
0x1800051a8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800051b0  movdqu  [rbp+57h+var_48], xmm0
0x1800051b5  mov     word ptr [rbp+57h+var_58], r15w
0x1800051ba  mov     [r8+20h], rdi
0x1800051be  add     qword ptr [rsi+8], 28h ; '('
0x1800051c3  jmp     loc_180005279
0x1800051c8  mov     [rbp+57h+var_88], rsi
0x1800051cc  movups  xmm1, [rbp+57h+var_58]
0x1800051d0  movups  [rbp+57h+var_80], xmm1
0x1800051d4  movups  xmm0, [rbp+57h+var_48]
0x1800051d8  movups  [rbp+57h+var_70], xmm0
0x1800051dc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800051e4  movdqu  [rbp+57h+var_48], xmm1
0x1800051e9  mov     word ptr [rbp+57h+var_58], r15w
0x1800051ee  mov     [rbp+57h+var_60], rdi
0x1800051f2  lea     rdx, [r8-28h]
0x1800051f6  movups  xmm0, xmmword ptr [rdx]
0x1800051f9  movups  xmmword ptr [r8], xmm0
0x1800051fd  movups  xmm1, xmmword ptr [rdx+10h]
0x180005201  movups  xmmword ptr [r8+10h], xmm1
0x180005206  mov     [rdx+10h], r15
0x18000520a  mov     qword ptr [rdx+18h], 7
0x180005212  mov     [rdx], r15w
0x180005216  mov     rax, [rdx+20h]
0x18000521a  mov     [rdx+20h], r15
0x18000521e  mov     [r8+20h], rax
0x180005222  add     qword ptr [rsi+8], 28h ; '('
0x180005227  mov     rcx, rbx
0x18000522a  call    ??$_Move_backward_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@PEAU12@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@PEAU10@00@Z; std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *)
0x18000522f  lea     rdx, [rbp+57h+var_80]
0x180005233  mov     rcx, rbx
0x180005236  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(std::pair<std::wstring,web::json::value> &&)
0x18000523b  mov     rcx, [rbp+57h+var_60]
0x18000523f  test    rcx, rcx
0x180005242  jz      short loc_180005258
0x180005244  mov     rax, [rcx]
0x180005247  mov     edx, 1
0x18000524c  mov     rax, [rax+0C0h]
0x180005253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005258  lea     rcx, [rbp+57h+var_80]
0x18000525c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005261  jmp     short loc_180005279
0x180005263  lea     r8, [rbp+57h+var_58]
0x180005267  mov     rdx, rbx
0x18000526a  mov     rcx, rsi
0x18000526d  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> &&)
0x180005272  mov     rbx, rax
0x180005275  mov     r14, [rbp+57h+var_38]
0x180005279  test    r14, r14
0x18000527c  jz      short loc_180005295
0x18000527e  mov     rax, [r14]
0x180005281  mov     edx, 1
0x180005286  mov     rcx, r14
0x180005289  mov     rax, [rax+0C0h]
0x180005290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005295  lea     rcx, [rbp+57h+var_58]
0x180005299  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000529e  nop
0x18000529f  lea     rax, [rbx+20h]
0x1800052a3  mov     rcx, [rbp+57h+var_30]
0x1800052a7  xor     rcx, rsp; StackCookie
0x1800052aa  call    __security_check_cookie
0x1800052af  mov     rbx, [rsp+0B0h+arg_10]
0x1800052b7  add     rsp, 90h
0x1800052be  pop     r15
0x1800052c0  pop     r14
0x1800052c2  pop     rdi
0x1800052c3  pop     rsi
0x1800052c4  pop     rbp
0x1800052c5  retn
```
