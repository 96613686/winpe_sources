# OwningUser::CreateForUserWorker(void *)

- ea: `0x180035e04`
- end: `0x180036110`
- name: `?CreateForUserWorker@OwningUser@@AEAAJPEAX@Z`
- size: `780`
- prototype: `int(OwningUser *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036254`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x1800050cd`
- `0x1800075e4`
- `0x18000a444`
- `0x180010148`
- `0x180035e04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035f1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035f1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035ee6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180035ee6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180035ebf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180035ebf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035e42`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035e42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035e4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035e4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360cc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003600c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003600c`

## string_xrefs

- `0x180035f33`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`
- `0x1800360fe`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OwningUser::CreateForUserWorker(OwningUser *this, void *a2)
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
      (void *)0x39,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
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
    v17 = 64;
LABEL_14:
    v18 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
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
    v17 = 86;
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
0x180035e04  mov     [rsp-8+arg_10], rbx
0x180035e09  push    rbp
0x180035e0a  push    rsi
0x180035e0b  push    rdi
0x180035e0c  push    r12
0x180035e0e  push    r13
0x180035e10  push    r14
0x180035e12  push    r15
0x180035e14  lea     rbp, [rsp-1C0h]
0x180035e1c  sub     rsp, 2C0h
0x180035e23  mov     rax, cs:__security_cookie
0x180035e2a  xor     rax, rsp
0x180035e2d  mov     [rbp+1F0h+var_40], rax
0x180035e34  mov     r15, rdx
0x180035e37  mov     [rsp+2F0h+pSourceSid], rdx
0x180035e3c  mov     r13, rcx
0x180035e3f  mov     rcx, rdx; pSid
0x180035e42  call    cs:__imp_GetLengthSid
0x180035e48  mov     r12d, eax
0x180035e4b  mov     edx, eax; uBytes
0x180035e4d  xor     ecx, ecx; uFlags
0x180035e4f  call    cs:__imp_LocalAlloc
0x180035e55  mov     r14, rax
0x180035e58  lea     rsi, [r13+8]
0x180035e5c  lea     rax, [rsp+2F0h+var_288]
0x180035e61  xor     edi, edi
0x180035e63  cmp     rsi, rax
0x180035e66  jz      short loc_180035E93
0x180035e68  mov     r15, [rsi]
0x180035e6b  test    r15, r15
0x180035e6e  jz      short loc_180035E89
0x180035e70  call    cs:__imp_GetLastError
0x180035e76  mov     ebx, eax
0x180035e78  mov     rcx, r15; hMem
0x180035e7b  call    cs:__imp_LocalFree
0x180035e81  mov     ecx, ebx; dwErrCode
0x180035e83  call    cs:__imp_SetLastError
0x180035e89  mov     [rsi], r14
0x180035e8c  mov     r15, [rsp+2F0h+pSourceSid]
0x180035e91  jmp     short loc_180035EA1
0x180035e93  test    r14, r14
0x180035e96  jz      short loc_180035EA1
0x180035e98  mov     rcx, r14; hMem
0x180035e9b  call    cs:__imp_LocalFree
0x180035ea1  cmp     [rsi], rdi
0x180035ea4  setz    al
0x180035ea7  mov     rcx, [rbp+1F8h]; this
0x180035eae  test    al, al
0x180035eb0  jnz     loc_1800360FE
0x180035eb6  mov     r8, r15; pSourceSid
0x180035eb9  mov     rdx, [rsi]; pDestinationSid
0x180035ebc  mov     ecx, r12d; nDestinationSidLength
0x180035ebf  call    cs:__imp_CopySid
0x180035ec5  mov     [rsp+2F0h+hMem], rdi
0x180035eca  lea     rax, [rsp+2F0h+hMem]
0x180035ecf  mov     [rsp+2F0h+var_2A0], rax
0x180035ed4  mov     [rsp+2F0h+StringSid], rdi
0x180035ed9  mov     [rsp+2F0h+var_290], 1
0x180035ede  lea     rdx, [rsp+2F0h+StringSid]; StringSid
0x180035ee3  mov     rcx, r15; Sid
0x180035ee6  call    cs:__imp_ConvertSidToStringSidW
0x180035eec  mov     r12d, eax
0x180035eef  cmp     [rsp+2F0h+var_290], dil
0x180035ef4  jz      short loc_180035F29
0x180035ef6  mov     r15, [rsp+2F0h+StringSid]
0x180035efb  mov     rsi, [rsp+2F0h+var_2A0]
0x180035f00  mov     r14, [rsi]
0x180035f03  test    r14, r14
0x180035f06  jz      short loc_180035F21
0x180035f08  call    cs:__imp_GetLastError
0x180035f0e  mov     ebx, eax
0x180035f10  mov     rcx, r14; hMem
0x180035f13  call    cs:__imp_LocalFree
0x180035f19  mov     ecx, ebx; dwErrCode
0x180035f1b  call    cs:__imp_SetLastError
0x180035f21  mov     [rsi], r15
0x180035f24  mov     r15, [rsp+2F0h+pSourceSid]
0x180035f29  test    r12d, r12d
0x180035f2c  jnz     short loc_180035F5F
0x180035f2e  lea     edx, [r12+40h]; void *
0x180035f33  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180035f3a  mov     rcx, [rbp+1F8h]; this
0x180035f41  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035f46  mov     ebx, eax
0x180035f48  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180035f4d  test    rcx, rcx
0x180035f50  jz      short loc_180035F58
0x180035f52  call    cs:__imp_LocalFree
0x180035f58  mov     eax, ebx
0x180035f5a  jmp     loc_1800360D4
0x180035f5f  mov     r9, [rsp+2F0h+hMem]
0x180035f64  lea     rcx, [r13+10h]
0x180035f68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035f6c  mov     rdx, rsi
0x180035f6f  inc     rdx
0x180035f72  cmp     [r9+rdx*2], di
0x180035f77  jnz     short loc_180035F6F
0x180035f79  cmp     rdx, [rcx+18h]
0x180035f7d  ja      short loc_180035FAB
0x180035f7f  cmp     qword ptr [rcx+18h], 7
0x180035f84  jbe     short loc_180035F8B
0x180035f86  mov     r14, [rcx]
0x180035f89  jmp     short loc_180035F8E
0x180035f8b  mov     r14, rcx
0x180035f8e  mov     [rcx+10h], rdx
0x180035f92  lea     rbx, [rdx+rdx]
0x180035f96  mov     r8, rbx; Size
0x180035f99  mov     rdx, r9; Src
0x180035f9c  mov     rcx, r14; void *
0x180035f9f  call    memmove_0
0x180035fa4  mov     [rbx+r14], di
0x180035fa9  jmp     short loc_180035FB0
0x180035fab  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180035fb0  xor     edx, edx; Val
0x180035fb2  mov     r8d, 204h; Size
0x180035fb8  lea     rcx, [rbp+1F0h+Name]; void *
0x180035fbc  call    memset_0
0x180035fc1  mov     [rsp+2F0h+cchName], 101h
0x180035fc9  xorps   xmm0, xmm0
0x180035fcc  xor     eax, eax
0x180035fce  movups  xmmword ptr [rsp+2F0h+ReferencedDomainName], xmm0
0x180035fd3  movups  [rbp+1F0h+var_270], xmm0
0x180035fd7  mov     [rbp+1F0h+var_260], ax
0x180035fdb  mov     [rsp+2F0h+var_2B4], 10h
0x180035fe3  mov     [rsp+2F0h+var_2B8], edi
0x180035fe7  lea     rax, [rsp+2F0h+var_2B8]
0x180035fec  mov     [rsp+2F0h+peUse], rax; peUse
0x180035ff1  lea     rax, [rsp+2F0h+var_2B4]
0x180035ff6  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180035ffb  lea     r9, [rsp+2F0h+ReferencedDomainName]; ReferencedDomainName
0x180036000  lea     r8, [rsp+2F0h+cchName]; cchName
0x180036005  lea     rdx, [rbp+1F0h+Name]; Name
0x180036009  mov     rcx, r15; Sid
0x18003600c  call    cs:__imp_LookupAccountSidLocalW
0x180036012  test    eax, eax
0x180036014  jnz     short loc_18003601E
0x180036016  lea     edx, [rax+56h]
0x180036019  jmp     loc_180035F33
0x18003601e  lea     rcx, [r13+50h]
0x180036022  lea     rax, [rsp+2F0h+ReferencedDomainName]
0x180036027  mov     rdx, rsi
0x18003602a  inc     rdx
0x18003602d  cmp     [rax+rdx*2], di
0x180036031  jnz     short loc_18003602A
0x180036033  cmp     rdx, [rcx+18h]
0x180036037  ja      short loc_180036067
0x180036039  cmp     qword ptr [rcx+18h], 7
0x18003603e  jbe     short loc_180036045
0x180036040  mov     r14, [rcx]
0x180036043  jmp     short loc_180036048
0x180036045  mov     r14, rcx
0x180036048  mov     [rcx+10h], rdx
0x18003604c  lea     rbx, [rdx+rdx]
0x180036050  mov     r8, rbx; Size
0x180036053  lea     rdx, [rsp+2F0h+ReferencedDomainName]; Src
0x180036058  mov     rcx, r14; void *
0x18003605b  call    memmove_0
0x180036060  mov     [rbx+r14], di
0x180036065  jmp     short loc_180036071
0x180036067  lea     r9, [rsp+2F0h+ReferencedDomainName]
0x18003606c  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x180036071  lea     rcx, [r13+30h]
0x180036075  lea     rax, [rbp+1F0h+Name]
0x180036079  inc     rsi
0x18003607c  cmp     [rax+rsi*2], di
0x180036080  jnz     short loc_180036079
0x180036082  cmp     rsi, [rcx+18h]
0x180036086  ja      short loc_1800360B5
0x180036088  cmp     qword ptr [rcx+18h], 7
0x18003608d  jbe     short loc_180036094
0x18003608f  mov     r14, [rcx]
0x180036092  jmp     short loc_180036097
0x180036094  mov     r14, rcx
0x180036097  mov     [rcx+10h], rsi
0x18003609b  lea     rbx, [rsi+rsi]
0x18003609f  mov     r8, rbx; Size
0x1800360a2  lea     rdx, [rbp+1F0h+Name]; Src
0x1800360a6  mov     rcx, r14; void *
0x1800360a9  call    memmove_0
0x1800360ae  mov     [rbx+r14], di
0x1800360b3  jmp     short loc_1800360C2
0x1800360b5  lea     r9, [rbp+1F0h+Name]
0x1800360b9  mov     rdx, rsi
0x1800360bc  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800360c1  nop
0x1800360c2  mov     rcx, [rsp+2F0h+hMem]; hMem
0x1800360c7  test    rcx, rcx
0x1800360ca  jz      short loc_1800360D2
0x1800360cc  call    cs:__imp_LocalFree
0x1800360d2  xor     eax, eax
0x1800360d4  mov     rcx, [rbp+1F0h+var_40]
0x1800360db  xor     rcx, rsp; StackCookie
0x1800360de  call    __security_check_cookie
0x1800360e3  mov     rbx, [rsp+2F0h+arg_10]
0x1800360eb  add     rsp, 2C0h
0x1800360f2  pop     r15
0x1800360f4  pop     r14
0x1800360f6  pop     r13
0x1800360f8  pop     r12
0x1800360fa  pop     rdi
0x1800360fb  pop     rsi
0x1800360fc  pop     rbp
0x1800360fd  retn
0x1800360fe  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180036105  mov     edx, 39h ; '9'; void *
0x18003610a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
