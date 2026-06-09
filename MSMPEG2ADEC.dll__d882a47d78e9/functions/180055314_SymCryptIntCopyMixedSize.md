# SymCryptIntCopyMixedSize

- ea: `0x180055314`
- end: `0x1800553b0`
- name: `SymCryptIntCopyMixedSize`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18005158c`
- `0x1800561d0`
- `0x1800567d4`

## callees

- `0x180009170`
- `0x180055314`
- `0x1800886fc`

## pseudocode

```c
__int64 __fastcall SymCryptIntCopyMixedSize(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned int v5; // esi
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  _QWORD *v8; // rax
  int v9; // ecx
  __int64 v10; // rdx

  v2 = 0;
  if ( a1 != a2 )
  {
    v5 = *(_DWORD *)(a1 + 4);
    if ( v5 >= *(_DWORD *)(a2 + 4) )
      v5 = *(_DWORD *)(a2 + 4);
    memcpy_0((void *)(a2 + 32), (const void *)(a1 + 32), v5 << 6);
    v6 = *(_DWORD *)(a2 + 4);
    if ( v6 > v5 )
      SymCryptWipeAsm(a2 + 32 + 64LL * v5, (v6 - v5) << 6);
    v7 = *(_DWORD *)(a1 + 4);
    if ( v7 > v5 )
    {
      v8 = (_QWORD *)(a1 + 32 + 64LL * v5);
      v9 = (8 * (v7 - v5)) & 0x1FFFFFFF;
      v10 = 0;
      if ( v9 )
      {
        do
        {
          v10 |= *v8++;
          --v9;
        }
        while ( v9 );
        if ( v10 )
          return 32781;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180055314  push    rbx
0x180055316  push    rbp
0x180055317  push    rsi
0x180055318  push    rdi
0x180055319  push    r14
0x18005531b  sub     rsp, 20h
0x18005531f  xor     ebx, ebx
0x180055321  mov     rbp, rdx
0x180055324  mov     rdi, rcx
0x180055327  cmp     rcx, rdx
0x18005532a  jz      short loc_1800553A2
0x18005532c  mov     eax, [rdx+4]
0x18005532f  lea     rdx, [rcx+20h]; Src
0x180055333  mov     esi, [rcx+4]
0x180055336  cmp     esi, eax
0x180055338  lea     rcx, [rbp+20h]; void *
0x18005533c  cmovnb  esi, eax
0x18005533f  mov     r8d, esi
0x180055342  shl     r8d, 6; Size
0x180055346  call    memcpy_0
0x18005534b  mov     ecx, [rbp+4]
0x18005534e  mov     eax, esi
0x180055350  shl     eax, 4
0x180055353  mov     r14d, eax
0x180055356  cmp     ecx, esi
0x180055358  jbe     short loc_18005536E
0x18005535a  sub     ecx, esi
0x18005535c  shl     ecx, 6
0x18005535f  mov     edx, ecx
0x180055361  lea     rcx, [rbp+20h]
0x180055365  lea     rcx, [rcx+rax*4]
0x180055369  call    SymCryptWipeAsm
0x18005536e  mov     ecx, [rdi+4]
0x180055371  cmp     ecx, esi
0x180055373  jbe     short loc_1800553A2
0x180055375  sub     ecx, esi
0x180055377  lea     rax, [rdi+20h]
0x18005537b  shl     ecx, 6
0x18005537e  lea     rax, [rax+r14*4]
0x180055382  shr     ecx, 3
0x180055385  xor     edx, edx
0x180055387  test    ecx, ecx
0x180055389  jz      short loc_1800553A2
0x18005538b  or      rdx, [rax]
0x18005538e  lea     rax, [rax+8]
0x180055392  add     ecx, 0FFFFFFFFh
0x180055395  jnz     short loc_18005538B
0x180055397  test    rdx, rdx
0x18005539a  mov     eax, 800Dh
0x18005539f  cmovnz  ebx, eax
0x1800553a2  mov     eax, ebx
0x1800553a4  add     rsp, 20h
0x1800553a8  pop     r14
0x1800553aa  pop     rdi
0x1800553ab  pop     rsi
0x1800553ac  pop     rbp
0x1800553ad  pop     rbx
0x1800553ae  retn
```
