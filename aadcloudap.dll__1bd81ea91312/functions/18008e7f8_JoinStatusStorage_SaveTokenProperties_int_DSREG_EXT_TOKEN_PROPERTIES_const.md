# JoinStatusStorage::SaveTokenProperties(int,_DSREG_EXT_TOKEN_PROPERTIES const *)

- ea: `0x18008e7f8`
- end: `0x18008e9ea`
- name: `?SaveTokenProperties@JoinStatusStorage@@SAJHPEBU_DSREG_EXT_TOKEN_PROPERTIES@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(int, const struct _DSREG_EXT_TOKEN_PROPERTIES *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18005950c`

## callees

- `0x1800878c4`
- `0x180087b58`
- `0x18008aa28`
- `0x18008aecc`
- `0x18008c6fc`
- `0x18008cfc4`
- `0x18008e3ac`
- `0x18008e7f8`
- `0x1800924b8`

## string_xrefs

- `0x18008e847`: `pTokenProperties`
- `0x18008e866`: `pTokenProperties`
- `0x18008e89d`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18008e8dd`: `RegistryPath::Append`
- `0x18008e982`: `pTokenProperties->pszTenantId`
- `0x18008e9a1`: `pTokenProperties->pszTenantId`
- `0x18008e853`: `JoinStatusStorage::SaveTokenProperties`
- `0x18008e8a7`: `JoinStatusStorage::SaveTokenProperties`
- `0x18008e8e4`: `JoinStatusStorage::SaveTokenProperties`
- `0x18008e98e`: `JoinStatusStorage::SaveTokenProperties`
- `0x18008e9a8`: `JoinStatusStorage::SaveTokenProperties`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::SaveTokenProperties(__int64 a1, const unsigned __int16 **a2)
{
  __int64 v3; // rdx
  signed int v4; // ebx
  const unsigned __int16 *v5; // rdx
  _WORD *v6; // rax
  int inited; // eax
  const wchar_t *v8; // r8
  unsigned int v9; // eax
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rax
  bool v12; // zf
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  const WCHAR *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h]
  __int64 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int128 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  _BYTE v24[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  const WCHAR *v27; // [rsp+A0h] [rbp-60h]

  struct_join_status::Clear((struct_join_status *)v24);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( !v3 )
  {
    v4 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"JoinStatusStorage::SaveTokenProperties",
      L"pTokenProperties");
    v5 = L"pTokenProperties";
LABEL_24:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"JoinStatusStorage::SaveTokenProperties", v5);
    goto LABEL_25;
  }
  v6 = *(_WORD **)(v3 + 16);
  if ( !v6 || !*v6 )
  {
    v4 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"JoinStatusStorage::SaveTokenProperties",
      L"pTokenProperties->pszTenantId");
    v5 = L"pTokenProperties->pszTenantId";
    goto LABEL_24;
  }
  inited = JoinStatusStorage::InitJoinStatusRegPath(1, (struct RegistryPath *)&v17);
  v4 = inited;
  if ( inited < 0 )
  {
    v8 = L"JoinStatusStorage::InitJoinStatusRegPath";
LABEL_7:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::SaveTokenProperties",
      v8,
      (unsigned int)inited,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23);
    goto LABEL_25;
  }
  v9 = RegistryPath::Append((RegistryPath *)&v17, L"TenantInfo", a2[2]);
  v4 = v9;
  if ( v9 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::SaveTokenProperties",
      L"RegistryPath::Append",
      v9,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v10 = &base;
    v11 = &base;
    if ( a2[3] )
      v11 = a2[3];
    v12 = a2[4] == 0;
    *(_QWORD *)&v25 = v11;
    v13 = &base;
    if ( !v12 )
      v13 = a2[4];
    v12 = a2[5] == 0;
    *((_QWORD *)&v25 + 1) = v13;
    v14 = &base;
    if ( !v12 )
      v14 = a2[5];
    v12 = a2[6] == 0;
    *(_QWORD *)&v26 = v14;
    v15 = &base;
    if ( !v12 )
      v15 = a2[6];
    v12 = a2[7] == 0;
    *((_QWORD *)&v26 + 1) = v15;
    if ( !v12 )
      v10 = a2[7];
    v27 = v10;
    inited = JoinStatusStorage::SaveTenantKey((struct struct_join_status *)v24, (struct RegistryPath *)&v17);
    v4 = inited;
    if ( inited < 0 )
    {
      v8 = L"JoinStatusStorage::SaveTenantKey";
      goto LABEL_7;
    }
  }
LABEL_25:
  v27 = 0;
  v25 = 0;
  v26 = 0;
  RegistryPath::Reset((RegistryPath *)&v17);
  struct_join_status::~struct_join_status((struct_join_status *)v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008e7f8  push    rbp
0x18008e7fa  push    rbx
0x18008e7fb  push    rsi
0x18008e7fc  push    rdi
0x18008e7fd  lea     rbp, [rsp-0A8h]
0x18008e805  sub     rsp, 1A8h
0x18008e80c  lea     rcx, [rsp+1C0h+var_160]; this
0x18008e811  mov     rdi, rdx
0x18008e814  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x18008e819  xor     esi, esi
0x18008e81b  xorps   xmm0, xmm0
0x18008e81e  mov     [rsp+1C0h+var_1A0], rsi
0x18008e823  mov     [rsp+1C0h+var_198], rsi
0x18008e828  mov     [rsp+1C0h+var_190], rsi
0x18008e82d  mov     [rsp+1C0h+var_188], rsi
0x18008e832  movdqa  [rsp+1C0h+var_180], xmm0
0x18008e838  mov     [rsp+1C0h+var_170], rsi
0x18008e83d  mov     [rsp+1C0h+var_168], rsi
0x18008e842  test    rdx, rdx
0x18008e845  jnz     short loc_18008E872
0x18008e847  lea     r8, aPtokenproperti_0; "pTokenProperties"
0x18008e84e  mov     ebx, 80070057h
0x18008e853  lea     rdx, aJoinstatusstor_9; "JoinStatusStorage::SaveTokenProperties"
0x18008e85a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008e861  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008e866  lea     rdx, aPtokenproperti_0; "pTokenProperties"
0x18008e86d  jmp     loc_18008E9A8
0x18008e872  mov     rax, [rdx+10h]
0x18008e876  test    rax, rax
0x18008e879  jz      loc_18008E982
0x18008e87f  cmp     [rax], si
0x18008e882  jz      loc_18008E982
0x18008e888  lea     rdx, [rsp+1C0h+var_1A0]; struct RegistryPath *
0x18008e88d  mov     ecx, 1; int
0x18008e892  call    ?InitJoinStatusRegPath@JoinStatusStorage@@CAJHAEAVRegistryPath@@@Z; JoinStatusStorage::InitJoinStatusRegPath(int,RegistryPath &)
0x18008e897  mov     ebx, eax
0x18008e899  test    eax, eax
0x18008e89b  jns     short loc_18008E8BF
0x18008e89d  lea     r8, aJoinstatusstor_4; "JoinStatusStorage::InitJoinStatusRegPat"...
0x18008e8a4  mov     r9d, eax
0x18008e8a7  lea     rdx, aJoinstatusstor_9; "JoinStatusStorage::SaveTokenProperties"
0x18008e8ae  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008e8b5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008e8ba  jmp     loc_18008E9B4
0x18008e8bf  mov     r8, [rdi+10h]; unsigned __int16 *
0x18008e8c3  lea     rdx, aTenantinfo; "TenantInfo"
0x18008e8ca  lea     rcx, [rsp+1C0h+var_1A0]; this
0x18008e8cf  call    ?Append@RegistryPath@@QEAAKPEBG0@Z; RegistryPath::Append(ushort const *,ushort const *)
0x18008e8d4  mov     ebx, eax
0x18008e8d6  test    eax, eax
0x18008e8d8  jz      short loc_18008E90D
0x18008e8da  mov     r9d, eax
0x18008e8dd  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18008e8e4  lea     rdx, aJoinstatusstor_9; "JoinStatusStorage::SaveTokenProperties"
0x18008e8eb  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008e8f2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008e8f7  test    ebx, ebx
0x18008e8f9  jle     loc_18008E9B4
0x18008e8ff  movzx   ebx, bx
0x18008e902  or      ebx, 80070000h
0x18008e908  jmp     loc_18008E9B4
0x18008e90d  cmp     [rdi+18h], rsi
0x18008e911  lea     rcx, base
0x18008e918  mov     rax, rcx
0x18008e91b  lea     rdx, [rsp+1C0h+var_1A0]; struct RegistryPath *
0x18008e920  cmovnz  rax, [rdi+18h]
0x18008e925  cmp     [rdi+20h], rsi
0x18008e929  mov     qword ptr [rbp+0C0h+var_140], rax
0x18008e92d  mov     rax, rcx
0x18008e930  cmovnz  rax, [rdi+20h]
0x18008e935  cmp     [rdi+28h], rsi
0x18008e939  mov     qword ptr [rbp+0C0h+var_140+8], rax
0x18008e93d  mov     rax, rcx
0x18008e940  cmovnz  rax, [rdi+28h]
0x18008e945  cmp     [rdi+30h], rsi
0x18008e949  mov     qword ptr [rbp+0C0h+var_130], rax
0x18008e94d  mov     rax, rcx
0x18008e950  cmovnz  rax, [rdi+30h]
0x18008e955  cmp     [rdi+38h], rsi
0x18008e959  mov     qword ptr [rbp+0C0h+var_130+8], rax
0x18008e95d  cmovnz  rcx, [rdi+38h]
0x18008e962  mov     [rbp+0C0h+var_120], rcx
0x18008e966  lea     rcx, [rsp+1C0h+var_160]; struct struct_join_status *
0x18008e96b  call    ?SaveTenantKey@JoinStatusStorage@@KAJPEAUstruct_join_status@@AEAVRegistryPath@@@Z; JoinStatusStorage::SaveTenantKey(struct_join_status *,RegistryPath &)
0x18008e970  mov     ebx, eax
0x18008e972  test    eax, eax
0x18008e974  jns     short loc_18008E9B4
0x18008e976  lea     r8, aJoinstatusstor_8; "JoinStatusStorage::SaveTenantKey"
0x18008e97d  jmp     loc_18008E8A4
0x18008e982  lea     r8, aPtokenproperti; "pTokenProperties->pszTenantId"
0x18008e989  mov     ebx, 80070057h
0x18008e98e  lea     rdx, aJoinstatusstor_9; "JoinStatusStorage::SaveTokenProperties"
0x18008e995  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x18008e99c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008e9a1  lea     rdx, aPtokenproperti; "pTokenProperties->pszTenantId"
0x18008e9a8  lea     rcx, aJoinstatusstor_9; "JoinStatusStorage::SaveTokenProperties"
0x18008e9af  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008e9b4  xorps   xmm0, xmm0
0x18008e9b7  mov     [rbp+0C0h+var_120], rsi
0x18008e9bb  xorps   xmm1, xmm1
0x18008e9be  movdqa  [rbp+0C0h+var_140], xmm0
0x18008e9c3  lea     rcx, [rsp+1C0h+var_1A0]; this
0x18008e9c8  movdqa  [rbp+0C0h+var_130], xmm1
0x18008e9cd  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18008e9d2  lea     rcx, [rsp+1C0h+var_160]; this
0x18008e9d7  call    ??1struct_join_status@@QEAA@XZ; struct_join_status::~struct_join_status(void)
0x18008e9dc  mov     eax, ebx
0x18008e9de  add     rsp, 1A8h
0x18008e9e5  pop     rdi
0x18008e9e6  pop     rsi
0x18008e9e7  pop     rbx
0x18008e9e8  pop     rbp
0x18008e9e9  retn
```
