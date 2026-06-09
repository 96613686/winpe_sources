# I_BCryptPrimitiveHMACParam

- ea: `0x18007e870`
- end: `0x18007eb77`
- name: `I_BCryptPrimitiveHMACParam`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007e5c8`

## callees

- `0x18000ecb0`
- `0x180016af4`
- `0x180063170`
- `0x180063180`
- `0x18006319c`
- `0x18006cfdc`
- `0x18007e870`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x18007e972`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_BCryptPrimitiveHMACParam(
        void *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  unsigned int v7; // r12d
  bool v9; // cc
  unsigned __int64 v10; // rbx
  void **p_Src; // rsi
  __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  _DWORD *v15; // rax
  void **v16; // rdi
  __int64 v17; // r9
  const char *v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  _DWORD *v25; // rax
  size_t v26; // r8
  unsigned int v27; // edx
  __int64 v28; // rcx
  _BYTE v30[32]; // [rsp+0h] [rbp-40h] BYREF
  int v31; // [rsp+40h] [rbp+0h] BYREF
  void *Src; // [rsp+48h] [rbp+8h] BYREF
  __int64 v33; // [rsp+50h] [rbp+10h]
  char v34; // [rsp+60h] [rbp+20h] BYREF
  char v35; // [rsp+E0h] [rbp+A0h] BYREF

  v7 = 0;
  v31 = a4;
  v33 = a3;
  v9 = *(_DWORD *)(a5 + 16) <= 0x80u;
  Src = a1;
  if ( v9 )
  {
    p_Src = (void **)&v34;
    v16 = (void **)&v35;
  }
  else
  {
    v10 = *(unsigned int *)(a5 + 16);
    p_Src = 0;
    if ( v10 > g_ulMaxStackAllocSize || v10 + g_ulAdditionalProbeSize + 8 < v10 || !(unsigned int)VerifyStackAvailable() )
      goto LABEL_50;
    v12 = v10 + 23;
    if ( v10 + 23 <= v10 + 8 )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
    v14 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
    p_Src = (void **)&v31;
    if ( v30 == (_BYTE *)-64LL || (v31 = 1801679955, (p_Src = &Src) == 0) )
    {
LABEL_50:
      if ( v10 + 8 >= v10 )
      {
        v15 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_Src = (void **)v15;
        if ( v15 )
        {
          *v15 = 1885431112;
          p_Src = (void **)(v15 + 2);
        }
      }
    }
    v16 = 0;
    if ( !p_Src )
    {
      v17 = 393;
LABEL_14:
      v18 = "STATUS_NO_MEMORY";
      v19 = 3221225495LL;
LABEL_15:
      DebugTraceError(v19, v18, "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", v17);
      goto LABEL_40;
    }
    v20 = *(unsigned int *)(a5 + 16);
    if ( !*(_DWORD *)(a5 + 16)
      || v20 > g_ulMaxStackAllocSize
      || v20 + g_ulAdditionalProbeSize + 8 < v20
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_51;
    }
    v21 = v20 + 23;
    if ( v20 + 23 <= v20 + 8 )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
    v23 = alloca(v22);
    v24 = alloca(v22);
    v16 = (void **)&v31;
    if ( v30 == (_BYTE *)-64LL || (v31 = 1801679955, (v16 = &Src) == 0) )
    {
LABEL_51:
      if ( v20 + 8 >= v20 )
      {
        v25 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v16 = (void **)v25;
        if ( v25 )
        {
          *v25 = 1885431112;
          v16 = (void **)(v25 + 2);
        }
      }
    }
    if ( !v16 )
    {
      v17 = 400;
      goto LABEL_14;
    }
  }
  v26 = *(unsigned int *)(a5 + 16);
  if ( a2 > (unsigned int)v26 )
    a2 = *(_DWORD *)(a5 + 16);
  memset_0(p_Src, 0, v26);
  memcpy_0(p_Src, Src, a2);
  memset_0(v16, 0, *(unsigned int *)(a5 + 16));
  memcpy_0(v16, Src, a2);
  v27 = *(_DWORD *)(a5 + 16);
  v28 = 0;
  if ( (v27 & 0xFFFFFFFC) != 0 )
  {
    do
    {
      *((_DWORD *)p_Src + v28) ^= 0x36363636u;
      *((_DWORD *)v16 + v28) ^= 0x5C5C5C5Cu;
      v28 = (unsigned int)(v28 + 1);
      v27 = *(_DWORD *)(a5 + 16);
    }
    while ( (unsigned int)v28 < v27 >> 2 );
  }
  if ( !(unsigned int)I_BCryptPrimitiveHash((__int64)p_Src, v27, v33, v31, a5, a6, a7) )
  {
    v17 = 445;
LABEL_36:
    v18 = "NTE_FAIL";
    v19 = 2148073504LL;
    goto LABEL_15;
  }
  if ( !(unsigned int)I_BCryptPrimitiveHash((__int64)v16, *(_DWORD *)(a5 + 16), a6, a7, a5, a6, a7) )
  {
    v17 = 459;
    goto LABEL_36;
  }
  v7 = 1;
LABEL_40:
  if ( *(_DWORD *)(a5 + 16) > 0x80u )
  {
    if ( p_Src && *((_DWORD *)p_Src - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    if ( v16 && *((_DWORD *)v16 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v7;
}

```

## disassembly

```asm
0x18007e870  push    rbp
0x18007e872  push    rbx
0x18007e873  push    rsi
0x18007e874  push    rdi
0x18007e875  push    r12
0x18007e877  push    r13
0x18007e879  push    r14
0x18007e87b  push    r15
0x18007e87d  sub     rsp, 178h
0x18007e884  lea     rbp, [rsp+40h]
0x18007e889  mov     rax, cs:__security_cookie
0x18007e890  xor     rax, rbp
0x18007e893  mov     [rbp+170h+var_50], rax
0x18007e89a  mov     r14, [rbp+170h+arg_20]
0x18007e8a1  xor     r12d, r12d
0x18007e8a4  mov     r15, [rbp+170h+arg_28]
0x18007e8ab  mov     r13d, edx
0x18007e8ae  mov     [rbp+170h+var_170], r9d
0x18007e8b2  mov     [rbp+170h+var_160], r8
0x18007e8b6  cmp     dword ptr [r14+10h], 80h
0x18007e8be  mov     [rbp+170h+Src], rcx
0x18007e8c2  jbe     loc_18007EA24
0x18007e8c8  mov     ebx, [r14+10h]
0x18007e8cc  xor     esi, esi
0x18007e8ce  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007e8d5  mov     rdi, 0FFFFFFFFFFFFFF0h
0x18007e8df  ja      short loc_18007E932
0x18007e8e1  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007e8e8  add     rcx, 8
0x18007e8ec  add     rcx, rbx
0x18007e8ef  cmp     rcx, rbx
0x18007e8f2  jb      short loc_18007E932
0x18007e8f4  call    VerifyStackAvailable
0x18007e8f9  test    eax, eax
0x18007e8fb  jz      short loc_18007E932
0x18007e8fd  lea     rax, [rbx+8]
0x18007e901  lea     rcx, [rax+0Fh]
0x18007e905  cmp     rcx, rax
0x18007e908  ja      short loc_18007E90D
0x18007e90a  mov     rcx, rdi
0x18007e90d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007e911  mov     rax, rcx
0x18007e914  call    __chkstk_0
0x18007e919  sub     rsp, rcx
0x18007e91c  lea     rsi, [rsp+1B0h+var_170]
0x18007e921  test    rsi, rsi
0x18007e924  jz      short loc_18007E932
0x18007e926  mov     dword ptr [rsi], 6B637453h
0x18007e92c  add     rsi, 8
0x18007e930  jnz     short loc_18007E959
0x18007e932  lea     rcx, [rbx+8]
0x18007e936  cmp     rcx, rbx
0x18007e939  jb      short loc_18007E959
0x18007e93b  mov     rax, cs:g_pfnAllocate
0x18007e942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e947  mov     rsi, rax
0x18007e94a  test    rax, rax
0x18007e94d  jz      short loc_18007E959
0x18007e94f  mov     dword ptr [rax], 70616548h
0x18007e955  add     rsi, 8
0x18007e959  xor     edi, edi
0x18007e95b  test    rsi, rsi
0x18007e95e  jnz     short loc_18007E983
0x18007e960  mov     r9d, 189h
0x18007e966  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x18007e96d  mov     ecx, 0C0000017h
0x18007e972  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e979  call    DebugTraceError
0x18007e97e  jmp     loc_18007EB0C
0x18007e983  mov     ebx, [r14+10h]
0x18007e987  test    rbx, rbx
0x18007e98a  jz      short loc_18007E9ED
0x18007e98c  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007e993  ja      short loc_18007E9ED
0x18007e995  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007e99c  add     rcx, 8
0x18007e9a0  add     rcx, rbx
0x18007e9a3  cmp     rcx, rbx
0x18007e9a6  jb      short loc_18007E9ED
0x18007e9a8  call    VerifyStackAvailable
0x18007e9ad  test    eax, eax
0x18007e9af  jz      short loc_18007E9ED
0x18007e9b1  lea     rax, [rbx+8]
0x18007e9b5  lea     rcx, [rax+0Fh]
0x18007e9b9  cmp     rcx, rax
0x18007e9bc  ja      short loc_18007E9C8
0x18007e9be  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007e9c8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007e9cc  mov     rax, rcx
0x18007e9cf  call    __chkstk_0
0x18007e9d4  sub     rsp, rcx
0x18007e9d7  lea     rdi, [rsp+1B0h+var_170]
0x18007e9dc  test    rdi, rdi
0x18007e9df  jz      short loc_18007E9ED
0x18007e9e1  mov     dword ptr [rdi], 6B637453h
0x18007e9e7  add     rdi, 8
0x18007e9eb  jnz     short loc_18007EA14
0x18007e9ed  lea     rcx, [rbx+8]
0x18007e9f1  cmp     rcx, rbx
0x18007e9f4  jb      short loc_18007EA14
0x18007e9f6  mov     rax, cs:g_pfnAllocate
0x18007e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea02  mov     rdi, rax
0x18007ea05  test    rax, rax
0x18007ea08  jz      short loc_18007EA14
0x18007ea0a  mov     dword ptr [rax], 70616548h
0x18007ea10  add     rdi, 8
0x18007ea14  test    rdi, rdi
0x18007ea17  jnz     short loc_18007EA2F
0x18007ea19  mov     r9d, 190h
0x18007ea1f  jmp     loc_18007E966
0x18007ea24  lea     rsi, [rbp+170h+var_150]
0x18007ea28  lea     rdi, [rbp+170h+var_D0]
0x18007ea2f  mov     r8d, [r14+10h]; Size
0x18007ea33  mov     rcx, rsi; void *
0x18007ea36  cmp     r13d, r8d
0x18007ea39  cmova   r13d, r8d
0x18007ea3d  xor     edx, edx; Val
0x18007ea3f  call    memset_0
0x18007ea44  mov     rdx, [rbp+170h+Src]; Src
0x18007ea48  mov     rcx, rsi; void *
0x18007ea4b  mov     r8d, r13d; Size
0x18007ea4e  call    memcpy_0
0x18007ea53  mov     r8d, [r14+10h]; Size
0x18007ea57  xor     edx, edx; Val
0x18007ea59  mov     rcx, rdi; void *
0x18007ea5c  call    memset_0
0x18007ea61  mov     rdx, [rbp+170h+Src]; Src
0x18007ea65  mov     rcx, rdi; void *
0x18007ea68  mov     r8d, r13d; Size
0x18007ea6b  call    memcpy_0
0x18007ea70  mov     edx, [r14+10h]
0x18007ea74  xor     ecx, ecx
0x18007ea76  test    edx, 0FFFFFFFCh
0x18007ea7c  jbe     short loc_18007EA9B
0x18007ea7e  xor     dword ptr [rsi+rcx*4], 36363636h
0x18007ea85  xor     dword ptr [rdi+rcx*4], 5C5C5C5Ch
0x18007ea8c  inc     ecx
0x18007ea8e  mov     edx, [r14+10h]
0x18007ea92  mov     eax, edx
0x18007ea94  shr     eax, 2
0x18007ea97  cmp     ecx, eax
0x18007ea99  jb      short loc_18007EA7E
0x18007ea9b  mov     ebx, [rbp+170h+arg_30]
0x18007eaa1  mov     rcx, rsi
0x18007eaa4  mov     r9d, [rbp+170h+var_170]
0x18007eaa8  mov     r8, [rbp+170h+var_160]
0x18007eaac  mov     [rsp+1B0h+var_180], ebx
0x18007eab0  mov     [rsp+1B0h+var_188], r15
0x18007eab5  mov     [rsp+1B0h+var_190], r14
0x18007eaba  call    I_BCryptPrimitiveHash
0x18007eabf  test    eax, eax
0x18007eac1  jnz     short loc_18007EADA
0x18007eac3  mov     r9d, 1BDh
0x18007eac9  lea     rdx, aNteFail; "NTE_FAIL"
0x18007ead0  mov     ecx, 80090020h
0x18007ead5  jmp     loc_18007E972
0x18007eada  mov     edx, [r14+10h]
0x18007eade  mov     r9d, ebx
0x18007eae1  mov     [rsp+1B0h+var_180], ebx
0x18007eae5  mov     r8, r15
0x18007eae8  mov     [rsp+1B0h+var_188], r15
0x18007eaed  mov     rcx, rdi
0x18007eaf0  mov     [rsp+1B0h+var_190], r14
0x18007eaf5  call    I_BCryptPrimitiveHash
0x18007eafa  test    eax, eax
0x18007eafc  jnz     short loc_18007EB06
0x18007eafe  mov     r9d, 1CBh
0x18007eb04  jmp     short loc_18007EAC9
0x18007eb06  mov     r12d, 1
0x18007eb0c  cmp     dword ptr [r14+10h], 80h
0x18007eb14  jbe     short loc_18007EB50
0x18007eb16  test    rsi, rsi
0x18007eb19  jz      short loc_18007EB33
0x18007eb1b  lea     rcx, [rsi-8]
0x18007eb1f  cmp     dword ptr [rcx], 70616548h
0x18007eb25  jnz     short loc_18007EB33
0x18007eb27  mov     rax, cs:g_pfnFree
0x18007eb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb33  test    rdi, rdi
0x18007eb36  jz      short loc_18007EB50
0x18007eb38  lea     rcx, [rdi-8]
0x18007eb3c  cmp     dword ptr [rcx], 70616548h
0x18007eb42  jnz     short loc_18007EB50
0x18007eb44  mov     rax, cs:g_pfnFree
0x18007eb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb50  mov     eax, r12d
0x18007eb53  mov     rcx, [rbp+170h+var_50]
0x18007eb5a  xor     rcx, rbp; StackCookie
0x18007eb5d  call    __security_check_cookie
0x18007eb62  lea     rsp, [rbp+138h]
0x18007eb69  pop     r15
0x18007eb6b  pop     r14
0x18007eb6d  pop     r13
0x18007eb6f  pop     r12
0x18007eb71  pop     rdi
0x18007eb72  pop     rsi
0x18007eb73  pop     rbx
0x18007eb74  pop     rbp
0x18007eb75  retn
```
