# GetUserNameForSid(void *)

- ea: `0x180026234`
- end: `0x18002635f`
- name: `?GetUserNameForSid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026368`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180011e18`
- `0x180014c04`
- `0x180026234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800262c9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800262c9`

## string_xrefs

- `0x1800262e3`: `LookupAccountSidLocal failed: %#x`

## pseudocode

```c
__int64 __fastcall GetUserNameForSid(__int64 a1, void *a2)
{
  DWORD LastError; // eax
  WCHAR *v5; // rdx
  unsigned __int64 v6; // r8
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchName[4]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h]
  __int16 v13; // [rsp+68h] [rbp-98h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  cchName[1] = HIDWORD(a1);
  memset_0(Name, 0, 0x204u);
  cchName[0] = 257;
  v13 = 0;
  peUse = 0;
  cchReferencedDomainName = 16;
  *(_OWORD *)ReferencedDomainName = 0;
  v12 = 0;
  if ( LookupAccountSidLocalW(a2, Name, cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v6 = -1;
    *(_QWORD *)(a1 + 24) = 0;
    do
      ++v6;
    while ( Name[v6] );
    v5 = Name;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1332 )
      Log(3u, L"LookupAccountSidLocal failed: %#x", LastError);
    v5 = (WCHAR *)&word_180096C4C;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v6 = 0;
    *(_QWORD *)(a1 + 24) = 0;
  }
  std::wstring::_Construct<1,wchar_t const *>((char **)a1, v5, v6);
  return a1;
}

```

## disassembly

```asm
0x180026234  mov     [rsp-8+arg_10], rbx
0x180026239  push    rbp
0x18002623a  push    rsi
0x18002623b  push    rdi
0x18002623c  lea     rbp, [rsp-190h]
0x180026244  sub     rsp, 290h
0x18002624b  mov     rax, cs:__security_cookie
0x180026252  xor     rax, rsp
0x180026255  mov     [rbp+1A0h+var_20], rax
0x18002625c  mov     rbx, rdx
0x18002625f  mov     qword ptr [rsp+2A0h+cchName], rcx
0x180026264  mov     rdi, rcx
0x180026267  xor     edx, edx; Val
0x180026269  lea     rcx, [rsp+2A0h+Name]; void *
0x18002626e  mov     r8d, 204h; Size
0x180026274  xor     esi, esi
0x180026276  call    memset_0
0x18002627b  xor     eax, eax
0x18002627d  mov     [rsp+2A0h+cchName], 101h
0x180026285  mov     [rsp+2A0h+var_238], ax
0x18002628a  lea     r9, [rsp+2A0h+ReferencedDomainName]; ReferencedDomainName
0x18002628f  xorps   xmm0, xmm0
0x180026292  mov     [rsp+2A0h+var_270], esi
0x180026296  lea     rax, [rsp+2A0h+var_270]
0x18002629b  mov     [rsp+2A0h+var_26C], 10h
0x1800262a3  mov     [rsp+2A0h+peUse], rax; peUse
0x1800262a8  lea     r8, [rsp+2A0h+cchName]; cchName
0x1800262ad  lea     rax, [rsp+2A0h+var_26C]
0x1800262b2  mov     rcx, rbx; Sid
0x1800262b5  lea     rdx, [rsp+2A0h+Name]; Name
0x1800262ba  mov     [rsp+2A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800262bf  movups  xmmword ptr [rsp+2A0h+ReferencedDomainName], xmm0
0x1800262c4  movups  [rsp+2A0h+var_248], xmm0
0x1800262c9  call    cs:__imp_LookupAccountSidLocalW
0x1800262cf  test    eax, eax
0x1800262d1  jnz     short loc_18002630C
0x1800262d3  call    cs:__imp_GetLastError
0x1800262d9  cmp     eax, 534h
0x1800262de  jz      short loc_1800262F2
0x1800262e0  mov     r8d, eax
0x1800262e3  lea     rdx, aLookupaccounts; "LookupAccountSidLocal failed: %#x"
0x1800262ea  lea     ecx, [rsi+3]; unsigned __int8
0x1800262ed  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800262f2  xorps   xmm0, xmm0
0x1800262f5  lea     rdx, word_180096C4C
0x1800262fc  movups  xmmword ptr [rdi], xmm0
0x1800262ff  mov     [rdi+10h], rsi
0x180026303  xor     r8d, r8d
0x180026306  mov     [rdi+18h], rsi
0x18002630a  jmp     short loc_180026332
0x18002630c  xorps   xmm0, xmm0
0x18002630f  lea     rax, [rsp+2A0h+Name]
0x180026314  movups  xmmword ptr [rdi], xmm0
0x180026317  mov     [rdi+10h], rsi
0x18002631b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002631f  mov     [rdi+18h], rsi
0x180026323  inc     r8
0x180026326  cmp     [rax+r8*2], si
0x18002632b  jnz     short loc_180026323
0x18002632d  lea     rdx, [rsp+2A0h+Name]
0x180026332  mov     rcx, rdi
0x180026335  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002633a  mov     rax, rdi
0x18002633d  mov     rcx, [rbp+1A0h+var_20]
0x180026344  xor     rcx, rsp; StackCookie
0x180026347  call    __security_check_cookie
0x18002634c  mov     rbx, [rsp+2A0h+arg_10]
0x180026354  add     rsp, 290h
0x18002635b  pop     rdi
0x18002635c  pop     rsi
0x18002635d  pop     rbp
0x18002635e  retn
```
