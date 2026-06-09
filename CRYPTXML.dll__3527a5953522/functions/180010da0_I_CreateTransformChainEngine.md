# I_CreateTransformChainEngine

- ea: `0x180010da0`
- end: `0x18001102c`
- name: `I_CreateTransformChainEngine`
- size: `652`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800057a0`
- `0x18000c990`

## callees

- `0x1800070d0`
- `0x180010da0`
- `0x180014ce0`
- `0x180018625`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010eed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180010eed`

## string_xrefs

- `0x180010fa7`: `onecore\ds\security\cryptoapi\xml\lib\engine.cpp`

## pseudocode

```c
__int64 __fastcall I_CreateTransformChainEngine(
        struct _CRYPT_XML_TRANSFORM_CHAIN_CONFIG *a1,
        unsigned int a2,
        __int64 a3,
        _OWORD *a4,
        __int64 *a5)
{
  __int64 v5; // rdi
  struct _CRYPT_XML_TRANSFORM_CHAIN_CONFIG *v7; // rsi
  __int64 result; // rax
  int v10; // edi
  __int64 i; // rbp
  PCRYPT_XML_TRANSFORM_INFO v12; // r15
  PCNZWCH *v13; // rdx
  PCNZWCH v14; // rcx
  int v15; // ebx
  __int64 v16; // rdi
  PCRYPT_XML_TRANSFORM_INFO v17; // r8
  int cchCount2; // eax
  bool v19; // zf
  const WCHAR *wszAlgorithm; // r8
  __int64 v21; // rbx
  __int128 v22; // xmm1
  const char *v23; // rax
  const char *v24; // r10
  void (__fastcall *v25)(__int64); // rax
  __int64 v26; // rcx
  struct _CRYPT_XML_TRANSFORM_CHAIN_CONFIG *v27; // [rsp+30h] [rbp-108h]
  __int128 v29; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v30; // [rsp+50h] [rbp-E8h]
  PCNZWCH *v31; // [rsp+60h] [rbp-D8h]
  _QWORD v32[16]; // [rsp+70h] [rbp-C8h] BYREF

  v5 = a3;
  v7 = a1;
  v27 = a1;
  memset_0(v32, 0, sizeof(v32));
  v29 = 0;
  v30 = 0;
  *(_OWORD *)a5 = *a4;
  *((_OWORD *)a5 + 1) = a4[1];
  if ( !a2 )
    return 0;
  if ( !v7 )
  {
    v7 = &g_CHAIN_CONFIG;
    v27 = &g_CHAIN_CONFIG;
  }
  if ( a2 > 0x10 )
  {
    v10 = -2146885374;
LABEL_28:
    v23 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\engine.cpp");
    WPPTraceLogA(v24, (unsigned int)v10, v23);
    v25 = (void (__fastcall *)(__int64))*((_QWORD *)&v30 + 1);
    if ( *((_QWORD *)&v30 + 1) )
    {
      v26 = v29;
    }
    else
    {
      v25 = (void (__fastcall *)(__int64))a5[3];
      if ( !v25 )
      {
LABEL_33:
        result = (unsigned int)v10;
        *(_OWORD *)a5 = 0;
        *((_OWORD *)a5 + 1) = 0;
        return result;
      }
      v26 = *a5;
    }
    v25(v26);
    goto LABEL_33;
  }
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v12 = 0;
    v13 = (PCNZWCH *)(v5 + 32LL * (unsigned int)i + 8);
    v31 = v13;
    v14 = *v13;
    if ( *v13 )
    {
      v15 = 0;
      if ( *v14 )
      {
        do
        {
          if ( v14[v15] == 63 )
            break;
          ++v15;
        }
        while ( v14[v15] );
      }
      v16 = 0;
      while ( (unsigned int)v16 < v7->cTransformInfo )
      {
        v17 = v27->rgpTransformInfo[v16];
        cchCount2 = -1;
        v19 = (v17->dwFlags & 4) == 0;
        wszAlgorithm = v17->wszAlgorithm;
        if ( !v19 )
          cchCount2 = v15;
        if ( CompareStringW(0, 1u, wszAlgorithm, -1, *v13, cchCount2) == 2 )
        {
          v12 = v27->rgpTransformInfo[v16];
          break;
        }
        v7 = v27;
        v16 = (unsigned int)(v16 + 1);
        v13 = v31;
      }
      v5 = a3;
    }
    v32[i] = v12;
    if ( !v12 )
    {
      v10 = -2146885371;
      goto LABEL_28;
    }
    v7 = v27;
  }
  v21 = 0;
  while ( (unsigned int)v21 < a2 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(v32[v21] + 24LL))(
            v5 + 32LL * (unsigned int)v21,
            a5,
            &v29);
    if ( v10 < 0 )
      goto LABEL_28;
    v5 = a3;
    v21 = (unsigned int)(v21 + 1);
    v22 = v30;
    *(_OWORD *)a5 = v29;
    v29 = 0;
    v30 = 0;
    *((_OWORD *)a5 + 1) = v22;
  }
  return 0;
}

```

## disassembly

```asm
0x180010da0  push    rbx
0x180010da2  push    rsi
0x180010da3  push    rdi
0x180010da4  push    r12
0x180010da6  push    r14
0x180010da8  sub     rsp, 110h
0x180010daf  mov     rax, cs:__security_cookie
0x180010db6  xor     rax, rsp
0x180010db9  mov     [rsp+138h+var_48], rax
0x180010dc1  mov     r14, [rsp+138h+arg_20]
0x180010dc9  mov     rdi, r8
0x180010dcc  mov     [rsp+138h+var_100], r8
0x180010dd1  mov     r12d, edx
0x180010dd4  mov     rsi, rcx
0x180010dd7  mov     [rsp+138h+var_108], rcx
0x180010ddc  xor     edx, edx; Val
0x180010dde  lea     rcx, [rsp+138h+var_C8]; void *
0x180010de3  mov     r8d, 80h; Size
0x180010de9  mov     rbx, r9
0x180010dec  call    memset_0
0x180010df1  xorps   xmm0, xmm0
0x180010df4  movups  [rsp+138h+var_F8], xmm0
0x180010df9  movups  [rsp+138h+var_E8], xmm0
0x180010dfe  movups  xmm0, xmmword ptr [rbx]
0x180010e01  movups  xmmword ptr [r14], xmm0
0x180010e05  movups  xmm1, xmmword ptr [rbx+10h]
0x180010e09  movups  xmmword ptr [r14+10h], xmm1
0x180010e0e  test    r12d, r12d
0x180010e11  jnz     short loc_180010E1A
0x180010e13  xor     eax, eax
0x180010e15  jmp     loc_18001100C
0x180010e1a  test    rsi, rsi
0x180010e1d  jnz     short loc_180010E2B
0x180010e1f  lea     rsi, ?g_CHAIN_CONFIG@@3U_CRYPT_XML_TRANSFORM_CHAIN_CONFIG@@A; _CRYPT_XML_TRANSFORM_CHAIN_CONFIG g_CHAIN_CONFIG
0x180010e26  mov     [rsp+138h+var_108], rsi
0x180010e2b  mov     [rsp+138h+arg_8], rbp
0x180010e33  mov     [rsp+138h+var_30], r13
0x180010e3b  mov     [rsp+138h+var_38], r15
0x180010e43  cmp     r12d, 10h
0x180010e47  jbe     short loc_180010E59
0x180010e49  mov     edi, 80092102h
0x180010e4e  mov     r9d, 97h
0x180010e54  jmp     loc_180010FA0
0x180010e59  xor     ebp, ebp
0x180010e5b  nop     dword ptr [rax+rax+00h]
0x180010e60  cmp     ebp, r12d
0x180010e63  jnb     loc_180010F41
0x180010e69  mov     edx, ebp
0x180010e6b  xor     r15d, r15d
0x180010e6e  shl     rdx, 5
0x180010e72  add     rdx, 8
0x180010e76  add     rdx, rdi
0x180010e79  mov     [rsp+138h+var_D8], rdx
0x180010e7e  mov     rcx, [rdx]
0x180010e81  test    rcx, rcx
0x180010e84  jz      loc_180010F1E
0x180010e8a  xor     ebx, ebx
0x180010e8c  cmp     [rcx], bx
0x180010e8f  jz      short loc_180010EA7
0x180010e91  movsxd  rax, ebx
0x180010e94  cmp     word ptr [rcx+rax*2], 3Fh ; '?'
0x180010e99  jz      short loc_180010EA7
0x180010e9b  inc     ebx
0x180010e9d  movsxd  rax, ebx
0x180010ea0  cmp     [rcx+rax*2], r15w
0x180010ea5  jnz     short loc_180010E91
0x180010ea7  xor     edi, edi
0x180010ea9  cmp     edi, [rsi+4]
0x180010eac  jnb     short loc_180010F19
0x180010eae  mov     rax, [rsp+138h+var_108]
0x180010eb3  lea     rsi, ds:0[rdi*8]
0x180010ebb  mov     r9d, 0FFFFFFFFh; cchCount1
0x180010ec1  mov     rax, [rax+8]
0x180010ec5  mov     r8, [rsi+rax]
0x180010ec9  mov     eax, 0FFFFFFFFh
0x180010ece  test    byte ptr [r8+14h], 4
0x180010ed3  mov     r8, [r8+8]; lpString1
0x180010ed7  cmovnz  eax, ebx
0x180010eda  xor     ecx, ecx; Locale
0x180010edc  mov     [rsp+138h+cchCount2], eax; cchCount2
0x180010ee0  mov     rax, [rdx]
0x180010ee3  mov     edx, 1; dwCmpFlags
0x180010ee8  mov     [rsp+138h+lpString2], rax; lpString2
0x180010eed  call    cs:__imp_CompareStringW
0x180010ef4  nop     dword ptr [rax+rax+00h]
0x180010ef9  cmp     eax, 2
0x180010efc  jz      short loc_180010F0C
0x180010efe  mov     rsi, [rsp+138h+var_108]
0x180010f03  inc     edi
0x180010f05  mov     rdx, [rsp+138h+var_D8]
0x180010f0a  jmp     short loc_180010EA9
0x180010f0c  mov     rax, [rsp+138h+var_108]
0x180010f11  mov     rax, [rax+8]
0x180010f15  mov     r15, [rsi+rax]
0x180010f19  mov     rdi, [rsp+138h+var_100]
0x180010f1e  mov     [rsp+rbp*8+138h+var_C8], r15
0x180010f23  test    r15, r15
0x180010f26  jz      short loc_180010F34
0x180010f28  mov     rsi, [rsp+138h+var_108]
0x180010f2d  inc     ebp
0x180010f2f  jmp     loc_180010E60
0x180010f34  mov     edi, 80092105h
0x180010f39  mov     r9d, 0A9h
0x180010f3f  jmp     short loc_180010FA0
0x180010f41  xor     ebx, ebx
0x180010f43  cmp     ebx, r12d
0x180010f46  jnb     loc_180010FF2
0x180010f4c  mov     rax, [rsp+rbx*8+138h+var_C8]
0x180010f51  lea     r8, [rsp+138h+var_F8]
0x180010f56  mov     ecx, ebx
0x180010f58  mov     rdx, r14
0x180010f5b  shl     rcx, 5
0x180010f5f  add     rcx, rdi
0x180010f62  mov     rax, [rax+18h]
0x180010f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6b  mov     edi, eax
0x180010f6d  test    eax, eax
0x180010f6f  js      short loc_180010F9A
0x180010f71  movups  xmm0, [rsp+138h+var_F8]
0x180010f76  mov     rdi, [rsp+138h+var_100]
0x180010f7b  inc     ebx
0x180010f7d  movups  xmm1, [rsp+138h+var_E8]
0x180010f82  movups  xmmword ptr [r14], xmm0
0x180010f86  xorps   xmm0, xmm0
0x180010f89  movups  [rsp+138h+var_F8], xmm0
0x180010f8e  movups  [rsp+138h+var_E8], xmm0
0x180010f93  movups  xmmword ptr [r14+10h], xmm1
0x180010f98  jmp     short loc_180010F43
0x180010f9a  mov     r9d, 0BCh
0x180010fa0  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010fa7  lea     rcx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010fae  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010fb3  mov     r8, rax
0x180010fb6  mov     edx, edi
0x180010fb8  mov     rcx, r10; char *
0x180010fbb  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180010fc0  mov     rax, qword ptr [rsp+138h+var_E8+8]
0x180010fc5  test    rax, rax
0x180010fc8  jz      short loc_180010FD1
0x180010fca  mov     rcx, qword ptr [rsp+138h+var_F8]
0x180010fcf  jmp     short loc_180010FDD
0x180010fd1  mov     rax, [r14+18h]
0x180010fd5  test    rax, rax
0x180010fd8  jz      short loc_180010FE2
0x180010fda  mov     rcx, [r14]
0x180010fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe2  xorps   xmm0, xmm0
0x180010fe5  mov     eax, edi
0x180010fe7  movups  xmmword ptr [r14], xmm0
0x180010feb  movups  xmmword ptr [r14+10h], xmm0
0x180010ff0  jmp     short loc_180010FF4
0x180010ff2  xor     eax, eax
0x180010ff4  mov     r13, [rsp+138h+var_30]
0x180010ffc  mov     rbp, [rsp+138h+arg_8]
0x180011004  mov     r15, [rsp+138h+var_38]
0x18001100c  mov     rcx, [rsp+138h+var_48]
0x180011014  xor     rcx, rsp; StackCookie
0x180011017  call    __security_check_cookie
0x18001101c  add     rsp, 110h
0x180011023  pop     r14
0x180011025  pop     r12
0x180011027  pop     rdi
0x180011028  pop     rsi
0x180011029  pop     rbx
0x18001102a  retn
```
