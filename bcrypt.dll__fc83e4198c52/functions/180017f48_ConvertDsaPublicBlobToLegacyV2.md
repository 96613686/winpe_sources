# ConvertDsaPublicBlobToLegacyV2

- ea: `0x180017f48`
- end: `0x1800180d0`
- name: `ConvertDsaPublicBlobToLegacyV2`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000edac`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180017f48`
- `0x18001b7a9`
- `0x18001b7e0`

## string_xrefs

- `0x180018097`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertDsaPublicBlobToLegacyV2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int *a5)
{
  int v5; // edx
  unsigned int v8; // ecx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r10
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // r10d
  unsigned int v16; // r10d
  __int64 v17; // xmm1_8
  __int64 v18; // r9
  __int64 v20; // [rsp+28h] [rbp-40h]
  __int128 v21; // [rsp+30h] [rbp-38h] BYREF
  __int64 v22; // [rsp+40h] [rbp-28h]

  v5 = *(_DWORD *)(a1 + 4);
  v22 = 0;
  v21 = 0;
  if ( (unsigned int)(v5 - 64) > 0x40 )
  {
    v9 = -2146893783;
    DebugTraceError(
      2148073513LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      1819);
    return v9;
  }
  v8 = 3 * (v5 + 20);
  *a5 = v8;
  if ( a3 )
  {
    if ( a4 < v8 )
      return (unsigned int)-2146893784;
    HIDWORD(v20) = 8 * *(_DWORD *)(a1 + 4);
    LODWORD(v20) = 827544388;
    memset_0(a3, 0, a4);
    *a3 = 0x220000000206LL;
    a3[1] = v20;
    ReverseMemCopy(a3 + 2, a1 + 52, *(unsigned int *)(a1 + 4));
    ReverseMemCopy((char *)a3 + *(unsigned int *)(a1 + 4) + 16, a1 + 32, 20);
    ReverseMemCopy(v11 + v10, v12, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v13, *(unsigned int *)(a1 + 4) + v14, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(&v21, a1 + 8, (unsigned int)(v15 - 16));
    ReverseMemCopy((char *)&v21 + 4, a1 + 12, v16);
    v17 = v22;
    *(_OWORD *)v18 = v21;
    *(_QWORD *)(v18 + 16) = v17;
  }
  return 0;
}

```

## disassembly

```asm
0x180017f48  mov     [rsp+arg_8], rbx
0x180017f4d  push    rsi
0x180017f4e  push    rdi
0x180017f4f  push    r14
0x180017f51  sub     rsp, 50h
0x180017f55  mov     rax, cs:__security_cookie
0x180017f5c  xor     rax, rsp
0x180017f5f  mov     [rsp+68h+var_20], rax
0x180017f64  mov     edx, [rcx+4]
0x180017f67  xor     eax, eax
0x180017f69  mov     [rsp+68h+var_28], rax
0x180017f6e  xorps   xmm0, xmm0
0x180017f71  mov     r14, r8
0x180017f74  mov     rsi, rcx
0x180017f77  mov     r8, [rsp+68h+arg_20]
0x180017f7f  lea     eax, [rdx-40h]
0x180017f82  movups  [rsp+68h+var_38], xmm0
0x180017f87  cmp     eax, 40h ; '@'
0x180017f8a  ja      loc_180018092
0x180017f90  lea     eax, [rdx+14h]
0x180017f93  lea     ecx, [rax+rax*2]
0x180017f96  mov     [r8], ecx
0x180017f99  test    r14, r14
0x180017f9c  jnz     short loc_180017FA5
0x180017f9e  xor     ebx, ebx
0x180017fa0  jmp     loc_1800180B2
0x180017fa5  cmp     r9d, ecx
0x180017fa8  jnb     short loc_180017FB4
0x180017faa  mov     ebx, 80090028h
0x180017faf  jmp     loc_1800180B2
0x180017fb4  mov     eax, [rsi+4]
0x180017fb7  lea     rdi, [r14+10h]
0x180017fbb  shl     eax, 3
0x180017fbe  lea     rbx, [rsi+34h]
0x180017fc2  mov     [rsp+68h+var_48], 0
0x180017fcb  xor     edx, edx; Val
0x180017fcd  mov     r8d, r9d; Size
0x180017fd0  mov     rcx, r14; void *
0x180017fd3  mov     dword ptr [rsp+68h+var_40+4], eax
0x180017fd7  mov     word ptr [rsp+68h+var_48], 206h
0x180017fde  mov     dword ptr [rsp+68h+var_48+4], 2200h
0x180017fe6  mov     dword ptr [rsp+68h+var_40], 31535344h
0x180017fee  call    memset_0
0x180017ff3  mov     rax, [rsp+68h+var_48]
0x180017ff8  mov     rdx, rbx
0x180017ffb  mov     [r14], rax
0x180017ffe  mov     rcx, rdi
0x180018001  mov     rax, [rsp+68h+var_40]
0x180018006  mov     [r14+8], rax
0x18001800a  mov     r8d, [rsi+4]
0x18001800e  call    ReverseMemCopy
0x180018013  mov     ecx, [rsi+4]
0x180018016  lea     rdx, [rsi+20h]
0x18001801a  mov     r10d, 14h
0x180018020  mov     r8d, r10d
0x180018023  lea     r9, [rcx+rbx]
0x180018027  add     rcx, rdi
0x18001802a  call    ReverseMemCopy
0x18001802f  mov     r8d, [rsi+4]
0x180018033  mov     rdx, r9
0x180018036  add     rcx, r10
0x180018039  call    ReverseMemCopy
0x18001803e  mov     r8d, [rsi+4]
0x180018042  add     rcx, r8
0x180018045  lea     rdx, [r8+r9]
0x180018049  call    ReverseMemCopy
0x18001804e  mov     r9d, [rsi+4]
0x180018052  lea     rdx, [rsi+8]
0x180018056  add     r9, rcx
0x180018059  lea     r8d, [r10-10h]
0x18001805d  lea     rcx, [rsp+68h+var_38]
0x180018062  call    ReverseMemCopy
0x180018067  lea     rdx, [rsi+0Ch]
0x18001806b  mov     r8d, r10d
0x18001806e  lea     rcx, [rsp+68h+var_38+4]
0x180018073  call    ReverseMemCopy
0x180018078  movups  xmm0, [rsp+68h+var_38]
0x18001807d  movsd   xmm1, [rsp+68h+var_28]
0x180018083  movups  xmmword ptr [r9], xmm0
0x180018087  movsd   qword ptr [r9+10h], xmm1
0x18001808d  jmp     loc_180017F9E
0x180018092  mov     ebx, 80090029h
0x180018097  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001809e  mov     ecx, ebx
0x1800180a0  lea     rdx, aStatus; "Status"
0x1800180a7  mov     r9d, 71Bh
0x1800180ad  call    DebugTraceError
0x1800180b2  mov     eax, ebx
0x1800180b4  mov     rcx, [rsp+68h+var_20]
0x1800180b9  xor     rcx, rsp; StackCookie
0x1800180bc  call    __security_check_cookie
0x1800180c1  mov     rbx, [rsp+68h+arg_8]
0x1800180c6  add     rsp, 50h
0x1800180ca  pop     r14
0x1800180cc  pop     rdi
0x1800180cd  pop     rsi
0x1800180ce  retn
```
