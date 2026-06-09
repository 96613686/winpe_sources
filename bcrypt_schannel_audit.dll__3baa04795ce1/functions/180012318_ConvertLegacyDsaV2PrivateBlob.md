# ConvertLegacyDsaV2PrivateBlob

- ea: `0x180012318`
- end: `0x1800124be`
- name: `ConvertLegacyDsaV2PrivateBlob`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18000e0c0`
- `0x180012318`
- `0x18001b520`
- `0x18001b7a9`

## string_xrefs

- `0x18001235d`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x180012399`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyDsaV2PrivateBlob(__int64 a1, int a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  unsigned int v7; // eax
  size_t v8; // r10
  unsigned int *v9; // r11
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // xmm1_8
  __int64 v14; // rcx
  __int64 v15; // r10
  __int64 v16; // rsi
  __int64 v17; // r9
  __int64 v18; // r11
  __int64 v19; // rdi
  size_t v20; // rbx
  char *v21; // rsi
  __int128 v22; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+50h] [rbp-28h]

  if ( !a1 )
  {
    v5 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        99);
    return v5;
  }
  v7 = VerifyLegacyDsaV2PrivateBlob();
  v5 = v7;
  if ( v7 )
  {
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v5;
  }
  v10 = (unsigned int)HIDWORD(*(_QWORD *)(a1 + 8)) >> 3;
  v11 = 3 * (v10 + 24);
  *v9 = v11;
  if ( a3 )
  {
    if ( (unsigned int)v8 < v11 )
      return 2148073512LL;
    v12 = 2 * v10 + 56;
    v13 = *(_QWORD *)(v12 + a1 + 16);
    v22 = *(_OWORD *)(v12 + a1);
    v23 = v13;
    memset_0(a3, 0, v8);
    *a3 = 1448104772;
    a3[1] = v10;
    ReverseMemCopy(a3 + 2, &v22, 4);
    ReverseMemCopy(a3 + 3, (char *)&v22 + 4, 20);
    ReverseMemCopy(a3 + 13, a1 + 16, (unsigned int)a3[1]);
    v14 = (unsigned int)a3[1];
    v16 = v14 + v15;
    ReverseMemCopy(a3 + 8, v14 + v17, 20);
    v19 = v18 + 20;
    ReverseMemCopy(v16, v18 + 20, (unsigned int)a3[1]);
    v20 = (unsigned int)a3[1];
    v21 = (char *)(v20 + v16);
    memset_0(v21, 0, v20);
    ReverseMemCopy(&v21[a3[1]], v19 + v20, 20);
  }
  return 0;
}

```

## disassembly

```asm
0x180012318  mov     [rsp+arg_8], rbx
0x18001231d  push    rsi
0x18001231e  push    rdi
0x18001231f  push    r14
0x180012321  sub     rsp, 60h
0x180012325  mov     r11, [rsp+78h+arg_20]
0x18001232d  mov     r14, r8
0x180012330  mov     r10d, r9d
0x180012333  mov     rdi, rcx
0x180012336  test    rcx, rcx
0x180012339  jnz     short loc_180012388
0x18001233b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012342  lea     rax, WPP_GLOBAL_Control
0x180012349  mov     ebx, 80090027h
0x18001234e  cmp     rcx, rax
0x180012351  jz      short loc_180012381
0x180012353  test    byte ptr [rcx+1Ch], 1
0x180012357  jz      short loc_180012381
0x180012359  mov     rcx, [rcx+10h]
0x18001235d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012364  mov     [rsp+78h+var_48], 963h
0x18001236c  lea     r9, aStatus; "Status"
0x180012373  mov     [rsp+78h+var_50], r8
0x180012378  mov     [rsp+78h+var_58], ebx
0x18001237c  call    WPP_SF_sDsd
0x180012381  mov     eax, ebx
0x180012383  jmp     loc_1800124AC
0x180012388  call    VerifyLegacyDsaV2PrivateBlob
0x18001238d  mov     ebx, eax
0x18001238f  test    eax, eax
0x180012391  jz      short loc_1800123B0
0x180012393  mov     r9d, 96Eh
0x180012399  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800123a0  lea     rdx, aStatus; "Status"
0x1800123a7  mov     ecx, eax
0x1800123a9  call    DebugTraceError
0x1800123ae  jmp     short loc_180012381
0x1800123b0  mov     rbx, [rdi+8]
0x1800123b4  shr     rbx, 20h
0x1800123b8  shr     ebx, 3
0x1800123bb  lea     eax, [rbx+18h]
0x1800123be  lea     ecx, [rax+rax*2]
0x1800123c1  mov     [r11], ecx
0x1800123c4  test    r14, r14
0x1800123c7  jz      loc_1800124AA
0x1800123cd  cmp     r10d, ecx
0x1800123d0  jnb     short loc_1800123DC
0x1800123d2  mov     eax, 80090028h
0x1800123d7  jmp     loc_1800124AC
0x1800123dc  lea     eax, ds:38h[rbx*2]
0x1800123e3  mov     r8, r10; Size
0x1800123e6  movups  xmm0, xmmword ptr [rax+rdi]
0x1800123ea  xor     edx, edx; Val
0x1800123ec  mov     rcx, r14; void *
0x1800123ef  movsd   xmm1, qword ptr [rax+rdi+10h]
0x1800123f5  movups  [rsp+78h+var_38], xmm0
0x1800123fa  movsd   [rsp+78h+var_28], xmm1
0x180012400  call    memset_0
0x180012405  lea     rcx, [r14+8]
0x180012409  mov     dword ptr [r14], 56505344h
0x180012410  mov     r8d, 4
0x180012416  mov     [r14+4], ebx
0x18001241a  lea     rdx, [rsp+78h+var_38]
0x18001241f  call    ReverseMemCopy
0x180012424  mov     r8d, 14h
0x18001242a  lea     rdx, [rsp+78h+var_38+4]
0x18001242f  lea     rcx, [r14+0Ch]
0x180012433  call    ReverseMemCopy
0x180012438  mov     r8d, [r14+4]
0x18001243c  lea     r9, [rdi+10h]
0x180012440  lea     r10, [r14+34h]
0x180012444  mov     rdx, r9
0x180012447  mov     rcx, r10
0x18001244a  call    ReverseMemCopy
0x18001244f  mov     ecx, [r14+4]
0x180012453  mov     r8d, 14h
0x180012459  lea     r11, [rcx+r9]
0x18001245d  lea     rsi, [rcx+r10]
0x180012461  mov     rdx, r11
0x180012464  lea     rcx, [r14+20h]
0x180012468  call    ReverseMemCopy
0x18001246d  mov     r8d, [r14+4]
0x180012471  lea     rdi, [r11+14h]
0x180012475  mov     rdx, rdi
0x180012478  mov     rcx, rsi
0x18001247b  call    ReverseMemCopy
0x180012480  mov     ebx, [r14+4]
0x180012484  xor     edx, edx; Val
0x180012486  add     rsi, rbx
0x180012489  mov     r8d, ebx; Size
0x18001248c  mov     rcx, rsi; void *
0x18001248f  call    memset_0
0x180012494  mov     ecx, [r14+4]
0x180012498  lea     rdx, [rdi+rbx]
0x18001249c  add     rcx, rsi
0x18001249f  mov     r8d, 14h
0x1800124a5  call    ReverseMemCopy
0x1800124aa  xor     eax, eax
0x1800124ac  mov     rbx, [rsp+78h+arg_8]
0x1800124b4  add     rsp, 60h
0x1800124b8  pop     r14
0x1800124ba  pop     rdi
0x1800124bb  pop     rsi
0x1800124bc  retn
```
