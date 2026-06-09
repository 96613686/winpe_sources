# web::json::details::_Number::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800079a0`
- end: `0x180007afa`
- name: `?format@_Number@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800028f0`
- `0x180003520`
- `0x180003aa0`
- `0x1800079a0`
- `0x180008230`
- `0x18000883f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x1800079e1`
- `api-ms-win-crt-private-l1-1-0!_o__i64toa_s` at `0x1800079e1`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x1800079e9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64toa_s` at `0x1800079e9`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800079f9`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800079f9`

## pseudocode

```c
void *__fastcall web::json::details::_Number::format(__int64 a1, _QWORD *a2)
{
  int v2; // eax
  unsigned __int64 v4; // rcx
  size_t v5; // rax
  unsigned __int64 v6; // rdx
  size_t Size; // rdi
  __int64 v8; // rax
  char *v9; // rbx
  void *result; // rax
  __int64 v11; // xmm6_8
  __crt_locale_pointers *v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  char Buffer[32]; // [rsp+30h] [rbp-48h] BYREF

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 != 2 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      _ui64toa_s(v4, Buffer, 0x16u, 10);
    else
      _i64toa_s(v4, Buffer, 0x16u, 10);
    v5 = strnlen(Buffer, 0x16u);
    v6 = a2[3];
    Size = v5;
    v8 = a2[2];
    if ( Size <= v6 - v8 )
    {
      a2[2] = v8 + Size;
      if ( v6 > 0xF )
        a2 = (_QWORD *)*a2;
      v9 = (char *)a2 + v8;
      result = memmove_0(v9, Buffer, Size);
      v9[Size] = 0;
      return result;
    }
    return (void *)____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  }
  v11 = *(_QWORD *)(a1 + 8);
  v12 = utility::details::scoped_c_thread_locale::c_locale();
  v13 = sprintf_s_l(Buffer, 0x19u, "%.*g", v12, 17, v11);
  v14 = a2[3];
  v15 = a2[2];
  Size = v13;
  if ( v13 > v14 - v15 )
    return (void *)____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                     a2,
                     Size);
  a2[2] = v13 + v15;
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
0x1800079a0  mov     [rsp+arg_10], rbx
0x1800079a5  push    rdi
0x1800079a6  sub     rsp, 70h
0x1800079aa  mov     rax, cs:__security_cookie
0x1800079b1  xor     rax, rsp
0x1800079b4  mov     [rsp+78h+var_28], rax
0x1800079b9  mov     eax, [rcx+10h]
0x1800079bc  mov     rbx, rdx
0x1800079bf  cmp     eax, 2
0x1800079c2  jz      loc_180007A4C
0x1800079c8  mov     rcx, [rcx+8]; Value
0x1800079cc  mov     r9d, 0Ah; Radix
0x1800079d2  lea     rdx, [rsp+78h+Buffer]; Buffer
0x1800079d7  mov     r8d, 16h; BufferCount
0x1800079dd  test    eax, eax
0x1800079df  jnz     short loc_1800079E9
0x1800079e1  call    cs:__imp__i64toa_s
0x1800079e7  jmp     short loc_1800079EF
0x1800079e9  call    cs:__imp__ui64toa_s
0x1800079ef  mov     edx, 16h; MaxCount
0x1800079f4  lea     rcx, [rsp+78h+Buffer]; String
0x1800079f9  call    cs:__imp_strnlen
0x1800079ff  mov     rdx, [rbx+18h]
0x180007a03  mov     rdi, rax
0x180007a06  mov     rax, [rbx+10h]
0x180007a0a  mov     rcx, rdx
0x180007a0d  sub     rcx, rax
0x180007a10  cmp     rdi, rcx
0x180007a13  ja      short loc_180007A42
0x180007a15  lea     rcx, [rax+rdi]
0x180007a19  mov     [rbx+10h], rcx
0x180007a1d  cmp     rdx, 0Fh
0x180007a21  jbe     short loc_180007A26
0x180007a23  mov     rbx, [rbx]
0x180007a26  add     rbx, rax
0x180007a29  lea     rdx, [rsp+78h+Buffer]; Src
0x180007a2e  mov     rcx, rbx; void *
0x180007a31  mov     r8, rdi; Size
0x180007a34  call    memmove_0
0x180007a39  mov     byte ptr [rbx+rdi], 0
0x180007a3d  jmp     loc_180007ADF
0x180007a42  lea     r9, [rsp+78h+Buffer]
0x180007a47  jmp     loc_180007ACC
0x180007a4c  movaps  [rsp+78h+var_18], xmm6
0x180007a51  movsd   xmm6, qword ptr [rcx+8]
0x180007a56  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x180007a5b  movsd   [rsp+78h+var_50], xmm6
0x180007a61  lea     r8, Format; "%.*g"
0x180007a68  mov     r9, rax; Locale
0x180007a6b  mov     dword ptr [rsp+78h+Size], 11h
0x180007a73  mov     edx, 19h; BufferCount
0x180007a78  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180007a7d  call    _sprintf_s_l
0x180007a82  mov     rdx, [rbx+18h]
0x180007a86  mov     rcx, [rbx+10h]
0x180007a8a  movaps  xmm6, [rsp+78h+var_18]
0x180007a8f  movsxd  rdi, eax
0x180007a92  mov     rax, rdx
0x180007a95  sub     rax, rcx
0x180007a98  cmp     rdi, rax
0x180007a9b  ja      short loc_180007AC7
0x180007a9d  lea     rax, [rdi+rcx]
0x180007aa1  mov     [rbx+10h], rax
0x180007aa5  cmp     rdx, 0Fh
0x180007aa9  jbe     short loc_180007AAE
0x180007aab  mov     rbx, [rbx]
0x180007aae  add     rbx, rcx
0x180007ab1  lea     rdx, [rsp+78h+Buffer]; Src
0x180007ab6  mov     rcx, rbx; void *
0x180007ab9  mov     r8, rdi; Size
0x180007abc  call    memmove_0
0x180007ac1  mov     byte ptr [rbx+rdi], 0
0x180007ac5  jmp     short loc_180007ADF
0x180007ac7  lea     r9, [rsp+78h+Buffer]
0x180007acc  xor     r8d, r8d
0x180007acf  mov     [rsp+78h+Size], rdi; Size
0x180007ad4  mov     rdx, rdi
0x180007ad7  mov     rcx, rbx; Src
0x180007ada  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x180007adf  mov     rcx, [rsp+78h+var_28]
0x180007ae4  xor     rcx, rsp; StackCookie
0x180007ae7  call    __security_check_cookie
0x180007aec  mov     rbx, [rsp+78h+arg_10]
0x180007af4  add     rsp, 70h
0x180007af8  pop     rdi
0x180007af9  retn
```
