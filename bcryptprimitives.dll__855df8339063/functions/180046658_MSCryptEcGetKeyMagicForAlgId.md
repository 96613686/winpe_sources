# MSCryptEcGetKeyMagicForAlgId

- ea: `0x180046658`
- end: `0x18004672f`
- name: `MSCryptEcGetKeyMagicForAlgId`
- size: `215`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180045b60`
- `0x180046120`
- `0x180046410`
- `0x180047c50`
- `0x180048430`
- `0x1800679b8`

## callees

- `0x18000ecb0`
- `0x180046658`
- `0x180056520`

## string_xrefs

- `0x1800466f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcGetKeyMagicForAlgId(int a1, __int64 *a2, int a3, int a4, _DWORD *a5)
{
  wchar_t **v5; // r15
  __int64 v8; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  unsigned int v14; // ebx

  v5 = &off_180084710;
  if ( !a3 )
    v5 = &off_1800847D0;
  v8 = 0;
  while ( 1 )
  {
    v10 = (__int64)&v5[6 * v8];
    if ( a1 == *(_DWORD *)(v10 + 8) )
      break;
    if ( (unsigned int)(a1 - 196618) <= 1 )
    {
      if ( a2 )
      {
        v11 = *a2;
        if ( *a2 )
        {
          if ( *(_DWORD *)(v11 + 12) == *(_DWORD *)(v10 + 20)
            && (unsigned int)TestIfCurveParametersAreEqual(v11, *(_QWORD *)(v10 + 32)) )
          {
            v12 = (__int64)&v5[6 * v8];
            v10 = a4 != 0 ? 16LL : 12LL;
            goto LABEL_14;
          }
        }
      }
    }
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= 4 )
      goto LABEL_15;
  }
  v12 = a4 != 0 ? 16LL : 12LL;
LABEL_14:
  v13 = *(_DWORD *)(v10 + v12);
  if ( !v13 )
  {
LABEL_15:
    v14 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 332);
    return v14;
  }
  v14 = 0;
  *a5 = v13;
  return v14;
}

```

## disassembly

```asm
0x180046658  push    rbx
0x18004665a  push    rbp
0x18004665b  push    rsi
0x18004665c  push    rdi
0x18004665d  push    r14
0x18004665f  push    r15
0x180046661  sub     rsp, 28h
0x180046665  test    r8d, r8d
0x180046668  lea     rax, off_1800847D0; "ECDH_P256"
0x18004666f  lea     r15, off_180084710; "ECDSA_P256"
0x180046676  mov     edi, r9d
0x180046679  cmovz   r15, rax
0x18004667d  mov     r14, rdx
0x180046680  xor     esi, esi
0x180046682  mov     ebp, ecx
0x180046684  lea     rbx, [rsi+rsi*2]
0x180046688  shl     rbx, 4
0x18004668c  add     rbx, r15
0x18004668f  cmp     ebp, [rbx+8]
0x180046692  jz      short loc_1800466DB
0x180046694  lea     eax, [rbp-3000Ah]
0x18004669a  cmp     eax, 1
0x18004669d  ja      short loc_1800466C1
0x18004669f  test    r14, r14
0x1800466a2  jz      short loc_1800466C1
0x1800466a4  mov     rcx, [r14]
0x1800466a7  test    rcx, rcx
0x1800466aa  jz      short loc_1800466C1
0x1800466ac  mov     eax, [rbx+14h]
0x1800466af  cmp     [rcx+0Ch], eax
0x1800466b2  jnz     short loc_1800466C1
0x1800466b4  mov     rdx, [rbx+20h]
0x1800466b8  call    TestIfCurveParametersAreEqual
0x1800466bd  test    eax, eax
0x1800466bf  jnz     short loc_1800466CA
0x1800466c1  inc     esi
0x1800466c3  cmp     esi, 4
0x1800466c6  jb      short loc_180046684
0x1800466c8  jmp     short loc_1800466EE
0x1800466ca  mov     rax, rbx
0x1800466cd  neg     edi
0x1800466cf  sbb     rbx, rbx
0x1800466d2  and     ebx, 4
0x1800466d5  add     rbx, 0Ch
0x1800466d9  jmp     short loc_1800466E7
0x1800466db  neg     edi
0x1800466dd  sbb     rax, rax
0x1800466e0  and     eax, 4
0x1800466e3  add     rax, 0Ch
0x1800466e7  mov     ecx, [rbx+rax]
0x1800466ea  test    ecx, ecx
0x1800466ec  jnz     short loc_180046713
0x1800466ee  mov     r9d, 14Ch
0x1800466f4  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800466fb  lea     rdx, aStatus; "Status"
0x180046702  mov     ecx, 0C000000Dh
0x180046707  mov     ebx, 0C000000Dh
0x18004670c  call    DebugTraceError
0x180046711  jmp     short loc_18004671F
0x180046713  mov     rax, [rsp+58h+arg_20]
0x18004671b  xor     ebx, ebx
0x18004671d  mov     [rax], ecx
0x18004671f  mov     eax, ebx
0x180046721  add     rsp, 28h
0x180046725  pop     r15
0x180046727  pop     r14
0x180046729  pop     rdi
0x18004672a  pop     rsi
0x18004672b  pop     rbp
0x18004672c  pop     rbx
0x18004672d  retn
```
