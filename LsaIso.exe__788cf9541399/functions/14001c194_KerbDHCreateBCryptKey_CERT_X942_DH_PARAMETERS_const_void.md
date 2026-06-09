# KerbDHCreateBCryptKey(_CERT_X942_DH_PARAMETERS const &,void * *)

- ea: `0x14001c194`
- end: `0x14001c4a0`
- name: `?KerbDHCreateBCryptKey@@YAJAEBU_CERT_X942_DH_PARAMETERS@@PEAPEAX@Z`
- size: `780`
- prototype: `__int64 __fastcall(const struct _CERT_X942_DH_PARAMETERS *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14001d584`

## callees

- `0x14001193c`
- `0x140011964`
- `0x14001c194`
- `0x14001d484`
- `0x140036f94`
- `0x140038cd2`
- `0x140038d10`
- `0x140038dd0`
- `0x14003a010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x14001c423`
- `bcrypt!BCryptSetProperty` at `0x14001c423`
- `bcrypt!BCryptDestroyKey` at `0x14001c206`
- `bcrypt!BCryptDestroyKey` at `0x14001c206`
- `bcrypt!BCryptFinalizeKeyPair` at `0x14001c460`
- `bcrypt!BCryptFinalizeKeyPair` at `0x14001c460`
- `bcrypt!BCryptGenerateKeyPair` at `0x14001c2ad`
- `bcrypt!BCryptGenerateKeyPair` at `0x14001c2ad`

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
  _QWORD *v13; // rcx
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids);
    goto LABEL_5;
  }
  v8 = v6 & 0xFFFFFFF8;
  if ( (unsigned int)(8 * v8) < 0x400 )
  {
    v5 = 65;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_5;
    v14 = 18;
    goto LABEL_19;
  }
  v15 = (unsigned int)(2 * v8 + 12);
  if ( v15 > g_ulMaxStackAllocSize )
    goto LABEL_42;
  v16 = v15 + g_ulAdditionalProbeSize + 8;
  if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16, v10, v11, (unsigned int)KeyPair) )
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
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_5;
      v14 = 19;
LABEL_19:
      WPP_SF_d(v13[2], v14, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids, v12);
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
0x14001c194  push    rbp
0x14001c196  push    rbx
0x14001c197  push    rsi
0x14001c198  push    rdi
0x14001c199  push    r12
0x14001c19b  push    r13
0x14001c19d  push    r14
0x14001c19f  push    r15
0x14001c1a1  sub     rsp, 48h
0x14001c1a5  lea     rbp, [rsp+30h]
0x14001c1aa  mov     rax, cs:__security_cookie
0x14001c1b1  xor     rax, rbp
0x14001c1b4  mov     [rbp+50h+var_48], rax
0x14001c1b8  xor     esi, esi
0x14001c1ba  mov     r15, rdx
0x14001c1bd  mov     [rdx], rsi
0x14001c1c0  mov     r13, rcx
0x14001c1c3  mov     eax, [rcx]
0x14001c1c5  lea     r12d, [rsi+3Ch]
0x14001c1c9  lea     r14d, [rax+7]
0x14001c1cd  cmp     r14d, eax
0x14001c1d0  jnb     short loc_14001C250
0x14001c1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1d9  lea     rax, WPP_GLOBAL_Control
0x14001c1e0  cmp     rcx, rax
0x14001c1e3  jz      short loc_14001C1FE
0x14001c1e5  test    byte ptr [rcx+1Ch], 1
0x14001c1e9  jz      short loc_14001C1FE
0x14001c1eb  mov     rcx, [rcx+10h]
0x14001c1ef  lea     edx, [rsi+10h]
0x14001c1f2  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x14001c1f9  call    WPP_SF_
0x14001c1fe  mov     rcx, [r15]; hKey
0x14001c201  test    rcx, rcx
0x14001c204  jz      short loc_14001C213
0x14001c206  call    cs:__imp_BCryptDestroyKey
0x14001c20c  mov     qword ptr [r15], 0
0x14001c213  test    rsi, rsi
0x14001c216  jz      short loc_14001C230
0x14001c218  lea     rcx, [rsi-8]
0x14001c21c  cmp     dword ptr [rcx], 70616548h
0x14001c222  jnz     short loc_14001C230
0x14001c224  mov     rax, cs:g_pfnFree
0x14001c22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c230  mov     eax, r12d
0x14001c233  mov     rcx, [rbp+50h+var_48]
0x14001c237  xor     rcx, rbp; StackCookie
0x14001c23a  call    __security_check_cookie
0x14001c23f  lea     rsp, [rbp+18h]
0x14001c243  pop     r15
0x14001c245  pop     r14
0x14001c247  pop     r13
0x14001c249  pop     r12
0x14001c24b  pop     rdi
0x14001c24c  pop     rsi
0x14001c24d  pop     rbx
0x14001c24e  pop     rbp
0x14001c24f  retn
0x14001c250  and     r14d, 0FFFFFFF8h
0x14001c254  lea     r8d, ds:0[r14*8]; dwLength
0x14001c25c  cmp     r8d, 400h
0x14001c263  jnb     short loc_14001C2A5
0x14001c265  mov     r12d, 41h ; 'A'
0x14001c26b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c272  lea     rax, WPP_GLOBAL_Control
0x14001c279  cmp     rcx, rax
0x14001c27c  jz      short loc_14001C1FE
0x14001c27e  test    byte ptr [rcx+1Ch], 1
0x14001c282  jz      loc_14001C1FE
0x14001c288  mov     rcx, [rcx+10h]
0x14001c28c  lea     edx, [r12-30h]
0x14001c291  mov     r9d, r14d
0x14001c294  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x14001c29b  call    WPP_SF_d
0x14001c2a0  jmp     loc_14001C1FE
0x14001c2a5  xor     r9d, r9d; dwFlags
0x14001c2a8  mov     ecx, 281h; hAlgorithm
0x14001c2ad  call    cs:__imp_BCryptGenerateKeyPair
0x14001c2b3  mov     r9d, eax
0x14001c2b6  test    eax, eax
0x14001c2b8  jns     short loc_14001C2F5
0x14001c2ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2c1  lea     rax, WPP_GLOBAL_Control
0x14001c2c8  cmp     rcx, rax
0x14001c2cb  jz      loc_14001C1FE
0x14001c2d1  test    byte ptr [rcx+1Ch], 1
0x14001c2d5  jz      loc_14001C1FE
0x14001c2db  mov     edx, 12h
0x14001c2e0  mov     rcx, [rcx+10h]
0x14001c2e4  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x14001c2eb  call    WPP_SF_d
0x14001c2f0  jmp     loc_14001C1FE
0x14001c2f5  lea     edi, ds:0Ch[r14*2]
0x14001c2fd  mov     ebx, edi
0x14001c2ff  cmp     rbx, cs:g_ulMaxStackAllocSize
0x14001c306  ja      short loc_14001C360
0x14001c308  mov     rcx, cs:g_ulAdditionalProbeSize
0x14001c30f  add     rcx, 8
0x14001c313  add     rcx, rbx
0x14001c316  cmp     rcx, rbx
0x14001c319  jb      short loc_14001C360
0x14001c31b  call    VerifyStackAvailable
0x14001c320  test    eax, eax
0x14001c322  jz      short loc_14001C360
0x14001c324  lea     rax, [rdi+8]
0x14001c328  lea     rcx, [rax+0Fh]
0x14001c32c  cmp     rcx, rax
0x14001c32f  ja      short loc_14001C33B
0x14001c331  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14001c33b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001c33f  mov     rax, rcx
0x14001c342  call    _alloca_probe
0x14001c347  sub     rsp, rcx
0x14001c34a  lea     rsi, [rsp+80h+var_50]
0x14001c34f  test    rsi, rsi
0x14001c352  jz      short loc_14001C360
0x14001c354  mov     dword ptr [rsi], 6B637453h
0x14001c35a  add     rsi, 8
0x14001c35e  jnz     short loc_14001C387
0x14001c360  lea     rcx, [rdi+8]
0x14001c364  cmp     rcx, rbx
0x14001c367  jb      short loc_14001C387
0x14001c369  mov     rax, cs:g_pfnAllocate
0x14001c370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c375  mov     rsi, rax
0x14001c378  test    rax, rax
0x14001c37b  jz      short loc_14001C387
0x14001c37d  mov     dword ptr [rax], 70616548h
0x14001c383  add     rsi, 8
0x14001c387  test    rsi, rsi
0x14001c38a  jz      loc_14001C1FE
0x14001c390  mov     r8, rbx; Size
0x14001c393  xor     edx, edx; Val
0x14001c395  mov     rcx, rsi; void *
0x14001c398  call    memset_0
0x14001c39d  mov     eax, r14d
0x14001c3a0  mov     [rsi], edi
0x14001c3a2  mov     [rsi+8], r14d
0x14001c3a6  lea     rcx, [rsi+0Ch]; void *
0x14001c3aa  mov     dword ptr [rsi+4], 4D504844h
0x14001c3b1  xor     edx, edx; Val
0x14001c3b3  sub     eax, [r13+0]
0x14001c3b7  mov     r8d, eax; Size
0x14001c3ba  mov     ebx, eax
0x14001c3bc  call    memset_0
0x14001c3c1  mov     rdx, [r13+8]
0x14001c3c5  lea     rcx, [rbx+0Ch]
0x14001c3c9  mov     r8d, [r13+0]
0x14001c3cd  add     rcx, rsi
0x14001c3d0  call    ReverseMemCpy
0x14001c3d5  mov     eax, r14d
0x14001c3d8  lea     rcx, [r14+0Ch]
0x14001c3dc  sub     eax, [r13+10h]
0x14001c3e0  add     rcx, rsi; void *
0x14001c3e3  mov     r8d, eax; Size
0x14001c3e6  xor     edx, edx; Val
0x14001c3e8  mov     edi, eax
0x14001c3ea  call    memset_0
0x14001c3ef  mov     rdx, [r13+18h]
0x14001c3f3  lea     rcx, [r14+0Ch]
0x14001c3f7  mov     r8d, [r13+10h]
0x14001c3fb  add     rcx, rdi
0x14001c3fe  add     rcx, rsi
0x14001c401  call    ReverseMemCpy
0x14001c406  mov     rcx, [r15]; hObject
0x14001c409  lea     r9d, ds:0Ch[r14*2]; cbInput
0x14001c411  mov     r8, rsi; pbInput
0x14001c414  mov     [rsp+80h+dwFlags], 0; dwFlags
0x14001c41c  lea     rdx, aDhparameters; "DHParameters"
0x14001c423  call    cs:__imp_BCryptSetProperty
0x14001c429  mov     r9d, eax
0x14001c42c  test    eax, eax
0x14001c42e  jns     short loc_14001C45B
0x14001c430  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c437  lea     rax, WPP_GLOBAL_Control
0x14001c43e  cmp     rcx, rax
0x14001c441  jz      loc_14001C1FE
0x14001c447  test    byte ptr [rcx+1Ch], 1
0x14001c44b  jz      loc_14001C1FE
0x14001c451  mov     edx, 13h
0x14001c456  jmp     loc_14001C2E0
0x14001c45b  mov     rcx, [r15]; hKey
0x14001c45e  xor     edx, edx; dwFlags
0x14001c460  call    cs:__imp_BCryptFinalizeKeyPair
0x14001c466  mov     r9d, eax
0x14001c469  test    eax, eax
0x14001c46b  jns     short loc_14001C498
0x14001c46d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c474  lea     rax, WPP_GLOBAL_Control
0x14001c47b  cmp     rcx, rax
0x14001c47e  jz      loc_14001C1FE
0x14001c484  test    byte ptr [rcx+1Ch], 1
0x14001c488  jz      loc_14001C1FE
0x14001c48e  mov     edx, 14h
0x14001c493  jmp     loc_14001C2E0
0x14001c498  xor     r12d, r12d
0x14001c49b  jmp     loc_14001C218
```
