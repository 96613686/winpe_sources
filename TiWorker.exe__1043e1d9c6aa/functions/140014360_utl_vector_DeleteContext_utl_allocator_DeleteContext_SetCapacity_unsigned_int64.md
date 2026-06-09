# utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_SetCapacity(unsigned __int64)

- ea: `0x140014360`
- end: `0x140014489`
- name: `?_SetCapacity@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@AEAA_N_K@Z`
- size: `297`
- prototype: `char __fastcall(__int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140014304`

## callees

- `0x140002310`
- `0x140002e88`
- `0x14001245c`
- `0x140014360`
- `0x140014490`

## pseudocode

```c
char __fastcall utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_SetCapacity(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v3; // rbx
  char *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rdi
  char *v7; // rbp
  __int64 v8; // rbx
  __m128i v9; // xmm0
  char v10; // bl
  __m128i si128; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-28h]

  if ( a2 > 0xAAAAAAAAAAAAAAALL
    || (v3 = 24 * a2,
        v4 = (char *)operator new(24 * a2, (const struct std::nothrow_t *)&std::nothrow),
        si128.m128i_i64[0] = (__int64)v4,
        (v6 = (__int64)v4) == 0) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v13 = -1;
LABEL_7:
    v10 = 0;
    goto LABEL_8;
  }
  si128.m128i_i64[1] = (__int64)v4;
  v7 = &v4[v3];
  v13 = (__int64)&v4[v3];
  if ( v4 == (char *)-1LL
    || !utl::_RangeTransferAppc<utl::allocator<DeleteContext>>(
          0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 3),
          v5,
          (__int64)v4,
          *a1,
          0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 3)) )
  {
    goto LABEL_7;
  }
  v8 = v6 + 8 * ((a1[1] - *a1) >> 3);
  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(a1);
  v9 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  a1[1] = v8;
  v10 = 1;
  si128 = v9;
  *a1 = v6;
  a1[2] = (__int64)v7;
  v13 = -1;
LABEL_8:
  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(&si128);
  return v10;
}

```

## disassembly

```asm
0x140014360  mov     [rsp+arg_10], rbx
0x140014365  push    rbp
0x140014366  push    rsi
0x140014367  push    rdi
0x140014368  sub     rsp, 50h
0x14001436c  mov     rax, cs:__security_cookie
0x140014373  xor     rax, rsp
0x140014376  mov     [rsp+68h+var_20], rax
0x14001437b  mov     rax, 0AAAAAAAAAAAAAAAh
0x140014385  mov     rsi, rcx
0x140014388  cmp     rdx, rax
0x14001438b  ja      loc_140014447
0x140014391  lea     rax, [rdx+rdx*2]
0x140014395  lea     rbx, ds:0[rax*8]
0x14001439d  mov     rcx, rbx; unsigned __int64
0x1400143a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400143a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400143ac  mov     qword ptr [rsp+68h+var_38], rax
0x1400143b1  mov     rdi, rax
0x1400143b4  test    rax, rax
0x1400143b7  jz      loc_140014447
0x1400143bd  mov     qword ptr [rsp+68h+var_38+8], rax
0x1400143c2  lea     rbp, [rbx+rax]
0x1400143c6  mov     [rsp+68h+var_28], rbp
0x1400143cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400143cf  jz      loc_14001445E
0x1400143d5  mov     rcx, [rsi+8]
0x1400143d9  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1400143e3  sub     rcx, [rsi]
0x1400143e6  mov     r8, rax
0x1400143e9  mov     r9, [rsi]
0x1400143ec  sar     rcx, 3
0x1400143f0  imul    rcx, rbx
0x1400143f4  mov     [rsp+68h+var_48], rcx
0x1400143f9  call    ??$_RangeTransferAppc@V?$allocator@UDeleteContext@@@utl@@@utl@@YA_NU?$integral_constant@_N$0A@@0@AEAV?$allocator@UDeleteContext@@@0@PEAUDeleteContext@@2_K@Z; utl::_RangeTransferAppc<utl::allocator<DeleteContext>>(utl::integral_constant<bool,0>,utl::allocator<DeleteContext> &,DeleteContext *,DeleteContext *,unsigned __int64)
0x1400143fe  test    al, al
0x140014400  jz      short loc_14001445E
0x140014402  mov     rax, [rsi+8]
0x140014406  mov     rcx, rsi
0x140014409  sub     rax, [rsi]
0x14001440c  sar     rax, 3
0x140014410  imul    rax, rbx
0x140014414  lea     rax, [rax+rax*2]
0x140014418  lea     rbx, [rdi+rax*8]
0x14001441c  call    ?_Uninit@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@AEAAXXZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(void)
0x140014421  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140014429  mov     [rsi+8], rbx
0x14001442d  mov     bl, 1
0x14001442f  movdqu  [rsp+68h+var_38], xmm0
0x140014435  mov     [rsi], rdi
0x140014438  mov     [rsi+10h], rbp
0x14001443c  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x140014445  jmp     short loc_140014460
0x140014447  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001444f  movdqu  [rsp+68h+var_38], xmm0
0x140014455  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x14001445e  xor     bl, bl
0x140014460  lea     rcx, [rsp+68h+var_38]
0x140014465  call    ?_Uninit@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@AEAAXXZ; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(void)
0x14001446a  mov     al, bl
0x14001446c  mov     rcx, [rsp+68h+var_20]
0x140014471  xor     rcx, rsp; StackCookie
0x140014474  call    __security_check_cookie
0x140014479  mov     rbx, [rsp+68h+arg_10]
0x140014481  add     rsp, 50h
0x140014485  pop     rdi
0x140014486  pop     rsi
0x140014487  pop     rbp
0x140014488  retn
```
