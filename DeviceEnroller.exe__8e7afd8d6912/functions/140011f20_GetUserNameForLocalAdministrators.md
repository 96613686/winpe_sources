# GetUserNameForLocalAdministrators

- ea: `0x140011f20`
- end: `0x14001216f`
- name: `GetUserNameForLocalAdministrators`
- size: `591`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400123f4`
- `0x140013494`

## callees

- `0x1400045a8`
- `0x140004660`
- `0x140004e28`
- `0x140009594`
- `0x1400095b4`
- `0x140011f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fcb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140011fbd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400120e5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140011fbd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400120e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011f73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400120b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001211f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001213d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012150`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011f73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400120b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001211f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001213d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012150`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140011f49`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140011f49`

## pseudocode

```c
__int64 __fastcall GetUserNameForLocalAdministrators(_QWORD *a1)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v5; // rbx
  void *v6; // rax
  void *v7; // rdi
  unsigned __int64 v8; // rsi
  void *v9; // rax
  void *v10; // rbx
  void *v11; // rcx
  const char *v12; // r9
  unsigned int v13; // esi
  int ReferencedDomainName; // [rsp+20h] [rbp-30h]
  PSID Sid; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD cchReferencedDomainName; // [rsp+88h] [rbp+38h] BYREF
  DWORD cchName; // [rsp+90h] [rbp+40h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+98h] [rbp+48h] BYREF

  Sid = 0;
  if ( !ConvertStringSidToSidW(L"S-1-5-32-544", &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x529,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
                  v2);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    if ( Sid )
      LocalFree(Sid);
    return 1;
  }
  else
  {
    v5 = 2LL * (cchName + 1);
    if ( !is_mul_ok(cchName + 1, 2u) )
      v5 = -1;
    v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
      memset_0(v6, 0, v5);
    else
      v7 = 0;
    v8 = 2LL * (cchReferencedDomainName + 1);
    if ( !is_mul_ok(cchReferencedDomainName + 1, 2u) )
      v8 = -1;
    v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
      memset_0(v9, 0, v8);
    else
      v10 = 0;
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)0x8007000ELL,
        ReferencedDomainName);
      if ( !v10 )
      {
LABEL_23:
        if ( Sid )
          LocalFree(Sid);
        return 2147942414LL;
      }
      v11 = v10;
LABEL_22:
      operator delete(v11);
      goto LABEL_23;
    }
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)0x8007000ELL,
        ReferencedDomainName);
      v11 = v7;
      goto LABEL_22;
    }
    if ( LookupAccountSidW(0, Sid, (LPWSTR)v7, &cchName, (LPWSTR)v10, &cchReferencedDomainName, &peUse) )
    {
      *a1 = v7;
      operator delete(v10);
      if ( Sid )
        LocalFree(Sid);
      return 0;
    }
    else
    {
      v13 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x547,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
              v12);
      operator delete(v10);
      operator delete(v7);
      if ( Sid )
        LocalFree(Sid);
      return v13;
    }
  }
}

```

## disassembly

```asm
0x140011f20  mov     [rsp-28h+arg_0], rbx
0x140011f25  push    rbp
0x140011f26  push    rsi
0x140011f27  push    rdi
0x140011f28  push    r12
0x140011f2a  push    r14
0x140011f2c  mov     rbp, rsp
0x140011f2f  sub     rsp, 50h
0x140011f33  mov     r14, rcx
0x140011f36  mov     [rbp+Sid], 0
0x140011f3e  lea     rcx, StringSid; "S-1-5-32-544"
0x140011f45  lea     rdx, [rbp+Sid]; Sid
0x140011f49  call    cs:__imp_ConvertStringSidToSidW
0x140011f4f  test    eax, eax
0x140011f51  jnz     short loc_140011F80
0x140011f53  mov     rcx, [rbp+28h]; this
0x140011f57  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140011f5e  mov     edx, 529h; void *
0x140011f63  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011f68  mov     rcx, [rbp+Sid]; hMem
0x140011f6c  mov     ebx, eax
0x140011f6e  test    rcx, rcx
0x140011f71  jz      short loc_140011F79
0x140011f73  call    cs:__imp_LocalFree
0x140011f79  mov     eax, ebx
0x140011f7b  jmp     loc_14001215B
0x140011f80  mov     rdx, [rbp+Sid]; Sid
0x140011f84  lea     rax, [rbp+arg_18]
0x140011f88  mov     [rsp+50h+peUse], rax; peUse
0x140011f8d  lea     r9, [rbp+cchName]; cchName
0x140011f91  lea     rax, [rbp+arg_8]
0x140011f95  mov     [rbp+cchName], 0
0x140011f9c  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140011fa1  xor     r8d, r8d; Name
0x140011fa4  xor     ecx, ecx; lpSystemName
0x140011fa6  mov     [rsp+50h+ReferencedDomainName], 0; int
0x140011faf  mov     [rbp+arg_8], 0
0x140011fb6  mov     [rbp+arg_18], 0
0x140011fbd  call    cs:__imp_LookupAccountSidW
0x140011fc3  test    eax, eax
0x140011fc5  jnz     loc_140012147
0x140011fcb  call    cs:__imp_GetLastError
0x140011fd1  cmp     eax, 7Ah ; 'z'
0x140011fd4  jnz     loc_140012147
0x140011fda  mov     ecx, [rbp+cchName]
0x140011fdd  lea     esi, [rax-78h]
0x140011fe0  inc     ecx
0x140011fe2  lea     r12, [rsi-3]
0x140011fe6  mov     eax, esi
0x140011fe8  mul     rcx
0x140011feb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011ff2  mov     rbx, rax
0x140011ff5  cmovb   rbx, r12
0x140011ff9  mov     rcx, rbx; unsigned __int64
0x140011ffc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140012001  mov     rdi, rax
0x140012004  test    rax, rax
0x140012007  jz      short loc_140012018
0x140012009  mov     r8, rbx; Size
0x14001200c  xor     edx, edx; Val
0x14001200e  mov     rcx, rax; void *
0x140012011  call    memset_0
0x140012016  jmp     short loc_14001201A
0x140012018  xor     edi, edi
0x14001201a  mov     r8d, [rbp+arg_8]
0x14001201e  mov     rax, rsi
0x140012021  inc     r8d
0x140012024  mul     r8
0x140012027  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001202e  mov     rsi, rax
0x140012031  cmovb   rsi, r12
0x140012035  mov     rcx, rsi; unsigned __int64
0x140012038  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001203d  mov     rbx, rax
0x140012040  test    rax, rax
0x140012043  jz      short loc_140012054
0x140012045  mov     r8, rsi; Size
0x140012048  xor     edx, edx; Val
0x14001204a  mov     rcx, rax; void *
0x14001204d  call    memset_0
0x140012052  jmp     short loc_140012056
0x140012054  xor     ebx, ebx
0x140012056  test    rdi, rdi
0x140012059  jnz     short loc_140012080
0x14001205b  mov     rcx, [rbp+28h]; this
0x14001205f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012066  mov     r9d, 8007000Eh; char *
0x14001206c  mov     edx, 53Bh; void *
0x140012071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012076  test    rbx, rbx
0x140012079  jz      short loc_1400120A8
0x14001207b  mov     rcx, rbx
0x14001207e  jmp     short loc_1400120A3
0x140012080  test    rbx, rbx
0x140012083  jnz     short loc_1400120C1
0x140012085  mov     rcx, [rbp+28h]; this
0x140012089  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140012090  mov     r9d, 8007000Eh; char *
0x140012096  mov     edx, 53Ch; void *
0x14001209b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400120a0  mov     rcx, rdi; Block
0x1400120a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400120a8  mov     rcx, [rbp+Sid]; hMem
0x1400120ac  test    rcx, rcx
0x1400120af  jz      short loc_1400120B7
0x1400120b1  call    cs:__imp_LocalFree
0x1400120b7  mov     eax, 8007000Eh
0x1400120bc  jmp     loc_14001215B
0x1400120c1  mov     rdx, [rbp+Sid]; Sid
0x1400120c5  lea     rax, [rbp+arg_18]
0x1400120c9  mov     [rsp+50h+peUse], rax; peUse
0x1400120ce  lea     r9, [rbp+cchName]; cchName
0x1400120d2  lea     rax, [rbp+arg_8]
0x1400120d6  mov     r8, rdi; Name
0x1400120d9  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400120de  xor     ecx, ecx; lpSystemName
0x1400120e0  mov     [rsp+50h+ReferencedDomainName], rbx; ReferencedDomainName
0x1400120e5  call    cs:__imp_LookupAccountSidW
0x1400120eb  test    eax, eax
0x1400120ed  jnz     short loc_140012129
0x1400120ef  mov     rcx, [rbp+28h]; this
0x1400120f3  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400120fa  mov     edx, 547h; void *
0x1400120ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140012104  mov     rcx, rbx; Block
0x140012107  mov     esi, eax
0x140012109  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001210e  mov     rcx, rdi; Block
0x140012111  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012116  mov     rcx, [rbp+Sid]; hMem
0x14001211a  test    rcx, rcx
0x14001211d  jz      short loc_140012125
0x14001211f  call    cs:__imp_LocalFree
0x140012125  mov     eax, esi
0x140012127  jmp     short loc_14001215B
0x140012129  mov     rcx, rbx; Block
0x14001212c  mov     [r14], rdi
0x14001212f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012134  mov     rcx, [rbp+Sid]; hMem
0x140012138  test    rcx, rcx
0x14001213b  jz      short loc_140012143
0x14001213d  call    cs:__imp_LocalFree
0x140012143  xor     eax, eax
0x140012145  jmp     short loc_14001215B
0x140012147  mov     rcx, [rbp+Sid]; hMem
0x14001214b  test    rcx, rcx
0x14001214e  jz      short loc_140012156
0x140012150  call    cs:__imp_LocalFree
0x140012156  mov     eax, 1
0x14001215b  mov     rbx, [rsp+50h+arg_0]
0x140012163  add     rsp, 50h
0x140012167  pop     r14
0x140012169  pop     r12
0x14001216b  pop     rdi
0x14001216c  pop     rsi
0x14001216d  pop     rbp
0x14001216e  retn
```
