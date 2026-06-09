# UsageAndQualityInsights::Utilities::ShouldUseSystemDatabase(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002305c`
- end: `0x180023110`
- name: `?ShouldUseSystemDatabase@Utilities@UsageAndQualityInsights@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f3a98`

## callees

- `0x1800033d0`
- `0x18002305c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023096`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023096`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800230e2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800230e2`

## pseudocode

```c
bool __fastcall UsageAndQualityInsights::Utilities::ShouldUseSystemDatabase(const WCHAR *a1)
{
  bool v1; // cc
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+260h] [rbp+160h] BYREF

  v1 = *((_QWORD *)a1 + 3) <= 7u;
  Sid = 0;
  if ( !v1 )
    a1 = *(const WCHAR **)a1;
  ConvertStringSidToSidW(a1, &Sid);
  peUse = 0;
  cchName = 256;
  cchReferencedDomainName = 256;
  return !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
      || peUse != SidTypeUser;
}

```

## disassembly

```asm
0x18002305c  push    rbp
0x18002305e  lea     rbp, [rsp-370h]
0x180023066  sub     rsp, 470h
0x18002306d  mov     rax, cs:__security_cookie
0x180023074  xor     rax, rsp
0x180023077  mov     [rbp+370h+var_10], rax
0x18002307e  cmp     qword ptr [rcx+18h], 7
0x180023083  mov     [rsp+470h+Sid], 0
0x18002308c  jbe     short loc_180023091
0x18002308e  mov     rcx, [rcx]; StringSid
0x180023091  lea     rdx, [rsp+470h+Sid]; Sid
0x180023096  call    cs:__imp_ConvertStringSidToSidW
0x18002309c  mov     rdx, [rsp+470h+Sid]; Sid
0x1800230a1  lea     r9, [rsp+470h+cchName]; cchName
0x1800230a6  mov     eax, 100h
0x1800230ab  mov     [rsp+470h+var_430], 0
0x1800230b3  mov     [rsp+470h+cchName], eax
0x1800230b7  lea     r8, [rbp+370h+Name]; Name
0x1800230be  mov     [rsp+470h+var_42C], eax
0x1800230c2  xor     ecx, ecx; lpSystemName
0x1800230c4  lea     rax, [rsp+470h+var_430]
0x1800230c9  mov     [rsp+470h+peUse], rax; peUse
0x1800230ce  lea     rax, [rsp+470h+var_42C]
0x1800230d3  mov     [rsp+470h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800230d8  lea     rax, [rsp+470h+var_410]
0x1800230dd  mov     [rsp+470h+ReferencedDomainName], rax; ReferencedDomainName
0x1800230e2  call    cs:__imp_LookupAccountSidW
0x1800230e8  test    eax, eax
0x1800230ea  jz      short loc_1800230F6
0x1800230ec  cmp     [rsp+470h+var_430], 1
0x1800230f1  setnz   al
0x1800230f4  jmp     short loc_1800230F8
0x1800230f6  mov     al, 1
0x1800230f8  mov     rcx, [rbp+370h+var_10]
0x1800230ff  xor     rcx, rsp; StackCookie
0x180023102  call    __security_check_cookie
0x180023107  add     rsp, 470h
0x18002310e  pop     rbp
0x18002310f  retn
```
