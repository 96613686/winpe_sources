# LsaAgentAccountHelper::GetSingleUseAgentUserCred(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180044a68`
- end: `0x180044d94`
- name: `?GetSingleUseAgentUserCred@LsaAgentAccountHelper@@QEAAJPEB_W0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@11@Z`
- size: `812`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180041b64`
- `0x180049a50`

## callees

- `0x1800050cd`
- `0x1800075e4`
- `0x180010148`
- `0x180011e18`
- `0x180044a68`
- `0x180046af8`
- `0x180046bf4`
- `0x18006389c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180044aa1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180044ac1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180044aa1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180044ac1`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044ba3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044cec`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044d3d`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044ba3`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044cec`
- `SspiCli!LsaFreeReturnBuffer` at `0x180044d3d`
- `SspiCli!SspiEncodeAuthIdentityAsStrings` at `0x180044b4d`
- `SspiCli!SspiEncodeAuthIdentityAsStrings` at `0x180044b4d`
- `SspiCli!SspiLocalFree` at `0x180044b7a`
- `SspiCli!SspiLocalFree` at `0x180044b89`
- `SspiCli!SspiLocalFree` at `0x180044b98`
- `SspiCli!SspiLocalFree` at `0x180044cc3`
- `SspiCli!SspiLocalFree` at `0x180044cd2`
- `SspiCli!SspiLocalFree` at `0x180044ce1`
- `SspiCli!SspiLocalFree` at `0x180044d14`
- `SspiCli!SspiLocalFree` at `0x180044d23`
- `SspiCli!SspiLocalFree` at `0x180044d32`
- `SspiCli!SspiLocalFree` at `0x180044b7a`
- `SspiCli!SspiLocalFree` at `0x180044b89`
- `SspiCli!SspiLocalFree` at `0x180044b98`
- `SspiCli!SspiLocalFree` at `0x180044cc3`
- `SspiCli!SspiLocalFree` at `0x180044cd2`
- `SspiCli!SspiLocalFree` at `0x180044ce1`
- `SspiCli!SspiLocalFree` at `0x180044d14`
- `SspiCli!SspiLocalFree` at `0x180044d23`
- `SspiCli!SspiLocalFree` at `0x180044d32`

## string_xrefs

- `0x180044d5b`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x180044d6d`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x180044d82`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x180044b5f`: `Failed to encode agent cred for AU %s: %#x`
- `0x180044cf9`: `Encoded agent cred for AU %s is missing username or password`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall LsaAgentAccountHelper::GetSingleUseAgentUserCred(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        char *a4,
        char **a5,
        char **a6)
{
  NTSTATUS inited; // eax
  NTSTATUS v10; // eax
  int v11; // eax
  unsigned int v12; // r8d
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // ebx
  PCWSTR v17; // r9
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rdx
  char *v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // r8
  PCWSTR v23; // r9
  unsigned __int64 v24; // rdx
  char *v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // r8
  PCWSTR v28; // r9
  char *v29; // rsi
  PCWSTR ppszPackedCredentialsString; // [rsp+20h] [rbp-59h] BYREF
  PCWSTR ppszDomainName; // [rsp+28h] [rbp-51h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity[2]; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING v33; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE *v35; // [rsp+60h] [rbp-19h]
  char v36; // [rsp+68h] [rbp-11h]
  PCWSTR *p_ppszUserName; // [rsp+70h] [rbp-9h]
  PCWSTR *p_ppszDomainName; // [rsp+78h] [rbp-1h]
  PCWSTR *p_ppszPackedCredentialsString; // [rsp+80h] [rbp+7h]
  char v40; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  PCWSTR ppszUserName; // [rsp+D0h] [rbp+57h] BYREF

  if ( !*(_BYTE *)a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xA7,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      a4);
  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( inited < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)inited,
      (int)ppszPackedCredentialsString);
  v33 = 0;
  v10 = RtlInitUnicodeStringEx(&v33, a3);
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)v10,
      (int)ppszPackedCredentialsString);
  *(_OWORD *)pAuthIdentity = 0;
  v11 = LsaRetrieveAgentLogonCredential(*(_QWORD *)(a1 + 8), &DestinationString, &v33, pAuthIdentity);
  if ( v11 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xB4,
             v12,
             (const char *)(unsigned int)v11,
             (int)ppszPackedCredentialsString);
  v35 = pAuthIdentity;
  v36 = 1;
  ppszUserName = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  p_ppszUserName = &ppszUserName;
  p_ppszDomainName = &ppszDomainName;
  p_ppszPackedCredentialsString = &ppszPackedCredentialsString;
  v40 = 1;
  v14 = SspiEncodeAuthIdentityAsStrings(pAuthIdentity[1], &ppszUserName, &ppszDomainName, &ppszPackedCredentialsString);
  v16 = v14;
  if ( v14 )
  {
    Log(2u, L"Failed to encode agent cred for AU %s: %#x", a3, v14);
    if ( ppszUserName )
      SspiLocalFree((PVOID)ppszUserName);
    if ( ppszDomainName )
      SspiLocalFree((PVOID)ppszDomainName);
    if ( ppszPackedCredentialsString )
      SspiLocalFree((PVOID)ppszPackedCredentialsString);
    LsaFreeReturnBuffer(pAuthIdentity[1]);
    return v16;
  }
  else if ( ppszUserName && ppszPackedCredentialsString )
  {
    v17 = &word_180096C4C;
    if ( ppszDomainName )
      v17 = ppszDomainName;
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( v17[v19] );
    if ( v19 > (unsigned __int64)a5[3] )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
        a5,
        v19,
        v15,
        v17);
    }
    else
    {
      if ( (unsigned __int64)a5[3] <= 7 )
        v20 = (char *)a5;
      else
        v20 = *a5;
      a5[2] = (char *)v19;
      v21 = 2 * v19;
      memmove_0(v20, v17, 2 * v19);
      *(_WORD *)&v20[v21] = 0;
    }
    v23 = ppszUserName;
    v24 = -1;
    do
      ++v24;
    while ( ppszUserName[v24] );
    if ( v24 > *((_QWORD *)a4 + 3) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
        (char **)a4,
        v24,
        v22,
        ppszUserName);
    }
    else
    {
      if ( *((_QWORD *)a4 + 3) <= 7u )
        v25 = a4;
      else
        v25 = *(char **)a4;
      *((_QWORD *)a4 + 2) = v24;
      v26 = 2 * v24;
      memmove_0(v25, v23, 2 * v24);
      *(_WORD *)&v25[v26] = 0;
    }
    v28 = ppszPackedCredentialsString;
    do
      ++v18;
    while ( ppszPackedCredentialsString[v18] );
    if ( v18 > (unsigned __int64)a6[3] )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
        a6,
        v18,
        v27,
        ppszPackedCredentialsString);
    }
    else
    {
      if ( (unsigned __int64)a6[3] <= 7 )
        v29 = (char *)a6;
      else
        v29 = *a6;
      a6[2] = (char *)v18;
      memmove_0(v29, v28, 2 * v18);
      *(_WORD *)&v29[2 * v18] = 0;
    }
    if ( ppszUserName )
      SspiLocalFree((PVOID)ppszUserName);
    if ( ppszDomainName )
      SspiLocalFree((PVOID)ppszDomainName);
    if ( ppszPackedCredentialsString )
      SspiLocalFree((PVOID)ppszPackedCredentialsString);
    LsaFreeReturnBuffer(pAuthIdentity[1]);
    return 0;
  }
  else
  {
    Log(2u, L"Encoded agent cred for AU %s is missing username or password", a3);
    if ( ppszUserName )
      SspiLocalFree((PVOID)ppszUserName);
    if ( ppszDomainName )
      SspiLocalFree((PVOID)ppszDomainName);
    if ( ppszPackedCredentialsString )
      SspiLocalFree((PVOID)ppszPackedCredentialsString);
    LsaFreeReturnBuffer(pAuthIdentity[1]);
    return -2147418113;
  }
}

```

## disassembly

```asm
0x180044a68  push    rbp
0x180044a6a  push    rbx
0x180044a6b  push    rsi
0x180044a6c  push    rdi
0x180044a6d  push    r14
0x180044a6f  push    r15
0x180044a71  lea     rbp, [rsp-1Fh]
0x180044a76  sub     rsp, 98h
0x180044a7d  mov     r14, r9
0x180044a80  mov     rdi, r8
0x180044a83  mov     rbx, rcx
0x180044a86  mov     rcx, [rbp+4Fh]; this
0x180044a8a  xor     r15d, r15d
0x180044a8d  cmp     [rbx], r15b
0x180044a90  jz      loc_180044D6D
0x180044a96  xorps   xmm0, xmm0
0x180044a99  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180044a9d  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180044aa1  call    cs:__imp_RtlInitUnicodeStringEx
0x180044aa7  mov     rcx, [rbp+4Fh]; this
0x180044aab  test    eax, eax
0x180044aad  js      loc_180044D7F
0x180044ab3  xorps   xmm0, xmm0
0x180044ab6  movups  xmmword ptr [rbp+47h+var_80.Length], xmm0
0x180044aba  mov     rdx, rdi; SourceString
0x180044abd  lea     rcx, [rbp+47h+var_80]; DestinationString
0x180044ac1  call    cs:__imp_RtlInitUnicodeStringEx
0x180044ac7  mov     rcx, [rbp+4Fh]; this
0x180044acb  test    eax, eax
0x180044acd  js      loc_180044D58
0x180044ad3  xorps   xmm0, xmm0
0x180044ad6  movups  xmmword ptr [rbp+47h+pAuthIdentity], xmm0
0x180044ada  lea     r9, [rbp+47h+pAuthIdentity]
0x180044ade  lea     r8, [rbp+47h+var_80]
0x180044ae2  lea     rdx, [rbp+47h+DestinationString]
0x180044ae6  mov     rcx, [rbx+8]
0x180044aea  call    LsaRetrieveAgentLogonCredential
0x180044aef  test    eax, eax
0x180044af1  jns     short loc_180044B09
0x180044af3  mov     rcx, [rbp+4Fh]; this
0x180044af7  mov     r9d, eax; char *
0x180044afa  mov     edx, 0B4h; void *
0x180044aff  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180044b04  jmp     loc_180044D48
0x180044b09  lea     rax, [rbp+47h+pAuthIdentity]
0x180044b0d  mov     [rbp+47h+var_60], rax
0x180044b11  mov     [rbp+47h+var_58], 1
0x180044b15  mov     [rbp+47h+ppszUserName], r15
0x180044b19  mov     [rbp+47h+ppszDomainName], r15
0x180044b1d  mov     [rbp+47h+ppszPackedCredentialsString], r15
0x180044b21  lea     rax, [rbp+47h+ppszUserName]
0x180044b25  mov     [rbp+47h+var_50], rax
0x180044b29  lea     rax, [rbp+47h+ppszDomainName]
0x180044b2d  mov     [rbp+47h+var_48], rax
0x180044b31  lea     rax, [rbp+47h+ppszPackedCredentialsString]
0x180044b35  mov     [rbp+47h+var_40], rax
0x180044b39  mov     [rbp+47h+var_38], 1
0x180044b3d  lea     r9, [rbp+47h+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x180044b41  lea     r8, [rbp+47h+ppszDomainName]; ppszDomainName
0x180044b45  lea     rdx, [rbp+47h+ppszUserName]; ppszUserName
0x180044b49  mov     rcx, [rbp+47h+pAuthIdentity+8]; pAuthIdentity
0x180044b4d  call    cs:__imp_SspiEncodeAuthIdentityAsStrings
0x180044b53  mov     ebx, eax
0x180044b55  test    eax, eax
0x180044b57  jz      short loc_180044BB0
0x180044b59  mov     r9d, eax
0x180044b5c  mov     r8, rdi
0x180044b5f  lea     rdx, aFailedToEncode; "Failed to encode agent cred for AU %s: "...
0x180044b66  mov     ecx, 2; unsigned __int8
0x180044b6b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180044b70  nop
0x180044b71  mov     rcx, [rbp+47h+ppszUserName]; DataBuffer
0x180044b75  test    rcx, rcx
0x180044b78  jz      short loc_180044B80
0x180044b7a  call    cs:__imp_SspiLocalFree
0x180044b80  mov     rcx, [rbp+47h+ppszDomainName]; DataBuffer
0x180044b84  test    rcx, rcx
0x180044b87  jz      short loc_180044B8F
0x180044b89  call    cs:__imp_SspiLocalFree
0x180044b8f  mov     rcx, [rbp+47h+ppszPackedCredentialsString]; DataBuffer
0x180044b93  test    rcx, rcx
0x180044b96  jz      short loc_180044B9F
0x180044b98  call    cs:__imp_SspiLocalFree
0x180044b9e  nop
0x180044b9f  mov     rcx, [rbp+47h+pAuthIdentity+8]; Buffer
0x180044ba3  call    cs:__imp_LsaFreeReturnBuffer
0x180044ba9  mov     eax, ebx
0x180044bab  jmp     loc_180044D48
0x180044bb0  cmp     [rbp+47h+ppszUserName], r15
0x180044bb4  jz      loc_180044CF6
0x180044bba  cmp     [rbp+47h+ppszPackedCredentialsString], r15
0x180044bbe  jz      loc_180044CF6
0x180044bc4  lea     r9, word_180096C4C
0x180044bcb  mov     rax, [rbp+47h+ppszDomainName]
0x180044bcf  test    rax, rax
0x180044bd2  cmovnz  r9, rax
0x180044bd6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180044bda  mov     rdx, rdi
0x180044bdd  inc     rdx
0x180044be0  cmp     [r9+rdx*2], r15w
0x180044be5  jnz     short loc_180044BDD
0x180044be7  mov     rcx, [rbp+47h+arg_20]
0x180044beb  cmp     rdx, [rcx+18h]
0x180044bef  ja      short loc_180044C1D
0x180044bf1  cmp     qword ptr [rcx+18h], 7
0x180044bf6  jbe     short loc_180044BFD
0x180044bf8  mov     rsi, [rcx]
0x180044bfb  jmp     short loc_180044C00
0x180044bfd  mov     rsi, rcx
0x180044c00  mov     [rcx+10h], rdx
0x180044c04  lea     rbx, [rdx+rdx]
0x180044c08  mov     r8, rbx; Size
0x180044c0b  mov     rdx, r9; Src
0x180044c0e  mov     rcx, rsi; void *
0x180044c11  call    memmove_0
0x180044c16  mov     [rbx+rsi], r15w
0x180044c1b  jmp     short loc_180044C22
0x180044c1d  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180044c22  mov     r9, [rbp+47h+ppszUserName]
0x180044c26  mov     rdx, rdi
0x180044c29  inc     rdx
0x180044c2c  cmp     [r9+rdx*2], r15w
0x180044c31  jnz     short loc_180044C29
0x180044c33  cmp     rdx, [r14+18h]
0x180044c37  ja      short loc_180044C65
0x180044c39  cmp     qword ptr [r14+18h], 7
0x180044c3e  jbe     short loc_180044C45
0x180044c40  mov     rsi, [r14]
0x180044c43  jmp     short loc_180044C48
0x180044c45  mov     rsi, r14
0x180044c48  mov     [r14+10h], rdx
0x180044c4c  lea     rbx, [rdx+rdx]
0x180044c50  mov     r8, rbx; Size
0x180044c53  mov     rdx, r9; Src
0x180044c56  mov     rcx, rsi; void *
0x180044c59  call    memmove_0
0x180044c5e  mov     [rbx+rsi], r15w
0x180044c63  jmp     short loc_180044C6D
0x180044c65  mov     rcx, r14
0x180044c68  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180044c6d  mov     r9, [rbp+47h+ppszPackedCredentialsString]
0x180044c71  inc     rdi
0x180044c74  cmp     [r9+rdi*2], r15w
0x180044c79  jnz     short loc_180044C71
0x180044c7b  mov     rcx, [rbp+47h+arg_28]
0x180044c7f  cmp     rdi, [rcx+18h]
0x180044c83  ja      short loc_180044CB1
0x180044c85  cmp     qword ptr [rcx+18h], 7
0x180044c8a  jbe     short loc_180044C91
0x180044c8c  mov     rsi, [rcx]
0x180044c8f  jmp     short loc_180044C94
0x180044c91  mov     rsi, rcx
0x180044c94  mov     [rcx+10h], rdi
0x180044c98  lea     rbx, [rdi+rdi]
0x180044c9c  mov     r8, rbx; Size
0x180044c9f  mov     rdx, r9; Src
0x180044ca2  mov     rcx, rsi; void *
0x180044ca5  call    memmove_0
0x180044caa  mov     [rbx+rsi], r15w
0x180044caf  jmp     short loc_180044CBA
0x180044cb1  mov     rdx, rdi
0x180044cb4  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180044cb9  nop
0x180044cba  mov     rcx, [rbp+47h+ppszUserName]; DataBuffer
0x180044cbe  test    rcx, rcx
0x180044cc1  jz      short loc_180044CC9
0x180044cc3  call    cs:__imp_SspiLocalFree
0x180044cc9  mov     rcx, [rbp+47h+ppszDomainName]; DataBuffer
0x180044ccd  test    rcx, rcx
0x180044cd0  jz      short loc_180044CD8
0x180044cd2  call    cs:__imp_SspiLocalFree
0x180044cd8  mov     rcx, [rbp+47h+ppszPackedCredentialsString]; DataBuffer
0x180044cdc  test    rcx, rcx
0x180044cdf  jz      short loc_180044CE8
0x180044ce1  call    cs:__imp_SspiLocalFree
0x180044ce7  nop
0x180044ce8  mov     rcx, [rbp+47h+pAuthIdentity+8]; Buffer
0x180044cec  call    cs:__imp_LsaFreeReturnBuffer
0x180044cf2  xor     eax, eax
0x180044cf4  jmp     short loc_180044D48
0x180044cf6  mov     r8, rdi
0x180044cf9  lea     rdx, aEncodedAgentCr; "Encoded agent cred for AU %s is missing"...
0x180044d00  mov     ecx, 2; unsigned __int8
0x180044d05  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180044d0a  nop
0x180044d0b  mov     rcx, [rbp+47h+ppszUserName]; DataBuffer
0x180044d0f  test    rcx, rcx
0x180044d12  jz      short loc_180044D1A
0x180044d14  call    cs:__imp_SspiLocalFree
0x180044d1a  mov     rcx, [rbp+47h+ppszDomainName]; DataBuffer
0x180044d1e  test    rcx, rcx
0x180044d21  jz      short loc_180044D29
0x180044d23  call    cs:__imp_SspiLocalFree
0x180044d29  mov     rcx, [rbp+47h+ppszPackedCredentialsString]; DataBuffer
0x180044d2d  test    rcx, rcx
0x180044d30  jz      short loc_180044D39
0x180044d32  call    cs:__imp_SspiLocalFree
0x180044d38  nop
0x180044d39  mov     rcx, [rbp+47h+pAuthIdentity+8]; Buffer
0x180044d3d  call    cs:__imp_LsaFreeReturnBuffer
0x180044d43  mov     eax, 8000FFFFh
0x180044d48  add     rsp, 98h
0x180044d4f  pop     r15
0x180044d51  pop     r14
0x180044d53  pop     rdi
0x180044d54  pop     rsi
0x180044d55  pop     rbx
0x180044d56  pop     rbp
0x180044d57  retn
0x180044d58  mov     r9d, eax; char *
0x180044d5b  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044d62  mov     edx, 0AEh; void *
0x180044d67  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x180044d6d  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044d74  mov     edx, 0A7h; void *
0x180044d79  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180044d7f  mov     r9d, eax; char *
0x180044d82  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044d89  mov     edx, 0AAh; void *
0x180044d8e  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
```
