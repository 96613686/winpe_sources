# KerbIumSignPkcsMessage

- ea: `0x140018880`
- end: `0x140018fe4`
- name: `KerbIumSignPkcsMessage`
- size: `1892`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, __int128 *, __int128 *, __int128 *, void *, __int128 *, unsigned int, __int64, char *, unsigned int, const unsigned __int8 *, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140004ca8`
- `0x1400066f0`
- `0x140006720`
- `0x14001212c`
- `0x140014f5c`
- `0x140018880`
- `0x140036f94`
- `0x140038cd2`
- `0x140038d10`
- `0x140038dd0`
- `0x14003a010`

## import_xrefs

- `iumcrypt!iumCryptMsgOpenToEncode` at `0x140018d35`
- `iumcrypt!iumCryptMsgOpenToEncode` at `0x140018d35`
- `iumcrypt!iumCryptMsgGetParam` at `0x140018dd6`
- `iumcrypt!iumCryptMsgGetParam` at `0x140018f03`
- `iumcrypt!iumCryptMsgGetParam` at `0x140018dd6`
- `iumcrypt!iumCryptMsgGetParam` at `0x140018f03`
- `iumcrypt!iumCryptMsgUpdate` at `0x140018d83`
- `iumcrypt!iumCryptMsgUpdate` at `0x140018d83`
- `iumcrypt!iumCryptMsgClose` at `0x140018e25`
- `iumcrypt!iumCryptMsgClose` at `0x140018e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018eb0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001890a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001890a`
- `bcrypt!BCryptDestroyKey` at `0x140018e67`
- `bcrypt!BCryptDestroyKey` at `0x140018e67`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140018af2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140018af2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140018e82`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140018e82`
- `bcrypt!BCryptImportKeyPair` at `0x140018b54`
- `bcrypt!BCryptImportKeyPair` at `0x140018b54`

## string_xrefs

- `0x140018937`: `KerbIumSignPkcsMessage`
- `0x140018a70`: `KerbIumSignPkcsMessage`
- `0x140018db0`: `KerbIumSignPkcsMessage`
- `0x140018f66`: `KerbIumSignPkcsMessage`
- `0x140018f9c`: `KerbIumSignPkcsMessage`

## pseudocode

```c
__int64 __fastcall KerbIumSignPkcsMessage(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6,
        __int128 *a7,
        __int128 *a8,
        void *a9,
        __int128 *a10,
        unsigned int a11,
        __int64 a12,
        char *a13,
        unsigned int a14,
        const unsigned __int8 *a15,
        unsigned int *a16,
        _QWORD *a17)
{
  int v22; // r13d
  NTSTATUS v23; // ebx
  PVOID *v24; // rcx
  __int64 v25; // rdx
  void **v26; // rdi
  __int128 v27; // xmm0
  __int128 v28; // xmm0
  unsigned __int64 v29; // rsi
  __int128 v30; // xmm0
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  _DWORD *v35; // rax
  unsigned int i; // edx
  __int64 v37; // rcx
  void *v38; // rax
  void *v39; // rdi
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  void *v42; // rax
  DWORD LastError; // eax
  __int64 v44; // [rsp+0h] [rbp-40h] BYREF
  void *v45; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v46; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp+10h] BYREF
  __int64 v48; // [rsp+58h] [rbp+18h]
  __int64 v49; // [rsp+60h] [rbp+20h]
  __int128 v50; // [rsp+68h] [rbp+28h] BYREF
  __int128 v51; // [rsp+78h] [rbp+38h]
  __int128 v52; // [rsp+88h] [rbp+48h]
  int v53; // [rsp+A0h] [rbp+60h] BYREF
  _BYTE *v54; // [rsp+A8h] [rbp+68h]
  BCRYPT_KEY_HANDLE phKey[10]; // [rsp+B0h] [rbp+70h] BYREF
  _BYTE v56[8]; // [rsp+100h] [rbp+C0h] BYREF
  __int128 v57; // [rsp+108h] [rbp+C8h]
  __int64 v58; // [rsp+118h] [rbp+D8h]
  __int128 v59; // [rsp+120h] [rbp+E0h]
  __int128 v60; // [rsp+130h] [rbp+F0h]
  __int64 v61; // [rsp+160h] [rbp+120h]
  __int128 v62; // [rsp+168h] [rbp+128h]
  __int128 v63; // [rsp+178h] [rbp+138h]
  __int64 v64; // [rsp+188h] [rbp+148h]

  v49 = a2;
  v46 = a3;
  v48 = a4;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  memset_0(&v53, 0, 0x60u);
  memset_0(v56, 0, 0xD0u);
  phAlgorithm = 0;
  v45 = 0;
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumSignPkcsMessage");
  if ( a16 )
    *a16 = 0;
  if ( a17 )
    *a17 = 0;
  if ( !a4 || !a3 || !a5 || !a6 || !a7 || !a8 || !a9 || !a10 || !a16 || !a17 || !a14 || !a15 || !a11 || !a12 || a2 == -1 )
    return 3221225485LL;
  v22 = 0;
  v23 = ValidateAuthPackBuffer(v49, a14, a15);
  if ( v23 < 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_74;
    v25 = 104;
    goto LABEL_29;
  }
  v23 = (*((__int64 (__fastcall **)(__int64, _QWORD, void **, _QWORD, _QWORD))LsaIsoFunctions + 3))(
          v48,
          v46,
          &v45,
          0,
          0);
  if ( v23 < 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_74;
    v25 = 105;
    goto LABEL_29;
  }
  v23 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)v45, L"Microsoft Primitive Provider", 0);
  if ( v23 < 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_74;
    v25 = 106;
    goto LABEL_29;
  }
  v23 = BCryptImportKeyPair(phAlgorithm, 0, *((LPCWSTR *)v45 + 1), phKey, *((PUCHAR *)v45 + 3), *((_DWORD *)v45 + 4), 0);
  if ( v23 < 0 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_74;
    v25 = 107;
    goto LABEL_29;
  }
  v58 = a5;
  v61 = a5;
  v26 = 0;
  v53 = 96;
  v27 = *a7;
  *(_QWORD *)&v50 = 0x100000030LL;
  v60 = v27;
  v28 = *a6;
  v57 = *a8;
  v29 = 16LL * a11;
  v64 = *((_QWORD *)a10 + 2);
  v59 = v28;
  v62 = v28;
  v30 = *a10;
  v54 = v56;
  phKey[2] = a9;
  *((_QWORD *)&v50 + 1) = &v53;
  v63 = v30;
  if ( !v29
    || v29 > g_ulMaxStackAllocSize
    || v29 + g_ulAdditionalProbeSize + 8 < v29
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_110;
  }
  v31 = v29 + 23;
  if ( v29 + 23 <= v29 + 8 )
    v31 = 0xFFFFFFFFFFFFFF0LL;
  v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
  v33 = alloca(v32);
  v34 = alloca(v32);
  v26 = &v45;
  if ( &v44 == (__int64 *)-64LL || (LODWORD(v45) = 1801679955, (v26 = (void **)&v46) == 0) )
  {
LABEL_110:
    if ( v29 + 8 >= v29 )
    {
      v35 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v26 = (void **)v35;
      if ( v35 )
      {
        *v35 = 1885431112;
        v26 = (void **)(v35 + 2);
      }
    }
  }
  *((_QWORD *)&v51 + 1) = v26;
  if ( !v26 )
  {
    v23 = -1073741801;
    goto LABEL_73;
  }
  for ( i = 0; i < a11; ++i )
  {
    v37 = i;
    *(_OWORD *)(*((_QWORD *)&v51 + 1) + 16 * v37) = *(_OWORD *)(a12 + 16 * v37);
  }
  LODWORD(v51) = a11;
  v38 = iumCryptMsgOpenToEncode(0x10001u, 0x40u, 2u, &v50, a13, 0);
  v39 = v38;
  if ( v38 )
  {
    if ( iumCryptMsgUpdate(v38, a15, a14, 1) )
    {
      if ( iumCryptMsgGetParam(v39, 2u, 0, 0, a16) )
      {
        v42 = MIDL_user_allocate(*a16);
        *a17 = v42;
        if ( !v42 )
        {
          v23 = -1073741801;
          goto LABEL_72;
        }
        if ( iumCryptMsgGetParam(v39, 2u, 0, v42, a16) )
          goto LABEL_72;
        v22 = 1;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_72;
        v41 = 111;
      }
      else
      {
        v22 = 1;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_72;
        v41 = 110;
      }
    }
    else
    {
      v22 = 1;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_72;
      v41 = 109;
    }
    WPP_SF_s(v40[2], v41, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids, "KerbIumSignPkcsMessage");
LABEL_72:
    iumCryptMsgClose(v39);
    goto LABEL_73;
  }
  v22 = 1;
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_74;
  v25 = 108;
LABEL_29:
  WPP_SF_s(v24[2], v25, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids, "KerbIumSignPkcsMessage");
LABEL_73:
  v24 = (PVOID *)WPP_GLOBAL_Control;
LABEL_74:
  if ( *((_QWORD *)&v51 + 1) && *(_DWORD *)(*((_QWORD *)&v51 + 1) - 8LL) == 1885431112 )
  {
    ((void (__fastcall *)(__int64))g_pfnFree)(*((_QWORD *)&v51 + 1) - 8LL);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( phKey[0] )
  {
    BCryptDestroyKey(phKey[0]);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v45 )
  {
    SafeAllocaFreeToHeap(v45);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v22 )
    goto LABEL_102;
  LastError = GetLastError();
  switch ( LastError )
  {
    case 0x8007000E:
      v23 = -1073741801;
      goto LABEL_99;
    case 0x80070057:
      goto LABEL_97;
    case 0x80091001:
      v23 = -1073741595;
      goto LABEL_99;
    case 0x80091002:
    case 0x80091003:
    case 0x80091004:
    case 0x80091005:
LABEL_97:
      v23 = -1073741811;
      goto LABEL_99;
  }
  v23 = -1073741715;
LABEL_99:
  v24 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumSignPkcsMessage",
      LastError);
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_102:
  if ( v23 < 0 && v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
    WPP_SF_sd(
      (unsigned int)v24[2],
      113,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumSignPkcsMessage",
      v23);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140018880  push    rbp
0x140018882  push    rbx
0x140018883  push    rsi
0x140018884  push    rdi
0x140018885  push    r12
0x140018887  push    r13
0x140018889  push    r14
0x14001888b  push    r15
0x14001888d  sub     rsp, 1E8h
0x140018894  lea     rbp, [rsp+40h]
0x140018899  mov     rax, cs:__security_cookie
0x1400188a0  xor     rax, rbp
0x1400188a3  mov     [rbp+1E0h+var_50], rax
0x1400188aa  xorps   xmm0, xmm0
0x1400188ad  mov     [rbp+1E0h+var_1C0], rdx
0x1400188b1  mov     r13, rdx
0x1400188b4  mov     [rbp+1E0h+var_1D8], r8d
0x1400188b8  xor     edx, edx; Val
0x1400188ba  mov     [rbp+1E0h+var_1C8], r9
0x1400188be  mov     esi, r8d
0x1400188c1  mov     rbx, rcx
0x1400188c4  lea     rcx, [rbp+1E0h+var_180]; void *
0x1400188c8  mov     rdi, r9
0x1400188cb  movups  [rbp+1E0h+var_1B8], xmm0
0x1400188cf  lea     r8d, [rdx+60h]; Size
0x1400188d3  movups  [rbp+1E0h+var_1A8], xmm0
0x1400188d7  movups  [rbp+1E0h+var_198], xmm0
0x1400188db  call    memset_0
0x1400188e0  xor     edx, edx; Val
0x1400188e2  lea     rcx, [rbp+1E0h+var_120]; void *
0x1400188e9  mov     r8d, 0D0h; Size
0x1400188ef  call    memset_0
0x1400188f4  xor     edx, edx
0x1400188f6  cmp     cs:qword_140052C40, rbx
0x1400188fd  mov     [rbp+1E0h+phAlgorithm], rdx
0x140018901  mov     [rbp+1E0h+var_1E0], rdx
0x140018905  jz      short loc_14001891A
0x140018907  lea     ecx, [rdx+5]; dwMilliseconds
0x14001890a  call    cs:__imp_Sleep
0x140018910  mov     eax, 0C0000022h
0x140018915  jmp     loc_140018FC1
0x14001891a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018921  lea     rax, WPP_GLOBAL_Control
0x140018928  cmp     rcx, rax
0x14001892b  jz      short loc_140018951
0x14001892d  test    byte ptr [rcx+1Ch], 4
0x140018931  jz      short loc_140018951
0x140018933  mov     rcx, [rcx+10h]
0x140018937  lea     r9, aKerbiumsignpkc; "KerbIumSignPkcsMessage"
0x14001893e  mov     edx, 67h ; 'g'
0x140018943  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x14001894a  call    WPP_SF_s
0x14001894f  xor     edx, edx
0x140018951  mov     r14, [rbp+1E0h+arg_78]
0x140018958  test    r14, r14
0x14001895b  jz      short loc_140018960
0x14001895d  mov     [r14], edx
0x140018960  mov     r12, [rbp+1E0h+arg_80]
0x140018967  test    r12, r12
0x14001896a  jz      short loc_140018970
0x14001896c  mov     [r12], rdx
0x140018970  test    rdi, rdi
0x140018973  jz      loc_140018FBC
0x140018979  test    esi, esi
0x14001897b  jz      loc_140018FBC
0x140018981  mov     rdi, [rbp+1E0h+arg_20]
0x140018988  test    rdi, rdi
0x14001898b  jz      loc_140018FBC
0x140018991  mov     rsi, [rbp+1E0h+arg_28]
0x140018998  test    rsi, rsi
0x14001899b  jz      loc_140018FBC
0x1400189a1  cmp     [rbp+1E0h+arg_30], rdx
0x1400189a8  jz      loc_140018FBC
0x1400189ae  cmp     [rbp+1E0h+arg_38], rdx
0x1400189b5  jz      loc_140018FBC
0x1400189bb  cmp     [rbp+1E0h+arg_40], rdx
0x1400189c2  jz      loc_140018FBC
0x1400189c8  cmp     [rbp+1E0h+arg_48], rdx
0x1400189cf  jz      loc_140018FBC
0x1400189d5  test    r14, r14
0x1400189d8  jz      loc_140018FBC
0x1400189de  test    r12, r12
0x1400189e1  jz      loc_140018FBC
0x1400189e7  mov     ecx, [rbp+1E0h+arg_68]
0x1400189ed  test    ecx, ecx
0x1400189ef  jz      loc_140018FBC
0x1400189f5  mov     rax, [rbp+1E0h+arg_70]
0x1400189fc  test    rax, rax
0x1400189ff  jz      loc_140018FBC
0x140018a05  mov     r15d, [rbp+1E0h+arg_50]
0x140018a0c  test    r15d, r15d
0x140018a0f  jz      loc_140018FBC
0x140018a15  cmp     [rbp+1E0h+arg_58], rdx
0x140018a1c  jz      loc_140018FBC
0x140018a22  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140018a26  jz      loc_140018FBC
0x140018a2c  mov     r13d, edx
0x140018a2f  mov     r8, rax
0x140018a32  mov     edx, ecx
0x140018a34  mov     rcx, [rbp+1E0h+var_1C0]
0x140018a38  call    ValidateAuthPackBuffer
0x140018a3d  mov     ebx, eax
0x140018a3f  test    eax, eax
0x140018a41  jns     short loc_140018A88
0x140018a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a4a  lea     r14, WPP_GLOBAL_Control
0x140018a51  cmp     rcx, r14
0x140018a54  jz      loc_140018E32
0x140018a5a  mov     esi, 1
0x140018a5f  test    [rcx+1Ch], sil
0x140018a63  jz      loc_140018E32
0x140018a69  lea     edx, [rsi+67h]
0x140018a6c  mov     rcx, [rcx+10h]
0x140018a70  lea     r9, aKerbiumsignpkc; "KerbIumSignPkcsMessage"
0x140018a77  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140018a7e  call    WPP_SF_s
0x140018a83  jmp     loc_140018E2B
0x140018a88  mov     rax, cs:?LsaIsoFunctions@@3PEBU_LsaIsoSupportFunctions@@EB; _LsaIsoSupportFunctions const * const LsaIsoFunctions
0x140018a8f  lea     r8, [rbp+1E0h+var_1E0]
0x140018a93  mov     edx, [rbp+1E0h+var_1D8]
0x140018a96  xor     r9d, r9d
0x140018a99  mov     rcx, [rbp+1E0h+var_1C8]
0x140018a9d  mov     [rsp+220h+pbInput], 0
0x140018aa6  mov     rax, [rax+18h]
0x140018aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018aaf  mov     ebx, eax
0x140018ab1  test    eax, eax
0x140018ab3  jns     short loc_140018ADD
0x140018ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x140018abc  lea     r14, WPP_GLOBAL_Control
0x140018ac3  cmp     rcx, r14
0x140018ac6  jz      loc_140018E32
0x140018acc  test    byte ptr [rcx+1Ch], 1
0x140018ad0  jz      loc_140018E32
0x140018ad6  mov     edx, 69h ; 'i'
0x140018adb  jmp     short loc_140018A6C
0x140018add  mov     rdx, [rbp+1E0h+var_1E0]
0x140018ae1  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140018ae8  xor     r9d, r9d; dwFlags
0x140018aeb  lea     rcx, [rbp+1E0h+phAlgorithm]; phAlgorithm
0x140018aef  mov     rdx, [rdx]; pszAlgId
0x140018af2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140018af8  mov     ebx, eax
0x140018afa  test    eax, eax
0x140018afc  jns     short loc_140018B29
0x140018afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b05  lea     r14, WPP_GLOBAL_Control
0x140018b0c  cmp     rcx, r14
0x140018b0f  jz      loc_140018E32
0x140018b15  test    byte ptr [rcx+1Ch], 1
0x140018b19  jz      loc_140018E32
0x140018b1f  mov     edx, 6Ah ; 'j'
0x140018b24  jmp     loc_140018A6C
0x140018b29  mov     r8, [rbp+1E0h+var_1E0]
0x140018b2d  lea     r9, [rbp+1E0h+phKey]; phKey
0x140018b31  mov     rcx, [rbp+1E0h+phAlgorithm]; hAlgorithm
0x140018b35  xor     edx, edx; hImportKey
0x140018b37  mov     [rsp+220h+dwFlags], 0; dwFlags
0x140018b3f  mov     eax, [r8+10h]
0x140018b43  mov     [rsp+220h+cbInput], eax; cbInput
0x140018b47  mov     rax, [r8+18h]
0x140018b4b  mov     r8, [r8+8]; pszBlobType
0x140018b4f  mov     [rsp+220h+pbInput], rax; pbInput
0x140018b54  call    cs:__imp_BCryptImportKeyPair
0x140018b5a  mov     ebx, eax
0x140018b5c  test    eax, eax
0x140018b5e  jns     short loc_140018B8B
0x140018b60  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b67  lea     r14, WPP_GLOBAL_Control
0x140018b6e  cmp     rcx, r14
0x140018b71  jz      loc_140018E32
0x140018b77  test    byte ptr [rcx+1Ch], 1
0x140018b7b  jz      loc_140018E32
0x140018b81  mov     edx, 6Bh ; 'k'
0x140018b86  jmp     loc_140018A6C
0x140018b8b  mov     rax, [rbp+1E0h+arg_30]
0x140018b92  mov     [rbp+1E0h+var_108], rdi
0x140018b99  mov     [rbp+1E0h+var_C0], rdi
0x140018ba0  xor     edi, edi
0x140018ba2  mov     [rbp+1E0h+var_180], 60h ; '`'
0x140018ba9  movups  xmm0, xmmword ptr [rax]
0x140018bac  mov     rax, [rbp+1E0h+arg_38]
0x140018bb3  mov     dword ptr [rbp+1E0h+var_1B8], 30h ; '0'
0x140018bba  movdqu  [rbp+1E0h+var_F0], xmm0
0x140018bc2  mov     dword ptr [rbp+1E0h+var_1B8+4], 1
0x140018bc9  movups  xmm1, xmmword ptr [rax]
0x140018bcc  mov     rax, [rbp+1E0h+arg_48]
0x140018bd3  movups  xmm0, xmmword ptr [rsi]
0x140018bd6  mov     rsi, r15
0x140018bd9  movdqu  [rbp+1E0h+var_118], xmm1
0x140018be1  shl     rsi, 4
0x140018be5  movsd   xmm1, qword ptr [rax+10h]
0x140018bea  movsd   [rbp+1E0h+var_98], xmm1
0x140018bf2  movdqu  [rbp+1E0h+var_100], xmm0
0x140018bfa  movdqu  [rbp+1E0h+var_B8], xmm0
0x140018c02  movups  xmm0, xmmword ptr [rax]
0x140018c05  lea     rax, [rbp+1E0h+var_120]
0x140018c0c  mov     [rbp+1E0h+var_178], rax
0x140018c10  mov     rax, [rbp+1E0h+arg_40]
0x140018c17  mov     [rbp+1E0h+var_160], rax
0x140018c1e  lea     rax, [rbp+1E0h+var_180]
0x140018c22  mov     qword ptr [rbp+1E0h+var_1B8+8], rax
0x140018c26  movups  [rbp+1E0h+var_A8], xmm0
0x140018c2d  test    rsi, rsi
0x140018c30  jz      short loc_140018C93
0x140018c32  cmp     rsi, cs:g_ulMaxStackAllocSize
0x140018c39  ja      short loc_140018C93
0x140018c3b  mov     rcx, cs:g_ulAdditionalProbeSize
0x140018c42  add     rcx, 8
0x140018c46  add     rcx, rsi
0x140018c49  cmp     rcx, rsi
0x140018c4c  jb      short loc_140018C93
0x140018c4e  call    VerifyStackAvailable
0x140018c53  test    eax, eax
0x140018c55  jz      short loc_140018C93
0x140018c57  lea     rax, [rsi+8]
0x140018c5b  lea     rcx, [rax+0Fh]
0x140018c5f  cmp     rcx, rax
0x140018c62  ja      short loc_140018C6E
0x140018c64  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140018c6e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140018c72  mov     rax, rcx
0x140018c75  call    _alloca_probe
0x140018c7a  sub     rsp, rcx
0x140018c7d  lea     rdi, [rsp+220h+var_1E0]
0x140018c82  test    rdi, rdi
0x140018c85  jz      short loc_140018C93
0x140018c87  mov     dword ptr [rdi], 6B637453h
0x140018c8d  add     rdi, 8
0x140018c91  jnz     short loc_140018CBA
0x140018c93  lea     rcx, [rsi+8]
0x140018c97  cmp     rcx, rsi
0x140018c9a  jb      short loc_140018CBA
0x140018c9c  mov     rax, cs:g_pfnAllocate
0x140018ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ca8  mov     rdi, rax
0x140018cab  test    rax, rax
0x140018cae  jz      short loc_140018CBA
0x140018cb0  mov     dword ptr [rax], 70616548h
0x140018cb6  add     rdi, 8
0x140018cba  mov     qword ptr [rbp+1E0h+var_1A8+8], rdi
0x140018cbe  test    rdi, rdi
0x140018cc1  jnz     short loc_140018CD4
0x140018cc3  mov     ebx, 0C0000017h
0x140018cc8  lea     r14, WPP_GLOBAL_Control
0x140018ccf  jmp     loc_140018E2B
0x140018cd4  xor     edx, edx
0x140018cd6  lea     esi, [rdx+1]
0x140018cd9  test    r15d, r15d
0x140018cdc  jz      short loc_140018D06
0x140018cde  mov     r14, [rbp+1E0h+arg_58]
0x140018ce5  mov     rax, qword ptr [rbp+1E0h+var_1A8+8]
0x140018ce9  mov     ecx, edx
0x140018ceb  add     edx, esi
0x140018ced  add     rcx, rcx
0x140018cf0  movups  xmm0, xmmword ptr [r14+rcx*8]
0x140018cf5  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x140018cfa  cmp     edx, r15d
0x140018cfd  jb      short loc_140018CE5
0x140018cff  mov     r14, [rbp+1E0h+arg_78]
0x140018d06  mov     rax, [rbp+1E0h+arg_60]
0x140018d0d  lea     r9, [rbp+1E0h+var_1B8]
0x140018d11  mov     dword ptr [rbp+1E0h+var_1A8], r15d
0x140018d15  mov     ecx, 10001h
0x140018d1a  mov     r15d, 2
0x140018d20  mov     qword ptr [rsp+220h+cbInput], 0
0x140018d29  mov     r8d, r15d
0x140018d2c  mov     [rsp+220h+pbInput], rax
0x140018d31  lea     edx, [r15+3Eh]
0x140018d35  call    cs:__imp_?iumCryptMsgOpenToEncode@@YAPEAXKKKPEBXPEADPEAU_CMSG_STREAM_INFO@@@Z; iumCryptMsgOpenToEncode(ulong,ulong,ulong,void const *,char *,_CMSG_STREAM_INFO *)
0x140018d3b  mov     rdi, rax
0x140018d3e  test    rax, rax
0x140018d41  jnz     short loc_140018D6F
0x140018d43  mov     r13d, esi
0x140018d46  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d4d  lea     r14, WPP_GLOBAL_Control
0x140018d54  cmp     rcx, r14
0x140018d57  jz      loc_140018E32
0x140018d5d  test    [rcx+1Ch], sil
0x140018d61  jz      loc_140018E32
0x140018d67  lea     edx, [rax+6Ch]
0x140018d6a  jmp     loc_140018A6C
0x140018d6f  mov     r8d, [rbp+1E0h+arg_68]
0x140018d76  mov     r9d, esi
0x140018d79  mov     rdx, [rbp+1E0h+arg_70]
0x140018d80  mov     rcx, rdi
0x140018d83  call    cs:__imp_?iumCryptMsgUpdate@@YAHPEAXPEBEKH@Z; iumCryptMsgUpdate(void *,uchar const *,ulong,int)
0x140018d89  test    eax, eax
0x140018d8b  jnz     short loc_140018DC5
0x140018d8d  mov     r13d, esi
0x140018d90  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d97  lea     r14, WPP_GLOBAL_Control
0x140018d9e  cmp     rcx, r14
0x140018da1  jz      short loc_140018E22
0x140018da3  test    [rcx+1Ch], sil
0x140018da7  jz      short loc_140018E22
0x140018da9  lea     edx, [rax+6Dh]
0x140018dac  mov     rcx, [rcx+10h]
0x140018db0  lea     r9, aKerbiumsignpkc; "KerbIumSignPkcsMessage"
0x140018db7  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
  ... truncated ...
```
