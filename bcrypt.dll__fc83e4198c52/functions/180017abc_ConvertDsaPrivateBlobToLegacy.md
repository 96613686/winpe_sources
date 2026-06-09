# ConvertDsaPrivateBlobToLegacy

- ea: `0x180017abc`
- end: `0x180017c54`
- name: `ConvertDsaPrivateBlobToLegacy`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000edac`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180017abc`
- `0x18001b7a9`
- `0x18001b7e0`

## string_xrefs

- `0x180017c1f`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertDsaPrivateBlobToLegacy(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  char *v10; // rdi
  unsigned int v11; // r9d
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r10
  __int128 v21; // [rsp+28h] [rbp-38h]
  _OWORD v22[2]; // [rsp+38h] [rbp-28h] BYREF

  v7 = *(_DWORD *)(a1 + 4);
  if ( (unsigned int)(v7 - 64) > 0x40 )
  {
    v9 = -2146893783;
    DebugTraceError(
      2148073513LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      1665);
    return v9;
  }
  v8 = v7 + 2 * (v7 + 46);
  *a5 = v8;
  if ( a3 )
  {
    if ( a4 < v8 )
      return (unsigned int)-2146893784;
    v10 = (char *)a3 + 52;
    DWORD1(v21) = 8 * *(_DWORD *)(a1 + 4);
    *((_QWORD *)&v21 + 1) = 160;
    LODWORD(v22[0]) = 160;
    memset((char *)v22 + 4, 0, 24);
    LODWORD(v21) = 877876036;
    ReverseMemCopy((char *)v22 + 4, a1 + 8, 4);
    ReverseMemCopy((char *)v22 + 8, a1 + 12, 20);
    memset_0(a3, 0, v11);
    v12 = v22[0];
    *a3 = 0x220000000307LL;
    *(_OWORD *)(a3 + 1) = v21;
    v13 = *(_OWORD *)((char *)v22 + 12);
    *(_OWORD *)(a3 + 3) = v12;
    *(_OWORD *)((char *)a3 + 36) = v13;
    ReverseMemCopy(v10, a1 + 52, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(&v10[*(unsigned int *)(a1 + 4)], a1 + 32, 20);
    ReverseMemCopy(v14 + 20, v15, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v17, *(unsigned int *)(a1 + 4) + v16, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(v19 + *(unsigned int *)(a1 + 4), v18 + *(unsigned int *)(a1 + 4), 20);
  }
  return 0;
}

```

## disassembly

```asm
0x180017abc  push    rbp
0x180017abe  push    rbx
0x180017abf  push    rsi
0x180017ac0  push    rdi
0x180017ac1  push    r14
0x180017ac3  mov     rbp, rsp
0x180017ac6  sub     rsp, 60h
0x180017aca  mov     rax, cs:__security_cookie
0x180017ad1  xor     rax, rsp
0x180017ad4  mov     [rbp+var_8], rax
0x180017ad8  mov     rsi, rcx
0x180017adb  mov     r14, r8
0x180017ade  mov     rcx, [rbp+arg_20]
0x180017ae2  mov     edx, [rsi+4]
0x180017ae5  lea     eax, [rdx-40h]
0x180017ae8  cmp     eax, 40h ; '@'
0x180017aeb  ja      loc_180017C1A
0x180017af1  lea     eax, [rdx+2Eh]
0x180017af4  lea     eax, [rdx+rax*2]
0x180017af7  mov     [rcx], eax
0x180017af9  test    r8, r8
0x180017afc  jnz     short loc_180017B05
0x180017afe  xor     ebx, ebx
0x180017b00  jmp     loc_180017C3A
0x180017b05  cmp     r9d, eax
0x180017b08  jnb     short loc_180017B14
0x180017b0a  mov     ebx, 80090028h
0x180017b0f  jmp     loc_180017C3A
0x180017b14  mov     eax, [rsi+4]
0x180017b17  lea     rdi, [r8+34h]
0x180017b1b  shl     eax, 3
0x180017b1e  lea     rdx, [rsi+8]
0x180017b22  mov     dword ptr [rbp+var_38+4], eax
0x180017b25  lea     rcx, [rbp+var_28+4]
0x180017b29  mov     eax, 0A0h
0x180017b2e  mov     [rbp+var_40], 0
0x180017b36  xorps   xmm0, xmm0
0x180017b39  mov     qword ptr [rbp+var_38+8], rax
0x180017b3d  mov     r8d, 4
0x180017b43  mov     dword ptr [rbp+var_28], eax
0x180017b46  lea     rbx, [rsi+34h]
0x180017b4a  mov     word ptr [rbp+var_40], 307h
0x180017b50  mov     dword ptr [rbp+var_40+4], 2200h
0x180017b57  movdqu  [rbp+var_28+4], xmm0
0x180017b5c  mov     [rbp+var_14], 0
0x180017b64  mov     dword ptr [rbp+var_38], 34535344h
0x180017b6b  call    ReverseMemCopy
0x180017b70  lea     rdx, [rsi+0Ch]
0x180017b74  mov     r8d, 14h
0x180017b7a  lea     rcx, [rbp+var_28+8]
0x180017b7e  call    ReverseMemCopy
0x180017b83  mov     r8d, r9d; Size
0x180017b86  xor     edx, edx; Val
0x180017b88  mov     rcx, r14; void *
0x180017b8b  call    memset_0
0x180017b90  movups  xmm0, [rbp+var_38]
0x180017b94  mov     rax, [rbp+var_40]
0x180017b98  mov     rdx, rbx
0x180017b9b  movups  xmm1, [rbp+var_28]
0x180017b9f  mov     [r14], rax
0x180017ba2  mov     rcx, rdi
0x180017ba5  movups  xmmword ptr [r14+8], xmm0
0x180017baa  movups  xmm0, [rbp+var_28+0Ch]
0x180017bae  movups  xmmword ptr [r14+18h], xmm1
0x180017bb3  movups  xmmword ptr [r14+24h], xmm0
0x180017bb8  mov     r8d, [rsi+4]
0x180017bbc  call    ReverseMemCopy
0x180017bc1  mov     ecx, [rsi+4]
0x180017bc4  lea     rdx, [rsi+20h]
0x180017bc8  mov     r8d, 14h
0x180017bce  lea     r9, [rcx+rbx]
0x180017bd2  add     rcx, rdi
0x180017bd5  call    ReverseMemCopy
0x180017bda  mov     r8d, [rsi+4]
0x180017bde  mov     rdx, r9
0x180017be1  add     rcx, 14h
0x180017be5  call    ReverseMemCopy
0x180017bea  mov     r8d, [rsi+4]
0x180017bee  add     r9, r8
0x180017bf1  mov     rdx, r9
0x180017bf4  lea     r10, [r8+rcx]
0x180017bf8  mov     rcx, r10
0x180017bfb  call    ReverseMemCopy
0x180017c00  mov     ecx, [rsi+4]
0x180017c03  mov     r8d, 14h
0x180017c09  lea     rdx, [r9+rcx]
0x180017c0d  add     rcx, r10
0x180017c10  call    ReverseMemCopy
0x180017c15  jmp     loc_180017AFE
0x180017c1a  mov     ebx, 80090029h
0x180017c1f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017c26  mov     ecx, ebx
0x180017c28  lea     rdx, aStatus; "Status"
0x180017c2f  mov     r9d, 681h
0x180017c35  call    DebugTraceError
0x180017c3a  mov     eax, ebx
0x180017c3c  mov     rcx, [rbp+var_8]
0x180017c40  xor     rcx, rsp; StackCookie
0x180017c43  call    __security_check_cookie
0x180017c48  add     rsp, 60h
0x180017c4c  pop     r14
0x180017c4e  pop     rdi
0x180017c4f  pop     rsi
0x180017c50  pop     rbx
0x180017c51  pop     rbp
0x180017c52  retn
```
