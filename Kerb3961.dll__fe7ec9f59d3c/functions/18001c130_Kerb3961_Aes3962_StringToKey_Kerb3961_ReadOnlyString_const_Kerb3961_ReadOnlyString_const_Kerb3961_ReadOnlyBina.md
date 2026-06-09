# Kerb3961::Aes3962::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001c130`
- end: `0x18001c38f`
- name: `?StringToKey@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000901c`
- `0x18000ec30`
- `0x18001a538`
- `0x18001c130`

## import_xrefs

- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x18001c2fc`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x18001c2fc`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::StringToKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // r10
  char *v9; // rcx
  unsigned __int32 v10; // esi
  const char *v11; // rdx
  int v12; // r8d
  int v13; // r14d
  PUCHAR v14; // rcx
  const char *v15; // rdx
  int v16; // r8d
  int v17; // r14d
  ULONG cbSalt; // r12d
  int v19; // r8d
  int v20; // r14d
  PUCHAR v21; // rcx
  PUCHAR v22; // r14
  ULONGLONG cIterations; // rcx
  PUCHAR v24; // rsi
  NTSTATUS v25; // eax
  int v26; // r8d
  NTSTATUS v27; // r12d
  ULONG cbPassword[2]; // [rsp+50h] [rbp-41h] BYREF
  PUCHAR pbPassword; // [rsp+58h] [rbp-39h]
  char *v31; // [rsp+60h] [rbp-31h]
  ULONG cbDerivedKey; // [rsp+68h] [rbp-29h] BYREF
  PUCHAR pbDerivedKey; // [rsp+70h] [rbp-21h]
  char *v34; // [rsp+78h] [rbp-19h]
  ULONG v35[2]; // [rsp+80h] [rbp-11h] BYREF
  PUCHAR pbSalt; // [rsp+88h] [rbp-9h]
  char *v37; // [rsp+90h] [rbp-1h]

  v6 = a3;
  if ( *(_QWORD *)a5 != 4 )
  {
    v9 = "stringToKeyParameters.length == sizeof(uint32_t)";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v9, (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  v10 = _byteswap_ulong(**(_DWORD **)(a5 + 8));
  if ( v10 > *(_DWORD *)(a1 + 156) )
  {
    v9 = "iterations <= m_maxIterationCount";
    goto LABEL_3;
  }
  if ( v10 < *(_DWORD *)(a1 + 160) )
  {
    v9 = "iterations >= m_minIterationCount";
    goto LABEL_3;
  }
  LOBYTE(a3) = 1;
  Kerb3961::ConvertToUTF8(cbPassword, v6, a3);
  v13 = (int)v31;
  if ( (int)v31 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"passwordUTF8",
      (const char *)(unsigned int)v31,
      v12);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v13;
    goto LABEL_10;
  }
  if ( *(_QWORD *)cbPassword > 0xFFFFFFFF )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"passwordUTF8.length <= utl::numeric_limits<uint32_t>::max()",
      v11);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    goto LABEL_10;
  }
  Kerb3961::ConvertToUTF8(v35, a4, 0);
  v17 = (int)v37;
  if ( (int)v37 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"saltUTF8",
      (const char *)(unsigned int)v37,
      v16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v17;
    goto LABEL_16;
  }
  cbSalt = v35[0];
  if ( *(_QWORD *)v35 > 0xFFFFFFFF )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"saltUTF8.length <= utl::numeric_limits<uint32_t>::max()",
      v15);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
LABEL_16:
    if ( pbSalt )
      operator delete(pbSalt, 0);
LABEL_10:
    v14 = pbPassword;
    if ( !pbPassword )
      return a2;
LABEL_32:
    operator delete(v14, 0);
    return a2;
  }
  Kerb3961::MakeBuffer(&cbDerivedKey);
  v20 = (int)v34;
  if ( (int)v34 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"tkey", (const char *)(unsigned int)v34, v19);
    v21 = pbDerivedKey;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v20;
    if ( v21 )
      operator delete(v21, 0);
    goto LABEL_16;
  }
  v22 = pbSalt;
  cIterations = v10;
  v24 = pbPassword;
  v25 = BCryptDeriveKeyPBKDF2(
          *(BCRYPT_ALG_HANDLE *)(a1 + 184),
          pbPassword,
          cbPassword[0],
          pbSalt,
          cbSalt,
          cIterations,
          pbDerivedKey,
          cbDerivedKey,
          0);
  v27 = v25;
  if ( v25 >= 0 )
  {
    *(_QWORD *)cbPassword = 8;
    pbPassword = (PUCHAR)"kerberos";
    Kerb3961::Aes3962::DeriveKey(a1, a2, (__int64)&cbDerivedKey, (size_t *)cbPassword);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"BCryptDeriveKeyPBKDF2(m_checksumHandle, passwordUTF8.buffer, static_cast<uint32_t>(pa"
                                   "sswordUTF8.length), saltUTF8.buffer, static_cast<uint32_t>(saltUTF8.length), iteratio"
                                   "ns, tkey.buffer, static_cast<uint32_t>(tkey.length), 0)",
      (const char *)(unsigned int)v25,
      v26);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v27;
  }
  if ( pbDerivedKey )
    operator delete(pbDerivedKey, 0);
  if ( v22 )
    operator delete(v22, 0);
  if ( v24 )
  {
    v14 = v24;
    goto LABEL_32;
  }
  return a2;
}

```

## disassembly

```asm
0x18001c130  push    rbp
0x18001c132  push    rbx
0x18001c133  push    rsi
0x18001c134  push    rdi
0x18001c135  push    r12
0x18001c137  push    r13
0x18001c139  push    r14
0x18001c13b  push    r15
0x18001c13d  lea     rbp, [rsp-17h]
0x18001c142  sub     rsp, 0A8h
0x18001c149  mov     rax, [rbp+4Fh+arg_20]
0x18001c14d  mov     r12, r9
0x18001c150  mov     r10, r8
0x18001c153  mov     rdi, rdx
0x18001c156  mov     r15, rcx
0x18001c159  cmp     qword ptr [rax], 4
0x18001c15d  jz      short loc_18001C180
0x18001c15f  lea     rcx, aStringtokeypar; "stringToKeyParameters.length == sizeof("...
0x18001c166  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001c16b  xor     ebx, ebx
0x18001c16d  mov     [rdi], rbx
0x18001c170  mov     [rdi+8], rbx
0x18001c174  mov     dword ptr [rdi+10h], 0C000000Dh
0x18001c17b  jmp     loc_18001C378
0x18001c180  mov     rax, [rax+8]
0x18001c184  mov     esi, [rax]
0x18001c186  bswap   esi
0x18001c188  cmp     esi, [rcx+9Ch]
0x18001c18e  jbe     short loc_18001C199
0x18001c190  lea     rcx, aIterationsMMax; "iterations <= m_maxIterationCount"
0x18001c197  jmp     short loc_18001C166
0x18001c199  cmp     esi, [rcx+0A0h]
0x18001c19f  jnb     short loc_18001C1AA
0x18001c1a1  lea     rcx, aIterationsMMin; "iterations >= m_minIterationCount"
0x18001c1a8  jmp     short loc_18001C166
0x18001c1aa  mov     r8b, 1
0x18001c1ad  lea     rcx, [rbp+4Fh+cbPassword]
0x18001c1b1  mov     rdx, r10
0x18001c1b4  call    ?ConvertToUTF8@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyString@1@_N@Z; Kerb3961::ConvertToUTF8(Kerb3961::ReadOnlyString const &,bool)
0x18001c1b9  mov     r14d, dword ptr [rbp+4Fh+var_80]
0x18001c1bd  xor     ebx, ebx
0x18001c1bf  test    r14d, r14d
0x18001c1c2  jns     short loc_18001C1F0
0x18001c1c4  mov     edx, r14d; char *
0x18001c1c7  lea     rcx, aPasswordutf8; "passwordUTF8"
0x18001c1ce  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c1d3  mov     [rdi], rbx
0x18001c1d6  mov     [rdi+8], rbx
0x18001c1da  mov     [rdi+10h], r14d
0x18001c1de  mov     rcx, [rbp+4Fh+pbPassword]
0x18001c1e2  test    rcx, rcx
0x18001c1e5  jz      loc_18001C378
0x18001c1eb  jmp     loc_18001C371
0x18001c1f0  mov     r13d, 0FFFFFFFFh
0x18001c1f6  cmp     qword ptr [rbp+4Fh+cbPassword], r13
0x18001c1fa  jbe     short loc_18001C218
0x18001c1fc  lea     rcx, aPasswordutf8Le; "passwordUTF8.length <= utl::numeric_lim"...
0x18001c203  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001c208  mov     [rdi], rbx
0x18001c20b  mov     [rdi+8], rbx
0x18001c20f  mov     dword ptr [rdi+10h], 0C0000095h
0x18001c216  jmp     short loc_18001C1DE
0x18001c218  xor     r8d, r8d
0x18001c21b  lea     rcx, [rbp+4Fh+var_60]
0x18001c21f  mov     rdx, r12
0x18001c222  call    ?ConvertToUTF8@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyString@1@_N@Z; Kerb3961::ConvertToUTF8(Kerb3961::ReadOnlyString const &,bool)
0x18001c227  mov     r14d, dword ptr [rbp+4Fh+var_50]
0x18001c22b  test    r14d, r14d
0x18001c22e  jns     short loc_18001C25C
0x18001c230  mov     edx, r14d; char *
0x18001c233  lea     rcx, aSaltutf8; "saltUTF8"
0x18001c23a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c23f  mov     [rdi], rbx
0x18001c242  mov     [rdi+8], rbx
0x18001c246  mov     [rdi+10h], r14d
0x18001c24a  mov     rcx, [rbp+4Fh+pbSalt]; void *
0x18001c24e  test    rcx, rcx
0x18001c251  jz      short loc_18001C1DE
0x18001c253  xor     edx, edx; struct std::nothrow_t *
0x18001c255  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c25a  jmp     short loc_18001C1DE
0x18001c25c  mov     r12, qword ptr [rbp+4Fh+var_60]
0x18001c260  cmp     r12, r13
0x18001c263  jbe     short loc_18001C281
0x18001c265  lea     rcx, aSaltutf8Length; "saltUTF8.length <= utl::numeric_limits<"...
0x18001c26c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001c271  mov     [rdi], rbx
0x18001c274  mov     [rdi+8], rbx
0x18001c278  mov     dword ptr [rdi+10h], 0C0000095h
0x18001c27f  jmp     short loc_18001C24A
0x18001c281  mov     rdx, [r15+68h]
0x18001c285  lea     rcx, [rbp+4Fh+var_78]
0x18001c289  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001c28e  mov     r14d, dword ptr [rbp+4Fh+var_68]
0x18001c292  test    r14d, r14d
0x18001c295  jns     short loc_18001C2C3
0x18001c297  mov     edx, r14d; char *
0x18001c29a  lea     rcx, aTkey; "tkey"
0x18001c2a1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c2a6  mov     rcx, [rbp+4Fh+var_70]; void *
0x18001c2aa  mov     [rdi], rbx
0x18001c2ad  mov     [rdi+8], rbx
0x18001c2b1  mov     [rdi+10h], r14d
0x18001c2b5  test    rcx, rcx
0x18001c2b8  jz      short loc_18001C24A
0x18001c2ba  xor     edx, edx; struct std::nothrow_t *
0x18001c2bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c2c1  jmp     short loc_18001C24A
0x18001c2c3  mov     eax, [rbp+4Fh+var_78]
0x18001c2c6  mov     r14, [rbp+4Fh+pbSalt]
0x18001c2ca  mov     r8d, [rbp+4Fh+cbPassword]; cbPassword
0x18001c2ce  mov     r9, r14; pbSalt
0x18001c2d1  mov     [rsp+0E0h+dwFlags], ebx; dwFlags
0x18001c2d5  mov     [rsp+0E0h+cbDerivedKey], eax; cbDerivedKey
0x18001c2d9  mov     rax, [rbp+4Fh+var_70]
0x18001c2dd  mov     ecx, esi
0x18001c2df  mov     rsi, [rbp+4Fh+pbPassword]
0x18001c2e3  mov     [rsp+0E0h+pbDerivedKey], rax; pbDerivedKey
0x18001c2e8  mov     rdx, rsi; pbPassword
0x18001c2eb  mov     [rsp+0E0h+cIterations], rcx; cIterations
0x18001c2f0  mov     rcx, [r15+0B8h]; hPrf
0x18001c2f7  mov     [rsp+0E0h+cbSalt], r12d; cbSalt
0x18001c2fc  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x18001c302  mov     r12d, eax
0x18001c305  test    eax, eax
0x18001c307  jns     short loc_18001C324
0x18001c309  mov     edx, eax; char *
0x18001c30b  lea     rcx, aBcryptderiveke; "BCryptDeriveKeyPBKDF2(m_checksumHandle,"...
0x18001c312  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c317  mov     [rdi], rbx
0x18001c31a  mov     [rdi+8], rbx
0x18001c31e  mov     [rdi+10h], r12d
0x18001c322  jmp     short loc_18001C34A
0x18001c324  lea     rax, aKerberos; "kerberos"
0x18001c32b  mov     qword ptr [rbp+4Fh+cbPassword], 8
0x18001c333  lea     r9, [rbp+4Fh+cbPassword]
0x18001c337  mov     [rbp+4Fh+pbPassword], rax
0x18001c33b  lea     r8, [rbp+4Fh+var_78]
0x18001c33f  mov     rdx, rdi
0x18001c342  mov     rcx, r15
0x18001c345  call    ?DeriveKey@Aes3962@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::Aes3962::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001c34a  mov     rcx, [rbp+4Fh+var_70]; void *
0x18001c34e  test    rcx, rcx
0x18001c351  jz      short loc_18001C35A
0x18001c353  xor     edx, edx; struct std::nothrow_t *
0x18001c355  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c35a  test    r14, r14
0x18001c35d  jz      short loc_18001C369
0x18001c35f  xor     edx, edx; struct std::nothrow_t *
0x18001c361  mov     rcx, r14; void *
0x18001c364  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c369  test    rsi, rsi
0x18001c36c  jz      short loc_18001C378
0x18001c36e  mov     rcx, rsi; void *
0x18001c371  xor     edx, edx; struct std::nothrow_t *
0x18001c373  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c378  mov     rax, rdi
0x18001c37b  add     rsp, 0A8h
0x18001c382  pop     r15
0x18001c384  pop     r14
0x18001c386  pop     r13
0x18001c388  pop     r12
0x18001c38a  pop     rdi
0x18001c38b  pop     rsi
0x18001c38c  pop     rbx
0x18001c38d  pop     rbp
0x18001c38e  retn
```
