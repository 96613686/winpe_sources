# web::json::details::_Number::format(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180007b00`
- end: `0x180007c64`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800028f0`
- `0x1800034bc`
- `0x180003c30`
- `0x180007b00`
- `0x180008230`
- `0x18000883f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180007b44`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180007b44`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180007b4c`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180007b4c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180007b5c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180007b5c`

## pseudocode

```c
__int64 __fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  __int64 v4; // rcx
  size_t v5; // rax
  unsigned __int64 v6; // r8
  __int64 v7; // rdx
  size_t v8; // rdi
  __int64 result; // rax
  __int64 v10; // xmm6_8
  __crt_locale_pointers *v11; // rax
  int v12; // eax
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rdi
  wchar_t Source[28]; // [rsp+30h] [rbp-58h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 == 2 )
  {
    v10 = *(_QWORD *)(a1 + 8);
    v11 = utility::details::scoped_c_thread_locale::c_locale();
    v12 = swprintf_s_l(Source, 0x19u, L"%.*g", v11, 17, v10);
    v13 = a2[3];
    v14 = a2[2];
    if ( v12 > v13 - v14 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v12);
    }
    else
    {
      v15 = v12 + v14;
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
    v4 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _o__ui64tow_s(v4, Source, 22, 10);
    else
      _o__i64tow_s(v4, Source, 22, 10);
    v5 = wcsnlen(Source, 0x16u);
    v6 = a2[3];
    v7 = a2[2];
    if ( v5 > v6 - v7 )
    {
      return ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
               a2,
               v5);
    }
    else
    {
      v8 = v7 + v5;
      a2[2] = v7 + v5;
      if ( v6 > 7 )
        a2 = (_QWORD *)*a2;
      memmove_0((char *)a2 + 2 * v7, Source, 2 * v5);
      result = 0;
      *((_WORD *)a2 + v8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp+arg_10], rbx
0x180007b05  push    rdi
0x180007b06  sub     rsp, 80h
0x180007b0d  mov     rax, cs:__security_cookie
0x180007b14  xor     rax, rsp
0x180007b17  mov     [rsp+88h+var_20], rax
0x180007b1c  mov     eax, [rcx+10h]
0x180007b1f  mov     rbx, rdx
0x180007b22  cmp     eax, 2
0x180007b25  jz      loc_180007BB5
0x180007b2b  mov     rcx, [rcx+8]
0x180007b2f  mov     r9d, 0Ah
0x180007b35  lea     rdx, [rsp+88h+Source]
0x180007b3a  mov     r8d, 16h
0x180007b40  test    eax, eax
0x180007b42  jnz     short loc_180007B4C
0x180007b44  call    cs:__imp__o__i64tow_s
0x180007b4a  jmp     short loc_180007B52
0x180007b4c  call    cs:__imp__o__ui64tow_s
0x180007b52  mov     edx, 16h; MaxCount
0x180007b57  lea     rcx, [rsp+88h+Source]; Source
0x180007b5c  call    cs:__imp_wcsnlen
0x180007b62  mov     r8, [rbx+18h]
0x180007b66  mov     rdx, [rbx+10h]
0x180007b6a  mov     rcx, r8
0x180007b6d  sub     rcx, rdx
0x180007b70  cmp     rax, rcx
0x180007b73  ja      short loc_180007BA3
0x180007b75  lea     rdi, [rdx+rax]
0x180007b79  mov     [rbx+10h], rdi
0x180007b7d  cmp     r8, 7
0x180007b81  jbe     short loc_180007B86
0x180007b83  mov     rbx, [rbx]
0x180007b86  lea     rcx, [rbx+rdx*2]; void *
0x180007b8a  lea     rdx, [rsp+88h+Source]; Src
0x180007b8f  lea     r8, [rax+rax]; Size
0x180007b93  call    memmove_0
0x180007b98  xor     eax, eax
0x180007b9a  mov     [rbx+rdi*2], ax
0x180007b9e  jmp     loc_180007C46
0x180007ba3  mov     [rsp+88h+var_68], rax
0x180007ba8  lea     r9, [rsp+88h+Source]
0x180007bad  mov     rdx, rax
0x180007bb0  jmp     loc_180007C3B
0x180007bb5  movaps  [rsp+88h+var_18], xmm6
0x180007bba  movsd   xmm6, qword ptr [rcx+8]
0x180007bbf  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x180007bc4  movsd   [rsp+88h+var_60], xmm6
0x180007bca  lea     r8, aG; "%.*g"
0x180007bd1  mov     r9, rax; Locale
0x180007bd4  mov     dword ptr [rsp+88h+var_68], 11h
0x180007bdc  mov     edx, 19h; BufferCount
0x180007be1  lea     rcx, [rsp+88h+Source]; Buffer
0x180007be6  call    _swprintf_s_l
0x180007beb  mov     r8, [rbx+18h]
0x180007bef  mov     rcx, [rbx+10h]
0x180007bf3  movaps  xmm6, [rsp+88h+var_18]
0x180007bf8  movsxd  rdx, eax
0x180007bfb  mov     rax, r8
0x180007bfe  sub     rax, rcx
0x180007c01  cmp     rdx, rax
0x180007c04  ja      short loc_180007C31
0x180007c06  lea     rdi, [rdx+rcx]
0x180007c0a  mov     [rbx+10h], rdi
0x180007c0e  cmp     r8, 7
0x180007c12  jbe     short loc_180007C17
0x180007c14  mov     rbx, [rbx]
0x180007c17  lea     r8, [rdx+rdx]; Size
0x180007c1b  lea     rdx, [rsp+88h+Source]; Src
0x180007c20  lea     rcx, [rbx+rcx*2]; void *
0x180007c24  call    memmove_0
0x180007c29  xor     eax, eax
0x180007c2b  mov     [rbx+rdi*2], ax
0x180007c2f  jmp     short loc_180007C46
0x180007c31  mov     [rsp+88h+var_68], rdx; __int64
0x180007c36  lea     r9, [rsp+88h+Source]
0x180007c3b  xor     r8d, r8d
0x180007c3e  mov     rcx, rbx; Src
0x180007c41  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180007c46  mov     rcx, [rsp+88h+var_20]
0x180007c4b  xor     rcx, rsp; StackCookie
0x180007c4e  call    __security_check_cookie
0x180007c53  mov     rbx, [rsp+88h+arg_10]
0x180007c5b  add     rsp, 80h
0x180007c62  pop     rdi
0x180007c63  retn
```
