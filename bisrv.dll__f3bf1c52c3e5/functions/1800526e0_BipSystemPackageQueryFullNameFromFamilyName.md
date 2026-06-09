# BipSystemPackageQueryFullNameFromFamilyName

- ea: `0x1800526e0`
- end: `0x180052ebb`
- name: `BipSystemPackageQueryFullNameFromFamilyName`
- size: `2011`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057614`

## callees

- `0x180017a4c`
- `0x180017d50`
- `0x180018eb8`
- `0x18001a1f0`
- `0x18001abd0`
- `0x18001b5f8`
- `0x180049bb0`
- `0x1800526e0`
- `0x18006db64`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180052817`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180052817`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180052de1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180052de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800528c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800527cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052e9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800527cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180052e9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052a2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052bec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052e7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052a2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052bec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180052e7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180052e68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800527a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800527a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180052a02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x180052a02`

## string_xrefs

- `0x180052b71`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18005292a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180052828`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052889`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180052b8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180052bae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180052bce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180052c0c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800527e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall BipSystemPackageQueryFullNameFromFamilyName(
        PSID Sid,
        unsigned __int16 *a2,
        unsigned int *a3,
        _WORD *a4)
{
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // ecx
  signed int v11; // ebx
  __int64 v12; // r8
  const char *v13; // r9
  int LastError; // ebx
  int v15; // eax
  int v16; // ebx
  int v17; // ebx
  int v18; // eax
  int v19; // ebx
  int v20; // edx
  int v21; // ebx
  int v22; // eax
  int v23; // edi
  int IsEmpty; // eax
  __int64 v25; // rcx
  bool v26; // bl
  int v27; // ebx
  unsigned int v28; // eax
  bool v29; // sf
  __int64 *v30; // rcx
  int v31; // eax
  __int64 v32; // rax
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // esi
  unsigned __int64 v38; // rdi
  _WORD *v39; // rcx
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  _WORD *v42; // r8
  __int64 v43; // r10
  __int64 v44; // r9
  _WORD *v45; // rcx
  __int64 v46; // rdi
  unsigned __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int UserDataCount; // [rsp+28h] [rbp-E0h]
  int UserDataCountb; // [rsp+28h] [rbp-E0h]
  int UserDataCounta; // [rsp+28h] [rbp-E0h]
  bool v59[8]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v60; // [rsp+40h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A8h]
  __int64 v64; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v65; // [rsp+70h] [rbp-98h] BYREF
  __int64 v66; // [rsp+78h] [rbp-90h]
  __int64 v67; // [rsp+80h] [rbp-88h]
  __int64 v68; // [rsp+88h] [rbp-80h] BYREF
  __int64 v69[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-60h]
  __int64 v71; // [rsp+B0h] [rbp-58h]
  __int64 v72; // [rsp+B8h] [rbp-50h]
  __int64 v73; // [rsp+C0h] [rbp-48h]
  __int64 v74; // [rsp+C8h] [rbp-40h]
  __int64 v75; // [rsp+D0h] [rbp-38h]
  __int128 v76; // [rsp+D8h] [rbp-30h]
  int v77; // [rsp+E8h] [rbp-20h]
  __int64 v78; // [rsp+F0h] [rbp-18h]
  __int64 v79; // [rsp+F8h] [rbp-10h]
  __int64 v80; // [rsp+108h] [rbp+0h] BYREF
  __int128 v81; // [rsp+110h] [rbp+8h]
  __int128 v82; // [rsp+120h] [rbp+18h]
  __int128 v83; // [rsp+130h] [rbp+28h]
  __int128 v84; // [rsp+140h] [rbp+38h]
  int v85; // [rsp+150h] [rbp+48h]
  __int64 v86; // [rsp+158h] [rbp+50h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+168h] [rbp+60h] BYREF
  __int16 *v88; // [rsp+178h] [rbp+70h]
  int v89; // [rsp+180h] [rbp+78h]
  int v90; // [rsp+184h] [rbp+7Ch]
  unsigned __int16 *v91; // [rsp+188h] [rbp+80h]
  int v92; // [rsp+190h] [rbp+88h]
  int v93; // [rsp+194h] [rbp+8Ch]
  __int64 *v94; // [rsp+198h] [rbp+90h]
  int v95; // [rsp+1A0h] [rbp+98h]
  int v96; // [rsp+1A4h] [rbp+9Ch]
  __int64 *v97; // [rsp+1A8h] [rbp+A0h]
  __int64 v98; // [rsp+1B0h] [rbp+A8h]
  bool *v99; // [rsp+1B8h] [rbp+B0h]
  __int64 v100; // [rsp+1C0h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  v85 = 0;
  v59[0] = 0;
  v60 = 0;
  v80 = 0;
  v86 = 0;
  v81 = 0;
  v65 = 0;
  v82 = 0;
  LODWORD(v66) = 0;
  v83 = 0;
  v67 = 0;
  v84 = 0;
  v68 = 0;
  *(_OWORD *)v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  *(_QWORD *)&EventDescriptor.Id = &v60;
  EventDescriptor.Keyword = 0;
  LOBYTE(v63) = 1;
  v8 = SRCacheManager_Open(0, &EventDescriptor.Keyword);
  if ( (_BYTE)v63 )
  {
    v9 = **(_QWORD **)&EventDescriptor.Id;
    **(_QWORD **)&EventDescriptor.Id = EventDescriptor.Keyword;
    if ( v9 )
      SRCacheManager_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v8,
      UserDataCount);
    v10 = 10;
    v11 = v8 | 0xC0000000;
    goto LABEL_42;
  }
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v15 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
            (struct StateRepository::Cache::Manager_NoThrow *)&v60,
            StringSid,
            v12,
            (unsigned __int64 *)&v80,
            v59);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v15,
        UserDataCount);
      if ( StringSid )
        LocalFree(StringSid);
      v10 = 20;
      v11 = v16 | 0xC0000000;
      goto LABEL_42;
    }
    if ( StringSid )
      LocalFree(StringSid);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v13);
    if ( StringSid )
      LocalFree(StringSid);
    if ( LastError < 0 )
    {
      v10 = 20;
      v11 = LastError | 0xC0000000;
      goto LABEL_42;
    }
  }
  if ( !v59[0] )
  {
    v10 = 30;
    v11 = -1073741724;
    goto LABEL_43;
  }
  v17 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v60,
          a2,
          &v68);
  if ( v17 < 0 )
  {
    v10 = 40;
    v11 = v17 | 0xC0000000;
    goto LABEL_42;
  }
  v18 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
          (StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v65,
          (struct StateRepository::Cache::Manager_NoThrow *)&v60,
          v68);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v18,
      UserDataCount);
    v10 = 50;
    v11 = v19 | 0xC0000000;
    goto LABEL_42;
  }
  v20 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v65, 4, v69, v59);
  if ( v20 < 0 )
  {
LABEL_39:
    v10 = 80;
    v28 = v20 | 0xC0000000;
    v29 = v20 < 0;
LABEL_40:
    v11 = 0;
    if ( v29 )
      v11 = v28;
LABEL_42:
    if ( v11 < 0 )
      goto LABEL_43;
    goto LABEL_78;
  }
  while ( 1 )
  {
    if ( !v59[0] )
    {
      v10 = 90;
      v11 = -1073741275;
      goto LABEL_43;
    }
    if ( (v71 & 0xFFFFFFDE) == 0 )
      break;
LABEL_38:
    LODWORD(v66) = v66 + 1;
    v20 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v65, 4, v69, v59);
    if ( v20 < 0 )
      goto LABEL_39;
  }
  v21 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
          (struct StateRepository::Cache::Manager_NoThrow *)&v60,
          v80,
          v69[0],
          v59);
  if ( v21 < 0 )
  {
    v10 = 60;
    v11 = v21 | 0xC0000000;
    goto LABEL_42;
  }
  if ( !v59[0] )
    goto LABEL_38;
  if ( !v69[0] )
  {
    v23 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      UserDataCount);
LABEL_57:
    v10 = 70;
    v28 = v23 | 0xC0000000;
    v29 = v23 < 0;
    goto LABEL_40;
  }
  v59[0] = 0;
  *(_QWORD *)&EventDescriptor.Id = 0;
  LODWORD(EventDescriptor.Keyword) = 0;
  v63 = 0;
  v22 = StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
          (StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *)&EventDescriptor,
          (struct StateRepository::Cache::Manager_NoThrow *)&v60,
          v69[0]);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v22,
      UserDataCount);
    v35 = 1123;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v23,
      UserDataCounta);
    v36 = *(_QWORD *)&EventDescriptor.Id;
    *(_QWORD *)&EventDescriptor.Id = 0;
    if ( v36 )
    {
      SRCacheContext_Close(v36);
      v10 = 70;
      v28 = v23 | 0xC0000000;
      v29 = v23 < 0;
      goto LABEL_40;
    }
    goto LABEL_57;
  }
  if ( !*(_QWORD *)&EventDescriptor.Id )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    goto LABEL_38;
  }
  *(_DWORD *)&v59[4] = 0;
  IsEmpty = SRCacheContext_IsEmpty(*(_QWORD *)&EventDescriptor.Id, &v59[4]);
  v23 = IsEmpty;
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      UserDataCount);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v23,
      UserDataCountb);
    v35 = 1129;
    goto LABEL_54;
  }
  v25 = *(_QWORD *)&EventDescriptor.Id;
  v26 = *(_DWORD *)&v59[4] == 0;
  *(_QWORD *)&EventDescriptor.Id = 0;
  v59[0] = *(_DWORD *)&v59[4] == 0;
  if ( v25 )
    SRCacheContext_Close(v25);
  if ( !v26 )
    goto LABEL_38;
  v27 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v65, 1, v69, v59);
  if ( v27 < 0 )
  {
    v10 = 100;
    v11 = v27 | 0xC0000000;
    goto LABEL_42;
  }
  if ( !v59[0] )
  {
    v10 = 110;
    v11 = -1073741275;
    goto LABEL_43;
  }
  v37 = *a3;
  v38 = (unsigned __int64)*a3 >> 1;
  if ( v38 )
  {
    v39 = (_WORD *)v69[1];
    v40 = 2147483646;
    v41 = (unsigned __int64)*a3 >> 1;
    v42 = a4;
    v43 = 0;
    do
    {
      if ( !v40 )
        break;
      if ( !*v39 )
        break;
      *v42++ = *v39++;
      --v40;
      ++v43;
      --v41;
    }
    while ( v41 );
    v44 = v43 - 1;
    v45 = v42 - 1;
    v11 = -2147483643;
    if ( v41 )
    {
      v45 = v42;
      v44 = v43;
      v11 = 0;
    }
    *v45 = 0;
    v46 = v38 - v44;
    if ( v41 )
    {
      v47 = (v37 & 1) + 2 * v46;
      if ( v47 > 2 )
        memset_0(&a4[v44 + 1], 0, v47 - 2);
    }
    if ( v11 >= 0 )
    {
      *a3 -= (v37 & 1) + 2 * v46;
      v11 = 0;
      goto LABEL_78;
    }
  }
  else
  {
    v11 = -1073741811;
  }
  v10 = 120;
LABEL_43:
  if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    *(_DWORD *)&v59[4] = v10;
    v99 = &v59[4];
    v30 = &BipTraceLoggingNullSid;
    LODWORD(v64) = v11;
    v100 = 4;
    if ( Sid )
      v30 = (__int64 *)Sid;
    v97 = &v64;
    v98 = 4;
    v31 = *((unsigned __int8 *)v30 + 1);
    v94 = v30;
    v96 = 0;
    v95 = 4 * v31 + 8;
    if ( a2 )
    {
      v32 = -1;
      while ( a2[++v32] != 0 )
        ;
      v34 = 2 * v32 + 2;
    }
    else
    {
      a2 = (unsigned __int16 *)&qword_1800A1670;
      v34 = 2;
    }
    v92 = v34;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v91 = a2;
    v93 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v88 = &word_1800AD806;
    UserData.Reserved = 2;
    v89 = 73;
    v90 = 1;
    LODWORD(StringSid) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
LABEL_78:
  v48 = v78;
  v78 = 0;
  if ( v48 )
    SRCache_Free(v48);
  v49 = *((_QWORD *)&v76 + 1);
  *((_QWORD *)&v76 + 1) = 0;
  if ( v49 )
    SRCache_Free(v49);
  v50 = v76;
  *(_QWORD *)&v76 = 0;
  if ( v50 )
    SRCache_Free(v50);
  v51 = v75;
  v75 = 0;
  if ( v51 )
    SRCache_Free(v51);
  v52 = v69[1];
  v69[1] = 0;
  if ( v52 )
    SRCache_Free(v52);
  v53 = v65;
  v65 = 0;
  if ( v53 )
    SRCacheContext_Close(v53);
  v54 = v60;
  v60 = 0;
  if ( v54 )
    SRCacheManager_Close(v54);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800526e0  mov     r11, rsp
0x1800526e3  push    rbp
0x1800526e4  push    rbx
0x1800526e5  lea     rbp, [r11-118h]
0x1800526ec  sub     rsp, 208h
0x1800526f3  mov     rax, cs:__security_cookie
0x1800526fa  xor     rax, rsp
0x1800526fd  mov     [rbp+110h+var_50], rax
0x180052704  xorps   xmm0, xmm0
0x180052707  mov     [r11-18h], rsi
0x18005270b  xor     esi, esi
0x18005270d  mov     [r11-28h], r12
0x180052711  xor     eax, eax
0x180052713  mov     [r11-30h], r13
0x180052717  mov     [r11-38h], r14
0x18005271b  mov     r13, rcx
0x18005271e  mov     [rbp+110h+var_C8], eax
0x180052721  mov     r14, rdx
0x180052724  mov     [rsp+210h+var_1E0], al
0x180052728  lea     rdx, [rsp+210h+EventDescriptor.Keyword]
0x18005272d  lea     rax, [rsp+210h+var_1D8]
0x180052732  mov     [r11-40h], r15
0x180052736  xor     ecx, ecx
0x180052738  mov     [rsp+210h+var_1D8], rsi
0x18005273d  mov     r12, r9
0x180052740  mov     [rbp+110h+var_110], rsi
0x180052744  mov     r15, r8
0x180052747  mov     [rbp+110h+var_C0], rsi
0x18005274b  movups  [rbp+110h+var_108], xmm0
0x18005274f  mov     [rsp+210h+var_1A8], rsi
0x180052754  movups  [rbp+110h+var_F8], xmm0
0x180052758  mov     dword ptr [rsp+210h+var_1A0], esi
0x18005275c  movups  [rbp+110h+var_E8], xmm0
0x180052760  mov     [rsp+210h+var_198], rsi
0x180052765  movups  [rbp+110h+var_D8], xmm0
0x180052769  mov     [rbp+110h+var_190], rsi
0x18005276d  movdqa  xmmword ptr [rbp+110h+var_180], xmm0
0x180052772  mov     [rbp+110h+var_170], rsi
0x180052776  mov     [rbp+110h+var_168], rsi
0x18005277a  mov     [rbp+110h+var_160], rsi
0x18005277e  mov     [rbp+110h+var_158], rsi
0x180052782  mov     [rbp+110h+var_150], rsi
0x180052786  mov     [rbp+110h+var_148], rsi
0x18005278a  movdqa  [rbp+110h+var_140], xmm0
0x18005278f  mov     [rbp+110h+var_130], esi
0x180052792  mov     [rbp+110h+var_128], rsi
0x180052796  mov     [rbp+110h+var_120], rsi
0x18005279a  mov     qword ptr [rsp+210h+EventDescriptor.Id], rax
0x18005279f  mov     [rsp+210h+EventDescriptor.Keyword], rsi
0x1800527a4  mov     byte ptr [rsp+210h+var_1B8], 1
0x1800527a9  call    cs:__imp_SRCacheManager_Open
0x1800527af  mov     ebx, eax
0x1800527b1  cmp     byte ptr [rsp+210h+var_1B8], sil
0x1800527b6  jz      short loc_1800527D3
0x1800527b8  mov     rdx, qword ptr [rsp+210h+EventDescriptor.Id]
0x1800527bd  mov     rax, [rsp+210h+EventDescriptor.Keyword]
0x1800527c2  mov     rcx, [rdx]
0x1800527c5  mov     [rdx], rax
0x1800527c8  test    rcx, rcx
0x1800527cb  jz      short loc_1800527D3
0x1800527cd  call    cs:__imp_SRCacheManager_Close
0x1800527d3  mov     [rsp+210h+var_18], rdi
0x1800527db  test    ebx, ebx
0x1800527dd  jns     short loc_18005280A
0x1800527df  mov     rcx, [rbp+118h]; this
0x1800527e6  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800527ed  mov     r9d, ebx; char *
0x1800527f0  mov     edx, 0A5h; void *
0x1800527f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800527fa  mov     ecx, 0Ah
0x1800527ff  or      ebx, 0C0000000h
0x180052805  jmp     loc_180052AA3
0x18005280a  lea     rdx, [rsp+210h+StringSid]; StringSid
0x18005280f  mov     [rsp+210h+StringSid], rsi
0x180052814  mov     rcx, r13; Sid
0x180052817  call    cs:__imp_ConvertSidToStringSidW
0x18005281d  test    eax, eax
0x18005281f  jnz     short loc_18005285F
0x180052821  mov     rcx, [rbp+118h]; this
0x180052828  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18005282f  mov     edx, 0DCh; void *
0x180052834  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052839  mov     rcx, [rsp+210h+StringSid]; hMem
0x18005283e  mov     ebx, eax
0x180052840  test    rcx, rcx
0x180052843  jz      short loc_18005284B
0x180052845  call    cs:__imp_LocalFree
0x18005284b  test    ebx, ebx
0x18005284d  jns     short loc_1800528CD
0x18005284f  mov     ecx, 14h
0x180052854  or      ebx, 0C0000000h
0x18005285a  jmp     loc_180052AA3
0x18005285f  mov     rdx, [rsp+210h+StringSid]
0x180052864  lea     rax, [rsp+210h+var_1E0]
0x180052869  lea     r9, [rbp+110h+var_110]
0x18005286d  mov     qword ptr [rsp+210h+UserDataCount], rax; int
0x180052872  lea     rcx, [rsp+210h+var_1D8]
0x180052877  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x18005287c  mov     ebx, eax
0x18005287e  test    eax, eax
0x180052880  jns     short loc_1800528BD
0x180052882  mov     rcx, [rbp+118h]; this
0x180052889  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052890  mov     r9d, eax; char *
0x180052893  mov     edx, 0DEh; void *
0x180052898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005289d  mov     rcx, [rsp+210h+StringSid]; hMem
0x1800528a2  test    rcx, rcx
0x1800528a5  jz      short loc_1800528AD
0x1800528a7  call    cs:__imp_LocalFree
0x1800528ad  mov     ecx, 14h
0x1800528b2  or      ebx, 0C0000000h
0x1800528b8  jmp     loc_180052AA3
0x1800528bd  mov     rcx, [rsp+210h+StringSid]; hMem
0x1800528c2  test    rcx, rcx
0x1800528c5  jz      short loc_1800528CD
0x1800528c7  call    cs:__imp_LocalFree
0x1800528cd  cmp     [rsp+210h+var_1E0], sil
0x1800528d2  jnz     short loc_1800528E3
0x1800528d4  mov     ecx, 1Eh
0x1800528d9  mov     ebx, 0C0000064h
0x1800528de  jmp     loc_180052AAB
0x1800528e3  lea     r8, [rbp+110h+var_190]; __int64 *
0x1800528e7  mov     rdx, r14; unsigned __int16 *
0x1800528ea  lea     rcx, [rsp+210h+var_1D8]; struct StateRepository::Cache::Manager_NoThrow *
0x1800528ef  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800528f4  mov     ebx, eax
0x1800528f6  test    eax, eax
0x1800528f8  jns     short loc_18005290A
0x1800528fa  mov     ecx, 28h ; '('
0x1800528ff  or      ebx, 0C0000000h
0x180052905  jmp     loc_180052AA3
0x18005290a  mov     r8, [rbp+110h+var_190]; __int64
0x18005290e  lea     rdx, [rsp+210h+var_1D8]; struct StateRepository::Cache::Manager_NoThrow *
0x180052913  lea     rcx, [rsp+210h+var_1A8]; this
0x180052918  call    ?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18005291d  mov     ebx, eax
0x18005291f  test    eax, eax
0x180052921  jns     short loc_18005294E
0x180052923  mov     rcx, [rbp+118h]; this
0x18005292a  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052931  mov     r9d, eax; char *
0x180052934  mov     edx, 81Fh; void *
0x180052939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005293e  mov     ecx, 32h ; '2'
0x180052943  or      ebx, 0C0000000h
0x180052949  jmp     loc_180052AA3
0x18005294e  lea     r9, [rsp+210h+var_1E0]
0x180052953  mov     edx, 4
0x180052958  lea     r8, [rbp+110h+var_180]
0x18005295c  lea     rcx, [rsp+210h+var_1A8]
0x180052961  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180052966  mov     edx, eax
0x180052968  test    eax, eax
0x18005296a  js      loc_180052A90
0x180052970  movzx   ebx, [rsp+210h+var_1E0]
0x180052975  test    bl, bl
0x180052977  jz      loc_180052C48
0x18005297d  test    dword ptr [rbp+110h+var_168], 0FFFFFFDEh
0x180052984  jnz     loc_180052A6A
0x18005298a  mov     r8, [rbp+110h+var_180]; __int64
0x18005298e  lea     r9, [rsp+210h+var_1E0]; bool *
0x180052993  mov     rdx, [rbp+110h+var_110]; __int64
0x180052997  lea     rcx, [rsp+210h+var_1D8]; struct StateRepository::Cache::Manager_NoThrow *
0x18005299c  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x1800529a1  mov     ebx, eax
0x1800529a3  test    eax, eax
0x1800529a5  js      loc_180052C38
0x1800529ab  cmp     [rsp+210h+var_1E0], sil
0x1800529b0  jz      loc_180052A6A
0x1800529b6  mov     r8, [rbp+110h+var_180]; __int64
0x1800529ba  test    r8, r8
0x1800529bd  jz      loc_180052C05
0x1800529c3  lea     rdx, [rsp+210h+var_1D8]; struct StateRepository::Cache::Manager_NoThrow *
0x1800529c8  mov     [rsp+210h+var_1E0], sil
0x1800529cd  lea     rcx, [rsp+210h+EventDescriptor]; this
0x1800529d2  mov     qword ptr [rsp+210h+EventDescriptor.Id], rsi
0x1800529d7  mov     dword ptr [rsp+210h+EventDescriptor.Keyword], esi
0x1800529db  mov     [rsp+210h+var_1B8], rsi
0x1800529e0  call    ?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)
0x1800529e5  mov     edi, eax
0x1800529e7  test    eax, eax
0x1800529e9  js      loc_180052BA7
0x1800529ef  mov     rcx, qword ptr [rsp+210h+EventDescriptor.Id]
0x1800529f4  test    rcx, rcx
0x1800529f7  jz      short loc_180052A65
0x1800529f9  lea     rdx, [rsp+210h+var_1E0+4]
0x1800529fe  mov     dword ptr [rsp+210h+var_1E0+4], esi
0x180052a02  call    cs:__imp_SRCacheContext_IsEmpty
0x180052a08  mov     edi, eax
0x180052a0a  test    eax, eax
0x180052a0c  js      loc_180052B6A
0x180052a12  cmp     dword ptr [rsp+210h+var_1E0+4], esi
0x180052a16  mov     rcx, qword ptr [rsp+210h+EventDescriptor.Id]
0x180052a1b  setz    bl
0x180052a1e  mov     qword ptr [rsp+210h+EventDescriptor.Id], rsi
0x180052a23  mov     [rsp+210h+var_1E0], bl
0x180052a27  test    rcx, rcx
0x180052a2a  jz      short loc_180052A32
0x180052a2c  call    cs:__imp_SRCacheContext_Close
0x180052a32  test    bl, bl
0x180052a34  jz      short loc_180052A6A
0x180052a36  lea     r9, [rsp+210h+var_1E0]
0x180052a3b  mov     edx, 1
0x180052a40  lea     r8, [rbp+110h+var_180]
0x180052a44  lea     rcx, [rsp+210h+var_1A8]
0x180052a49  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180052a4e  mov     ebx, eax
0x180052a50  test    eax, eax
0x180052a52  jns     loc_180052C57
0x180052a58  mov     ecx, 64h ; 'd'
0x180052a5d  or      ebx, 0C0000000h
0x180052a63  jmp     short loc_180052AA3
0x180052a65  mov     qword ptr [rsp+210h+EventDescriptor.Id], rsi
0x180052a6a  inc     dword ptr [rsp+210h+var_1A0]
0x180052a6e  lea     r9, [rsp+210h+var_1E0]
0x180052a73  lea     r8, [rbp+110h+var_180]
0x180052a77  mov     edx, 4
0x180052a7c  lea     rcx, [rsp+210h+var_1A8]
0x180052a81  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180052a86  mov     edx, eax
0x180052a88  test    eax, eax
0x180052a8a  jns     loc_180052970
0x180052a90  mov     eax, edx
0x180052a92  mov     ecx, 50h ; 'P'
0x180052a97  or      eax, 0C0000000h
0x180052a9c  test    edx, edx
0x180052a9e  mov     ebx, esi
0x180052aa0  cmovs   ebx, eax
0x180052aa3  test    ebx, ebx
0x180052aa5  jns     loc_180052DE7
0x180052aab  mov     eax, cs:dword_1800C3098
0x180052ab1  cmp     eax, 2
0x180052ab4  jbe     loc_180052DE7
0x180052aba  mov     rdx, cs:qword_1800C30B0
0x180052ac1  mov     rax, cs:qword_1800C30A8
0x180052ac8  test    al, 3
0x180052aca  jz      loc_180052DE7
0x180052ad0  mov     rax, rdx
0x180052ad3  and     eax, 3
0x180052ad6  cmp     rax, rdx
0x180052ad9  jnz     loc_180052DE7
0x180052adf  mov     dword ptr [rsp+210h+var_1E0+4], ecx
0x180052ae3  lea     rax, [rsp+210h+var_1E0+4]
0x180052ae8  mov     [rbp+110h+var_60], rax
0x180052aef  lea     rcx, BipTraceLoggingNullSid
0x180052af6  test    r13, r13
0x180052af9  mov     dword ptr [rsp+210h+var_1B0], ebx
0x180052afd  lea     rax, [rsp+210h+var_1B0]
0x180052b02  mov     [rbp+110h+var_58], 4
0x180052b0d  cmovnz  rcx, r13
0x180052b11  mov     [rbp+110h+var_70], rax
0x180052b18  mov     [rbp+110h+var_68], 4
0x180052b23  movzx   eax, byte ptr [rcx+1]
0x180052b27  mov     [rbp+110h+var_80], rcx
0x180052b2e  mov     [rbp+110h+var_74], esi
0x180052b34  lea     eax, ds:8[rax*4]
0x180052b3b  mov     [rbp+110h+var_78], eax
0x180052b41  test    r14, r14
0x180052b44  jz      loc_180052D3A
0x180052b4a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180052b51  cmp     word ptr [r14+rax*2+2], 0
0x180052b58  lea     rax, [rax+1]
0x180052b5c  jnz     short loc_180052B51
0x180052b5e  lea     eax, ds:2[rax*2]
0x180052b65  jmp     loc_180052D46
0x180052b6a  mov     rcx, [rbp+118h]; this
0x180052b71  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b78  mov     r9d, edi; char *
0x180052b7b  mov     edx, 2B8h; void *
0x180052b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b85  mov     rcx, [rbp+118h]; this
0x180052b8c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052b93  mov     r9d, edi; char *
0x180052b96  mov     edx, 41Eh; void *
0x180052b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ba0  mov     edx, 469h
0x180052ba5  jmp     short loc_180052BC7
0x180052ba7  mov     rcx, [rbp+118h]; this
0x180052bae  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052bb5  mov     r9d, edi; char *
0x180052bb8  mov     edx, 47Bh; void *
0x180052bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bc2  mov     edx, 463h; void *
0x180052bc7  mov     rcx, [rbp+118h]; this
0x180052bce  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180052bd5  mov     r9d, edi; char *
0x180052bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052bdd  mov     rcx, qword ptr [rsp+210h+EventDescriptor.Id]
0x180052be2  mov     qword ptr [rsp+210h+EventDescriptor.Id], rsi
0x180052be7  test    rcx, rcx
0x180052bea  jz      short loc_180052C25
0x180052bec  call    cs:__imp_SRCacheContext_Close
0x180052bf2  mov     eax, edi
0x180052bf4  mov     ecx, 46h ; 'F'
0x180052bf9  or      eax, 0C0000000h
0x180052bfe  test    edi, edi
0x180052c00  jmp     loc_180052A9E
0x180052c05  mov     rcx, [rbp+118h]; this
0x180052c0c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
  ... truncated ...
```
