# I_BCryptP_Hash

- ea: `0x18007e5c8`
- end: `0x18007e869`
- name: `I_BCryptP_Hash`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007ecd4`

## callees

- `0x18000ecb0`
- `0x180016af4`
- `0x180063170`
- `0x18006319c`
- `0x18006cfdc`
- `0x18007e5c8`
- `0x18007e870`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x18007e6b5`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`
- `0x18007e715`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_BCryptP_Hash(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        char *a6,
        unsigned int Size)
{
  unsigned int v7; // r13d
  size_t v8; // r12
  size_t v9; // rbx
  __int64 *v10; // rdi
  __int64 v11; // r14
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  __int64 *v16; // rax
  unsigned int v17; // ebx
  size_t v18; // rsi
  char *v19; // r14
  __int64 v20; // r9
  int v21; // eax
  void *v22; // r15
  char *v25; // rdx
  __int64 v27; // [rsp+0h] [rbp-40h] BYREF
  int v28; // [rsp+40h] [rbp+0h] BYREF
  __int64 v29[2]; // [rsp+48h] [rbp+8h] BYREF
  void *Src; // [rsp+58h] [rbp+18h]

  v7 = a2;
  v8 = a4;
  Src = a3;
  v29[0] = a1;
  v9 = *(unsigned int *)(a5 + 12);
  v10 = 0;
  v11 = a4 + (_DWORD)v9 * ((*(_DWORD *)(a5 + 16) < a2) + 2);
  if ( !(_DWORD)v11
    || (unsigned int)v11 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v11 + g_ulAdditionalProbeSize + 8 < (unsigned int)v11
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_37;
  }
  v12 = v11 + 23;
  if ( v11 + 23 <= (unsigned __int64)(v11 + 8) )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
  v14 = alloca(v13);
  v15 = alloca(v13);
  v10 = (__int64 *)&v28;
  if ( &v27 == (__int64 *)-64LL || (v28 = 1801679955, (v10 = v29) == 0) )
  {
LABEL_37:
    if ( v11 + 8 >= (unsigned __int64)(unsigned int)v11 )
    {
      v16 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
      v10 = v16;
      if ( v16 )
      {
        *(_DWORD *)v16 = 1885431112;
        v10 = v16 + 1;
      }
    }
  }
  if ( !v10 )
  {
    v17 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", 527);
    return v17;
  }
  v18 = v8;
  v19 = (char *)v10 + v9 + v8;
  if ( v7 <= *(_DWORD *)(a5 + 16) )
  {
    v21 = v29[0];
LABEL_20:
    v22 = Src;
    if ( (unsigned int)I_BCryptPrimitiveHMACParam(v21, v7, (_DWORD)Src, v8, a5, (__int64)v10, v9) )
    {
      memcpy_0((char *)v10 + v9, v22, v18);
      while ( 1 )
      {
        if ( !Size )
          goto LABEL_30;
        if ( !(unsigned int)I_BCryptPrimitiveHMACParam(
                              v29[0],
                              v7,
                              (_DWORD)v10,
                              (int)v9 + (int)v8,
                              a5,
                              (__int64)v10 + v9 + v8,
                              v9) )
          break;
        v25 = (char *)v10 + v9 + v8;
        if ( Size < (unsigned int)v9 )
        {
          memcpy_0(a6, v25, Size);
LABEL_30:
          v17 = 0;
          goto LABEL_31;
        }
        memcpy_0(a6, v25, v9);
        if ( !(unsigned int)I_BCryptPrimitiveHMACParam(v29[0], v7, (_DWORD)v10, v9, a5, (__int64)v10, v9) )
        {
          v20 = 615;
          goto LABEL_17;
        }
        a6 += v9;
        Size -= v9;
      }
      v20 = 592;
    }
    else
    {
      v20 = 577;
    }
    goto LABEL_17;
  }
  if ( (unsigned int)I_BCryptPrimitiveHash(v29[0], v7, 0, 0, a5, (__int64)&v19[v9], v9) )
  {
    v21 = v9 + (_DWORD)v19;
    v7 = v9;
    v29[0] = (__int64)&v19[v9];
    v18 = v8;
    goto LABEL_20;
  }
  v20 = 547;
LABEL_17:
  v17 = -1073741174;
  DebugTraceError(3221226122LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", v20);
LABEL_31:
  if ( *((_DWORD *)v10 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v17;
}

```

## disassembly

```asm
0x18007e5c8  push    rbp
0x18007e5ca  push    rbx
0x18007e5cb  push    rsi
0x18007e5cc  push    rdi
0x18007e5cd  push    r12
0x18007e5cf  push    r13
0x18007e5d1  push    r14
0x18007e5d3  push    r15
0x18007e5d5  sub     rsp, 78h
0x18007e5d9  lea     rbp, [rsp+40h]
0x18007e5de  mov     rax, cs:__security_cookie
0x18007e5e5  xor     rax, rbp
0x18007e5e8  mov     [rbp+70h+var_50], rax
0x18007e5ec  mov     r15, [rbp+70h+arg_20]
0x18007e5f3  mov     r13d, edx
0x18007e5f6  mov     r12d, r9d
0x18007e5f9  mov     [rbp+70h+Src], r8
0x18007e5fd  mov     [rbp+70h+var_68], rcx
0x18007e601  cmp     [r15+10h], edx
0x18007e605  mov     ebx, [r15+0Ch]
0x18007e609  sbb     eax, eax
0x18007e60b  xor     edi, edi
0x18007e60d  neg     eax
0x18007e60f  lea     r14d, [rax+2]
0x18007e613  imul    r14d, ebx
0x18007e617  add     r14d, r9d
0x18007e61a  jz      short loc_18007E680
0x18007e61c  mov     esi, r14d
0x18007e61f  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18007e626  ja      short loc_18007E680
0x18007e628  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007e62f  add     rcx, 8
0x18007e633  add     rcx, rsi
0x18007e636  cmp     rcx, rsi
0x18007e639  jb      short loc_18007E680
0x18007e63b  call    VerifyStackAvailable
0x18007e640  test    eax, eax
0x18007e642  jz      short loc_18007E680
0x18007e644  lea     rax, [r14+8]
0x18007e648  lea     rcx, [rax+0Fh]
0x18007e64c  cmp     rcx, rax
0x18007e64f  ja      short loc_18007E65B
0x18007e651  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007e65b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007e65f  mov     rax, rcx
0x18007e662  call    __chkstk_0
0x18007e667  sub     rsp, rcx
0x18007e66a  lea     rdi, [rsp+0B0h+var_70]
0x18007e66f  test    rdi, rdi
0x18007e672  jz      short loc_18007E680
0x18007e674  mov     dword ptr [rdi], 6B637453h
0x18007e67a  add     rdi, 8
0x18007e67e  jnz     short loc_18007E6AA
0x18007e680  mov     eax, r14d
0x18007e683  lea     rcx, [r14+8]
0x18007e687  cmp     rcx, rax
0x18007e68a  jb      short loc_18007E6AA
0x18007e68c  mov     rax, cs:g_pfnAllocate
0x18007e693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e698  mov     rdi, rax
0x18007e69b  test    rax, rax
0x18007e69e  jz      short loc_18007E6AA
0x18007e6a0  mov     dword ptr [rax], 70616548h
0x18007e6a6  add     rdi, 8
0x18007e6aa  test    rdi, rdi
0x18007e6ad  jnz     short loc_18007E6D7
0x18007e6af  mov     r9d, 20Fh
0x18007e6b5  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e6bc  lea     rdx, aStatus; "Status"
0x18007e6c3  mov     ecx, 0C0000017h
0x18007e6c8  mov     ebx, 0C0000017h
0x18007e6cd  call    DebugTraceError
0x18007e6d2  jmp     loc_18007E83E
0x18007e6d7  lea     r14, [rbx+r12]
0x18007e6db  mov     rsi, r12
0x18007e6de  add     r14, rdi
0x18007e6e1  cmp     r13d, [r15+10h]
0x18007e6e5  jbe     short loc_18007E746
0x18007e6e7  mov     rcx, [rbp+70h+var_68]
0x18007e6eb  lea     rsi, [rbx+r14]
0x18007e6ef  mov     [rsp+0B0h+var_80], ebx
0x18007e6f3  xor     r9d, r9d
0x18007e6f6  mov     [rsp+0B0h+var_88], rsi
0x18007e6fb  xor     r8d, r8d
0x18007e6fe  mov     edx, r13d
0x18007e701  mov     [rsp+0B0h+var_90], r15
0x18007e706  call    I_BCryptPrimitiveHash
0x18007e70b  test    eax, eax
0x18007e70d  jnz     short loc_18007E737
0x18007e70f  mov     r9d, 223h
0x18007e715  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e71c  mov     ecx, 0C000028Ah
0x18007e721  lea     rdx, aStatus; "Status"
0x18007e728  mov     ebx, 0C000028Ah
0x18007e72d  call    DebugTraceError
0x18007e732  jmp     loc_18007E826
0x18007e737  mov     rax, rsi
0x18007e73a  mov     r13d, ebx
0x18007e73d  mov     [rbp+70h+var_68], rax
0x18007e741  mov     rsi, r12
0x18007e744  jmp     short loc_18007E74A
0x18007e746  mov     rax, [rbp+70h+var_68]
0x18007e74a  mov     [rsp+0B0h+var_80], ebx
0x18007e74e  mov     r9d, r12d
0x18007e751  mov     [rsp+0B0h+var_88], rdi
0x18007e756  mov     edx, r13d
0x18007e759  mov     [rsp+0B0h+var_90], r15
0x18007e75e  mov     rcx, rax
0x18007e761  mov     r15, [rbp+70h+Src]
0x18007e765  mov     r8, r15
0x18007e768  call    I_BCryptPrimitiveHMACParam
0x18007e76d  test    eax, eax
0x18007e76f  jnz     short loc_18007E779
0x18007e771  mov     r9d, 241h
0x18007e777  jmp     short loc_18007E715
0x18007e779  lea     rcx, [rbx+rdi]; void *
0x18007e77d  mov     r8, rsi; Size
0x18007e780  mov     rdx, r15; Src
0x18007e783  call    memcpy_0
0x18007e788  mov     esi, dword ptr [rbp+70h+Size]
0x18007e78e  mov     r15, [rbp+70h+arg_28]
0x18007e795  test    esi, esi
0x18007e797  jz      loc_18007E824
0x18007e79d  mov     rax, [rbp+70h+arg_20]
0x18007e7a4  lea     r9d, [rbx+r12]
0x18007e7a8  mov     rcx, [rbp+70h+var_68]
0x18007e7ac  mov     r8, rdi
0x18007e7af  mov     [rsp+0B0h+var_80], ebx
0x18007e7b3  mov     edx, r13d
0x18007e7b6  mov     [rsp+0B0h+var_88], r14
0x18007e7bb  mov     [rsp+0B0h+var_90], rax
0x18007e7c0  call    I_BCryptPrimitiveHMACParam
0x18007e7c5  test    eax, eax
0x18007e7c7  jz      loc_18007E85E
0x18007e7cd  mov     rdx, r14; Src
0x18007e7d0  mov     rcx, r15; void *
0x18007e7d3  cmp     esi, ebx
0x18007e7d5  jb      short loc_18007E81C
0x18007e7d7  mov     r8, rbx; Size
0x18007e7da  call    memcpy_0
0x18007e7df  mov     rax, [rbp+70h+arg_20]
0x18007e7e6  mov     r9d, ebx
0x18007e7e9  mov     rcx, [rbp+70h+var_68]
0x18007e7ed  mov     r8, rdi
0x18007e7f0  mov     [rsp+0B0h+var_80], ebx
0x18007e7f4  mov     edx, r13d
0x18007e7f7  mov     [rsp+0B0h+var_88], rdi
0x18007e7fc  mov     [rsp+0B0h+var_90], rax
0x18007e801  call    I_BCryptPrimitiveHMACParam
0x18007e806  test    eax, eax
0x18007e808  jz      short loc_18007E811
0x18007e80a  add     r15, rbx
0x18007e80d  sub     esi, ebx
0x18007e80f  jmp     short loc_18007E795
0x18007e811  mov     r9d, 267h
0x18007e817  jmp     loc_18007E715
0x18007e81c  mov     r8d, esi; Size
0x18007e81f  call    memcpy_0
0x18007e824  xor     ebx, ebx
0x18007e826  lea     rcx, [rdi-8]
0x18007e82a  cmp     dword ptr [rcx], 70616548h
0x18007e830  jnz     short loc_18007E83E
0x18007e832  mov     rax, cs:g_pfnFree
0x18007e839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e83e  mov     eax, ebx
0x18007e840  mov     rcx, [rbp+70h+var_50]
0x18007e844  xor     rcx, rbp; StackCookie
0x18007e847  call    __security_check_cookie
0x18007e84c  lea     rsp, [rbp+38h]
0x18007e850  pop     r15
0x18007e852  pop     r14
0x18007e854  pop     r13
0x18007e856  pop     r12
0x18007e858  pop     rdi
0x18007e859  pop     rsi
0x18007e85a  pop     rbx
0x18007e85b  pop     rbp
0x18007e85c  retn
0x18007e85e  mov     r9d, 250h
0x18007e864  jmp     loc_18007E715
```
