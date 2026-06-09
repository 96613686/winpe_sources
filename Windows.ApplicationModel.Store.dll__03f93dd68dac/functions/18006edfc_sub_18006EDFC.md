# sub_18006EDFC

- ea: `0x18006edfc`
- end: `0x18006f0cd`
- name: `sub_18006EDFC`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180075980`

## callees

- `0x1800044c0`
- `0x180004890`
- `0x18001b940`
- `0x180035678`
- `0x180038a50`
- `0x18003c3c8`
- `0x180044e68`
- `0x18006dcf4`
- `0x18006edfc`
- `0x1800aa538`
- `0x1800c6950`
- `0x1800f4568`
- `0x1801519b8`
- `0x1801551dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18006ee4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18006efdb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18006ee4b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18006efdb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006f06d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006f06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ee95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006eec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ee95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006eec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ef94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006eee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006eee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006efa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006efa3`

## string_xrefs

- `0x18006f001`: `serviceTicket`
- `0x18006f015`: `CurrentApp.GetCustomerCollectionsIdAsync`
- `0x18006ef51`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x18006ef4a`: `CatalogServiceProxyV6::GetCustomerCollectionsId`
- `0x18006ef3a`: `ChkHr(GetB2BKey(collectionKeysUri.Get(), serviceTicket, publisherUserId, pCV, collectionsId))`
- `0x18006ef09`: `ChkHr(UriHelper::GetUriWithPath( UriHelper::MDCollections, HStringReference(L"v6.0/beneficiaries/me/keys").Get(), collectionKeysUri.GetAddressOf()))`

## pseudocode

```c
__int64 __fastcall sub_18006EDFC(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  int v5; // r14d
  __int64 v6; // r15
  __int64 v7; // r12
  HRESULT v8; // eax
  int v9; // ebx
  const char *v10; // r9
  int v11; // edx
  HSTRING v12; // r15
  HSTRING *v13; // r14
  __int64 v14; // r14
  __int64 v15; // r15
  __int64 v16; // r12
  HSTRING v18; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v19; // [rsp+68h] [rbp-98h] BYREF
  GUID Buf2; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v23[136]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD *v24; // [rsp+128h] [rbp+28h]
  __int64 v25; // [rsp+130h] [rbp+30h]
  __int64 v26; // [rsp+138h] [rbp+38h]

  v4 = a1 + 24;
  if ( !*(_BYTE *)(a1 + 24) && *(_WORD *)(a1 + 154) )
    o_wcstombs(a1 + 24, a1 + 154, 129);
  sub_18006DCF4(v23, v4);
  if ( v24 )
    *v24 = 0;
  v23[0] = 0;
  if ( v25 )
    sub_180035678(v25, v23);
  sub_180044E68(&Buf2);
  v19 = 0;
  WindowsDeleteString(0);
  if ( v24 )
    *v24 = 0;
  v23[0] = 0;
  v5 = v25;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(_QWORD *)(a1 + 8);
  v19 = 0;
  WindowsDeleteString(0);
  v18 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"v6.0/beneficiaries/me/keys", 0x1Au, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    sub_18003C3C8((unsigned int)v8);
    JUMPOUT(0x18006F0CCLL);
  }
  v9 = sub_1800C6950(0, string, &v18);
  if ( v9 < 0 )
  {
    v10 = "ChkHr(UriHelper::GetUriWithPath( UriHelper::MDCollections, HStringReference(L\"v6.0/beneficiaries/me/keys\").G"
          "et(), collectionKeysUri.GetAddressOf()))";
    v11 = 385;
LABEL_15:
    sub_1801519B8(
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
      v11,
      (unsigned int)"CatalogServiceProxyV6::GetCustomerCollectionsId",
      (_DWORD)v10,
      v9);
    sub_18001B940((unsigned int)v9);
    goto LABEL_16;
  }
  v9 = sub_1800F4568((_DWORD)v18, v7, v6, v5, (__int64)&v19);
  if ( v9 < 0 )
  {
    v10 = "ChkHr(GetB2BKey(collectionKeysUri.Get(), serviceTicket, publisherUserId, pCV, collectionsId))";
    v11 = 387;
    goto LABEL_15;
  }
LABEL_16:
  WindowsDeleteString(v18);
  sub_180038A50((unsigned int)v9);
  if ( v9 >= 0 )
  {
    v12 = v19;
    v13 = (HSTRING *)(a2 + 16);
    if ( !v19 || v19 != *v13 )
    {
      WindowsDeleteString(*v13);
      *v13 = 0;
      WindowsDuplicateString(v12, v13);
    }
  }
  v14 = *(_QWORD *)(a1 + 16);
  v15 = *(_QWORD *)(a1 + 8);
  v16 = *(_QWORD *)(*(_QWORD *)a1 + 184LL);
  if ( !*(_BYTE *)v4 && *(_WORD *)(v4 + 130) )
    o_wcstombs(v4, v4 + 130, 129);
  sub_1800AA538(
    "CurrentApp.GetCustomerCollectionsIdAsync",
    (unsigned int)v9,
    v4,
    v16,
    "serviceTicket",
    v15,
    "publisherUserId",
    v14,
    0,
    0);
  WindowsDeleteString(*(HSTRING *)(a1 + 8));
  WindowsDeleteString(*(HSTRING *)(a1 + 16));
  WindowsDeleteString(v19);
  v19 = 0;
  if ( memcmp(&xmmword_1801A57E0, &Buf2, 0x10u) )
    EventActivityIdControl(2u, &Buf2);
  if ( v26 )
  {
    j_j__o_free(v26);
    v26 = 0;
  }
  if ( v24 )
    j_j__o_free(v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006edfc  mov     [rsp-8+arg_10], rbx
0x18006ee01  push    rbp
0x18006ee02  push    rsi
0x18006ee03  push    rdi
0x18006ee04  push    r12
0x18006ee06  push    r13
0x18006ee08  push    r14
0x18006ee0a  push    r15
0x18006ee0c  lea     rbp, [rsp-50h]
0x18006ee11  sub     rsp, 150h
0x18006ee18  mov     rax, cs:__security_cookie
0x18006ee1f  xor     rax, rsp
0x18006ee22  mov     [rbp+80h+var_40], rax
0x18006ee26  mov     r13, rdx
0x18006ee29  mov     rsi, rcx
0x18006ee2c  lea     rdi, [rcx+18h]
0x18006ee30  xor     ebx, ebx
0x18006ee32  cmp     [rdi], bl
0x18006ee34  jnz     short loc_18006EE51
0x18006ee36  lea     rdx, [rdi+82h]
0x18006ee3d  cmp     bx, [rdx]
0x18006ee40  jz      short loc_18006EE51
0x18006ee42  mov     r8d, 81h
0x18006ee48  mov     rcx, rdi
0x18006ee4b  call    cs:_o_wcstombs
0x18006ee51  mov     rdx, rdi
0x18006ee54  lea     rcx, [rbp+80h+var_E0]
0x18006ee58  call    sub_18006DCF4
0x18006ee5d  nop
0x18006ee5e  mov     rcx, [rbp+80h+var_58]
0x18006ee62  test    rcx, rcx
0x18006ee65  jz      short loc_18006EE6A
0x18006ee67  mov     [rcx], bx
0x18006ee6a  mov     [rbp+80h+var_E0], bl
0x18006ee6d  mov     rcx, [rbp+80h+var_50]
0x18006ee71  test    rcx, rcx
0x18006ee74  jz      short loc_18006EE7F
0x18006ee76  lea     rdx, [rbp+80h+var_E0]
0x18006ee7a  call    sub_180035678
0x18006ee7f  lea     rdx, [rbp+80h+var_E0]
0x18006ee83  lea     rcx, [rsp+180h+Buf2]; ActivityId
0x18006ee88  call    sub_180044E68
0x18006ee8d  nop
0x18006ee8e  mov     [rsp+180h+var_118], rbx
0x18006ee93  xor     ecx, ecx; string
0x18006ee95  call    cs:WindowsDeleteString
0x18006ee9b  mov     rcx, [rbp+80h+var_58]
0x18006ee9f  test    rcx, rcx
0x18006eea2  jz      short loc_18006EEA7
0x18006eea4  mov     [rcx], bx
0x18006eea7  mov     [rbp+80h+var_E0], bl
0x18006eeaa  mov     r14, [rbp+80h+var_50]
0x18006eeae  mov     r15, [rsi+10h]
0x18006eeb2  mov     r12, [rsi+8]
0x18006eeb6  mov     [rsp+180h+var_118], rbx
0x18006eebb  mov     [rsp+180h+var_120], rbx
0x18006eec0  xor     ecx, ecx; string
0x18006eec2  call    cs:WindowsDeleteString
0x18006eec8  mov     [rsp+180h+var_120], rbx
0x18006eecd  mov     [rbp+80h+string], rbx
0x18006eed1  lea     r9, [rbp+80h+string]; string
0x18006eed5  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x18006eed9  mov     edx, 1Ah; length
0x18006eede  lea     rcx, aV60Beneficiari; "v6.0/beneficiaries/me/keys"
0x18006eee5  call    cs:WindowsCreateStringReference
0x18006eeeb  test    eax, eax
0x18006eeed  js      loc_18006F0C5
0x18006eef3  lea     r8, [rsp+180h+var_120]
0x18006eef8  mov     rdx, [rbp+80h+string]
0x18006eefc  xor     ecx, ecx
0x18006eefe  call    sub_1800C6950
0x18006ef03  mov     ebx, eax
0x18006ef05  test    eax, eax
0x18006ef07  jns     short loc_18006EF17
0x18006ef09  lea     r9, aChkhrUrihelper_3; "ChkHr(UriHelper::GetUriWithPath( UriHel"...
0x18006ef10  mov     edx, 181h
0x18006ef15  jmp     short loc_18006EF46
0x18006ef17  lea     rax, [rsp+180h+var_118]
0x18006ef1c  mov     [rsp+180h+var_160], rax
0x18006ef21  mov     r9, r14
0x18006ef24  mov     r8, r15
0x18006ef27  mov     rdx, r12
0x18006ef2a  mov     rcx, [rsp+180h+var_120]
0x18006ef2f  call    sub_1800F4568
0x18006ef34  mov     ebx, eax
0x18006ef36  test    eax, eax
0x18006ef38  jns     short loc_18006EF65
0x18006ef3a  lea     r9, aChkhrGetb2bkey_0; "ChkHr(GetB2BKey(collectionKeysUri.Get()"...
0x18006ef41  mov     edx, 183h
0x18006ef46  mov     dword ptr [rsp+180h+var_160], ebx
0x18006ef4a  lea     r8, aCatalogservice_0; "CatalogServiceProxyV6::GetCustomerColle"...
0x18006ef51  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x18006ef58  call    sub_1801519B8
0x18006ef5d  mov     ecx, ebx
0x18006ef5f  call    sub_18001B940
0x18006ef64  nop
0x18006ef65  mov     rcx, [rsp+180h+var_120]; string
0x18006ef6a  call    cs:WindowsDeleteString
0x18006ef70  mov     ecx, ebx
0x18006ef72  call    sub_180038A50
0x18006ef77  test    ebx, ebx
0x18006ef79  js      short loc_18006EFAB
0x18006ef7b  mov     r15, [rsp+180h+var_118]
0x18006ef80  lea     r14, [r13+10h]
0x18006ef84  xor     r13d, r13d
0x18006ef87  test    r15, r15
0x18006ef8a  jz      short loc_18006EF91
0x18006ef8c  cmp     r15, [r14]
0x18006ef8f  jz      short loc_18006EFAE
0x18006ef91  mov     rcx, [r14]; string
0x18006ef94  call    cs:WindowsDeleteString
0x18006ef9a  mov     [r14], r13
0x18006ef9d  mov     rdx, r14; newString
0x18006efa0  mov     rcx, r15; string
0x18006efa3  call    cs:WindowsDuplicateString
0x18006efa9  jmp     short loc_18006EFAE
0x18006efab  xor     r13d, r13d
0x18006efae  mov     r14, [rsi+10h]
0x18006efb2  mov     r15, [rsi+8]
0x18006efb6  mov     rax, [rsi]
0x18006efb9  mov     r12, [rax+0B8h]
0x18006efc0  cmp     [rdi], r13b
0x18006efc3  jnz     short loc_18006EFE1
0x18006efc5  lea     rdx, [rdi+82h]
0x18006efcc  cmp     r13w, [rdx]
0x18006efd0  jz      short loc_18006EFE1
0x18006efd2  mov     r8d, 81h
0x18006efd8  mov     rcx, rdi
0x18006efdb  call    cs:_o_wcstombs
0x18006efe1  mov     [rsp+180h+var_138], r13
0x18006efe6  mov     [rsp+180h+var_140], r13
0x18006efeb  mov     [rsp+180h+var_148], r14
0x18006eff0  lea     rax, aPublisheruseri_0; "publisherUserId"
0x18006eff7  mov     [rsp+180h+var_150], rax
0x18006effc  mov     [rsp+180h+var_158], r15
0x18006f001  lea     rax, aServiceticket_0; "serviceTicket"
0x18006f008  mov     [rsp+180h+var_160], rax
0x18006f00d  mov     r9, r12
0x18006f010  mov     r8, rdi
0x18006f013  mov     edx, ebx
0x18006f015  lea     rcx, aCurrentappGetc; "CurrentApp.GetCustomerCollectionsIdAsyn"...
0x18006f01c  call    sub_1800AA538
0x18006f021  mov     rcx, [rsi+8]; string
0x18006f025  call    cs:WindowsDeleteString
0x18006f02b  mov     rcx, [rsi+10h]; string
0x18006f02f  call    cs:WindowsDeleteString
0x18006f035  nop
0x18006f036  mov     rcx, [rsp+180h+var_118]; string
0x18006f03b  call    cs:WindowsDeleteString
0x18006f041  mov     [rsp+180h+var_118], r13
0x18006f046  mov     r8d, 10h; Size
0x18006f04c  lea     rdx, [rsp+180h+Buf2]; Buf2
0x18006f051  lea     rcx, xmmword_1801A57E0; Buf1
0x18006f058  call    memcmp
0x18006f05d  mov     edi, 2
0x18006f062  test    eax, eax
0x18006f064  jz      short loc_18006F074
0x18006f066  lea     rdx, [rsp+180h+Buf2]; ActivityId
0x18006f06b  mov     ecx, edi; ControlCode
0x18006f06d  call    cs:EventActivityIdControl
0x18006f073  nop
0x18006f074  mov     rcx, [rbp+80h+var_48]
0x18006f078  test    rcx, rcx
0x18006f07b  jz      short loc_18006F08B
0x18006f07d  mov     edx, 90h
0x18006f082  call    j_j__o_free
0x18006f087  mov     [rbp+80h+var_48], r13
0x18006f08b  mov     rcx, [rbp+80h+var_58]
0x18006f08f  test    rcx, rcx
0x18006f092  jz      short loc_18006F09C
0x18006f094  mov     rdx, rdi
0x18006f097  call    j_j__o_free
0x18006f09c  mov     eax, ebx
0x18006f09e  mov     rcx, [rbp+80h+var_40]
0x18006f0a2  xor     rcx, rsp; StackCookie
0x18006f0a5  call    __security_check_cookie
0x18006f0aa  mov     rbx, [rsp+180h+arg_10]
0x18006f0b2  add     rsp, 150h
0x18006f0b9  pop     r15
0x18006f0bb  pop     r14
0x18006f0bd  pop     r13
0x18006f0bf  pop     r12
0x18006f0c1  pop     rdi
0x18006f0c2  pop     rsi
0x18006f0c3  pop     rbp
0x18006f0c4  retn
0x18006f0c5  mov     ecx, eax
0x18006f0c7  call    sub_18003C3C8
```
