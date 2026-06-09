# BparseInvalidInstallableCombination1

- ea: `0x180072b8c`
- end: `0x180072cfe`
- name: `BparseInvalidInstallableCombination1`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180070d04`

## callees

- `0x180007220`
- `0x18000aa88`
- `0x18000b09c`
- `0x180072b8c`

## string_xrefs

- `0x180072cd2`: `Must have at least 2 objects to define an InvalidInstallableCombination.`
- `0x180072cd9`: `BparseInvalidInstallableCombination1`

## pseudocode

```c
__int64 __fastcall BparseInvalidInstallableCombination1(int a1, unsigned int a2, _QWORD *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  __int64 v6; // rdi
  __int64 v7; // r15
  unsigned int v8; // r14d
  __int64 v9; // rcx
  int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // r9d
  unsigned int v14; // r10d
  __int64 v15; // rdx
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v19; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v20; // [rsp+78h] [rbp+20h] BYREF

  v3 = a3[3];
  v5 = a3[27];
  v6 = a3[21];
  v7 = a2;
  v19 = 0;
  v20 = 0;
  if ( (unsigned int)BparseList(a1, (unsigned int)&v19, (unsigned int)BparsePartiallyQualifiedName, 4, (__int64)a3) )
  {
    v8 = v19;
    LODWORD(v9) = v19;
    v10 = 1;
    if ( *(_DWORD *)(v6 + 8LL * v19 + 4) == -1 )
      goto LABEL_14;
    do
    {
      ++v10;
      v9 = *(unsigned int *)(v6 + 8LL * (unsigned int)v9 + 4);
    }
    while ( *(_DWORD *)(v6 + 8 * v9 + 4) != -1 );
    if ( v10 == 1 )
    {
LABEL_14:
      WriteDbgTraceErrorGpd(
        "BparseInvalidInstallableCombination1",
        "Must have at least 2 objects to define an InvalidInstallableCombination.");
    }
    else
    {
      v11 = BallocElementFromMasterTable(9, &v20, a3);
      v12 = *(_DWORD *)(v7 + v3);
      v13 = v11;
      v14 = v20;
      if ( v12 == 0x7FFFFFFF )
        v12 = -1;
      *(_DWORD *)(v5 + 16LL * v20 + 12) = v12;
      *(_DWORD *)(v7 + v3) = v14;
      if ( v11 )
      {
        do
        {
          if ( *(_WORD *)(v6 + 8LL * v8 + 2) == 0xFFFF )
            *(_WORD *)(v6 + 8LL * v8 + 2) = -1;
          v15 = 2LL * v14;
          *(_DWORD *)(v5 + 8 * v15) = *(unsigned __int16 *)(v6 + 8LL * v8);
          *(_DWORD *)(v5 + 8 * v15 + 4) = *(unsigned __int16 *)(v6 + 8LL * v8 + 2);
          v8 = *(_DWORD *)(v6 + 8LL * v8 + 4);
          if ( v8 == -1 )
            break;
          v16 = 16LL * v14;
          v17 = BallocElementFromMasterTable(9, v16 + v5 + 8, a3);
          v14 = *(_DWORD *)(v16 + v5 + 8);
          v13 = v17;
        }
        while ( v17 );
        if ( v13 )
        {
          *(_DWORD *)(v5 + 16LL * v14 + 8) = -1;
          return v13;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180072b8c  mov     rax, rsp
0x180072b8f  mov     [rax+8], rbx
0x180072b93  mov     [rax+10h], rbp
0x180072b97  push    rsi
0x180072b98  push    rdi
0x180072b99  push    r12
0x180072b9b  push    r14
0x180072b9d  push    r15
0x180072b9f  sub     rsp, 30h
0x180072ba3  mov     rbx, [r8+18h]
0x180072ba7  mov     rsi, r8
0x180072baa  mov     rbp, [r8+0D8h]
0x180072bb1  mov     r9d, 4
0x180072bb7  mov     rdi, [r8+0A8h]
0x180072bbe  mov     r15d, edx
0x180072bc1  lea     rdx, [rax+18h]
0x180072bc5  mov     [rax-38h], r8
0x180072bc9  lea     r8, BparsePartiallyQualifiedName
0x180072bd0  mov     dword ptr [rax+18h], 0
0x180072bd7  mov     dword ptr [rax+20h], 0
0x180072bde  call    BparseList
0x180072be3  test    eax, eax
0x180072be5  jz      loc_180072CE5
0x180072beb  mov     r14d, [rsp+58h+arg_10]
0x180072bf0  or      r12d, 0FFFFFFFFh
0x180072bf4  mov     ecx, r14d
0x180072bf7  mov     edx, 1
0x180072bfc  cmp     [rdi+r14*8+4], r12d
0x180072c01  jz      loc_180072CD2
0x180072c07  mov     eax, ecx
0x180072c09  inc     edx
0x180072c0b  mov     ecx, [rdi+rax*8+4]
0x180072c0f  cmp     [rdi+rcx*8+4], r12d
0x180072c14  jnz     short loc_180072C07
0x180072c16  cmp     edx, 1
0x180072c19  jz      loc_180072CD2
0x180072c1f  mov     r8, rsi
0x180072c22  lea     rdx, [rsp+58h+arg_18]
0x180072c27  mov     ecx, 9
0x180072c2c  call    BallocElementFromMasterTable
0x180072c31  mov     edx, [r15+rbx]
0x180072c35  mov     r9d, eax
0x180072c38  mov     r10d, [rsp+58h+arg_18]
0x180072c3d  mov     ecx, r10d
0x180072c40  add     rcx, rcx
0x180072c43  cmp     edx, 7FFFFFFFh
0x180072c49  cmovz   edx, r12d
0x180072c4d  mov     [rbp+rcx*8+0Ch], edx
0x180072c51  mov     [r15+rbx], r10d
0x180072c55  test    eax, eax
0x180072c57  jz      loc_180072CE5
0x180072c5d  mov     r15d, 0FFFFh
0x180072c63  mov     ecx, r14d
0x180072c66  cmp     [rdi+rcx*8+2], r15w
0x180072c6c  jnz     short loc_180072C74
0x180072c6e  mov     [rdi+rcx*8+2], r15w
0x180072c74  movzx   eax, word ptr [rdi+rcx*8]
0x180072c78  mov     edx, r10d
0x180072c7b  add     rdx, rdx
0x180072c7e  mov     [rbp+rdx*8+0], eax
0x180072c82  movzx   eax, word ptr [rdi+rcx*8+2]
0x180072c87  mov     [rbp+rdx*8+4], eax
0x180072c8b  mov     r14d, [rdi+rcx*8+4]
0x180072c90  cmp     r14d, r12d
0x180072c93  jz      short loc_180072CBD
0x180072c95  lea     rbx, ds:0[rdx*8]
0x180072c9d  mov     r8, rsi
0x180072ca0  lea     rdx, [rbp+8]
0x180072ca4  mov     ecx, 9
0x180072ca9  add     rdx, rbx
0x180072cac  call    BallocElementFromMasterTable
0x180072cb1  mov     r10d, [rbx+rbp+8]
0x180072cb6  mov     r9d, eax
0x180072cb9  test    eax, eax
0x180072cbb  jnz     short loc_180072C63
0x180072cbd  test    r9d, r9d
0x180072cc0  jz      short loc_180072CE5
0x180072cc2  mov     eax, r10d
0x180072cc5  add     rax, rax
0x180072cc8  mov     [rbp+rax*8+8], r12d
0x180072ccd  mov     eax, r9d
0x180072cd0  jmp     short loc_180072CE7
0x180072cd2  lea     rdx, aMustHaveAtLeas; "Must have at least 2 objects to define "...
0x180072cd9  lea     rcx, aBparseinvalidi; "BparseInvalidInstallableCombination1"
0x180072ce0  call    WriteDbgTraceErrorGpd
0x180072ce5  xor     eax, eax
0x180072ce7  mov     rbx, [rsp+58h+arg_0]
0x180072cec  mov     rbp, [rsp+58h+arg_8]
0x180072cf1  add     rsp, 30h
0x180072cf5  pop     r15
0x180072cf7  pop     r14
0x180072cf9  pop     r12
0x180072cfb  pop     rdi
0x180072cfc  pop     rsi
0x180072cfd  retn
```
