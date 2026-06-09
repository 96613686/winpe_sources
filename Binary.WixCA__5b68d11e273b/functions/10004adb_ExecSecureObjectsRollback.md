# ExecSecureObjectsRollback

- ea: `0x10004adb`
- end: `0x10004da5`
- name: `ExecSecureObjectsRollback`
- size: `714`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10004260`
- `0x10004adb`
- `0x1000a952`
- `0x1000ad15`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e13e`
- `0x1000e662`
- `0x1000ef44`
- `0x1000efcc`
- `0x100106cb`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorControl` at `0x10004c63`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x10004c63`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x10004c26`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x10004c26`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x10004ce1`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x10004ce1`
- `KERNEL32!GetLastError` at `0x10004be7`
- `KERNEL32!GetLastError` at `0x10004c37`
- `KERNEL32!GetLastError` at `0x10004c6d`
- `KERNEL32!GetLastError` at `0x10004d05`
- `KERNEL32!GetLastError` at `0x10004bdd`
- `KERNEL32!GetLastError` at `0x10004c37`
- `KERNEL32!LocalFree` at `0x10004d8a`
- `KERNEL32!LocalFree` at `0x10004d8a`

## string_xrefs

- `0x10004c02`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\secureobj.cpp`
- `0x10004c88`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\secureobj.cpp`
- `0x10004c95`: `failed to get security descriptor control for object: %ls`
- `0x10004ae5`: `ExecSecureObjectsRollback`
- `0x10004c0c`: `failed to convert security descriptor string to a valid security descriptor`
- `0x10004c41`: `failed to get security descriptor's DACL - error code: %d`
- `0x10004c51`: `security descriptor does not contain a DACL`
- `0x10004d0b`: `failed to set security info for object: %ls error code: %d`

## pseudocode

```c
int __stdcall ExecSecureObjectsRollback(MSIHANDLE hInstall)
{
  signed int v1; // edi
  signed int v2; // esi
  signed int LastError; // eax
  bool v4; // sf
  signed int v5; // eax
  bool v6; // sf
  SECURITY_INFORMATION v7; // eax
  const char *v9; // [esp-8h] [ebp-44h]
  const char *v10; // [esp-8h] [ebp-44h]
  ULONG SecurityDescriptorSize; // [esp+8h] [ebp-34h] BYREF
  SE_OBJECT_TYPE ObjectType; // [esp+Ch] [ebp-30h]
  WORD pControl[2]; // [esp+10h] [ebp-2Ch] BYREF
  DWORD dwRevision; // [esp+14h] [ebp-28h] BYREF
  BOOL bDaclDefaulted; // [esp+18h] [ebp-24h] BYREF
  PACL pDacl; // [esp+1Ch] [ebp-20h] BYREF
  BOOL bDaclPresent; // [esp+20h] [ebp-1Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [esp+24h] [ebp-18h] BYREF
  LPCWSTR StringSecurityDescriptor; // [esp+28h] [ebp-14h] BYREF
  DWORD pcchValueBuf; // [esp+2Ch] [ebp-10h] BYREF
  wchar_t SubStr[2]; // [esp+30h] [ebp-Ch] BYREF
  LPCWSTR lpString2; // [esp+34h] [ebp-8h] BYREF
  LPWSTR pObjectName; // [esp+38h] [ebp-4h] BYREF

  v1 = 0;
  *(_DWORD *)SubStr = 0;
  pcchValueBuf = 0;
  pObjectName = 0;
  lpString2 = 0;
  StringSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  *(_DWORD *)pControl = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  dwRevision = 0;
  v2 = sub_1000D51F(hInstall, (int)"ExecSecureObjectsRollback");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_40;
  }
  v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to get CustomActionData");
    goto LABEL_40;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v2 = sub_1000EFCC((wchar_t)SubStr, (int)&pObjectName);
  if ( v2 < 0 || (v2 = sub_1000EFCC((wchar_t)SubStr, (int)&lpString2), v2 < 0) )
  {
    sub_1000DA66(v2, "failed to process CustomActionData");
    goto LABEL_40;
  }
  ObjectType = sub_10004260(lpString2);
  if ( ObjectType )
  {
    v2 = sub_1000EFCC((wchar_t)SubStr, (int)&StringSecurityDescriptor);
    if ( v2 < 0 || (v2 = sub_1000EF44((wchar_t)SubStr, (int)&hInstall), v2 < 0) )
    {
      v9 = "failed to process CustomActionData";
LABEL_17:
      sub_1000DA66(v2, v9);
      goto LABEL_40;
    }
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            StringSecurityDescriptor,
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      LastError = GetLastError();
      v2 = LastError;
      v4 = LastError < 0;
      if ( LastError > 0 )
      {
        v2 = (unsigned __int16)LastError | 0x80070000;
        v4 = 1;
      }
      if ( v4 )
      {
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\secureobj.cpp", 839, v2);
        v9 = "failed to convert security descriptor string to a valid security descriptor";
        goto LABEL_17;
      }
    }
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v2 = -2147418113;
      GetLastError();
      sub_1000DA66(-2147418113, "failed to get security descriptor's DACL - error code: %d");
      goto LABEL_40;
    }
    if ( !bDaclPresent )
    {
      v10 = "security descriptor does not contain a DACL";
LABEL_30:
      v2 = -2147418113;
      sub_1000DA66(-2147418113, v10);
      goto LABEL_40;
    }
    if ( !GetSecurityDescriptorControl(SecurityDescriptor, pControl, &dwRevision) )
    {
      v5 = GetLastError();
      v2 = v5;
      v6 = v5 < 0;
      if ( v5 > 0 )
      {
        v2 = (unsigned __int16)v5 | 0x80070000;
        v6 = 1;
      }
      if ( v6 )
      {
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\secureobj.cpp", 858, v2);
        sub_1000DA66(v2, "failed to get security descriptor control for object: %ls");
        goto LABEL_40;
      }
    }
    if ( hInstall )
    {
      if ( hInstall != 1 )
      {
        v10 = "unrecognized value in CustomActionData";
        goto LABEL_30;
      }
      v7 = -2147483644;
    }
    else
    {
      v7 = 4;
    }
    v1 = SetNamedSecurityInfoW(pObjectName, ObjectType, v7, 0, 0, pDacl, 0);
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    if ( v2 < 0 )
    {
      v2 = v1;
      if ( v1 > 0 )
        v2 = (unsigned __int16)v1 | 0x80070000;
      GetLastError();
      sub_1000DA66(v2, "failed to set security info for object: %ls error code: %d");
    }
  }
  else
  {
    sub_1000DA66(-2147418113, "unknown object type: %ls");
    v2 = -2147418113;
    sub_1000E13E(25522, -2147418113, INSTALLMESSAGE_ERROR, 1);
  }
LABEL_40:
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( pObjectName )
    sub_1000A952(pObjectName);
  if ( lpString2 )
    sub_1000A952(lpString2);
  if ( StringSecurityDescriptor )
    sub_1000A952(StringSecurityDescriptor);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10004adb  push    ebp
0x10004adc  mov     ebp, esp
0x10004ade  sub     esp, 34h
0x10004ae1  push    esi
0x10004ae2  push    edi
0x10004ae3  xor     edi, edi
0x10004ae5  push    offset aExecsecureobje_3; "ExecSecureObjectsRollback"
0x10004aea  push    [ebp+hInstall]; hInstall
0x10004aed  mov     dword ptr [ebp+SubStr], edi
0x10004af0  mov     [ebp+pcchValueBuf], edi
0x10004af3  mov     [ebp+pObjectName], edi
0x10004af6  mov     [ebp+lpString2], edi
0x10004af9  mov     [ebp+StringSecurityDescriptor], edi
0x10004afc  mov     [ebp+SecurityDescriptor], edi
0x10004aff  mov     dword ptr [ebp+pControl], edi
0x10004b02  mov     [ebp+pDacl], edi
0x10004b05  mov     [ebp+bDaclPresent], edi
0x10004b08  mov     [ebp+bDaclDefaulted], edi
0x10004b0b  mov     [ebp+dwRevision], edi
0x10004b0e  call    sub_1000D51F
0x10004b13  mov     esi, eax
0x10004b15  test    esi, esi
0x10004b17  jns     short loc_10004B2B
0x10004b19  push    offset aFailedToInitia_2; "failed to initialize"
0x10004b1e  push    esi
0x10004b1f  call    sub_1000DA66
0x10004b24  pop     ecx
0x10004b25  pop     ecx
0x10004b26  jmp     loc_10004D49
0x10004b2b  lea     eax, [ebp+pcchValueBuf]
0x10004b2e  push    eax; pcchValueBuf
0x10004b2f  push    offset aCustomactionda; "CustomActionData"
0x10004b34  call    sub_1000E662
0x10004b39  mov     esi, eax
0x10004b3b  test    esi, esi
0x10004b3d  jns     short loc_10004B46
0x10004b3f  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10004b44  jmp     short loc_10004B1E
0x10004b46  push    [ebp+pcchValueBuf]
0x10004b49  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10004b4e  push    edi
0x10004b4f  call    sub_1000D9AB
0x10004b54  mov     eax, [ebp+pcchValueBuf]
0x10004b57  add     esp, 0Ch
0x10004b5a  mov     dword ptr [ebp+SubStr], eax
0x10004b5d  lea     eax, [ebp+pObjectName]
0x10004b60  push    eax; int
0x10004b61  lea     eax, [ebp+SubStr]
0x10004b64  push    eax; SubStr
0x10004b65  call    sub_1000EFCC
0x10004b6a  mov     esi, eax
0x10004b6c  test    esi, esi
0x10004b6e  jns     short loc_10004B77
0x10004b70  push    offset aFailedToProces; "failed to process CustomActionData"
0x10004b75  jmp     short loc_10004B1E
0x10004b77  lea     eax, [ebp+lpString2]
0x10004b7a  push    eax; int
0x10004b7b  lea     eax, [ebp+SubStr]
0x10004b7e  push    eax; SubStr
0x10004b7f  call    sub_1000EFCC
0x10004b84  mov     esi, eax
0x10004b86  test    esi, esi
0x10004b88  js      short loc_10004B70
0x10004b8a  push    ebx
0x10004b8b  push    [ebp+lpString2]; lpString2
0x10004b8e  call    sub_10004260
0x10004b93  mov     [ebp+ObjectType], eax
0x10004b96  test    eax, eax
0x10004b98  jz      loc_10004D1B
0x10004b9e  lea     eax, [ebp+StringSecurityDescriptor]
0x10004ba1  push    eax; int
0x10004ba2  lea     eax, [ebp+SubStr]
0x10004ba5  push    eax; SubStr
0x10004ba6  call    sub_1000EFCC
0x10004bab  mov     esi, eax
0x10004bad  test    esi, esi
0x10004baf  js      short loc_10004BC4
0x10004bb1  lea     eax, [ebp+hInstall]
0x10004bb4  push    eax; int
0x10004bb5  lea     eax, [ebp+SubStr]
0x10004bb8  push    eax; SubStr
0x10004bb9  call    sub_1000EF44
0x10004bbe  mov     esi, eax
0x10004bc0  test    esi, esi
0x10004bc2  jns     short loc_10004BCB
0x10004bc4  push    offset aFailedToProces; "failed to process CustomActionData"
0x10004bc9  jmp     short loc_10004C11
0x10004bcb  lea     eax, [ebp+SecurityDescriptorSize]
0x10004bce  push    eax; SecurityDescriptorSize
0x10004bcf  lea     eax, [ebp+SecurityDescriptor]
0x10004bd2  push    eax; SecurityDescriptor
0x10004bd3  push    1; StringSDRevision
0x10004bd5  push    [ebp+StringSecurityDescriptor]; StringSecurityDescriptor
0x10004bd8  call    ConvertStringSecurityDescriptorToSecurityDescriptorW
0x10004bdd  mov     ebx, ds:GetLastError
0x10004be3  test    eax, eax
0x10004be5  jnz     short loc_10004C17
0x10004be7  call    ebx ; GetLastError
0x10004be9  mov     esi, eax
0x10004beb  test    esi, esi
0x10004bed  jle     short loc_10004BFA
0x10004bef  movzx   esi, si
0x10004bf2  or      esi, 80070000h
0x10004bf8  test    esi, esi
0x10004bfa  jns     short loc_10004C17
0x10004bfc  push    esi
0x10004bfd  push    347h
0x10004c02  push    offset aDAWork1SSrcExt_1; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10004c07  call    nullsub_1
0x10004c0c  push    offset aFailedToConver; "failed to convert security descriptor s"...
0x10004c11  push    esi
0x10004c12  jmp     loc_10004CC1
0x10004c17  lea     eax, [ebp+bDaclDefaulted]
0x10004c1a  push    eax; lpbDaclDefaulted
0x10004c1b  lea     eax, [ebp+pDacl]
0x10004c1e  push    eax; pDacl
0x10004c1f  lea     eax, [ebp+bDaclPresent]
0x10004c22  push    eax; lpbDaclPresent
0x10004c23  push    [ebp+SecurityDescriptor]; pSecurityDescriptor
0x10004c26  call    ds:GetSecurityDescriptorDacl
0x10004c2c  test    eax, eax
0x10004c2e  jnz     short loc_10004C4C
0x10004c30  mov     ebx, 8000FFFFh
0x10004c35  mov     esi, ebx
0x10004c37  call    ds:GetLastError
0x10004c3d  push    eax
0x10004c3e  push    [ebp+StringSecurityDescriptor]
0x10004c41  push    offset aFailedToGetSec_1; "failed to get security descriptor's DAC"...
0x10004c46  push    ebx
0x10004c47  jmp     loc_10004D11
0x10004c4c  cmp     [ebp+bDaclPresent], edi
0x10004c4f  jnz     short loc_10004C58
0x10004c51  push    offset aSecurityDescri; "security descriptor does not contain a "...
0x10004c56  jmp     short loc_10004CB9
0x10004c58  lea     eax, [ebp+dwRevision]
0x10004c5b  push    eax; lpdwRevision
0x10004c5c  lea     eax, [ebp+pControl]
0x10004c5f  push    eax; pControl
0x10004c60  push    [ebp+SecurityDescriptor]; pSecurityDescriptor
0x10004c63  call    ds:GetSecurityDescriptorControl
0x10004c69  test    eax, eax
0x10004c6b  jnz     short loc_10004CA8
0x10004c6d  call    ebx ; GetLastError
0x10004c6f  mov     esi, eax
0x10004c71  test    esi, esi
0x10004c73  jle     short loc_10004C80
0x10004c75  movzx   esi, si
0x10004c78  or      esi, 80070000h
0x10004c7e  test    esi, esi
0x10004c80  jns     short loc_10004CA8
0x10004c82  push    esi
0x10004c83  push    35Ah
0x10004c88  push    offset aDAWork1SSrcExt_1; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10004c8d  call    nullsub_1
0x10004c92  push    [ebp+pObjectName]
0x10004c95  push    offset aFailedToGetSec; "failed to get security descriptor contr"...
0x10004c9a  push    esi
0x10004c9b  call    sub_1000DA66
0x10004ca0  add     esp, 0Ch
0x10004ca3  jmp     loc_10004D48
0x10004ca8  mov     eax, [ebp+hInstall]
0x10004cab  sub     eax, edi
0x10004cad  jz      short loc_10004CD1
0x10004caf  sub     eax, 1
0x10004cb2  jz      short loc_10004CCA
0x10004cb4  push    offset aUnrecognizedVa; "unrecognized value in CustomActionData"
0x10004cb9  mov     ebx, 8000FFFFh
0x10004cbe  mov     esi, ebx
0x10004cc0  push    ebx
0x10004cc1  call    sub_1000DA66
0x10004cc6  pop     ecx
0x10004cc7  pop     ecx
0x10004cc8  jmp     short loc_10004D48
0x10004cca  mov     eax, 80000004h
0x10004ccf  jmp     short loc_10004CD4
0x10004cd1  push    4
0x10004cd3  pop     eax
0x10004cd4  push    edi; pSacl
0x10004cd5  push    [ebp+pDacl]; pDacl
0x10004cd8  push    edi; psidGroup
0x10004cd9  push    edi; psidOwner
0x10004cda  push    eax; SecurityInfo
0x10004cdb  push    [ebp+ObjectType]; ObjectType
0x10004cde  push    [ebp+pObjectName]; pObjectName
0x10004ce1  call    ds:SetNamedSecurityInfoW
0x10004ce7  mov     edi, eax
0x10004ce9  movzx   eax, di
0x10004cec  mov     esi, edi
0x10004cee  or      eax, 80070000h
0x10004cf3  test    edi, edi
0x10004cf5  jle     short loc_10004CF9
0x10004cf7  mov     esi, eax
0x10004cf9  test    esi, esi
0x10004cfb  jns     short loc_10004D48
0x10004cfd  mov     esi, edi
0x10004cff  test    edi, edi
0x10004d01  jle     short loc_10004D05
0x10004d03  mov     esi, eax
0x10004d05  call    ebx ; GetLastError
0x10004d07  push    eax
0x10004d08  push    [ebp+pObjectName]
0x10004d0b  push    offset aFailedToSetSec_0; "failed to set security info for object:"...
0x10004d10  push    esi
0x10004d11  call    sub_1000DA66
0x10004d16  add     esp, 10h
0x10004d19  jmp     short loc_10004D48
0x10004d1b  push    [ebp+lpString2]
0x10004d1e  mov     ebx, 8000FFFFh
0x10004d23  push    offset aUnknownObjectT; "unknown object type: %ls"
0x10004d28  push    ebx
0x10004d29  call    sub_1000DA66
0x10004d2e  push    [ebp+lpString2]
0x10004d31  mov     esi, ebx
0x10004d33  push    1; int
0x10004d35  push    1000000h; eMessageType
0x10004d3a  push    ebx; int
0x10004d3b  push    63B2h; iValue
0x10004d40  call    sub_1000E13E
0x10004d45  add     esp, 20h
0x10004d48  pop     ebx
0x10004d49  cmp     [ebp+pcchValueBuf], 0
0x10004d4d  jz      short loc_10004D57
0x10004d4f  push    [ebp+pcchValueBuf]
0x10004d52  call    sub_1000A952
0x10004d57  cmp     [ebp+pObjectName], 0
0x10004d5b  jz      short loc_10004D65
0x10004d5d  push    [ebp+pObjectName]
0x10004d60  call    sub_1000A952
0x10004d65  cmp     [ebp+lpString2], 0
0x10004d69  jz      short loc_10004D73
0x10004d6b  push    [ebp+lpString2]
0x10004d6e  call    sub_1000A952
0x10004d73  cmp     [ebp+StringSecurityDescriptor], 0
0x10004d77  jz      short loc_10004D81
0x10004d79  push    [ebp+StringSecurityDescriptor]
0x10004d7c  call    sub_1000A952
0x10004d81  cmp     [ebp+SecurityDescriptor], 0
0x10004d85  jz      short loc_10004D90
0x10004d87  push    [ebp+SecurityDescriptor]; hMem
0x10004d8a  call    ds:LocalFree
0x10004d90  test    esi, esi
0x10004d92  jns     short loc_10004D99
0x10004d94  mov     edi, 643h
0x10004d99  push    edi
0x10004d9a  call    sub_1000D4AE
0x10004d9f  pop     edi
0x10004da0  pop     esi
0x10004da1  leave
0x10004da2  retn    4
```
