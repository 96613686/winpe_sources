# ConvertLegacyRsaPrivateBlob

- ea: `0x18000df40`
- end: `0x18000e0ba`
- name: `ConvertLegacyRsaPrivateBlob`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180005060`
- `0x18000df40`
- `0x18000e0c0`
- `0x18000e0e4`
- `0x18001b7a9`

## string_xrefs

- `0x18000df72`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyRsaPrivateBlob(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // r9d
  unsigned int v7; // r10d
  unsigned int *v8; // r11
  unsigned int v9; // ebx
  int v11; // r15d
  int v12; // eax
  __int64 v13; // rbp
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  int *v17; // rdx
  __int64 v18; // rsi
  _DWORD *v19; // r14
  _BYTE *i; // rcx
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // r10
  int v24; // [rsp+28h] [rbp-30h] BYREF

  v5 = VerifyLegacyRsaPrivateBlob();
  v9 = v5;
  if ( v5 )
  {
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v9;
  }
  if ( !a1 || v7 < 0x14 )
    return 2148073511LL;
  v11 = *(_DWORD *)(a1 + 12);
  v12 = *(_DWORD *)(a1 + 16);
  v13 = (unsigned int)(v11 + 7) >> 3;
  v14 = (unsigned int)(v11 + 15) >> 4;
  v24 = v12;
  if ( (v12 & 0xFF000000) != 0 )
  {
    v15 = 4;
  }
  else if ( (v12 & 0xFF0000) != 0 )
  {
    v15 = 3;
  }
  else
  {
    v15 = ((v12 & 0xFF00) != 0) + 1;
  }
  v16 = v15 + v13 + 2 * v14 + 24;
  *v8 = v16;
  if ( !a3 )
    return 0;
  if ( v6 >= v16 )
  {
    memset_0(a3, 0, v6);
    *a3 = 843141970;
    v17 = &v24;
    a3[1] = v11;
    v18 = a1 + 20;
    a3[2] = v15;
    a3[3] = v13;
    a3[4] = v14;
    a3[5] = v14;
    v19 = a3 + 6;
    for ( i = (char *)v19 + v15 - 1; i >= (_BYTE *)v19; --i )
    {
      *i = *(_BYTE *)v17;
      v17 = (int *)((char *)v17 + 1);
    }
    ReverseMemCopy((char *)v19 + v15, v18, (unsigned int)v13);
    ReverseMemCopy((unsigned int)v13 + v21, v18 + v13, (unsigned int)v14);
    ReverseMemCopy(v23 + (unsigned int)v14, v22 + v14, (unsigned int)v14);
    return 0;
  }
  return 2148073512LL;
}

```

## disassembly

```asm
0x18000df40  mov     [rsp+arg_8], rbx
0x18000df45  push    rbp
0x18000df46  push    rsi
0x18000df47  push    rdi
0x18000df48  push    r14
0x18000df4a  push    r15
0x18000df4c  sub     rsp, 30h
0x18000df50  mov     r11, [rsp+58h+arg_20]
0x18000df58  mov     r14, r8
0x18000df5b  mov     r10d, edx
0x18000df5e  mov     rsi, rcx
0x18000df61  call    VerifyLegacyRsaPrivateBlob
0x18000df66  mov     ebx, eax
0x18000df68  test    eax, eax
0x18000df6a  jz      short loc_18000DF8E
0x18000df6c  mov     r9d, 120h
0x18000df72  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000df79  lea     rdx, aStatus; "Status"
0x18000df80  mov     ecx, eax
0x18000df82  call    DebugTraceError
0x18000df87  mov     eax, ebx
0x18000df89  jmp     loc_18000E0A8
0x18000df8e  test    rsi, rsi
0x18000df91  jz      loc_18000E0A3
0x18000df97  cmp     r10d, 14h
0x18000df9b  jb      loc_18000E0A3
0x18000dfa1  mov     r15d, [rsi+0Ch]
0x18000dfa5  mov     eax, [rsi+8]
0x18000dfa8  mov     [rsp+58h+var_38], eax
0x18000dfac  mov     eax, [rsi+10h]
0x18000dfaf  lea     ebp, [r15+7]
0x18000dfb3  mov     [rsp+58h+var_34], r15d
0x18000dfb8  lea     edi, [r15+0Fh]
0x18000dfbc  shr     ebp, 3
0x18000dfbf  shr     edi, 4
0x18000dfc2  mov     [rsp+58h+var_30], eax
0x18000dfc6  test    eax, 0FF000000h
0x18000dfcb  jz      short loc_18000DFD4
0x18000dfcd  mov     ebx, 4
0x18000dfd2  jmp     short loc_18000DFEF
0x18000dfd4  test    eax, 0FF0000h
0x18000dfd9  jz      short loc_18000DFE2
0x18000dfdb  mov     ebx, 3
0x18000dfe0  jmp     short loc_18000DFEF
0x18000dfe2  and     eax, 0FF00h
0x18000dfe7  neg     eax
0x18000dfe9  sbb     ebx, ebx
0x18000dfeb  neg     ebx
0x18000dfed  inc     ebx
0x18000dfef  lea     ecx, ds:18h[rdi*2]
0x18000dff6  add     ecx, ebp
0x18000dff8  add     ecx, ebx
0x18000dffa  mov     [r11], ecx
0x18000dffd  test    r14, r14
0x18000e000  jnz     short loc_18000E009
0x18000e002  xor     eax, eax
0x18000e004  jmp     loc_18000E0A8
0x18000e009  cmp     r9d, ecx
0x18000e00c  jnb     short loc_18000E018
0x18000e00e  mov     eax, 80090028h
0x18000e013  jmp     loc_18000E0A8
0x18000e018  mov     r8d, r9d; Size
0x18000e01b  xor     edx, edx; Val
0x18000e01d  mov     rcx, r14; void *
0x18000e020  call    memset_0
0x18000e025  mov     dword ptr [r14], 32415352h
0x18000e02c  lea     rdx, [rsp+58h+var_30]
0x18000e031  mov     [r14+4], r15d
0x18000e035  add     rsi, 14h
0x18000e039  mov     [r14+8], ebx
0x18000e03d  mov     [r14+0Ch], ebp
0x18000e041  mov     [r14+10h], edi
0x18000e045  mov     [r14+14h], edi
0x18000e049  add     r14, 18h
0x18000e04d  mov     r10d, ebx
0x18000e050  add     r10, r14
0x18000e053  lea     rcx, [r10-1]
0x18000e057  jmp     short loc_18000E063
0x18000e059  mov     al, [rdx]
0x18000e05b  mov     [rcx], al
0x18000e05d  dec     rcx
0x18000e060  inc     rdx
0x18000e063  cmp     rcx, r14
0x18000e066  jnb     short loc_18000E059
0x18000e068  mov     r8d, ebp
0x18000e06b  mov     rdx, rsi
0x18000e06e  mov     rcx, r10
0x18000e071  call    ReverseMemCopy
0x18000e076  mov     ecx, ebp
0x18000e078  lea     r9, [rsi+rbp]
0x18000e07c  add     r10, rcx
0x18000e07f  mov     r8d, edi
0x18000e082  mov     rcx, r10
0x18000e085  mov     rdx, r9
0x18000e088  call    ReverseMemCopy
0x18000e08d  mov     ecx, edi
0x18000e08f  lea     rdx, [r9+rdi]
0x18000e093  add     rcx, r10
0x18000e096  mov     r8d, edi
0x18000e099  call    ReverseMemCopy
0x18000e09e  jmp     loc_18000E002
0x18000e0a3  mov     eax, 80090027h
0x18000e0a8  mov     rbx, [rsp+58h+arg_8]
0x18000e0ad  add     rsp, 30h
0x18000e0b1  pop     r15
0x18000e0b3  pop     r14
0x18000e0b5  pop     rdi
0x18000e0b6  pop     rsi
0x18000e0b7  pop     rbp
0x18000e0b8  retn
```
