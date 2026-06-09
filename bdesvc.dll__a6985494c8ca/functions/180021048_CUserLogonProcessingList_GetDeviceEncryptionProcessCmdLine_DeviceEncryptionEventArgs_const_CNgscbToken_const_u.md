# CUserLogonProcessingList::GetDeviceEncryptionProcessCmdLine(DeviceEncryptionEventArgs const &,CNgscbToken const &,ushort * *)

- ea: `0x180021048`
- end: `0x180021bcc`
- name: `?GetDeviceEncryptionProcessCmdLine@CUserLogonProcessingList@@IEAAJAEBUDeviceEncryptionEventArgs@@AEBVCNgscbToken@@PEAPEAG@Z`
- size: `2948`
- prototype: `__int64 __fastcall(CUserLogonProcessingList *__hidden this, const struct DeviceEncryptionEventArgs *, const struct CNgscbToken *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000dd60`
- `0x18000f7e0`
- `0x18001d2a0`
- `0x180021048`
- `0x180021bd4`
- `0x180021c20`
- `0x180021d18`
- `0x180022a1c`
- `0x180024918`
- `0x18002a718`
- `0x18002a774`
- `0x18002ae7c`
- `0x18002b6ac`
- `0x18002cac4`
- `0x18002f5f4`
- `0x18002f65c`
- `0x18002fe8c`
- `0x18003062c`
- `0x180031aec`
- `0x180031c20`
- `0x18003293c`
- `0x1800329b8`
- `0x180034070`
- `0x180034440`
- `0x1800345ec`
- `0x180051fc4`
- `0x180052594`
- `0x180059158`
- `0x180071ea8`
- `0x180072908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002111f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002111f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002110f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002110f`

## string_xrefs

- `0x180021170`: `Impersonation.ImpersonateUser`
- `0x1800218fd`: `StringCchCopyW`

## pseudocode

```c
__int64 __fastcall CUserLogonProcessingList::GetDeviceEncryptionProcessCmdLine(
        CUserLogonProcessingList *this,
        const struct DeviceEncryptionEventArgs *a2,
        const struct CNgscbToken *a3,
        unsigned __int16 **a4)
{
  signed int LastError; // eax
  signed int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  unsigned int v11; // eax
  int v12; // r15d
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  PVOID *v17; // r10
  bool v18; // r13
  struct CNgscbToken *v19; // r15
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  const struct CNgscbToken *v23; // rdx
  FveSkyStatusCache *v24; // r15
  unsigned int v25; // eax
  unsigned int v26; // eax
  PVOID *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int SharedNo; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  const struct DeviceEncryptionEventArgs *v34; // r13
  const unsigned __int16 *v35; // rdx
  unsigned int RequiredProvisioningSteps; // eax
  PVOID *v37; // rcx
  char v38; // r15
  struct CNgscbToken *v39; // rdx
  unsigned __int64 v40; // rax
  unsigned __int16 *v41; // rax
  unsigned __int16 *v42; // r15
  const unsigned __int16 *v43; // r8
  unsigned int v44; // eax
  PVOID *v45; // rcx
  const struct std::nothrow_t *v46; // rdx
  const unsigned __int16 *v47; // rdx
  int v48; // eax
  unsigned __int16 **v49; // r9
  unsigned __int16 **v50; // r9
  __int64 result; // rax
  const char *v52; // [rsp+28h] [rbp-110h]
  const char *v53; // [rsp+20h] [rbp-118h]
  const char *v54; // [rsp+28h] [rbp-110h]
  bool v55; // [rsp+40h] [rbp-F8h] BYREF
  bool v56; // [rsp+41h] [rbp-F7h] BYREF
  bool v57; // [rsp+42h] [rbp-F6h] BYREF
  char v58; // [rsp+43h] [rbp-F5h] BYREF
  int v59; // [rsp+44h] [rbp-F4h] BYREF
  FveEasUtil *v60; // [rsp+48h] [rbp-F0h] BYREF
  struct CNgscbToken *v61; // [rsp+50h] [rbp-E8h] BYREF
  FveSkyStatusCache *v62[2]; // [rsp+58h] [rbp-E0h] BYREF
  FveCloudStatusCache *v63[2]; // [rsp+68h] [rbp-D0h] BYREF
  const struct DeviceEncryptionEventArgs *v64; // [rsp+78h] [rbp-C0h]
  unsigned __int16 **v65; // [rsp+80h] [rbp-B8h]
  int v66[8]; // [rsp+88h] [rbp-B0h] BYREF
  unsigned int v67; // [rsp+A8h] [rbp-90h] BYREF
  unsigned __int16 *Src[2]; // [rsp+B0h] [rbp-88h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-78h]
  unsigned __int16 *v70[3]; // [rsp+D0h] [rbp-68h] BYREF
  unsigned __int64 v71; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v65 = a4;
  v61 = a3;
  v64 = a2;
  *(_OWORD *)v62 = 0;
  *(_OWORD *)v63 = 0;
  v58 = 0;
  v60 = 0;
  v57 = 0;
  v56 = 0;
  v55 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  *(_OWORD *)Src = 0;
  si128 = 0;
  std::wstring::_Construct_empty(Src);
  v67 = 0;
  if ( ImpersonateLoggedOnUser(*(HANDLE *)a3) )
  {
    v7 = 0;
    v58 = 1;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      (unsigned int)v7);
  if ( v7 < 0 )
  {
    v8 = "Impersonation.ImpersonateUser";
    v9 = 2873;
LABEL_13:
    v10 = (unsigned int)v7;
LABEL_14:
    LODWORD(v53) = (_DWORD)v8;
LABEL_15:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v10,
      (int)v53,
      v54);
    goto LABEL_157;
  }
  v11 = FveDomain::CheckIsDeviceAzureJoined(0, &v57);
  v12 = v11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v11);
  if ( v12 < 0 )
  {
    v7 = v12;
    v8 = "CheckIsDeviceAzureJoined";
    v10 = (unsigned int)v12;
    v9 = 2875;
    goto LABEL_14;
  }
  v59 = v12 == 0;
  CScopedImpersonation::Revert((CScopedImpersonation *)&v58);
  v13 = CUserLogonProcessingList::CheckIsConnectedUser(this, v61, &v56);
  v7 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v13);
    if ( v7 < 0 )
      goto LABEL_157;
  }
  v14 = FveEasUtil::CheckDEBackupRecoveryPasswordToAAD(v57, v12 == 0, &v55);
  v7 = v14;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v14);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    v8 = "CheckDEBackupRecoveryPasswordToAAD";
    v9 = 2883;
    goto LABEL_13;
  }
  if ( v17 == &WPP_GLOBAL_Control || (*((_BYTE *)v17 + 28) & 8) == 0 )
  {
    v18 = v56;
  }
  else
  {
    v18 = v56;
    WPP_SF_DDDD(v17[2], v15, v16, v57, v59, v56, v55);
  }
  if ( v12 )
    goto LABEL_87;
  if ( !v55 )
  {
    if ( v18 )
    {
      v19 = v61;
      goto LABEL_39;
    }
LABEL_87:
    SharedNo = MakeSharedNoThrow<FveSkyStatusCache>(v62);
    v7 = SharedNo;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, SharedNo);
    if ( v7 < 0 )
    {
      v8 = "MakeSharedNoThrow";
      v9 = 2921;
      goto LABEL_13;
    }
    v32 = FveSkyStatusCache::SetCurrentUser(v62[0], v61);
    v7 = v32;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v32);
    if ( v7 < 0 )
    {
      v8 = "SetCurrentUser";
      v9 = 2923;
      goto LABEL_13;
    }
    v55 = 0;
    v59 = 2;
    v33 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveSkyStatusCache> &,enum ProvisionSingleBackupStatusCache,bool>(
            &v60,
            v62,
            &v59,
            &v55);
    v7 = v33;
    v27 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v33);
      v27 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 < 0 )
    {
      v8 = "MakeUniqueNoThrow6";
      v9 = 2928;
      goto LABEL_13;
    }
    if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
    {
      v28 = 209;
      goto LABEL_105;
    }
    goto LABEL_106;
  }
  v21 = MakeSharedNoThrow<FveCloudStatusCache>(v63);
  v7 = v21;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v21);
  if ( v7 < 0 )
  {
    v8 = "MakeSharedNoThrow1";
    v9 = 2892;
    goto LABEL_13;
  }
  v19 = v61;
  v22 = FveCloudStatusCache::SetCurrentUser(v63[0], v61);
  v7 = v22;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v22);
  if ( v7 < 0 )
  {
    v8 = "SetCurrentUser1";
    v9 = 2893;
    goto LABEL_13;
  }
LABEL_39:
  if ( v18 )
  {
    v20 = MakeSharedNoThrow<FveSkyStatusCache>(v62);
    v7 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v20);
    if ( v7 < 0 )
    {
      v8 = "MakeSharedNoThrow2";
      v9 = 2897;
      goto LABEL_13;
    }
    v23 = v19;
    v24 = v62[0];
    v25 = FveSkyStatusCache::SetCurrentUser(v62[0], v23);
    v7 = v25;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v25);
    if ( v7 < 0 )
    {
      v8 = "SetCurrentUser2";
      v9 = 2898;
      goto LABEL_13;
    }
  }
  else
  {
    v24 = v62[0];
  }
  v55 = 0;
  if ( v63[0] )
  {
    if ( v24 )
    {
      v26 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveCloudStatusCache> &,std::shared_ptr<FveSkyStatusCache> &,bool>(
              &v60,
              v63,
              v62,
              &v55);
      v7 = v26;
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v26);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
      {
        v8 = "MakeUniqueNoThrow3";
        v9 = 2905;
        goto LABEL_13;
      }
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
      {
        v28 = 201;
LABEL_105:
        WPP_SF_(v27[2], v28, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      }
    }
    else
    {
      v59 = 1;
      v29 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveSkyStatusCache> &,enum ProvisionSingleBackupStatusCache,bool>(
              &v60,
              v63,
              &v59,
              &v55);
      v7 = v29;
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v29);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
      {
        v8 = "MakeUniqueNoThrow4";
        v9 = 2911;
        goto LABEL_13;
      }
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
      {
        v28 = 203;
        goto LABEL_105;
      }
    }
  }
  else
  {
    v59 = 2;
    v30 = MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveSkyStatusCache> &,enum ProvisionSingleBackupStatusCache,bool>(
            &v60,
            v62,
            &v59,
            &v55);
    v7 = v30;
    v27 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v30);
      v27 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 < 0 )
    {
      v8 = "MakeUniqueNoThrow5";
      v9 = 2917;
      goto LABEL_13;
    }
    if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
    {
      v28 = 205;
      goto LABEL_105;
    }
  }
LABEL_106:
  v34 = v64;
  v35 = (const unsigned __int16 *)(*(_QWORD *)v64 + 40LL);
  if ( *(_QWORD *)(*(_QWORD *)v64 + 64LL) > 7u )
    v35 = *(const unsigned __int16 **)v35;
  RequiredProvisioningSteps = FveEasUtil::GetRequiredProvisioningSteps(v60, v35, (enum RequiredProvisioningSteps *)&v67);
  v7 = RequiredProvisioningSteps;
  v37 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      210,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      RequiredProvisioningSteps);
    v37 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    v53 = "GetRequiredProvisioningSteps";
    v10 = (unsigned int)v7;
    v9 = 2933;
    goto LABEL_15;
  }
  v38 = 0;
  if ( v67 )
  {
    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 8) != 0 )
      WPP_SF_d(v37[2], 211, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v67);
    v38 = 1;
  }
  std::wstring::_Assign<unsigned short>(Src, L"BitLockerDeviceEncryption.exe", 29);
  std::operator+<unsigned short>((int)v70);
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::~wstring(v70);
  v39 = (struct CNgscbToken *)***((_QWORD ***)v34 + 1);
  v61 = v39;
  while ( v39 != **((struct CNgscbToken ***)v64 + 1) )
  {
    std::wstring::wstring(v70, (char *)v39 + 32);
    v47 = (const unsigned __int16 *)v70;
    if ( v71 > 7 )
      v47 = v70[0];
    v48 = FveEasUtil::GetRequiredProvisioningSteps(v60, v47, (enum RequiredProvisioningSteps *)&v67);
    v7 = v48;
    if ( v48 >= 0 )
    {
      if ( v67 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v50 = v70;
          if ( v71 > 7 )
            LODWORD(v50) = v70[0];
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            214,
            (unsigned int)&WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
            (_DWORD)v50,
            v67);
        }
        try
        {
          std::operator+<unsigned short>((int)v66);
          std::wstring::_Append<unsigned short>(Src);
          std::wstring::~wstring(v66);
          v38 = 1;
        }
        catch ( ... )
        {
          v59 = -2147024882;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xBAA,
            (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
            (const char *)0x8007000ELL,
            (int)"Commandline2",
            v52);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              215,
              &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
              2147942414LL);
          std::wstring::~wstring(v70);
          v7 = v59;
LABEL_157:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              220,
              &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
              (unsigned int)v7);
LABEL_160:
          if ( si128.m128i_i64[1] > 7uLL )
            std::_Deallocate<16>(Src[0], 2 * si128.m128i_i64[1] + 2);
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Src[0]) = 0;
          if ( v60 )
            std::default_delete<FveEasUtil>::operator()();
          CScopedImpersonation::Revert((CScopedImpersonation *)&v58);
          if ( v63[1] )
            std::_Ref_count_base::_Decref(v63[1]);
          if ( v62[1] )
            std::_Ref_count_base::_Decref(v62[1]);
          result = (unsigned int)v7;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v49 = v70;
        if ( v71 > 7 )
          LODWORD(v49) = v70[0];
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          213,
          (unsigned int)&WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
          (_DWORD)v49,
          v48);
      }
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB9C,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v7,
        (int)"GetRequiredProvisioningSteps",
        v54);
      v7 = 0;
    }
    std::wstring::~wstring(v70);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++(&v61);
    v39 = v61;
  }
  if ( v38 )
  {
    v40 = 2 * (si128.m128i_i64[0] + 1);
    if ( !is_mul_ok(si128.m128i_i64[0] + 1, 2u) )
      v40 = -1;
    v41 = (unsigned __int16 *)operator new[](v40, (const struct std::nothrow_t *)&std::nothrow);
    v42 = v41;
    if ( !v41 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xBBB,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)0x8007000ELL,
        (int)"OutputCmdline",
        v54);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_160;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_157;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942414LL);
      goto LABEL_157;
    }
    v43 = (const unsigned __int16 *)Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v43 = Src[0];
    v44 = StringCchCopyW(v41, si128.m128i_i64[0] + 1, v43);
    v7 = v44;
    v45 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v44);
      v45 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xBC1,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v7,
        (int)"StringCchCopyW",
        v54);
      operator delete(v42, v46);
      goto LABEL_157;
    }
    if ( v45 != &WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 8) != 0 )
      WPP_SF_S(v45[2], 218, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v42);
  }
  else
  {
    v42 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  }
  *v65 = v42;
  goto LABEL_157;
}

```

## disassembly

```asm
0x180021048  push    rbx
0x18002104a  push    rsi
0x18002104b  push    rdi
0x18002104c  push    r12
0x18002104e  push    r13
0x180021050  push    r14
0x180021052  push    r15
0x180021054  sub     rsp, 100h
0x18002105b  mov     rax, cs:__security_cookie
0x180021062  xor     rax, rsp
0x180021065  mov     [rsp+138h+var_48], rax
0x18002106d  mov     [rsp+138h+var_B8], r9
0x180021075  mov     rbx, r8
0x180021078  mov     [rsp+138h+var_E8], rbx
0x18002107d  mov     [rsp+138h+var_C0], rdx
0x180021082  mov     r13, rcx
0x180021085  xorps   xmm0, xmm0
0x180021088  movdqu  xmmword ptr [rsp+138h+var_E0], xmm0
0x18002108e  movdqu  xmmword ptr [rsp+138h+var_D0], xmm0
0x180021094  xor     edi, edi
0x180021096  mov     [rsp+138h+var_F5], dil
0x18002109b  mov     [rsp+138h+var_F0], rdi
0x1800210a0  mov     [rsp+138h+var_F6], dil
0x1800210a5  mov     [rsp+138h+var_F7], dil
0x1800210aa  mov     [rsp+138h+var_F8], dil
0x1800210af  lea     r14, WPP_GLOBAL_Control
0x1800210b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210bd  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800210c4  cmp     rcx, r14
0x1800210c7  jz      short loc_1800210E0
0x1800210c9  test    byte ptr [rcx+1Ch], 20h
0x1800210cd  jz      short loc_1800210E0
0x1800210cf  mov     edx, 0BEh
0x1800210d4  mov     r8, rsi
0x1800210d7  mov     rcx, [rcx+10h]
0x1800210db  call    WPP_SF_
0x1800210e0  xorps   xmm0, xmm0
0x1800210e3  movups  xmmword ptr [rsp+138h+Src], xmm0
0x1800210eb  xorps   xmm1, xmm1
0x1800210ee  movdqu  [rsp+138h+var_78], xmm1
0x1800210f7  lea     rcx, [rsp+138h+Src]
0x1800210ff  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180021104  nop
0x180021105  mov     [rsp+138h+var_90], edi
0x18002110c  mov     rcx, [rbx]; hToken
0x18002110f  call    cs:__imp_ImpersonateLoggedOnUser
0x180021116  nop     dword ptr [rax+rax+00h]
0x18002111b  test    eax, eax
0x18002111d  jnz     short loc_18002113C
0x18002111f  call    cs:__imp_GetLastError
0x180021126  nop     dword ptr [rax+rax+00h]
0x18002112b  mov     ebx, eax
0x18002112d  test    eax, eax
0x18002112f  jle     short loc_180021143
0x180021131  movzx   ebx, ax
0x180021134  or      ebx, 80070000h
0x18002113a  jmp     short loc_180021143
0x18002113c  mov     ebx, edi
0x18002113e  mov     [rsp+138h+var_F5], 1
0x180021143  mov     rcx, cs:WPP_GLOBAL_Control
0x18002114a  mov     r12b, 40h ; '@'
0x18002114d  cmp     rcx, r14
0x180021150  jz      short loc_18002116C
0x180021152  test    [rcx+1Ch], r12b
0x180021156  jz      short loc_18002116C
0x180021158  mov     edx, 0BFh
0x18002115d  mov     r9d, ebx
0x180021160  mov     r8, rsi
0x180021163  mov     rcx, [rcx+10h]
0x180021167  call    WPP_SF_d
0x18002116c  test    ebx, ebx
0x18002116e  jns     short loc_18002119D
0x180021170  lea     rax, aImpersonationI; "Impersonation.ImpersonateUser"
0x180021177  mov     edx, 0B39h; void *
0x18002117c  mov     r9d, ebx; char *
0x18002117f  mov     qword ptr [rsp+138h+var_118], rax; int
0x180021184  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18002118b  mov     rcx, [rsp+138h]; this
0x180021193  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021198  jmp     loc_180021B09
0x18002119d  lea     rdx, [rsp+138h+var_F6]; bool *
0x1800211a2  xor     ecx, ecx; bool *
0x1800211a4  call    ?CheckIsDeviceAzureJoined@FveDomain@@SAJPEA_N0@Z; FveDomain::CheckIsDeviceAzureJoined(bool *,bool *)
0x1800211a9  mov     r15d, eax
0x1800211ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211b3  cmp     rcx, r14
0x1800211b6  jz      short loc_1800211D2
0x1800211b8  test    [rcx+1Ch], r12b
0x1800211bc  jz      short loc_1800211D2
0x1800211be  mov     edx, 0C0h
0x1800211c3  mov     r9d, eax
0x1800211c6  mov     r8, rsi
0x1800211c9  mov     rcx, [rcx+10h]
0x1800211cd  call    WPP_SF_d
0x1800211d2  test    r15d, r15d
0x1800211d5  jns     short loc_1800211EB
0x1800211d7  mov     ebx, r15d
0x1800211da  lea     rax, aCheckisdevicea; "CheckIsDeviceAzureJoined"
0x1800211e1  mov     r9d, r15d
0x1800211e4  mov     edx, 0B3Bh
0x1800211e9  jmp     short loc_18002117F
0x1800211eb  mov     eax, edi
0x1800211ed  test    r15d, r15d
0x1800211f0  setz    al
0x1800211f3  mov     [rsp+138h+var_F4], eax
0x1800211f7  lea     rcx, [rsp+138h+var_F5]; this
0x1800211fc  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x180021201  lea     r8, [rsp+138h+var_F7]; bool *
0x180021206  mov     rdx, [rsp+138h+var_E8]; struct CNgscbToken *
0x18002120b  mov     rcx, r13; this
0x18002120e  call    ?CheckIsConnectedUser@CUserLogonProcessingList@@IEBAJAEBVCNgscbToken@@PEA_N@Z; CUserLogonProcessingList::CheckIsConnectedUser(CNgscbToken const &,bool *)
0x180021213  mov     ebx, eax
0x180021215  test    eax, eax
0x180021217  jz      short loc_180021247
0x180021219  mov     rcx, cs:WPP_GLOBAL_Control
0x180021220  cmp     rcx, r14
0x180021223  jz      short loc_18002123F
0x180021225  test    [rcx+1Ch], r12b
0x180021229  jz      short loc_18002123F
0x18002122b  mov     edx, 0C1h
0x180021230  mov     r9d, eax
0x180021233  mov     r8, rsi
0x180021236  mov     rcx, [rcx+10h]
0x18002123a  call    WPP_SF_d
0x18002123f  test    ebx, ebx
0x180021241  js      loc_180021B09
0x180021247  test    r15d, r15d
0x18002124a  setz    dl; bool
0x18002124d  lea     r8, [rsp+138h+var_F8]; bool *
0x180021252  mov     cl, [rsp+138h+var_F6]; bool
0x180021256  call    ?CheckDEBackupRecoveryPasswordToAAD@FveEasUtil@@SAJ_N0PEA_N@Z; FveEasUtil::CheckDEBackupRecoveryPasswordToAAD(bool,bool,bool *)
0x18002125b  mov     ebx, eax
0x18002125d  mov     r10, cs:WPP_GLOBAL_Control
0x180021264  cmp     r10, r14
0x180021267  jz      short loc_18002128A
0x180021269  test    [r10+1Ch], r12b
0x18002126d  jz      short loc_18002128A
0x18002126f  mov     edx, 0C2h
0x180021274  mov     r9d, eax
0x180021277  mov     r8, rsi
0x18002127a  mov     rcx, [r10+10h]
0x18002127e  call    WPP_SF_d
0x180021283  mov     r10, cs:WPP_GLOBAL_Control
0x18002128a  test    ebx, ebx
0x18002128c  jns     short loc_18002129F
0x18002128e  lea     rax, aCheckdebackupr; "CheckDEBackupRecoveryPasswordToAAD"
0x180021295  mov     edx, 0B43h
0x18002129a  jmp     loc_18002117C
0x18002129f  cmp     r10, r14
0x1800212a2  jz      short loc_1800212D8
0x1800212a4  test    byte ptr [r10+1Ch], 8
0x1800212a9  jz      short loc_1800212D8
0x1800212ab  movzx   ecx, [rsp+138h+var_F8]
0x1800212b0  movzx   r13d, [rsp+138h+var_F7]
0x1800212b6  movzx   r9d, [rsp+138h+var_F6]
0x1800212bc  mov     [rsp+138h+var_108], ecx
0x1800212c0  mov     dword ptr [rsp+138h+var_110], r13d
0x1800212c5  mov     eax, [rsp+138h+var_F4]
0x1800212c9  mov     [rsp+138h+var_118], eax
0x1800212cd  mov     rcx, [r10+10h]
0x1800212d1  call    WPP_SF_DDDD
0x1800212d6  jmp     short loc_1800212DD
0x1800212d8  mov     r13b, [rsp+138h+var_F7]
0x1800212dd  test    r15d, r15d
0x1800212e0  jnz     loc_1800215B5
0x1800212e6  cmp     [rsp+138h+var_F8], dil
0x1800212eb  jnz     short loc_18002134F
0x1800212ed  test    r13b, r13b
0x1800212f0  jz      loc_1800215B5
0x1800212f6  mov     r15, [rsp+138h+var_E8]
0x1800212fb  test    r13b, r13b
0x1800212fe  jz      loc_180021436
0x180021304  lea     rcx, [rsp+138h+var_E0]
0x180021309  call    ??$MakeSharedNoThrow@VFveSkyStatusCache@@@@YAJAEAV?$shared_ptr@VFveSkyStatusCache@@@std@@@Z; MakeSharedNoThrow<FveSkyStatusCache>(std::shared_ptr<FveSkyStatusCache> &)
0x18002130e  mov     ebx, eax
0x180021310  mov     rcx, cs:WPP_GLOBAL_Control
0x180021317  cmp     rcx, r14
0x18002131a  jz      short loc_180021336
0x18002131c  test    [rcx+1Ch], r12b
0x180021320  jz      short loc_180021336
0x180021322  mov     edx, 0C6h
0x180021327  mov     r9d, eax
0x18002132a  mov     r8, rsi
0x18002132d  mov     rcx, [rcx+10h]
0x180021331  call    WPP_SF_d
0x180021336  test    ebx, ebx
0x180021338  jns     loc_1800213E9
0x18002133e  lea     rax, aMakesharednoth_0; "MakeSharedNoThrow2"
0x180021345  mov     edx, 0B51h
0x18002134a  jmp     loc_18002117C
0x18002134f  lea     rcx, [rsp+138h+var_D0]
0x180021354  call    ??$MakeSharedNoThrow@VFveCloudStatusCache@@@@YAJAEAV?$shared_ptr@VFveCloudStatusCache@@@std@@@Z; MakeSharedNoThrow<FveCloudStatusCache>(std::shared_ptr<FveCloudStatusCache> &)
0x180021359  mov     ebx, eax
0x18002135b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021362  cmp     rcx, r14
0x180021365  jz      short loc_180021381
0x180021367  test    [rcx+1Ch], r12b
0x18002136b  jz      short loc_180021381
0x18002136d  mov     edx, 0C4h
0x180021372  mov     r9d, eax
0x180021375  mov     r8, rsi
0x180021378  mov     rcx, [rcx+10h]
0x18002137c  call    WPP_SF_d
0x180021381  test    ebx, ebx
0x180021383  jns     short loc_180021396
0x180021385  lea     rax, aMakesharednoth_1; "MakeSharedNoThrow1"
0x18002138c  mov     edx, 0B4Ch
0x180021391  jmp     loc_18002117C
0x180021396  mov     r15, [rsp+138h+var_E8]
0x18002139b  mov     rdx, r15; struct CNgscbToken *
0x18002139e  mov     rcx, [rsp+138h+var_D0]; this
0x1800213a3  call    ?SetCurrentUser@FveCloudStatusCache@@QEAAJAEBVCNgscbToken@@@Z; FveCloudStatusCache::SetCurrentUser(CNgscbToken const &)
0x1800213a8  mov     ebx, eax
0x1800213aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213b1  cmp     rcx, r14
0x1800213b4  jz      short loc_1800213D0
0x1800213b6  test    [rcx+1Ch], r12b
0x1800213ba  jz      short loc_1800213D0
0x1800213bc  mov     edx, 0C5h
0x1800213c1  mov     r9d, eax
0x1800213c4  mov     r8, rsi
0x1800213c7  mov     rcx, [rcx+10h]
0x1800213cb  call    WPP_SF_d
0x1800213d0  test    ebx, ebx
0x1800213d2  jns     loc_1800212FB
0x1800213d8  lea     rax, aSetcurrentuser; "SetCurrentUser1"
0x1800213df  mov     edx, 0B4Dh
0x1800213e4  jmp     loc_18002117C
0x1800213e9  mov     rdx, r15; struct CNgscbToken *
0x1800213ec  mov     r15, [rsp+138h+var_E0]
0x1800213f1  mov     rcx, r15; this
0x1800213f4  call    ?SetCurrentUser@FveSkyStatusCache@@QEAAJAEBVCNgscbToken@@@Z; FveSkyStatusCache::SetCurrentUser(CNgscbToken const &)
0x1800213f9  mov     ebx, eax
0x1800213fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021402  cmp     rcx, r14
0x180021405  jz      short loc_180021421
0x180021407  test    [rcx+1Ch], r12b
0x18002140b  jz      short loc_180021421
0x18002140d  mov     edx, 0C7h
0x180021412  mov     r9d, eax
0x180021415  mov     r8, rsi
0x180021418  mov     rcx, [rcx+10h]
0x18002141c  call    WPP_SF_d
0x180021421  test    ebx, ebx
0x180021423  jns     short loc_18002143B
0x180021425  lea     rax, aSetcurrentuser_0; "SetCurrentUser2"
0x18002142c  mov     edx, 0B52h
0x180021431  jmp     loc_18002117C
0x180021436  mov     r15, [rsp+138h+var_E0]
0x18002143b  mov     [rsp+138h+var_F8], dil
0x180021440  lea     r9, [rsp+138h+var_F8]
0x180021445  lea     rcx, [rsp+138h+var_F0]
0x18002144a  cmp     [rsp+138h+var_D0], rdi
0x18002144f  jz      loc_18002153D
0x180021455  lea     rdx, [rsp+138h+var_D0]
0x18002145a  test    r15, r15
0x18002145d  jz      short loc_1800214CA
0x18002145f  lea     r8, [rsp+138h+var_E0]
0x180021464  call    ??$MakeUniqueNoThrow@VFveEasUtil@@AEAV?$shared_ptr@VFveCloudStatusCache@@@std@@AEAV?$shared_ptr@VFveSkyStatusCache@@@3@_N@@YAJAEAV?$unique_ptr@VFveEasUtil@@U?$default_delete@VFveEasUtil@@@std@@@std@@AEAV?$shared_ptr@VFveCloudStatusCache@@@1@AEAV?$shared_ptr@VFveSkyStatusCache@@@1@$$QEA_N@Z; MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveCloudStatusCache> &,std::shared_ptr<FveSkyStatusCache> &,bool>(std::unique_ptr<FveEasUtil> &,std::shared_ptr<FveCloudStatusCache> &,std::shared_ptr<FveSkyStatusCache> &,bool &&)
0x180021469  mov     ebx, eax
0x18002146b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021472  cmp     rcx, r14
0x180021475  jz      short loc_180021498
0x180021477  test    [rcx+1Ch], r12b
0x18002147b  jz      short loc_180021498
0x18002147d  mov     edx, 0C8h
0x180021482  mov     r9d, eax
0x180021485  mov     r8, rsi
0x180021488  mov     rcx, [rcx+10h]
0x18002148c  call    WPP_SF_d
0x180021491  mov     rcx, cs:WPP_GLOBAL_Control
0x180021498  test    ebx, ebx
0x18002149a  jns     short loc_1800214AD
0x18002149c  lea     rax, aMakeuniquenoth_0; "MakeUniqueNoThrow3"
0x1800214a3  mov     edx, 0B59h
0x1800214a8  jmp     loc_18002117C
0x1800214ad  cmp     rcx, r14
0x1800214b0  jz      loc_1800216CE
0x1800214b6  test    byte ptr [rcx+1Ch], 8
0x1800214ba  jz      loc_1800216CE
0x1800214c0  mov     edx, 0C9h
0x1800214c5  jmp     loc_1800216C2
0x1800214ca  mov     [rsp+138h+var_F4], 1
0x1800214d2  lea     r8, [rsp+138h+var_F4]
0x1800214d7  call    ??$MakeUniqueNoThrow@VFveEasUtil@@AEAV?$shared_ptr@VFveSkyStatusCache@@@std@@W4ProvisionSingleBackupStatusCache@@_N@@YAJAEAV?$unique_ptr@VFveEasUtil@@U?$default_delete@VFveEasUtil@@@std@@@std@@AEAV?$shared_ptr@VFveSkyStatusCache@@@1@$$QEAW4ProvisionSingleBackupStatusCache@@$$QEA_N@Z; MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<FveSkyStatusCache> &,ProvisionSingleBackupStatusCache,bool>(std::unique_ptr<FveEasUtil> &,std::shared_ptr<FveSkyStatusCache> &,ProvisionSingleBackupStatusCache &&,bool &&)
0x1800214dc  mov     ebx, eax
0x1800214de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214e5  cmp     rcx, r14
0x1800214e8  jz      short loc_18002150B
0x1800214ea  test    [rcx+1Ch], r12b
0x1800214ee  jz      short loc_18002150B
0x1800214f0  mov     edx, 0CAh
0x1800214f5  mov     r9d, eax
0x1800214f8  mov     r8, rsi
0x1800214fb  mov     rcx, [rcx+10h]
0x1800214ff  call    WPP_SF_d
0x180021504  mov     rcx, cs:WPP_GLOBAL_Control
0x18002150b  test    ebx, ebx
0x18002150d  jns     short loc_180021520
0x18002150f  lea     rax, aMakeuniquenoth_2; "MakeUniqueNoThrow4"
  ... truncated ...
```
