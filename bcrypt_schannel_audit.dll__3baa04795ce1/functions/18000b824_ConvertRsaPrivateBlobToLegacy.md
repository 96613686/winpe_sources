# ConvertRsaPrivateBlobToLegacy

- ea: `0x18000b824`
- end: `0x18000bab9`
- name: `ConvertRsaPrivateBlobToLegacy`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e368`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x18000b824`
- `0x18000bac0`
- `0x18000cae4`
- `0x18000ddd4`
- `0x18001b785`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x18000b9e6`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000ba36`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000ba86`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ConvertRsaPrivateBlobToLegacy(_DWORD *a1, int a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  bool v5; // cc
  int v7; // r12d
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned int *v17; // rdi
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  unsigned int *v23; // rax
  int v24; // edx
  unsigned int v25; // eax
  __int64 v27; // [rsp+0h] [rbp-40h] BYREF
  unsigned int v28; // [rsp+40h] [rbp+0h] BYREF
  __int64 v29; // [rsp+48h] [rbp+8h] BYREF

  v5 = a1[2] <= 4u;
  v7 = a3;
  v28 = 0;
  if ( !v5
    || a1[3] > 0x800u
    || (v10 = a1[1], (unsigned int)(v10 - 256) > 0x3F00)
    || (v10 & 7) != 0
    || (v11 = (unsigned int)(v10 + 15) >> 4, a1[4] != v11)
    || a1[5] != v11 )
  {
    v15 = 2148073513LL;
    v13 = -2146893783;
    goto LABEL_36;
  }
  v12 = v11 + 8 * v11 + 20;
  *a5 = v12;
  if ( !a3 )
    return 0;
  if ( a4 < v12 )
    return (unsigned int)-2146893784;
  v14 = ConvertRsaPrivateBlobToFullRsa((_DWORD)a1, a2, 0, 0, (__int64)&v28);
  v13 = v14;
  if ( v14 )
  {
    v15 = v14;
LABEL_36:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    return v13;
  }
  v16 = v28;
  v17 = 0;
  if ( !v28 )
    goto LABEL_40;
  if ( v28 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_40;
  v18 = v28 + g_ulAdditionalProbeSize + 8;
  if ( v18 < v28 || !(unsigned int)VerifyStackAvailable(v18) )
    goto LABEL_40;
  v19 = v16 + 23;
  if ( v16 + 23 <= v16 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  v17 = &v28;
  if ( &v27 == (__int64 *)-64LL || (v28 = 1801679955, (v17 = (unsigned int *)&v29) == 0) )
  {
LABEL_40:
    if ( v16 + 8 >= v16 )
    {
      v23 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
      v17 = v23;
      if ( v23 )
      {
        *v23 = 1885431112;
        v17 = v23 + 2;
      }
    }
  }
  if ( !v17 )
  {
    v13 = -2146893810;
    v15 = 2148073486LL;
    goto LABEL_36;
  }
  v13 = ConvertRsaPrivateBlobToFullRsa((_DWORD)a1, a2, (_DWORD)v17, v28, (__int64)&v28);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
        32);
  }
  else
  {
    v25 = ConvertFullRsaToLegacy((_DWORD)v17, v28, v7, a4, (__int64)a5, 41984);
    v13 = v25;
    if ( v25 )
      DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    else
      v13 = 0;
  }
  if ( *(v17 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v13;
}

```

## disassembly

```asm
0x18000b824  push    rbp
0x18000b826  push    rbx
0x18000b827  push    rsi
0x18000b828  push    rdi
0x18000b829  push    r12
0x18000b82b  push    r13
0x18000b82d  push    r14
0x18000b82f  push    r15
0x18000b831  sub     rsp, 68h
0x18000b835  lea     rbp, [rsp+40h]
0x18000b83a  mov     rax, cs:__security_cookie
0x18000b841  xor     rax, rbp
0x18000b844  mov     [rbp+60h+var_50], rax
0x18000b848  cmp     dword ptr [rcx+8], 4
0x18000b84c  mov     r15d, r9d
0x18000b84f  mov     r12, r8
0x18000b852  mov     [rbp+60h+var_60], 0
0x18000b859  mov     r13d, edx
0x18000b85c  mov     rsi, rcx
0x18000b85f  ja      loc_18000BA79
0x18000b865  cmp     dword ptr [rcx+0Ch], 800h
0x18000b86c  ja      loc_18000BA79
0x18000b872  mov     ecx, [rcx+4]
0x18000b875  lea     eax, [rcx-100h]
0x18000b87b  cmp     eax, 3F00h
0x18000b880  ja      loc_18000BA71
0x18000b886  test    cl, 7
0x18000b889  jnz     loc_18000BA71
0x18000b88f  lea     eax, [rcx+0Fh]
0x18000b892  shr     eax, 4
0x18000b895  cmp     [rsi+10h], eax
0x18000b898  jnz     loc_18000BA69
0x18000b89e  cmp     [rsi+14h], eax
0x18000b8a1  jnz     loc_18000BA69
0x18000b8a7  mov     r14, [rbp+60h+arg_20]
0x18000b8ae  lea     ecx, ds:14h[rax*8]
0x18000b8b5  add     ecx, eax
0x18000b8b7  mov     [r14], ecx
0x18000b8ba  test    r8, r8
0x18000b8bd  jnz     short loc_18000B8C6
0x18000b8bf  xor     ebx, ebx
0x18000b8c1  jmp     loc_18000BA99
0x18000b8c6  cmp     r15d, ecx
0x18000b8c9  jnb     short loc_18000B8D5
0x18000b8cb  mov     ebx, 80090028h
0x18000b8d0  jmp     loc_18000BA99
0x18000b8d5  lea     rax, [rbp+60h+var_60]
0x18000b8d9  xor     r9d, r9d
0x18000b8dc  xor     r8d, r8d
0x18000b8df  mov     [rsp+0A0h+var_80], rax
0x18000b8e4  mov     rcx, rsi
0x18000b8e7  call    ConvertRsaPrivateBlobToFullRsa
0x18000b8ec  mov     ebx, eax
0x18000b8ee  test    eax, eax
0x18000b8f0  jz      short loc_18000B8FF
0x18000b8f2  mov     r9d, 30Ch
0x18000b8f8  mov     ecx, eax
0x18000b8fa  jmp     loc_18000BA86
0x18000b8ff  mov     ebx, [rbp+60h+var_60]
0x18000b902  xor     edi, edi
0x18000b904  test    rbx, rbx
0x18000b907  jz      short loc_18000B96A
0x18000b909  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000b910  ja      short loc_18000B96A
0x18000b912  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000b919  add     rcx, 8
0x18000b91d  add     rcx, rbx
0x18000b920  cmp     rcx, rbx
0x18000b923  jb      short loc_18000B96A
0x18000b925  call    VerifyStackAvailable
0x18000b92a  test    eax, eax
0x18000b92c  jz      short loc_18000B96A
0x18000b92e  lea     rax, [rbx+8]
0x18000b932  lea     rcx, [rax+0Fh]
0x18000b936  cmp     rcx, rax
0x18000b939  ja      short loc_18000B945
0x18000b93b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000b945  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b949  mov     rax, rcx
0x18000b94c  call    __chkstk_0
0x18000b951  sub     rsp, rcx
0x18000b954  lea     rdi, [rsp+0A0h+var_60]
0x18000b959  test    rdi, rdi
0x18000b95c  jz      short loc_18000B96A
0x18000b95e  mov     dword ptr [rdi], 6B637453h
0x18000b964  add     rdi, 8
0x18000b968  jnz     short loc_18000B991
0x18000b96a  lea     rcx, [rbx+8]
0x18000b96e  cmp     rcx, rbx
0x18000b971  jb      short loc_18000B991
0x18000b973  mov     rax, cs:g_pfnAllocate
0x18000b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97f  mov     rdi, rax
0x18000b982  test    rax, rax
0x18000b985  jz      short loc_18000B991
0x18000b987  mov     dword ptr [rax], 70616548h
0x18000b98d  add     rdi, 8
0x18000b991  test    rdi, rdi
0x18000b994  jnz     short loc_18000B9A8
0x18000b996  mov     ebx, 8009000Eh
0x18000b99b  mov     r9d, 319h
0x18000b9a1  mov     ecx, ebx
0x18000b9a3  jmp     loc_18000BA86
0x18000b9a8  mov     r9d, [rbp+60h+var_60]
0x18000b9ac  lea     rax, [rbp+60h+var_60]
0x18000b9b0  mov     r8, rdi
0x18000b9b3  mov     [rsp+0A0h+var_80], rax
0x18000b9b8  mov     edx, r13d
0x18000b9bb  mov     rcx, rsi
0x18000b9be  call    ConvertRsaPrivateBlobToFullRsa
0x18000b9c3  mov     ebx, eax
0x18000b9c5  test    eax, eax
0x18000b9c7  jz      short loc_18000BA0C
0x18000b9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9d0  lea     rax, WPP_GLOBAL_Control
0x18000b9d7  cmp     rcx, rax
0x18000b9da  jz      short loc_18000BA4F
0x18000b9dc  test    byte ptr [rcx+1Ch], 1
0x18000b9e0  jz      short loc_18000BA4F
0x18000b9e2  mov     rcx, [rcx+10h]
0x18000b9e6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b9ed  mov     [rsp+0A0h+var_70], 320h
0x18000b9f5  lea     r9, aStatus; "Status"
0x18000b9fc  mov     [rsp+0A0h+var_78], r8
0x18000ba01  mov     dword ptr [rsp+0A0h+var_80], ebx
0x18000ba05  call    WPP_SF_sDsd
0x18000ba0a  jmp     short loc_18000BA4F
0x18000ba0c  mov     edx, [rbp+60h+var_60]
0x18000ba0f  mov     r9d, r15d
0x18000ba12  mov     dword ptr [rsp+0A0h+var_78], 0A400h
0x18000ba1a  mov     r8, r12
0x18000ba1d  mov     rcx, rdi
0x18000ba20  mov     [rsp+0A0h+var_80], r14
0x18000ba25  call    ConvertFullRsaToLegacy
0x18000ba2a  mov     ebx, eax
0x18000ba2c  test    eax, eax
0x18000ba2e  jz      short loc_18000BA4D
0x18000ba30  mov     r9d, 334h
0x18000ba36  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ba3d  lea     rdx, aStatus; "Status"
0x18000ba44  mov     ecx, eax
0x18000ba46  call    DebugTraceError
0x18000ba4b  jmp     short loc_18000BA4F
0x18000ba4d  xor     ebx, ebx
0x18000ba4f  lea     rcx, [rdi-8]
0x18000ba53  cmp     dword ptr [rcx], 70616548h
0x18000ba59  jnz     short loc_18000BA99
0x18000ba5b  mov     rax, cs:g_pfnFree
0x18000ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba67  jmp     short loc_18000BA99
0x18000ba69  mov     r9d, 2EBh
0x18000ba6f  jmp     short loc_18000BA7F
0x18000ba71  mov     r9d, 2DEh
0x18000ba77  jmp     short loc_18000BA7F
0x18000ba79  mov     r9d, 2D5h
0x18000ba7f  mov     ecx, 80090029h
0x18000ba84  mov     ebx, ecx
0x18000ba86  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ba8d  lea     rdx, aStatus; "Status"
0x18000ba94  call    DebugTraceError
0x18000ba99  mov     eax, ebx
0x18000ba9b  mov     rcx, [rbp+60h+var_50]
0x18000ba9f  xor     rcx, rbp; StackCookie
0x18000baa2  call    __security_check_cookie
0x18000baa7  lea     rsp, [rbp+28h]
0x18000baab  pop     r15
0x18000baad  pop     r14
0x18000baaf  pop     r13
0x18000bab1  pop     r12
0x18000bab3  pop     rdi
0x18000bab4  pop     rsi
0x18000bab5  pop     rbx
0x18000bab6  pop     rbp
0x18000bab7  retn
```
