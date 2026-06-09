# OwningUser2::CreateForUserWorker(void *)

- ea: `0x18005beb4`
- end: `0x18005c1c0`
- name: `?CreateForUserWorker@OwningUser2@@AEAAJPEAX@Z`
- size: `780`
- prototype: `int(OwningUser2 *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c2ac`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x1800050cd`
- `0x1800075e4`
- `0x18000a444`
- `0x180010148`
- `0x18005beb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bf33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bf33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005bfcb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005bf96`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005bf96`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005bf6f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005bf6f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005bef2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005bef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005beff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005beff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bfc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c17c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bf4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bfc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c17c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18005c0bc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18005c0bc`

## string_xrefs

- `0x18005bfe3`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`
- `0x18005c1ae`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`

## pseudocode

```c
__int64 __fastcall OwningUser2::CreateForUserWorker(OwningUser2 *this, void *a2)
{
  PSID v2; // r15
  DWORD LengthSid; // r12d
  const char *v5; // r9
  HLOCAL v6; // r14
  PSID *v7; // rsi
  PSID v8; // r15
  DWORD LastError; // ebx
  __int64 v10; // r8
  const char *v11; // r9
  BOOL v12; // r12d
  LPWSTR v13; // r15
  _QWORD *v14; // rsi
  HLOCAL v15; // r14
  DWORD v16; // ebx
  __int64 v17; // rdx
  unsigned int v18; // ebx
  HLOCAL v20; // r9
  char **v21; // rcx
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdx
  char *v24; // r14
  __int64 v25; // rbx
  __int64 v26; // r8
  char **v27; // rcx
  unsigned __int64 v28; // rdx
  char *v29; // r14
  __int64 v30; // rbx
  __int64 v31; // r8
  char **v32; // rcx
  char *v33; // r14
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSourceSid; // [rsp+48h] [rbp-B8h]
  HLOCAL *p_hMem; // [rsp+50h] [rbp-B0h]
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  char v41; // [rsp+60h] [rbp-A0h]
  char v42; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v44; // [rsp+80h] [rbp-80h]
  __int16 v45; // [rsp+90h] [rbp-70h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v2 = a2;
  pSourceSid = a2;
  LengthSid = GetLengthSid(a2);
  v6 = LocalAlloc(0, LengthSid);
  v7 = (PSID *)((char *)this + 8);
  if ( (char *)this + 8 == &v42 )
  {
    if ( v6 )
      LocalFree(v6);
  }
  else
  {
    v8 = *v7;
    if ( *v7 )
    {
      LastError = GetLastError();
      LocalFree(v8);
      SetLastError(LastError);
    }
    *v7 = v6;
    v2 = pSourceSid;
  }
  if ( !*v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
      v5);
  CopySid(LengthSid, *v7, v2);
  hMem = 0;
  p_hMem = &hMem;
  StringSid = 0;
  v41 = 1;
  v12 = ConvertSidToStringSidW(v2, &StringSid);
  if ( v41 )
  {
    v13 = StringSid;
    v14 = p_hMem;
    v15 = *p_hMem;
    if ( *p_hMem )
    {
      v16 = GetLastError();
      LocalFree(v15);
      SetLastError(v16);
    }
    *v14 = v13;
    v2 = pSourceSid;
  }
  if ( !v12 )
  {
    v17 = 65;
LABEL_14:
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
            v11);
    if ( hMem )
      LocalFree(hMem);
    return v18;
  }
  v20 = hMem;
  v21 = (char **)((char *)this + 16);
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)hMem + v23) );
  if ( v23 > *((_QWORD *)this + 5) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v21,
      v23,
      v10,
      hMem);
  }
  else
  {
    if ( *((_QWORD *)this + 5) <= 7u )
      v24 = (char *)this + 16;
    else
      v24 = *v21;
    *((_QWORD *)this + 4) = v23;
    v25 = 2 * v23;
    memmove_0(v24, v20, 2 * v23);
    *(_WORD *)&v24[v25] = 0;
  }
  memset_0(Name, 0, 0x204u);
  cchName = 257;
  *(_OWORD *)ReferencedDomainName = 0;
  v44 = 0;
  v45 = 0;
  cchReferencedDomainName = 16;
  peUse = 0;
  if ( !LookupAccountSidLocalW(v2, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v17 = 87;
    goto LABEL_14;
  }
  v27 = (char **)((char *)this + 80);
  v28 = -1;
  do
    ++v28;
  while ( ReferencedDomainName[v28] );
  if ( v28 > *((_QWORD *)this + 13) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v27,
      v28,
      v26,
      ReferencedDomainName);
  }
  else
  {
    if ( *((_QWORD *)this + 13) <= 7u )
      v29 = (char *)this + 80;
    else
      v29 = *v27;
    *((_QWORD *)this + 12) = v28;
    v30 = 2 * v28;
    memmove_0(v29, ReferencedDomainName, 2 * v28);
    *(_WORD *)&v29[v30] = 0;
  }
  v32 = (char **)((char *)this + 48);
  do
    ++v22;
  while ( Name[v22] );
  if ( v22 > *((_QWORD *)this + 9) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v32,
      v22,
      v31,
      Name);
  }
  else
  {
    if ( *((_QWORD *)this + 9) <= 7u )
      v33 = (char *)this + 48;
    else
      v33 = *v32;
    *((_QWORD *)this + 8) = v22;
    memmove_0(v33, Name, 2 * v22);
    *(_WORD *)&v33[2 * v22] = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18005beb4  mov     [rsp-8+arg_10], rbx
0x18005beb9  push    rbp
0x18005beba  push    rsi
0x18005bebb  push    rdi
0x18005bebc  push    r12
0x18005bebe  push    r13
0x18005bec0  push    r14
0x18005bec2  push    r15
0x18005bec4  lea     rbp, [rsp-1C0h]
0x18005becc  sub     rsp, 2C0h
0x18005bed3  mov     rax, cs:__security_cookie
0x18005beda  xor     rax, rsp
0x18005bedd  mov     [rbp+1F0h+var_40], rax
0x18005bee4  mov     r15, rdx
0x18005bee7  mov     [rsp+2F0h+pSourceSid], rdx
0x18005beec  mov     r13, rcx
0x18005beef  mov     rcx, rdx; pSid
0x18005bef2  call    cs:__imp_GetLengthSid
0x18005bef8  mov     r12d, eax
0x18005befb  mov     edx, eax; uBytes
0x18005befd  xor     ecx, ecx; uFlags
0x18005beff  call    cs:__imp_LocalAlloc
0x18005bf05  mov     r14, rax
0x18005bf08  lea     rsi, [r13+8]
0x18005bf0c  lea     rax, [rsp+2F0h+var_288]
0x18005bf11  xor     edi, edi
0x18005bf13  cmp     rsi, rax
0x18005bf16  jz      short loc_18005BF43
0x18005bf18  mov     r15, [rsi]
0x18005bf1b  test    r15, r15
0x18005bf1e  jz      short loc_18005BF39
0x18005bf20  call    cs:__imp_GetLastError
0x18005bf26  mov     ebx, eax
0x18005bf28  mov     rcx, r15; hMem
0x18005bf2b  call    cs:__imp_LocalFree
0x18005bf31  mov     ecx, ebx; dwErrCode
0x18005bf33  call    cs:__imp_SetLastError
0x18005bf39  mov     [rsi], r14
0x18005bf3c  mov     r15, [rsp+2F0h+pSourceSid]
0x18005bf41  jmp     short loc_18005BF51
0x18005bf43  test    r14, r14
0x18005bf46  jz      short loc_18005BF51
0x18005bf48  mov     rcx, r14; hMem
0x18005bf4b  call    cs:__imp_LocalFree
0x18005bf51  cmp     [rsi], rdi
0x18005bf54  setz    al
0x18005bf57  mov     rcx, [rbp+1F8h]; this
0x18005bf5e  test    al, al
0x18005bf60  jnz     loc_18005C1AE
0x18005bf66  mov     r8, r15; pSourceSid
0x18005bf69  mov     rdx, [rsi]; pDestinationSid
0x18005bf6c  mov     ecx, r12d; nDestinationSidLength
0x18005bf6f  call    cs:__imp_CopySid
0x18005bf75  mov     [rsp+2F0h+hMem], rdi
0x18005bf7a  lea     rax, [rsp+2F0h+hMem]
0x18005bf7f  mov     [rsp+2F0h+var_2A0], rax
0x18005bf84  mov     [rsp+2F0h+StringSid], rdi
0x18005bf89  mov     [rsp+2F0h+var_290], 1
0x18005bf8e  lea     rdx, [rsp+2F0h+StringSid]; StringSid
0x18005bf93  mov     rcx, r15; Sid
0x18005bf96  call    cs:__imp_ConvertSidToStringSidW
0x18005bf9c  mov     r12d, eax
0x18005bf9f  cmp     [rsp+2F0h+var_290], dil
0x18005bfa4  jz      short loc_18005BFD9
0x18005bfa6  mov     r15, [rsp+2F0h+StringSid]
0x18005bfab  mov     rsi, [rsp+2F0h+var_2A0]
0x18005bfb0  mov     r14, [rsi]
0x18005bfb3  test    r14, r14
0x18005bfb6  jz      short loc_18005BFD1
0x18005bfb8  call    cs:__imp_GetLastError
0x18005bfbe  mov     ebx, eax
0x18005bfc0  mov     rcx, r14; hMem
0x18005bfc3  call    cs:__imp_LocalFree
0x18005bfc9  mov     ecx, ebx; dwErrCode
0x18005bfcb  call    cs:__imp_SetLastError
0x18005bfd1  mov     [rsi], r15
0x18005bfd4  mov     r15, [rsp+2F0h+pSourceSid]
0x18005bfd9  test    r12d, r12d
0x18005bfdc  jnz     short loc_18005C00F
0x18005bfde  lea     edx, [r12+41h]; void *
0x18005bfe3  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005bfea  mov     rcx, [rbp+1F8h]; this
0x18005bff1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005bff6  mov     ebx, eax
0x18005bff8  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18005bffd  test    rcx, rcx
0x18005c000  jz      short loc_18005C008
0x18005c002  call    cs:__imp_LocalFree
0x18005c008  mov     eax, ebx
0x18005c00a  jmp     loc_18005C184
0x18005c00f  mov     r9, [rsp+2F0h+hMem]
0x18005c014  lea     rcx, [r13+10h]
0x18005c018  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005c01c  mov     rdx, rsi
0x18005c01f  inc     rdx
0x18005c022  cmp     [r9+rdx*2], di
0x18005c027  jnz     short loc_18005C01F
0x18005c029  cmp     rdx, [rcx+18h]
0x18005c02d  ja      short loc_18005C05B
0x18005c02f  cmp     qword ptr [rcx+18h], 7
0x18005c034  jbe     short loc_18005C03B
0x18005c036  mov     r14, [rcx]
0x18005c039  jmp     short loc_18005C03E
0x18005c03b  mov     r14, rcx
0x18005c03e  mov     [rcx+10h], rdx
0x18005c042  lea     rbx, [rdx+rdx]
0x18005c046  mov     r8, rbx; Size
0x18005c049  mov     rdx, r9; Src
0x18005c04c  mov     rcx, r14; void *
0x18005c04f  call    memmove_0
0x18005c054  mov     [rbx+r14], di
0x18005c059  jmp     short loc_18005C060
0x18005c05b  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x18005c060  xor     edx, edx; Val
0x18005c062  mov     r8d, 204h; Size
0x18005c068  lea     rcx, [rbp+1F0h+Name]; void *
0x18005c06c  call    memset_0
0x18005c071  mov     [rsp+2F0h+cchName], 101h
0x18005c079  xorps   xmm0, xmm0
0x18005c07c  xor     eax, eax
0x18005c07e  movups  xmmword ptr [rsp+2F0h+ReferencedDomainName], xmm0
0x18005c083  movups  [rbp+1F0h+var_270], xmm0
0x18005c087  mov     [rbp+1F0h+var_260], ax
0x18005c08b  mov     [rsp+2F0h+var_2B4], 10h
0x18005c093  mov     [rsp+2F0h+var_2B8], edi
0x18005c097  lea     rax, [rsp+2F0h+var_2B8]
0x18005c09c  mov     [rsp+2F0h+peUse], rax; peUse
0x18005c0a1  lea     rax, [rsp+2F0h+var_2B4]
0x18005c0a6  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18005c0ab  lea     r9, [rsp+2F0h+ReferencedDomainName]; ReferencedDomainName
0x18005c0b0  lea     r8, [rsp+2F0h+cchName]; cchName
0x18005c0b5  lea     rdx, [rbp+1F0h+Name]; Name
0x18005c0b9  mov     rcx, r15; Sid
0x18005c0bc  call    cs:__imp_LookupAccountSidLocalW
0x18005c0c2  test    eax, eax
0x18005c0c4  jnz     short loc_18005C0CE
0x18005c0c6  lea     edx, [rax+57h]
0x18005c0c9  jmp     loc_18005BFE3
0x18005c0ce  lea     rcx, [r13+50h]
0x18005c0d2  lea     rax, [rsp+2F0h+ReferencedDomainName]
0x18005c0d7  mov     rdx, rsi
0x18005c0da  inc     rdx
0x18005c0dd  cmp     [rax+rdx*2], di
0x18005c0e1  jnz     short loc_18005C0DA
0x18005c0e3  cmp     rdx, [rcx+18h]
0x18005c0e7  ja      short loc_18005C117
0x18005c0e9  cmp     qword ptr [rcx+18h], 7
0x18005c0ee  jbe     short loc_18005C0F5
0x18005c0f0  mov     r14, [rcx]
0x18005c0f3  jmp     short loc_18005C0F8
0x18005c0f5  mov     r14, rcx
0x18005c0f8  mov     [rcx+10h], rdx
0x18005c0fc  lea     rbx, [rdx+rdx]
0x18005c100  mov     r8, rbx; Size
0x18005c103  lea     rdx, [rsp+2F0h+ReferencedDomainName]; Src
0x18005c108  mov     rcx, r14; void *
0x18005c10b  call    memmove_0
0x18005c110  mov     [rbx+r14], di
0x18005c115  jmp     short loc_18005C121
0x18005c117  lea     r9, [rsp+2F0h+ReferencedDomainName]
0x18005c11c  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x18005c121  lea     rcx, [r13+30h]
0x18005c125  lea     rax, [rbp+1F0h+Name]
0x18005c129  inc     rsi
0x18005c12c  cmp     [rax+rsi*2], di
0x18005c130  jnz     short loc_18005C129
0x18005c132  cmp     rsi, [rcx+18h]
0x18005c136  ja      short loc_18005C165
0x18005c138  cmp     qword ptr [rcx+18h], 7
0x18005c13d  jbe     short loc_18005C144
0x18005c13f  mov     r14, [rcx]
0x18005c142  jmp     short loc_18005C147
0x18005c144  mov     r14, rcx
0x18005c147  mov     [rcx+10h], rsi
0x18005c14b  lea     rbx, [rsi+rsi]
0x18005c14f  mov     r8, rbx; Size
0x18005c152  lea     rdx, [rbp+1F0h+Name]; Src
0x18005c156  mov     rcx, r14; void *
0x18005c159  call    memmove_0
0x18005c15e  mov     [rbx+r14], di
0x18005c163  jmp     short loc_18005C172
0x18005c165  lea     r9, [rbp+1F0h+Name]
0x18005c169  mov     rdx, rsi
0x18005c16c  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x18005c171  nop
0x18005c172  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18005c177  test    rcx, rcx
0x18005c17a  jz      short loc_18005C182
0x18005c17c  call    cs:__imp_LocalFree
0x18005c182  xor     eax, eax
0x18005c184  mov     rcx, [rbp+1F0h+var_40]
0x18005c18b  xor     rcx, rsp; StackCookie
0x18005c18e  call    __security_check_cookie
0x18005c193  mov     rbx, [rsp+2F0h+arg_10]
0x18005c19b  add     rsp, 2C0h
0x18005c1a2  pop     r15
0x18005c1a4  pop     r14
0x18005c1a6  pop     r13
0x18005c1a8  pop     r12
0x18005c1aa  pop     rdi
0x18005c1ab  pop     rsi
0x18005c1ac  pop     rbp
0x18005c1ad  retn
0x18005c1ae  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005c1b5  mov     edx, 3Ah ; ':'; void *
0x18005c1ba  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
