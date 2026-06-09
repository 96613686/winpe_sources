# CheckOAEPPadding

- ea: `0x180016efc`
- end: `0x1800171ae`
- name: `CheckOAEPPadding`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180014d6c`

## callees

- `0x180004200`
- `0x180005060`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180009430`
- `0x18000cc10`
- `0x180012cc4`
- `0x180016efc`
- `0x18001b79d`

## string_xrefs

- `0x180017164`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall CheckOAEPPadding(
        void *a1,
        unsigned int a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        _BYTE *a6,
        unsigned int a7,
        void *a8,
        unsigned int a9,
        unsigned int *a10)
{
  __int64 v11; // rdi
  ULONG v13; // esi
  UCHAR *v14; // rax
  UCHAR *v15; // rbp
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // rcx
  UCHAR *v19; // r9
  unsigned int v20; // eax
  __int64 v21; // rdx
  PUCHAR v22; // r10
  __int64 v23; // r9
  UCHAR *v24; // r14
  UCHAR *i; // r8
  PUCHAR v26; // r15
  __int64 j; // rdx
  unsigned int v28; // esi
  __int64 dwFlags; // [rsp+30h] [rbp-58h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbOutput; // [rsp+48h] [rbp-40h]

  v11 = a2;
  phHash = 0;
  if ( a7 < a2 + 1 || *a6 )
  {
    v15 = 0;
LABEL_33:
    v16 = -1073741811;
    v18 = 3221225485LL;
    goto LABEL_34;
  }
  v13 = a7 - a2 - 1;
  v14 = (UCHAR *)SafeAllocaAllocateFromHeap(a2 + 5 + a3 + 2 * (a2 + 5) + 2 * v13);
  v15 = v14;
  if ( !v14 )
  {
    v16 = -1073741801;
    goto LABEL_35;
  }
  v17 = MaskGeneration(a1, v11, a3, &a6[v11 + 1], v13, v14, v11);
  v16 = v17;
  if ( v17 < 0 )
    goto LABEL_6;
  v19 = &v15[v11];
  v20 = 0;
  for ( pbOutput = &v15[v11 + v11]; v20 < (unsigned int)v11; v19[v21] = v15[v21] ^ a6[v20] )
    v21 = v20++;
  LODWORD(dwFlags) = v13;
  v17 = MaskGeneration(a1, v11, a3, v19, v11, &v15[v11 + v11], dwFlags);
  v16 = v17;
  if ( v17 < 0 )
    goto LABEL_6;
  v22 = pbOutput;
  v23 = 0;
  v24 = &pbOutput[v13];
  pbOutput = &v24[v13];
  for ( i = (UCHAR *)((unsigned __int64)&pbOutput[v11 + 15] & 0xFFFFFFFFFFFFFFF0uLL);
        (unsigned int)v23 < v13;
        v23 = (unsigned int)(v23 + 1) )
  {
    v24[v23] = v22[v23] ^ a6[(unsigned int)(v11 + 1 + v23)];
  }
  if ( (v17 = BCryptCreateHash(a1, &phHash, i, a3, 0, 0, 0), v16 = v17, v17 < 0)
    || cbInput && (v17 = BCryptHashData(phHash, a4, cbInput, 0), v16 = v17, v17 < 0)
    || (v26 = pbOutput, v17 = BCryptFinishHash(phHash, pbOutput, v11, 0), v16 = v17, v17 < 0) )
  {
LABEL_6:
    v18 = (unsigned int)v17;
LABEL_34:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    goto LABEL_35;
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v11; j = (unsigned int)(j + 1) )
  {
    if ( v26[j] != v24[j] )
      goto LABEL_33;
  }
  while ( (unsigned int)v11 < v13 )
  {
    if ( v24[v11] == 1 )
    {
      LODWORD(v11) = v11 + 1;
      break;
    }
    if ( v24[v11] )
      goto LABEL_33;
    v11 = (unsigned int)(v11 + 1);
  }
  v28 = v13 - v11;
  *a10 = v28;
  if ( !a8 )
    goto LABEL_28;
  if ( a9 >= v28 )
  {
    memcpy_0(a8, &v24[(unsigned int)v11], v28);
LABEL_28:
    v16 = 0;
    goto LABEL_35;
  }
  v16 = -1073741789;
LABEL_35:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v15 )
    MSCryptFree(v15);
  return v16;
}

```

## disassembly

```asm
0x180016efc  mov     rax, rsp
0x180016eff  mov     [rax+10h], rbx
0x180016f03  mov     [rax+20h], r9
0x180016f07  mov     [rax+8], rcx
0x180016f0b  push    rbp
0x180016f0c  push    rsi
0x180016f0d  push    rdi
0x180016f0e  push    r12
0x180016f10  push    r13
0x180016f12  push    r14
0x180016f14  push    r15
0x180016f16  sub     rsp, 50h
0x180016f1a  mov     esi, [rsp+88h+arg_30]
0x180016f21  mov     r13d, r8d
0x180016f24  mov     edi, edx
0x180016f26  mov     r14, rcx
0x180016f29  mov     qword ptr [rax-48h], 0
0x180016f31  lea     eax, [rdi+1]
0x180016f34  cmp     esi, eax
0x180016f36  jb      loc_180017152
0x180016f3c  mov     r15, [rsp+88h+arg_28]
0x180016f44  cmp     byte ptr [r15], 0
0x180016f48  jnz     loc_180017152
0x180016f4e  lea     ecx, [rdi+5]
0x180016f51  sub     esi, edi
0x180016f53  lea     eax, [rcx+r8]
0x180016f57  dec     esi
0x180016f59  lea     eax, [rax+rcx*2]
0x180016f5c  lea     ecx, [rax+rsi*2]
0x180016f5f  call    SafeAllocaAllocateFromHeap
0x180016f64  mov     rbp, rax
0x180016f67  test    rax, rax
0x180016f6a  jnz     short loc_180016F76
0x180016f6c  mov     ebx, 0C0000017h
0x180016f71  jmp     loc_180017177
0x180016f76  mov     [rsp+88h+dwFlags], edi
0x180016f7a  lea     r9, [r15+1]
0x180016f7e  add     r9, rdi
0x180016f81  mov     qword ptr [rsp+88h+cbSecret], rbp
0x180016f86  mov     r8d, r13d
0x180016f89  mov     dword ptr [rsp+88h+pbSecret], esi
0x180016f8d  mov     edx, edi
0x180016f8f  mov     rcx, r14
0x180016f92  call    MaskGeneration
0x180016f97  mov     ebx, eax
0x180016f99  test    eax, eax
0x180016f9b  jns     short loc_180016FAA
0x180016f9d  mov     r9d, 2F8h
0x180016fa3  mov     ecx, eax
0x180016fa5  jmp     loc_180017164
0x180016faa  lea     r9, [rdi+rbp]
0x180016fae  xor     eax, eax
0x180016fb0  lea     r10, [r9+rdi]
0x180016fb4  mov     [rsp+88h+pbOutput], r10
0x180016fb9  test    edi, edi
0x180016fbb  jz      short loc_180016FD6
0x180016fbd  mov     edx, eax
0x180016fbf  lea     r8d, [rax+1]
0x180016fc3  mov     cl, [r8+r15]
0x180016fc7  mov     eax, r8d
0x180016fca  xor     cl, [rdx+rbp]
0x180016fcd  mov     [rdx+r9], cl
0x180016fd1  cmp     r8d, edi
0x180016fd4  jb      short loc_180016FBD
0x180016fd6  mov     [rsp+88h+dwFlags], esi
0x180016fda  mov     r8d, r13d
0x180016fdd  mov     qword ptr [rsp+88h+cbSecret], r10
0x180016fe2  mov     edx, edi
0x180016fe4  mov     rcx, r14
0x180016fe7  mov     dword ptr [rsp+88h+pbSecret], edi
0x180016feb  call    MaskGeneration
0x180016ff0  mov     ebx, eax
0x180016ff2  test    eax, eax
0x180016ff4  jns     short loc_180016FFE
0x180016ff6  mov     r9d, 30Ch
0x180016ffc  jmp     short loc_180016FA3
0x180016ffe  mov     r10, [rsp+88h+pbOutput]
0x180017003  lea     r8, [rdi+0Fh]
0x180017007  mov     eax, esi
0x180017009  xor     r9d, r9d
0x18001700c  lea     r14, [rsi+r10]
0x180017010  add     rax, r14
0x180017013  add     r8, rax
0x180017016  mov     [rsp+88h+pbOutput], rax
0x18001701b  and     r8, 0FFFFFFFFFFFFFFF0h; pbHashObject
0x18001701f  test    esi, esi
0x180017021  jz      short loc_18001703F
0x180017023  lea     r11d, [rdi+1]
0x180017027  lea     eax, [r11+r9]
0x18001702b  mov     al, [rax+r15]
0x18001702f  xor     al, [r9+r10]
0x180017033  mov     [r9+r14], al
0x180017037  inc     r9d
0x18001703a  cmp     r9d, esi
0x18001703d  jb      short loc_180017027
0x18001703f  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x180017047  lea     rdx, [rsp+88h+phHash]; phHash
0x18001704c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180017054  mov     r9d, r13d; cbHashObject
0x180017057  mov     [rsp+88h+cbSecret], 0; cbSecret
0x18001705f  mov     [rsp+88h+pbSecret], 0; pbSecret
0x180017068  call    BCryptCreateHash
0x18001706d  mov     ebx, eax
0x18001706f  test    eax, eax
0x180017071  jns     short loc_18001707E
0x180017073  mov     r9d, 320h
0x180017079  jmp     loc_180016FA3
0x18001707e  mov     r8d, [rsp+88h+cbInput]; cbInput
0x180017086  test    r8d, r8d
0x180017089  jz      short loc_1800170B1
0x18001708b  mov     rdx, [rsp+88h+pbInput]; pbInput
0x180017093  xor     r9d, r9d; dwFlags
0x180017096  mov     rcx, [rsp+88h+phHash]; hHash
0x18001709b  call    BCryptHashData
0x1800170a0  mov     ebx, eax
0x1800170a2  test    eax, eax
0x1800170a4  jns     short loc_1800170B1
0x1800170a6  mov     r9d, 32Dh
0x1800170ac  jmp     loc_180016FA3
0x1800170b1  mov     r15, [rsp+88h+pbOutput]
0x1800170b6  xor     r9d, r9d; dwFlags
0x1800170b9  mov     rcx, [rsp+88h+phHash]; hHash
0x1800170be  mov     rdx, r15; pbOutput
0x1800170c1  mov     r8d, edi; cbOutput
0x1800170c4  call    BCryptFinishHash
0x1800170c9  mov     ebx, eax
0x1800170cb  test    eax, eax
0x1800170cd  jns     short loc_1800170DA
0x1800170cf  mov     r9d, 338h
0x1800170d5  jmp     loc_180016FA3
0x1800170da  xor     edx, edx
0x1800170dc  cmp     edx, edi
0x1800170de  jnb     short loc_1800170F6
0x1800170e0  mov     al, [rdx+r14]
0x1800170e4  cmp     [rdx+r15], al
0x1800170e8  jnz     short loc_1800170EE
0x1800170ea  inc     edx
0x1800170ec  jmp     short loc_1800170DC
0x1800170ee  mov     r9d, 342h
0x1800170f4  jmp     short loc_18001715A
0x1800170f6  cmp     edi, esi
0x1800170f8  jnb     short loc_180017116
0x1800170fa  cmp     byte ptr [rdi+r14], 1
0x1800170ff  jz      short loc_180017114
0x180017101  cmp     byte ptr [rdi+r14], 0
0x180017106  jnz     short loc_18001710C
0x180017108  inc     edi
0x18001710a  jmp     short loc_1800170F6
0x18001710c  mov     r9d, 352h
0x180017112  jmp     short loc_18001715A
0x180017114  inc     edi
0x180017116  mov     rax, [rsp+88h+arg_48]
0x18001711e  sub     esi, edi
0x180017120  mov     rcx, [rsp+88h+arg_38]; void *
0x180017128  mov     [rax], esi
0x18001712a  test    rcx, rcx
0x18001712d  jnz     short loc_180017133
0x18001712f  xor     ebx, ebx
0x180017131  jmp     short loc_180017177
0x180017133  cmp     [rsp+88h+arg_40], esi
0x18001713a  jnb     short loc_180017143
0x18001713c  mov     ebx, 0C0000023h
0x180017141  jmp     short loc_180017177
0x180017143  mov     edx, edi
0x180017145  add     rdx, r14; Src
0x180017148  mov     r8d, esi; Size
0x18001714b  call    memcpy_0
0x180017150  jmp     short loc_18001712F
0x180017152  xor     ebp, ebp
0x180017154  mov     r9d, 2D8h
0x18001715a  mov     ebx, 0C000000Dh
0x18001715f  mov     ecx, 0C000000Dh
0x180017164  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001716b  lea     rdx, aStatus; "Status"
0x180017172  call    DebugTraceError
0x180017177  mov     rcx, [rsp+88h+phHash]; hHash
0x18001717c  test    rcx, rcx
0x18001717f  jz      short loc_180017186
0x180017181  call    BCryptDestroyHash
0x180017186  test    rbp, rbp
0x180017189  jz      short loc_180017193
0x18001718b  mov     rcx, rbp
0x18001718e  call    MSCryptFree
0x180017193  mov     eax, ebx
0x180017195  mov     rbx, [rsp+88h+arg_8]
0x18001719d  add     rsp, 50h
0x1800171a1  pop     r15
0x1800171a3  pop     r14
0x1800171a5  pop     r13
0x1800171a7  pop     r12
0x1800171a9  pop     rdi
0x1800171aa  pop     rsi
0x1800171ab  pop     rbp
0x1800171ac  retn
```
