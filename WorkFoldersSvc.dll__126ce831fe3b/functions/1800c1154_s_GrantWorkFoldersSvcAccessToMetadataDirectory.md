# s_GrantWorkFoldersSvcAccessToMetadataDirectory

- ea: `0x1800c1154`
- end: `0x1800c1395`
- name: `s_GrantWorkFoldersSvcAccessToMetadataDirectory`
- size: `577`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800bfb64`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x1800c1154`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800c1358`
- `KERNEL32!LocalFree` at `0x1800c1367`
- `KERNEL32!LocalFree` at `0x1800c1376`
- `KERNEL32!LocalFree` at `0x1800c1358`
- `KERNEL32!LocalFree` at `0x1800c1367`
- `KERNEL32!LocalFree` at `0x1800c1376`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800c1227`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800c1227`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800c12ab`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800c12ab`
- `ADVAPI32!SetEntriesInAclW` at `0x1800c12e2`
- `ADVAPI32!SetEntriesInAclW` at `0x1800c12e2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800c1329`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800c1329`

## string_xrefs

- `0x1800c11c2`: `s_GrantWorkFoldersSvcAccessToMetadataDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall s_GrantWorkFoldersSvcAccessToMetadataDirectory(LPWSTR pObjectName)
{
  _BYTE *v2; // rax
  char v3; // cl
  __int16 v4; // ax
  __int16 v5; // ax
  signed int NamedSecurityInfoW; // eax
  bool v7; // sf
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-9h] BYREF
  int v13; // [rsp+44h] [rbp-5h]
  char v14; // [rsp+48h] [rbp-1h]
  const char *v15; // [rsp+50h] [rbp+7h]
  __int64 v16; // [rsp+58h] [rbp+Fh]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp+17h] BYREF
  PSID Sid; // [rsp+B0h] [rbp+67h] BYREF
  PACL NewAcl; // [rsp+B8h] [rbp+6Fh] BYREF
  PACL OldAcl; // [rsp+C0h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( (v2[68] & 0x20) == 0 || (v3 = 1, v2[65] < 6u) )
    v3 = 0;
  v13 = 1021;
  v14 = v3;
  v15 = "s_GrantWorkFoldersSvcAccessToMetadataDirectory";
  v4 = 1029;
  v16 = 0;
  Sid = 0;
  OldAcl = 0;
  NewAcl = 0;
  hMem = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( !pObjectName || (LOWORD(v13) = 1029, v4 = 1030, !*pObjectName) )
  {
    LastFailureAsHRESULT = -2147024809;
    HIWORD(v13) = v4;
    goto LABEL_30;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v13) = 1030;
  if ( ConvertStringSidToSidW(L"S-1-5-80-3006764832-2469330069-4024865495-2754276538-3243839463", &Sid) )
  {
    LastFailureAsHRESULT = 0;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    LOWORD(v13) = 1040;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
    NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
    if ( NamedSecurityInfoW > 0 )
      NamedSecurityInfoW = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    LastFailureAsHRESULT = NamedSecurityInfoW;
    v7 = NamedSecurityInfoW < 0;
    v5 = 1059;
    if ( !v7 )
    {
      LOWORD(v13) = 1059;
      v8 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      LastFailureAsHRESULT = v8;
      v7 = v8 < 0;
      v5 = 1061;
      if ( !v7 )
      {
        LOWORD(v13) = 1061;
        v9 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        LastFailureAsHRESULT = v9;
        v7 = v9 < 0;
        v5 = 1070;
        if ( !v7 )
        {
          LOWORD(v13) = 1070;
          goto LABEL_24;
        }
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    v5 = 1040;
  }
  HIWORD(v13) = v5;
LABEL_24:
  if ( Sid )
    LocalFree(Sid);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
LABEL_30:
  v10 = LastFailureAsHRESULT;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x1800c1154  push    rbp
0x1800c1156  push    rbx
0x1800c1157  push    rdi
0x1800c1158  lea     rbp, [rsp-47h]
0x1800c115d  sub     rsp, 90h
0x1800c1164  mov     rbx, rcx
0x1800c1167  mov     rax, cs:WPP_GLOBAL_Control
0x1800c116e  lea     rcx, WPP_GLOBAL_Control
0x1800c1175  cmp     rax, rcx
0x1800c1178  jz      short loc_1800C11A2
0x1800c117a  test    byte ptr [rax+44h], 20h
0x1800c117e  jz      short loc_1800C11A2
0x1800c1180  cmp     byte ptr [rax+41h], 6
0x1800c1184  jb      short loc_1800C11A2
0x1800c1186  mov     rcx, [rax+38h]
0x1800c118a  lea     r8, WPP_dbe8969e182c3b657e3bce81cc6e8544_Traceguids
0x1800c1191  mov     edx, 2Fh ; '/'
0x1800c1196  call    WPP_SF_
0x1800c119b  mov     rax, cs:WPP_GLOBAL_Control
0x1800c11a2  xor     edi, edi
0x1800c11a4  test    byte ptr [rax+44h], 20h
0x1800c11a8  jz      short loc_1800C11B2
0x1800c11aa  cmp     byte ptr [rax+41h], 6
0x1800c11ae  mov     cl, 1
0x1800c11b0  jnb     short loc_1800C11B5
0x1800c11b2  mov     cl, dil
0x1800c11b5  mov     [rbp+57h+var_5C], 3FDh
0x1800c11bc  xorps   xmm0, xmm0
0x1800c11bf  mov     [rbp+57h+var_58], cl
0x1800c11c2  lea     rax, aSGrantworkfold; "s_GrantWorkFoldersSvcAccessToMetadataDi"...
0x1800c11c9  mov     [rbp+57h+var_50], rax
0x1800c11cd  mov     eax, 405h
0x1800c11d2  mov     [rbp+57h+var_48], rdi
0x1800c11d6  mov     [rbp+57h+Sid], rdi
0x1800c11da  mov     [rbp+57h+OldAcl], rdi
0x1800c11de  mov     [rbp+57h+NewAcl], rdi
0x1800c11e2  mov     [rbp+57h+hMem], rdi
0x1800c11e6  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1800c11ea  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1800c11ee  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800c11f2  test    rbx, rbx
0x1800c11f5  jnz     short loc_1800C1207
0x1800c11f7  mov     [rbp+57h+var_60], 80070057h
0x1800c11fe  mov     word ptr [rbp+57h+var_5C+2], ax
0x1800c1202  jmp     loc_1800C137C
0x1800c1207  mov     word ptr [rbp+57h+var_5C], ax
0x1800c120b  mov     eax, 406h
0x1800c1210  cmp     [rbx], di
0x1800c1213  jz      short loc_1800C11F7
0x1800c1215  lea     rdx, [rbp+57h+Sid]; Sid
0x1800c1219  mov     [rbp+57h+var_60], edi
0x1800c121c  lea     rcx, StringSid; "S-1-5-80-3006764832-2469330069-40248654"...
0x1800c1223  mov     word ptr [rbp+57h+var_5C], ax
0x1800c1227  call    cs:__imp_ConvertStringSidToSidW
0x1800c122d  test    eax, eax
0x1800c122f  jnz     short loc_1800C1247
0x1800c1231  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c1236  mov     [rbp+57h+var_60], eax
0x1800c1239  mov     eax, 410h
0x1800c123e  mov     word ptr [rbp+57h+var_5C+2], ax
0x1800c1242  jmp     loc_1800C134F
0x1800c1247  xor     r9d, r9d; ppsidOwner
0x1800c124a  mov     [rbp+57h+var_60], edi
0x1800c124d  mov     eax, 410h
0x1800c1252  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800c1259  mov     word ptr [rbp+57h+var_5C], ax
0x1800c125d  mov     rcx, rbx; pObjectName
0x1800c1260  mov     rax, [rbp+57h+Sid]
0x1800c1264  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800c1268  lea     edx, [r9+1]; ObjectType
0x1800c126c  lea     rax, [rbp+57h+hMem]
0x1800c1270  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800c1277  mov     [rsp+0A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800c127c  lea     r8d, [r9+4]; SecurityInfo
0x1800c1280  lea     rax, [rbp+57h+OldAcl]
0x1800c1284  mov     [rsp+0A0h+ppSacl], rdi; ppSacl
0x1800c1289  mov     [rsp+0A0h+ppDacl], rax; ppDacl
0x1800c128e  mov     [rsp+0A0h+ppsidGroup], rdi; ppsidGroup
0x1800c1293  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x1800c129a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], edi
0x1800c129d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800c12a4  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x1800c12a8  mov     [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], edi
0x1800c12ab  call    cs:__imp_GetNamedSecurityInfoW
0x1800c12b1  test    eax, eax
0x1800c12b3  jle     short loc_1800C12BD
0x1800c12b5  movzx   eax, ax
0x1800c12b8  or      eax, 80070000h
0x1800c12bd  mov     [rbp+57h+var_60], eax
0x1800c12c0  test    eax, eax
0x1800c12c2  mov     eax, 423h
0x1800c12c7  js      loc_1800C123E
0x1800c12cd  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x1800c12d1  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800c12d5  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800c12d9  mov     word ptr [rbp+57h+var_5C], ax
0x1800c12dd  mov     ecx, 1; cCountOfExplicitEntries
0x1800c12e2  call    cs:__imp_SetEntriesInAclW
0x1800c12e8  test    eax, eax
0x1800c12ea  jle     short loc_1800C12F4
0x1800c12ec  movzx   eax, ax
0x1800c12ef  or      eax, 80070000h
0x1800c12f4  mov     [rbp+57h+var_60], eax
0x1800c12f7  test    eax, eax
0x1800c12f9  mov     eax, 425h
0x1800c12fe  js      loc_1800C123E
0x1800c1304  xor     r9d, r9d; psidOwner
0x1800c1307  mov     word ptr [rbp+57h+var_5C], ax
0x1800c130b  mov     rax, [rbp+57h+NewAcl]
0x1800c130f  mov     rcx, rbx; pObjectName
0x1800c1312  mov     [rsp+0A0h+ppSacl], rdi; pSacl
0x1800c1317  mov     [rsp+0A0h+ppDacl], rax; pDacl
0x1800c131c  lea     edx, [r9+1]; ObjectType
0x1800c1320  mov     [rsp+0A0h+ppsidGroup], rdi; psidGroup
0x1800c1325  lea     r8d, [r9+4]; SecurityInfo
0x1800c1329  call    cs:__imp_SetNamedSecurityInfoW
0x1800c132f  test    eax, eax
0x1800c1331  jle     short loc_1800C133B
0x1800c1333  movzx   eax, ax
0x1800c1336  or      eax, 80070000h
0x1800c133b  mov     [rbp+57h+var_60], eax
0x1800c133e  test    eax, eax
0x1800c1340  mov     eax, 42Eh
0x1800c1345  js      loc_1800C123E
0x1800c134b  mov     word ptr [rbp+57h+var_5C], ax
0x1800c134f  mov     rcx, [rbp+57h+Sid]; hMem
0x1800c1353  test    rcx, rcx
0x1800c1356  jz      short loc_1800C135E
0x1800c1358  call    cs:__imp_LocalFree
0x1800c135e  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800c1362  test    rcx, rcx
0x1800c1365  jz      short loc_1800C136D
0x1800c1367  call    cs:__imp_LocalFree
0x1800c136d  mov     rcx, [rbp+57h+hMem]; hMem
0x1800c1371  test    rcx, rcx
0x1800c1374  jz      short loc_1800C137C
0x1800c1376  call    cs:__imp_LocalFree
0x1800c137c  mov     ebx, [rbp+57h+var_60]
0x1800c137f  lea     rcx, [rbp+57h+var_60]; this
0x1800c1383  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800c1388  mov     eax, ebx
0x1800c138a  add     rsp, 90h
0x1800c1391  pop     rdi
0x1800c1392  pop     rbx
0x1800c1393  pop     rbp
0x1800c1394  retn
```
