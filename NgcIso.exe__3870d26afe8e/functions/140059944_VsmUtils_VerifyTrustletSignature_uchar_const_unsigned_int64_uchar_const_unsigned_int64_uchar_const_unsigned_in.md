# VsmUtils::VerifyTrustletSignature(uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140059944`
- end: `0x140059deb`
- name: `?VerifyTrustletSignature@VsmUtils@@YAJPEBE_K0101PEA_K2@Z`
- size: `1191`
- prototype: `__int64 __fastcall(VsmUtils *__hidden this, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *, unsigned __int64, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003dee4`

## callees

- `0x140009be0`
- `0x140009fa0`
- `0x14000b658`
- `0x14000e034`
- `0x14000ee38`
- `0x14000f6a0`
- `0x1400104f0`
- `0x140010514`
- `0x14001b224`
- `0x14002bdcc`
- `0x1400530b0`
- `0x140059688`
- `0x140059944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059b3a`
- `IumSdk!RtlNtStatusToDosError` at `0x140059b47`
- `IumSdk!RtlNtStatusToDosError` at `0x140059b47`
- `IumSdk!GetSecureIdentitySigningKey` at `0x140059b21`
- `IumSdk!GetSecureIdentitySigningKey` at `0x140059b86`
- `IumSdk!GetSecureIdentitySigningKey` at `0x140059b21`
- `IumSdk!GetSecureIdentitySigningKey` at `0x140059b86`
- `bcrypt!BCryptImportKeyPair` at `0x140059c62`
- `bcrypt!BCryptImportKeyPair` at `0x140059c62`
- `bcrypt!BCryptVerifySignature` at `0x140059d5b`
- `bcrypt!BCryptVerifySignature` at `0x140059d5b`

## string_xrefs

- `0x140059a5e`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x140059b94`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x140059c13`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x140059c71`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x140059cbc`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`
- `0x140059db2`: `onecore\ds\security\trustlet\utils\vtl1\lib\signeddata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  char *v16; // rbx
  UCHAR *v17; // rsi
  ULONG cbInput; // ebx
  NTSTATUS v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  int pbInput; // [rsp+20h] [rbp-89h]
  int pbInputa; // [rsp+20h] [rbp-89h]
  int pbInputb; // [rsp+20h] [rbp-89h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-69h] BYREF
  char *v31; // [rsp+48h] [rbp-61h] BYREF
  _DWORD *v32; // [rsp+50h] [rbp-59h] BYREF
  void *v33; // [rsp+58h] [rbp-51h]
  __int64 v34; // [rsp+60h] [rbp-49h]
  _QWORD *v35; // [rsp+68h] [rbp-41h]
  _QWORD pPaddingInfo[2]; // [rsp+70h] [rbp-39h] BYREF
  _OWORD Buf2[2]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]

  v35 = a7;
  if ( (unsigned __int64)a6 <= 0x18 )
  {
    v8 = 137;
LABEL_66:
    LastError = -2147024809;
    goto LABEL_67;
  }
  if ( *(_QWORD *)a5 > (unsigned __int64)a6 )
  {
    v8 = 140;
    goto LABEL_66;
  }
  if ( (unsigned __int64)a6 <= 0x44 )
  {
    v8 = 142;
    goto LABEL_66;
  }
  if ( *(_DWORD *)(a5 + 24) != 1347570515 )
  {
    v8 = 144;
    goto LABEL_66;
  }
  v9 = *(unsigned int *)(a5 + 32);
  if ( v9 + 36 < (unsigned __int64)(v9 + 24) )
  {
    LastError = -2147024362;
    v8 = 152;
LABEL_67:
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
    goto LABEL_66;
  }
  if ( *(_DWORD *)(v9 + a5 + 24) < 0x15u || *(_DWORD *)(v9 + a5 + 28) != 1 || *(_DWORD *)(v9 + a5 + 32) != 1 )
  {
    v8 = 160;
    goto LABEL_66;
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
    goto LABEL_67;
  }
  if ( v9 + 45 >= (unsigned __int64)a6 )
  {
    v8 = 171;
    goto LABEL_66;
  }
  if ( *(_DWORD *)(v9 + a5 + 36) != 32780 || *(_DWORD *)(v9 + a5 + 40) != 32 )
  {
    v8 = 176;
    goto LABEL_66;
  }
  if ( *(_DWORD *)(v9 + a5 + 24) != *(unsigned int *)(v9 + a5 + 40) + 20LL )
  {
    v8 = 180;
    goto LABEL_66;
  }
  if ( memcmp_0((const void *)(v9 + a5 + 44), Buf2, 0x20u) )
  {
    LastError = -805305815;
    v8 = 183;
    goto LABEL_67;
  }
  v31 = 0;
  if ( (unsigned int)GetSecureIdentitySigningKey(0, &v31) )
  {
    LastError = -2147418113;
    v8 = 187;
    goto LABEL_67;
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
    goto LABEL_67;
  }
  std::vector<unsigned char>::vector<unsigned char>(&v32, v31);
  if ( (unsigned int)GetSecureIdentitySigningKey(v32, &v31) )
  {
    if ( (unsigned __int64)v31 >= (_BYTE *)v33 - (_BYTE *)v32 )
    {
      if ( (unsigned __int64)v31 > (_BYTE *)v33 - (_BYTE *)v32 )
      {
        if ( (unsigned __int64)v31 <= v34 - (__int64)v32 )
        {
          v16 = (char *)v32 + (_QWORD)v31;
          memset_0(v33, 0, (size_t)&v31[-((_BYTE *)v33 - (_BYTE *)v32)]);
          v33 = v16;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v32, v31);
        }
      }
    }
    else
    {
      v33 = &v31[(_QWORD)v32];
    }
    v17 = (UCHAR *)v32;
    if ( *v32 < 0x29u )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
        (const char *)0x80070057LL,
        pbInput);
      goto LABEL_63;
    }
    phKey = 0;
    cbInput = v32[2] - 8;
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v19 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0xE1, 0, L"RSAPUBLICBLOB", &phKey, v17 + 16, cbInput, 0);
    if ( v19 < 0 )
    {
      v20 = 207;
LABEL_47:
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)v20,
                    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
                    (const char *)(unsigned int)v19,
                    pbInputa);
LABEL_48:
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      goto LABEL_63;
    }
    v21 = anonymous_namespace_::HashData(0, 0, (PUCHAR)(a5 + 24), *(_DWORD *)(a5 + 28), (PUCHAR)Buf2);
    LastError = v21;
    if ( v21 >= 0 )
    {
      pPaddingInfo[0] = L"SHA256";
      pPaddingInfo[1] = 32;
      v24 = *(_QWORD *)(a5 + 8);
      v25 = v24 + 24;
      if ( v24 < 0xFFFFFFFFFFFFFFE8uLL )
      {
        v26 = v25 + *(_QWORD *)(a5 + 16);
        if ( v26 >= v25 )
        {
          if ( v26 <= (unsigned __int64)a6 )
          {
            v19 = BCryptVerifySignature(
                    phKey,
                    pPaddingInfo,
                    (PUCHAR)Buf2,
                    0x20u,
                    (PUCHAR)(v24 + a5 + 24),
                    *(_DWORD *)(a5 + 16),
                    8u);
            if ( v19 >= 0 )
            {
              *v35 = *(_QWORD *)(a5 + 52);
              if ( a8 )
                *a8 = *(_QWORD *)(a5 + 44);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
              LastError = 0;
              goto LABEL_63;
            }
            v20 = 233;
            goto LABEL_47;
          }
          LastError = -2147024809;
          v22 = 2147942487LL;
          v23 = 224;
        }
        else
        {
          LastError = -2147024362;
          v22 = 2147942934LL;
          v23 = 222;
        }
      }
      else
      {
        LastError = -2147024362;
        v22 = 2147942934LL;
        v23 = 219;
      }
    }
    else
    {
      v22 = (unsigned int)v21;
      v23 = 213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
      (const char *)v22,
      pbInputb);
    goto LABEL_48;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xC0,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\signeddata.cpp",
                v15);
LABEL_63:
  std::vector<unsigned char>::_Tidy(&v32);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140059944  mov     [rsp-8+arg_8], rbx
0x140059949  push    rbp
0x14005994a  push    rsi
0x14005994b  push    rdi
0x14005994c  push    r12
0x14005994e  push    r13
0x140059950  push    r14
0x140059952  push    r15
0x140059954  lea     rbp, [rsp-7]
0x140059959  sub     rsp, 0B0h
0x140059960  mov     rax, cs:__security_cookie
0x140059967  xor     rax, rsp
0x14005996a  mov     [rbp+37h+var_40], rax
0x14005996e  mov     r13, [rbp+37h+arg_20]
0x140059972  mov     rax, [rbp+37h+arg_30]
0x140059976  mov     [rbp+37h+var_78], rax
0x14005997a  mov     r12, [rbp+37h+arg_38]
0x14005997e  mov     r14, [rbp+37h+arg_28]
0x140059982  cmp     r14, 18h
0x140059986  ja      short loc_140059992
0x140059988  mov     edx, 89h
0x14005998d  jmp     loc_140059DAA
0x140059992  cmp     [r13+0], r14
0x140059996  jbe     short loc_1400599A2
0x140059998  mov     edx, 8Ch
0x14005999d  jmp     loc_140059DAA
0x1400599a2  cmp     r14, 44h ; 'D'
0x1400599a6  ja      short loc_1400599B2
0x1400599a8  mov     edx, 8Eh
0x1400599ad  jmp     loc_140059DAA
0x1400599b2  cmp     dword ptr [r13+18h], 50524B53h
0x1400599ba  jz      short loc_1400599C6
0x1400599bc  mov     edx, 90h
0x1400599c1  jmp     loc_140059DAA
0x1400599c6  mov     ebx, [r13+20h]
0x1400599ca  lea     rsi, [rbx+18h]
0x1400599ce  cmp     rsi, 18h
0x1400599d2  jnb     short loc_1400599E3
0x1400599d4  mov     ebx, 80070216h
0x1400599d9  mov     edx, 95h
0x1400599de  jmp     loc_140059DAF
0x1400599e3  lea     rax, [rsi+0Ch]
0x1400599e7  cmp     rax, rsi
0x1400599ea  jnb     short loc_1400599FB
0x1400599ec  mov     ebx, 80070216h
0x1400599f1  mov     edx, 98h
0x1400599f6  jmp     loc_140059DAF
0x1400599fb  cmp     rax, r14
0x1400599fe  jb      short loc_140059A0A
0x140059a00  mov     edx, 9Ah
0x140059a05  jmp     loc_140059DAA
0x140059a0a  cmp     dword ptr [rbx+r13+18h], 15h
0x140059a10  jb      loc_140059DA5
0x140059a16  cmp     dword ptr [rbx+r13+1Ch], 1
0x140059a1c  jnz     loc_140059DA5
0x140059a22  cmp     dword ptr [rbx+r13+20h], 1
0x140059a28  jnz     loc_140059DA5
0x140059a2e  xorps   xmm0, xmm0
0x140059a31  movups  [rbp+37h+Buf2], xmm0
0x140059a35  movups  [rbp+37h+var_50], xmm0
0x140059a39  lea     rax, [rbp+37h+Buf2]
0x140059a3d  mov     [rsp+0E0h+pbInput], rax; int
0x140059a42  mov     edx, 10h; cbInput
0x140059a47  lea     r9d, [rdx+10h]; ULONG
0x140059a4b  call    _anonymous_namespace___HashData
0x140059a50  mov     r15d, eax
0x140059a53  test    eax, eax
0x140059a55  jns     short loc_140059A77
0x140059a57  mov     rcx, [rbp+3Fh]; this
0x140059a5b  mov     r9d, eax; char *
0x140059a5e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059a65  mov     edx, 0A6h; void *
0x140059a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059a6f  mov     eax, r15d
0x140059a72  jmp     loc_140059DC4
0x140059a77  lea     rax, [rsi+15h]
0x140059a7b  cmp     rax, rsi
0x140059a7e  jnb     short loc_140059A8F
0x140059a80  mov     ebx, 80070216h
0x140059a85  mov     edx, 0A9h
0x140059a8a  jmp     loc_140059DAF
0x140059a8f  cmp     rax, r14
0x140059a92  jb      short loc_140059A9E
0x140059a94  mov     edx, 0ABh
0x140059a99  jmp     loc_140059DAA
0x140059a9e  cmp     dword ptr [rbx+r13+24h], 800Ch
0x140059aa7  jnz     loc_140059D9E
0x140059aad  cmp     dword ptr [rbx+r13+28h], 20h ; ' '
0x140059ab3  jnz     loc_140059D9E
0x140059ab9  mov     ecx, [rbx+r13+28h]
0x140059abe  add     rcx, 14h
0x140059ac2  cmp     rcx, 14h
0x140059ac6  jnb     short loc_140059AD7
0x140059ac8  mov     ebx, 80070216h
0x140059acd  mov     edx, 0B3h
0x140059ad2  jmp     loc_140059DAF
0x140059ad7  mov     eax, [rbx+r13+18h]
0x140059adc  cmp     rax, rcx
0x140059adf  jz      short loc_140059AEB
0x140059ae1  mov     edx, 0B4h
0x140059ae6  jmp     loc_140059DAA
0x140059aeb  lea     rcx, [r13+2Ch]
0x140059aef  add     rcx, rbx; Buf1
0x140059af2  mov     r8d, 20h ; ' '; Size
0x140059af8  lea     rdx, [rbp+37h+Buf2]; Buf2
0x140059afc  call    memcmp_0
0x140059b01  xor     r15d, r15d
0x140059b04  test    eax, eax
0x140059b06  jz      short loc_140059B17
0x140059b08  mov     ebx, 0D0000229h
0x140059b0d  mov     edx, 0B7h
0x140059b12  jmp     loc_140059DAF
0x140059b17  mov     [rbp+37h+var_98], r15
0x140059b1b  lea     rdx, [rbp+37h+var_98]
0x140059b1f  xor     ecx, ecx
0x140059b21  call    cs:__imp_GetSecureIdentitySigningKey
0x140059b27  test    eax, eax
0x140059b29  jz      short loc_140059B3A
0x140059b2b  mov     ebx, 8000FFFFh
0x140059b30  mov     edx, 0BBh
0x140059b35  jmp     loc_140059DAF
0x140059b3a  call    cs:__imp_GetLastError
0x140059b40  mov     ebx, eax
0x140059b42  mov     ecx, 0C0000023h; Status
0x140059b47  call    cs:__imp_RtlNtStatusToDosError
0x140059b4d  cmp     ebx, eax
0x140059b4f  jz      short loc_140059B70
0x140059b51  test    ebx, ebx
0x140059b53  jle     short loc_140059B60
0x140059b55  movzx   ebx, bx
0x140059b58  or      ebx, 80070000h
0x140059b5e  test    ebx, ebx
0x140059b60  jns     loc_140059DC2
0x140059b66  mov     edx, 0BDh
0x140059b6b  jmp     loc_140059DAF
0x140059b70  mov     rdx, [rbp+37h+var_98]
0x140059b74  lea     rcx, [rbp+37h+var_90]
0x140059b78  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140059b7d  nop
0x140059b7e  lea     rdx, [rbp+37h+var_98]
0x140059b82  mov     rcx, [rbp+37h+var_90]
0x140059b86  call    cs:__imp_GetSecureIdentitySigningKey
0x140059b8c  test    eax, eax
0x140059b8e  jnz     short loc_140059BAC
0x140059b90  mov     rcx, [rbp+3Fh]; this
0x140059b94  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059b9b  mov     edx, 0C0h; void *
0x140059ba0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140059ba5  mov     ebx, eax
0x140059ba7  jmp     loc_140059D93
0x140059bac  mov     r8, [rbp+37h+var_98]
0x140059bb0  mov     rdx, [rbp+37h+var_90]
0x140059bb4  mov     r9, [rbp+37h+var_88]
0x140059bb8  mov     rcx, r9
0x140059bbb  sub     rcx, rdx
0x140059bbe  cmp     r8, rcx
0x140059bc1  jnb     short loc_140059BCD
0x140059bc3  lea     rax, [rdx+r8]
0x140059bc7  mov     [rbp+37h+var_88], rax
0x140059bcb  jmp     short loc_140059BFE
0x140059bcd  jbe     short loc_140059BFE
0x140059bcf  mov     rax, [rbp+37h+var_80]
0x140059bd3  sub     rax, rdx
0x140059bd6  cmp     r8, rax
0x140059bd9  jbe     short loc_140059BE9
0x140059bdb  mov     rdx, r8
0x140059bde  lea     rcx, [rbp+37h+var_90]
0x140059be2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140059be7  jmp     short loc_140059BFE
0x140059be9  sub     r8, rcx; Size
0x140059bec  lea     rbx, [r8+r9]
0x140059bf0  xor     edx, edx; Val
0x140059bf2  mov     rcx, r9; void *
0x140059bf5  call    memset_0
0x140059bfa  mov     [rbp+37h+var_88], rbx
0x140059bfe  mov     rsi, [rbp+37h+var_90]
0x140059c02  cmp     dword ptr [rsi], 29h ; ')'
0x140059c05  jnb     short loc_140059C29
0x140059c07  mov     rcx, [rbp+3Fh]; this
0x140059c0b  mov     ebx, 80070057h
0x140059c10  mov     r9d, ebx; char *
0x140059c13  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059c1a  mov     edx, 0C5h; void *
0x140059c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059c24  jmp     loc_140059D93
0x140059c29  mov     [rbp+37h+phKey], r15
0x140059c2d  mov     ebx, [rsi+8]
0x140059c30  add     ebx, 0FFFFFFF8h
0x140059c33  xor     edx, edx
0x140059c35  lea     rcx, [rbp+37h+phKey]
0x140059c39  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140059c3e  lea     rax, [rsi+10h]
0x140059c42  mov     [rsp+0E0h+dwFlags], r15d; dwFlags
0x140059c47  mov     [rsp+0E0h+cbInput], ebx; cbInput
0x140059c4b  mov     [rsp+0E0h+pbInput], rax; int
0x140059c50  lea     r9, [rbp+37h+phKey]; phKey
0x140059c54  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x140059c5b  xor     edx, edx; hImportKey
0x140059c5d  mov     ecx, 0E1h; hAlgorithm
0x140059c62  call    cs:__imp_BCryptImportKeyPair
0x140059c68  test    eax, eax
0x140059c6a  jns     short loc_140059C94
0x140059c6c  mov     edx, 0CFh; void *
0x140059c71  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059c78  mov     r9d, eax; char *
0x140059c7b  mov     rcx, [rbp+3Fh]; this
0x140059c7f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140059c84  mov     ebx, eax
0x140059c86  lea     rcx, [rbp+37h+phKey]
0x140059c8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140059c8f  jmp     loc_140059D93
0x140059c94  mov     r9d, [r13+1Ch]; ULONG
0x140059c98  lea     rax, [rbp+37h+Buf2]
0x140059c9c  mov     [rsp+0E0h+pbInput], rax; int
0x140059ca1  lea     r8, [r13+18h]; PUCHAR
0x140059ca5  xor     edx, edx; cbInput
0x140059ca7  xor     ecx, ecx; pbInput
0x140059ca9  call    _anonymous_namespace___HashData
0x140059cae  mov     ebx, eax
0x140059cb0  test    eax, eax
0x140059cb2  jns     short loc_140059CCE
0x140059cb4  mov     r9d, eax; char *
0x140059cb7  mov     edx, 0D5h; void *
0x140059cbc  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059cc3  mov     rcx, [rbp+3Fh]; this
0x140059cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059ccc  jmp     short loc_140059C86
0x140059cce  lea     rax, aSha256; "SHA256"
0x140059cd5  mov     [rbp+37h+pPaddingInfo], rax
0x140059cd9  mov     [rbp+37h+var_68], 20h ; ' '
0x140059ce1  mov     r8, [r13+8]
0x140059ce5  lea     rcx, [r8+18h]
0x140059ce9  cmp     rcx, 18h
0x140059ced  jnb     short loc_140059CFE
0x140059cef  mov     ebx, 80070216h
0x140059cf4  mov     r9d, ebx
0x140059cf7  mov     edx, 0DBh
0x140059cfc  jmp     short loc_140059CBC
0x140059cfe  mov     rdx, [r13+10h]
0x140059d02  add     rdx, rcx
0x140059d05  cmp     rdx, rcx
0x140059d08  jnb     short loc_140059D19
0x140059d0a  mov     ebx, 80070216h
0x140059d0f  mov     r9d, ebx
0x140059d12  mov     edx, 0DEh
0x140059d17  jmp     short loc_140059CBC
0x140059d19  cmp     rdx, r14
0x140059d1c  jbe     short loc_140059D2D
0x140059d1e  mov     ebx, 80070057h
0x140059d23  mov     r9d, ebx
0x140059d26  mov     edx, 0E0h
0x140059d2b  jmp     short loc_140059CBC
0x140059d2d  lea     rdx, [r13+18h]
0x140059d31  add     rdx, r8
0x140059d34  mov     [rsp+0E0h+dwFlags], 8; dwFlags
0x140059d3c  mov     eax, [r13+10h]
0x140059d40  mov     [rsp+0E0h+cbInput], eax; cbSignature
0x140059d44  mov     [rsp+0E0h+pbInput], rdx; pbSignature
0x140059d49  mov     r9d, 20h ; ' '; cbHash
0x140059d4f  lea     r8, [rbp+37h+Buf2]; pbHash
0x140059d53  lea     rdx, [rbp+37h+pPaddingInfo]; pPaddingInfo
0x140059d57  mov     rcx, [rbp+37h+phKey]; hKey
0x140059d5b  call    cs:__imp_BCryptVerifySignature
0x140059d61  test    eax, eax
0x140059d63  jns     short loc_140059D6F
0x140059d65  mov     edx, 0E9h
0x140059d6a  jmp     loc_140059C71
0x140059d6f  mov     rax, [r13+34h]
0x140059d73  mov     rcx, [rbp+37h+var_78]
0x140059d77  mov     [rcx], rax
0x140059d7a  test    r12, r12
0x140059d7d  jz      short loc_140059D87
0x140059d7f  mov     rax, [r13+2Ch]
0x140059d83  mov     [r12], rax
0x140059d87  lea     rcx, [rbp+37h+phKey]
0x140059d8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140059d90  mov     ebx, r15d
0x140059d93  lea     rcx, [rbp+37h+var_90]
0x140059d97  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140059d9c  jmp     short loc_140059DC2
0x140059d9e  mov     edx, 0B0h
0x140059da3  jmp     short loc_140059DAA
0x140059da5  mov     edx, 0A0h; void *
0x140059daa  mov     ebx, 80070057h
0x140059daf  mov     r9d, ebx; char *
0x140059db2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x140059db9  mov     rcx, [rbp+3Fh]; this
0x140059dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140059dc2  mov     eax, ebx
0x140059dc4  mov     rcx, [rbp+37h+var_40]
0x140059dc8  xor     rcx, rsp; StackCookie
0x140059dcb  call    __security_check_cookie
0x140059dd0  mov     rbx, [rsp+0E0h+arg_8]
0x140059dd8  add     rsp, 0B0h
0x140059ddf  pop     r15
0x140059de1  pop     r14
0x140059de3  pop     r13
0x140059de5  pop     r12
0x140059de7  pop     rdi
0x140059de8  pop     rsi
  ... truncated ...
```
