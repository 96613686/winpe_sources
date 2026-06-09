# SetSecurityAttributes(_SECURITY_ATTRIBUTES *,_EXPLICIT_ACCESS_W * const,void *,void *,void *,_ACL * *,void * *)

- ea: `0x40784b`
- end: `0x407a39`
- name: `?SetSecurityAttributes@@YGJPAU_SECURITY_ATTRIBUTES@@QAU_EXPLICIT_ACCESS_W@@PAX22PAPAU_ACL@@PAPAX@Z`
- size: `494`
- prototype: `unsigned int __userpurge@<eax>(struct _EXPLICIT_ACCESS_W *@<edx>, _DWORD *@<ecx>, struct _SECURITY_ATTRIBUTES *pSid, struct _EXPLICIT_ACCESS_W *const pDestinationSid, WCHAR *, PACL *NewAcl, PSECURITY_DESCRIPTOR *, struct _ACL **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x407a3f`

## callees

- `0x40784b`
- `0x409d63`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x4079ae`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x4079ae`
- `ADVAPI32!CopySid` at `0x407917`
- `ADVAPI32!CopySid` at `0x407917`
- `ADVAPI32!CreateWellKnownSid` at `0x40789e`
- `ADVAPI32!CreateWellKnownSid` at `0x4078eb`
- `ADVAPI32!CreateWellKnownSid` at `0x40795b`
- `ADVAPI32!CreateWellKnownSid` at `0x40789e`
- `ADVAPI32!CreateWellKnownSid` at `0x4078eb`
- `ADVAPI32!CreateWellKnownSid` at `0x40795b`
- `ADVAPI32!SetEntriesInAclW` at `0x407991`
- `ADVAPI32!SetEntriesInAclW` at `0x407991`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x4079c0`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x4079c0`
- `KERNEL32!LocalAlloc` at `0x40799f`
- `KERNEL32!LocalAlloc` at `0x40799f`
- `KERNEL32!LocalFree` at `0x407a08`
- `KERNEL32!LocalFree` at `0x407a1b`
- `KERNEL32!LocalFree` at `0x407a2a`
- `KERNEL32!LocalFree` at `0x407a08`
- `KERNEL32!LocalFree` at `0x407a1b`
- `KERNEL32!LocalFree` at `0x407a2a`
- `KERNEL32!GetLastError` at `0x4079ea`
- `KERNEL32!GetLastError` at `0x4079ea`
- `iertutil!__imp_?GetCurrentUserSid@@YGKPAPAX@Z` at `0x407900`
- `iertutil!__imp_?GetCurrentUserSid@@YGKPAPAX@Z` at `0x407900`

## pseudocode

```c
unsigned int __userpurge SetSecurityAttributes@<eax>(
        struct _EXPLICIT_ACCESS_W *a1@<edx>,
        _DWORD *a2@<ecx>,
        struct _SECURITY_ATTRIBUTES *pSid,
        struct _EXPLICIT_ACCESS_W *const pDestinationSid,
        WCHAR *a5,
        PACL *NewAcl,
        PSECURITY_DESCRIPTOR *a7,
        struct _ACL **a8,
        void **a9)
{
  unsigned int InstallScopeFromIntegrityLevel; // esi
  BOOL v11; // eax
  signed int LastError; // eax
  HLOCAL v13; // eax
  unsigned int result; // eax
  unsigned int *v15; // [esp+0h] [ebp-1Ch]
  int v17; // [esp+10h] [ebp-Ch]
  PSID pSourceSid; // [esp+14h] [ebp-8h] BYREF
  DWORD cbSid; // [esp+18h] [ebp-4h] BYREF

  cbSid = 68;
  pSourceSid = 0;
  InstallScopeFromIntegrityLevel = GetInstallScopeFromIntegrityLevel(v15);
  if ( !InstallScopeFromIntegrityLevel )
  {
    *NewAcl = 0;
    *a7 = 0;
    memset(a1, 0, 0x60u);
    if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, pSid, &cbSid) )
    {
LABEL_16:
      LastError = GetLastError();
LABEL_17:
      InstallScopeFromIntegrityLevel = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        InstallScopeFromIntegrityLevel = LastError;
      goto LABEL_19;
    }
    a1->grfAccessPermissions = -1610612736;
    a1->grfAccessMode = SET_ACCESS;
    a1->grfInheritance = 3;
    a1->Trustee.TrusteeForm = TRUSTEE_IS_SID;
    a1->Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    a1->Trustee.ptstrName = (LPWCH)pSid;
    cbSid = 68;
    if ( v17 == 1 )
    {
      v11 = CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pDestinationSid, &cbSid);
LABEL_8:
      if ( v11 )
      {
        a1[1].grfAccessMode = SET_ACCESS;
        a1[1].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
        a1[1].Trustee.ptstrName = (LPWCH)pDestinationSid;
        a1[1].grfAccessPermissions = 270467072;
        a1[1].grfInheritance = 3;
        a1[1].Trustee.TrusteeForm = TRUSTEE_IS_SID;
        cbSid = 68;
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, a5, &cbSid) )
        {
          a1[2].grfAccessMode = SET_ACCESS;
          a1[2].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
          a1[2].grfAccessPermissions = 270467072;
          a1[2].grfInheritance = 3;
          a1[2].Trustee.TrusteeForm = TRUSTEE_IS_SID;
          a1[2].Trustee.ptstrName = a5;
          if ( !SetEntriesInAclW(3u, a1, 0, NewAcl) )
          {
            v13 = LocalAlloc(0x40u, 0x14u);
            *a7 = v13;
            if ( v13 )
            {
              if ( InitializeSecurityDescriptor(v13, 1u) && SetSecurityDescriptorDacl(*a7, 1, *NewAcl, 0) )
              {
                a2[1] = *a7;
                result = 0;
                *a2 = 12;
                a2[2] = 0;
                return result;
              }
            }
          }
        }
      }
      goto LABEL_16;
    }
    if ( v17 == 2 )
    {
      LastError = GetCurrentUserSid(&pSourceSid);
      if ( LastError )
        goto LABEL_17;
      v11 = CopySid(cbSid, pDestinationSid, pSourceSid);
      goto LABEL_8;
    }
    InstallScopeFromIntegrityLevel = -2147467263;
  }
LABEL_19:
  if ( *NewAcl )
  {
    LocalFree(*NewAcl);
    *NewAcl = 0;
  }
  if ( *a7 )
  {
    LocalFree(*a7);
    *a7 = 0;
  }
  LocalFree(pSourceSid);
  return InstallScopeFromIntegrityLevel;
}

```

## disassembly

```asm
0x40784b  mov     edi, edi
0x40784d  push    ebp
0x40784e  mov     ebp, esp
0x407850  sub     esp, 10h
0x407853  push    ebx
0x407854  push    esi
0x407855  mov     [ebp+var_10], ecx
0x407858  lea     ecx, [ebp+var_C]
0x40785b  push    edi; unsigned int *
0x40785c  mov     edi, edx
0x40785e  mov     [ebp+cbSid], 44h ; 'D'
0x407865  mov     [ebp+pSourceSid], 0
0x40786c  call    ?GetInstallScopeFromIntegrityLevel@@YGJPAK@Z; GetInstallScopeFromIntegrityLevel(ulong *)
0x407871  mov     ebx, [ebp+arg_10]
0x407874  mov     esi, eax
0x407876  test    esi, esi
0x407878  jnz     loc_4079FE
0x40787e  mov     esi, [ebp+NewAcl]
0x407881  xor     eax, eax
0x407883  push    60h ; '`'; Size
0x407885  push    eax; Val
0x407886  push    edi; void *
0x407887  mov     [esi], eax
0x407889  mov     [ebx], eax
0x40788b  call    _memset
0x407890  add     esp, 0Ch
0x407893  lea     eax, [ebp+cbSid]
0x407896  push    eax; cbSid
0x407897  push    [ebp+pSid]; pSid
0x40789a  push    0; DomainSid
0x40789c  push    11h; WellKnownSidType
0x40789e  call    ds:__imp__CreateWellKnownSid@16; CreateWellKnownSid(x,x,x,x)
0x4078a4  test    eax, eax
0x4078a6  jz      loc_4079EA
0x4078ac  cmp     [ebp+var_C], 1
0x4078b0  mov     eax, [ebp+pSid]
0x4078b3  push    2
0x4078b5  pop     ecx
0x4078b6  mov     dword ptr [edi], 0A0000000h
0x4078bc  mov     [edi+4], ecx
0x4078bf  mov     dword ptr [edi+8], 3
0x4078c6  mov     dword ptr [edi+14h], 0
0x4078cd  mov     dword ptr [edi+18h], 5
0x4078d4  mov     [edi+1Ch], eax
0x4078d7  mov     [ebp+cbSid], 44h ; 'D'
0x4078de  jnz     short loc_4078F3
0x4078e0  lea     eax, [ebp+cbSid]
0x4078e3  push    eax; cbSid
0x4078e4  push    [ebp+pDestinationSid]; pSid
0x4078e7  push    0; DomainSid
0x4078e9  push    1Ah; WellKnownSidType
0x4078eb  call    ds:__imp__CreateWellKnownSid@16; CreateWellKnownSid(x,x,x,x)
0x4078f1  jmp     short loc_40791D
0x4078f3  cmp     [ebp+var_C], ecx
0x4078f6  jnz     loc_4079E3
0x4078fc  lea     eax, [ebp+pSourceSid]
0x4078ff  push    eax
0x407900  call    ds:__imp_?GetCurrentUserSid@@YGKPAPAX@Z; GetCurrentUserSid(void * *)
0x407906  test    eax, eax
0x407908  jnz     loc_4079F0
0x40790e  push    [ebp+pSourceSid]; pSourceSid
0x407911  push    [ebp+pDestinationSid]; pDestinationSid
0x407914  push    [ebp+cbSid]; nDestinationSidLength
0x407917  call    ds:__imp__CopySid@12; CopySid(x,x,x)
0x40791d  test    eax, eax
0x40791f  jz      loc_4079EA
0x407925  push    2
0x407927  pop     eax
0x407928  mov     [edi+24h], eax
0x40792b  mov     [edi+38h], eax
0x40792e  mov     eax, [ebp+pDestinationSid]
0x407931  mov     [edi+3Ch], eax
0x407934  lea     eax, [ebp+cbSid]
0x407937  push    eax; cbSid
0x407938  push    [ebp+arg_8]; pSid
0x40793b  mov     dword ptr [edi+20h], 101F0000h
0x407942  push    0; DomainSid
0x407944  push    16h; WellKnownSidType
0x407946  mov     dword ptr [edi+28h], 3
0x40794d  mov     dword ptr [edi+34h], 0
0x407954  mov     [ebp+cbSid], 44h ; 'D'
0x40795b  call    ds:__imp__CreateWellKnownSid@16; CreateWellKnownSid(x,x,x,x)
0x407961  test    eax, eax
0x407963  jz      loc_4079EA
0x407969  push    2
0x40796b  pop     eax
0x40796c  push    3
0x40796e  pop     ecx
0x40796f  push    esi; NewAcl
0x407970  push    0; OldAcl
0x407972  push    edi; pListOfExplicitEntries
0x407973  mov     [edi+44h], eax
0x407976  mov     [edi+58h], eax
0x407979  mov     eax, [ebp+arg_8]
0x40797c  push    ecx; cCountOfExplicitEntries
0x40797d  mov     dword ptr [edi+40h], 101F0000h
0x407984  mov     [edi+48h], ecx
0x407987  mov     dword ptr [edi+54h], 0
0x40798e  mov     [edi+5Ch], eax
0x407991  call    ds:__imp__SetEntriesInAclW@16; SetEntriesInAclW(x,x,x,x)
0x407997  test    eax, eax
0x407999  jnz     short loc_4079EA
0x40799b  push    14h; uBytes
0x40799d  push    40h ; '@'; uFlags
0x40799f  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x4079a5  mov     [ebx], eax
0x4079a7  test    eax, eax
0x4079a9  jz      short loc_4079EA
0x4079ab  push    1; dwRevision
0x4079ad  push    eax; pSecurityDescriptor
0x4079ae  call    ds:__imp__InitializeSecurityDescriptor@8; InitializeSecurityDescriptor(x,x)
0x4079b4  test    eax, eax
0x4079b6  jz      short loc_4079EA
0x4079b8  push    0; bDaclDefaulted
0x4079ba  push    dword ptr [esi]; pDacl
0x4079bc  push    1; bDaclPresent
0x4079be  push    dword ptr [ebx]; pSecurityDescriptor
0x4079c0  call    ds:__imp__SetSecurityDescriptorDacl@16; SetSecurityDescriptorDacl(x,x,x,x)
0x4079c6  test    eax, eax
0x4079c8  jz      short loc_4079EA
0x4079ca  mov     ecx, [ebp+var_10]
0x4079cd  mov     eax, [ebx]
0x4079cf  mov     [ecx+4], eax
0x4079d2  xor     eax, eax
0x4079d4  mov     dword ptr [ecx], 0Ch
0x4079da  mov     dword ptr [ecx+8], 0
0x4079e1  jmp     short loc_407A32
0x4079e3  mov     esi, 80004001h
0x4079e8  jmp     short loc_4079FE
0x4079ea  call    ds:__imp__GetLastError@0; GetLastError()
0x4079f0  movzx   esi, ax
0x4079f3  or      esi, 80070000h
0x4079f9  test    eax, eax
0x4079fb  cmovle  esi, eax
0x4079fe  mov     edi, [ebp+NewAcl]
0x407a01  cmp     dword ptr [edi], 0
0x407a04  jz      short loc_407A14
0x407a06  push    dword ptr [edi]; hMem
0x407a08  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407a0e  mov     dword ptr [edi], 0
0x407a14  cmp     dword ptr [ebx], 0
0x407a17  jz      short loc_407A27
0x407a19  push    dword ptr [ebx]; hMem
0x407a1b  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407a21  mov     dword ptr [ebx], 0
0x407a27  push    [ebp+pSourceSid]; hMem
0x407a2a  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407a30  mov     eax, esi
0x407a32  pop     edi
0x407a33  pop     esi
0x407a34  pop     ebx
0x407a35  leave
0x407a36  retn    14h
```
