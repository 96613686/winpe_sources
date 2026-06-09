# AppXMiniRepository::CreatePackageRootKey(Common::COMMON_STRING const *,Common::RegistryKey &)

- ea: `0x18005e090`
- end: `0x18005e352`
- name: `?CreatePackageRootKey@AppXMiniRepository@@QEAAJPEBUCOMMON_STRING@Common@@AEAVRegistryKey@3@@Z`
- size: `706`
- prototype: `int(AppXMiniRepository *__hidden this, const struct Common::COMMON_STRING *, struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d624`

## callees

- `0x18005e090`
- `0x18005e358`
- `0x18005e938`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800ae33c`
- `0x1800f0260`
- `0x1800f10e4`
- `0x1800f18cb`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e2f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e2f3`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18005e1eb`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18005e28b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18005e1eb`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18005e28b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18005e235`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18005e235`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e205`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e2a5`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e205`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e2a5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005e19b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005e19b`

## pseudocode

```c
__int64 __fastcall AppXMiniRepository::CreatePackageRootKey(
        AppXMiniRepository *this,
        const struct Common::COMMON_STRING *a2,
        HKEY *a3)
{
  int LastErrorFailHr; // ebx
  __int64 v7; // rdx
  const WCHAR *v9; // rbx
  LSTATUS Key; // eax
  wil::details *v11; // rcx
  void *v12; // r8
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // eax
  void *v16; // r8
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  __int64 v19; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  SECURITY_INFORMATION SecurityInformation; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v25[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[48]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  if ( !*((_DWORD *)this + 8) )
  {
    LastErrorFailHr = -2147024891;
    v7 = 765;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)LastErrorFailHr,
      dwOptions);
    return (unsigned int)LastErrorFailHr;
  }
  if ( !a2 || !*(_DWORD *)a2 )
  {
    LastErrorFailHr = -2147024809;
    v7 = 768;
    goto LABEL_3;
  }
  v9 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( (unsigned __int64)*a3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(*a3);
  *a3 = 0;
  Key = RegCreateKeyExW_0(*(HKEY *)this, v9, 0, 0, 0, 0xF003Fu, 0, a3, 0);
  LastErrorFailHr = Key;
  if ( Key > 0 )
    LastErrorFailHr = (unsigned __int16)Key | 0x80070000;
  if ( LastErrorFailHr < 0 )
  {
    v7 = 775;
    goto LABEL_3;
  }
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, pSid, &cbSid) )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
    goto LABEL_24;
  }
  pSecurityDescriptor = 0;
  SecurityInformation = 0;
  v13 = AppXMiniRepository::CreateSecurityDescriptorForPackageKey(
          a3,
          pSid,
          v12,
          &SecurityInformation,
          &pSecurityDescriptor);
  LastErrorFailHr = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)v13,
      dwOptionsa);
LABEL_29:
    v19 = 787;
    goto LABEL_23;
  }
  v14 = RegSetKeySecurity(*a3, SecurityInformation, pSecurityDescriptor);
  LastErrorFailHr = v14;
  if ( v14 > 0 )
    LastErrorFailHr = (unsigned __int16)v14 | 0x80070000;
  DestroyPrivateObjectSecurity(&pSecurityDescriptor);
  if ( LastErrorFailHr < 0 )
    goto LABEL_29;
  v25[0] = 2359330;
  v25[1] = L"lpacAppExperience";
  v15 = RtlDeriveCapabilitySidsFromName(v25, v28, v27);
  LastErrorFailHr = v15 | 0x10000000;
  if ( v15 < 0 )
  {
    v19 = 796;
    goto LABEL_23;
  }
  pSecurityDescriptor = 0;
  SecurityInformation = 0;
  v17 = AppXMiniRepository::CreateSecurityDescriptorForPackageKey(
          a3,
          v27,
          v16,
          &SecurityInformation,
          &pSecurityDescriptor);
  LastErrorFailHr = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)v17,
      dwOptionsa);
LABEL_22:
    v19 = 797;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\appxminirepository\\lib\\appxminirepository.cpp",
      (const char *)(unsigned int)LastErrorFailHr,
      dwOptionsa);
LABEL_24:
    AppXMiniRepository::RemovePackage(this, a2);
    return (unsigned int)LastErrorFailHr;
  }
  v18 = RegSetKeySecurity(*a3, SecurityInformation, pSecurityDescriptor);
  LastErrorFailHr = v18;
  if ( v18 > 0 )
    LastErrorFailHr = (unsigned __int16)v18 | 0x80070000;
  DestroyPrivateObjectSecurity(&pSecurityDescriptor);
  if ( LastErrorFailHr < 0 )
    goto LABEL_22;
  return 0;
}

```

## disassembly

```asm
0x18005e090  push    rbp
0x18005e092  push    rbx
0x18005e093  push    rsi
0x18005e094  push    rdi
0x18005e095  push    r14
0x18005e097  lea     rbp, [rsp-40h]
0x18005e09c  sub     rsp, 140h
0x18005e0a3  mov     rax, cs:__security_cookie
0x18005e0aa  xor     rax, rsp
0x18005e0ad  mov     [rbp+60h+var_30], rax
0x18005e0b1  cmp     dword ptr [rcx+20h], 0
0x18005e0b5  mov     rdi, r8
0x18005e0b8  mov     rsi, rdx
0x18005e0bb  mov     r14, rcx
0x18005e0be  jnz     short loc_18005E0F9
0x18005e0c0  mov     ebx, 80070005h
0x18005e0c5  mov     edx, 2FDh; void *
0x18005e0ca  mov     rcx, [rbp+68h]; this
0x18005e0ce  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005e0d5  mov     r9d, ebx; char *
0x18005e0d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e0dd  mov     eax, ebx
0x18005e0df  mov     rcx, [rbp+60h+var_30]
0x18005e0e3  xor     rcx, rsp; StackCookie
0x18005e0e6  call    __security_check_cookie
0x18005e0eb  add     rsp, 140h
0x18005e0f2  pop     r14
0x18005e0f4  pop     rdi
0x18005e0f5  pop     rsi
0x18005e0f6  pop     rbx
0x18005e0f7  pop     rbp
0x18005e0f8  retn
0x18005e0f9  test    rsi, rsi
0x18005e0fc  jz      loc_18005E2DB
0x18005e102  cmp     dword ptr [rdx], 0
0x18005e105  jz      loc_18005E2DB
0x18005e10b  mov     rcx, [r8]; hKey
0x18005e10e  mov     rbx, [rdx+8]
0x18005e112  lea     rax, [rcx-1]
0x18005e116  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005e11a  jbe     loc_18005E2F3
0x18005e120  mov     [rsp+160h+lpdwDisposition], 0; lpdwDisposition
0x18005e129  xor     r9d, r9d; lpClass
0x18005e12c  mov     [rsp+160h+phkResult], rdi; phkResult
0x18005e131  xor     r8d, r8d; Reserved
0x18005e134  mov     [rsp+160h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005e13d  mov     rdx, rbx; lpSubKey
0x18005e140  mov     qword ptr [rdi], 0
0x18005e147  mov     rcx, [r14]; hKey
0x18005e14a  mov     [rsp+160h+samDesired], 0F003Fh; samDesired
0x18005e152  mov     [rsp+160h+dwOptions], 0; dwOptions
0x18005e15a  call    RegCreateKeyExW_0
0x18005e15f  mov     ebx, eax
0x18005e161  test    eax, eax
0x18005e163  jle     short loc_18005E16E
0x18005e165  movzx   ebx, ax
0x18005e168  or      ebx, 80070000h
0x18005e16e  test    ebx, ebx
0x18005e170  js      loc_18005E2FE
0x18005e176  mov     ebx, 44h ; 'D'
0x18005e17b  lea     rcx, [rbp+60h+pSid]; void *
0x18005e17f  mov     r8d, ebx; Size
0x18005e182  xor     edx, edx; Val
0x18005e184  call    memset_0
0x18005e189  lea     r9, [rsp+160h+cbSid]; cbSid
0x18005e18e  mov     [rsp+160h+cbSid], ebx
0x18005e192  lea     r8, [rbp+60h+pSid]; pSid
0x18005e196  xor     edx, edx; DomainSid
0x18005e198  lea     ecx, [rbx+10h]; WellKnownSidType
0x18005e19b  call    cs:__imp_CreateWellKnownSid
0x18005e1a1  test    eax, eax
0x18005e1a3  jz      loc_18005E2EA
0x18005e1a9  lea     rax, [rsp+160h+pSecurityDescriptor]
0x18005e1ae  mov     [rsp+160h+pSecurityDescriptor], 0
0x18005e1b7  lea     r9, [rsp+160h+SecurityInformation]; unsigned int *
0x18005e1bc  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x18005e1c1  lea     rdx, [rbp+60h+pSid]; void *
0x18005e1c5  mov     [rsp+160h+SecurityInformation], 0
0x18005e1cd  mov     rcx, rdi; struct Common::RegistryKey *
0x18005e1d0  call    ?CreateSecurityDescriptorForPackageKey@AppXMiniRepository@@CAJAEAVRegistryKey@Common@@PEAX1PEAKPEAPEAX@Z; AppXMiniRepository::CreateSecurityDescriptorForPackageKey(Common::RegistryKey &,void *,void *,ulong *,void * *)
0x18005e1d5  mov     ebx, eax
0x18005e1d7  test    eax, eax
0x18005e1d9  js      loc_18005E308
0x18005e1df  mov     r8, [rsp+160h+pSecurityDescriptor]; pSecurityDescriptor
0x18005e1e4  mov     edx, [rsp+160h+SecurityInformation]; SecurityInformation
0x18005e1e8  mov     rcx, [rdi]; hKey
0x18005e1eb  call    cs:__imp_RegSetKeySecurity
0x18005e1f1  mov     ebx, eax
0x18005e1f3  test    eax, eax
0x18005e1f5  jle     short loc_18005E200
0x18005e1f7  movzx   ebx, ax
0x18005e1fa  or      ebx, 80070000h
0x18005e200  lea     rcx, [rsp+160h+pSecurityDescriptor]; ObjectDescriptor
0x18005e205  call    cs:__imp_DestroyPrivateObjectSecurity
0x18005e20b  test    ebx, ebx
0x18005e20d  js      loc_18005E320
0x18005e213  lea     rax, aLpacappexperie; "lpacAppExperience"
0x18005e21a  mov     [rsp+160h+var_F8], 240022h
0x18005e223  lea     r8, [rbp+60h+var_90]
0x18005e227  mov     [rsp+160h+var_F0], rax
0x18005e22c  lea     rdx, [rbp+60h+var_60]
0x18005e230  lea     rcx, [rsp+160h+var_F8]
0x18005e235  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18005e23b  mov     ebx, eax
0x18005e23d  or      ebx, 10000000h
0x18005e243  jl      loc_18005E327
0x18005e249  lea     rax, [rsp+160h+pSecurityDescriptor]
0x18005e24e  mov     [rsp+160h+pSecurityDescriptor], 0
0x18005e257  lea     r9, [rsp+160h+SecurityInformation]; unsigned int *
0x18005e25c  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x18005e261  lea     rdx, [rbp+60h+var_90]; void *
0x18005e265  mov     [rsp+160h+SecurityInformation], 0
0x18005e26d  mov     rcx, rdi; struct Common::RegistryKey *
0x18005e270  call    ?CreateSecurityDescriptorForPackageKey@AppXMiniRepository@@CAJAEAVRegistryKey@Common@@PEAX1PEAKPEAPEAX@Z; AppXMiniRepository::CreateSecurityDescriptorForPackageKey(Common::RegistryKey &,void *,void *,ulong *,void * *)
0x18005e275  mov     ebx, eax
0x18005e277  test    eax, eax
0x18005e279  js      loc_18005E32E
0x18005e27f  mov     r8, [rsp+160h+pSecurityDescriptor]; pSecurityDescriptor
0x18005e284  mov     edx, [rsp+160h+SecurityInformation]; SecurityInformation
0x18005e288  mov     rcx, [rdi]; hKey
0x18005e28b  call    cs:__imp_RegSetKeySecurity
0x18005e291  mov     ebx, eax
0x18005e293  test    eax, eax
0x18005e295  jle     short loc_18005E2A0
0x18005e297  movzx   ebx, ax
0x18005e29a  or      ebx, 80070000h
0x18005e2a0  lea     rcx, [rsp+160h+pSecurityDescriptor]; ObjectDescriptor
0x18005e2a5  call    cs:__imp_DestroyPrivateObjectSecurity
0x18005e2ab  test    ebx, ebx
0x18005e2ad  jns     loc_18005E34B
0x18005e2b3  mov     edx, 31Dh; void *
0x18005e2b8  mov     rcx, [rbp+68h]; this
0x18005e2bc  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005e2c3  mov     r9d, ebx; char *
0x18005e2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e2cb  mov     rdx, rsi; struct Common::COMMON_STRING *
0x18005e2ce  mov     rcx, r14; this
0x18005e2d1  call    ?RemovePackage@AppXMiniRepository@@QEAAJPEBUCOMMON_STRING@Common@@@Z; AppXMiniRepository::RemovePackage(Common::COMMON_STRING const *)
0x18005e2d6  jmp     loc_18005E0DD
0x18005e2db  mov     ebx, 80070057h
0x18005e2e0  mov     edx, 300h
0x18005e2e5  jmp     loc_18005E0CA
0x18005e2ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005e2ef  mov     ebx, eax
0x18005e2f1  jmp     short loc_18005E2CB
0x18005e2f3  call    cs:__imp_RegCloseKey
0x18005e2f9  jmp     loc_18005E120
0x18005e2fe  mov     edx, 307h
0x18005e303  jmp     loc_18005E0CA
0x18005e308  mov     rcx, [rbp+68h]; this
0x18005e30c  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005e313  mov     r9d, eax; char *
0x18005e316  mov     edx, 552h; void *
0x18005e31b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e320  mov     edx, 313h
0x18005e325  jmp     short loc_18005E2B8
0x18005e327  mov     edx, 31Ch
0x18005e32c  jmp     short loc_18005E2B8
0x18005e32e  mov     rcx, [rbp+68h]; this
0x18005e332  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\appxminireposi"...
0x18005e339  mov     r9d, eax; char *
0x18005e33c  mov     edx, 552h; void *
0x18005e341  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e346  jmp     loc_18005E2B3
0x18005e34b  xor     eax, eax
0x18005e34d  jmp     loc_18005E0DF
```
