# _GetHMACAlgName

- ea: `0x180015280`
- end: `0x18001537e`
- name: `_GetHMACAlgName`
- size: `254`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x180015280`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800152ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800152e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001531c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015353`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800152ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800152e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001531c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015353`

## string_xrefs

- `0x18001528d`: `http://www.w3.org/2000/09/xmldsig#hmac-sha1`
- `0x1800152c8`: `http://www.w3.org/2001/04/xmldsig-more#hmac-sha256`
- `0x1800152ff`: `http://www.w3.org/2001/04/xmldsig-more#hmac-sha384`
- `0x180015336`: `http://www.w3.org/2001/04/xmldsig-more#hmac-sha512`

## pseudocode

```c
const wchar_t *__fastcall GetHMACAlgName(PCNZWCH lpString1)
{
  const wchar_t *v2; // rdx
  int v3; // eax

  if ( CompareStringW(0, 1u, lpString1, -1, L"http://www.w3.org/2000/09/xmldsig#hmac-sha1", -1) == 2 )
    return L"SHA1";
  if ( CompareStringW(0, 1u, lpString1, -1, L"http://www.w3.org/2001/04/xmldsig-more#hmac-sha256", -1) == 2 )
    return L"SHA256";
  if ( CompareStringW(0, 1u, lpString1, -1, L"http://www.w3.org/2001/04/xmldsig-more#hmac-sha384", -1) == 2 )
    return L"SHA384";
  v3 = CompareStringW(0, 1u, lpString1, -1, L"http://www.w3.org/2001/04/xmldsig-more#hmac-sha512", -1);
  v2 = L"SHA512";
  if ( v3 != 2 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180015280  mov     [rsp+arg_0], rbx
0x180015285  push    rdi
0x180015286  sub     rsp, 30h
0x18001528a  or      edi, 0FFFFFFFFh
0x18001528d  lea     rax, aHttpWwwW3Org20_17; "http://www.w3.org/2000/09/xmldsig#hmac-"...
0x180015294  mov     rbx, rcx
0x180015297  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18001529b  mov     r8, rcx; lpString1
0x18001529e  mov     [rsp+38h+lpString2], rax; lpString2
0x1800152a3  mov     r9d, edi; cchCount1
0x1800152a6  xor     ecx, ecx; Locale
0x1800152a8  lea     edx, [rdi+2]; dwCmpFlags
0x1800152ab  call    cs:__imp_CompareStringW
0x1800152b2  nop     dword ptr [rax+rax+00h]
0x1800152b7  cmp     eax, 2
0x1800152ba  jnz     short loc_1800152C8
0x1800152bc  lea     rdx, aSha1; "SHA1"
0x1800152c3  jmp     loc_18001536F
0x1800152c8  lea     rax, aHttpWwwW3Org20_6; "http://www.w3.org/2001/04/xmldsig-more#"...
0x1800152cf  mov     [rsp+38h+cchCount2], edi; cchCount2
0x1800152d3  mov     r9d, edi; cchCount1
0x1800152d6  mov     [rsp+38h+lpString2], rax; lpString2
0x1800152db  mov     r8, rbx; lpString1
0x1800152de  mov     edx, 1; dwCmpFlags
0x1800152e3  xor     ecx, ecx; Locale
0x1800152e5  call    cs:__imp_CompareStringW
0x1800152ec  nop     dword ptr [rax+rax+00h]
0x1800152f1  cmp     eax, 2
0x1800152f4  jnz     short loc_1800152FF
0x1800152f6  lea     rdx, aSha256; "SHA256"
0x1800152fd  jmp     short loc_18001536F
0x1800152ff  lea     rax, aHttpWwwW3Org20_0; "http://www.w3.org/2001/04/xmldsig-more#"...
0x180015306  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18001530a  mov     r9d, edi; cchCount1
0x18001530d  mov     [rsp+38h+lpString2], rax; lpString2
0x180015312  mov     r8, rbx; lpString1
0x180015315  mov     edx, 1; dwCmpFlags
0x18001531a  xor     ecx, ecx; Locale
0x18001531c  call    cs:__imp_CompareStringW
0x180015323  nop     dword ptr [rax+rax+00h]
0x180015328  cmp     eax, 2
0x18001532b  jnz     short loc_180015336
0x18001532d  lea     rdx, aSha384; "SHA384"
0x180015334  jmp     short loc_18001536F
0x180015336  lea     rax, aHttpWwwW3Org20_5; "http://www.w3.org/2001/04/xmldsig-more#"...
0x18001533d  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180015341  mov     r9d, edi; cchCount1
0x180015344  mov     [rsp+38h+lpString2], rax; lpString2
0x180015349  mov     r8, rbx; lpString1
0x18001534c  mov     edx, 1; dwCmpFlags
0x180015351  xor     ecx, ecx; Locale
0x180015353  call    cs:__imp_CompareStringW
0x18001535a  nop     dword ptr [rax+rax+00h]
0x18001535f  xor     ecx, ecx
0x180015361  lea     rdx, aSha512; "SHA512"
0x180015368  cmp     eax, 2
0x18001536b  cmovnz  rdx, rcx
0x18001536f  mov     rbx, [rsp+38h+arg_0]
0x180015374  mov     rax, rdx
0x180015377  add     rsp, 30h
0x18001537b  pop     rdi
0x18001537c  retn
```
