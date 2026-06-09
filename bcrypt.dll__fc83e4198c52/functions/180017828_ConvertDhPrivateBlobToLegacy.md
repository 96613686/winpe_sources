# ConvertDhPrivateBlobToLegacy

- ea: `0x180017828`
- end: `0x180017979`
- name: `ConvertDhPrivateBlobToLegacy`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f1fc`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180017828`
- `0x18001b7a9`

## string_xrefs

- `0x180017946`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertDhPrivateBlobToLegacy(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  int v5; // edx
  unsigned int v8; // edx
  unsigned int v9; // ebx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r10
  unsigned __int64 v17; // [rsp+20h] [rbp-30h]
  _OWORD v18[2]; // [rsp+30h] [rbp-20h] BYREF

  v5 = *(_DWORD *)(a1 + 4);
  if ( (unsigned int)(v5 - 64) > 0x1C0 )
  {
    v9 = -2146893783;
    DebugTraceError(
      2148073513LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      2830);
    return v9;
  }
  v8 = 4 * v5 + 52;
  *a5 = v8;
  if ( a3 )
  {
    if ( a4 < v8 )
      return (unsigned int)-2146893784;
    v10 = (char *)a3 + 52;
    v11 = a1 + 8;
    HIDWORD(v17) = 8 * *(_DWORD *)(a1 + 4);
    *(_QWORD *)&v18[0] = HIDWORD(v17) | 0xFFFFFFFF00000000uLL;
    memset((char *)v18 + 8, 0, 20);
    LODWORD(v17) = 877151232;
    memset_0(a3, 0, a4);
    *a3 = 0xAA0100000307LL;
    *(_OWORD *)(a3 + 1) = v17;
    *(_OWORD *)(a3 + 3) = v18[0];
    *(_OWORD *)((char *)a3 + 36) = *(_OWORD *)((char *)v18 + 12);
    ReverseMemCopy(v10, v11, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(&v10[*(unsigned int *)(a1 + 4)], *(unsigned int *)(a1 + 4) + v11, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v12, *(unsigned int *)(a1 + 4) + v13, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v14, *(unsigned int *)(a1 + 4) + v15, *(unsigned int *)(a1 + 4));
  }
  return 0;
}

```

## disassembly

```asm
0x180017828  mov     [rsp-18h+arg_8], rbx
0x18001782d  mov     [rsp-18h+arg_10], rsi
0x180017832  push    rbp
0x180017833  push    rdi
0x180017834  push    r14
0x180017836  mov     rbp, rsp
0x180017839  sub     rsp, 50h
0x18001783d  mov     edx, [rcx+4]
0x180017840  mov     rsi, r8
0x180017843  mov     r14, rcx
0x180017846  lea     eax, [rdx-40h]
0x180017849  cmp     eax, 1C0h
0x18001784e  ja      loc_180017941
0x180017854  mov     rax, [rbp+arg_20]
0x180017858  lea     edx, ds:34h[rdx*4]
0x18001785f  mov     [rax], edx
0x180017861  test    r8, r8
0x180017864  jnz     short loc_18001786D
0x180017866  xor     ebx, ebx
0x180017868  jmp     loc_180017961
0x18001786d  cmp     r9d, edx
0x180017870  jnb     short loc_18001787C
0x180017872  mov     ebx, 80090028h
0x180017877  jmp     loc_180017961
0x18001787c  mov     eax, [rcx+4]
0x18001787f  lea     rdi, [r8+34h]
0x180017883  shl     eax, 3
0x180017886  lea     rbx, [rcx+8]
0x18001788a  xorps   xmm0, xmm0
0x18001788d  mov     [rbp+arg_0], 0
0x180017895  mov     r8d, r9d; Size
0x180017898  xor     edx, edx; Val
0x18001789a  mov     rcx, rsi; void *
0x18001789d  mov     dword ptr [rbp+var_30+4], eax
0x1800178a0  mov     dword ptr [rbp+var_20], eax
0x1800178a3  mov     word ptr [rbp+arg_0], 307h
0x1800178a9  mov     dword ptr [rbp+arg_0+4], 0AA01h
0x1800178b0  movdqu  [rbp+var_20+8], xmm0
0x1800178b5  mov     [rbp+var_8], 0
0x1800178bc  mov     dword ptr [rbp+var_30], 34484400h
0x1800178c3  mov     qword ptr [rbp+var_30+8], 0
0x1800178cb  mov     dword ptr [rbp+var_20+4], 0FFFFFFFFh
0x1800178d2  call    memset_0
0x1800178d7  movups  xmm0, [rbp+var_30]
0x1800178db  mov     rax, [rbp+arg_0]
0x1800178df  mov     rdx, rbx
0x1800178e2  movups  xmm1, [rbp+var_20]
0x1800178e6  mov     [rsi], rax
0x1800178e9  mov     rcx, rdi
0x1800178ec  movups  xmmword ptr [rsi+8], xmm0
0x1800178f0  movups  xmm0, [rbp+var_20+0Ch]
0x1800178f4  movups  xmmword ptr [rsi+18h], xmm1
0x1800178f8  movups  xmmword ptr [rsi+24h], xmm0
0x1800178fc  mov     r8d, [r14+4]
0x180017900  call    ReverseMemCopy
0x180017905  mov     r8d, [r14+4]
0x180017909  lea     r9, [r8+rbx]
0x18001790d  mov     rdx, r9
0x180017910  lea     rcx, [r8+rdi]
0x180017914  call    ReverseMemCopy
0x180017919  mov     r8d, [r14+4]
0x18001791d  add     rcx, r8
0x180017920  lea     r10, [r8+r9]
0x180017924  mov     rdx, r10
0x180017927  call    ReverseMemCopy
0x18001792c  mov     r8d, [r14+4]
0x180017930  add     rcx, r8
0x180017933  lea     rdx, [r8+r10]
0x180017937  call    ReverseMemCopy
0x18001793c  jmp     loc_180017866
0x180017941  mov     ebx, 80090029h
0x180017946  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001794d  mov     ecx, ebx
0x18001794f  lea     rdx, aStatus; "Status"
0x180017956  mov     r9d, 0B0Eh
0x18001795c  call    DebugTraceError
0x180017961  lea     r11, [rsp+50h+var_s0]
0x180017966  mov     eax, ebx
0x180017968  mov     rbx, [r11+28h]
0x18001796c  mov     rsi, [r11+30h]
0x180017970  mov     rsp, r11
0x180017973  pop     r14
0x180017975  pop     rdi
0x180017976  pop     rbp
0x180017977  retn
```
