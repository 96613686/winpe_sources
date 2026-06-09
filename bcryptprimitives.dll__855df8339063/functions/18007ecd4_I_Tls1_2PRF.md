# I_Tls1_2PRF

- ea: `0x18007ecd4`
- end: `0x18007eef9`
- name: `I_Tls1_2PRF`
- size: `549`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, void *, size_t, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18007f21c`

## callees

- `0x18000ecb0`
- `0x180054188`
- `0x180063170`
- `0x18006319c`
- `0x18006cfdc`
- `0x18007e5c8`
- `0x18007eb80`
- `0x18007ebb4`
- `0x18007ecd4`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x18007ed77`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`
- `0x18007eea3`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_Tls1_2PRF(
        __int64 a1,
        char *a2,
        __int64 a3,
        unsigned int a4,
        void *Src,
        size_t Size,
        void *a7,
        size_t a8,
        __int64 a9,
        int a10)
{
  char *v10; // rdi
  __int64 i; // rcx
  unsigned __int16 *v15; // rdx
  int v16; // r8d
  int v17; // eax
  int PRFCachedHashEntry; // eax
  unsigned int v19; // ebx
  __int64 v20; // rsi
  __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  char *v24; // rax
  int v25; // eax
  __int64 v27; // [rsp+0h] [rbp-40h] BYREF
  __int128 v28; // [rsp+40h] [rbp+0h] BYREF
  __int64 v29; // [rsp+50h] [rbp+10h]

  v10 = 0;
  v29 = 0;
  v28 = 0;
  if ( a2 && *(_WORD *)a2 )
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      v15 = (unsigned __int16 *)a2;
      do
      {
        v16 = *(unsigned __int16 *)((char *)v15 + (char *)off_180087F00[(unsigned int)i] - a2);
        v17 = *v15 - v16;
        if ( v17 )
          break;
        ++v15;
      }
      while ( v16 );
      if ( !v17 )
        goto LABEL_12;
    }
    PRFCachedHashEntry = I_LoadPRFHashProvider(a2, &v28);
  }
  else
  {
    i = 0;
LABEL_12:
    PRFCachedHashEntry = I_GetPRFCachedHashEntry(i, &v28);
  }
  v19 = PRFCachedHashEntry;
  if ( PRFCachedHashEntry >= 0 )
  {
    v20 = (unsigned int)(Size + a8);
    if ( !(_DWORD)v20
      || (unsigned int)v20 > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)(unsigned int)v20 + g_ulAdditionalProbeSize + 8 < (unsigned int)v20
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_35;
    }
    v21 = v20 + 23;
    if ( v20 + 23 <= (unsigned __int64)(v20 + 8) )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
    v23 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
    v10 = (char *)&v28;
    if ( &v27 == (__int64 *)-64LL || (LODWORD(v28) = 1801679955, v10 = (char *)&v28 + 8, &v28 == (__int128 *)-8LL) )
    {
LABEL_35:
      if ( v20 + 8 >= (unsigned __int64)(unsigned int)v20 )
      {
        v24 = (char *)((__int64 (*)(void))g_pfnAllocate)();
        v10 = v24;
        if ( v24 )
        {
          *(_DWORD *)v24 = 1885431112;
          v10 = v24 + 8;
        }
      }
    }
    if ( v10 )
    {
      memcpy_0(v10, Src, (unsigned int)Size);
      memcpy_0(&v10[(unsigned int)Size], a7, (unsigned int)a8);
      v25 = I_BCryptP_Hash(a3, a4, v10, (unsigned int)v20, &v28, a9, a10);
      v19 = v25;
      if ( v25 < 0 )
        DebugTraceError((unsigned int)v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", 871);
      if ( *((_DWORD *)v10 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
    }
    else
    {
      v19 = -1073741801;
    }
  }
  else
  {
    DebugTraceError(
      (unsigned int)PRFCachedHashEntry,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c",
      840);
  }
  I_ClosePRFHashEntry(&v28);
  return v19;
}

```

## disassembly

```asm
0x18007ecd4  push    rbp
0x18007ecd6  push    rbx
0x18007ecd7  push    rsi
0x18007ecd8  push    rdi
0x18007ecd9  push    r12
0x18007ecdb  push    r13
0x18007ecdd  push    r14
0x18007ecdf  push    r15
0x18007ece1  sub     rsp, 78h
0x18007ece5  lea     rbp, [rsp+40h]
0x18007ecea  mov     rax, cs:__security_cookie
0x18007ecf1  xor     rax, rbp
0x18007ecf4  mov     [rbp+70h+var_50], rax
0x18007ecf8  xor     eax, eax
0x18007ecfa  xor     edi, edi
0x18007ecfc  mov     [rbp+70h+var_60], rax
0x18007ed00  xorps   xmm0, xmm0
0x18007ed03  mov     r12d, r9d
0x18007ed06  mov     r13, r8
0x18007ed09  mov     r10, rdx
0x18007ed0c  movups  [rbp+70h+var_70], xmm0
0x18007ed10  test    rdx, rdx
0x18007ed13  jz      short loc_18007ED60
0x18007ed15  cmp     [rdx], di
0x18007ed18  jz      short loc_18007ED60
0x18007ed1a  mov     ecx, edi
0x18007ed1c  cmp     ecx, 2
0x18007ed1f  jnb     short loc_18007ED52
0x18007ed21  mov     eax, ecx
0x18007ed23  lea     r9, off_180087F00; "SHA256"
0x18007ed2a  mov     rdx, r10
0x18007ed2d  mov     r9, [r9+rax*8]
0x18007ed31  sub     r9, r10
0x18007ed34  movzx   eax, word ptr [rdx]
0x18007ed37  movzx   r8d, word ptr [rdx+r9]
0x18007ed3c  sub     eax, r8d
0x18007ed3f  jnz     short loc_18007ED4A
0x18007ed41  add     rdx, 2
0x18007ed45  test    r8d, r8d
0x18007ed48  jnz     short loc_18007ED34
0x18007ed4a  test    eax, eax
0x18007ed4c  jz      short loc_18007ED62
0x18007ed4e  inc     ecx
0x18007ed50  jmp     short loc_18007ED1C
0x18007ed52  lea     rdx, [rbp+70h+var_70]
0x18007ed56  mov     rcx, r10
0x18007ed59  call    I_LoadPRFHashProvider
0x18007ed5e  jmp     short loc_18007ED6B
0x18007ed60  mov     ecx, edi
0x18007ed62  lea     rdx, [rbp+70h+var_70]
0x18007ed66  call    I_GetPRFCachedHashEntry
0x18007ed6b  mov     ebx, eax
0x18007ed6d  test    eax, eax
0x18007ed6f  jns     short loc_18007ED91
0x18007ed71  mov     r9d, 348h
0x18007ed77  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ed7e  lea     rdx, aStatus; "Status"
0x18007ed85  mov     ecx, eax
0x18007ed87  call    DebugTraceError
0x18007ed8c  jmp     loc_18007EED0
0x18007ed91  mov     r14d, dword ptr [rbp+70h+Size]
0x18007ed98  mov     r15d, dword ptr [rbp+70h+arg_38]
0x18007ed9f  lea     esi, [r14+r15]
0x18007eda3  test    esi, esi
0x18007eda5  jz      short loc_18007EE0A
0x18007eda7  mov     ebx, esi
0x18007eda9  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007edb0  ja      short loc_18007EE0A
0x18007edb2  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007edb9  add     rcx, 8
0x18007edbd  add     rcx, rbx
0x18007edc0  cmp     rcx, rbx
0x18007edc3  jb      short loc_18007EE0A
0x18007edc5  call    VerifyStackAvailable
0x18007edca  test    eax, eax
0x18007edcc  jz      short loc_18007EE0A
0x18007edce  lea     rax, [rsi+8]
0x18007edd2  lea     rcx, [rax+0Fh]
0x18007edd6  cmp     rcx, rax
0x18007edd9  ja      short loc_18007EDE5
0x18007eddb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007ede5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007ede9  mov     rax, rcx
0x18007edec  call    __chkstk_0
0x18007edf1  sub     rsp, rcx
0x18007edf4  lea     rdi, [rsp+0B0h+var_70]
0x18007edf9  test    rdi, rdi
0x18007edfc  jz      short loc_18007EE0A
0x18007edfe  mov     dword ptr [rdi], 6B637453h
0x18007ee04  add     rdi, 8
0x18007ee08  jnz     short loc_18007EE33
0x18007ee0a  mov     eax, esi
0x18007ee0c  lea     rcx, [rsi+8]
0x18007ee10  cmp     rcx, rax
0x18007ee13  jb      short loc_18007EE33
0x18007ee15  mov     rax, cs:g_pfnAllocate
0x18007ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee21  mov     rdi, rax
0x18007ee24  test    rax, rax
0x18007ee27  jz      short loc_18007EE33
0x18007ee29  mov     dword ptr [rax], 70616548h
0x18007ee2f  add     rdi, 8
0x18007ee33  test    rdi, rdi
0x18007ee36  jnz     short loc_18007EE42
0x18007ee38  mov     ebx, 0C0000017h
0x18007ee3d  jmp     loc_18007EED0
0x18007ee42  mov     rdx, [rbp+70h+Src]; Src
0x18007ee49  mov     r8, r14; Size
0x18007ee4c  mov     rcx, rdi; void *
0x18007ee4f  call    memcpy_0
0x18007ee54  mov     rdx, [rbp+70h+arg_30]; Src
0x18007ee5b  lea     rcx, [r14+rdi]; void *
0x18007ee5f  mov     r8, r15; Size
0x18007ee62  call    memcpy_0
0x18007ee67  mov     eax, [rbp+70h+arg_48]
0x18007ee6d  mov     r9d, esi
0x18007ee70  mov     [rsp+0B0h+var_80], eax
0x18007ee74  mov     r8, rdi
0x18007ee77  mov     rax, [rbp+70h+arg_40]
0x18007ee7e  mov     edx, r12d
0x18007ee81  mov     [rsp+0B0h+var_88], rax
0x18007ee86  mov     rcx, r13
0x18007ee89  lea     rax, [rbp+70h+var_70]
0x18007ee8d  mov     [rsp+0B0h+var_90], rax
0x18007ee92  call    I_BCryptP_Hash
0x18007ee97  mov     ebx, eax
0x18007ee99  test    eax, eax
0x18007ee9b  jns     short loc_18007EEB8
0x18007ee9d  mov     r9d, 367h
0x18007eea3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007eeaa  lea     rdx, aStatus; "Status"
0x18007eeb1  mov     ecx, eax
0x18007eeb3  call    DebugTraceError
0x18007eeb8  lea     rcx, [rdi-8]
0x18007eebc  cmp     dword ptr [rcx], 70616548h
0x18007eec2  jnz     short loc_18007EED0
0x18007eec4  mov     rax, cs:g_pfnFree
0x18007eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eed0  lea     rcx, [rbp+70h+var_70]
0x18007eed4  call    I_ClosePRFHashEntry
0x18007eed9  mov     eax, ebx
0x18007eedb  mov     rcx, [rbp+70h+var_50]
0x18007eedf  xor     rcx, rbp; StackCookie
0x18007eee2  call    __security_check_cookie
0x18007eee7  lea     rsp, [rbp+38h]
0x18007eeeb  pop     r15
0x18007eeed  pop     r14
0x18007eeef  pop     r13
0x18007eef1  pop     r12
0x18007eef3  pop     rdi
0x18007eef4  pop     rsi
0x18007eef5  pop     rbx
0x18007eef6  pop     rbp
0x18007eef7  retn
```
