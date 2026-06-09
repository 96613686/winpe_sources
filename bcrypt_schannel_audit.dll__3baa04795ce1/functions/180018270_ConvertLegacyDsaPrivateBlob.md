# ConvertLegacyDsaPrivateBlob

- ea: `0x180018270`
- end: `0x180018459`
- name: `ConvertLegacyDsaPrivateBlob`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008890`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180018270`
- `0x18001b480`
- `0x18001b7a9`

## string_xrefs

- `0x1800182a5`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18001842f`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertLegacyDsaPrivateBlob(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4, unsigned int *a5)
{
  size_t v6; // rbp
  unsigned int v8; // eax
  unsigned int v9; // r11d
  unsigned int v10; // edi
  int v12; // r14d
  __int128 v13; // xmm1
  int v14; // edi
  unsigned int v15; // ecx
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // r11
  __int64 v19; // r10
  __int64 v20; // r10
  __int64 v21; // r11
  __int64 v22; // r9
  __int64 v23; // r10
  __int64 v24; // rcx
  _BYTE v25[56]; // [rsp+38h] [rbp-50h] BYREF

  v6 = a4;
  v8 = VerifyLegacyDsaPrivateBlob();
  v10 = v8;
  if ( v8 )
  {
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v10;
  }
  if ( !a1 || v9 < 0x34 )
  {
    v16 = -2146893785;
    v24 = 2148073511LL;
    goto LABEL_14;
  }
  if ( (unsigned __int16)*(_QWORD *)a1 != 775 || HIDWORD(*(_QWORD *)a1) != 8704 )
  {
    v24 = 2148073475LL;
    v16 = -2146893821;
LABEL_14:
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v16;
  }
  v12 = *(_DWORD *)(a1 + 20);
  v13 = *(_OWORD *)(a1 + 36);
  v14 = *(_DWORD *)(a1 + 12) >> 3;
  *(_OWORD *)v25 = *(_OWORD *)(a1 + 24);
  v15 = 3 * (v14 + 24);
  *a5 = v15;
  *(_OWORD *)&v25[12] = v13;
  if ( a3 )
  {
    if ( (unsigned int)v6 < v15 )
      return (unsigned int)-2146893784;
    memset_0(a3, 0, v6);
    *a3 = 1448104772;
    a3[1] = v14;
    ReverseMemCopy(a3 + 2, &v25[4], 4);
    ReverseMemCopy(a3 + 3, &v25[8], 20);
    ReverseMemCopy(a3 + 13, a1 + 52, (unsigned int)a3[1]);
    ReverseMemCopy(a3 + 8, (unsigned int)a3[1] + v17, 20);
    ReverseMemCopy(v19, v18 + 20, (unsigned int)a3[1]);
    ReverseMemCopy((unsigned int)a3[1] + v20, v21 + a3[1] + ((unsigned int)(v12 + 7) >> 3), (unsigned int)a3[1]);
    ReverseMemCopy(v23 + (unsigned int)a3[1], v22 + (unsigned int)a3[1], 20);
  }
  return 0;
}

```

## disassembly

```asm
0x180018270  mov     [rsp+arg_8], rbx
0x180018275  push    rbp
0x180018276  push    rsi
0x180018277  push    rdi
0x180018278  push    r14
0x18001827a  push    r15
0x18001827c  sub     rsp, 60h
0x180018280  mov     r15, [rsp+88h+arg_20]
0x180018288  mov     rsi, r8
0x18001828b  mov     ebp, r9d
0x18001828e  mov     r11d, edx
0x180018291  mov     rbx, rcx
0x180018294  call    VerifyLegacyDsaPrivateBlob
0x180018299  mov     edi, eax
0x18001829b  test    eax, eax
0x18001829d  jz      short loc_1800182C1
0x18001829f  mov     r9d, 83Eh
0x1800182a5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800182ac  lea     rdx, aStatus; "Status"
0x1800182b3  mov     ecx, eax
0x1800182b5  call    DebugTraceError
0x1800182ba  mov     eax, edi
0x1800182bc  jmp     loc_180018444
0x1800182c1  test    rbx, rbx
0x1800182c4  jz      loc_180018422
0x1800182ca  cmp     r11d, 34h ; '4'
0x1800182ce  jb      loc_180018422
0x1800182d4  mov     rax, [rbx]
0x1800182d7  mov     [rsp+88h+var_68], rax
0x1800182dc  cmp     al, 7
0x1800182de  jz      short loc_1800182EB
0x1800182e0  mov     r9d, 854h
0x1800182e6  jmp     loc_180018419
0x1800182eb  cmp     byte ptr [rsp+88h+var_68+1], 3
0x1800182f0  jnz     loc_180018413
0x1800182f6  cmp     dword ptr [rsp+88h+var_68+4], 2200h
0x1800182fe  jnz     loc_180018413
0x180018304  mov     edi, [rbx+0Ch]
0x180018307  mov     eax, [rbx+8]
0x18001830a  movups  xmm0, xmmword ptr [rbx+18h]
0x18001830e  mov     r14d, [rbx+14h]
0x180018312  movups  xmm1, xmmword ptr [rbx+24h]
0x180018316  mov     [rsp+88h+var_60], eax
0x18001831a  mov     eax, [rbx+10h]
0x18001831d  mov     [rsp+88h+var_5C], edi
0x180018321  shr     edi, 3
0x180018324  mov     [rsp+88h+var_58], eax
0x180018328  mov     [rsp+88h+var_54], r14d
0x18001832d  movups  [rsp+88h+var_50], xmm0
0x180018332  lea     eax, [rdi+18h]
0x180018335  lea     ecx, [rax+rax*2]
0x180018338  mov     [r15], ecx
0x18001833b  movups  [rsp+88h+var_50+0Ch], xmm1
0x180018340  test    rsi, rsi
0x180018343  jnz     short loc_18001834C
0x180018345  xor     ebx, ebx
0x180018347  jmp     loc_180018442
0x18001834c  cmp     ebp, ecx
0x18001834e  jnb     short loc_18001835A
0x180018350  mov     ebx, 80090028h
0x180018355  jmp     loc_180018442
0x18001835a  mov     r8, rbp; Size
0x18001835d  xor     edx, edx; Val
0x18001835f  mov     rcx, rsi; void *
0x180018362  call    memset_0
0x180018367  lea     rcx, [rsi+8]
0x18001836b  mov     dword ptr [rsi], 56505344h
0x180018371  mov     r8d, 4
0x180018377  mov     [rsi+4], edi
0x18001837a  lea     rdx, [rsp+88h+var_50+4]
0x18001837f  call    ReverseMemCopy
0x180018384  mov     edi, 14h
0x180018389  lea     rcx, [rsi+0Ch]
0x18001838d  mov     r8d, edi
0x180018390  lea     rdx, [rsp+88h+var_50+8]
0x180018395  call    ReverseMemCopy
0x18001839a  mov     r8d, [rsi+4]
0x18001839e  lea     r9, [rbx+34h]
0x1800183a2  lea     r10, [rsi+34h]
0x1800183a6  mov     rdx, r9
0x1800183a9  mov     rcx, r10
0x1800183ac  call    ReverseMemCopy
0x1800183b1  mov     ecx, [rsi+4]
0x1800183b4  mov     r8d, edi
0x1800183b7  add     r10, rcx
0x1800183ba  lea     r11, [rcx+r9]
0x1800183be  mov     rdx, r11
0x1800183c1  lea     rcx, [rsi+20h]
0x1800183c5  call    ReverseMemCopy
0x1800183ca  mov     r8d, [rsi+4]
0x1800183ce  add     r11, rdi
0x1800183d1  mov     rdx, r11
0x1800183d4  mov     rcx, r10
0x1800183d7  call    ReverseMemCopy
0x1800183dc  mov     r8d, [rsi+4]
0x1800183e0  lea     r9d, [r14+7]
0x1800183e4  shr     r9d, 3
0x1800183e8  add     r10, r8
0x1800183eb  add     r9d, r8d
0x1800183ee  mov     rcx, r10
0x1800183f1  add     r9, r11
0x1800183f4  mov     rdx, r9
0x1800183f7  call    ReverseMemCopy
0x1800183fc  mov     ecx, [rsi+4]
0x1800183ff  mov     r8d, edi
0x180018402  lea     rdx, [r9+rcx]
0x180018406  add     rcx, r10
0x180018409  call    ReverseMemCopy
0x18001840e  jmp     loc_180018345
0x180018413  mov     r9d, 85Ch
0x180018419  mov     ecx, 80090003h
0x18001841e  mov     ebx, ecx
0x180018420  jmp     short loc_18001842F
0x180018422  mov     ebx, 80090027h
0x180018427  mov     r9d, 846h
0x18001842d  mov     ecx, ebx
0x18001842f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180018436  lea     rdx, aStatus; "Status"
0x18001843d  call    DebugTraceError
0x180018442  mov     eax, ebx
0x180018444  mov     rbx, [rsp+88h+arg_8]
0x18001844c  add     rsp, 60h
0x180018450  pop     r15
0x180018452  pop     r14
0x180018454  pop     rdi
0x180018455  pop     rsi
0x180018456  pop     rbp
0x180018457  retn
```
