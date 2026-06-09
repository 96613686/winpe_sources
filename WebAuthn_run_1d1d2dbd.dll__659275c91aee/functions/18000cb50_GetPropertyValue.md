# GetPropertyValue

- ea: `0x18000cb50`
- end: `0x18000ce08`
- name: `GetPropertyValue`
- size: `696`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004fe20`

## callees

- `0x18000cb50`
- `0x180017764`
- `0x180036da4`
- `0x180036dc8`
- `0x18007bf50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cbd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cbd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cc9f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cc9f`
- `ncrypt!NCryptGetProperty` at `0x18000cb85`
- `ncrypt!NCryptGetProperty` at `0x18000cc19`
- `ncrypt!NCryptGetProperty` at `0x18000cb85`
- `ncrypt!NCryptGetProperty` at `0x18000cc19`

## string_xrefs

- `0x18000cbab`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18000cc2a`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18000ccae`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18000cda4`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18000cddb`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18000cc53`: `NgcUserSid`

## pseudocode

```c
__int64 __fastcall GetPropertyValue(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, WCHAR **a3)
{
  SECURITY_STATUS Property; // eax
  unsigned int v7; // ebx
  __int64 v9; // r14
  BYTE *v10; // rax
  BYTE *v11; // rbx
  BYTE *i; // rcx
  SECURITY_STATUS v13; // eax
  unsigned int v14; // esi
  __int64 v15; // rax
  int v16; // edx
  const char *v17; // r9
  unsigned int v18; // edi
  WCHAR *v19; // rsi
  __int64 v20; // rcx
  char *v21; // rax
  rsize_t v22; // rdi
  WCHAR *v23; // rax
  LPWSTR v24; // rbp
  DWORD LastError; // edi
  int pcbResult; // [rsp+20h] [rbp-38h]
  int pcbResulta; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD cbOutput; // [rsp+70h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  cbOutput = 0;
  Property = NCryptGetProperty(hObject, pszProperty, 0, 0, &cbOutput, 0);
  v7 = Property;
  if ( Property == -2146893807 )
    return 0;
  if ( Property < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    return v7;
  }
  v9 = cbOutput;
  v10 = (BYTE *)LocalAlloc(0, cbOutput);
  v11 = v10;
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x253,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
    return 2147942414LL;
  }
  for ( i = &v10[v9]; v10 != i; ++v10 )
    *v10 = 0;
  v13 = NCryptGetProperty(hObject, pszProperty, v11, cbOutput, &cbOutput, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)v13,
      pcbResulta);
    LocalFree(v11);
    return v14;
  }
  StringSid = 0;
  v15 = -1;
  do
  {
    v16 = pszProperty[v15 + 1] - aNgcusersid[v15 + 1];
    if ( v16 )
      break;
    v15 += 2;
    if ( v15 == 11 )
      break;
    v16 = pszProperty[v15] - aNgcusersid[v15];
  }
  while ( !v16 );
  if ( v16 )
  {
    v20 = 0x7FFFFFFF;
    v21 = (char *)v11;
    do
    {
      if ( !*(_WORD *)v21 )
        break;
      v21 += 2;
      --v20;
    }
    while ( v20 );
    v22 = 2 * ((v21 - (char *)v11) >> 1);
    v23 = (WCHAR *)LocalAlloc(0, v22 + 2);
    v19 = v23;
    if ( v23 )
    {
      memcpy_s_3(v23, v22 + 2, v11, v22);
      v19[v22 / 2] = 0;
    }
    v24 = StringSid;
    if ( StringSid )
    {
      LastError = GetLastError();
      LocalFree(v24);
      SetLastError(LastError);
    }
    StringSid = v19;
    if ( v19 )
      goto LABEL_28;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x267,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x8007000ELL,
      pcbResulta);
    if ( StringSid )
      LocalFree(StringSid);
    LocalFree(v11);
    return 2147942414LL;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(v11, &StringSid) )
  {
    v19 = StringSid;
LABEL_28:
    StringSid = 0;
    *a3 = v19;
    LocalFree(v11);
    return 0;
  }
  v18 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x261,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
          v17);
  if ( StringSid )
    LocalFree(StringSid);
  LocalFree(v11);
  return v18;
}

```

## disassembly

```asm
0x18000cb50  push    rbx
0x18000cb52  push    rsi
0x18000cb53  push    rdi
0x18000cb54  push    r12
0x18000cb56  push    r15
0x18000cb58  sub     rsp, 30h
0x18000cb5c  xor     r12d, r12d
0x18000cb5f  lea     rax, [rsp+58h+cbOutput]
0x18000cb64  mov     [r8], r12
0x18000cb67  mov     r15, r8
0x18000cb6a  xor     r8d, r8d; pbOutput
0x18000cb6d  mov     [rsp+58h+dwFlags], r12d; dwFlags
0x18000cb72  xor     r9d, r9d; cbOutput
0x18000cb75  mov     [rsp+58h+cbOutput], r12d
0x18000cb7a  mov     rdi, rdx
0x18000cb7d  mov     [rsp+58h+pcbResult], rax; int
0x18000cb82  mov     rsi, rcx
0x18000cb85  call    cs:__imp_NCryptGetProperty
0x18000cb8b  mov     ebx, eax
0x18000cb8d  cmp     eax, 80090011h
0x18000cb92  jnz     short loc_18000CBA2
0x18000cb94  xor     eax, eax
0x18000cb96  add     rsp, 30h
0x18000cb9a  pop     r15
0x18000cb9c  pop     r12
0x18000cb9e  pop     rdi
0x18000cb9f  pop     rsi
0x18000cba0  pop     rbx
0x18000cba1  retn
0x18000cba2  test    ebx, ebx
0x18000cba4  jns     short loc_18000CBC6
0x18000cba6  mov     rcx, [rsp+58h]; this
0x18000cbab  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000cbb2  mov     r9d, ebx; char *
0x18000cbb5  mov     edx, 250h; void *
0x18000cbba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbbf  mov     eax, ebx
0x18000cbc1  jmp     loc_18000CDFC
0x18000cbc6  mov     [rsp+58h+arg_8], r14
0x18000cbcb  xor     ecx, ecx; uFlags
0x18000cbcd  mov     r14d, [rsp+58h+cbOutput]
0x18000cbd2  mov     edx, r14d; uBytes
0x18000cbd5  call    cs:__imp_LocalAlloc
0x18000cbdb  mov     rbx, rax
0x18000cbde  test    rax, rax
0x18000cbe1  jz      loc_18000CDD6
0x18000cbe7  lea     rcx, [r14+rax]
0x18000cbeb  cmp     rax, rcx
0x18000cbee  jz      short loc_18000CBFC
0x18000cbf0  xor     edx, edx
0x18000cbf2  mov     [rax], dl
0x18000cbf4  inc     rax
0x18000cbf7  cmp     rax, rcx
0x18000cbfa  jnz     short loc_18000CBF0
0x18000cbfc  mov     r9d, [rsp+58h+cbOutput]; cbOutput
0x18000cc01  lea     rax, [rsp+58h+cbOutput]
0x18000cc06  mov     [rsp+58h+dwFlags], r12d; dwFlags
0x18000cc0b  mov     r8, rbx; pbOutput
0x18000cc0e  mov     rdx, rdi; pszProperty
0x18000cc11  mov     [rsp+58h+pcbResult], rax; int
0x18000cc16  mov     rcx, rsi; hObject
0x18000cc19  call    cs:__imp_NCryptGetProperty
0x18000cc1f  mov     esi, eax
0x18000cc21  test    eax, eax
0x18000cc23  jns     short loc_18000CC4E
0x18000cc25  mov     rcx, [rsp+58h]; this
0x18000cc2a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000cc31  mov     r9d, eax; char *
0x18000cc34  mov     edx, 25Bh; void *
0x18000cc39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc3e  mov     rcx, rbx; hMem
0x18000cc41  call    cs:__imp_LocalFree
0x18000cc47  mov     eax, esi
0x18000cc49  jmp     loc_18000CDF7
0x18000cc4e  mov     [rsp+58h+StringSid], r12
0x18000cc53  lea     r8, aNgcusersid; "NgcUserSid"
0x18000cc5a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cc61  movzx   edx, word ptr [rdi+rax*2+2]
0x18000cc66  movzx   ecx, word ptr [r8+rax*2+2]
0x18000cc6c  sub     edx, ecx
0x18000cc6e  jnz     short loc_18000CC87
0x18000cc70  add     rax, 2
0x18000cc74  cmp     rax, 0Bh
0x18000cc78  jz      short loc_18000CC87
0x18000cc7a  movzx   edx, word ptr [rdi+rax*2]
0x18000cc7e  movzx   ecx, word ptr [r8+rax*2]
0x18000cc83  sub     edx, ecx
0x18000cc85  jz      short loc_18000CC61
0x18000cc87  test    edx, edx
0x18000cc89  jnz     short loc_18000CCF7
0x18000cc8b  xor     edx, edx
0x18000cc8d  lea     rcx, [rsp+58h+StringSid]
0x18000cc92  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000cc97  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18000cc9c  mov     rcx, rbx; Sid
0x18000cc9f  call    cs:__imp_ConvertSidToStringSidW
0x18000cca5  test    eax, eax
0x18000cca7  jnz     short loc_18000CCED
0x18000cca9  mov     rcx, [rsp+58h]; this
0x18000ccae  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000ccb5  mov     edx, 261h; void *
0x18000ccba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ccbf  mov     rcx, [rsp+58h+StringSid]; hMem
0x18000ccc4  mov     edi, eax
0x18000ccc6  test    rcx, rcx
0x18000ccc9  jz      short loc_18000CCD1
0x18000cccb  call    cs:__imp_LocalFree
0x18000ccd1  mov     rcx, rbx; hMem
0x18000ccd4  call    cs:__imp_LocalFree
0x18000ccda  mov     r14, [rsp+58h+arg_8]
0x18000ccdf  mov     eax, edi
0x18000cce1  add     rsp, 30h
0x18000cce5  pop     r15
0x18000cce7  pop     r12
0x18000cce9  pop     rdi
0x18000ccea  pop     rsi
0x18000cceb  pop     rbx
0x18000ccec  retn
0x18000cced  mov     rsi, [rsp+58h+StringSid]
0x18000ccf2  jmp     loc_18000CD7B
0x18000ccf7  mov     [rsp+58h+arg_0], rbp
0x18000ccfc  mov     ecx, 7FFFFFFFh
0x18000cd01  mov     rax, rbx
0x18000cd04  cmp     [rax], r12w
0x18000cd08  jz      short loc_18000CD14
0x18000cd0a  add     rax, 2
0x18000cd0e  sub     rcx, 1
0x18000cd12  jnz     short loc_18000CD04
0x18000cd14  sub     rax, rbx
0x18000cd17  xor     ecx, ecx; uFlags
0x18000cd19  sar     rax, 1
0x18000cd1c  lea     rdi, [rax+rax]
0x18000cd20  lea     rdx, [rdi+2]; uBytes
0x18000cd24  call    cs:__imp_LocalAlloc
0x18000cd2a  mov     rsi, rax
0x18000cd2d  test    rax, rax
0x18000cd30  jz      short loc_18000CD49
0x18000cd32  mov     r9, rdi; SourceSize
0x18000cd35  lea     rdx, [rdi+2]; DestinationSize
0x18000cd39  mov     r8, rbx; Source
0x18000cd3c  mov     rcx, rax; Destination
0x18000cd3f  call    memcpy_s_3
0x18000cd44  mov     [rdi+rsi], r12w
0x18000cd49  mov     rbp, [rsp+58h+StringSid]
0x18000cd4e  test    rbp, rbp
0x18000cd51  jz      short loc_18000CD6C
0x18000cd53  call    cs:__imp_GetLastError
0x18000cd59  mov     rcx, rbp; hMem
0x18000cd5c  mov     edi, eax
0x18000cd5e  call    cs:__imp_LocalFree
0x18000cd64  mov     ecx, edi; dwErrCode
0x18000cd66  call    cs:__imp_SetLastError
0x18000cd6c  mov     rbp, [rsp+58h+arg_0]
0x18000cd71  mov     [rsp+58h+StringSid], rsi
0x18000cd76  test    rsi, rsi
0x18000cd79  jz      short loc_18000CD9F
0x18000cd7b  mov     rcx, rbx; hMem
0x18000cd7e  mov     [rsp+58h+StringSid], r12
0x18000cd83  mov     [r15], rsi
0x18000cd86  call    cs:__imp_LocalFree
0x18000cd8c  mov     r14, [rsp+58h+arg_8]
0x18000cd91  xor     eax, eax
0x18000cd93  add     rsp, 30h
0x18000cd97  pop     r15
0x18000cd99  pop     r12
0x18000cd9b  pop     rdi
0x18000cd9c  pop     rsi
0x18000cd9d  pop     rbx
0x18000cd9e  retn
0x18000cd9f  mov     rcx, [rsp+58h]; this
0x18000cda4  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000cdab  mov     r9d, 8007000Eh; char *
0x18000cdb1  mov     edx, 267h; void *
0x18000cdb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdbb  mov     rcx, [rsp+58h+StringSid]; hMem
0x18000cdc0  test    rcx, rcx
0x18000cdc3  jz      short loc_18000CDCB
0x18000cdc5  call    cs:__imp_LocalFree
0x18000cdcb  mov     rcx, rbx; hMem
0x18000cdce  call    cs:__imp_LocalFree
0x18000cdd4  jmp     short loc_18000CDF2
0x18000cdd6  mov     rcx, [rsp+58h]; this
0x18000cddb  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18000cde2  mov     r9d, 8007000Eh; char *
0x18000cde8  mov     edx, 253h; void *
0x18000cded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdf2  mov     eax, 8007000Eh
0x18000cdf7  mov     r14, [rsp+58h+arg_8]
0x18000cdfc  add     rsp, 30h
0x18000ce00  pop     r15
0x18000ce02  pop     r12
0x18000ce04  pop     rdi
0x18000ce05  pop     rsi
0x18000ce06  pop     rbx
0x18000ce07  retn
```
