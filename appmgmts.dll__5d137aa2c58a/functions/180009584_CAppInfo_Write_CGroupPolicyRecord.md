# CAppInfo::Write(CGroupPolicyRecord *)

- ea: `0x180009584`
- end: `0x18000a140`
- name: `?Write@CAppInfo@@QEAAJPEAVCGroupPolicyRecord@@@Z`
- size: `3004`
- prototype: `__int64 __fastcall(CAppInfo *__hidden this, struct CGroupPolicyRecord *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c8c0`

## callees

- `0x1800016d0`
- `0x1800061a0`
- `0x1800071e4`
- `0x180009584`
- `0x18000a148`
- `0x180012fbc`
- `0x18001b1a0`
- `0x180029cc0`
- `0x180029eb4`
- `0x180029f40`
- `0x180029fd0`
- `0x18002a054`
- `0x18002a110`
- `0x18002a1cc`
- `0x18002a2b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d6c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009d2c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009d2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800096bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800096bd`

## string_xrefs

- `0x1800097b7`: `SecurityDescriptor`
- `0x18000996d`: `InstallationUI`
- `0x1800099a0`: `InstallationUI`
- `0x1800099b7`: `DemandInstallable`
- `0x1800099da`: `DemandInstallable`
- `0x180009c0c`: `UninstallUnmanaged`
- `0x180009c2b`: `UninstallUnmanaged`
- `0x180009ea2`: `OnDemandFileExtension`
- `0x180009f26`: `OnDemandFileExtension`
- `0x180009ed0`: `OnDemandClsid`
- `0x180009f54`: `OnDemandClsid`

## pseudocode

```c
__int64 __fastcall CAppInfo::Write(CAppInfo *this, struct CGroupPolicyRecord *a2)
{
  int RsopEntryType; // r15d
  unsigned int v5; // esi
  __int64 result; // rax
  const unsigned __int16 *v7; // r8
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r8d
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  const unsigned __int16 *v31; // r8
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  BOOL v38; // r8d
  int v39; // eax
  int v40; // eax
  int v41; // r8d
  int v42; // eax
  __int64 v43; // rdx
  int v44; // ecx
  const unsigned __int16 *v45; // r8
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // eax
  int v50; // eax
  const unsigned __int16 *v51; // rsi
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // r8d
  int v57; // eax
  int v58; // eax
  int v59; // r8d
  int v60; // eax
  __int64 v61; // rcx
  int v62; // r8d
  int v63; // eax
  int v64; // eax
  int v65; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int16 v67[40]; // [rsp+30h] [rbp-98h] BYREF

  if ( *((_DWORD *)this + 74) )
    RsopEntryType = *(_DWORD *)(*((_QWORD *)this + 2) + 308LL) != 0 ? 3 : 1;
  else
    RsopEntryType = CAppInfo::GetRsopEntryType(this);
  v5 = CGroupPolicyRecord::SetValue(a2, L"EntryType", RsopEntryType);
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  LODWORD(result) = CGroupPolicyRecord::SetValue(a2, L"name", *((const unsigned __int16 **)this + 5));
  v5 = result;
  if ( (int)result >= 0 )
  {
    GuidToString((struct _GUID *)((char *)this + 24), v67);
    LODWORD(result) = CGroupPolicyRecord::SetValue(a2, L"ApplicationId", v67);
    v5 = result;
    if ( (int)result < 0 )
    {
      if ( !*(_DWORD *)&gDebugLevel )
        return v5;
      v7 = L"ApplicationId";
      goto LABEL_8;
    }
    result = CGroupPolicyRecord::SetValue(a2, L"EntryType", RsopEntryType);
    v5 = result;
    if ( (int)result < 0 )
    {
      if ( !*(_DWORD *)&gDebugLevel )
        return v5;
      v7 = L"EntryType";
      goto LABEL_8;
    }
    if ( !*((_DWORD *)a2 + 4) )
      return result;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v8 = CGroupPolicyRecord::SetValue(a2, L"creationTime", &SystemTime);
    if ( v8 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"creationTime", (unsigned int)v8);
    v9 = CGroupPolicyRecord::SetValue(a2, L"GPOID", *((const unsigned __int16 **)this + 8));
    if ( v9 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"GPOID", (unsigned int)v9);
    v10 = CGroupPolicyRecord::SetValue(a2, L"SOMID", *((const unsigned __int16 **)this + 7));
    if ( v10 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"SOMID", (unsigned int)v10);
    v11 = CGroupPolicyRecord::SetValue(a2, L"EntryType", RsopEntryType);
    if ( v11 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"EntryType", (unsigned int)v11);
    v13 = CGroupPolicyRecord::SetValue(a2, v12, *((unsigned __int8 **)this + 30), *((_DWORD *)this + 62));
    if ( v13 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"SecurityDescriptor", (unsigned int)v13);
    v14 = CGroupPolicyRecord::SetValue(a2, L"VersionNumberLo", *((_DWORD *)this + 41));
    if ( v14 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"VersionNumberLo", (unsigned int)v14);
    v15 = CGroupPolicyRecord::SetValue(a2, L"VersionNumberHi", *((_DWORD *)this + 40));
    if ( v15 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"VersionNumberHi", (unsigned int)v15);
    v16 = CGroupPolicyRecord::SetValue(a2, L"ProductId", *((const unsigned __int16 **)this + 10));
    if ( v16 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"ProductId", (unsigned int)v16);
    v17 = CGroupPolicyRecord::SetValue(a2, L"ScriptFile", *((const unsigned __int16 **)this + 12));
    if ( v17 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"ScriptFile", (unsigned int)v17);
    v18 = CGroupPolicyRecord::SetValue(a2, L"LanguageId", *((unsigned __int16 *)this + 90));
    if ( v18 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"LanguageId", (unsigned int)v18);
    v19 = CGroupPolicyRecord::SetValue(a2, L"DeploymentType", 2 - (unsigned int)((*((_DWORD *)this + 53) & 0x400) != 0));
    if ( v19 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"DeploymentType", (unsigned int)v19);
    if ( (*((_DWORD *)this + 53) & 8) != 0 )
      v20 = 1;
    else
      v20 = (*((_DWORD *)this + 53) & 0x2000 | 0x4000u) >> 13;
    v21 = CGroupPolicyRecord::SetValue(a2, L"AssignmentType", v20);
    if ( v21 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"AssignmentType", (unsigned int)v21);
    v22 = CGroupPolicyRecord::SetValue(a2, L"InstallationUI", (unsigned int)(*((_DWORD *)this + 52) == 5) + 1);
    if ( v22 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"InstallationUI", (unsigned int)v22);
    v23 = CGroupPolicyRecord::SetValue(a2, L"DemandInstallable", *((_DWORD *)this + 53) & 0x40);
    if ( v23 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"DemandInstallable", (unsigned int)v23);
    v24 = CGroupPolicyRecord::SetValue(
            a2,
            L"LossOfScopeAction",
            (unsigned int)((*((_DWORD *)this + 53) & 0x800) != 0) + 1);
    if ( v24 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"LossOfScopeAction", (unsigned int)v24);
    v25 = CGroupPolicyRecord::SetValue(a2, L"IgnoreLanguage", *((_DWORD *)this + 53) & 0x20000);
    if ( v25 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"IgnoreLanguage", (unsigned int)v25);
    v26 = CGroupPolicyRecord::SetValue(a2, L"PackageLocation", *((const unsigned __int16 **)this + 44));
    if ( v26 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"PackageLocation", (unsigned int)v26);
    v27 = CGroupPolicyRecord::SetValue(a2, L"Categories", *((unsigned __int16 ***)this + 42), *((_DWORD *)this + 86));
    if ( v27 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"Categories", (unsigned int)v27);
    v28 = CGroupPolicyRecord::SetValue(a2, L"Transforms", *((unsigned __int16 ***)this + 40), *((_DWORD *)this + 82));
    if ( v28 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"Transforms", (unsigned int)v28);
    v30 = CGroupPolicyRecord::SetValue(a2, v29, *((int **)this + 46), *((_DWORD *)this + 90));
    if ( v30 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"MachineArchitectures", (unsigned int)v30);
    v31 = &word_18002F430;
    if ( *((_QWORD *)this + 18) )
      v31 = (const unsigned __int16 *)*((_QWORD *)this + 18);
    v32 = CGroupPolicyRecord::SetValue(a2, L"Publisher", v31);
    if ( v32 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"Publisher", (unsigned int)v32);
    v33 = CGroupPolicyRecord::SetValue(a2, L"RedeployCount", *((_DWORD *)this + 51));
    if ( v33 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"RedeployCount", (unsigned int)v33);
    v34 = CGroupPolicyRecord::SetValue(a2, L"UpgradeSettingsMandatory", *((_DWORD *)this + 53) & 0x4000);
    if ( v34 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"UpgradeSettingsMandatory", (unsigned int)v34);
    v35 = CGroupPolicyRecord::SetValue(a2, L"UninstallUnmanaged", *((_DWORD *)this + 59));
    if ( v35 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"UninstallUnmanaged", (unsigned int)v35);
    v36 = CGroupPolicyRecord::SetValue(a2, L"DisplayInARP", *((_DWORD *)this + 53) & 0x20);
    if ( v36 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"DisplayInARP", (unsigned int)v36);
    v37 = CGroupPolicyRecord::SetValue(a2, L"SupportURL", *((const unsigned __int16 **)this + 19));
    if ( v37 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"SupportURL", (unsigned int)v37);
    if ( RsopEntryType == 2 )
      CAppInfo::WriteRemovalProperties(this, a2);
    v38 = 0;
    if ( !*((_DWORD *)this + 94) )
    {
      LOBYTE(v38) = (*((_DWORD *)this + 53) & 0x10000) == 0;
      if ( *((_DWORD *)this + 42) == 6 )
        v38 = (*((_DWORD *)this + 53) & 0x10000) != 0;
    }
    v39 = CGroupPolicyRecord::SetValue(a2, L"AllowX86OnIA64", v38);
    if ( v39 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"AllowX86OnIA64", (unsigned int)v39);
    SystemTime = 0;
    if ( FileTimeToSystemTime((const FILETIME *)((char *)this + 172), &SystemTime) )
    {
      v40 = CGroupPolicyRecord::SetValue(a2, L"DeploymentLastModifyTime", &SystemTime);
      if ( v40 < 0 && *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"DeploymentLastModifyTime", (unsigned int)v40);
    }
    else
    {
      GetLastError();
    }
    v41 = 0;
    if ( *((_DWORD *)this + 42) == 5 )
    {
      v41 = 1;
    }
    else if ( *((_DWORD *)this + 42) == 6 )
    {
      v41 = 2;
    }
    v42 = CGroupPolicyRecord::SetValue(a2, L"PackageType", v41);
    if ( v42 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"PackageType", (unsigned int)v42);
    v43 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v43 + 308) )
    {
LABEL_157:
      v58 = *((_DWORD *)this + 46);
      switch ( v58 )
      {
        case 512:
          v59 = 4;
          break;
        case 1024:
          v59 = 2;
          break;
        case 1536:
          v59 = 1;
          break;
        default:
          v59 = 3;
          if ( v58 != 2048 )
            v59 = 5;
          break;
      }
      v60 = CGroupPolicyRecord::SetValue(a2, L"LanguageMatch", v59);
      if ( v60 < 0 && *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"LanguageMatch", (unsigned int)v60);
      v61 = *((_QWORD *)this + 2);
      v62 = 0;
      v63 = *(_DWORD *)(v61 + 440);
      if ( v63 == 2 )
        goto LABEL_183;
      if ( v63 == 1 || *((_DWORD *)this + 74) )
      {
        v64 = *((_DWORD *)this + 53);
        if ( (v64 & 0x400) != 0 || (*((_BYTE *)this + 224) & 1) != 0 )
        {
          v62 = 1;
          goto LABEL_183;
        }
        if ( (v64 & 0x40000) != 0 )
        {
          v62 = 3;
LABEL_183:
          v65 = CGroupPolicyRecord::SetValue(a2, L"Eligibility", v62);
          v5 = v65;
          if ( v65 < 0 )
          {
            if ( *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xC29u, L"Eligibility", (unsigned int)v65);
          }
          CAppInfo::LogUpgrades(this, a2);
          return v5;
        }
        if ( *((_DWORD *)this + 95) != 3 && !*((_DWORD *)this + 55) )
        {
          v62 = 2;
          if ( *(_DWORD *)(v61 + 396) == 1 )
            v62 = 4;
          goto LABEL_183;
        }
      }
      v62 = 2;
      goto LABEL_183;
    }
    v44 = *(_DWORD *)(v43 + 444);
    v45 = *(const unsigned __int16 **)(v43 + 448);
    if ( v44 )
    {
      v46 = v44 - 1;
      if ( !v46 )
      {
        v51 = L"OnDemandClsid";
        *((_DWORD *)this + 95) = 5;
        goto LABEL_139;
      }
      v47 = v46 - 1;
      if ( !v47 )
      {
        v51 = L"OnDemandProgid";
        *((_DWORD *)this + 95) = 7;
        goto LABEL_139;
      }
      v48 = v47 - 1;
      if ( !v48 )
      {
        v51 = L"OnDemandFileExtension";
        *((_DWORD *)this + 95) = 4;
        goto LABEL_139;
      }
      if ( v48 == 1 && !*((_DWORD *)this + 95) && !*((_DWORD *)this + 74) )
      {
        v49 = *((_DWORD *)this + 53);
        if ( (v49 & 0x400) != 0 )
          goto LABEL_135;
        if ( (v49 & 8) == 0 )
          goto LABEL_143;
        v50 = *((_DWORD *)this + 56);
        if ( (v50 & 0x200) != 0 )
        {
          *((_DWORD *)this + 95) = 3;
          goto LABEL_143;
        }
        if ( (v50 & 1) != 0 )
        {
LABEL_135:
          *((_DWORD *)this + 95) = 1;
        }
        else
        {
          *((_DWORD *)this + 95) = 2;
          if ( !*(_DWORD *)(v43 + 456) )
          {
            v51 = (const unsigned __int16 *)*((_QWORD *)this + 56);
            v45 = (const unsigned __int16 *)*((_QWORD *)this + 55);
            *((_DWORD *)this + 95) = *((_DWORD *)this + 109);
            if ( v51 )
            {
LABEL_139:
              v52 = CGroupPolicyRecord::SetValue(a2, v51, v45);
              if ( v52 < 0 && *(_DWORD *)&gDebugLevel )
                _DebugMsg(4, 0xC29u, v51, (unsigned int)v52);
              goto LABEL_153;
            }
          }
        }
      }
    }
    else
    {
      *((_DWORD *)this + 95) = 2;
    }
LABEL_143:
    if ( RsopEntryType != 2 )
    {
      v53 = CGroupPolicyRecord::ClearValue(a2, L"OnDemandFileExtension");
      if ( v53 < 0 && *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"OnDemandFileExtension", (unsigned int)v53);
      v54 = CGroupPolicyRecord::ClearValue(a2, L"OnDemandClsid");
      if ( v54 < 0 && *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"OnDemandClsid", (unsigned int)v54);
      v55 = CGroupPolicyRecord::ClearValue(a2, L"OnDemandProgid");
      if ( v55 < 0 && *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"OnDemandProgid", (unsigned int)v55);
    }
LABEL_153:
    v56 = *((_DWORD *)this + 95);
    if ( v56 )
    {
      v57 = CGroupPolicyRecord::SetValue(a2, L"ApplyCause", v56);
      if ( v57 < 0 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC29u, L"ApplyCause", (unsigned int)v57);
      }
    }
    goto LABEL_157;
  }
  if ( *(_DWORD *)&gDebugLevel )
  {
    v7 = L"name";
LABEL_8:
    _DebugMsg(4, 0xC29u, v7, (unsigned int)result);
  }
  return v5;
}

```

## disassembly

```asm
0x180009584  mov     [rsp+arg_10], rbx
0x180009589  push    rbp
0x18000958a  push    rsi
0x18000958b  push    rdi
0x18000958c  push    r12
0x18000958e  push    r13
0x180009590  push    r14
0x180009592  push    r15
0x180009594  sub     rsp, 90h
0x18000959b  mov     rax, cs:__security_cookie
0x1800095a2  xor     rax, rsp
0x1800095a5  mov     [rsp+0C8h+var_48], rax
0x1800095ad  xor     r12d, r12d
0x1800095b0  mov     r14, rdx
0x1800095b3  mov     rbx, rcx
0x1800095b6  cmp     [rcx+128h], r12d
0x1800095bd  jz      short loc_1800095D7
0x1800095bf  mov     rax, [rcx+10h]
0x1800095c3  mov     ecx, [rax+134h]
0x1800095c9  neg     ecx; this
0x1800095cb  sbb     r15d, r15d
0x1800095ce  and     r15d, 2
0x1800095d2  inc     r15d
0x1800095d5  jmp     short loc_1800095DF
0x1800095d7  call    ?GetRsopEntryType@CAppInfo@@QEAAJXZ; CAppInfo::GetRsopEntryType(void)
0x1800095dc  mov     r15d, eax
0x1800095df  lea     r13, aEntrytype; "EntryType"
0x1800095e6  mov     r8d, r15d; int
0x1800095e9  mov     rdx, r13; unsigned __int16 *
0x1800095ec  mov     rcx, r14; this
0x1800095ef  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x1800095f4  mov     esi, eax
0x1800095f6  test    eax, eax
0x1800095f8  js      loc_18000A113
0x1800095fe  mov     r8, [rbx+28h]; unsigned __int16 *
0x180009602  lea     rdx, aName_0; "name"
0x180009609  mov     rcx, r14; this
0x18000960c  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009611  mov     esi, eax
0x180009613  test    eax, eax
0x180009615  jns     short loc_180009642
0x180009617  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18000961e  jz      loc_18000A113
0x180009624  lea     r8, aName_0; "name"
0x18000962b  mov     r9d, eax
0x18000962e  mov     edx, 0C29h; unsigned int
0x180009633  mov     ecx, 4; unsigned int
0x180009638  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000963d  jmp     loc_18000A113
0x180009642  lea     rcx, [rbx+18h]; struct _GUID *
0x180009646  lea     rdx, [rsp+0C8h+var_98]; unsigned __int16 *
0x18000964b  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x180009650  lea     r8, [rsp+0C8h+var_98]; unsigned __int16 *
0x180009655  mov     rcx, r14; this
0x180009658  lea     rdx, aApplicationid; "ApplicationId"
0x18000965f  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009664  mov     esi, eax
0x180009666  test    eax, eax
0x180009668  jns     short loc_180009680
0x18000966a  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009671  jz      loc_18000A113
0x180009677  lea     r8, aApplicationid; "ApplicationId"
0x18000967e  jmp     short loc_18000962B
0x180009680  mov     r8d, r15d; int
0x180009683  mov     rdx, r13; unsigned __int16 *
0x180009686  mov     rcx, r14; this
0x180009689  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000968e  mov     esi, eax
0x180009690  test    eax, eax
0x180009692  jns     short loc_1800096A6
0x180009694  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18000969b  jz      loc_18000A113
0x1800096a1  mov     r8, r13
0x1800096a4  jmp     short loc_18000962B
0x1800096a6  cmp     [r14+10h], r12d
0x1800096aa  jz      loc_18000A115
0x1800096b0  xorps   xmm0, xmm0
0x1800096b3  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x1800096b8  movups  xmmword ptr [rsp+0C8h+SystemTime.wYear], xmm0
0x1800096bd  call    cs:__imp_GetSystemTime
0x1800096c3  lea     r8, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x1800096c8  mov     rcx, r14; this
0x1800096cb  lea     rdx, aCreationtime_0; "creationTime"
0x1800096d2  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAU_SYSTEMTIME@@@Z; CGroupPolicyRecord::SetValue(ushort const *,_SYSTEMTIME *)
0x1800096d7  mov     ebp, 0C29h
0x1800096dc  mov     edi, 4
0x1800096e1  test    eax, eax
0x1800096e3  jns     short loc_180009701
0x1800096e5  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800096ec  jz      short loc_180009701
0x1800096ee  mov     r9d, eax
0x1800096f1  lea     r8, aCreationtime_0; "creationTime"
0x1800096f8  mov     edx, ebp; unsigned int
0x1800096fa  mov     ecx, edi; unsigned int
0x1800096fc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009701  mov     r8, [rbx+40h]; unsigned __int16 *
0x180009705  lea     rdx, aGpoid; "GPOID"
0x18000970c  mov     rcx, r14; this
0x18000970f  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009714  test    eax, eax
0x180009716  jns     short loc_180009734
0x180009718  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18000971f  jz      short loc_180009734
0x180009721  mov     r9d, eax
0x180009724  lea     r8, aGpoid; "GPOID"
0x18000972b  mov     edx, ebp; unsigned int
0x18000972d  mov     ecx, edi; unsigned int
0x18000972f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009734  mov     r8, [rbx+38h]; unsigned __int16 *
0x180009738  lea     rdx, aSomid; "SOMID"
0x18000973f  mov     rcx, r14; this
0x180009742  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009747  test    eax, eax
0x180009749  jns     short loc_180009767
0x18000974b  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009752  jz      short loc_180009767
0x180009754  mov     r9d, eax
0x180009757  lea     r8, aSomid; "SOMID"
0x18000975e  mov     edx, ebp; unsigned int
0x180009760  mov     ecx, edi; unsigned int
0x180009762  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009767  mov     r8d, r15d; int
0x18000976a  mov     rdx, r13; unsigned __int16 *
0x18000976d  mov     rcx, r14; this
0x180009770  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x180009775  test    eax, eax
0x180009777  jns     short loc_180009791
0x180009779  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009780  jz      short loc_180009791
0x180009782  mov     r9d, eax
0x180009785  mov     r8, r13
0x180009788  mov     edx, ebp; unsigned int
0x18000978a  mov     ecx, edi; unsigned int
0x18000978c  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009791  mov     r9d, [rbx+0F8h]; unsigned int
0x180009798  mov     rcx, r14; this
0x18000979b  mov     r8, [rbx+0F0h]; unsigned __int8 *
0x1800097a2  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAEK@Z; CGroupPolicyRecord::SetValue(ushort const *,uchar *,ulong)
0x1800097a7  test    eax, eax
0x1800097a9  jns     short loc_1800097C7
0x1800097ab  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800097b2  jz      short loc_1800097C7
0x1800097b4  mov     r9d, eax
0x1800097b7  lea     r8, aSecuritydescri; "SecurityDescriptor"
0x1800097be  mov     edx, ebp; unsigned int
0x1800097c0  mov     ecx, edi; unsigned int
0x1800097c2  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800097c7  mov     r8d, [rbx+0A4h]; int
0x1800097ce  lea     rdx, aVersionnumberl_0; "VersionNumberLo"
0x1800097d5  mov     rcx, r14; this
0x1800097d8  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x1800097dd  test    eax, eax
0x1800097df  jns     short loc_1800097FD
0x1800097e1  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800097e8  jz      short loc_1800097FD
0x1800097ea  mov     r9d, eax
0x1800097ed  lea     r8, aVersionnumberl_0; "VersionNumberLo"
0x1800097f4  mov     edx, ebp; unsigned int
0x1800097f6  mov     ecx, edi; unsigned int
0x1800097f8  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800097fd  mov     r8d, [rbx+0A0h]; int
0x180009804  lea     rdx, aVersionnumberh_0; "VersionNumberHi"
0x18000980b  mov     rcx, r14; this
0x18000980e  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x180009813  test    eax, eax
0x180009815  jns     short loc_180009833
0x180009817  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18000981e  jz      short loc_180009833
0x180009820  mov     r9d, eax
0x180009823  lea     r8, aVersionnumberh_0; "VersionNumberHi"
0x18000982a  mov     edx, ebp; unsigned int
0x18000982c  mov     ecx, edi; unsigned int
0x18000982e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009833  mov     r8, [rbx+50h]; unsigned __int16 *
0x180009837  lea     rdx, aProductid; "ProductId"
0x18000983e  mov     rcx, r14; this
0x180009841  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009846  test    eax, eax
0x180009848  jns     short loc_180009866
0x18000984a  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009851  jz      short loc_180009866
0x180009853  mov     r9d, eax
0x180009856  lea     r8, aProductid; "ProductId"
0x18000985d  mov     edx, ebp; unsigned int
0x18000985f  mov     ecx, edi; unsigned int
0x180009861  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009866  mov     r8, [rbx+60h]; unsigned __int16 *
0x18000986a  lea     rdx, aScriptfile; "ScriptFile"
0x180009871  mov     rcx, r14; this
0x180009874  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x180009879  test    eax, eax
0x18000987b  jns     short loc_180009899
0x18000987d  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009884  jz      short loc_180009899
0x180009886  mov     r9d, eax
0x180009889  lea     r8, aScriptfile; "ScriptFile"
0x180009890  mov     edx, ebp; unsigned int
0x180009892  mov     ecx, edi; unsigned int
0x180009894  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009899  movzx   r8d, word ptr [rbx+0B4h]; int
0x1800098a1  lea     rdx, aLanguageid; "LanguageId"
0x1800098a8  mov     rcx, r14; this
0x1800098ab  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x1800098b0  test    eax, eax
0x1800098b2  jns     short loc_1800098D0
0x1800098b4  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800098bb  jz      short loc_1800098D0
0x1800098bd  mov     r9d, eax
0x1800098c0  lea     r8, aLanguageid; "LanguageId"
0x1800098c7  mov     edx, ebp; unsigned int
0x1800098c9  mov     ecx, edi; unsigned int
0x1800098cb  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800098d0  mov     eax, [rbx+0D4h]
0x1800098d6  lea     rdx, aDeploymenttype; "DeploymentType"
0x1800098dd  and     eax, 400h
0x1800098e2  mov     rcx, r14; this
0x1800098e5  neg     eax
0x1800098e7  sbb     r8d, r8d
0x1800098ea  add     r8d, 2; int
0x1800098ee  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x1800098f3  test    eax, eax
0x1800098f5  jns     short loc_180009913
0x1800098f7  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800098fe  jz      short loc_180009913
0x180009900  mov     r9d, eax
0x180009903  lea     r8, aDeploymenttype; "DeploymentType"
0x18000990a  mov     edx, ebp; unsigned int
0x18000990c  mov     ecx, edi; unsigned int
0x18000990e  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009913  mov     r8d, [rbx+0D4h]
0x18000991a  mov     esi, 4000h
0x18000991f  test    r8b, 8
0x180009923  jz      short loc_18000992D
0x180009925  mov     r8d, 1
0x18000992b  jmp     short loc_18000993B
0x18000992d  and     r8d, 2000h
0x180009934  or      r8d, esi
0x180009937  shr     r8d, 0Dh; int
0x18000993b  lea     rdx, aAssignmenttype; "AssignmentType"
0x180009942  mov     rcx, r14; this
0x180009945  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000994a  test    eax, eax
0x18000994c  jns     short loc_18000996A
0x18000994e  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009955  jz      short loc_18000996A
0x180009957  mov     r9d, eax
0x18000995a  lea     r8, aAssignmenttype; "AssignmentType"
0x180009961  mov     edx, ebp; unsigned int
0x180009963  mov     ecx, edi; unsigned int
0x180009965  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000996a  mov     r8d, r12d
0x18000996d  lea     rdx, aInstallationui; "InstallationUI"
0x180009974  mov     r13d, 5
0x18000997a  mov     rcx, r14; this
0x18000997d  cmp     [rbx+0D0h], r13d
0x180009984  setz    r8b
0x180009988  inc     r8d; int
0x18000998b  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x180009990  test    eax, eax
0x180009992  jns     short loc_1800099B0
0x180009994  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x18000999b  jz      short loc_1800099B0
0x18000999d  mov     r9d, eax
0x1800099a0  lea     r8, aInstallationui; "InstallationUI"
0x1800099a7  mov     edx, ebp; unsigned int
0x1800099a9  mov     ecx, edi; unsigned int
0x1800099ab  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800099b0  mov     r8d, [rbx+0D4h]
0x1800099b7  lea     rdx, aDemandinstalla; "DemandInstallable"
0x1800099be  and     r8d, 40h; int
0x1800099c2  mov     rcx, r14; this
0x1800099c5  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGH@Z; CGroupPolicyRecord::SetValue(ushort const *,int)
0x1800099ca  test    eax, eax
0x1800099cc  jns     short loc_1800099EA
0x1800099ce  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x1800099d5  jz      short loc_1800099EA
0x1800099d7  mov     r9d, eax
0x1800099da  lea     r8, aDemandinstalla; "DemandInstallable"
0x1800099e1  mov     edx, ebp; unsigned int
0x1800099e3  mov     ecx, edi; unsigned int
0x1800099e5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800099ea  mov     eax, [rbx+0D4h]
0x1800099f0  lea     rdx, aLossofscopeact; "LossOfScopeAction"
0x1800099f7  and     eax, 800h
0x1800099fc  mov     rcx, r14; this
0x1800099ff  neg     eax
0x180009a01  sbb     r8d, r8d
0x180009a04  neg     r8d
0x180009a07  inc     r8d; int
0x180009a0a  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x180009a0f  test    eax, eax
0x180009a11  jns     short loc_180009A2F
0x180009a13  cmp     cs:?gDebugLevel@@3KA, r12d; ulong gDebugLevel
0x180009a1a  jz      short loc_180009A2F
0x180009a1c  mov     r9d, eax
0x180009a1f  lea     r8, aLossofscopeact; "LossOfScopeAction"
0x180009a26  mov     edx, ebp; unsigned int
0x180009a28  mov     ecx, edi; unsigned int
0x180009a2a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180009a2f  mov     r8d, [rbx+0D4h]
  ... truncated ...
```
