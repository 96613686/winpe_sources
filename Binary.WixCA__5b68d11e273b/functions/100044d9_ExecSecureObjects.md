# ExecSecureObjects

- ea: `0x100044d9`
- end: `0x10004adb`
- name: `ExecSecureObjects`
- size: `1538`
- prototype: `int __stdcall(SE_OBJECT_TYPE ObjectType)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10004260`
- `0x100044d9`
- `0x1000995c`
- `0x10009962`
- `0x1000a54f`
- `0x1000a952`
- `0x1000ad15`
- `0x1000ba7f`
- `0x1000bbf8`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e13e`
- `0x1000e662`
- `0x1000ee5c`
- `0x1000ef44`
- `0x1000efcc`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorControl` at `0x10004883`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x10004883`
- `ADVAPI32!SetEntriesInAclW` at `0x100048b7`
- `ADVAPI32!SetEntriesInAclW` at `0x100048b7`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x10004858`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x10004858`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x100048f4`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x100048f4`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x10004809`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x10004809`
- `KERNEL32!GetLastError` at `0x1000488d`
- `KERNEL32!GetLastError` at `0x1000488d`
- `KERNEL32!LocalFree` at `0x10004a94`
- `KERNEL32!LocalFree` at `0x10004aa3`
- `KERNEL32!LocalFree` at `0x10004a94`
- `KERNEL32!LocalFree` at `0x10004aa3`
- `KERNEL32!lstrcmpW` at `0x1000462e`
- `KERNEL32!lstrcmpW` at `0x1000465a`
- `KERNEL32!lstrcmpW` at `0x1000467e`
- `KERNEL32!lstrcmpW` at `0x100046a2`
- `KERNEL32!lstrcmpW` at `0x100046c6`
- `KERNEL32!lstrcmpW` at `0x100046ed`
- `KERNEL32!lstrcmpW` at `0x10004714`
- `KERNEL32!lstrcmpW` at `0x10004737`
- `KERNEL32!lstrcmpW` at `0x1000475a`
- `KERNEL32!lstrcmpW` at `0x1000477d`
- `KERNEL32!lstrcmpW` at `0x100047ea`
- `KERNEL32!lstrcmpW` at `0x10004824`
- `KERNEL32!lstrcmpW` at `0x10004620`
- `KERNEL32!lstrcmpW` at `0x100047ea`
- `KERNEL32!lstrcmpW` at `0x10004824`

## string_xrefs

- `0x100047e5`: `CreateFolder`
- `0x1000481c`: `ServiceInstall`
- `0x10004939`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\secureobj.cpp`
- `0x10004603`: `Securing Object: %ls Type: %ls User: %ls`
- `0x1000469a`: `LocalService`
- `0x100046be`: `NetworkService`
- `0x10004a0d`: `failed to get sid for account: %ls%ls%ls`
- `0x100049b7`: `failed to get security info for object: %ls`
- `0x10004946`: `failed to get security descriptor control for object: %ls`
- `0x1000499f`: `failed to add ACLs for object: %ls`
- `0x10004968`: `failed to set security info for object: %ls`

## pseudocode

```c
int __stdcall ExecSecureObjects(SE_OBJECT_TYPE ObjectType)
{
  int v1; // ebx
  MSIHANDLE Record; // esi
  signed int v3; // edi
  _WORD *v4; // eax
  char v5; // al
  int v6; // eax
  SE_OBJECT_TYPE v7; // edi
  int v8; // eax
  DWORD v9; // ecx
  signed int NamedSecurityInfoW; // eax
  int v11; // edi
  signed int LastError; // eax
  bool v13; // sf
  signed int v14; // eax
  signed int v15; // eax
  int v16; // edi
  int v17; // eax
  int v18; // edi
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [esp+Ch] [ebp-58h] BYREF
  DWORD dwRevision; // [esp+2Ch] [ebp-38h] BYREF
  WORD pControl[2]; // [esp+30h] [ebp-34h] BYREF
  PACL ppDacl; // [esp+34h] [ebp-30h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [esp+38h] [ebp-2Ch] BYREF
  PACL NewAcl; // [esp+3Ch] [ebp-28h] BYREF
  LPCWSTR lpAccountName; // [esp+40h] [ebp-24h] BYREF
  DWORD pcchValueBuf; // [esp+44h] [ebp-20h] BYREF
  int v28; // [esp+48h] [ebp-1Ch] BYREF
  wchar_t SubStr[2]; // [esp+4Ch] [ebp-18h] BYREF
  LPCWSTR lpString2; // [esp+50h] [ebp-14h] BYREF
  LPCWSTR pObjectName; // [esp+54h] [ebp-10h] BYREF
  PSID pSid; // [esp+58h] [ebp-Ch] BYREF
  int v33; // [esp+5Ch] [ebp-8h] BYREF
  LPCWSTR lpString1; // [esp+60h] [ebp-4h] BYREF
  SE_OBJECT_TYPE ObjectTypea; // [esp+6Ch] [ebp+8h]

  *(_DWORD *)SubStr = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  v1 = 0;
  pcchValueBuf = 0;
  pObjectName = 0;
  lpString2 = 0;
  v33 = 0;
  dwRevision = 0;
  lpString1 = 0;
  v28 = 0;
  lpAccountName = 0;
  pSid = 0;
  ppSecurityDescriptor = 0;
  *(_DWORD *)pControl = 0;
  ppDacl = 0;
  NewAcl = 0;
  Record = MsiCreateRecord(1u);
  v3 = sub_1000D51F(ObjectType, (int)"ExecSecureObjects");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize");
    goto LABEL_88;
  }
  v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v3 >= 0 )
  {
    sub_1000D9AB(0, "CustomActionData: %ls");
    v4 = (_WORD *)pcchValueBuf;
    for ( *(_DWORD *)SubStr = pcchValueBuf; ; v4 = *(_WORD **)SubStr )
    {
      if ( !v4 || !*v4 )
        goto LABEL_88;
      v3 = sub_1000EFCC((wchar_t)SubStr, (int)&pObjectName);
      if ( v3 < 0
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpString2), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v33), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpString1), v3 < 0) )
      {
        sub_1000DA66(v3, "failed to process CustomActionData");
        goto LABEL_88;
      }
      v3 = sub_1000EF44((wchar_t)SubStr, (int)&v28);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to processCustomActionData");
        goto LABEL_88;
      }
      sub_1000D9AB(1, "Securing Object: %ls Type: %ls User: %ls");
      v5 = v33;
      if ( !*(_WORD *)v33 )
      {
        if ( !lstrcmpW(lpString1, L"Everyone") )
        {
          v6 = sub_1000BBF8(WinWorldSid, (int)&pSid);
          goto LABEL_45;
        }
        v5 = v33;
        if ( !*(_WORD *)v33 )
        {
          if ( !lstrcmpW(lpString1, L"Administrators") )
          {
            v6 = sub_1000BBF8(WinBuiltinAdministratorsSid, (int)&pSid);
            goto LABEL_45;
          }
          v5 = v33;
          if ( !*(_WORD *)v33 )
          {
            if ( !lstrcmpW(lpString1, L"LocalSystem") )
            {
              v6 = sub_1000BBF8(WinLocalSystemSid, (int)&pSid);
              goto LABEL_45;
            }
            v5 = v33;
            if ( !*(_WORD *)v33 )
            {
              if ( !lstrcmpW(lpString1, L"LocalService") )
              {
                v6 = sub_1000BBF8(WinLocalServiceSid, (int)&pSid);
                goto LABEL_45;
              }
              v5 = v33;
              if ( !*(_WORD *)v33 )
              {
                if ( !lstrcmpW(lpString1, L"NetworkService") )
                {
                  v6 = sub_1000BBF8(WinNetworkServiceSid, (int)&pSid);
                  goto LABEL_45;
                }
                v5 = v33;
                if ( !*(_WORD *)v33 )
                {
                  if ( !lstrcmpW(lpString1, L"AuthenticatedUser") )
                  {
                    v6 = sub_1000BBF8(WinAuthenticatedUserSid, (int)&pSid);
                    goto LABEL_45;
                  }
                  v5 = v33;
                  if ( !*(_WORD *)v33 )
                  {
                    if ( !lstrcmpW(lpString1, L"Guests") )
                    {
                      v6 = sub_1000BBF8(WinBuiltinGuestsSid, (int)&pSid);
                      goto LABEL_45;
                    }
                    v5 = v33;
                    if ( !*(_WORD *)v33 )
                    {
                      if ( !lstrcmpW(lpString1, L"CREATOR OWNER") )
                      {
                        v6 = sub_1000BBF8(WinCreatorOwnerSid, (int)&pSid);
                        goto LABEL_45;
                      }
                      v5 = v33;
                      if ( !*(_WORD *)v33 )
                      {
                        if ( !lstrcmpW(lpString1, L"INTERACTIVE") )
                        {
                          v6 = sub_1000BBF8(WinInteractiveSid, (int)&pSid);
                          goto LABEL_45;
                        }
                        v5 = v33;
                        if ( !*(_WORD *)v33 )
                        {
                          if ( !lstrcmpW(lpString1, L"Users") )
                          {
                            v6 = sub_1000BBF8(WinBuiltinUsersSid, (int)&pSid);
                            goto LABEL_45;
                          }
                          v5 = v33;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v3 = sub_1000A54F(&lpAccountName, L"%s%s%s", v5);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to build domain user name");
        goto LABEL_88;
      }
      v6 = sub_1000BA7F(0, lpAccountName, (int)&pSid);
LABEL_45:
      v3 = v6;
      if ( v6 < 0 )
      {
        sub_1000DA66(v6, "failed to get sid for account: %ls%ls%ls");
        goto LABEL_88;
      }
      pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
      if ( lstrcmpW(L"CreateFolder", lpString2) )
        pListOfExplicitEntries.grfInheritance = 0;
      else
        pListOfExplicitEntries.grfInheritance = 3;
      BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, pSid);
      v7 = sub_10004260(lpString2);
      ObjectTypea = v7;
      v8 = lstrcmpW(L"ServiceInstall", lpString2);
      v9 = v28;
      if ( !v8 )
      {
        v9 = v28 | 0x8D;
        v28 |= 0x8Du;
      }
      pListOfExplicitEntries.grfAccessPermissions = v9;
      if ( v7 == SE_UNKNOWN_OBJECT_TYPE )
      {
        v3 = -2147418113;
        sub_1000DA66(-2147418113, "unknown object type: %ls");
        sub_1000E13E(25522, -2147418113, INSTALLMESSAGE_ERROR, 1);
        goto LABEL_88;
      }
      NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, v7, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
      v1 = NamedSecurityInfoW;
      v11 = (unsigned __int16)NamedSecurityInfoW;
      if ( NamedSecurityInfoW > 0 )
        NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      if ( NamedSecurityInfoW < 0 )
      {
        if ( v1 > 0 )
          v3 = v11 | 0x80070000;
        else
          v3 = v1;
        sub_1000DA66(v3, "failed to get security info for object: %ls");
        goto LABEL_88;
      }
      if ( !GetSecurityDescriptorControl(ppSecurityDescriptor, pControl, &dwRevision) )
      {
        LastError = GetLastError();
        v3 = LastError;
        v13 = LastError < 0;
        if ( LastError > 0 )
        {
          v3 = (unsigned __int16)LastError | 0x80070000;
          v13 = 1;
        }
        if ( v13 )
        {
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\secureobj.cpp", 726, v3);
          sub_1000DA66(v3, "failed to get security descriptor control for object: %ls");
          goto LABEL_88;
        }
      }
      v14 = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
      v1 = v14;
      v3 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 < 0 )
      {
        if ( v1 <= 0 )
          v3 = v1;
        sub_1000DA66(v3, "failed to add ACLs for object: %ls");
        goto LABEL_88;
      }
      v15 = SetNamedSecurityInfoW((LPWSTR)pObjectName, ObjectTypea, ((pControl[0] & 0xF000) << 19) | 4, 0, 0, NewAcl, 0);
      v1 = v15;
      v16 = (unsigned __int16)v15;
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 < 0 )
      {
        v3 = v16 | 0x80070000;
        v17 = v1;
        if ( v1 > 0 )
          v17 = v3;
        sub_1000DA66(v17, "failed to set security info for object: %ls");
        if ( v1 <= 0 )
          v3 = v1;
        sub_1000E13E(25521, v3, INSTALLMESSAGE_ERROR, 1);
        goto LABEL_88;
      }
      v3 = sub_1000EE5C(1000, 0);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to send progress message");
        goto LABEL_88;
      }
    }
  }
  sub_1000DA66(v3, "failed to get CustomActionData");
LABEL_88:
  if ( lpString1 )
    sub_1000A952(lpString1);
  if ( v33 )
    sub_1000A952(v33);
  if ( lpString2 )
    sub_1000A952(lpString2);
  if ( pObjectName )
    sub_1000A952(pObjectName);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpAccountName )
    sub_1000A952(lpAccountName);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( pSid )
    sub_1000A952(pSid);
  if ( v3 < 0 )
    v1 = 1603;
  v18 = sub_1000D4AE(v1);
  if ( Record )
    MsiCloseHandle(Record);
  return v18;
}

```

## disassembly

```asm
0x100044d9  push    ebp
0x100044da  mov     ebp, esp
0x100044dc  sub     esp, 58h
0x100044df  push    ebx
0x100044e0  xor     edx, edx
0x100044e2  xor     eax, eax
0x100044e4  push    esi
0x100044e5  push    edi
0x100044e6  push    8
0x100044e8  pop     ecx
0x100044e9  lea     edi, [ebp+pListOfExplicitEntries]
0x100044ec  mov     dword ptr [ebp+SubStr], edx
0x100044ef  rep stosd
0x100044f1  push    1; cParams
0x100044f3  mov     ebx, edx
0x100044f5  mov     [ebp+pcchValueBuf], edx
0x100044f8  mov     [ebp+pObjectName], edx
0x100044fb  mov     [ebp+lpString2], edx
0x100044fe  mov     [ebp+var_8], edx
0x10004501  mov     [ebp+dwRevision], edx
0x10004504  mov     [ebp+lpString1], edx
0x10004507  mov     [ebp+var_1C], edx
0x1000450a  mov     [ebp+lpAccountName], edx
0x1000450d  mov     [ebp+pSid], edx
0x10004510  mov     [ebp+ppSecurityDescriptor], edx
0x10004513  mov     dword ptr [ebp+pControl], edx
0x10004516  mov     [ebp+ppDacl], edx
0x10004519  mov     [ebp+NewAcl], edx
0x1000451c  call    MsiCreateRecord
0x10004521  push    offset aExecsecureobje_2; "ExecSecureObjects"
0x10004526  push    [ebp+ObjectType]; hInstall
0x10004529  mov     esi, eax
0x1000452b  call    sub_1000D51F
0x10004530  mov     edi, eax
0x10004532  test    edi, edi
0x10004534  jns     short loc_10004540
0x10004536  push    offset aFailedToInitia_2; "failed to initialize"
0x1000453b  jmp     loc_10004A30
0x10004540  lea     eax, [ebp+pcchValueBuf]
0x10004543  push    eax; pcchValueBuf
0x10004544  push    offset aCustomactionda; "CustomActionData"
0x10004549  call    sub_1000E662
0x1000454e  mov     edi, eax
0x10004550  test    edi, edi
0x10004552  jns     short loc_1000455E
0x10004554  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10004559  jmp     loc_10004A30
0x1000455e  push    [ebp+pcchValueBuf]
0x10004561  xor     eax, eax
0x10004563  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10004568  push    eax
0x10004569  call    sub_1000D9AB
0x1000456e  mov     eax, [ebp+pcchValueBuf]
0x10004571  add     esp, 0Ch
0x10004574  mov     dword ptr [ebp+SubStr], eax
0x10004577  jmp     loc_10004926
0x1000457c  xor     ecx, ecx
0x1000457e  cmp     [eax], cx
0x10004581  jz      loc_10004A38
0x10004587  lea     eax, [ebp+pObjectName]
0x1000458a  push    eax; int
0x1000458b  lea     eax, [ebp+SubStr]
0x1000458e  push    eax; SubStr
0x1000458f  call    sub_1000EFCC
0x10004594  mov     edi, eax
0x10004596  test    edi, edi
0x10004598  js      loc_10004A2B
0x1000459e  lea     eax, [ebp+lpString2]
0x100045a1  push    eax; int
0x100045a2  lea     eax, [ebp+SubStr]
0x100045a5  push    eax; SubStr
0x100045a6  call    sub_1000EFCC
0x100045ab  mov     edi, eax
0x100045ad  test    edi, edi
0x100045af  js      loc_10004A2B
0x100045b5  lea     eax, [ebp+var_8]
0x100045b8  push    eax; int
0x100045b9  lea     eax, [ebp+SubStr]
0x100045bc  push    eax; SubStr
0x100045bd  call    sub_1000EFCC
0x100045c2  mov     edi, eax
0x100045c4  test    edi, edi
0x100045c6  js      loc_10004A2B
0x100045cc  lea     eax, [ebp+lpString1]
0x100045cf  push    eax; int
0x100045d0  lea     eax, [ebp+SubStr]
0x100045d3  push    eax; SubStr
0x100045d4  call    sub_1000EFCC
0x100045d9  mov     edi, eax
0x100045db  test    edi, edi
0x100045dd  js      loc_10004A2B
0x100045e3  lea     eax, [ebp+var_1C]
0x100045e6  push    eax; int
0x100045e7  lea     eax, [ebp+SubStr]
0x100045ea  push    eax; SubStr
0x100045eb  call    sub_1000EF44
0x100045f0  mov     edi, eax
0x100045f2  test    edi, edi
0x100045f4  js      loc_10004A24
0x100045fa  push    [ebp+lpString1]
0x100045fd  push    [ebp+lpString2]
0x10004600  push    [ebp+pObjectName]
0x10004603  push    offset aSecuringObject; "Securing Object: %ls Type: %ls User: %l"...
0x10004608  push    1
0x1000460a  call    sub_1000D9AB
0x1000460f  mov     eax, [ebp+var_8]
0x10004612  xor     ecx, ecx
0x10004614  add     esp, 14h
0x10004617  cmp     [eax], cx
0x1000461a  jnz     loc_1000479D
0x10004620  mov     edi, ds:lstrcmpW
0x10004626  push    offset String2; "Everyone"
0x1000462b  push    [ebp+lpString1]; lpString1
0x1000462e  call    edi ; lstrcmpW
0x10004630  test    eax, eax
0x10004632  jnz     short loc_10004644
0x10004634  lea     eax, [ebp+pSid]
0x10004637  push    eax; int
0x10004638  push    1; WellKnownSidType
0x1000463a  call    sub_1000BBF8
0x1000463f  jmp     loc_100047D1
0x10004644  mov     eax, [ebp+var_8]
0x10004647  xor     ecx, ecx
0x10004649  cmp     [eax], cx
0x1000464c  jnz     loc_1000479D
0x10004652  push    offset aAdministrators; "Administrators"
0x10004657  push    [ebp+lpString1]; lpString1
0x1000465a  call    edi ; lstrcmpW
0x1000465c  test    eax, eax
0x1000465e  jnz     short loc_10004668
0x10004660  lea     eax, [ebp+pSid]
0x10004663  push    eax
0x10004664  push    1Ah
0x10004666  jmp     short loc_1000463A
0x10004668  mov     eax, [ebp+var_8]
0x1000466b  xor     ecx, ecx
0x1000466d  cmp     [eax], cx
0x10004670  jnz     loc_1000479D
0x10004676  push    offset aLocalsystem; "LocalSystem"
0x1000467b  push    [ebp+lpString1]; lpString1
0x1000467e  call    edi ; lstrcmpW
0x10004680  test    eax, eax
0x10004682  jnz     short loc_1000468C
0x10004684  lea     eax, [ebp+pSid]
0x10004687  push    eax
0x10004688  push    16h
0x1000468a  jmp     short loc_1000463A
0x1000468c  mov     eax, [ebp+var_8]
0x1000468f  xor     ecx, ecx
0x10004691  cmp     [eax], cx
0x10004694  jnz     loc_1000479D
0x1000469a  push    offset aLocalservice; "LocalService"
0x1000469f  push    [ebp+lpString1]; lpString1
0x100046a2  call    edi ; lstrcmpW
0x100046a4  test    eax, eax
0x100046a6  jnz     short loc_100046B0
0x100046a8  lea     eax, [ebp+pSid]
0x100046ab  push    eax
0x100046ac  push    17h
0x100046ae  jmp     short loc_1000463A
0x100046b0  mov     eax, [ebp+var_8]
0x100046b3  xor     ecx, ecx
0x100046b5  cmp     [eax], cx
0x100046b8  jnz     loc_1000479D
0x100046be  push    offset aNetworkservice; "NetworkService"
0x100046c3  push    [ebp+lpString1]; lpString1
0x100046c6  call    edi ; lstrcmpW
0x100046c8  test    eax, eax
0x100046ca  jnz     short loc_100046D7
0x100046cc  lea     eax, [ebp+pSid]
0x100046cf  push    eax
0x100046d0  push    18h
0x100046d2  jmp     loc_1000463A
0x100046d7  mov     eax, [ebp+var_8]
0x100046da  xor     ecx, ecx
0x100046dc  cmp     [eax], cx
0x100046df  jnz     loc_1000479D
0x100046e5  push    offset aAuthenticatedu; "AuthenticatedUser"
0x100046ea  push    [ebp+lpString1]; lpString1
0x100046ed  call    edi ; lstrcmpW
0x100046ef  test    eax, eax
0x100046f1  jnz     short loc_100046FE
0x100046f3  lea     eax, [ebp+pSid]
0x100046f6  push    eax
0x100046f7  push    11h
0x100046f9  jmp     loc_1000463A
0x100046fe  mov     eax, [ebp+var_8]
0x10004701  xor     ecx, ecx
0x10004703  cmp     [eax], cx
0x10004706  jnz     loc_1000479D
0x1000470c  push    offset aGuests; "Guests"
0x10004711  push    [ebp+lpString1]; lpString1
0x10004714  call    edi ; lstrcmpW
0x10004716  test    eax, eax
0x10004718  jnz     short loc_10004725
0x1000471a  lea     eax, [ebp+pSid]
0x1000471d  push    eax
0x1000471e  push    1Ch
0x10004720  jmp     loc_1000463A
0x10004725  mov     eax, [ebp+var_8]
0x10004728  xor     ecx, ecx
0x1000472a  cmp     [eax], cx
0x1000472d  jnz     short loc_1000479D
0x1000472f  push    offset aCreatorOwner; "CREATOR OWNER"
0x10004734  push    [ebp+lpString1]; lpString1
0x10004737  call    edi ; lstrcmpW
0x10004739  test    eax, eax
0x1000473b  jnz     short loc_10004748
0x1000473d  lea     eax, [ebp+pSid]
0x10004740  push    eax
0x10004741  push    3
0x10004743  jmp     loc_1000463A
0x10004748  mov     eax, [ebp+var_8]
0x1000474b  xor     ecx, ecx
0x1000474d  cmp     [eax], cx
0x10004750  jnz     short loc_1000479D
0x10004752  push    offset aInteractive; "INTERACTIVE"
0x10004757  push    [ebp+lpString1]; lpString1
0x1000475a  call    edi ; lstrcmpW
0x1000475c  test    eax, eax
0x1000475e  jnz     short loc_1000476B
0x10004760  lea     eax, [ebp+pSid]
0x10004763  push    eax
0x10004764  push    0Bh
0x10004766  jmp     loc_1000463A
0x1000476b  mov     eax, [ebp+var_8]
0x1000476e  xor     ecx, ecx
0x10004770  cmp     [eax], cx
0x10004773  jnz     short loc_1000479D
0x10004775  push    offset aUsers_0; "Users"
0x1000477a  push    [ebp+lpString1]; lpString1
0x1000477d  call    edi ; lstrcmpW
0x1000477f  test    eax, eax
0x10004781  jnz     short loc_1000478E
0x10004783  lea     eax, [ebp+pSid]
0x10004786  push    eax
0x10004787  push    1Bh
0x10004789  jmp     loc_1000463A
0x1000478e  mov     eax, [ebp+var_8]
0x10004791  xor     ecx, ecx
0x10004793  cmp     [eax], cx
0x10004796  mov     ecx, offset dword_100226F0
0x1000479b  jz      short loc_100047A2
0x1000479d  mov     ecx, offset SubBlock; "\\"
0x100047a2  push    [ebp+lpString1]
0x100047a5  push    ecx
0x100047a6  push    eax
0x100047a7  lea     eax, [ebp+lpAccountName]
0x100047aa  push    offset aSSS; "%s%s%s"
0x100047af  push    eax
0x100047b0  call    sub_1000A54F
0x100047b5  mov     edi, eax
0x100047b7  add     esp, 14h
0x100047ba  test    edi, edi
0x100047bc  js      loc_10004A1D
0x100047c2  lea     eax, [ebp+pSid]
0x100047c5  push    eax; int
0x100047c6  push    [ebp+lpAccountName]; lpAccountName
0x100047c9  xor     eax, eax
0x100047cb  push    eax; lpSystemName
0x100047cc  call    sub_1000BA7F
0x100047d1  mov     edi, eax
0x100047d3  test    edi, edi
0x100047d5  js      loc_100049F4
0x100047db  push    [ebp+lpString2]; lpString2
0x100047de  mov     [ebp+pListOfExplicitEntries.grfAccessMode], 2
0x100047e5  push    offset aCreatefolder; "CreateFolder"
0x100047ea  call    ds:lstrcmpW
0x100047f0  test    eax, eax
0x100047f2  jnz     short loc_100047FD
0x100047f4  mov     [ebp+pListOfExplicitEntries.grfInheritance], 3
0x100047fb  jmp     short loc_10004802
0x100047fd  xor     eax, eax
0x100047ff  mov     [ebp+pListOfExplicitEntries.grfInheritance], eax
0x10004802  push    [ebp+pSid]; pSid
0x10004805  lea     eax, [ebp+pListOfExplicitEntries.Trustee]
0x10004808  push    eax; pTrustee
0x10004809  call    ds:BuildTrusteeWithSidW
0x1000480f  push    [ebp+lpString2]; lpString2
0x10004812  call    sub_10004260
0x10004817  push    [ebp+lpString2]; lpString2
0x1000481a  mov     edi, eax
0x1000481c  push    offset String1; "ServiceInstall"
0x10004821  mov     [ebp+ObjectType], edi
0x10004824  call    ds:lstrcmpW
0x1000482a  mov     ecx, [ebp+var_1C]
0x1000482d  test    eax, eax
0x1000482f  jnz     short loc_1000483A
0x10004831  or      ecx, 8Dh
0x10004837  mov     [ebp+var_1C], ecx
0x1000483a  mov     [ebp+pListOfExplicitEntries.grfAccessPermissions], ecx
0x1000483d  test    edi, edi
0x1000483f  jz      loc_100049C7
0x10004845  lea     eax, [ebp+ppSecurityDescriptor]
0x10004848  xor     ecx, ecx
0x1000484a  push    eax; ppSecurityDescriptor
0x1000484b  push    ecx; ppSacl
0x1000484c  lea     eax, [ebp+ppDacl]
0x1000484f  push    eax; ppDacl
0x10004850  push    ecx; ppsidGroup
  ... truncated ...
```
