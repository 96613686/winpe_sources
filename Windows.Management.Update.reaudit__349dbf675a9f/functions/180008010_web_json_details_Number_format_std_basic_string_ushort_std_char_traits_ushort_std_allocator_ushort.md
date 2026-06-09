# web::json::details::_Number::format(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180008010`
- end: `0x180008162`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180002880`
- `0x1800036c8`
- `0x180003ef0`
- `0x180008010`
- `0x1800087c0`
- `0x180008df1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180008052`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180008052`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000805a`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000805a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000806a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000806a`

## pseudocode

```c
__int64 __fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  __int64 v5; // rcx
  size_t v6; // rax
  unsigned __int64 v7; // r8
  __int64 v8; // rdx
  size_t v9; // rdi
  __int64 result; // rax
  __crt_locale_pointers *v11; // rax
  int v12; // eax
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdi
  wchar_t Source[28]; // [rsp+30h] [rbp-48h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 == 2 )
  {
    v11 = utility::details::scoped_c_thread_locale::c_locale();
    v12 = swprintf_s_l(Source, 0x19u, L"%.*g", v11, 17, *(_QWORD *)(a1 + 8));
    v13 = a2[3];
    v14 = a2[2];
    if ( v12 > v13 - v14 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v12);
    }
    else
    {
      v15 = v14 + v12;
      a2[2] = v15;
      if ( v13 > 7 )
        a2 = (_QWORD *)*a2;
      memmove_0((char *)a2 + 2 * v14, Source, 2LL * v12);
      result = 0;
      *((_WORD *)a2 + v15) = 0;
    }
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _o__ui64tow_s(v5, Source, 22);
    else
      _o__i64tow_s(v5, Source, 22);
    v6 = wcsnlen(Source, 0x16u);
    v7 = a2[3];
    v8 = a2[2];
    if ( v6 > v7 - v8 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v6);
    }
    else
    {
      v9 = v6 + v8;
      a2[2] = v6 + v8;
      if ( v7 > 7 )
        a2 = (_QWORD *)*a2;
      memmove_0((char *)a2 + 2 * v8, Source, 2 * v6);
      result = 0;
      *((_WORD *)a2 + v9) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008010  mov     [rsp+arg_10], rbx
0x180008015  push    rdi
0x180008016  sub     rsp, 70h
0x18000801a  mov     rax, cs:__security_cookie
0x180008021  xor     rax, rsp
0x180008024  mov     [rsp+78h+var_10], rax
0x180008029  mov     eax, [rcx+10h]
0x18000802c  mov     rbx, rdx
0x18000802f  mov     rdi, rcx
0x180008032  cmp     eax, 2
0x180008035  jz      loc_1800080C0
0x18000803b  mov     rcx, [rcx+8]
0x18000803f  mov     r9d, 0Ah
0x180008045  lea     rdx, [rsp+78h+Source]
0x18000804a  lea     r8d, [r9+0Ch]
0x18000804e  test    eax, eax
0x180008050  jnz     short loc_18000805A
0x180008052  call    cs:__imp__o__i64tow_s
0x180008058  jmp     short loc_180008060
0x18000805a  call    cs:__imp__o__ui64tow_s
0x180008060  mov     edx, 16h; MaxCount
0x180008065  lea     rcx, [rsp+78h+Source]; Source
0x18000806a  call    cs:__imp_wcsnlen
0x180008070  mov     r8, [rbx+18h]
0x180008074  mov     rdx, [rbx+10h]
0x180008078  mov     rcx, r8
0x18000807b  sub     rcx, rdx
0x18000807e  cmp     rax, rcx
0x180008081  ja      short loc_1800080B1
0x180008083  lea     rdi, [rax+rdx]
0x180008087  mov     [rbx+10h], rdi
0x18000808b  cmp     r8, 7
0x18000808f  jbe     short loc_180008094
0x180008091  mov     rbx, [rbx]
0x180008094  lea     rcx, [rbx+rdx*2]; void *
0x180008098  lea     rdx, [rsp+78h+Source]; Src
0x18000809d  lea     r8, [rax+rax]; Size
0x1800080a1  call    memmove_0
0x1800080a6  xor     eax, eax
0x1800080a8  mov     [rbx+rdi*2], ax
0x1800080ac  jmp     loc_180008147
0x1800080b1  mov     [rsp+78h+var_58], rax
0x1800080b6  lea     r9, [rsp+78h+Source]
0x1800080bb  mov     rdx, rax
0x1800080be  jmp     short loc_18000813C
0x1800080c0  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x1800080c5  movsd   xmm0, qword ptr [rdi+8]
0x1800080ca  lea     r8, aG; "%.*g"
0x1800080d1  movsd   [rsp+78h+var_50], xmm0
0x1800080d7  lea     rcx, [rsp+78h+Source]; Buffer
0x1800080dc  mov     r9, rax; Locale
0x1800080df  mov     dword ptr [rsp+78h+var_58], 11h
0x1800080e7  mov     edx, 19h; BufferCount
0x1800080ec  call    _swprintf_s_l
0x1800080f1  mov     r8, [rbx+18h]
0x1800080f5  mov     rcx, [rbx+10h]
0x1800080f9  movsxd  rdx, eax
0x1800080fc  mov     rax, r8
0x1800080ff  sub     rax, rcx
0x180008102  cmp     rdx, rax
0x180008105  ja      short loc_180008132
0x180008107  lea     rdi, [rcx+rdx]
0x18000810b  mov     [rbx+10h], rdi
0x18000810f  cmp     r8, 7
0x180008113  jbe     short loc_180008118
0x180008115  mov     rbx, [rbx]
0x180008118  lea     r8, [rdx+rdx]; Size
0x18000811c  lea     rdx, [rsp+78h+Source]; Src
0x180008121  lea     rcx, [rbx+rcx*2]; void *
0x180008125  call    memmove_0
0x18000812a  xor     eax, eax
0x18000812c  mov     [rbx+rdi*2], ax
0x180008130  jmp     short loc_180008147
0x180008132  mov     [rsp+78h+var_58], rdx; __int64
0x180008137  lea     r9, [rsp+78h+Source]
0x18000813c  xor     r8d, r8d
0x18000813f  mov     rcx, rbx; Src
0x180008142  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::append(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180008147  mov     rcx, [rsp+78h+var_10]
0x18000814c  xor     rcx, rsp; StackCookie
0x18000814f  call    __security_check_cookie
0x180008154  mov     rbx, [rsp+78h+arg_10]
0x18000815c  add     rsp, 70h
0x180008160  pop     rdi
0x180008161  retn
```
