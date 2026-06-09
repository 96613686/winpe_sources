# VsmUtils::VerifyTrustletSignature(uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)

- ea: `0x14007efc0`
- end: `0x14007f484`
- name: `?VerifyTrustletSignature@VsmUtils@@YAJPEBE_K0101PEA_K2@Z`
- size: `1220`
- prototype: `__int64 __fastcall(UCHAR *this, const unsigned __int8 *, UCHAR *, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, _QWORD *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140040b94`

## callees

- `0x14000a420`
- `0x14000ae0c`
- `0x14001bd40`
- `0x14001cb6c`
- `0x14001cb90`
- `0x14002826c`
- `0x14002b430`
- `0x1400580e8`
- `0x1400589c4`
- `0x14005f5dc`
- `0x14007ecd8`
- `0x14007efc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007f1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007f1bc`
- `ntdll!RtlNtStatusToDosError` at `0x14007f1cf`
- `ntdll!RtlNtStatusToDosError` at `0x14007f1cf`
- `IumSdk!GetSecureIdentitySigningKey` at `0x14007f19d`
- `IumSdk!GetSecureIdentitySigningKey` at `0x14007f214`
- `IumSdk!GetSecureIdentitySigningKey` at `0x14007f19d`
- `IumSdk!GetSecureIdentitySigningKey` at `0x14007f214`
- `bcrypt!BCryptVerifySignature` at `0x14007f3ed`
- `bcrypt!BCryptVerifySignature` at `0x14007f3ed`
- `bcrypt!BCryptImportKeyPair` at `0x14007f2ee`
- `bcrypt!BCryptImportKeyPair` at `0x14007f2ee`

## string_xrefs

- `0x14007f0da`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x14007f228`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x14007f2a6`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x14007f303`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x14007f34e`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x14007f44a`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall VsmUtils::VerifyTrustletSignature(
        UCHAR *this,
        const unsigned __int8 *a2,
        UCHAR *a3,
        const unsigned __int8 *a4,
        unsigned __int64 a5,
        const unsigned __int8 *a6,
        _QWORD *a7,
        unsigned __int64 *a8)
{
  __int64 v8; // rdx
  __int64 v9; // rbx
  signed int LastError; // ebx
  int v11; // eax
  unsigned int v12; // r15d
  bool v14; // sf
  const char *v15; // r9
  char *v16; // rsi
  char *v17; // rax
  size_t v18; // rbx
  ULONG cbInput; // ecx
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  int pbInput; // [rsp+20h] [rbp-89h]
  int pbInputa; // [rsp+20h] [rbp-89h]
  int pbInputb; // [rsp+20h] [rbp-89h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-69h] BYREF
  char *v32; // [rsp+48h] [rbp-61h] BYREF
  __int64 v33; // [rsp+50h] [rbp-59h] BYREF
  void *v34; // [rsp+58h] [rbp-51h]
  __int64 v35; // [rsp+60h] [rbp-49h]
  _QWORD *v36; // [rsp+68h] [rbp-41h]
  _QWORD pPaddingInfo[2]; // [rsp+70h] [rbp-39h] BYREF
  _OWORD Buf2[2]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]

  v36 = a7;
  if ( (unsigned __int64)a6 <= 0x18 )
  {
    v8 = 137;
LABEL_67:
    LastError = -2147024809;
    goto LABEL_68;
  }
  if ( *(_QWORD *)a5 > (unsigned __int64)a6 )
  {
    v8 = 140;
    goto LABEL_67;
  }
  if ( (unsigned __int64)a6 <= 0x44 )
  {
    v8 = 142;
    goto LABEL_67;
  }
  if ( *(_DWORD *)(a5 + 24) != 1347570515 )
  {
    v8 = 144;
    goto LABEL_67;
  }
  v9 = *(unsigned int *)(a5 + 32);
  if ( v9 + 36 < (unsigned __int64)(v9 + 24) )
  {
    LastError = -2147024362;
    v8 = 152;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
      (const char *)(unsigned int)LastError,
      pbInput);
    return (unsigned int)LastError;
  }
  if ( v9 + 36 >= (unsigned __int64)a6 )
  {
    v8 = 154;
    goto LABEL_67;
  }
  if ( *(_DWORD *)(v9 + a5 + 24) < 0x15u || *(_DWORD *)(v9 + a5 + 28) != 1 || *(_DWORD *)(v9 + a5 + 32) != 1 )
  {
    v8 = 160;
    goto LABEL_67;
  }
  memset(Buf2, 0, sizeof(Buf2));
  v11 = anonymous_namespace_::HashData(this, 0x10u, a3, 0x20u, (PUCHAR)Buf2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
      (const char *)(unsigned int)v11,
      pbInput);
    return v12;
  }
  if ( v9 + 45 < (unsigned __int64)(v9 + 24) )
  {
    LastError = -2147024362;
    v8 = 169;
    goto LABEL_68;
  }
  if ( v9 + 45 >= (unsigned __int64)a6 )
  {
    v8 = 171;
    goto LABEL_67;
  }
  if ( *(_DWORD *)(v9 + a5 + 36) != 32780 || *(_DWORD *)(v9 + a5 + 40) != 32 )
  {
    v8 = 176;
    goto LABEL_67;
  }
  if ( *(_DWORD *)(v9 + a5 + 24) != *(unsigned int *)(v9 + a5 + 40) + 20LL )
  {
    v8 = 180;
    goto LABEL_67;
  }
  if ( memcmp_0((const void *)(v9 + a5 + 44), Buf2, 0x20u) )
  {
    LastError = -805305815;
    v8 = 183;
    goto LABEL_68;
  }
  v32 = 0;
  if ( (unsigned int)GetSecureIdentitySigningKey(0, &v32) )
  {
    LastError = -2147418113;
    v8 = 187;
    goto LABEL_68;
  }
  LastError = GetLastError();
  if ( LastError != RtlNtStatusToDosError(-1073741789) )
  {
    v14 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError < 0;
    }
    if ( !v14 )
      return (unsigned int)LastError;
    v8 = 189;
    goto LABEL_68;
  }
  std::vector<unsigned char>::vector<unsigned char>(&v33, v32);
  if ( (unsigned int)GetSecureIdentitySigningKey(v33, &v32) )
  {
    v16 = (char *)v34;
    if ( v32 >= (char *)v34 - v33 )
    {
      if ( v32 <= (char *)v34 - v33 )
        goto LABEL_44;
      if ( (unsigned __int64)v32 > v35 - v33 )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v33, v32);
        goto LABEL_44;
      }
      v18 = v32 - ((char *)v34 - v33);
      memset_0(v34, 0, v18);
      v17 = &v16[v18];
    }
    else
    {
      v17 = &v32[v33];
    }
    v34 = v17;
LABEL_44:
    if ( *(_DWORD *)v33 < 0x29u )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
        (const char *)0x80070057LL,
        pbInput);
      goto LABEL_64;
    }
    phKey = 0;
    cbInput = *(_DWORD *)(v33 + 8) - 8;
    phKey = 0;
    v20 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0xE1, 0, L"RSAPUBLICBLOB", &phKey, (PUCHAR)(v33 + 16), cbInput, 0);
    if ( v20 < 0 )
    {
      v21 = 207;
LABEL_48:
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)v21,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
                    (const char *)(unsigned int)v20,
                    pbInputa);
LABEL_49:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_64;
    }
    v22 = anonymous_namespace_::HashData(0, 0, (PUCHAR)(a5 + 24), *(_DWORD *)(a5 + 28), (PUCHAR)Buf2);
    LastError = v22;
    if ( v22 >= 0 )
    {
      pPaddingInfo[0] = L"SHA256";
      pPaddingInfo[1] = 32;
      v25 = *(_QWORD *)(a5 + 8);
      v26 = v25 + 24;
      if ( v25 < 0xFFFFFFFFFFFFFFE8uLL )
      {
        v27 = v26 + *(_QWORD *)(a5 + 16);
        if ( v27 >= v26 )
        {
          if ( v27 <= (unsigned __int64)a6 )
          {
            v20 = BCryptVerifySignature(
                    phKey,
                    pPaddingInfo,
                    (PUCHAR)Buf2,
                    0x20u,
                    (PUCHAR)(v25 + a5 + 24),
                    *(_DWORD *)(a5 + 16),
                    8u);
            if ( v20 >= 0 )
            {
              *v36 = *(_QWORD *)(a5 + 52);
              if ( a8 )
                *a8 = *(_QWORD *)(a5 + 44);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
              LastError = 0;
              goto LABEL_64;
            }
            v21 = 233;
            goto LABEL_48;
          }
          LastError = -2147024809;
          v23 = 2147942487LL;
          v24 = 224;
        }
        else
        {
          LastError = -2147024362;
          v23 = 2147942934LL;
          v24 = 222;
        }
      }
      else
      {
        LastError = -2147024362;
        v23 = 2147942934LL;
        v24 = 219;
      }
    }
    else
    {
      v23 = (unsigned int)v22;
      v24 = 213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
      (const char *)v23,
      pbInputb);
    goto LABEL_49;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xC0,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
                v15);
LABEL_64:
  std::vector<unsigned char>::_Tidy(&v33);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14007efc0  mov     [rsp-8+arg_8], rbx
0x14007efc5  push    rbp
0x14007efc6  push    rsi
0x14007efc7  push    rdi
0x14007efc8  push    r12
0x14007efca  push    r13
0x14007efcc  push    r14
0x14007efce  push    r15
0x14007efd0  lea     rbp, [rsp-7]
0x14007efd5  sub     rsp, 0B0h
0x14007efdc  mov     rax, cs:__security_cookie
0x14007efe3  xor     rax, rsp
0x14007efe6  mov     [rbp+37h+var_40], rax
0x14007efea  mov     r13, [rbp+37h+arg_20]
0x14007efee  mov     rax, [rbp+37h+arg_30]
0x14007eff2  mov     [rbp+37h+var_78], rax
0x14007eff6  mov     r12, [rbp+37h+arg_38]
0x14007effa  mov     r14, [rbp+37h+arg_28]
0x14007effe  cmp     r14, 18h
0x14007f002  ja      short loc_14007F00E
0x14007f004  mov     edx, 89h
0x14007f009  jmp     loc_14007F442
0x14007f00e  cmp     [r13+0], r14
0x14007f012  jbe     short loc_14007F01E
0x14007f014  mov     edx, 8Ch
0x14007f019  jmp     loc_14007F442
0x14007f01e  cmp     r14, 44h ; 'D'
0x14007f022  ja      short loc_14007F02E
0x14007f024  mov     edx, 8Eh
0x14007f029  jmp     loc_14007F442
0x14007f02e  cmp     dword ptr [r13+18h], 50524B53h
0x14007f036  jz      short loc_14007F042
0x14007f038  mov     edx, 90h
0x14007f03d  jmp     loc_14007F442
0x14007f042  mov     ebx, [r13+20h]
0x14007f046  lea     rsi, [rbx+18h]
0x14007f04a  cmp     rsi, 18h
0x14007f04e  jnb     short loc_14007F05F
0x14007f050  mov     ebx, 80070216h
0x14007f055  mov     edx, 95h
0x14007f05a  jmp     loc_14007F447
0x14007f05f  lea     rax, [rsi+0Ch]
0x14007f063  cmp     rax, rsi
0x14007f066  jnb     short loc_14007F077
0x14007f068  mov     ebx, 80070216h
0x14007f06d  mov     edx, 98h
0x14007f072  jmp     loc_14007F447
0x14007f077  cmp     rax, r14
0x14007f07a  jb      short loc_14007F086
0x14007f07c  mov     edx, 9Ah
0x14007f081  jmp     loc_14007F442
0x14007f086  cmp     dword ptr [rbx+r13+18h], 15h
0x14007f08c  jb      loc_14007F43D
0x14007f092  cmp     dword ptr [rbx+r13+1Ch], 1
0x14007f098  jnz     loc_14007F43D
0x14007f09e  cmp     dword ptr [rbx+r13+20h], 1
0x14007f0a4  jnz     loc_14007F43D
0x14007f0aa  xorps   xmm0, xmm0
0x14007f0ad  movups  [rbp+37h+Buf2], xmm0
0x14007f0b1  movups  [rbp+37h+var_50], xmm0
0x14007f0b5  lea     rax, [rbp+37h+Buf2]
0x14007f0b9  mov     [rsp+0E0h+pbInput], rax; int
0x14007f0be  mov     edx, 10h; cbInput
0x14007f0c3  lea     r9d, [rdx+10h]; ULONG
0x14007f0c7  call    _anonymous_namespace___HashData
0x14007f0cc  mov     r15d, eax
0x14007f0cf  test    eax, eax
0x14007f0d1  jns     short loc_14007F0F3
0x14007f0d3  mov     rcx, [rbp+3Fh]; this
0x14007f0d7  mov     r9d, eax; char *
0x14007f0da  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f0e1  mov     edx, 0A6h; void *
0x14007f0e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f0eb  mov     eax, r15d
0x14007f0ee  jmp     loc_14007F45C
0x14007f0f3  lea     rax, [rsi+15h]
0x14007f0f7  cmp     rax, rsi
0x14007f0fa  jnb     short loc_14007F10B
0x14007f0fc  mov     ebx, 80070216h
0x14007f101  mov     edx, 0A9h
0x14007f106  jmp     loc_14007F447
0x14007f10b  cmp     rax, r14
0x14007f10e  jb      short loc_14007F11A
0x14007f110  mov     edx, 0ABh
0x14007f115  jmp     loc_14007F442
0x14007f11a  cmp     dword ptr [rbx+r13+24h], 800Ch
0x14007f123  jnz     loc_14007F436
0x14007f129  cmp     dword ptr [rbx+r13+28h], 20h ; ' '
0x14007f12f  jnz     loc_14007F436
0x14007f135  mov     ecx, [rbx+r13+28h]
0x14007f13a  add     rcx, 14h
0x14007f13e  cmp     rcx, 14h
0x14007f142  jnb     short loc_14007F153
0x14007f144  mov     ebx, 80070216h
0x14007f149  mov     edx, 0B3h
0x14007f14e  jmp     loc_14007F447
0x14007f153  mov     eax, [rbx+r13+18h]
0x14007f158  cmp     rax, rcx
0x14007f15b  jz      short loc_14007F167
0x14007f15d  mov     edx, 0B4h
0x14007f162  jmp     loc_14007F442
0x14007f167  lea     rcx, [r13+2Ch]
0x14007f16b  add     rcx, rbx; Buf1
0x14007f16e  mov     r8d, 20h ; ' '; Size
0x14007f174  lea     rdx, [rbp+37h+Buf2]; Buf2
0x14007f178  call    memcmp_0
0x14007f17d  xor     r15d, r15d
0x14007f180  test    eax, eax
0x14007f182  jz      short loc_14007F193
0x14007f184  mov     ebx, 0D0000229h
0x14007f189  mov     edx, 0B7h
0x14007f18e  jmp     loc_14007F447
0x14007f193  mov     [rbp+37h+var_98], r15
0x14007f197  lea     rdx, [rbp+37h+var_98]
0x14007f19b  xor     ecx, ecx
0x14007f19d  call    cs:__imp_GetSecureIdentitySigningKey
0x14007f1a4  nop     dword ptr [rax+rax+00h]
0x14007f1a9  test    eax, eax
0x14007f1ab  jz      short loc_14007F1BC
0x14007f1ad  mov     ebx, 8000FFFFh
0x14007f1b2  mov     edx, 0BBh
0x14007f1b7  jmp     loc_14007F447
0x14007f1bc  call    cs:__imp_GetLastError
0x14007f1c3  nop     dword ptr [rax+rax+00h]
0x14007f1c8  mov     ebx, eax
0x14007f1ca  mov     ecx, 0C0000023h; Status
0x14007f1cf  call    cs:__imp_RtlNtStatusToDosError
0x14007f1d6  nop     dword ptr [rax+rax+00h]
0x14007f1db  cmp     ebx, eax
0x14007f1dd  jz      short loc_14007F1FE
0x14007f1df  test    ebx, ebx
0x14007f1e1  jle     short loc_14007F1EE
0x14007f1e3  movzx   ebx, bx
0x14007f1e6  or      ebx, 80070000h
0x14007f1ec  test    ebx, ebx
0x14007f1ee  jns     loc_14007F45A
0x14007f1f4  mov     edx, 0BDh
0x14007f1f9  jmp     loc_14007F447
0x14007f1fe  mov     rdx, [rbp+37h+var_98]
0x14007f202  lea     rcx, [rbp+37h+var_90]
0x14007f206  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x14007f20b  nop
0x14007f20c  lea     rdx, [rbp+37h+var_98]
0x14007f210  mov     rcx, [rbp+37h+var_90]
0x14007f214  call    cs:__imp_GetSecureIdentitySigningKey
0x14007f21b  nop     dword ptr [rax+rax+00h]
0x14007f220  test    eax, eax
0x14007f222  jnz     short loc_14007F240
0x14007f224  mov     rcx, [rbp+3Fh]; this
0x14007f228  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f22f  mov     edx, 0C0h; void *
0x14007f234  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007f239  mov     ebx, eax
0x14007f23b  jmp     loc_14007F42B
0x14007f240  mov     rbx, [rbp+37h+var_98]
0x14007f244  mov     rdx, [rbp+37h+var_90]
0x14007f248  mov     rsi, [rbp+37h+var_88]
0x14007f24c  mov     rcx, rsi
0x14007f24f  sub     rcx, rdx
0x14007f252  cmp     rbx, rcx
0x14007f255  jnb     short loc_14007F25D
0x14007f257  lea     rax, [rdx+rbx]
0x14007f25b  jmp     short loc_14007F28D
0x14007f25d  jbe     short loc_14007F291
0x14007f25f  mov     rax, [rbp+37h+var_80]
0x14007f263  sub     rax, rdx
0x14007f266  cmp     rbx, rax
0x14007f269  jbe     short loc_14007F279
0x14007f26b  mov     rdx, rbx
0x14007f26e  lea     rcx, [rbp+37h+var_90]
0x14007f272  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14007f277  jmp     short loc_14007F291
0x14007f279  sub     rbx, rcx
0x14007f27c  mov     r8, rbx; Size
0x14007f27f  xor     edx, edx; Val
0x14007f281  mov     rcx, rsi; void *
0x14007f284  call    memset_0
0x14007f289  lea     rax, [rbx+rsi]
0x14007f28d  mov     [rbp+37h+var_88], rax
0x14007f291  mov     rdx, [rbp+37h+var_90]
0x14007f295  cmp     dword ptr [rdx], 29h ; ')'
0x14007f298  jnb     short loc_14007F2BC
0x14007f29a  mov     rcx, [rbp+3Fh]; this
0x14007f29e  mov     ebx, 80070057h
0x14007f2a3  mov     r9d, ebx; char *
0x14007f2a6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f2ad  mov     edx, 0C5h; void *
0x14007f2b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f2b7  jmp     loc_14007F42B
0x14007f2bc  mov     [rbp+37h+phKey], r15
0x14007f2c0  mov     ecx, [rdx+8]
0x14007f2c3  add     ecx, 0FFFFFFF8h
0x14007f2c6  mov     [rbp+37h+phKey], r15
0x14007f2ca  lea     rax, [rdx+10h]
0x14007f2ce  mov     [rsp+0E0h+dwFlags], r15d; dwFlags
0x14007f2d3  mov     [rsp+0E0h+cbInput], ecx; cbInput
0x14007f2d7  mov     [rsp+0E0h+pbInput], rax; int
0x14007f2dc  lea     r9, [rbp+37h+phKey]; phKey
0x14007f2e0  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x14007f2e7  xor     edx, edx; hImportKey
0x14007f2e9  mov     ecx, 0E1h; hAlgorithm
0x14007f2ee  call    cs:__imp_BCryptImportKeyPair
0x14007f2f5  nop     dword ptr [rax+rax+00h]
0x14007f2fa  test    eax, eax
0x14007f2fc  jns     short loc_14007F326
0x14007f2fe  mov     edx, 0CFh; void *
0x14007f303  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f30a  mov     r9d, eax; char *
0x14007f30d  mov     rcx, [rbp+3Fh]; this
0x14007f311  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14007f316  mov     ebx, eax
0x14007f318  lea     rcx, [rbp+37h+phKey]
0x14007f31c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14007f321  jmp     loc_14007F42B
0x14007f326  mov     r9d, [r13+1Ch]; ULONG
0x14007f32a  lea     rax, [rbp+37h+Buf2]
0x14007f32e  mov     [rsp+0E0h+pbInput], rax; int
0x14007f333  lea     r8, [r13+18h]; PUCHAR
0x14007f337  xor     edx, edx; cbInput
0x14007f339  xor     ecx, ecx; pbInput
0x14007f33b  call    _anonymous_namespace___HashData
0x14007f340  mov     ebx, eax
0x14007f342  test    eax, eax
0x14007f344  jns     short loc_14007F360
0x14007f346  mov     r9d, eax; char *
0x14007f349  mov     edx, 0D5h; void *
0x14007f34e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f355  mov     rcx, [rbp+3Fh]; this
0x14007f359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f35e  jmp     short loc_14007F318
0x14007f360  lea     rax, pszAlgId; "SHA256"
0x14007f367  mov     [rbp+37h+pPaddingInfo], rax
0x14007f36b  mov     [rbp+37h+var_68], 20h ; ' '
0x14007f373  mov     r8, [r13+8]
0x14007f377  lea     rcx, [r8+18h]
0x14007f37b  cmp     rcx, 18h
0x14007f37f  jnb     short loc_14007F390
0x14007f381  mov     ebx, 80070216h
0x14007f386  mov     r9d, ebx
0x14007f389  mov     edx, 0DBh
0x14007f38e  jmp     short loc_14007F34E
0x14007f390  mov     rdx, [r13+10h]
0x14007f394  add     rdx, rcx
0x14007f397  cmp     rdx, rcx
0x14007f39a  jnb     short loc_14007F3AB
0x14007f39c  mov     ebx, 80070216h
0x14007f3a1  mov     r9d, ebx
0x14007f3a4  mov     edx, 0DEh
0x14007f3a9  jmp     short loc_14007F34E
0x14007f3ab  cmp     rdx, r14
0x14007f3ae  jbe     short loc_14007F3BF
0x14007f3b0  mov     ebx, 80070057h
0x14007f3b5  mov     r9d, ebx
0x14007f3b8  mov     edx, 0E0h
0x14007f3bd  jmp     short loc_14007F34E
0x14007f3bf  lea     rdx, [r13+18h]
0x14007f3c3  add     rdx, r8
0x14007f3c6  mov     [rsp+0E0h+dwFlags], 8; dwFlags
0x14007f3ce  mov     eax, [r13+10h]
0x14007f3d2  mov     [rsp+0E0h+cbInput], eax; cbSignature
0x14007f3d6  mov     [rsp+0E0h+pbInput], rdx; pbSignature
0x14007f3db  mov     r9d, 20h ; ' '; cbHash
0x14007f3e1  lea     r8, [rbp+37h+Buf2]; pbHash
0x14007f3e5  lea     rdx, [rbp+37h+pPaddingInfo]; pPaddingInfo
0x14007f3e9  mov     rcx, [rbp+37h+phKey]; hKey
0x14007f3ed  call    cs:__imp_BCryptVerifySignature
0x14007f3f4  nop     dword ptr [rax+rax+00h]
0x14007f3f9  test    eax, eax
0x14007f3fb  jns     short loc_14007F407
0x14007f3fd  mov     edx, 0E9h
0x14007f402  jmp     loc_14007F303
0x14007f407  mov     rax, [r13+34h]
0x14007f40b  mov     rcx, [rbp+37h+var_78]
0x14007f40f  mov     [rcx], rax
0x14007f412  test    r12, r12
0x14007f415  jz      short loc_14007F41F
0x14007f417  mov     rax, [r13+2Ch]
0x14007f41b  mov     [r12], rax
0x14007f41f  lea     rcx, [rbp+37h+phKey]
0x14007f423  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14007f428  mov     ebx, r15d
0x14007f42b  lea     rcx, [rbp+37h+var_90]
0x14007f42f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14007f434  jmp     short loc_14007F45A
0x14007f436  mov     edx, 0B0h
0x14007f43b  jmp     short loc_14007F442
0x14007f43d  mov     edx, 0A0h; void *
0x14007f442  mov     ebx, 80070057h
0x14007f447  mov     r9d, ebx; char *
0x14007f44a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\trustlet\\utils"...
0x14007f451  mov     rcx, [rbp+3Fh]; this
0x14007f455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007f45a  mov     eax, ebx
0x14007f45c  mov     rcx, [rbp+37h+var_40]
0x14007f460  xor     rcx, rsp; StackCookie
0x14007f463  call    __security_check_cookie
0x14007f468  mov     rbx, [rsp+0E0h+arg_8]
0x14007f470  add     rsp, 0B0h
0x14007f477  pop     r15
0x14007f479  pop     r14
  ... truncated ...
```
