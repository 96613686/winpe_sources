# StartList::LoadSettings(void)

- ea: `0x14000ee8c`
- end: `0x14000f5d3`
- name: `?LoadSettings@StartList@@AEAAJXZ`
- size: `1863`
- prototype: `__int64 __fastcall(StartList *__hidden this)`
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b250`
- `0x14000cfd0`
- `0x14000f810`
- `0x140010244`
- `0x140010714`

## callees

- `0x140006a78`
- `0x140007708`
- `0x14000ab98`
- `0x14000c19c`
- `0x14000cb50`
- `0x14000d118`
- `0x14000d1b8`
- `0x14000d3a0`
- `0x14000df88`
- `0x14000e0c0`
- `0x14000e1dc`
- `0x14000e3e8`
- `0x14000e538`
- `0x14000ee8c`
- `0x1400111c0`
- `0x140015ac2`
- `0x140015b00`
- `0x140015b90`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000f471`
- `ADVAPI32!RegOpenKeyExW` at `0x14000f471`
- `ADVAPI32!RegCloseKey` at `0x14000ef8f`
- `ADVAPI32!RegCloseKey` at `0x14000f13c`
- `ADVAPI32!RegCloseKey` at `0x14000f19d`
- `ADVAPI32!RegCloseKey` at `0x14000f1f4`
- `ADVAPI32!RegCloseKey` at `0x14000f258`
- `ADVAPI32!RegCloseKey` at `0x14000f2b9`
- `ADVAPI32!RegCloseKey` at `0x14000f315`
- `ADVAPI32!RegCloseKey` at `0x14000f3a9`
- `ADVAPI32!RegCloseKey` at `0x14000f4d8`
- `ADVAPI32!RegCloseKey` at `0x14000f5a8`
- `ADVAPI32!RegCloseKey` at `0x14000ef8f`
- `ADVAPI32!RegCloseKey` at `0x14000f13c`
- `ADVAPI32!RegCloseKey` at `0x14000f19d`
- `ADVAPI32!RegCloseKey` at `0x14000f1f4`
- `ADVAPI32!RegCloseKey` at `0x14000f258`
- `ADVAPI32!RegCloseKey` at `0x14000f2b9`
- `ADVAPI32!RegCloseKey` at `0x14000f315`
- `ADVAPI32!RegCloseKey` at `0x14000f3a9`
- `ADVAPI32!RegCloseKey` at `0x14000f4d8`
- `ADVAPI32!RegCloseKey` at `0x14000f5a8`
- `KERNEL32!CloseHandle` at `0x14000f433`
- `KERNEL32!CloseHandle` at `0x14000f433`
- `KERNEL32!OpenMutexW` at `0x14000f421`
- `KERNEL32!OpenMutexW` at `0x14000f421`
- `KERNEL32!OOBEComplete` at `0x14000eee6`
- `KERNEL32!OOBEComplete` at `0x14000eee6`
- `KERNEL32!RegSetValueExW` at `0x14000f36b`
- `KERNEL32!RegSetValueExW` at `0x14000f36b`

## string_xrefs

- `0x14000f496`: `Configuration`
- `0x14000f35f`: `SecureConfiguration`
- `0x14000f463`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
__int64 __fastcall StartList::LoadSettings(StartList *this)
{
  StartList *v2; // rcx
  unsigned int v3; // r8d
  _QWORD *v4; // rdx
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned int v9; // r8d
  StartList *v10; // rcx
  unsigned int v11; // r8d
  int UserValue; // eax
  unsigned int v13; // esi
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  HKEY v16; // rdx
  int v18; // edi
  _QWORD *v19; // rdx
  HKEY v20; // rdx
  _QWORD *v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v24; // r8
  _QWORD *v25; // rdx
  HKEY v26; // rdx
  HKEY v27; // rcx
  HANDLE v28; // rax
  StartList *v29; // rcx
  unsigned int v30; // r8d
  HKEY v31; // rdi
  __int64 v32; // r8
  __int64 v33; // r8
  _QWORD *v34; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37[2]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h]
  HKEY v43[3]; // [rsp+68h] [rbp-98h] BYREF
  HKEY v44[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v45[1024]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v46[1024]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v47[1024]; // [rsp+10A0h] [rbp+FA0h] BYREF

  if ( *((_DWORD *)this + 72) )
    return 0;
  *((_DWORD *)this + 72) = 1;
  v37[0] = 0;
  if ( (unsigned int)OOBEComplete(v37) && !v37[0] )
  {
    memset_0(v46, 0, sizeof(v46));
    hKey = 0;
    v41 = 0;
    v42 = 0;
    StartList::GetSettingConfigurationValue(v2, v46, v3, (struct ATL::CRegKey *)&hKey);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v39,
      v46);
    StartList::BuildConfigList(&v39, (char *)this + 144);
    v4 = (_QWORD *)(v39 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v39 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
    if ( hKey )
      RegCloseKey(hKey);
  }
  v5 = IsInteractiveUser();
  memset(v43, 0, sizeof(v43));
  v39 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  StartList::BuildSessionListStringBasedOnCurrentSessionContext(v6, v5, &v39, v43);
  StartList::BuildConfigList(&v39, (char *)this + 48);
  memset_0(v45, 0, sizeof(v45));
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v36 = v7;
  v8 = v39;
  if ( !v5 )
  {
    v28 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( !v28 )
    {
      StartList::GetSessionValue(v29, v45, v30, (struct ATL::CRegKey *)v43, 1);
      v33 = -1;
      do
        ++v33;
      while ( v45[v33] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v36, v45, v33);
      if ( *(_DWORD *)(v36 - 16) )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v36, L",");
      ATL::CSimpleStringT<unsigned short,0>::Append(&v36, v8);
      goto LABEL_79;
    }
    CloseHandle(v28);
    v31 = 0;
    hKey = 0;
    v41 = 0;
    v42 = 0;
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, StartList::_oobeAccessibilityKeyString, 0, 0x20019u, &phkResult) )
    {
      v31 = phkResult;
      hKey = phkResult;
      v37[0] = 1024;
      if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&hKey, L"Configuration", v45, v37) )
        v45[0] = 0;
    }
    v32 = -1;
    do
      ++v32;
    while ( v45[v32] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v36, v45, v32);
    if ( !v31 )
    {
LABEL_79:
      StartList::BuildConfigList(&v36, this);
      v34 = (_QWORD *)(v36 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v36 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 8LL))(*v34);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
      if ( v43[0] )
        RegCloseKey(v43[0]);
      return 0;
    }
    v27 = v31;
LABEL_73:
    RegCloseKey(v27);
    goto LABEL_79;
  }
  hKey = 0;
  v41 = 0;
  v42 = 0;
  memset_0(v46, 0, sizeof(v46));
  memset_0(v47, 0, sizeof(v47));
  StartList::GetTempValue(this, v46, v9, v47, lpData, (struct ATL::CRegKey *)&hKey);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    v46);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v37,
    v47);
  StartList::BuildConfigList(&phkResult, (char *)this + 192);
  StartList::BuildConfigList(v37, (char *)this + 240);
  memset(v44, 0, 24);
  UserValue = StartList::GetUserValue(v10, v45, v11, (struct ATL::CRegKey *)v44);
  v13 = UserValue;
  if ( UserValue >= 0 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v45[v22] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v36, v45, v22);
    goto LABEL_53;
  }
  v14 = UserValue & 0x1FFF0000;
  if ( (_DWORD)v14 == 458752 )
    UserValue = (unsigned __int16)UserValue;
  if ( UserValue != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v13);
    if ( v44[0] )
      RegCloseKey(v44[0]);
    v15 = (_QWORD *)(*(_QWORD *)v37 - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v37 - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
    v16 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
    if ( hKey )
      RegCloseKey(hKey);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v7 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 - 24) + 8LL))(*(_QWORD *)(v7 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
    if ( v43[0] )
      RegCloseKey(v43[0]);
    return v13;
  }
  v18 = StartList::HandleFirstTime(v14, (char *)this + 48, &v36, v44);
  if ( v18 >= 0 )
  {
LABEL_53:
    v23 = RegSetValueExW(v43[0], L"SecureConfiguration", 0, 1u, &Data, 2u);
    if ( v23 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v24, v23);
    if ( v44[0] )
      RegCloseKey(v44[0]);
    v25 = (_QWORD *)(*(_QWORD *)v37 - 24LL);
    if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v37 - 24LL + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
    v26 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
    v27 = hKey;
    if ( !hKey )
      goto LABEL_79;
    goto LABEL_73;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
      (unsigned int)v18);
  if ( v44[0] )
    RegCloseKey(v44[0]);
  v19 = (_QWORD *)(*(_QWORD *)v37 - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v37 - 24LL + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
  v20 = phkResult - 6;
  if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  if ( hKey )
    RegCloseKey(hKey);
  v21 = (_QWORD *)(v36 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v36 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
  if ( v43[0] )
    RegCloseKey(v43[0]);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14000ee8c  push    rbp
0x14000ee8e  push    rbx
0x14000ee8f  push    rsi
0x14000ee90  push    rdi
0x14000ee91  push    r12
0x14000ee93  push    r13
0x14000ee95  push    r14
0x14000ee97  push    r15
0x14000ee99  lea     rbp, [rsp-17B8h]
0x14000eea1  mov     eax, 18B8h
0x14000eea6  call    _alloca_probe
0x14000eeab  sub     rsp, rax
0x14000eeae  mov     rax, cs:__security_cookie
0x14000eeb5  xor     rax, rsp
0x14000eeb8  mov     [rbp+17F0h+var_50], rax
0x14000eebf  mov     r14, rcx
0x14000eec2  xor     r12d, r12d
0x14000eec5  cmp     [rcx+120h], r12d
0x14000eecc  jnz     loc_14000F5AE
0x14000eed2  mov     dword ptr [rcx+120h], 1
0x14000eedc  mov     [rsp+18F0h+var_18B8], r12d
0x14000eee1  lea     rcx, [rsp+18F0h+var_18B8]
0x14000eee6  call    cs:__imp_OOBEComplete
0x14000eeec  mov     ebx, 800h
0x14000eef1  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000eef5  test    eax, eax
0x14000eef7  jz      loc_14000EF95
0x14000eefd  cmp     [rsp+18F0h+var_18B8], r12d
0x14000ef02  jnz     loc_14000EF95
0x14000ef08  mov     r8d, ebx; Size
0x14000ef0b  xor     edx, edx; Val
0x14000ef0d  lea     rcx, [rbp+17F0h+var_1050]; void *
0x14000ef14  call    memset_0
0x14000ef19  mov     [rsp+18F0h+hKey], r12
0x14000ef1e  mov     [rsp+18F0h+var_1898], r12
0x14000ef23  mov     [rsp+18F0h+var_1890], r12
0x14000ef28  lea     r9, [rsp+18F0h+hKey]; struct ATL::CRegKey *
0x14000ef2d  lea     rdx, [rbp+17F0h+var_1050]; unsigned __int16 *
0x14000ef34  call    ?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)
0x14000ef39  lea     rdx, [rbp+17F0h+var_1050]
0x14000ef40  lea     rcx, [rsp+18F0h+var_18A8]
0x14000ef45  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000ef4a  nop
0x14000ef4b  lea     rdx, [r14+90h]
0x14000ef52  lea     rcx, [rsp+18F0h+var_18A8]
0x14000ef57  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14000ef5c  nop
0x14000ef5d  mov     rdx, [rsp+18F0h+var_18A8]
0x14000ef62  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ef66  mov     eax, r13d
0x14000ef69  lock xadd [rdx+10h], eax
0x14000ef6e  add     eax, r13d
0x14000ef71  test    eax, eax
0x14000ef73  jg      short loc_14000EF85
0x14000ef75  mov     rcx, [rdx]
0x14000ef78  mov     rax, [rcx]
0x14000ef7b  mov     rax, [rax+8]
0x14000ef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef84  nop
0x14000ef85  mov     rcx, [rsp+18F0h+hKey]; hKey
0x14000ef8a  test    rcx, rcx
0x14000ef8d  jz      short loc_14000EF95
0x14000ef8f  call    cs:__imp_RegCloseKey
0x14000ef95  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14000ef9a  mov     esi, eax
0x14000ef9c  mov     [rsp+18F0h+var_1888], r12
0x14000efa1  mov     [rsp+18F0h+var_1880], r12
0x14000efa6  mov     [rsp+18F0h+var_1878], r12
0x14000efab  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000efb2  mov     rax, [rcx+18h]
0x14000efb6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000efbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efc2  add     rax, 18h
0x14000efc6  mov     [rsp+18F0h+var_18A8], rax
0x14000efcb  lea     r9, [rsp+18F0h+var_1888]
0x14000efd0  lea     r8, [rsp+18F0h+var_18A8]
0x14000efd5  mov     edx, esi
0x14000efd7  call    ?BuildSessionListStringBasedOnCurrentSessionContext@StartList@@AEBAXHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCRegKey@3@@Z; StartList::BuildSessionListStringBasedOnCurrentSessionContext(int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x14000efdc  lea     rdx, [r14+30h]
0x14000efe0  lea     rcx, [rsp+18F0h+var_18A8]
0x14000efe5  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14000efea  mov     r8, rbx; Size
0x14000efed  xor     edx, edx; Val
0x14000efef  lea     rcx, [rbp+17F0h+var_1850]; void *
0x14000eff3  call    memset_0
0x14000eff8  nop
0x14000eff9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f000  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000f007  mov     rax, [rax+18h]
0x14000f00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f010  lea     rdi, [rax+18h]
0x14000f014  mov     [rsp+18F0h+var_18C0], rdi
0x14000f019  mov     rbx, [rsp+18F0h+var_18A8]
0x14000f01e  test    esi, esi
0x14000f020  jz      loc_14000F413
0x14000f026  mov     [rsp+18F0h+hKey], r12
0x14000f02b  mov     [rsp+18F0h+var_1898], r12
0x14000f030  mov     [rsp+18F0h+var_1890], r12
0x14000f035  mov     esi, 800h
0x14000f03a  mov     r8d, esi; Size
0x14000f03d  xor     edx, edx; Val
0x14000f03f  lea     rcx, [rbp+17F0h+var_1050]; void *
0x14000f046  call    memset_0
0x14000f04b  mov     r8d, esi; Size
0x14000f04e  xor     edx, edx; Val
0x14000f050  lea     rcx, [rbp+17F0h+var_850]; void *
0x14000f057  call    memset_0
0x14000f05c  lea     rax, [rsp+18F0h+hKey]
0x14000f061  mov     qword ptr [rsp+18F0h+cbData], rax; struct ATL::CRegKey *
0x14000f066  lea     r9, [rbp+17F0h+var_850]; unsigned __int16 *
0x14000f06d  lea     rdx, [rbp+17F0h+var_1050]; unsigned __int16 *
0x14000f074  mov     rcx, r14; this
0x14000f077  call    ?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z; StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)
0x14000f07c  lea     rdx, [rbp+17F0h+var_1050]
0x14000f083  lea     rcx, [rsp+18F0h+phkResult]
0x14000f088  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000f08d  nop
0x14000f08e  lea     rdx, [rbp+17F0h+var_850]
0x14000f095  lea     rcx, [rsp+18F0h+var_18B8]
0x14000f09a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000f09f  nop
0x14000f0a0  lea     rdx, [r14+0C0h]
0x14000f0a7  lea     rcx, [rsp+18F0h+phkResult]
0x14000f0ac  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14000f0b1  lea     rdx, [r14+0F0h]
0x14000f0b8  lea     rcx, [rsp+18F0h+var_18B8]
0x14000f0bd  call    ?BuildConfigList@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x14000f0c2  mov     [rbp+17F0h+var_1870], r12
0x14000f0c6  mov     [rbp+17F0h+var_1868], r12
0x14000f0ca  mov     [rbp+17F0h+var_1860], r12
0x14000f0ce  lea     r9, [rbp+17F0h+var_1870]; struct ATL::CRegKey *
0x14000f0d2  lea     rdx, [rbp+17F0h+var_1850]; unsigned __int16 *
0x14000f0d6  call    ?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z; StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)
0x14000f0db  mov     esi, eax
0x14000f0dd  test    eax, eax
0x14000f0df  jns     loc_14000F322
0x14000f0e5  mov     ecx, eax
0x14000f0e7  and     ecx, 1FFF0000h
0x14000f0ed  cmp     ecx, 70000h
0x14000f0f3  jnz     short loc_14000F0F8
0x14000f0f5  movzx   eax, si
0x14000f0f8  cmp     eax, 2
0x14000f0fb  jz      loc_14000F201
0x14000f101  lea     rax, WPP_GLOBAL_Control
0x14000f108  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f10f  cmp     rcx, rax
0x14000f112  jz      short loc_14000F133
0x14000f114  test    byte ptr [rcx+1Ch], 8
0x14000f118  jz      short loc_14000F133
0x14000f11a  mov     edx, 14h
0x14000f11f  mov     r9d, esi
0x14000f122  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000f129  mov     rcx, [rcx+10h]
0x14000f12d  call    WPP_SF_D
0x14000f132  nop
0x14000f133  mov     rcx, [rbp+17F0h+var_1870]; hKey
0x14000f137  test    rcx, rcx
0x14000f13a  jz      short loc_14000F143
0x14000f13c  call    cs:__imp_RegCloseKey
0x14000f142  nop
0x14000f143  mov     rdx, qword ptr [rsp+18F0h+var_18B8]
0x14000f148  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f14c  mov     eax, r13d
0x14000f14f  lock xadd [rdx+10h], eax
0x14000f154  add     eax, r13d
0x14000f157  test    eax, eax
0x14000f159  jg      short loc_14000F16B
0x14000f15b  mov     rcx, [rdx]
0x14000f15e  mov     rax, [rcx]
0x14000f161  mov     rax, [rax+8]
0x14000f165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f16a  nop
0x14000f16b  mov     rdx, [rsp+18F0h+phkResult]
0x14000f170  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f174  mov     eax, r13d
0x14000f177  lock xadd [rdx+10h], eax
0x14000f17c  add     eax, r13d
0x14000f17f  test    eax, eax
0x14000f181  jg      short loc_14000F193
0x14000f183  mov     rcx, [rdx]
0x14000f186  mov     rax, [rcx]
0x14000f189  mov     rax, [rax+8]
0x14000f18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f192  nop
0x14000f193  mov     rcx, [rsp+18F0h+hKey]; hKey
0x14000f198  test    rcx, rcx
0x14000f19b  jz      short loc_14000F1A4
0x14000f19d  call    cs:__imp_RegCloseKey
0x14000f1a3  nop
0x14000f1a4  lea     rdx, [rdi-18h]
0x14000f1a8  mov     eax, r13d
0x14000f1ab  lock xadd [rdx+10h], eax
0x14000f1b0  add     eax, r13d
0x14000f1b3  test    eax, eax
0x14000f1b5  jg      short loc_14000F1C7
0x14000f1b7  mov     rcx, [rdx]
0x14000f1ba  mov     rax, [rcx]
0x14000f1bd  mov     rax, [rax+8]
0x14000f1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1c6  nop
0x14000f1c7  lea     rdx, [rbx-18h]
0x14000f1cb  mov     eax, r13d
0x14000f1ce  lock xadd [rdx+10h], eax
0x14000f1d3  add     eax, r13d
0x14000f1d6  test    eax, eax
0x14000f1d8  jg      short loc_14000F1EA
0x14000f1da  mov     rcx, [rdx]
0x14000f1dd  mov     rax, [rcx]
0x14000f1e0  mov     rax, [rax+8]
0x14000f1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1e9  nop
0x14000f1ea  mov     rcx, [rsp+18F0h+var_1888]; hKey
0x14000f1ef  test    rcx, rcx
0x14000f1f2  jz      short loc_14000F1FA
0x14000f1f4  call    cs:__imp_RegCloseKey
0x14000f1fa  mov     eax, esi
0x14000f1fc  jmp     loc_14000F5B0
0x14000f201  lea     r9, [rbp+17F0h+var_1870]
0x14000f205  lea     r8, [rsp+18F0h+var_18C0]
0x14000f20a  lea     rdx, [r14+30h]
0x14000f20e  call    ?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z; StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)
0x14000f213  mov     edi, eax
0x14000f215  test    eax, eax
0x14000f217  jns     loc_14000F342
0x14000f21d  lea     rax, WPP_GLOBAL_Control
0x14000f224  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f22b  cmp     rcx, rax
0x14000f22e  jz      short loc_14000F24F
0x14000f230  test    byte ptr [rcx+1Ch], 8
0x14000f234  jz      short loc_14000F24F
0x14000f236  mov     edx, 15h
0x14000f23b  mov     r9d, edi
0x14000f23e  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14000f245  mov     rcx, [rcx+10h]
0x14000f249  call    WPP_SF_D
0x14000f24e  nop
0x14000f24f  mov     rcx, [rbp+17F0h+var_1870]; hKey
0x14000f253  test    rcx, rcx
0x14000f256  jz      short loc_14000F25F
0x14000f258  call    cs:__imp_RegCloseKey
0x14000f25e  nop
0x14000f25f  mov     rdx, qword ptr [rsp+18F0h+var_18B8]
0x14000f264  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f268  mov     eax, r13d
0x14000f26b  lock xadd [rdx+10h], eax
0x14000f270  add     eax, r13d
0x14000f273  test    eax, eax
0x14000f275  jg      short loc_14000F287
0x14000f277  mov     rcx, [rdx]
0x14000f27a  mov     rax, [rcx]
0x14000f27d  mov     rax, [rax+8]
0x14000f281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f286  nop
0x14000f287  mov     rdx, [rsp+18F0h+phkResult]
0x14000f28c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f290  mov     eax, r13d
0x14000f293  lock xadd [rdx+10h], eax
0x14000f298  add     eax, r13d
0x14000f29b  test    eax, eax
0x14000f29d  jg      short loc_14000F2AF
0x14000f29f  mov     rcx, [rdx]
0x14000f2a2  mov     rax, [rcx]
0x14000f2a5  mov     rax, [rax+8]
0x14000f2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2ae  nop
0x14000f2af  mov     rcx, [rsp+18F0h+hKey]; hKey
0x14000f2b4  test    rcx, rcx
0x14000f2b7  jz      short loc_14000F2C0
0x14000f2b9  call    cs:__imp_RegCloseKey
0x14000f2bf  nop
0x14000f2c0  mov     rdx, [rsp+18F0h+var_18C0]
0x14000f2c5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f2c9  mov     eax, r13d
0x14000f2cc  lock xadd [rdx+10h], eax
0x14000f2d1  add     eax, r13d
0x14000f2d4  test    eax, eax
0x14000f2d6  jg      short loc_14000F2E8
0x14000f2d8  mov     rcx, [rdx]
0x14000f2db  mov     rax, [rcx]
0x14000f2de  mov     rax, [rax+8]
0x14000f2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2e7  nop
0x14000f2e8  lea     rdx, [rbx-18h]
0x14000f2ec  mov     eax, r13d
0x14000f2ef  lock xadd [rdx+10h], eax
0x14000f2f4  add     eax, r13d
0x14000f2f7  test    eax, eax
0x14000f2f9  jg      short loc_14000F30B
0x14000f2fb  mov     rcx, [rdx]
0x14000f2fe  mov     rax, [rcx]
0x14000f301  mov     rax, [rax+8]
0x14000f305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f30a  nop
0x14000f30b  mov     rcx, [rsp+18F0h+var_1888]; hKey
0x14000f310  test    rcx, rcx
0x14000f313  jz      short loc_14000F31B
0x14000f315  call    cs:__imp_RegCloseKey
0x14000f31b  mov     eax, edi
0x14000f31d  jmp     loc_14000F5B0
0x14000f322  lea     rax, [rbp+17F0h+var_1850]
  ... truncated ...
```
