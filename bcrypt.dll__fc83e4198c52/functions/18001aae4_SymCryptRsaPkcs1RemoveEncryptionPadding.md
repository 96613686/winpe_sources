# SymCryptRsaPkcs1RemoveEncryptionPadding

- ea: `0x18001aae4`
- end: `0x18001ac1c`
- name: `SymCryptRsaPkcs1RemoveEncryptionPadding`
- size: `312`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64, __int64, __int64, unsigned __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014d6c`

## callees

- `0x18001aae4`
- `0x18001ac3c`

## pseudocode

```c
__int64 __fastcall SymCryptRsaPkcs1RemoveEncryptionPadding(
        unsigned __int8 *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  int v6; // esi
  int v11; // ebx
  int v12; // r12d
  unsigned int v13; // edi
  int v14; // r9d
  unsigned int v15; // edx
  int v16; // ebx
  int v17; // r8d
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // rbp
  __int64 v22; // rcx
  __int64 i; // r9

  v6 = 0;
  if ( a2 >= 0xB )
  {
    v12 = 0;
    v14 = 0;
    v15 = 2;
    v16 = (-*a1 | -(a1[1] ^ 2)) >> 31;
    v17 = 0;
    do
    {
      v18 = ~(-a1[v15] >> 31);
      v19 = v18 & ~v17;
      v17 |= v18;
      v20 = v15++ & v19;
      v14 |= v20;
    }
    while ( v15 < a2 );
    v11 = ~v17 | ((v14 - 10) >> 31) | v16;
    v13 = ~v11 & (a2 - v14 - 1);
    if ( a4 )
    {
      v21 = a5;
      v22 = (unsigned int)a5;
      LODWORD(v22) = a5 & 0x7FFFFFFF;
      if ( v22 == a5 )
        v6 = (int)(v22 - v13) >> 31;
      SymCryptScsRotateBuffer(a1, a3, (a3 - 1) & (unsigned int)(v14 + 1));
      if ( a5 >= a2 )
        v21 = a2;
      for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
        *(_BYTE *)(i + a4) ^= (unsigned __int8)((int)(i - v13) >> 31) & (a1[i] ^ *(_BYTE *)(i + a4));
    }
  }
  else
  {
    v11 = 0;
    v12 = 32782;
    v13 = 0;
  }
  *a6 = v13;
  return v12 ^ v6 & (v12 ^ 0x800D) ^ v11 & (v12 ^ v6 & (v12 ^ 0x800D) ^ 0x800Eu);
}

```

## disassembly

```asm
0x18001aae4  push    rbx
0x18001aae6  push    rbp
0x18001aae7  push    rsi
0x18001aae8  push    rdi
0x18001aae9  push    r12
0x18001aaeb  push    r13
0x18001aaed  push    r14
0x18001aaef  push    r15
0x18001aaf1  sub     rsp, 28h
0x18001aaf5  xor     esi, esi
0x18001aaf7  mov     r13, r9
0x18001aafa  mov     r10, r8
0x18001aafd  mov     r14, rdx
0x18001ab00  mov     r15, rcx
0x18001ab03  cmp     rdx, 0Bh
0x18001ab07  jnb     short loc_18001AB18
0x18001ab09  xor     ebx, ebx
0x18001ab0b  mov     r12d, 800Eh
0x18001ab11  xor     edi, edi
0x18001ab13  jmp     loc_18001ABE4
0x18001ab18  movzx   ebx, byte ptr [rcx+1]
0x18001ab1c  xor     r12d, r12d
0x18001ab1f  movzx   eax, byte ptr [rcx]
0x18001ab22  xor     r9d, r9d
0x18001ab25  neg     eax
0x18001ab27  lea     edx, [r12+2]
0x18001ab2c  xor     ebx, edx
0x18001ab2e  neg     ebx
0x18001ab30  or      ebx, eax
0x18001ab32  sar     ebx, 1Fh
0x18001ab35  xor     r8d, r8d
0x18001ab38  mov     eax, edx
0x18001ab3a  movzx   ecx, byte ptr [rax+r15]
0x18001ab3f  mov     eax, r8d
0x18001ab42  neg     ecx
0x18001ab44  not     eax
0x18001ab46  sar     ecx, 1Fh
0x18001ab49  not     ecx
0x18001ab4b  and     eax, ecx
0x18001ab4d  or      r8d, ecx
0x18001ab50  and     eax, edx
0x18001ab52  inc     edx
0x18001ab54  or      r9d, eax
0x18001ab57  mov     eax, edx
0x18001ab59  cmp     rax, r14
0x18001ab5c  jb      short loc_18001AB38
0x18001ab5e  lea     eax, [r9-0Ah]
0x18001ab62  not     r8d
0x18001ab65  sar     eax, 1Fh
0x18001ab68  mov     edi, r14d
0x18001ab6b  or      eax, r8d
0x18001ab6e  sub     edi, r9d
0x18001ab71  or      ebx, eax
0x18001ab73  dec     edi
0x18001ab75  mov     eax, ebx
0x18001ab77  not     eax
0x18001ab79  and     edi, eax
0x18001ab7b  test    r13, r13
0x18001ab7e  jz      short loc_18001ABE4
0x18001ab80  mov     rbp, [rsp+68h+arg_20]
0x18001ab88  mov     ecx, ebp
0x18001ab8a  btr     ecx, 1Fh
0x18001ab8e  cmp     rcx, rbp
0x18001ab91  jnz     short loc_18001AB9A
0x18001ab93  mov     esi, ecx
0x18001ab95  sub     esi, edi
0x18001ab97  sar     esi, 1Fh
0x18001ab9a  lea     r8d, [r9+1]
0x18001ab9e  mov     rdx, r10
0x18001aba1  lea     rax, [r10-1]
0x18001aba5  mov     rcx, r15
0x18001aba8  and     r8, rax
0x18001abab  call    SymCryptScsRotateBuffer
0x18001abb0  cmp     rbp, r14
0x18001abb3  cmovnb  rbp, r14
0x18001abb7  xor     r9d, r9d
0x18001abba  test    rbp, rbp
0x18001abbd  jz      short loc_18001ABE4
0x18001abbf  mov     cl, [r9+r13]
0x18001abc3  mov     eax, r9d
0x18001abc6  sub     eax, edi
0x18001abc8  mov     dl, cl
0x18001abca  xor     dl, [r9+r15]
0x18001abce  sar     eax, 1Fh
0x18001abd1  and     dl, al
0x18001abd3  xor     dl, cl
0x18001abd5  mov     [r9+r13], dl
0x18001abd9  inc     r9d
0x18001abdc  mov     eax, r9d
0x18001abdf  cmp     rax, rbp
0x18001abe2  jb      short loc_18001ABBF
0x18001abe4  mov     rax, [rsp+68h+arg_28]
0x18001abec  mov     edx, r12d
0x18001abef  xor     edx, 800Dh
0x18001abf5  mov     ecx, edi
0x18001abf7  and     edx, esi
0x18001abf9  xor     edx, r12d
0x18001abfc  mov     [rax], rcx
0x18001abff  mov     eax, edx
0x18001ac01  xor     eax, 800Eh
0x18001ac06  and     eax, ebx
0x18001ac08  xor     eax, edx
0x18001ac0a  add     rsp, 28h
0x18001ac0e  pop     r15
0x18001ac10  pop     r14
0x18001ac12  pop     r13
0x18001ac14  pop     r12
0x18001ac16  pop     rdi
0x18001ac17  pop     rsi
0x18001ac18  pop     rbp
0x18001ac19  pop     rbx
0x18001ac1a  retn
```
