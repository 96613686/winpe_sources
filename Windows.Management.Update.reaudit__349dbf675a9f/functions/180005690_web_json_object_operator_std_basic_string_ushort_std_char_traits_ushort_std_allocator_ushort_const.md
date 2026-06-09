# web::json::object::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180005690`
- end: `0x180005885`
- name: `??Aobject@json@web@@QEAAAEAVvalue@12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180006a70`

## callees

- `0x180002880`
- `0x180002cac`
- `0x180003780`
- `0x180003970`
- `0x180003c40`
- `0x180005690`
- `0x1800066b0`
- `0x180007150`
- `0x18001da30`
- `0x1800226b4`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall web::json::object::operator[](__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rbx
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rcx
  size_t v8; // r8
  _QWORD *v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-39h] BYREF
  _OWORD v15[2]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-9h]
  __int128 v17; // [rsp+58h] [rbp-1h] BYREF
  __m128i si128; // [rsp+68h] [rbp+Fh]
  _QWORD *v19; // [rsp+78h] [rbp+1Fh]

  v4 = 0;
  web::json::object::find_insert_location(a1, v14, a2);
  v5 = v14[0];
  if ( v14[0] == *(_QWORD *)(a1 + 8) )
    goto LABEL_8;
  v6 = (const wchar_t *)v14[0];
  if ( *(_QWORD *)(v14[0] + 24LL) > 7u )
    v6 = *(const wchar_t **)v14[0];
  v7 = (const wchar_t *)a2;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v7 = *(const wchar_t **)a2;
  v8 = *(_QWORD *)(a2 + 16);
  if ( v8 != *(_QWORD *)(v14[0] + 16LL) || wmemcmp(v7, v6, v8) )
  {
LABEL_8:
    v9 = operator new(8u);
    v14[0] = v9;
    if ( v9 )
      *v9 = &web::json::details::_Null::`vftable';
    else
      v9 = 0;
    v14[0] = v9;
    std::wstring::wstring(&v17, a2);
    v14[0] = 0;
    v19 = v9;
    v10 = *(_QWORD *)(a1 + 8);
    if ( v10 == *(_QWORD *)(a1 + 16) )
    {
      v5 = std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(
             a1,
             v5,
             &v17);
      v4 = v19;
    }
    else
    {
      v19 = 0;
      if ( v5 == v10 )
      {
        *(_OWORD *)v10 = v17;
        *(__m128i *)(v10 + 16) = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v17) = 0;
        *(_QWORD *)(v10 + 32) = v9;
        *(_QWORD *)(a1 + 8) += 40LL;
      }
      else
      {
        v14[1] = a1;
        v15[0] = v17;
        v15[1] = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v17) = 0;
        v16 = v9;
        v11 = v10 - 40;
        *(_OWORD *)v10 = *(_OWORD *)(v10 - 40);
        *(_OWORD *)(v10 + 16) = *(_OWORD *)(v10 - 40 + 16);
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 7;
        *(_WORD *)v11 = 0;
        v12 = *(_QWORD *)(v10 - 40 + 32);
        *(_QWORD *)(v11 + 32) = 0;
        *(_QWORD *)(v10 + 32) = v12;
        *(_QWORD *)(a1 + 8) += 40LL;
        std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(v5);
        std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(v5, v15);
        if ( v16 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v16 + 192LL))(v16, 1);
        std::wstring::_Tidy_deallocate(v15);
      }
    }
    if ( v4 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v4 + 192LL))(v4, 1);
    std::wstring::_Tidy_deallocate(&v17);
  }
  return v5 + 32;
}

```

## disassembly

```asm
0x180005690  mov     [rsp-8+arg_10], rbx
0x180005695  push    rbp
0x180005696  push    rsi
0x180005697  push    rdi
0x180005698  push    r14
0x18000569a  push    r15
0x18000569c  lea     rbp, [rsp-37h]
0x1800056a1  sub     rsp, 90h
0x1800056a8  mov     rax, cs:__security_cookie
0x1800056af  xor     rax, rsp
0x1800056b2  mov     [rbp+57h+var_30], rax
0x1800056b6  mov     r15, rdx
0x1800056b9  mov     r14, rcx
0x1800056bc  xor     edi, edi
0x1800056be  mov     r8, rdx
0x1800056c1  lea     rdx, [rbp+57h+var_90]
0x1800056c5  call    ?find_insert_location@object@json@web@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; web::json::object::find_insert_location(std::wstring const &)
0x1800056ca  mov     rbx, [rbp+57h+var_90]
0x1800056ce  cmp     rbx, [r14+8]
0x1800056d2  jz      short loc_180005705
0x1800056d4  mov     rdx, rbx
0x1800056d7  cmp     qword ptr [rbx+18h], 7
0x1800056dc  jbe     short loc_1800056E1
0x1800056de  mov     rdx, [rbx]; S2
0x1800056e1  mov     rcx, r15
0x1800056e4  cmp     qword ptr [r15+18h], 7
0x1800056e9  jbe     short loc_1800056EE
0x1800056eb  mov     rcx, [r15]; S1
0x1800056ee  mov     r8, [r15+10h]; N
0x1800056f2  cmp     r8, [rbx+10h]
0x1800056f6  jnz     short loc_180005705
0x1800056f8  call    wmemcmp
0x1800056fd  test    eax, eax
0x1800056ff  jz      loc_18000585E
0x180005705  mov     ecx, 8; Size
0x18000570a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000570f  mov     rsi, rax
0x180005712  mov     [rbp+57h+var_90], rax
0x180005716  test    rax, rax
0x180005719  jz      short loc_180005727
0x18000571b  lea     rax, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180005722  mov     [rsi], rax
0x180005725  jmp     short loc_18000572A
0x180005727  mov     rsi, rdi
0x18000572a  mov     [rbp+57h+var_90], rsi
0x18000572e  mov     rdx, r15
0x180005731  lea     rcx, [rbp+57h+var_58]
0x180005735  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000573a  mov     [rbp+57h+var_90], rdi
0x18000573e  mov     [rbp+57h+var_38], rsi
0x180005742  mov     r8, [r14+8]
0x180005746  cmp     r8, [r14+10h]
0x18000574a  jz      loc_180005822
0x180005750  mov     [rbp+57h+var_38], rdi
0x180005754  cmp     rbx, r8
0x180005757  jnz     short loc_180005789
0x180005759  movups  xmm0, [rbp+57h+var_58]
0x18000575d  movups  xmmword ptr [r8], xmm0
0x180005761  movups  xmm1, [rbp+57h+var_48]
0x180005765  movups  xmmword ptr [r8+10h], xmm1
0x18000576a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180005772  movdqu  [rbp+57h+var_48], xmm0
0x180005777  mov     word ptr [rbp+57h+var_58], di
0x18000577b  mov     [r8+20h], rsi
0x18000577f  add     qword ptr [r14+8], 28h ; '('
0x180005784  jmp     loc_180005838
0x180005789  mov     [rbp+57h+var_88], r14
0x18000578d  movups  xmm1, [rbp+57h+var_58]
0x180005791  movups  [rbp+57h+var_80], xmm1
0x180005795  movups  xmm0, [rbp+57h+var_48]
0x180005799  movups  [rbp+57h+var_70], xmm0
0x18000579d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800057a5  movdqu  [rbp+57h+var_48], xmm1
0x1800057aa  mov     word ptr [rbp+57h+var_58], di
0x1800057ae  mov     [rbp+57h+var_60], rsi
0x1800057b2  lea     rdx, [r8-28h]
0x1800057b6  movups  xmm0, xmmword ptr [rdx]
0x1800057b9  movups  xmmword ptr [r8], xmm0
0x1800057bd  movups  xmm1, xmmword ptr [rdx+10h]
0x1800057c1  movups  xmmword ptr [r8+10h], xmm1
0x1800057c6  mov     [rdx+10h], rdi
0x1800057ca  mov     qword ptr [rdx+18h], 7
0x1800057d2  mov     [rdx], di
0x1800057d5  mov     rax, [rdx+20h]
0x1800057d9  mov     [rdx+20h], rdi
0x1800057dd  mov     [r8+20h], rax
0x1800057e1  add     qword ptr [r14+8], 28h ; '('
0x1800057e6  mov     rcx, rbx
0x1800057e9  call    ??$_Move_backward_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@PEAU12@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@PEAU10@00@Z; std::_Move_backward_unchecked<std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *)
0x1800057ee  lea     rdx, [rbp+57h+var_80]
0x1800057f2  mov     rcx, rbx
0x1800057f5  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,web::json::value>::operator=<std::pair<std::wstring,web::json::value>,0>(std::pair<std::wstring,web::json::value> &&)
0x1800057fa  mov     rcx, [rbp+57h+var_60]
0x1800057fe  test    rcx, rcx
0x180005801  jz      short loc_180005817
0x180005803  mov     rax, [rcx]
0x180005806  mov     edx, 1
0x18000580b  mov     rax, [rax+0C0h]
0x180005812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005817  lea     rcx, [rbp+57h+var_80]
0x18000581b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005820  jmp     short loc_180005838
0x180005822  lea     r8, [rbp+57h+var_58]
0x180005826  mov     rdx, rbx
0x180005829  mov     rcx, r14
0x18000582c  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::pair<std::wstring,web::json::value>>(std::pair<std::wstring,web::json::value> * const,std::pair<std::wstring,web::json::value> &&)
0x180005831  mov     rbx, rax
0x180005834  mov     rdi, [rbp+57h+var_38]
0x180005838  test    rdi, rdi
0x18000583b  jz      short loc_180005854
0x18000583d  mov     r8, [rdi]
0x180005840  mov     edx, 1
0x180005845  mov     rcx, rdi
0x180005848  mov     rax, [r8+0C0h]
0x18000584f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005854  lea     rcx, [rbp+57h+var_58]
0x180005858  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000585d  nop
0x18000585e  lea     rax, [rbx+20h]
0x180005862  mov     rcx, [rbp+57h+var_30]
0x180005866  xor     rcx, rsp; StackCookie
0x180005869  call    __security_check_cookie
0x18000586e  mov     rbx, [rsp+0B0h+arg_10]
0x180005876  add     rsp, 90h
0x18000587d  pop     r15
0x18000587f  pop     r14
0x180005881  pop     rdi
0x180005882  pop     rsi
0x180005883  pop     rbp
0x180005884  retn
```
