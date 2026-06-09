# RegisterInprocClass(_GUID const &,ushort const *,ushort const *)

- ea: `0x18000dddc`
- end: `0x18000e282`
- name: `?RegisterInprocClass@@YAJAEBU_GUID@@PEBG1@Z`
- size: `1190`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019f1c`

## callees

- `0x180004ae0`
- `0x18000d7fc`
- `0x18000dddc`
- `0x1800ce43c`
- `0x1800cee78`
- `0x1800dc038`
- `0x1800de258`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000de32`
- `KERNEL32!GetLastError` at `0x18000de32`
- `KERNEL32!LocalFree` at `0x18000de85`
- `KERNEL32!LocalFree` at `0x18000df8a`
- `KERNEL32!LocalFree` at `0x18000e023`
- `KERNEL32!LocalFree` at `0x18000e181`
- `KERNEL32!LocalFree` at `0x18000e266`
- `KERNEL32!LocalFree` at `0x18000de85`
- `KERNEL32!LocalFree` at `0x18000df8a`
- `KERNEL32!LocalFree` at `0x18000e023`
- `KERNEL32!LocalFree` at `0x18000e181`
- `KERNEL32!LocalFree` at `0x18000e266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e13c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e23d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e13c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e158`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e23d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000de28`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000de28`

## string_xrefs

- `0x18000df14`: `CLSID\%ls`
- `0x18000e076`: `CLSID\%ls\InProcServer32`

## pseudocode

```c
__int64 __fastcall RegisterInprocClass(struct _GUID *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const WCHAR *v4; // rcx
  unsigned __int16 **v5; // r8
  signed int LastError; // eax
  signed int StringFromGUID; // ebx
  const struct std::nothrow_t *v9; // rdx
  void *v10; // rbx
  const struct std::nothrow_t *v11; // rdx
  int v12; // edi
  struct _SECURITY_ATTRIBUTES *v13; // r8
  void *v14; // rdi
  const struct std::nothrow_t *v15; // rdx
  int v16; // esi
  const unsigned __int16 *v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  struct _SECURITY_ATTRIBUTES *v20; // r8
  void *v21; // rsi
  const struct std::nothrow_t *v22; // rdx
  const unsigned __int16 *v23; // r9
  int v24; // r14d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  const unsigned __int16 *v27; // r9
  struct _GUID v28; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 v29[4]; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v30; // [rsp+38h] [rbp-18h]
  __int64 v31; // [rsp+40h] [rbp-10h]
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+38h] BYREF
  HKEY v34; // [rsp+98h] [rbp+48h] BYREF

  hKey = (HKEY)a1;
  SecurityDescriptor = 0;
  v4 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-3418"
        "522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GA;;;BA)(A;OICIIO;GA;;;BA)(A;;GRGX;;;B"
        "U)(A;OICIIO;GRGX;;;BU)(A;;GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  if ( !(_BYTE)g_fDevMode )
    v4 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-34"
          "18522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GRGX;;;BU)(A;OICIIO;GRGX;;;BU)(A;;"
          "GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    StringFromGUID = LastError;
    if ( LastError > 0 )
      StringFromGUID = (unsigned __int16)LastError | 0x80070000;
    if ( StringFromGUID < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids,
          (unsigned int)StringFromGUID);
LABEL_10:
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return (unsigned int)StringFromGUID;
    }
  }
  v30 = SecurityDescriptor;
  *(_QWORD *)v29 = 24;
  v31 = 0;
  *(_QWORD *)&v28.Data1 = 0;
  StringFromGUID = ShieldProvider::GetStringFromGUID((ShieldProvider *)&CLSID_DefenderShellServiceObject, &v28, v5);
  if ( StringFromGUID < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids,
        (unsigned int)StringFromGUID);
    if ( *(_QWORD *)&v28.Data1 )
      operator delete(*(void **)&v28.Data1, v9);
    goto LABEL_10;
  }
  v10 = *(void **)&v28.Data1;
  *(_QWORD *)v28.Data4 = 0;
  v12 = CommonUtil::NewSprintfW(
          (CommonUtil *)v28.Data4,
          (unsigned __int16 **)L"CLSID\\%ls",
          *(const unsigned __int16 **)&v28.Data1);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids,
        (unsigned int)v12);
    if ( *(_QWORD *)v28.Data4 )
      operator delete(*(void **)v28.Data4, v11);
    if ( v10 )
      operator delete(v10, v11);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return (unsigned int)v12;
  }
  v14 = *(void **)v28.Data4;
  LOBYTE(v13) = (_BYTE)g_fDevMode;
  hKey = 0;
  v16 = ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(*(ShieldProvider **)v28.Data4, v29, v13, &hKey);
  if ( v16 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v19 = 41;
LABEL_34:
    WPP_SF_d(v18[2], v19, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids, (unsigned int)v16);
LABEL_35:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v14 )
      operator delete(v14, v15);
    if ( v10 )
      operator delete(v10, v15);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return (unsigned int)v16;
  }
  v16 = CommonUtil::UtilRegSetValueString((CommonUtil *)hKey, 0, L"Defender SSO", v17);
  if ( v16 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_35;
    v19 = 42;
    goto LABEL_34;
  }
  *(_QWORD *)v28.Data4 = 0;
  v16 = CommonUtil::NewSprintfW(
          (CommonUtil *)v28.Data4,
          (unsigned __int16 **)L"CLSID\\%ls\\InProcServer32",
          (const unsigned __int16 *)v10);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids,
        (unsigned int)v16);
    if ( *(_QWORD *)v28.Data4 )
      operator delete(*(void **)v28.Data4, v15);
    goto LABEL_35;
  }
  v21 = *(void **)v28.Data4;
  LOBYTE(v20) = (_BYTE)g_fDevMode;
  v34 = 0;
  v24 = ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(*(ShieldProvider **)v28.Data4, v29, v20, &v34);
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_59;
    v26 = 44;
LABEL_58:
    WPP_SF_d(v25[2], v26, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids, (unsigned int)v24);
LABEL_59:
    if ( v34 )
      RegCloseKey(v34);
    if ( v21 )
      operator delete(v21, v22);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v14 )
      operator delete(v14, v22);
    if ( v10 )
      operator delete(v10, v22);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return (unsigned int)v24;
  }
  v24 = CommonUtil::UtilRegSetValueString((CommonUtil *)v34, 0, a3, v23);
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_59;
    v26 = 45;
    goto LABEL_58;
  }
  v24 = CommonUtil::UtilRegSetValueString((CommonUtil *)v34, (HKEY)&stru_1800F4E58, L"Both", v27);
  if ( v24 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_59;
    v26 = 46;
    goto LABEL_58;
  }
  if ( v34 )
    RegCloseKey(v34);
  if ( v21 )
    operator delete(v21, v22);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 )
    operator delete(v14, v22);
  if ( v10 )
    operator delete(v10, v22);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x18000dddc  mov     [rsp-28h+arg_10], rbx
0x18000dde1  mov     [rsp-28h+SecurityDescriptor], rdx
0x18000dde6  mov     [rsp-28h+hKey], rcx
0x18000ddeb  push    rbp
0x18000ddec  push    rsi
0x18000dded  push    rdi
0x18000ddee  push    r14
0x18000ddf0  push    r15
0x18000ddf2  mov     rbp, rsp
0x18000ddf5  sub     rsp, 50h
0x18000ddf9  cmp     cs:?g_fDevMode@@3_NA, 0; bool g_fDevMode
0x18000de00  lea     rax, StringSecurityDescriptor; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x18000de07  mov     r15, r8
0x18000de0a  mov     [rbp+SecurityDescriptor], 0
0x18000de12  lea     rcx, aDPAGaS15809560; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x18000de19  cmovz   rcx, rax; StringSecurityDescriptor
0x18000de1d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000de21  xor     r9d, r9d; SecurityDescriptorSize
0x18000de24  lea     edx, [r9+1]; StringSDRevision
0x18000de28  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000de2e  test    eax, eax
0x18000de30  jnz     short loc_18000DE92
0x18000de32  call    cs:__imp_GetLastError
0x18000de38  mov     ebx, eax
0x18000de3a  test    eax, eax
0x18000de3c  jle     short loc_18000DE47
0x18000de3e  movzx   ebx, ax
0x18000de41  or      ebx, 80070000h
0x18000de47  test    ebx, ebx
0x18000de49  jns     short loc_18000DE92
0x18000de4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de52  lea     rax, WPP_GLOBAL_Control
0x18000de59  cmp     rcx, rax
0x18000de5c  jz      short loc_18000DE7C
0x18000de5e  test    byte ptr [rcx+1Ch], 1
0x18000de62  jz      short loc_18000DE7C
0x18000de64  mov     rcx, [rcx+10h]
0x18000de68  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000de6f  mov     edx, 26h ; '&'
0x18000de74  mov     r9d, ebx
0x18000de77  call    WPP_SF_d
0x18000de7c  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000de80  test    rcx, rcx
0x18000de83  jz      short loc_18000DE8B
0x18000de85  call    cs:__imp_LocalFree
0x18000de8b  mov     eax, ebx
0x18000de8d  jmp     loc_18000E26E
0x18000de92  mov     rax, [rbp+SecurityDescriptor]
0x18000de96  lea     rdx, [rbp+var_30]; struct _GUID *
0x18000de9a  lea     rcx, CLSID_DefenderShellServiceObject; this
0x18000dea1  mov     [rbp+var_18], rax
0x18000dea5  mov     qword ptr [rbp+var_20], 18h
0x18000dead  mov     [rbp+var_10], 0
0x18000deb5  mov     qword ptr [rbp+var_30.Data1], 0
0x18000debd  call    ?GetStringFromGUID@ShieldProvider@@YAJAEBU_GUID@@PEAPEAG@Z; ShieldProvider::GetStringFromGUID(_GUID const &,ushort * *)
0x18000dec2  mov     ebx, eax
0x18000dec4  test    eax, eax
0x18000dec6  jns     short loc_18000DF10
0x18000dec8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000decf  lea     rax, WPP_GLOBAL_Control
0x18000ded6  cmp     rcx, rax
0x18000ded9  jz      short loc_18000DEF9
0x18000dedb  test    byte ptr [rcx+1Ch], 1
0x18000dedf  jz      short loc_18000DEF9
0x18000dee1  mov     rcx, [rcx+10h]
0x18000dee5  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000deec  mov     edx, 27h ; '''
0x18000def1  mov     r9d, ebx
0x18000def4  call    WPP_SF_d
0x18000def9  mov     rcx, qword ptr [rbp+var_30.Data1]; void *
0x18000defd  test    rcx, rcx
0x18000df00  jz      loc_18000DE7C
0x18000df06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df0b  jmp     loc_18000DE7C
0x18000df10  mov     rbx, qword ptr [rbp+var_30.Data1]
0x18000df14  lea     rdx, aClsidLs; "CLSID\\%ls"
0x18000df1b  mov     r8, rbx; unsigned __int16 *
0x18000df1e  mov     qword ptr [rbp+var_30.Data4], 0
0x18000df26  lea     rcx, [rbp+var_30.Data4]; this
0x18000df2a  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18000df2f  mov     edi, eax
0x18000df31  test    eax, eax
0x18000df33  jns     short loc_18000DF97
0x18000df35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df3c  lea     rax, WPP_GLOBAL_Control
0x18000df43  cmp     rcx, rax
0x18000df46  jz      short loc_18000DF66
0x18000df48  test    byte ptr [rcx+1Ch], 1
0x18000df4c  jz      short loc_18000DF66
0x18000df4e  mov     rcx, [rcx+10h]
0x18000df52  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000df59  mov     edx, 28h ; '('
0x18000df5e  mov     r9d, edi
0x18000df61  call    WPP_SF_d
0x18000df66  mov     rcx, qword ptr [rbp+var_30.Data4]; void *
0x18000df6a  test    rcx, rcx
0x18000df6d  jz      short loc_18000DF74
0x18000df6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df74  test    rbx, rbx
0x18000df77  jz      short loc_18000DF81
0x18000df79  mov     rcx, rbx; void *
0x18000df7c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000df81  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000df85  test    rcx, rcx
0x18000df88  jz      short loc_18000DF90
0x18000df8a  call    cs:__imp_LocalFree
0x18000df90  mov     eax, edi
0x18000df92  jmp     loc_18000E26E
0x18000df97  mov     rdi, qword ptr [rbp+var_30.Data4]
0x18000df9b  lea     r9, [rbp+hKey]; bool
0x18000df9f  mov     r8b, cs:?g_fDevMode@@3_NA; struct _SECURITY_ATTRIBUTES *
0x18000dfa6  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18000dfaa  mov     rcx, rdi; this
0x18000dfad  mov     [rbp+hKey], 0
0x18000dfb5  call    ?GetRegKeyUnderClassesReAcledForWrite@ShieldProvider@@YAJPEAGPEAU_SECURITY_ATTRIBUTES@@_NPEAPEAUHKEY__@@@Z; ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(ushort *,_SECURITY_ATTRIBUTES *,bool,HKEY__ * *)
0x18000dfba  mov     esi, eax
0x18000dfbc  test    eax, eax
0x18000dfbe  jns     short loc_18000E030
0x18000dfc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfc7  lea     rax, WPP_GLOBAL_Control
0x18000dfce  cmp     rcx, rax
0x18000dfd1  jz      short loc_18000DFF1
0x18000dfd3  test    byte ptr [rcx+1Ch], 1
0x18000dfd7  jz      short loc_18000DFF1
0x18000dfd9  mov     edx, 29h ; ')'
0x18000dfde  mov     rcx, [rcx+10h]
0x18000dfe2  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000dfe9  mov     r9d, esi
0x18000dfec  call    WPP_SF_d
0x18000dff1  mov     rcx, [rbp+hKey]; hKey
0x18000dff5  test    rcx, rcx
0x18000dff8  jz      short loc_18000E000
0x18000dffa  call    cs:__imp_RegCloseKey
0x18000e000  test    rdi, rdi
0x18000e003  jz      short loc_18000E00D
0x18000e005  mov     rcx, rdi; void *
0x18000e008  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e00d  test    rbx, rbx
0x18000e010  jz      short loc_18000E01A
0x18000e012  mov     rcx, rbx; void *
0x18000e015  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e01a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000e01e  test    rcx, rcx
0x18000e021  jz      short loc_18000E029
0x18000e023  call    cs:__imp_LocalFree
0x18000e029  mov     eax, esi
0x18000e02b  jmp     loc_18000E26E
0x18000e030  mov     rcx, [rbp+hKey]; this
0x18000e034  lea     r8, aDefenderSso; "Defender SSO"
0x18000e03b  xor     edx, edx; HKEY
0x18000e03d  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000e042  mov     esi, eax
0x18000e044  test    eax, eax
0x18000e046  jns     short loc_18000E06B
0x18000e048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e04f  lea     rax, WPP_GLOBAL_Control
0x18000e056  cmp     rcx, rax
0x18000e059  jz      short loc_18000DFF1
0x18000e05b  test    byte ptr [rcx+1Ch], 1
0x18000e05f  jz      short loc_18000DFF1
0x18000e061  mov     edx, 2Ah ; '*'
0x18000e066  jmp     loc_18000DFDE
0x18000e06b  mov     r8, rbx; unsigned __int16 *
0x18000e06e  mov     qword ptr [rbp+var_30.Data4], 0
0x18000e076  lea     rdx, aClsidLsInprocs; "CLSID\\%ls\\InProcServer32"
0x18000e07d  lea     rcx, [rbp+var_30.Data4]; this
0x18000e081  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18000e086  mov     esi, eax
0x18000e088  test    eax, eax
0x18000e08a  jns     short loc_18000E0D4
0x18000e08c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e093  lea     rax, WPP_GLOBAL_Control
0x18000e09a  cmp     rcx, rax
0x18000e09d  jz      short loc_18000E0BD
0x18000e09f  test    byte ptr [rcx+1Ch], 1
0x18000e0a3  jz      short loc_18000E0BD
0x18000e0a5  mov     rcx, [rcx+10h]
0x18000e0a9  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000e0b0  mov     edx, 2Bh ; '+'
0x18000e0b5  mov     r9d, esi
0x18000e0b8  call    WPP_SF_d
0x18000e0bd  mov     rcx, qword ptr [rbp+var_30.Data4]; void *
0x18000e0c1  test    rcx, rcx
0x18000e0c4  jz      loc_18000DFF1
0x18000e0ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e0cf  jmp     loc_18000DFF1
0x18000e0d4  mov     rsi, qword ptr [rbp+var_30.Data4]
0x18000e0d8  lea     r9, [rbp+arg_18]; bool
0x18000e0dc  mov     r8b, cs:?g_fDevMode@@3_NA; struct _SECURITY_ATTRIBUTES *
0x18000e0e3  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18000e0e7  mov     rcx, rsi; this
0x18000e0ea  mov     [rbp+arg_18], 0
0x18000e0f2  call    ?GetRegKeyUnderClassesReAcledForWrite@ShieldProvider@@YAJPEAGPEAU_SECURITY_ATTRIBUTES@@_NPEAPEAUHKEY__@@@Z; ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(ushort *,_SECURITY_ATTRIBUTES *,bool,HKEY__ * *)
0x18000e0f7  mov     r14d, eax
0x18000e0fa  test    eax, eax
0x18000e0fc  jns     loc_18000E18F
0x18000e102  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e109  lea     rax, WPP_GLOBAL_Control
0x18000e110  cmp     rcx, rax
0x18000e113  jz      short loc_18000E133
0x18000e115  test    byte ptr [rcx+1Ch], 1
0x18000e119  jz      short loc_18000E133
0x18000e11b  mov     edx, 2Ch ; ','
0x18000e120  mov     rcx, [rcx+10h]
0x18000e124  lea     r8, WPP_55d254afc3b63f8c351b142c0db24d90_Traceguids
0x18000e12b  mov     r9d, r14d
0x18000e12e  call    WPP_SF_d
0x18000e133  mov     rcx, [rbp+arg_18]; hKey
0x18000e137  test    rcx, rcx
0x18000e13a  jz      short loc_18000E142
0x18000e13c  call    cs:__imp_RegCloseKey
0x18000e142  test    rsi, rsi
0x18000e145  jz      short loc_18000E14F
0x18000e147  mov     rcx, rsi; void *
0x18000e14a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e14f  mov     rcx, [rbp+hKey]; hKey
0x18000e153  test    rcx, rcx
0x18000e156  jz      short loc_18000E15E
0x18000e158  call    cs:__imp_RegCloseKey
0x18000e15e  test    rdi, rdi
0x18000e161  jz      short loc_18000E16B
0x18000e163  mov     rcx, rdi; void *
0x18000e166  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e16b  test    rbx, rbx
0x18000e16e  jz      short loc_18000E178
0x18000e170  mov     rcx, rbx; void *
0x18000e173  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e178  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000e17c  test    rcx, rcx
0x18000e17f  jz      short loc_18000E187
0x18000e181  call    cs:__imp_LocalFree
0x18000e187  mov     eax, r14d
0x18000e18a  jmp     loc_18000E26E
0x18000e18f  mov     rcx, [rbp+arg_18]; this
0x18000e193  mov     r8, r15; unsigned __int16 *
0x18000e196  xor     edx, edx; HKEY
0x18000e198  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000e19d  mov     r14d, eax
0x18000e1a0  test    eax, eax
0x18000e1a2  jns     short loc_18000E1CF
0x18000e1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ab  lea     rax, WPP_GLOBAL_Control
0x18000e1b2  cmp     rcx, rax
0x18000e1b5  jz      loc_18000E133
0x18000e1bb  test    byte ptr [rcx+1Ch], 1
0x18000e1bf  jz      loc_18000E133
0x18000e1c5  mov     edx, 2Dh ; '-'
0x18000e1ca  jmp     loc_18000E120
0x18000e1cf  mov     rcx, [rbp+arg_18]; this
0x18000e1d3  lea     r8, aBoth; "Both"
0x18000e1da  lea     rdx, stru_1800F4E58; HKEY
0x18000e1e1  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBG1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,ushort const *,ushort const *)
0x18000e1e6  mov     r14d, eax
0x18000e1e9  test    eax, eax
0x18000e1eb  jns     short loc_18000E218
0x18000e1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1f4  lea     rax, WPP_GLOBAL_Control
0x18000e1fb  cmp     rcx, rax
0x18000e1fe  jz      loc_18000E133
0x18000e204  test    byte ptr [rcx+1Ch], 1
0x18000e208  jz      loc_18000E133
0x18000e20e  mov     edx, 2Eh ; '.'
0x18000e213  jmp     loc_18000E120
0x18000e218  mov     rcx, [rbp+arg_18]; hKey
0x18000e21c  test    rcx, rcx
0x18000e21f  jz      short loc_18000E227
0x18000e221  call    cs:__imp_RegCloseKey
0x18000e227  test    rsi, rsi
0x18000e22a  jz      short loc_18000E234
0x18000e22c  mov     rcx, rsi; void *
0x18000e22f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e234  mov     rcx, [rbp+hKey]; hKey
0x18000e238  test    rcx, rcx
0x18000e23b  jz      short loc_18000E243
0x18000e23d  call    cs:__imp_RegCloseKey
0x18000e243  test    rdi, rdi
0x18000e246  jz      short loc_18000E250
0x18000e248  mov     rcx, rdi; void *
0x18000e24b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e250  test    rbx, rbx
0x18000e253  jz      short loc_18000E25D
0x18000e255  mov     rcx, rbx; void *
0x18000e258  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e25d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000e261  test    rcx, rcx
0x18000e264  jz      short loc_18000E26C
0x18000e266  call    cs:__imp_LocalFree
0x18000e26c  xor     eax, eax
0x18000e26e  mov     rbx, [rsp+50h+arg_10]
0x18000e276  add     rsp, 50h
0x18000e27a  pop     r15
0x18000e27c  pop     r14
0x18000e27e  pop     rdi
0x18000e27f  pop     rsi
0x18000e280  pop     rbp
0x18000e281  retn
```
