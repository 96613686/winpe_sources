# web::json::details::_Number::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180007ec0`
- end: `0x18000800a`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180002880`
- `0x180003724`
- `0x180003d50`
- `0x180007ec0`
- `0x1800087c0`
- `0x180008df1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x180007efe`
- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x180007efe`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x180007f06`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x180007f06`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180007f16`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180007f16`

## pseudocode

```c
void *__fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  unsigned __int64 v5; // rcx
  size_t v6; // rax
  unsigned __int64 v7; // rdx
  size_t Size; // rdi
  __int64 v9; // rax
  char *v10; // rbx
  void *result; // rax
  __crt_locale_pointers *v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  char Buffer[32]; // [rsp+30h] [rbp-38h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 != 2 )
  {
    v5 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _ui64toa_s(v5, Buffer, 0x16u, 10);
    else
      _i64toa_s(v5, Buffer, 0x16u, 10);
    v6 = strnlen(Buffer, 0x16u);
    v7 = a2[3];
    Size = v6;
    v9 = a2[2];
    if ( Size <= v7 - v9 )
    {
      a2[2] = v9 + Size;
      if ( v7 > 0xF )
        a2 = (_QWORD *)*a2;
      v10 = (char *)a2 + v9;
      result = memmove_0(v10, Buffer, Size);
      v10[Size] = 0;
      return result;
    }
    return (void *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  }
  v12 = utility::details::scoped_c_thread_locale::c_locale();
  v13 = sprintf_s_l(Buffer, 0x19u, "%.*g", v12, 17, *(_QWORD *)(a1 + 8));
  v14 = a2[3];
  v15 = a2[2];
  Size = v13;
  if ( v13 > v14 - v15 )
    return (void *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  a2[2] = v15 + v13;
  if ( v14 > 0xF )
    a2 = (_QWORD *)*a2;
  v16 = (char *)a2 + v15;
  result = memmove_0(v16, Buffer, v13);
  v16[Size] = 0;
  return result;
}

```

## disassembly

```asm
0x180007ec0  mov     [rsp+arg_10], rbx
0x180007ec5  push    rdi
0x180007ec6  sub     rsp, 60h
0x180007eca  mov     rax, cs:__security_cookie
0x180007ed1  xor     rax, rsp
0x180007ed4  mov     [rsp+68h+var_18], rax
0x180007ed9  mov     eax, [rcx+10h]
0x180007edc  mov     rbx, rdx
0x180007edf  mov     rdi, rcx
0x180007ee2  cmp     eax, 2
0x180007ee5  jz      short loc_180007F66
0x180007ee7  mov     rcx, [rcx+8]; Value
0x180007eeb  mov     r9d, 0Ah; Radix
0x180007ef1  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180007ef6  lea     r8d, [r9+0Ch]; BufferCount
0x180007efa  test    eax, eax
0x180007efc  jnz     short loc_180007F06
0x180007efe  call    cs:__imp__i64toa_s
0x180007f04  jmp     short loc_180007F0C
0x180007f06  call    cs:__imp__ui64toa_s
0x180007f0c  mov     edx, 16h; MaxCount
0x180007f11  lea     rcx, [rsp+68h+Buffer]; String
0x180007f16  call    cs:__imp_strnlen
0x180007f1c  mov     rdx, [rbx+18h]
0x180007f20  mov     rdi, rax
0x180007f23  mov     rax, [rbx+10h]
0x180007f27  mov     rcx, rdx
0x180007f2a  sub     rcx, rax
0x180007f2d  cmp     rdi, rcx
0x180007f30  ja      short loc_180007F5F
0x180007f32  lea     rcx, [rax+rdi]
0x180007f36  mov     [rbx+10h], rcx
0x180007f3a  cmp     rdx, 0Fh
0x180007f3e  jbe     short loc_180007F43
0x180007f40  mov     rbx, [rbx]
0x180007f43  add     rbx, rax
0x180007f46  lea     rdx, [rsp+68h+Buffer]; Src
0x180007f4b  mov     rcx, rbx; void *
0x180007f4e  mov     r8, rdi; Size
0x180007f51  call    memmove_0
0x180007f56  mov     byte ptr [rbx+rdi], 0
0x180007f5a  jmp     loc_180007FEF
0x180007f5f  lea     r9, [rsp+68h+Buffer]
0x180007f64  jmp     short loc_180007FDC
0x180007f66  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x180007f6b  movsd   xmm0, qword ptr [rdi+8]
0x180007f70  lea     r8, Format; "%.*g"
0x180007f77  movsd   [rsp+68h+var_40], xmm0
0x180007f7d  lea     rcx, [rsp+68h+Buffer]; Buffer
0x180007f82  mov     r9, rax; Locale
0x180007f85  mov     dword ptr [rsp+68h+Size], 11h
0x180007f8d  mov     edx, 19h; BufferCount
0x180007f92  call    _sprintf_s_l
0x180007f97  mov     rdx, [rbx+18h]
0x180007f9b  mov     rcx, [rbx+10h]
0x180007f9f  movsxd  rdi, eax
0x180007fa2  mov     rax, rdx
0x180007fa5  sub     rax, rcx
0x180007fa8  cmp     rdi, rax
0x180007fab  ja      short loc_180007FD7
0x180007fad  lea     rax, [rcx+rdi]
0x180007fb1  mov     [rbx+10h], rax
0x180007fb5  cmp     rdx, 0Fh
0x180007fb9  jbe     short loc_180007FBE
0x180007fbb  mov     rbx, [rbx]
0x180007fbe  add     rbx, rcx
0x180007fc1  lea     rdx, [rsp+68h+Buffer]; Src
0x180007fc6  mov     rcx, rbx; void *
0x180007fc9  mov     r8, rdi; Size
0x180007fcc  call    memmove_0
0x180007fd1  mov     byte ptr [rbx+rdi], 0
0x180007fd5  jmp     short loc_180007FEF
0x180007fd7  lea     r9, [rsp+68h+Buffer]
0x180007fdc  xor     r8d, r8d
0x180007fdf  mov     [rsp+68h+Size], rdi; Size
0x180007fe4  mov     rdx, rdi
0x180007fe7  mov     rcx, rbx; Src
0x180007fea  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x180007fef  mov     rcx, [rsp+68h+var_18]
0x180007ff4  xor     rcx, rsp; StackCookie
0x180007ff7  call    __security_check_cookie
0x180007ffc  mov     rbx, [rsp+68h+arg_10]
0x180008004  add     rsp, 60h
0x180008008  pop     rdi
0x180008009  retn
```
