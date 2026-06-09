# ConvertDhPublicBlobToLegacy

- ea: `0x180017980`
- end: `0x180017ab3`
- name: `ConvertDhPublicBlobToLegacy`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f1fc`

## callees

- `0x180005060`
- `0x18000e0c0`
- `0x180017980`
- `0x18001b7a9`

## string_xrefs

- `0x180017a8a`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertDhPublicBlobToLegacy(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  int v5; // edx
  unsigned int v8; // edx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned __int64 v15; // [rsp+20h] [rbp-38h]
  _BYTE v16[20]; // [rsp+30h] [rbp-28h]

  v5 = *(_DWORD *)(a1 + 4);
  if ( (unsigned int)(v5 - 64) > 0x1C0 )
  {
    v9 = -2146893783;
    DebugTraceError(
      2148073513LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      2704);
    return v9;
  }
  v8 = 3 * (v5 + 16);
  *a5 = v8;
  if ( a3 )
  {
    if ( a4 < v8 )
      return (unsigned int)-2146893784;
    memset_0(a3, 0, a4);
    HIDWORD(v15) = 8 * *(_DWORD *)(a1 + 4);
    *(_OWORD *)&v16[4] = 0;
    LODWORD(v15) = 860374016;
    *(_DWORD *)v16 = -1;
    *(_OWORD *)(a3 + 1) = v15;
    *(_OWORD *)(a3 + 3) = *(_OWORD *)v16;
    *a3 = 0xAA0100000306LL;
    a3[5] = 0;
    ReverseMemCopy(a3 + 6, a1 + 8, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v10, *(unsigned int *)(a1 + 4) + v11, *(unsigned int *)(a1 + 4));
    ReverseMemCopy(*(unsigned int *)(a1 + 4) + v12, *(unsigned int *)(a1 + 4) + v13, *(unsigned int *)(a1 + 4));
  }
  return 0;
}

```

## disassembly

```asm
0x180017980  mov     [rsp+arg_8], rbx
0x180017985  push    rdi
0x180017986  sub     rsp, 50h
0x18001798a  mov     edx, [rcx+4]
0x18001798d  mov     rbx, r8
0x180017990  mov     rdi, rcx
0x180017993  lea     eax, [rdx-40h]
0x180017996  cmp     eax, 1C0h
0x18001799b  ja      loc_180017A85
0x1800179a1  lea     eax, [rdx+10h]
0x1800179a4  lea     edx, [rax+rax*2]
0x1800179a7  mov     rax, [rsp+58h+arg_20]
0x1800179af  mov     [rax], edx
0x1800179b1  test    rbx, rbx
0x1800179b4  jnz     short loc_1800179BD
0x1800179b6  xor     ebx, ebx
0x1800179b8  jmp     loc_180017AA5
0x1800179bd  cmp     r9d, edx
0x1800179c0  jnb     short loc_1800179CC
0x1800179c2  mov     ebx, 80090028h
0x1800179c7  jmp     loc_180017AA5
0x1800179cc  mov     r8d, r9d; Size
0x1800179cf  xor     edx, edx; Val
0x1800179d1  mov     rcx, rbx; void *
0x1800179d4  call    memset_0
0x1800179d9  mov     eax, [rdi+4]
0x1800179dc  lea     r9, [rdi+8]
0x1800179e0  shl     eax, 3
0x1800179e3  lea     rcx, [rbx+30h]
0x1800179e7  xorps   xmm0, xmm0
0x1800179ea  mov     dword ptr [rsp+58h+var_38+4], eax
0x1800179ee  movdqu  [rsp+58h+var_28+4], xmm0
0x1800179f4  mov     [rsp+58h+arg_0], 0
0x1800179fd  mov     rdx, r9
0x180017a00  mov     dword ptr [rsp+58h+var_38], 33484400h
0x180017a08  mov     qword ptr [rsp+58h+var_38+8], 0
0x180017a11  movups  xmm0, [rsp+58h+var_38]
0x180017a16  mov     dword ptr [rsp+58h+var_28], 0FFFFFFFFh
0x180017a1e  movups  xmm1, [rsp+58h+var_28]
0x180017a23  mov     word ptr [rsp+58h+arg_0], 306h
0x180017a2a  movups  xmmword ptr [rbx+8], xmm0
0x180017a2e  mov     dword ptr [rsp+58h+arg_0+4], 0AA01h
0x180017a36  mov     rax, [rsp+58h+arg_0]
0x180017a3b  movups  xmmword ptr [rbx+18h], xmm1
0x180017a3f  mov     [rbx], rax
0x180017a42  mov     [rsp+58h+var_14], 0
0x180017a4a  movsd   xmm0, qword ptr [rsp+40h]
0x180017a50  movsd   qword ptr [rbx+28h], xmm0
0x180017a55  mov     r8d, [rdi+4]
0x180017a59  call    ReverseMemCopy
0x180017a5e  mov     r8d, [rdi+4]
0x180017a62  add     r9, r8
0x180017a65  add     rcx, r8
0x180017a68  mov     rdx, r9
0x180017a6b  call    ReverseMemCopy
0x180017a70  mov     r8d, [rdi+4]
0x180017a74  add     rcx, r8
0x180017a77  lea     rdx, [r8+r9]
0x180017a7b  call    ReverseMemCopy
0x180017a80  jmp     loc_1800179B6
0x180017a85  mov     ebx, 80090029h
0x180017a8a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017a91  mov     ecx, ebx
0x180017a93  lea     rdx, aStatus; "Status"
0x180017a9a  mov     r9d, 0A90h
0x180017aa0  call    DebugTraceError
0x180017aa5  mov     eax, ebx
0x180017aa7  mov     rbx, [rsp+58h+arg_8]
0x180017aac  add     rsp, 50h
0x180017ab0  pop     rdi
0x180017ab1  retn
```
