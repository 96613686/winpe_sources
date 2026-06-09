# WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess

- ea: `0x180098b70`
- end: `0x180098cc2`
- name: `WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess`
- size: `338`
- prototype: `__int64 __usercall@<rax>(PSID pSid1@<rcx>, PACL OldAcl@<rdx>, PACL *NewAcl)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180098cc8`

## callees

- `0x180098228`
- `0x180098b70`
- `0x18009a680`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180098c23`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180098c23`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180098bd0`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x180098bd0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180098c7e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180098c7e`

## pseudocode

```c
__int64 WindowsInternal::TextInputSettings::SettingsManager::EnsureAccess(PSID pSid1, PACL OldAcl, __int64 a3, ...)
{
  PACL *v3; // rsi
  DWORD ExplicitEntriesFromAclW; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  int v9; // r12d
  __int64 i; // r14
  PEXPLICIT_ACCESS_W v11; // rdi
  TRUSTEE_FORM TrusteeForm; // eax
  LPWCH ptstrName; // rdx
  unsigned int v14; // ebx
  struct _EXPLICIT_ACCESS_W v16; // [rsp+20h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  ULONG pcCountOfExplicitEntries; // [rsp+A0h] [rbp+50h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A8h] [rbp+58h] BYREF
  va_list pListOfExplicitEntriesa; // [rsp+A8h] [rbp+58h]
  PACL *NewAcl; // [rsp+B0h] [rbp+60h]
  va_list va1; // [rsp+B8h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(pListOfExplicitEntriesa, a3);
  pListOfExplicitEntries = va_arg(va1, PEXPLICIT_ACCESS_W);
  NewAcl = va_arg(va1, PACL *);
  v3 = NewAcl;
  pcCountOfExplicitEntries = 0;
  memset(&v16, 0, sizeof(v16));
  if ( NewAcl )
    *NewAcl = 0;
  pListOfExplicitEntries = 0;
  ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(
                              OldAcl,
                              &pcCountOfExplicitEntries,
                              (PEXPLICIT_ACCESS_W *)pListOfExplicitEntriesa);
  if ( ExplicitEntriesFromAclW )
  {
    v8 = 420;
LABEL_19:
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v8,
            v7,
            (const char *)ExplicitEntriesFromAclW,
            v16.grfAccessPermissions);
    goto LABEL_21;
  }
  v9 = 131097;
  for ( i = 0; (unsigned int)i < pcCountOfExplicitEntries; i = (unsigned int)(i + 1) )
  {
    v11 = pListOfExplicitEntries;
    TrusteeForm = pListOfExplicitEntries[i].Trustee.TrusteeForm;
    if ( TrusteeForm )
    {
      if ( TrusteeForm != TRUSTEE_IS_OBJECTS_AND_SID )
        continue;
      ptstrName = (LPWCH)*((_QWORD *)pListOfExplicitEntries[i].Trustee.ptstrName + 5);
    }
    else
    {
      ptstrName = pListOfExplicitEntries[i].Trustee.ptstrName;
    }
    if ( ptstrName )
    {
      if ( EqualSid(pSid1, ptstrName) )
      {
        if ( v11[i].grfAccessMode == GRANT_ACCESS )
        {
          v9 &= ~v11[i].grfAccessPermissions;
          if ( !v9 )
            goto LABEL_20;
        }
      }
    }
  }
  if ( v3 )
  {
    v16.grfAccessPermissions = 131097;
    v16.grfAccessMode = SET_ACCESS;
    v16.grfInheritance = 3;
    v16.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    v16.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    v16.Trustee.ptstrName = (LPWCH)pSid1;
    ExplicitEntriesFromAclW = SetEntriesInAclW(1u, &v16, OldAcl, v3);
    if ( ExplicitEntriesFromAclW )
    {
      v8 = 473;
      goto LABEL_19;
    }
  }
LABEL_20:
  v14 = 0;
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>((PEXPLICIT_ACCESS_W *)pListOfExplicitEntriesa);
  return v14;
}

```

## disassembly

```asm
0x180098b70  mov     [rsp-38h+arg_0], rbx
0x180098b75  mov     [rsp-38h+pListOfExplicitEntries], r9
0x180098b7a  mov     [rsp-38h+pcCountOfExplicitEntries], r8d
0x180098b7f  push    rbp
0x180098b80  push    rsi
0x180098b81  push    rdi
0x180098b82  push    r12
0x180098b84  push    r13
0x180098b86  push    r14
0x180098b88  push    r15
0x180098b8a  mov     rbp, rsp
0x180098b8d  sub     rsp, 50h
0x180098b91  mov     rsi, [rbp+NewAcl]
0x180098b95  xorps   xmm0, xmm0
0x180098b98  mov     [rbp+pcCountOfExplicitEntries], 0
0x180098b9f  mov     r15, rdx
0x180098ba2  mov     r13, rcx
0x180098ba5  movups  xmmword ptr [rbp+var_30.grfAccessPermissions], xmm0
0x180098ba9  movups  xmmword ptr [rbp+var_30.Trustee.pMultipleTrustee], xmm0
0x180098bad  movups  xmmword ptr [rbp+var_30.Trustee.TrusteeType], xmm0
0x180098bb1  test    rsi, rsi
0x180098bb4  jz      short loc_180098BBD
0x180098bb6  mov     qword ptr [rsi], 0
0x180098bbd  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180098bc1  mov     [rbp+pListOfExplicitEntries], 0
0x180098bc9  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x180098bcd  mov     rcx, r15; pacl
0x180098bd0  call    cs:__imp_GetExplicitEntriesFromAclW
0x180098bd6  test    eax, eax
0x180098bd8  jz      short loc_180098BE4
0x180098bda  mov     edx, 1A4h
0x180098bdf  jmp     loc_180098C8D
0x180098be4  mov     r12d, 20019h
0x180098bea  xor     r14d, r14d
0x180098bed  cmp     r14d, [rbp+pcCountOfExplicitEntries]
0x180098bf1  jnb     short loc_180098C43
0x180098bf3  mov     rdi, [rbp+pListOfExplicitEntries]
0x180098bf7  lea     rbx, [r14+r14*2]
0x180098bfb  add     rbx, rbx
0x180098bfe  mov     eax, [rdi+rbx*8+1Ch]
0x180098c02  test    eax, eax
0x180098c04  jnz     short loc_180098C0D
0x180098c06  mov     rdx, [rdi+rbx*8+28h]
0x180098c0b  jmp     short loc_180098C1B
0x180098c0d  cmp     eax, 3
0x180098c10  jnz     short loc_180098C3E
0x180098c12  mov     rax, [rdi+rbx*8+28h]
0x180098c17  mov     rdx, [rax+28h]; pSid2
0x180098c1b  test    rdx, rdx
0x180098c1e  jz      short loc_180098C3E
0x180098c20  mov     rcx, r13; pSid1
0x180098c23  call    cs:__imp_EqualSid
0x180098c29  test    eax, eax
0x180098c2b  jz      short loc_180098C3E
0x180098c2d  cmp     dword ptr [rdi+rbx*8+4], 1
0x180098c32  jnz     short loc_180098C3E
0x180098c34  mov     eax, [rdi+rbx*8]
0x180098c37  not     eax
0x180098c39  and     r12d, eax
0x180098c3c  jz      short loc_180098C9D
0x180098c3e  inc     r14d
0x180098c41  jmp     short loc_180098BED
0x180098c43  test    rsi, rsi
0x180098c46  jz      short loc_180098C9D
0x180098c48  mov     r9, rsi; NewAcl
0x180098c4b  mov     [rbp+var_30.grfAccessPermissions], 20019h
0x180098c52  mov     r8, r15; OldAcl
0x180098c55  mov     [rbp+var_30.grfAccessMode], 2
0x180098c5c  lea     rdx, [rbp+var_30]; pListOfExplicitEntries
0x180098c60  mov     [rbp+var_30.grfInheritance], 3
0x180098c67  mov     ecx, 1; cCountOfExplicitEntries
0x180098c6c  mov     [rbp+var_30.Trustee.TrusteeForm], 0
0x180098c73  mov     [rbp+var_30.Trustee.TrusteeType], 5
0x180098c7a  mov     [rbp+var_30.Trustee.ptstrName], r13
0x180098c7e  call    cs:__imp_SetEntriesInAclW
0x180098c84  test    eax, eax
0x180098c86  jz      short loc_180098C9D
0x180098c88  mov     edx, 1D9h; void *
0x180098c8d  mov     rcx, [rbp+38h]; this
0x180098c91  mov     r9d, eax; char *
0x180098c94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180098c99  mov     ebx, eax
0x180098c9b  jmp     short loc_180098C9F
0x180098c9d  xor     ebx, ebx
0x180098c9f  lea     rcx, [rbp+pListOfExplicitEntries]
0x180098ca3  call    ??1?$unique_storage@U?$resource_policy@PEAU_EXPLICIT_ACCESS_W@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EXPLICIT_ACCESS_W *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_EXPLICIT_ACCESS_W *,_EXPLICIT_ACCESS_W *,0,std::nullptr_t>>(void)
0x180098ca8  mov     eax, ebx
0x180098caa  mov     rbx, [rsp+50h+arg_0]
0x180098cb2  add     rsp, 50h
0x180098cb6  pop     r15
0x180098cb8  pop     r14
0x180098cba  pop     r13
0x180098cbc  pop     r12
0x180098cbe  pop     rdi
0x180098cbf  pop     rsi
0x180098cc0  pop     rbp
0x180098cc1  retn
```
