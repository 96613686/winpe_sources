# BparseInvalidInstallableCombination1

- ea: `0x180074c18`
- end: `0x180074d8b`
- name: `BparseInvalidInstallableCombination1`
- size: `371`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180072d78`

## callees

- `0x180007150`
- `0x18000aa88`
- `0x18000b0ac`
- `0x180074c18`

## string_xrefs

- `0x180074d5e`: `Must have at least 2 objects to define an InvalidInstallableCombination.`
- `0x180074d65`: `BparseInvalidInstallableCombination1`

## pseudocode

```c
__int64 __fastcall BparseInvalidInstallableCombination1(__int64 a1, unsigned int a2, __int64 a3)
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

  v3 = *(_QWORD *)(a3 + 24);
  v5 = *(_QWORD *)(a3 + 216);
  v6 = *(_QWORD *)(a3 + 168);
  v7 = a2;
  v19 = 0;
  v20 = 0;
  if ( (unsigned int)BparseList(
                       a1,
                       (int *)&v19,
                       (unsigned int (__fastcall *)(__int128 *, __int64, _QWORD, __int64))BparsePartiallyQualifiedName,
                       4u,
                       a3) )
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
        (__int64)"BparseInvalidInstallableCombination1",
        "Must have at least 2 objects to define an InvalidInstallableCombination.");
    }
    else
    {
      v11 = BallocElementFromMasterTable(9, &v20, (_DWORD *)a3);
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
          v17 = BallocElementFromMasterTable(9, (unsigned int *)(v16 + v5 + 8), (_DWORD *)a3);
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
0x180074c18  mov     rax, rsp
0x180074c1b  mov     [rax+8], rbx
0x180074c1f  mov     [rax+10h], rbp
0x180074c23  push    rsi
0x180074c24  push    rdi
0x180074c25  push    r12
0x180074c27  push    r14
0x180074c29  push    r15
0x180074c2b  sub     rsp, 30h
0x180074c2f  mov     rbx, [r8+18h]
0x180074c33  mov     rsi, r8
0x180074c36  mov     rbp, [r8+0D8h]
0x180074c3d  mov     r9d, 4
0x180074c43  mov     rdi, [r8+0A8h]
0x180074c4a  mov     r15d, edx
0x180074c4d  lea     rdx, [rax+18h]
0x180074c51  mov     [rax-38h], r8
0x180074c55  lea     r8, BparsePartiallyQualifiedName
0x180074c5c  mov     dword ptr [rax+18h], 0
0x180074c63  mov     dword ptr [rax+20h], 0
0x180074c6a  call    BparseList
0x180074c6f  test    eax, eax
0x180074c71  jz      loc_180074D71
0x180074c77  mov     r14d, [rsp+58h+arg_10]
0x180074c7c  or      r12d, 0FFFFFFFFh
0x180074c80  mov     ecx, r14d
0x180074c83  mov     edx, 1
0x180074c88  cmp     [rdi+r14*8+4], r12d
0x180074c8d  jz      loc_180074D5E
0x180074c93  mov     eax, ecx
0x180074c95  inc     edx
0x180074c97  mov     ecx, [rdi+rax*8+4]
0x180074c9b  cmp     [rdi+rcx*8+4], r12d
0x180074ca0  jnz     short loc_180074C93
0x180074ca2  cmp     edx, 1
0x180074ca5  jz      loc_180074D5E
0x180074cab  mov     r8, rsi
0x180074cae  lea     rdx, [rsp+58h+arg_18]
0x180074cb3  mov     ecx, 9
0x180074cb8  call    BallocElementFromMasterTable
0x180074cbd  mov     edx, [r15+rbx]
0x180074cc1  mov     r9d, eax
0x180074cc4  mov     r10d, [rsp+58h+arg_18]
0x180074cc9  mov     ecx, r10d
0x180074ccc  add     rcx, rcx
0x180074ccf  cmp     edx, 7FFFFFFFh
0x180074cd5  cmovz   edx, r12d
0x180074cd9  mov     [rbp+rcx*8+0Ch], edx
0x180074cdd  mov     [r15+rbx], r10d
0x180074ce1  test    eax, eax
0x180074ce3  jz      loc_180074D71
0x180074ce9  mov     r15d, 0FFFFh
0x180074cef  mov     ecx, r14d
0x180074cf2  cmp     [rdi+rcx*8+2], r15w
0x180074cf8  jnz     short loc_180074D00
0x180074cfa  mov     [rdi+rcx*8+2], r15w
0x180074d00  movzx   eax, word ptr [rdi+rcx*8]
0x180074d04  mov     edx, r10d
0x180074d07  add     rdx, rdx
0x180074d0a  mov     [rbp+rdx*8+0], eax
0x180074d0e  movzx   eax, word ptr [rdi+rcx*8+2]
0x180074d13  mov     [rbp+rdx*8+4], eax
0x180074d17  mov     r14d, [rdi+rcx*8+4]
0x180074d1c  cmp     r14d, r12d
0x180074d1f  jz      short loc_180074D49
0x180074d21  lea     rbx, ds:0[rdx*8]
0x180074d29  mov     r8, rsi
0x180074d2c  lea     rdx, [rbp+8]
0x180074d30  mov     ecx, 9
0x180074d35  add     rdx, rbx
0x180074d38  call    BallocElementFromMasterTable
0x180074d3d  mov     r10d, [rbx+rbp+8]
0x180074d42  mov     r9d, eax
0x180074d45  test    eax, eax
0x180074d47  jnz     short loc_180074CEF
0x180074d49  test    r9d, r9d
0x180074d4c  jz      short loc_180074D71
0x180074d4e  mov     eax, r10d
0x180074d51  add     rax, rax
0x180074d54  mov     [rbp+rax*8+8], r12d
0x180074d59  mov     eax, r9d
0x180074d5c  jmp     short loc_180074D73
0x180074d5e  lea     rdx, aMustHaveAtLeas; "Must have at least 2 objects to define "...
0x180074d65  lea     rcx, aBparseinvalidi; "BparseInvalidInstallableCombination1"
0x180074d6c  call    WriteDbgTraceErrorGpd
0x180074d71  xor     eax, eax
0x180074d73  mov     rbx, [rsp+58h+arg_0]
0x180074d78  mov     rbp, [rsp+58h+arg_8]
0x180074d7d  add     rsp, 30h
0x180074d81  pop     r15
0x180074d83  pop     r14
0x180074d85  pop     r12
0x180074d87  pop     rdi
0x180074d88  pop     rsi
0x180074d89  retn
```
