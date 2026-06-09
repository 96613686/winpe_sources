# OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary(Common::RegistryKey *,ushort const *,bool)

- ea: `0x18019c8d0`
- end: `0x18019cf01`
- name: `?RepairAclsOnKeyIfNecessary@RepairAclsOnRegistryTree@Internal@DEH@OSIntegration@@AEAAJPEAVRegistryKey@Common@@PEBG_N@Z`
- size: `1585`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::RepairAclsOnRegistryTree *__hidden this, struct Common::RegistryKey *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18019cf08`

## callees

- `0x1800040f0`
- `0x180067050`
- `0x180080b84`
- `0x180084290`
- `0x1800842cc`
- `0x180085594`
- `0x18008bafc`
- `0x18009aff4`
- `0x18009b028`
- `0x1800a6b30`
- `0x1800b10c0`
- `0x1800b1804`
- `0x1800c5988`
- `0x1800c9ec8`
- `0x1800f0260`
- `0x1800f0700`
- `0x18019b894`
- `0x18019ba48`
- `0x18019bb34`
- `0x18019bbe4`
- `0x18019bc08`
- `0x18019c628`
- `0x18019c668`
- `0x18019c8d0`
- `0x18019cfe8`
- `0x18019d0c4`
- `0x18019d0f4`
- `0x18019d43c`
- `0x18019df38`
- `0x18019e808`

## import_xrefs

- `ntdll!RtlGetAce` at `0x18019cc1b`
- `ntdll!RtlGetAce` at `0x18019cc1b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18019cad6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18019cad6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cb19`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cb30`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cc3e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cb19`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cb30`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18019cc3e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18019cbae`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18019cbae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18019cd45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18019cd45`

## string_xrefs

- `0x18019ca9a`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019cafa`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019cbd2`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019cd69`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019ce86`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019cae7`: `GetSecurityDescriptorOwner(securityDescriptor, &ownerSid, &ownerSidDefaulted)`
- `0x18019cbbf`: `GetSecurityDescriptorDacl(securityDescriptor, &daclPresent, &dacl, &daclDefaulted)`
- `0x18019ca87`: `rootKey->GetKeySecurity(DACL_SECURITY_INFORMATION | OWNER_SECURITY_INFORMATION, securityDescriptorBuffer)`
- `0x18019ca93`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019caf3`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019cbcb`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019cd62`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019cda2`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019ce7f`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary`
- `0x18019ce63`: `Failed to repair acls on key %ls`
- `0x18019ce73`: `RepairAclsOnKey(keyPath, isRootKey)`
- `0x18019cd96`: `RtlGetAce(dacl, aceIndex, (void**)&ace)`
- `0x18019cd56`: `ConvertSecurityDescriptorToStringSecurityDescriptor( securityDescriptor, SDDL_REVISION_1, DACL_SECURITY_INFORMATION | OWNER_SECURITY_INFORMATION, &securityDescriptorString, &securityDescriptorStringLength)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary(
        PSID *this,
        struct Common::RegistryKey *a2,
        unsigned __int16 *a3,
        char a4)
{
  char v4; // r15
  const unsigned __int16 *v5; // r14
  PSID *v7; // rsi
  char v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rax
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rax
  void *v13; // rcx
  int KeySecurity; // eax
  unsigned int LastError; // ebx
  bool v16; // bl
  char v17; // di
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  char v21; // r14
  char v22; // r15
  ULONG v23; // esi
  struct _ACL *v24; // rcx
  NTSTATUS v25; // eax
  unsigned int v26; // r8d
  _DWORD *v27; // rdi
  int v28; // eax
  __int64 v29; // rax
  LPWSTR v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  const struct _tlgProvider_t *v33; // rax
  int v34; // r8d
  int v35; // r9d
  int v36; // eax
  wil::details *v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+30h] [rbp-D0h]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR v45; // [rsp+68h] [rbp-98h] BYREF
  ULONG StringSecurityDescriptorLen[2]; // [rsp+70h] [rbp-90h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+7Ch] [rbp-84h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-80h] BYREF
  PSID pOwner; // [rsp+88h] [rbp-78h] BYREF
  PVOID Ace; // [rsp+90h] [rbp-70h] BYREF
  void **v52; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v53[3]; // [rsp+A8h] [rbp-58h] BYREF
  int v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  char v56; // [rsp+D0h] [rbp-30h]
  LPVOID pv; // [rsp+D8h] [rbp-28h] BYREF
  void **v58; // [rsp+E0h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+E8h] [rbp-18h] BYREF
  int v60; // [rsp+F0h] [rbp-10h]
  int v61; // [rsp+100h] [rbp+0h]
  volatile signed __int32 *v62; // [rsp+118h] [rbp+18h]
  _QWORD v63[4]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+188h] [rbp+88h]

  v4 = a4;
  v5 = a3;
  v45 = a3;
  v7 = this;
  *(_QWORD *)StringSecurityDescriptorLen = this;
  v8 = 0;
  v41 = 0;
  v9 = std::wstring::wstring(&v58, a3);
  v10 = tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(&v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(
    &pDacl,
    v10);
  std::wstring::operator=(&pDacl[34], v9);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&pDacl);
  std::wstring::_Tidy_deallocate(&v58);
  v52 = &tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::`vftable';
  v53[0] = 0;
  v53[1] = &v52;
  v53[2] = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,>(&pv);
  if ( v41 && (*(_QWORD *)(v41 + 248) || (*(_DWORD *)(v41 + 72) & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy>::reset(&v41);
  v11 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(&v41);
  tip2::details::shared_data<0,0,0>::start(*v11 + 8LL, v63);
  v58 = &tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)&pSecurityDescriptor,
    (struct wil::details::IFailureCallback *)&v58,
    0,
    1);
  v12 = (volatile signed __int32 *)v41;
  v62 = (volatile signed __int32 *)v41;
  if ( v41 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v41 + 344), 1u);
    v12 = v62;
  }
  v13 = pv;
  pv = (LPVOID)v12;
  if ( v12 )
    _InterlockedAdd(v12 + 86, 1u);
  if ( v13 )
    tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>::Release(v13);
  if ( v61 )
  {
    if ( !v54 )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v53);
  }
  else if ( v54 )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v53);
  }
  tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&v58);
  pSecurityDescriptor = 0;
  LODWORD(v58) = 0;
  v60 = 0;
  KeySecurity = Common::RegistryKey::GetKeySecurity(a2, 5u, (struct Common::ByteBuffer *)&v58);
  LastError = KeySecurity;
  if ( KeySecurity < 0 )
  {
    LODWORD(v38) = KeySecurity;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
      "rootKey->GetKeySecurity(DACL_SECURITY_INFORMATION | OWNER_SECURITY_INFORMATION, securityDescriptorBuffer)",
      (const char *)v38,
      v39);
    goto LABEL_63;
  }
  v16 = 0;
  v17 = v4;
  if ( !v4 )
  {
    bOwnerDefaulted = 0;
    pOwner = 0;
    if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
    {
      LastError = wil::details::in1diag5::Return_GetLastError(
                    retaddr,
                    (void *)0x4F,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
                    "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
                    "GetSecurityDescriptorOwner(securityDescriptor, &ownerSid, &ownerSidDefaulted)",
                    (const char *)v38);
      goto LABEL_63;
    }
    if ( EqualSid(pOwner, *v7) )
      v17 = 1;
    else
      v16 = !EqualSid(pOwner, v7[1]);
  }
  v18 = tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(&v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(
    &v43,
    v18);
  v19 = v43;
  *(_BYTE *)(v43 + 337) = v16;
  *(_BYTE *)(v19 + 338) = v17;
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::close(&v43);
  if ( !v17 )
  {
    if ( v16 )
      goto LABEL_53;
    goto LABEL_62;
  }
  if ( v16 )
    goto LABEL_53;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v20 = wil::details::in1diag5::Return_GetLastError(
            retaddr,
            (void *)0x70,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
            "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
            "GetSecurityDescriptorDacl(securityDescriptor, &daclPresent, &dacl, &daclDefaulted)",
            (const char *)v38);
LABEL_30:
    LastError = v20;
    goto LABEL_31;
  }
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = pDacl;
  if ( !pDacl->AceCount )
    goto LABEL_50;
  do
  {
    Ace = 0;
    v25 = RtlGetAce(v24, v23, &Ace);
    if ( v25 < 0 )
    {
      LODWORD(v38) = v25;
      v20 = wil::details::in1diag5::Return_NtStatus(
              retaddr,
              (void *)0x77,
              v26,
              "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
              "RtlGetAce(dacl, aceIndex, (void**)&ace)",
              v38,
              v39);
      goto LABEL_30;
    }
    v27 = Ace;
    if ( !*(_BYTE *)Ace && EqualSid((char *)Ace + 8, **(PSID **)StringSecurityDescriptorLen) )
    {
      v28 = v27[1];
      if ( v28 == 983103 )
      {
        if ( (*((_BYTE *)Ace + 1) & 8) == 0 )
        {
          v8 = 1;
          goto LABEL_46;
        }
      }
      else if ( v28 == 131097 )
      {
        if ( (*((_BYTE *)Ace + 1) & 8) == 0 )
        {
          v22 = 1;
          goto LABEL_46;
        }
      }
      else if ( (*((_BYTE *)Ace + 1) & 8) == 0 )
      {
        goto LABEL_45;
      }
      if ( v28 != 0x10000000 && v28 != 0x80000000 )
LABEL_45:
        v21 = 1;
    }
LABEL_46:
    ++v23;
    v24 = pDacl;
  }
  while ( v23 < pDacl->AceCount );
  if ( v21 || v22 || !v8 )
LABEL_50:
    v16 = 1;
  v29 = tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(&v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(
    &StringSecurityDescriptor,
    v29);
  v30 = StringSecurityDescriptor;
  *((_BYTE *)StringSecurityDescriptor + 336) = v21;
  *((_BYTE *)v30 + 340) = v8;
  *((_BYTE *)v30 + 339) = v22;
  *((_BYTE *)v30 + 341) = v16;
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::close(&StringSecurityDescriptor);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&StringSecurityDescriptor);
  if ( !v16 )
    goto LABEL_62;
  v7 = *(PSID **)StringSecurityDescriptorLen;
  v5 = v45;
  v4 = a4;
LABEL_53:
  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSecurityDescriptor,
    0);
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
          pSecurityDescriptor,
          1u,
          5u,
          &StringSecurityDescriptor,
          StringSecurityDescriptorLen) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0xAB,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
                  "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
                  "ConvertSecurityDescriptorToStringSecurityDescriptor( securityDescriptor, SDDL_REVISION_1, DACL_SECURIT"
                  "Y_INFORMATION | OWNER_SECURITY_INFORMATION, &securityDescriptorString, &securityDescriptorStringLength)",
                  (const char *)v38);
    goto LABEL_55;
  }
  v31 = std::wstring::wstring(v63, StringSecurityDescriptor);
  v32 = tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(&v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(
    &v45,
    v32);
  std::wstring::operator=(v45 + 152, v31);
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&v45);
  std::wstring::_Tidy_deallocate(v63);
  v33 = AppXDEHTelemetry::Provider();
  if ( *(_DWORD *)v33 > 5u )
  {
    v45 = StringSecurityDescriptor;
    v63[0] = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v33,
      (unsigned int)&unk_1802B5F28,
      v34,
      v35,
      (__int64)v63,
      (__int64)&v45);
  }
  v36 = OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey(v7, v5, v4);
  LastError = v36;
  if ( v36 >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSecurityDescriptor);
LABEL_62:
    tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::complete(&v41);
    tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&v43);
    LastError = 0;
    goto LABEL_63;
  }
  LODWORD(v38) = v36;
  wil::details::in1diag5::Return_HrMsg(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
    "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKeyIfNecessary",
    "RepairAclsOnKey(keyPath, isRootKey)",
    (const char *)v38,
    (int)"Failed to repair acls on key %ls",
    (const char *)v5);
LABEL_55:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSecurityDescriptor);
LABEL_31:
  tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&v43);
LABEL_63:
  operator delete(pSecurityDescriptor, 1u);
  tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(&v52);
  wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy>(&v41);
  return LastError;
}

```

## disassembly

```asm
0x18019c8d0  push    rbp
0x18019c8d2  push    rbx
0x18019c8d3  push    rsi
0x18019c8d4  push    rdi
0x18019c8d5  push    r12
0x18019c8d7  push    r14
0x18019c8d9  push    r15
0x18019c8db  lea     rbp, [rsp-50h]
0x18019c8e0  sub     rsp, 150h
0x18019c8e7  mov     rax, cs:__security_cookie
0x18019c8ee  xor     rax, rsp
0x18019c8f1  mov     [rbp+80h+var_40], rax
0x18019c8f5  mov     r15b, r9b
0x18019c8f8  mov     [rsp+180h+var_140], r9b
0x18019c8fd  mov     r14, r8
0x18019c900  mov     [rsp+180h+var_118], r8
0x18019c905  mov     rdi, rdx
0x18019c908  mov     rsi, rcx
0x18019c90b  mov     qword ptr [rsp+180h+var_110], rcx
0x18019c910  xor     r12d, r12d
0x18019c913  mov     [rsp+180h+var_138], r12
0x18019c918  mov     rdx, r8
0x18019c91b  lea     rcx, [rbp+80h+var_A0]
0x18019c91f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019c924  mov     rbx, rax
0x18019c927  lea     rcx, [rsp+180h+var_138]
0x18019c92c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(void)
0x18019c931  mov     rdx, rax
0x18019c934  lea     rcx, [rsp+180h+pDacl]
0x18019c939  call    ??0?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy> const &)
0x18019c93e  mov     rcx, [rsp+180h+pDacl]
0x18019c943  add     rcx, 110h
0x18019c94a  mov     rdx, rbx
0x18019c94d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18019c952  lea     rcx, [rsp+180h+pDacl]
0x18019c957  call    ??1?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(void)
0x18019c95c  lea     rcx, [rbp+80h+var_A0]
0x18019c960  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019c965  lea     rbx, ??_7?$test_watcher@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::`vftable'
0x18019c96c  mov     [rbp+80h+var_E0], rbx
0x18019c970  mov     [rbp+80h+var_D8], r12
0x18019c974  lea     rax, [rbp+80h+var_E0]
0x18019c978  mov     [rbp+80h+var_D0], rax
0x18019c97c  mov     [rbp+80h+var_C8], r12
0x18019c980  mov     [rbp+80h+var_C0], r12d
0x18019c984  mov     [rbp+80h+var_B8], r12
0x18019c988  mov     [rbp+80h+var_B0], r12b
0x18019c98c  lea     rcx, [rbp+80h+pv]
0x18019c990  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,>(void)
0x18019c995  nop
0x18019c996  mov     rax, [rsp+180h+var_138]
0x18019c99b  test    rax, rax
0x18019c99e  jz      short loc_18019C9BC
0x18019c9a0  cmp     [rax+0F8h], r12
0x18019c9a7  jnz     short loc_18019C9B2
0x18019c9a9  test    dword ptr [rax+48h], 100h
0x18019c9b0  jz      short loc_18019C9BC
0x18019c9b2  lea     rcx, [rsp+180h+var_138]
0x18019c9b7  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy>::reset(void)
0x18019c9bc  lea     rcx, [rsp+180h+var_138]
0x18019c9c1  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(void)
0x18019c9c6  mov     rcx, [rax]
0x18019c9c9  add     rcx, 8
0x18019c9cd  lea     rdx, [rbp+80h+var_60]
0x18019c9d1  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18019c9d6  mov     [rbp+80h+var_A0], rbx
0x18019c9da  mov     ebx, 1
0x18019c9df  mov     r9b, bl; bool
0x18019c9e2  xor     r8d, r8d; struct wil::CallContextInfo *
0x18019c9e5  lea     rdx, [rbp+80h+var_A0]; struct wil::details::IFailureCallback *
0x18019c9e9  lea     rcx, [rbp+80h+pSecurityDescriptor]; this
0x18019c9ed  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18019c9f2  mov     rax, [rsp+180h+var_138]
0x18019c9f7  mov     [rbp+80h+var_68], rax
0x18019c9fb  test    rax, rax
0x18019c9fe  jz      short loc_18019CA0B
0x18019ca00  lock add [rax+158h], ebx
0x18019ca07  mov     rax, [rbp+80h+var_68]
0x18019ca0b  mov     rcx, [rbp+80h+pv]; pv
0x18019ca0f  mov     [rbp+80h+pv], rax
0x18019ca13  test    rax, rax
0x18019ca16  jz      short loc_18019CA1F
0x18019ca18  lock add [rax+158h], ebx
0x18019ca1f  test    rcx, rcx
0x18019ca22  jz      short loc_18019CA29
0x18019ca24  call    ?Release@?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>::Release(void)
0x18019ca29  cmp     [rbp+80h+var_80], r12d
0x18019ca2d  jz      short loc_18019CA40
0x18019ca2f  cmp     [rbp+80h+var_C0], r12d
0x18019ca33  jnz     short loc_18019CA50
0x18019ca35  lea     rcx, [rbp+80h+var_D8]; this
0x18019ca39  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18019ca3e  jmp     short loc_18019CA50
0x18019ca40  cmp     [rbp+80h+var_C0], r12d
0x18019ca44  jz      short loc_18019CA50
0x18019ca46  lea     rcx, [rbp+80h+var_D8]; this
0x18019ca4a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18019ca4f  nop
0x18019ca50  lea     rcx, [rbp+80h+var_A0]
0x18019ca54  call    ??1?$test_watcher@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_watcher<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(void)
0x18019ca59  mov     [rbp+80h+pSecurityDescriptor], r12
0x18019ca5d  mov     dword ptr [rbp+80h+var_A0], r12d
0x18019ca61  mov     [rbp+80h+var_90], r12d
0x18019ca65  lea     r8, [rbp+80h+var_A0]; struct Common::ByteBuffer *
0x18019ca69  mov     edx, 5; unsigned int
0x18019ca6e  mov     rcx, rdi; this
0x18019ca71  call    ?GetKeySecurity@RegistryKey@Common@@QEAAJKAEAVByteBuffer@2@@Z; Common::RegistryKey::GetKeySecurity(ulong,Common::ByteBuffer &)
0x18019ca76  mov     ebx, eax
0x18019ca78  test    eax, eax
0x18019ca7a  jns     short loc_18019CAB0
0x18019ca7c  mov     rcx, [rbp+88h]; this
0x18019ca83  mov     dword ptr [rsp+180h+var_158], eax; char *
0x18019ca87  lea     rax, aRootkeyGetkeys; "rootKey->GetKeySecurity(DACL_SECURITY_I"...
0x18019ca8e  mov     [rsp+180h+StringSecurityDescriptorLen], rax; char *
0x18019ca93  lea     r9, aOsintegrationD_448; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019ca9a  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019caa1  mov     edx, 42h ; 'B'; void *
0x18019caa6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019caab  jmp     loc_18019CEBE
0x18019cab0  movzx   ebx, r12b
0x18019cab4  mov     dil, r15b
0x18019cab7  test    r15b, r15b
0x18019caba  jnz     loc_18019CB40
0x18019cac0  mov     [rsp+180h+bOwnerDefaulted], r12d
0x18019cac5  mov     [rbp+80h+pOwner], r12
0x18019cac9  lea     r8, [rsp+180h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18019cace  lea     rdx, [rbp+80h+pOwner]; pOwner
0x18019cad2  mov     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18019cad6  call    cs:__imp_GetSecurityDescriptorOwner
0x18019cadc  test    eax, eax
0x18019cade  jnz     short loc_18019CB12
0x18019cae0  mov     rcx, [rbp+88h]; this
0x18019cae7  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptorOwner(securityDesc"...
0x18019caee  mov     [rsp+180h+StringSecurityDescriptorLen], rax; char *
0x18019caf3  lea     r9, aOsintegrationD_448; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019cafa  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019cb01  mov     edx, 4Fh ; 'O'; void *
0x18019cb06  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x18019cb0b  mov     ebx, eax
0x18019cb0d  jmp     loc_18019CEBE
0x18019cb12  mov     rdx, [rsi]; pSid2
0x18019cb15  mov     rcx, [rbp+80h+pOwner]; pSid1
0x18019cb19  call    cs:__imp_EqualSid
0x18019cb1f  test    eax, eax
0x18019cb21  jz      short loc_18019CB28
0x18019cb23  mov     dil, 1
0x18019cb26  jmp     short loc_18019CB40
0x18019cb28  mov     rdx, [rsi+8]; pSid2
0x18019cb2c  mov     rcx, [rbp+80h+pOwner]; pSid1
0x18019cb30  call    cs:__imp_EqualSid
0x18019cb36  test    eax, eax
0x18019cb38  mov     eax, 1
0x18019cb3d  cmovz   ebx, eax
0x18019cb40  lea     rcx, [rsp+180h+var_138]
0x18019cb45  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(void)
0x18019cb4a  mov     rdx, rax
0x18019cb4d  lea     rcx, [rsp+180h+var_128]
0x18019cb52  call    ??0?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy> const &)
0x18019cb57  nop
0x18019cb58  mov     rax, [rsp+180h+var_128]
0x18019cb5d  mov     [rax+151h], bl
0x18019cb63  mov     [rax+152h], dil
0x18019cb6a  lea     rcx, [rsp+180h+var_128]
0x18019cb6f  call    ?close@?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::close(void)
0x18019cb74  test    dil, dil
0x18019cb77  jnz     short loc_18019CB86
0x18019cb79  test    bl, bl
0x18019cb7b  jnz     loc_18019CD13
0x18019cb81  jmp     loc_18019CEA6
0x18019cb86  test    bl, bl
0x18019cb88  jnz     loc_18019CD13
0x18019cb8e  mov     [rsp+180h+pDacl], r12
0x18019cb93  mov     [rbp+80h+bDaclPresent], r12d
0x18019cb97  mov     [rsp+180h+bDaclDefaulted], r12d
0x18019cb9c  lea     r9, [rsp+180h+bDaclDefaulted]; lpbDaclDefaulted
0x18019cba1  lea     r8, [rsp+180h+pDacl]; pDacl
0x18019cba6  lea     rdx, [rbp+80h+bDaclPresent]; lpbDaclPresent
0x18019cbaa  mov     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x18019cbae  call    cs:__imp_GetSecurityDescriptorDacl
0x18019cbb4  test    eax, eax
0x18019cbb6  jnz     short loc_18019CBF4
0x18019cbb8  mov     rcx, [rbp+88h]; this
0x18019cbbf  lea     rax, aGetsecuritydes_1; "GetSecurityDescriptorDacl(securityDescr"...
0x18019cbc6  mov     [rsp+180h+StringSecurityDescriptorLen], rax; char *
0x18019cbcb  lea     r9, aOsintegrationD_448; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019cbd2  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019cbd9  mov     edx, 70h ; 'p'; void *
0x18019cbde  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x18019cbe3  mov     ebx, eax
0x18019cbe5  lea     rcx, [rsp+180h+var_128]
0x18019cbea  call    ??1?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(void)
0x18019cbef  jmp     loc_18019CEBE
0x18019cbf4  mov     r14b, r12b
0x18019cbf7  xor     r15b, r15b
0x18019cbfa  xor     esi, esi
0x18019cbfc  xor     eax, eax
0x18019cbfe  mov     rcx, [rsp+180h+pDacl]; Acl
0x18019cc03  cmp     ax, [rcx+4]
0x18019cc07  jnb     loc_18019CCAC
0x18019cc0d  mov     [rbp+80h+Ace], 0
0x18019cc15  lea     r8, [rbp+80h+Ace]; Ace
0x18019cc19  mov     edx, esi; AceIndex
0x18019cc1b  call    cs:__imp_RtlGetAce
0x18019cc21  test    eax, eax
0x18019cc23  js      loc_18019CD8B
0x18019cc29  mov     rdi, [rbp+80h+Ace]
0x18019cc2d  cmp     byte ptr [rdi], 0
0x18019cc30  jnz     short loc_18019CC8A
0x18019cc32  lea     rcx, [rdi+8]; pSid1
0x18019cc36  mov     rax, qword ptr [rsp+180h+var_110]
0x18019cc3b  mov     rdx, [rax]; pSid2
0x18019cc3e  call    cs:__imp_EqualSid
0x18019cc44  test    eax, eax
0x18019cc46  jz      short loc_18019CC8A
0x18019cc48  mov     eax, [rdi+4]
0x18019cc4b  mov     rcx, [rbp+80h+Ace]
0x18019cc4f  cmp     eax, 0F003Fh
0x18019cc54  jnz     short loc_18019CC61
0x18019cc56  test    byte ptr [rcx+1], 8
0x18019cc5a  jnz     short loc_18019CC79
0x18019cc5c  mov     r12b, 1
0x18019cc5f  jmp     short loc_18019CC8A
0x18019cc61  cmp     eax, 20019h
0x18019cc66  jnz     short loc_18019CC73
0x18019cc68  test    byte ptr [rcx+1], 8
0x18019cc6c  jnz     short loc_18019CC79
0x18019cc6e  mov     r15b, 1
0x18019cc71  jmp     short loc_18019CC8A
0x18019cc73  test    byte ptr [rcx+1], 8
0x18019cc77  jz      short loc_18019CC87
0x18019cc79  cmp     eax, 10000000h
0x18019cc7e  jz      short loc_18019CC8A
0x18019cc80  cmp     eax, 80000000h
0x18019cc85  jz      short loc_18019CC8A
0x18019cc87  mov     r14b, 1
0x18019cc8a  inc     esi
0x18019cc8c  mov     rcx, [rsp+180h+pDacl]
0x18019cc91  movzx   eax, word ptr [rcx+4]
0x18019cc95  cmp     esi, eax
0x18019cc97  jb      loc_18019CC0D
0x18019cc9d  test    r14b, r14b
0x18019cca0  jnz     short loc_18019CCAC
0x18019cca2  test    r15b, r15b
0x18019cca5  jnz     short loc_18019CCAC
0x18019cca7  test    r12b, r12b
0x18019ccaa  jnz     short loc_18019CCAE
0x18019ccac  mov     bl, 1
0x18019ccae  lea     rcx, [rsp+180h+var_138]
0x18019ccb3  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::ensure_data(void)
0x18019ccb8  mov     rdx, rax
0x18019ccbb  lea     rcx, [rsp+180h+StringSecurityDescriptor]
0x18019ccc0  call    ??0?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(wil::com_ptr_t<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>,wil::err_returncode_policy> const &)
0x18019ccc5  mov     rax, [rsp+180h+StringSecurityDescriptor]
0x18019ccca  mov     [rax+150h], r14b
0x18019ccd1  mov     [rax+154h], r12b
0x18019ccd8  mov     [rax+153h], r15b
0x18019ccdf  mov     [rax+155h], bl
0x18019cce5  lea     rcx, [rsp+180h+StringSecurityDescriptor]
0x18019ccea  call    ?close@?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::close(void)
0x18019ccef  lea     rcx, [rsp+180h+StringSecurityDescriptor]
0x18019ccf4  call    ??1?$test_data_control@V?$merged_data@U_tip_RepairAclOnRegistryKey@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>::~test_data_control<tip2::details::merged_data<_tip_RepairAclOnRegistryKey,_tip_RepairAclOnRegistryKey>>(void)
0x18019ccf9  xor     r12d, r12d
0x18019ccfc  test    bl, bl
0x18019ccfe  jz      loc_18019CEA6
0x18019cd04  mov     rsi, qword ptr [rsp+180h+var_110]
0x18019cd09  mov     r14, [rsp+180h+var_118]
0x18019cd0e  mov     r15b, [rsp+180h+var_140]
0x18019cd13  mov     [rsp+180h+StringSecurityDescriptor], r12
0x18019cd18  mov     [rsp+180h+var_110], r12d
0x18019cd1d  xor     edx, edx
0x18019cd1f  lea     rcx, [rsp+180h+StringSecurityDescriptor]
0x18019cd24  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18019cd29  lea     rax, [rsp+180h+var_110]
0x18019cd2e  mov     [rsp+180h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18019cd33  lea     r9, [rsp+180h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18019cd38  mov     edx, 1; RequestedStringSDRevision
0x18019cd3d  lea     r8d, [rdx+4]; SecurityInformation
0x18019cd41  mov     rcx, [rbp+80h+pSecurityDescriptor]; SecurityDescriptor
0x18019cd45  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18019cd4b  test    eax, eax
0x18019cd4d  jnz     short loc_18019CDB8
0x18019cd4f  mov     rcx, [rbp+88h]; this
0x18019cd56  lea     rax, aConvertsecurit; "ConvertSecurityDescriptorToStringSecuri"...
0x18019cd5d  mov     [rsp+180h+StringSecurityDescriptorLen], rax; char *
0x18019cd62  lea     r9, aOsintegrationD_448; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019cd69  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019cd70  mov     edx, 0ABh; void *
0x18019cd75  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x18019cd7a  mov     ebx, eax
0x18019cd7c  lea     rcx, [rsp+180h+StringSecurityDescriptor]
0x18019cd81  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18019cd86  jmp     loc_18019CBE5
0x18019cd8b  mov     rcx, [rbp+88h]; this
0x18019cd92  mov     dword ptr [rsp+180h+var_158], eax; wil::details *
0x18019cd96  lea     rax, aRtlgetaceDaclA; "RtlGetAce(dacl, aceIndex, (void**)&ace)"
0x18019cd9d  mov     [rsp+180h+StringSecurityDescriptorLen], rax; char *
0x18019cda2  lea     r9, aOsintegrationD_448; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019cda9  mov     edx, 77h ; 'w'; void *
0x18019cdae  call    ?Return_NtStatus@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Return_NtStatus(void *,uint,char const *,char const *,char const *,long)
0x18019cdb3  jmp     loc_18019CBE3
  ... truncated ...
```
