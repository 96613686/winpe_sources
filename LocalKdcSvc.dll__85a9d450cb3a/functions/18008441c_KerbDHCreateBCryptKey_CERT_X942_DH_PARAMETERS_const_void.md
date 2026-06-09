# KerbDHCreateBCryptKey(_CERT_X942_DH_PARAMETERS const &,void * *)

- ea: `0x18008441c`
- end: `0x180084728`
- name: `?KerbDHCreateBCryptKey@@YAJAEBU_CERT_X942_DH_PARAMETERS@@PEAPEAX@Z`
- size: `780`
- prototype: `__int64 __fastcall(const struct _CERT_X942_DH_PARAMETERS *, void **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004ea74`
- `0x180050e78`
- `0x180055d94`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x180071868`
- `0x18008441c`
- `0x180085500`
- `0x180099be0`
- `0x18009c010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1800846ab`
- `bcrypt!BCryptSetProperty` at `0x1800846ab`
- `bcrypt!BCryptDestroyKey` at `0x18008448e`
- `bcrypt!BCryptDestroyKey` at `0x18008448e`
- `bcrypt!BCryptGenerateKeyPair` at `0x180084535`
- `bcrypt!BCryptGenerateKeyPair` at `0x180084535`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800846e8`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800846e8`

## pseudocode

```c
__int64 __fastcall KerbDHCreateBCryptKey(const struct _CERT_X942_DH_PARAMETERS *a1, void **a2)
{
  int *v2; // rsi
  unsigned int v5; // r12d
  DWORD v6; // r14d
  __int64 v8; // r14
  NTSTATUS KeyPair; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  CSecurityData *v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  int *v21; // rax
  size_t v22; // rbx
  size_t v23; // rdi
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  __int64 v26; // [rsp+0h] [rbp-30h] BYREF
  int v27; // [rsp+30h] [rbp+0h] BYREF
  _QWORD v28[9]; // [rsp+38h] [rbp+8h] BYREF

  v2 = 0;
  *a2 = 0;
  v5 = 60;
  v6 = a1->p.cbData + 7;
  if ( v6 < a1->p.cbData )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids);
    goto LABEL_5;
  }
  v8 = v6 & 0xFFFFFFF8;
  if ( (unsigned int)(8 * v8) < 0x400 )
  {
    v5 = 65;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids,
        (unsigned int)v8);
    goto LABEL_5;
  }
  KeyPair = BCryptGenerateKeyPair((BCRYPT_ALG_HANDLE)0x281, a2, 8 * v8, 0);
  v12 = (unsigned int)KeyPair;
  if ( KeyPair < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_5;
    v14 = 18;
    goto LABEL_19;
  }
  v15 = (unsigned int)(2 * v8 + 12);
  if ( v15 > g_ulMaxStackAllocSize )
    goto LABEL_42;
  v16 = v15 + g_ulAdditionalProbeSize + 8;
  if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16) )
    goto LABEL_42;
  v17 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  v2 = &v27;
  if ( &v26 == (__int64 *)-48LL || (v27 = 1801679955, (v2 = (int *)v28) == 0) )
  {
LABEL_42:
    if ( v15 + 8 >= v15 )
    {
      v21 = (int *)((__int64 (__fastcall *)(unsigned __int64, __int64, __int64, __int64))g_pfnAllocate)(
                     v15 + 8,
                     v10,
                     v11,
                     v12);
      v2 = v21;
      if ( v21 )
      {
        *v21 = 1885431112;
        v2 = v21 + 2;
      }
    }
  }
  if ( v2 )
  {
    memset_0(v2, 0, (unsigned int)(2 * v8 + 12));
    *v2 = v15;
    v2[2] = v8;
    v2[1] = 1297107012;
    v22 = (unsigned int)(v8 - a1->p.cbData);
    memset_0(v2 + 3, 0, v22);
    ReverseMemCpy((char *)v2 + v22 + 12, a1->p.pbData, a1->p.cbData);
    v23 = (unsigned int)(v8 - a1->g.cbData);
    memset_0((char *)v2 + v8 + 12, 0, v23);
    ReverseMemCpy((char *)v2 + v23 + v8 + 12, a1->g.pbData, a1->g.cbData);
    v24 = BCryptSetProperty(*a2, L"DHParameters", (PUCHAR)v2, 2 * v8 + 12, 0);
    v12 = (unsigned int)v24;
    if ( v24 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_5;
      v14 = 19;
LABEL_19:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids, v12);
      goto LABEL_5;
    }
    v25 = BCryptFinalizeKeyPair(*a2, 0);
    v12 = (unsigned int)v25;
    if ( v25 >= 0 )
    {
      v5 = 0;
LABEL_8:
      if ( *(v2 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return v5;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 20;
      goto LABEL_19;
    }
  }
LABEL_5:
  if ( *a2 )
  {
    BCryptDestroyKey(*a2);
    *a2 = 0;
  }
  if ( v2 )
    goto LABEL_8;
  return v5;
}

```

## disassembly

```asm
0x18008441c  push    rbp
0x18008441e  push    rbx
0x18008441f  push    rsi
0x180084420  push    rdi
0x180084421  push    r12
0x180084423  push    r13
0x180084425  push    r14
0x180084427  push    r15
0x180084429  sub     rsp, 48h
0x18008442d  lea     rbp, [rsp+30h]
0x180084432  mov     rax, cs:__security_cookie
0x180084439  xor     rax, rbp
0x18008443c  mov     [rbp+50h+var_48], rax
0x180084440  xor     esi, esi
0x180084442  mov     r15, rdx
0x180084445  mov     [rdx], rsi
0x180084448  mov     r13, rcx
0x18008444b  mov     eax, [rcx]
0x18008444d  lea     r12d, [rsi+3Ch]
0x180084451  lea     r14d, [rax+7]
0x180084455  cmp     r14d, eax
0x180084458  jnb     short loc_1800844D8
0x18008445a  mov     rcx, cs:WPP_GLOBAL_Control
0x180084461  lea     rax, WPP_GLOBAL_Control
0x180084468  cmp     rcx, rax
0x18008446b  jz      short loc_180084486
0x18008446d  test    byte ptr [rcx+1Ch], 1
0x180084471  jz      short loc_180084486
0x180084473  mov     rcx, [rcx+10h]
0x180084477  lea     edx, [rsi+10h]
0x18008447a  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x180084481  call    WPP_SF_
0x180084486  mov     rcx, [r15]; hKey
0x180084489  test    rcx, rcx
0x18008448c  jz      short loc_18008449B
0x18008448e  call    cs:__imp_BCryptDestroyKey
0x180084494  mov     qword ptr [r15], 0
0x18008449b  test    rsi, rsi
0x18008449e  jz      short loc_1800844B8
0x1800844a0  lea     rcx, [rsi-8]
0x1800844a4  cmp     dword ptr [rcx], 70616548h
0x1800844aa  jnz     short loc_1800844B8
0x1800844ac  mov     rax, cs:g_pfnFree
0x1800844b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844b8  mov     eax, r12d
0x1800844bb  mov     rcx, [rbp+50h+var_48]
0x1800844bf  xor     rcx, rbp; StackCookie
0x1800844c2  call    __security_check_cookie
0x1800844c7  lea     rsp, [rbp+18h]
0x1800844cb  pop     r15
0x1800844cd  pop     r14
0x1800844cf  pop     r13
0x1800844d1  pop     r12
0x1800844d3  pop     rdi
0x1800844d4  pop     rsi
0x1800844d5  pop     rbx
0x1800844d6  pop     rbp
0x1800844d7  retn
0x1800844d8  and     r14d, 0FFFFFFF8h
0x1800844dc  lea     r8d, ds:0[r14*8]; dwLength
0x1800844e4  cmp     r8d, 400h
0x1800844eb  jnb     short loc_18008452D
0x1800844ed  mov     r12d, 41h ; 'A'
0x1800844f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800844fa  lea     rax, WPP_GLOBAL_Control
0x180084501  cmp     rcx, rax
0x180084504  jz      short loc_180084486
0x180084506  test    byte ptr [rcx+1Ch], 1
0x18008450a  jz      loc_180084486
0x180084510  mov     rcx, [rcx+10h]
0x180084514  lea     edx, [r12-30h]
0x180084519  mov     r9d, r14d
0x18008451c  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x180084523  call    WPP_SF_d
0x180084528  jmp     loc_180084486
0x18008452d  xor     r9d, r9d; dwFlags
0x180084530  mov     ecx, 281h; hAlgorithm
0x180084535  call    cs:__imp_BCryptGenerateKeyPair
0x18008453b  mov     r9d, eax
0x18008453e  test    eax, eax
0x180084540  jns     short loc_18008457D
0x180084542  mov     rcx, cs:WPP_GLOBAL_Control
0x180084549  lea     rax, WPP_GLOBAL_Control
0x180084550  cmp     rcx, rax
0x180084553  jz      loc_180084486
0x180084559  test    byte ptr [rcx+1Ch], 1
0x18008455d  jz      loc_180084486
0x180084563  mov     edx, 12h
0x180084568  mov     rcx, [rcx+10h]
0x18008456c  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x180084573  call    WPP_SF_d
0x180084578  jmp     loc_180084486
0x18008457d  lea     edi, ds:0Ch[r14*2]
0x180084585  mov     ebx, edi
0x180084587  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18008458e  ja      short loc_1800845E8
0x180084590  mov     rcx, cs:g_ulAdditionalProbeSize
0x180084597  add     rcx, 8
0x18008459b  add     rcx, rbx
0x18008459e  cmp     rcx, rbx
0x1800845a1  jb      short loc_1800845E8
0x1800845a3  call    VerifyStackAvailable
0x1800845a8  test    eax, eax
0x1800845aa  jz      short loc_1800845E8
0x1800845ac  lea     rax, [rdi+8]
0x1800845b0  lea     rcx, [rax+0Fh]
0x1800845b4  cmp     rcx, rax
0x1800845b7  ja      short loc_1800845C3
0x1800845b9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800845c3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800845c7  mov     rax, rcx
0x1800845ca  call    _alloca_probe
0x1800845cf  sub     rsp, rcx
0x1800845d2  lea     rsi, [rsp+80h+var_50]
0x1800845d7  test    rsi, rsi
0x1800845da  jz      short loc_1800845E8
0x1800845dc  mov     dword ptr [rsi], 6B637453h
0x1800845e2  add     rsi, 8
0x1800845e6  jnz     short loc_18008460F
0x1800845e8  lea     rcx, [rdi+8]
0x1800845ec  cmp     rcx, rbx
0x1800845ef  jb      short loc_18008460F
0x1800845f1  mov     rax, cs:g_pfnAllocate
0x1800845f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845fd  mov     rsi, rax
0x180084600  test    rax, rax
0x180084603  jz      short loc_18008460F
0x180084605  mov     dword ptr [rax], 70616548h
0x18008460b  add     rsi, 8
0x18008460f  test    rsi, rsi
0x180084612  jz      loc_180084486
0x180084618  mov     r8, rbx; Size
0x18008461b  xor     edx, edx; Val
0x18008461d  mov     rcx, rsi; void *
0x180084620  call    memset_0
0x180084625  mov     eax, r14d
0x180084628  mov     [rsi], edi
0x18008462a  mov     [rsi+8], r14d
0x18008462e  lea     rcx, [rsi+0Ch]; void *
0x180084632  mov     dword ptr [rsi+4], 4D504844h
0x180084639  xor     edx, edx; Val
0x18008463b  sub     eax, [r13+0]
0x18008463f  mov     r8d, eax; Size
0x180084642  mov     ebx, eax
0x180084644  call    memset_0
0x180084649  mov     rdx, [r13+8]
0x18008464d  lea     rcx, [rbx+0Ch]
0x180084651  mov     r8d, [r13+0]
0x180084655  add     rcx, rsi
0x180084658  call    ReverseMemCpy
0x18008465d  mov     eax, r14d
0x180084660  lea     rcx, [r14+0Ch]
0x180084664  sub     eax, [r13+10h]
0x180084668  add     rcx, rsi; void *
0x18008466b  mov     r8d, eax; Size
0x18008466e  xor     edx, edx; Val
0x180084670  mov     edi, eax
0x180084672  call    memset_0
0x180084677  mov     rdx, [r13+18h]
0x18008467b  lea     rcx, [r14+0Ch]
0x18008467f  mov     r8d, [r13+10h]
0x180084683  add     rcx, rdi
0x180084686  add     rcx, rsi
0x180084689  call    ReverseMemCpy
0x18008468e  mov     rcx, [r15]; hObject
0x180084691  lea     r9d, ds:0Ch[r14*2]; cbInput
0x180084699  mov     r8, rsi; pbInput
0x18008469c  mov     [rsp+80h+dwFlags], 0; dwFlags
0x1800846a4  lea     rdx, aDhparameters; "DHParameters"
0x1800846ab  call    cs:__imp_BCryptSetProperty
0x1800846b1  mov     r9d, eax
0x1800846b4  test    eax, eax
0x1800846b6  jns     short loc_1800846E3
0x1800846b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800846bf  lea     rax, WPP_GLOBAL_Control
0x1800846c6  cmp     rcx, rax
0x1800846c9  jz      loc_180084486
0x1800846cf  test    byte ptr [rcx+1Ch], 1
0x1800846d3  jz      loc_180084486
0x1800846d9  mov     edx, 13h
0x1800846de  jmp     loc_180084568
0x1800846e3  mov     rcx, [r15]; hKey
0x1800846e6  xor     edx, edx; dwFlags
0x1800846e8  call    cs:__imp_BCryptFinalizeKeyPair
0x1800846ee  mov     r9d, eax
0x1800846f1  test    eax, eax
0x1800846f3  jns     short loc_180084720
0x1800846f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800846fc  lea     rax, WPP_GLOBAL_Control
0x180084703  cmp     rcx, rax
0x180084706  jz      loc_180084486
0x18008470c  test    byte ptr [rcx+1Ch], 1
0x180084710  jz      loc_180084486
0x180084716  mov     edx, 14h
0x18008471b  jmp     loc_180084568
0x180084720  xor     r12d, r12d
0x180084723  jmp     loc_1800844A0
```
