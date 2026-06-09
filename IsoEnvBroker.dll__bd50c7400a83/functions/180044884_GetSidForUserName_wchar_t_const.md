# GetSidForUserName(wchar_t const *)

- ea: `0x180044884`
- end: `0x180044a5f`
- name: `?GetSidForUserName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z`
- size: `475`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040d30`
- `0x1800414dc`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180011e18`
- `0x180014c04`
- `0x180044884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004491b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004491b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800449b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800449b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180044981`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180044981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800449ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800449ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044a2f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180044911`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180044911`

## string_xrefs

- `0x1800449d0`: `ConvertSidToStringSid failed for %s: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall GetSidForUserName(_QWORD *a1, const WCHAR *a2)
{
  DWORD v4; // eax
  BOOL v5; // r12d
  LPWSTR v6; // r15
  _QWORD *v7; // rsi
  HLOCAL v8; // r14
  DWORD LastError; // ebx
  DWORD v10; // eax
  unsigned __int64 v11; // r8
  const WCHAR *v12; // rdx
  HLOCAL hMem; // [rsp+30h] [rbp-99h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-91h] BYREF
  DWORD cchReferencedDomainName; // [rsp+3Ch] [rbp-8Dh] BYREF
  DWORD cbSid; // [rsp+40h] [rbp-89h] BYREF
  HLOCAL *p_hMem; // [rsp+48h] [rbp-81h]
  LPWSTR StringSid; // [rsp+50h] [rbp-79h] BYREF
  char v20; // [rsp+58h] [rbp-71h]
  WCHAR ReferencedDomainName[8]; // [rsp+68h] [rbp-61h] BYREF
  __int128 v22; // [rsp+78h] [rbp-51h]
  __int16 v23; // [rsp+88h] [rbp-41h]
  _BYTE Sid[80]; // [rsp+90h] [rbp-39h] BYREF

  hMem = a1;
  *(_OWORD *)ReferencedDomainName = 0;
  v22 = 0;
  v23 = 0;
  cchReferencedDomainName = 16;
  peUse = 0;
  memset_0(Sid, 0, 0x44u);
  cbSid = 68;
  if ( LookupAccountNameLocalW(a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    hMem = 0;
    p_hMem = &hMem;
    StringSid = 0;
    v20 = 1;
    v5 = ConvertSidToStringSidW(Sid, &StringSid);
    if ( v20 )
    {
      v6 = StringSid;
      v7 = p_hMem;
      v8 = *p_hMem;
      if ( *p_hMem )
      {
        LastError = GetLastError();
        LocalFree(v8);
        SetLastError(LastError);
      }
      *v7 = v6;
    }
    if ( v5 )
    {
      v12 = (const WCHAR *)hMem;
      *(_OWORD *)a1 = 0;
      a1[2] = 0;
      a1[3] = 0;
      v11 = -1;
      do
        ++v11;
      while ( v12[v11] );
    }
    else
    {
      v10 = GetLastError();
      Log(2u, L"ConvertSidToStringSid failed for %s: %#x", a2, v10);
      *(_OWORD *)a1 = 0;
      a1[2] = 0;
      a1[3] = 0;
      v11 = 0;
      v12 = &word_180096C4C;
    }
    std::wstring::_Construct<1,wchar_t const *>((char **)a1, v12, v11);
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    v4 = GetLastError();
    if ( v4 != 1332 )
      Log(3u, L"LookupAccountNameLocal failed for %s: %#x", a2, v4);
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)a1, &word_180096C4C, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x180044884  mov     [rsp-8+arg_10], rbx
0x180044889  push    rbp
0x18004488a  push    rsi
0x18004488b  push    rdi
0x18004488c  push    r12
0x18004488e  push    r13
0x180044890  push    r14
0x180044892  push    r15
0x180044894  lea     rbp, [rsp-27h]
0x180044899  sub     rsp, 0F0h
0x1800448a0  mov     rax, cs:__security_cookie
0x1800448a7  xor     rax, rsp
0x1800448aa  mov     [rbp+57h+var_40], rax
0x1800448ae  mov     r13, rdx
0x1800448b1  mov     rdi, rcx
0x1800448b4  mov     [rsp+120h+hMem], rcx
0x1800448b9  xor     esi, esi
0x1800448bb  xorps   xmm0, xmm0
0x1800448be  xor     eax, eax
0x1800448c0  movups  xmmword ptr [rbp+57h+ReferencedDomainName], xmm0
0x1800448c4  movups  [rbp+57h+var_A8], xmm0
0x1800448c8  mov     [rbp+57h+var_98], ax
0x1800448cc  mov     [rsp+120h+var_E4], 10h
0x1800448d4  mov     [rsp+120h+var_E8], esi
0x1800448d8  lea     ebx, [rsi+44h]
0x1800448db  mov     r8d, ebx; Size
0x1800448de  xor     edx, edx; Val
0x1800448e0  lea     rcx, [rbp+57h+Sid]; void *
0x1800448e4  call    memset_0
0x1800448e9  mov     [rsp+120h+cbSid], ebx
0x1800448ed  lea     rax, [rsp+120h+var_E8]
0x1800448f2  mov     [rsp+120h+peUse], rax; peUse
0x1800448f7  lea     rax, [rsp+120h+var_E4]
0x1800448fc  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180044901  lea     r9, [rbp+57h+ReferencedDomainName]; ReferencedDomainName
0x180044905  lea     r8, [rsp+120h+cbSid]; cbSid
0x18004490a  lea     rdx, [rbp+57h+Sid]; Sid
0x18004490e  mov     rcx, r13; lpAccountName
0x180044911  call    cs:__imp_LookupAccountNameLocalW
0x180044917  test    eax, eax
0x180044919  jnz     short loc_180044962
0x18004491b  call    cs:__imp_GetLastError
0x180044921  cmp     eax, 534h
0x180044926  jz      short loc_18004493D
0x180044928  mov     r9d, eax
0x18004492b  mov     r8, r13
0x18004492e  lea     rdx, aLookupaccountn; "LookupAccountNameLocal failed for %s: %"...
0x180044935  lea     ecx, [rsi+3]; unsigned __int8
0x180044938  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004493d  xorps   xmm0, xmm0
0x180044940  movups  xmmword ptr [rdi], xmm0
0x180044943  mov     [rdi+10h], rsi
0x180044947  mov     [rdi+18h], rsi
0x18004494b  xor     r8d, r8d
0x18004494e  lea     rdx, word_180096C4C
0x180044955  mov     rcx, rdi
0x180044958  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004495d  jmp     loc_180044A35
0x180044962  mov     [rsp+120h+hMem], rsi
0x180044967  lea     rax, [rsp+120h+hMem]
0x18004496c  mov     [rsp+120h+var_D8], rax
0x180044971  mov     [rbp+57h+StringSid], rsi
0x180044975  mov     [rbp+57h+var_C8], 1
0x180044979  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18004497d  lea     rcx, [rbp+57h+Sid]; Sid
0x180044981  call    cs:__imp_ConvertSidToStringSidW
0x180044987  mov     r12d, eax
0x18004498a  cmp     [rbp+57h+var_C8], sil
0x18004498e  jz      short loc_1800449BF
0x180044990  mov     r15, [rbp+57h+StringSid]
0x180044994  mov     rsi, [rsp+120h+var_D8]
0x180044999  mov     r14, [rsi]
0x18004499c  test    r14, r14
0x18004499f  jz      short loc_1800449BA
0x1800449a1  call    cs:__imp_GetLastError
0x1800449a7  mov     ebx, eax
0x1800449a9  mov     rcx, r14; hMem
0x1800449ac  call    cs:__imp_LocalFree
0x1800449b2  mov     ecx, ebx; dwErrCode
0x1800449b4  call    cs:__imp_SetLastError
0x1800449ba  mov     [rsi], r15
0x1800449bd  xor     esi, esi
0x1800449bf  test    r12d, r12d
0x1800449c2  jnz     short loc_1800449FB
0x1800449c4  call    cs:__imp_GetLastError
0x1800449ca  mov     r9d, eax
0x1800449cd  mov     r8, r13
0x1800449d0  lea     rdx, aConvertsidtost; "ConvertSidToStringSid failed for %s: %#"...
0x1800449d7  lea     ecx, [r12+2]; unsigned __int8
0x1800449dc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800449e1  xorps   xmm0, xmm0
0x1800449e4  movups  xmmword ptr [rdi], xmm0
0x1800449e7  mov     [rdi+10h], rsi
0x1800449eb  mov     [rdi+18h], rsi
0x1800449ef  xor     r8d, r8d
0x1800449f2  lea     rdx, word_180096C4C
0x1800449f9  jmp     short loc_180044A1C
0x1800449fb  mov     rdx, [rsp+120h+hMem]
0x180044a00  xorps   xmm0, xmm0
0x180044a03  movups  xmmword ptr [rdi], xmm0
0x180044a06  mov     [rdi+10h], rsi
0x180044a0a  mov     [rdi+18h], rsi
0x180044a0e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044a12  inc     r8
0x180044a15  cmp     [rdx+r8*2], si
0x180044a1a  jnz     short loc_180044A12
0x180044a1c  mov     rcx, rdi
0x180044a1f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180044a24  nop
0x180044a25  mov     rcx, [rsp+120h+hMem]; hMem
0x180044a2a  test    rcx, rcx
0x180044a2d  jz      short loc_180044A35
0x180044a2f  call    cs:__imp_LocalFree
0x180044a35  mov     rax, rdi
0x180044a38  mov     rcx, [rbp+57h+var_40]
0x180044a3c  xor     rcx, rsp; StackCookie
0x180044a3f  call    __security_check_cookie
0x180044a44  mov     rbx, [rsp+120h+arg_10]
0x180044a4c  add     rsp, 0F0h
0x180044a53  pop     r15
0x180044a55  pop     r14
0x180044a57  pop     r13
0x180044a59  pop     r12
0x180044a5b  pop     rdi
0x180044a5c  pop     rsi
0x180044a5d  pop     rbp
0x180044a5e  retn
```
