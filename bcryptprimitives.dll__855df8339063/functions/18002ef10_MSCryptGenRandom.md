# MSCryptGenRandom

- ea: `0x18002ef10`
- end: `0x18002f000`
- name: `MSCryptGenRandom`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18002eb90`
- `0x18002ef10`
- `0x18002f2e0`

## string_xrefs

- `0x18002efe1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\rng.c`

## pseudocode

```c
__int64 __fastcall MSCryptGenRandom(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rsi
  __int64 result; // rax
  unsigned __int64 v6; // rbx
  __int128 *v7; // rbp
  __int64 v8; // rdi
  __int128 *v9; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+28h] [rbp-10h] BYREF

  v4 = a2;
  if ( (a4 & 0xFFFFFFFE) != 0 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\rng.c", 214);
    return 3221225485LL;
  }
  if ( !a1 || *(_DWORD *)(a1 + 4) != 1297239623 )
    return 3221225480LL;
  if ( !a2 )
    return 3221225485LL;
  if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 327681) > 2 )
    return 3221225480LL;
  v9 = 0;
  v10 = 0;
  v6 = (unsigned int)a3;
  AesRNGState_select(&v9, a2, a3);
  if ( !v6 )
    return 0;
  v7 = v9;
  do
  {
    v8 = 0x10000;
    if ( v6 < 0x10000 )
      v8 = v6;
    result = AesRNGState_generate(v7, v4, v8, &v10);
    v4 += v8;
    v6 -= v8;
  }
  while ( v6 );
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18002ef10  push    rsi
0x18002ef12  sub     rsp, 30h
0x18002ef16  mov     rsi, rdx
0x18002ef19  test    r9d, 0FFFFFFFEh
0x18002ef20  jnz     loc_18002EFDB
0x18002ef26  test    rcx, rcx
0x18002ef29  jz      short loc_18002EF34
0x18002ef2b  cmp     dword ptr [rcx+4], 4D524E47h
0x18002ef32  jz      short loc_18002EF40
0x18002ef34  mov     eax, 0C0000008h
0x18002ef39  add     rsp, 30h
0x18002ef3d  pop     rsi
0x18002ef3e  retn
0x18002ef40  test    rdx, rdx
0x18002ef43  jz      loc_18002EFF9
0x18002ef49  mov     eax, [rcx+8]
0x18002ef4c  sub     eax, 50001h
0x18002ef51  cmp     eax, 2
0x18002ef54  ja      short loc_18002EF34
0x18002ef56  mov     [rsp+38h+arg_0], rbx
0x18002ef5b  lea     rcx, [rsp+38h+var_18]
0x18002ef60  mov     [rsp+38h+arg_18], r14
0x18002ef65  xor     r14d, r14d
0x18002ef68  mov     [rsp+38h+var_18], r14
0x18002ef6d  mov     [rsp+38h+var_10], r14
0x18002ef72  mov     ebx, r8d
0x18002ef75  call    AesRNGState_select
0x18002ef7a  test    rbx, rbx
0x18002ef7d  jz      short loc_18002EFD6
0x18002ef7f  mov     [rsp+38h+arg_8], rbp
0x18002ef84  mov     rbp, [rsp+38h+var_18]
0x18002ef89  mov     [rsp+38h+arg_10], rdi
0x18002ef8e  xchg    ax, ax
0x18002ef90  mov     edi, 10000h
0x18002ef95  lea     r9, [rsp+38h+var_10]
0x18002ef9a  cmp     rbx, rdi
0x18002ef9d  mov     rdx, rsi
0x18002efa0  mov     rcx, rbp
0x18002efa3  cmovb   rdi, rbx
0x18002efa7  mov     r8, rdi
0x18002efaa  call    AesRNGState_generate
0x18002efaf  add     rsi, rdi
0x18002efb2  sub     rbx, rdi
0x18002efb5  jnz     short loc_18002EF90
0x18002efb7  mov     rdi, [rsp+38h+arg_10]
0x18002efbc  mov     rbp, [rsp+38h+arg_8]
0x18002efc1  test    eax, eax
0x18002efc3  jns     short loc_18002EFD6
0x18002efc5  mov     rbx, [rsp+38h+arg_0]
0x18002efca  mov     r14, [rsp+38h+arg_18]
0x18002efcf  add     rsp, 30h
0x18002efd3  pop     rsi
0x18002efd4  retn
0x18002efd6  mov     eax, r14d
0x18002efd9  jmp     short loc_18002EFC5
0x18002efdb  mov     r9d, 0D6h
0x18002efe1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002efe8  lea     rdx, aStatus; "Status"
0x18002efef  mov     ecx, 0C000000Dh
0x18002eff4  call    DebugTraceError
0x18002eff9  mov     eax, 0C000000Dh
0x18002effe  jmp     short loc_18002EFCF
```
