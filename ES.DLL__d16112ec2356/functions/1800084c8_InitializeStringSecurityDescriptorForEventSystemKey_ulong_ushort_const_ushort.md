# InitializeStringSecurityDescriptorForEventSystemKey(ulong,ushort const *,ushort * *)

- ea: `0x1800084c8`
- end: `0x1800085e2`
- name: `?InitializeStringSecurityDescriptorForEventSystemKey@@YAJKPEBGPEAPEAG@Z`
- size: `282`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007e6c`
- `0x18000ae10`
- `0x18003a720`

## callees

- `0x180006194`
- `0x1800084c8`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800085a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085d8`

## pseudocode

```c
__int64 __fastcall InitializeStringSecurityDescriptorForEventSystemKey(
        unsigned int a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const wchar_t *v4; // rax
  __int64 v5; // r8
  unsigned __int16 *v7; // rdx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  unsigned __int16 v16; // ax
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rbx
  int v23; // edi
  unsigned __int16 v24[144]; // [rsp+20h] [rbp-148h] BYREF

  v4 = L"D:P(A;CI;KA;;;BA)(A;CIIO;KA;;;CO)(A;CI;KA;;;%s)(A;CI;KA;;;SY)(A;CI;KR;;;S-1-5-80-1772571935-1555666882-3369284645"
        "-1675012128-2386634627)";
  v5 = 2;
  v7 = v24;
  do
  {
    v8 = *((_OWORD *)v4 + 1);
    *(_OWORD *)v7 = *(_OWORD *)v4;
    v9 = *((_OWORD *)v4 + 2);
    *((_OWORD *)v7 + 1) = v8;
    v10 = *((_OWORD *)v4 + 3);
    *((_OWORD *)v7 + 2) = v9;
    v11 = *((_OWORD *)v4 + 4);
    *((_OWORD *)v7 + 3) = v10;
    v12 = *((_OWORD *)v4 + 5);
    *((_OWORD *)v7 + 4) = v11;
    v13 = *((_OWORD *)v4 + 6);
    *((_OWORD *)v7 + 5) = v12;
    v14 = *((_OWORD *)v4 + 7);
    v4 += 64;
    *((_OWORD *)v7 + 6) = v13;
    *((_OWORD *)v7 + 7) = v14;
    v7 += 64;
    --v5;
  }
  while ( v5 );
  v15 = *(_OWORD *)v4;
  v16 = v4[8];
  *(_OWORD *)v7 = v15;
  v7[8] = v16;
  v17 = a1 + 137;
  if ( (unsigned int)v17 < a1 )
    return 2147942934LL;
  v18 = (unsigned int)v17;
  v19 = 2 * v17;
  if ( v19 > 0xFFFFFFFF )
    return 2147942934LL;
  v21 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v19);
  v22 = v21;
  if ( v21 )
  {
    v23 = StringCchPrintfW(v21, v18, v24, a2);
    if ( v23 < 0 )
    {
      CoTaskMemFree(v22);
      v22 = 0;
    }
  }
  else
  {
    v23 = -2147024882;
  }
  *a3 = v22;
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800084c8  mov     [rsp+arg_18], rbx
0x1800084cd  push    rbp
0x1800084ce  push    rsi
0x1800084cf  push    rdi
0x1800084d0  sub     rsp, 150h
0x1800084d7  mov     rax, cs:__security_cookie
0x1800084de  xor     rax, rsp
0x1800084e1  mov     [rsp+168h+var_28], rax
0x1800084e9  mov     rsi, r8
0x1800084ec  lea     rax, aDPACiKaBaACiio_0; "D:P(A;CI;KA;;;BA)(A;CIIO;KA;;;CO)(A;CI;"...
0x1800084f3  mov     r8d, 2
0x1800084f9  mov     rbp, rdx
0x1800084fc  lea     rdx, [rsp+168h+var_148]
0x180008501  lea     r9d, [r8+7Eh]
0x180008505  movups  xmm0, xmmword ptr [rax]
0x180008508  movups  xmm1, xmmword ptr [rax+10h]
0x18000850c  movups  xmmword ptr [rdx], xmm0
0x18000850f  movups  xmm0, xmmword ptr [rax+20h]
0x180008513  movups  xmmword ptr [rdx+10h], xmm1
0x180008517  movups  xmm1, xmmword ptr [rax+30h]
0x18000851b  movups  xmmword ptr [rdx+20h], xmm0
0x18000851f  movups  xmm0, xmmword ptr [rax+40h]
0x180008523  movups  xmmword ptr [rdx+30h], xmm1
0x180008527  movups  xmm1, xmmword ptr [rax+50h]
0x18000852b  movups  xmmword ptr [rdx+40h], xmm0
0x18000852f  movups  xmm0, xmmword ptr [rax+60h]
0x180008533  movups  xmmword ptr [rdx+50h], xmm1
0x180008537  movups  xmm1, xmmword ptr [rax+70h]
0x18000853b  add     rax, r9
0x18000853e  movups  xmmword ptr [rdx+60h], xmm0
0x180008542  movups  xmmword ptr [rdx+70h], xmm1
0x180008546  add     rdx, r9
0x180008549  sub     r8, 1
0x18000854d  jnz     short loc_180008505
0x18000854f  movups  xmm0, xmmword ptr [rax]
0x180008552  movzx   eax, word ptr [rax+10h]
0x180008556  movups  xmmword ptr [rdx], xmm0
0x180008559  mov     [rdx+10h], ax
0x18000855d  lea     eax, [rcx+89h]
0x180008563  cmp     eax, ecx
0x180008565  jb      short loc_180008576
0x180008567  mov     edi, eax
0x180008569  mov     ecx, 0FFFFFFFFh
0x18000856e  add     rax, rax
0x180008571  cmp     rax, rcx
0x180008574  jbe     short loc_18000859E
0x180008576  mov     eax, 80070216h
0x18000857b  mov     rcx, [rsp+168h+var_28]
0x180008583  xor     rcx, rsp; StackCookie
0x180008586  call    __security_check_cookie
0x18000858b  mov     rbx, [rsp+168h+arg_18]
0x180008593  add     rsp, 150h
0x18000859a  pop     rdi
0x18000859b  pop     rsi
0x18000859c  pop     rbp
0x18000859d  retn
0x18000859e  mov     ecx, eax; cb
0x1800085a0  call    cs:__imp_CoTaskMemAlloc
0x1800085a6  mov     rbx, rax
0x1800085a9  test    rax, rax
0x1800085ac  jz      short loc_1800085CE
0x1800085ae  mov     r9, rbp
0x1800085b1  lea     r8, [rsp+168h+var_148]; unsigned __int16 *
0x1800085b6  mov     rdx, rdi; unsigned __int64
0x1800085b9  mov     rcx, rax; unsigned __int16 *
0x1800085bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800085c1  mov     edi, eax
0x1800085c3  test    eax, eax
0x1800085c5  js      short loc_1800085D5
0x1800085c7  mov     [rsi], rbx
0x1800085ca  mov     eax, edi
0x1800085cc  jmp     short loc_18000857B
0x1800085ce  mov     edi, 8007000Eh
0x1800085d3  jmp     short loc_1800085C7
0x1800085d5  mov     rcx, rbx; pv
0x1800085d8  call    cs:__imp_CoTaskMemFree
0x1800085de  xor     ebx, ebx
0x1800085e0  jmp     short loc_1800085C7
```
