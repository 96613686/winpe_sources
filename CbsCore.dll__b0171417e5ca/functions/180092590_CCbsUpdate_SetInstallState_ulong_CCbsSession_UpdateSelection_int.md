# CCbsUpdate::SetInstallState(ulong,CCbsSession *,UpdateSelection,int)

- ea: `0x180092590`
- end: `0x180093502`
- name: `?SetInstallState@CCbsUpdate@@QEAAJKPEAVCCbsSession@@W4UpdateSelection@@H@Z`
- size: `3954`
- prototype: ``
- caller_count: `6`
- callee_count: `37`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180068de0`
- `0x18015ac58`
- `0x1801680f4`
- `0x1801a9cd8`
- `0x1801b1874`
- `0x1801bc584`

## callees

- `0x18000d910`
- `0x18000e780`
- `0x180010cc0`
- `0x1800138b8`
- `0x18001e1a0`
- `0x180022c78`
- `0x18002341c`
- `0x180023444`
- `0x18003f40c`
- `0x18004a1cc`
- `0x18004d564`
- `0x180092590`
- `0x180093a70`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a0988`
- `0x1800a5fe0`
- `0x1800ad504`
- `0x1800be2e0`
- `0x1800be858`
- `0x1800e9f30`
- `0x1800eb920`
- `0x1801433b8`
- `0x18014b4e4`
- `0x18015a428`
- `0x1801a33f0`
- `0x1801b23c8`
- `0x1801b2460`
- `0x1801b260c`
- `0x1801b28bc`
- `0x1801b40fc`
- `0x1801c2c30`
- `0x1801c8ac4`
- `0x1801d304c`

## string_xrefs

- `0x180092629`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x180092a9f`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x1800931da`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x18009335d`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x18009343a`: `onecore\base\cbs\core\cbsupdate.cpp`
- `0x1800927d0`: `Update: Setting Install State, Package: {}, Update: {}, new state: {}`
- `0x180092727`: `Attempt to change a finalized session`
- `0x180093477`: `Failed to decompress OC content.`
- `0x1800928ac`: `Windows Optional Component Manager`
- `0x180092bdc`: `Update: Setting SynchronousScavenge to ensure content is immediately removed for {}, package: {}`
- `0x180092c35`: `Failed to get per-session update state`
- `0x1800929b9`: `Update: Inferring removal for disable request by client '{}' for {}, package: {}`
- `0x180092a1e`: `Update: Failed to check if the payload is removable for Package: {}, Update: {}`
- `0x180092832`: `Cannot change state of Update because Update: {} is not selectable.`
- `0x180092ff9`: `Failed to add task for package: {}, update: {}`
- `0x180093219`: `Exec: NetFx3 OC and package already added to the execution, ignore the failure and just added the feature name`
- `0x1800930db`: `Update: State is unchanged, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}`
- `0x180092f61`: `Update: Setting Install State, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}`
- `0x180092cb8`: `Failed to get current selection state for package: {}, update: {}`
- `0x180092ea2`: `No write operations (enable/disable feature) are allowed on a container, states: {}, {}`

## pseudocode

```c
__int64 __fastcall CCbsUpdate::SetInstallState(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v6; // r13d
  unsigned int v8; // edi
  __int64 v9; // rdx
  const wchar_t *v11; // r14
  struct PerSessionUpdateState *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // edx
  bool v16; // zf
  struct PerSessionUpdateState *v17; // r14
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rax
  __int64 v20; // rax
  int v21; // r9d
  __int64 v22; // r10
  _WORD *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // xmm0_8
  __int64 v26; // rax
  __int64 v27; // xmm0_8
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // xmm0_8
  __int64 v31; // rax
  __int64 v32; // xmm0_8
  int v33; // edx
  const wchar_t *v34; // rax
  const wchar_t *v35; // rax
  int v36; // eax
  unsigned int v37; // r12d
  __int64 v38; // rax
  const wchar_t *v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  int v42; // ecx
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // xmm0_8
  __int64 v46; // rax
  __int64 v47; // xmm0_8
  const wchar_t *v48; // rax
  const wchar_t *v49; // rax
  int SessionUpdateState; // eax
  int CurrentSelectionState; // eax
  __int64 v52; // r9
  __int64 v53; // rax
  const wchar_t *v54; // rcx
  unsigned int v55; // ebx
  const wchar_t *v56; // rax
  __int64 v57; // rax
  struct PerSessionUpdateState *v58; // rax
  __int64 v59; // r12
  __int64 v60; // rcx
  __int64 v61; // r10
  int v62; // edx
  int v63; // r8d
  const wchar_t *v64; // rax
  struct PerSessionUpdateState *v65; // rcx
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rax
  const wchar_t *v69; // rcx
  __int64 v70; // rax
  int v71; // edx
  __int64 v72; // r8
  const wchar_t *v73; // rax
  __int64 v74; // rax
  unsigned int v75; // ecx
  __int64 *v76; // r13
  __int64 *v77; // rax
  __int64 v78; // r12
  CCbsCapabilityManager *v79; // rbx
  struct CCbsCapability **InitPointer; // rax
  int v81; // r12d
  const wchar_t *v82; // rdx
  int v83; // eax
  unsigned int v84; // ebx
  __int64 v85; // rdx
  const wchar_t *v86; // rcx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  const wchar_t *v91; // rcx
  struct PerSessionUpdateState *v92; // rax
  __int64 v93; // rax
  const wchar_t *v94; // rcx
  int v95; // eax
  unsigned int v96; // esi
  int v97; // eax
  __int64 v98; // rax
  const wchar_t *v99; // r8
  int v100; // [rsp+20h] [rbp-E0h]
  int v101[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v102; // [rsp+58h] [rbp-A8h]
  int v103[2]; // [rsp+60h] [rbp-A0h] BYREF
  int *v104; // [rsp+68h] [rbp-98h] BYREF
  struct PerSessionUpdateState *v105; // [rsp+70h] [rbp-90h] BYREF
  int v106[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v107; // [rsp+80h] [rbp-80h] BYREF
  __int64 v108; // [rsp+90h] [rbp-70h]
  _BYTE v109[24]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v110; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v111; // [rsp+C0h] [rbp-40h]
  _BYTE v112[24]; // [rsp+C8h] [rbp-38h] BYREF
  int v113[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v114; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v115; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v114 = a4;
  v6 = a2;
  if ( !a3 )
  {
    v8 = -2147024809;
    v113[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session specified");
      v105 = (struct PerSessionUpdateState *)v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v105);
    }
    v9 = 276;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
      (const char *)v8,
      v100);
    return v8;
  }
  if ( (_DWORD)a4 != 255 && (unsigned int)a4 > 1 && (_DWORD)a4 != 999 )
  {
    v8 = -2146498560;
    v113[0] = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      v11 = &qword_1802EB518;
      v12 = (struct PerSessionUpdateState *)&qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v12 = *(struct PerSessionUpdateState **)(a1 + 32);
      v105 = v12;
      v13 = *(_QWORD *)(a1 + 24);
      if ( *(_QWORD *)(v13 + 120) )
        v11 = *(const wchar_t **)(v13 + 120);
      v115 = v11;
      LogAdapter::Logger::LogNumObjects<enum UpdateSelection,wchar_t const *,wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        a2,
        a3,
        a4,
        (__int64)&v114,
        (__int64)&v115,
        (__int64)&v105);
      *(_QWORD *)v103 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v103);
    }
    v9 = 279;
    goto LABEL_5;
  }
  if ( a5 && (unsigned int)CCbsSession::IsLocked((CCbsSession *)a3) )
  {
    v8 = -2146498494;
    v113[0] = -2146498494;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Attempt to change a finalized session");
      *(_QWORD *)v103 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v103);
    }
    v9 = 281;
    goto LABEL_5;
  }
  LODWORD(v115) = -1;
  v105 = 0;
  v113[0] = 0;
  v14 = CbsSelectionToString((unsigned int)a4);
  v16 = *(_QWORD *)(a1 + 32) == 0;
  v17 = (struct PerSessionUpdateState *)&qword_1802EB518;
  v18 = &qword_1802EB518;
  *(_QWORD *)v103 = v14;
  v19 = &qword_1802EB518;
  if ( !v16 )
    v19 = *(const wchar_t **)(a1 + 32);
  v104 = (int *)v19;
  v20 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v20 + 120) )
    v18 = *(const wchar_t **)(v20 + 120);
  *(_QWORD *)v101 = v18;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v15) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v15,
      1,
      (unsigned int)"Update: Setting Install State, Package: {}, Update: {}, new state: {}",
      (__int64)v101,
      (__int64)&v104,
      (__int64)v103);
  }
  if ( !(unsigned int)CCbsUpdate::IsSelectable((CCbsUpdate *)a1) )
  {
    v8 = -2146498541;
    v113[0] = -2146498541;
    if ( v22 )
    {
      if ( *(_QWORD *)(a1 + 32) )
        v17 = *(struct PerSessionUpdateState **)(a1 + 32);
      *(_QWORD *)v101 = v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        v22,
        0,
        3,
        (__int64)"Cannot change state of Update because Update: {} is not selectable.",
        (__int64)v101);
      v104 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v104);
    }
    v9 = 296;
    goto LABEL_5;
  }
  if ( !v21 )
  {
    v23 = *(_WORD **)(a3 + 648);
    if ( v23 )
    {
      if ( *v23 )
      {
        v24 = Windows::StringUtil::AsLUnicode(v112);
        v25 = *(_QWORD *)(v24 + 16);
        v110 = *(_OWORD *)v24;
        v111 = v25;
        v26 = Windows::StringUtil::AsLUnicode(v109);
        v27 = *(_QWORD *)(v26 + 16);
        v107 = *(_OWORD *)v26;
        v108 = v27;
        if ( (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                &v107,
                                &v110) )
        {
          if ( (unsigned int)CCbsUpdate::GetDeploymentType(a1) != 5 )
          {
            v28 = *(_QWORD *)(a1 + 24);
            v29 = Windows::StringUtil::AsLUnicode(v109);
            v30 = *(_QWORD *)(v29 + 16);
            v107 = *(_OWORD *)v29;
            v108 = v30;
            if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(&v107) )
            {
              v31 = Windows::StringUtil::AsLUnicode(v109);
              v32 = *(_QWORD *)(v31 + 16);
              v107 = *(_OWORD *)v31;
              v108 = v32;
              if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(&v107) )
              {
                v34 = &qword_1802EB518;
                if ( *(_QWORD *)(v28 + 120) )
                  v34 = *(const wchar_t **)(v28 + 120);
                v16 = *(_QWORD *)(a1 + 32) == 0;
                *(_QWORD *)v101 = v34;
                v35 = &qword_1802EB518;
                if ( !v16 )
                  v35 = *(const wchar_t **)(a1 + 32);
                v104 = (int *)v35;
                *(_QWORD *)v103 = *(_QWORD *)(a3 + 648);
                if ( LogAdapter::g_Logger )
                {
                  LOBYTE(v33) = 1;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
                    (_DWORD)LogAdapter::g_Logger,
                    v33,
                    1,
                    (unsigned int)"Update: Inferring removal for disable request by client '{}' for {}, package: {}",
                    (__int64)v103,
                    (__int64)&v104,
                    (__int64)v101);
                }
                v6 |= 1u;
              }
            }
          }
        }
      }
    }
  }
  if ( (v6 & 1) != 0 )
  {
    v102 = 0;
    v36 = IsSelectablePayloadRemovable((CCbsSession *)a3, (CCbsUpdate *)a1);
    v37 = v36;
    if ( v36 < 0 )
    {
      v113[0] = v36;
      if ( LogAdapter::g_Logger )
      {
        v38 = *(_QWORD *)(a1 + 24);
        v39 = &qword_1802EB518;
        if ( *(_QWORD *)(a1 + 32) )
          v39 = *(const wchar_t **)(a1 + 32);
        *(_QWORD *)v101 = v39;
        if ( *(_QWORD *)(v38 + 120) )
          v17 = *(struct PerSessionUpdateState **)(v38 + 120);
        v104 = (int *)v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Update: Failed to check if the payload is removable for Package: {}, Update: {}",
          (__int64)&v104,
          (__int64)v101);
        *(_QWORD *)v103 = v113;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v103);
      }
      v40 = 320;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
        (const char *)v37,
        v100);
      return v37;
    }
    if ( v102 )
    {
      if ( !(unsigned int)CCbsSession::IsClientPBR((CCbsSession *)a3) && !*(_BYTE *)(a3 + 1744) )
      {
        v41 = *(_DWORD *)(a3 + 692);
        if ( v41 >= 0 )
        {
          v42 = *(_DWORD *)(a3 + 2208);
          if ( (v42 & 0x100000) == 0 && (v41 & 4) == 0 && (v42 & 0x20) == 0 && (v42 & 0x10) == 0 && (v41 & 0x20) == 0 )
          {
            v43 = *(_QWORD *)(a1 + 24);
            v44 = Windows::StringUtil::AsLUnicode(v109);
            v45 = *(_QWORD *)(v44 + 16);
            v107 = *(_OWORD *)v44;
            v108 = v45;
            if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(&v107) )
            {
              v46 = Windows::StringUtil::AsLUnicode(v109);
              v47 = *(_QWORD *)(v46 + 16);
              v107 = *(_OWORD *)v46;
              v108 = v47;
              if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(&v107) )
              {
                if ( CCbsSession::IsAnLCUInstalled((CCbsSession *)a3, 0) )
                {
                  v48 = &qword_1802EB518;
                  if ( *(_QWORD *)(v43 + 120) )
                    v48 = *(const wchar_t **)(v43 + 120);
                  v16 = *(_QWORD *)(a1 + 32) == 0;
                  *(_QWORD *)v101 = v48;
                  v49 = &qword_1802EB518;
                  if ( !v16 )
                    v49 = *(const wchar_t **)(a1 + 32);
                  v104 = (int *)v49;
                  if ( LogAdapter::g_Logger )
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      1,
                      (__int64)"Update: Setting SynchronousScavenge to ensure content is immediately removed for {}, package: {}",
                      (__int64)&v104,
                      (__int64)v101);
                  *(_DWORD *)(a3 + 688) |= 0x401u;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v6 &= ~1u;
    }
  }
  SessionUpdateState = CCbsSession::GetSessionUpdateState((CCbsSession *)a3, (struct CCbsUpdate *)a1, 0, 1, &v105);
  v37 = SessionUpdateState;
  if ( SessionUpdateState < 0 )
  {
    v113[0] = SessionUpdateState;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get per-session update state");
      *(_QWORD *)v101 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v101);
    }
    v40 = 355;
    goto LABEL_56;
  }
  CurrentSelectionState = CCbsUpdate::GetCurrentSelectionState(
                            (CCbsUpdate *)a1,
                            (struct CCbsSession *)a3,
                            (enum UpdateSelection *)&v115,
                            v113);
  v37 = CurrentSelectionState;
  if ( CurrentSelectionState < 0 )
  {
    v113[0] = CurrentSelectionState;
    if ( LogAdapter::g_Logger )
    {
      v53 = *(_QWORD *)(a1 + 24);
      v54 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v54 = *(const wchar_t **)(a1 + 32);
      *(_QWORD *)v101 = v54;
      if ( *(_QWORD *)(v53 + 120) )
        v17 = *(struct PerSessionUpdateState **)(v53 + 120);
      v104 = (int *)v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get current selection state for package: {}, update: {}",
        (__int64)&v104,
        (__int64)v101);
      *(_QWORD *)v103 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v103);
    }
    v40 = 358;
    goto LABEL_56;
  }
  v55 = (unsigned int)v115;
  if ( v114 < 2 || v114 == 255 )
  {
    v58 = v105;
    *((_DWORD *)v105 + 2) = v114;
  }
  else
  {
    if ( v114 != 999 )
    {
      v8 = -2146498560;
      LODWORD(v115) = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        v56 = &qword_1802EB518;
        if ( *(_QWORD *)(a1 + 32) )
          v56 = *(const wchar_t **)(a1 + 32);
        *(_QWORD *)v101 = v56;
        v57 = *(_QWORD *)(a1 + 24);
        if ( *(_QWORD *)(v57 + 120) )
          v17 = *(struct PerSessionUpdateState **)(v57 + 120);
        v104 = (int *)v17;
        LogAdapter::Logger::LogNumObjects<enum UpdateSelection,wchar_t const *,wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          v114,
          0,
          v52,
          (__int64)&v114,
          (__int64)&v104,
          (__int64)v101);
        *(_QWORD *)v103 = &v115;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v103);
      }
      v9 = 380;
      goto LABEL_5;
    }
    v58 = v105;
    *((_DWORD *)v105 + 2) = (_DWORD)v115;
  }
  v59 = (__int64)v58 + 24;
  *((_DWORD *)v58 + 6) = v6;
  v60 = v114;
  if ( v55 == v114 )
    goto LABEL_107;
  if ( v55 == 255 )
  {
    if ( v114 == 1 && *(_DWORD *)(a1 + 448) )
      goto LABEL_132;
    if ( v114 || *(_DWORD *)(a1 + 448) )
      goto LABEL_110;
LABEL_107:
    if ( v114 )
      goto LABEL_133;
    if ( (v6 & 1) != 0 && !v113[0] )
      goto LABEL_110;
LABEL_132:
    if ( !v114 )
      goto LABEL_117;
LABEL_133:
    *(_QWORD *)v101 = CbsSelectionToString(v114);
    v70 = CbsSelectionToString(v55);
    v16 = *(_QWORD *)(a1 + 32) == v72;
    v104 = (int *)v70;
    v73 = &qword_1802EB518;
    if ( !v16 )
      v73 = *(const wchar_t **)(a1 + 32);
    *(_QWORD *)v103 = v73;
    v74 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(v74 + 120) != v72 )
      v17 = *(struct PerSessionUpdateState **)(v74 + 120);
    v105 = v17;
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
        (_DWORD)LogAdapter::g_Logger,
        v71,
        v72,
        (unsigned int)"Update: State is unchanged, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}",
        (__int64)&v105,
        (__int64)v103,
        (__int64)&v104,
        (__int64)v101,
        v59);
    return 0;
  }
LABEL_110:
  if ( CCbsSession::IsImageReadOnly((CCbsSession *)a3) )
  {
    if ( !vbInTestMode )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = -2146498493;
    v113[0] = -2146498493;
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v101 = CbsSelectionToString(v114);
      v104 = (int *)CbsSelectionToString(v55);
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        v61,
        0,
        3,
        (__int64)"No write operations (enable/disable feature) are allowed on a container, states: {}, {}",
        (__int64)&v104,
        (__int64)v101);
      *(_QWORD *)v103 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v103);
    }
    v9 = 416;
    goto LABEL_5;
  }
  v60 = v114;
LABEL_117:
  *(_QWORD *)v101 = CbsSelectionToString(v60);
  v104 = (int *)CbsSelectionToString(v55);
  v64 = &qword_1802EB518;
  v65 = (struct PerSessionUpdateState *)&qword_1802EB518;
  if ( *(_QWORD *)(a1 + 32) )
    v64 = *(const wchar_t **)(a1 + 32);
  *(_QWORD *)v103 = v64;
  v66 = *(_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(v66 + 120) )
    v65 = *(struct PerSessionUpdateState **)(v66 + 120);
  v105 = v65;
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned long>(
      (_DWORD)LogAdapter::g_Logger,
      v62,
      v63,
      (unsigned int)"Update: Setting Install State, Package: {}, Update: {}, current State: {}, new state: {}, RemovePayload: {}",
      (__int64)&v105,
      (__int64)v103,
      (__int64)&v104,
      (__int64)v101,
      v59);
  if ( !a5 )
  {
    v98 = *(_QWORD *)(a1 + 24);
    v99 = &qword_1802EB518;
    if ( *(_QWORD *)(a1 + 32) )
      v99 = *(const wchar_t **)(a1 + 32);
    if ( *(_QWORD *)(v98 + 120) )
      v17 = *(struct PerSessionUpdateState **)(v98 + 120);
    CCbsSession::ClearPlannedParentState((CCbsSession *)a3, (const wchar_t *const)v17, v99);
    return 0;
  }
  CCbsSession::InvalidateApplicabilityCache((CCbsSession *)a3);
  v100 = 0;
  v67 = CCbsSession::AddPackageTask(a3, 0, v6, *(_QWORD *)(a1 + 24));
  v37 = v67;
  if ( v67 < 0 )
  {
    v113[0] = v67;
    if ( LogAdapter::g_Logger )
    {
      v68 = *(_QWORD *)(a1 + 24);
      v69 = &qword_1802EB518;
      if ( *(_QWORD *)(a1 + 32) )
        v69 = *(const wchar_t **)(a1 + 32);
      *(_QWORD *)v101 = v69;
      if ( *(_QWORD *)(v68 + 120) )
        v17 = *(struct PerSessionUpdateState **)(v68 + 120);
      v104 = (int *)v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to add task for package: {}, update: {}",
        (__int64)&v104,
        (__int64)v101);
      *(_QWORD *)v103 = v113;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v103);
    }
    v40 = 449;
    goto LABEL_56;
  }
  if ( (unsigned int)CCbsUpdate::GetDeploymentType(a1) == 5 )
  {
    if ( !CCbsSession::IsImageReadOnly((CCbsSession *)a3) )
    {
      v75 = v114;
      if ( v114 == 1 )
      {
        *(_DWORD *)(a3 + 2208) |= 0x44u;
      }
      else if ( !v114 )
      {
        *(_DWORD *)(a3 + 2208) |= 0x88u;
      }
      v76 = *(__int64 **)(a1 + 224);
      v77 = &v76[*(_QWORD *)(a1 + 208)];
      for ( *(_QWORD *)v106 = v77; ; v77 = *(__int64 **)v106 )
      {
        if ( v76 == v77 )
          goto LABEL_174;
        v78 = *v76;
        v115 = 0;
        v79 = vpCapabilityManager;
        *(_QWORD *)v101 = v78;
        InitPointer = (struct CCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v115);
        v81 = CCbsCapabilityManager::ResolveCapability(
                v79,
                (struct CCbsSession *)a3,
                *(const struct CCbsIdentity **)(*(_QWORD *)(v78 + 40) + 24LL),
                InitPointer);
        if ( v81 >= 0 && (v82 = (const wchar_t *)*((_QWORD *)v115 + 6)) != 0 )
        {
          v83 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)(a3 + 1824), v82);
          v84 = v83;
          if ( v83 < 0 )
          {
            v85 = 520;
LABEL_151:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v85,
              (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
              (const char *)(unsigned int)v83,
              v100);
LABEL_172:
            Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v115);
            return v84;
          }
        }
        else
        {
          v86 = &qword_1802EB518;
          if ( *(_QWORD *)(a1 + 32) )
            v86 = *(const wchar_t **)(a1 + 32);
          if ( (unsigned __int8)StringsAreEqual(v86, L"NetFx3", 1) && (*(_DWORD *)(a3 + 2208) & 0x2000) != 0 )
          {
            LogAdapter::TraceAtLevel<>(
              1,
              "Exec: NetFx3 OC and package already added to the execution, ignore the failure and just added the feature name");
            v83 = CCbsStringArray::CopyAndAdd((CCbsStringArray *)(a3 + 1824), L"NetFx3");
            v84 = v83;
            if ( v83 < 0 )
            {
              v85 = 503;
              goto LABEL_151;
            }
          }
          else if ( v114 )
          {
            if ( v81 < 0 )
            {
              v113[0] = v81;
              if ( LogAdapter::g_Logger )
              {
                if ( *(_QWORD *)(a1 + 32) )
                  v17 = *(struct PerSessionUpdateState **)(a1 + 32);
                *(_QWORD *)v106 = v17;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to resolve OC capability: {}",
                  (__int64)v106);
                *(_QWORD *)v101 = v113;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v101);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x204,
                (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
                (const char *)(unsigned int)v81,
                v100);
              v84 = v81;
              goto LABEL_172;
            }
          }
          else
          {
            v104 = *(int **)(*(_QWORD *)(*(_QWORD *)v101 + 40LL) + 24LL);
            v87 = CbsSelectionToString(0);
            v16 = *(_QWORD *)(a1 + 32) == 0;
            v91 = &qword_1802EB518;
            *(_QWORD *)v103 = v87;
            v92 = (struct PerSessionUpdateState *)&qword_1802EB518;
            if ( !v16 )
              v92 = *(struct PerSessionUpdateState **)(a1 + 32);
            v105 = v92;
            v93 = *(_QWORD *)(a1 + 24);
            if ( *(_QWORD *)(v93 + 120) )
              v91 = *(const wchar_t **)(v93 + 120);
            *(_QWORD *)v113 = v91;
            if ( LogAdapter::g_Logger )
              LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t const *,CCbsIdentity *>(
                (__int64)LogAdapter::g_Logger,
                v88,
                v89,
                v90,
                (__int64)v113,
                (__int64)&v105,
                (__int64)v103,
                (__int64)&v104);
          }
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v115);
        v75 = v114;
        ++v76;
      }
    }
    return 0;
  }
  v75 = v114;
LABEL_174:
  if ( v75 != 1 )
    return 0;
  v94 = &qword_1802EB518;
  if ( *(_QWORD *)(a1 + 32) )
    v94 = *(const wchar_t **)(a1 + 32);
  if ( !(unsigned __int8)StringsAreEqual(v94, L"Containers-DisposableClientVM", 1) )
  {
    if ( *(_QWORD *)(a1 + 32) )
      v17 = *(struct PerSessionUpdateState **)(a1 + 32);
    if ( !(unsigned __int8)StringsAreEqual(v17, L"Windows-Defender-ApplicationGuard", 1) )
      return 0;
  }
  v95 = CCbsSession::SetEnhancedOptions((CCbsSession *)a3, 0x40u);
  v96 = v95;
  if ( v95 >= 0 )
  {
    v97 = CCbsSession::DecompressOCContent((CCbsSession *)a3);
    v8 = v97;
    if ( v97 < 0 )
    {
      v113[0] = v97;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to decompress OC content.");
        *(_QWORD *)v106 = v113;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v106);
      }
      v9 = 532;
      goto LABEL_5;
    }
    return 0;
  }
  v113[0] = v95;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set the enhanced option on the session.");
    *(_QWORD *)v106 = v113;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v106);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x212,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsupdate.cpp",
    (const char *)v96,
    v100);
  return v96;
}

```

## disassembly

```asm
0x180092590  push    rbp
0x180092592  push    rbx
0x180092593  push    rsi
0x180092594  push    rdi
0x180092595  push    r12
0x180092597  push    r13
0x180092599  push    r14
0x18009259b  push    r15
0x18009259d  lea     rbp, [rsp-8]
0x1800925a2  sub     rsp, 108h
0x1800925a9  mov     rax, cs:__security_cookie
0x1800925b0  xor     rax, rsp
0x1800925b3  mov     [rbp+40h+var_48], rax
0x1800925b7  xor     ebx, ebx
0x1800925b9  mov     [rbp+40h+var_58], r9d
0x1800925bd  mov     rdi, r8
0x1800925c0  mov     r13d, edx
0x1800925c3  mov     rsi, rcx
0x1800925c6  test    r8, r8
0x1800925c9  jnz     short loc_18009263F
0x1800925cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800925d2  mov     edi, 80070057h
0x1800925d7  mov     [rbp+40h+var_60], edi
0x1800925da  test    rcx, rcx
0x1800925dd  jz      short loc_180092620
0x1800925df  lea     ebx, [r8+3]
0x1800925e3  xor     edx, edx
0x1800925e5  mov     r8d, ebx
0x1800925e8  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1800925ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800925f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800925fb  lea     rax, [rbp+40h+var_60]
0x1800925ff  mov     [rsp+140h+var_D0], rax
0x180092604  lea     r9, asc_1802EE7AC; ": {}"
0x18009260b  lea     rax, [rsp+140h+var_D0]
0x180092610  mov     r8d, ebx
0x180092613  lea     edx, [rbx-2]
0x180092616  mov     [rsp+140h+var_120], rax; int
0x18009261b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092620  mov     edx, 114h; void *
0x180092625  mov     rcx, [rbp+48h]; this
0x180092629  lea     r8, aOnecoreBaseCbs_96; "onecore\\base\\cbs\\core\\cbsupdate.cpp"
0x180092630  mov     r9d, edi; char *
0x180092633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092638  mov     eax, edi
0x18009263a  jmp     loc_1800934E1
0x18009263f  mov     r15d, 1
0x180092645  cmp     r9d, 0FFh
0x18009264c  jz      loc_1800926FD
0x180092652  cmp     r9d, r15d
0x180092655  jbe     loc_1800926FD
0x18009265b  cmp     r9d, 3E7h
0x180092662  jz      loc_1800926FD
0x180092668  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009266f  mov     edi, 800F0800h
0x180092674  mov     [rbp+40h+var_60], edi
0x180092677  test    rcx, rcx
0x18009267a  jz      short loc_1800926F3
0x18009267c  cmp     [rsi+20h], rbx
0x180092680  lea     r14, qword_1802EB518
0x180092687  mov     rax, r14
0x18009268a  cmovnz  rax, [rsi+20h]
0x18009268f  mov     [rsp+140h+var_D0], rax
0x180092694  mov     rax, [rsi+18h]
0x180092698  cmp     [rax+78h], rbx
0x18009269c  cmovnz  r14, [rax+78h]
0x1800926a1  lea     rax, [rsp+140h+var_D0]
0x1800926a6  mov     [rsp+140h+var_110], rax
0x1800926ab  lea     rax, [rbp+40h+var_50]
0x1800926af  mov     [rsp+140h+var_118], rax
0x1800926b4  lea     rax, [rbp+40h+var_58]
0x1800926b8  mov     [rsp+140h+var_120], rax
0x1800926bd  mov     [rbp+40h+var_50], r14
0x1800926c1  call    ??$LogNumObjects@W4UpdateSelection@@PEB_WPEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBW4UpdateSelection@@AEBQEB_W4@Z; LogAdapter::Logger::LogNumObjects<UpdateSelection,wchar_t const *,wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,UpdateSelection const &,wchar_t const * const &,wchar_t const * const &)
0x1800926c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800926cd  lea     rax, [rbp+40h+var_60]
0x1800926d1  mov     qword ptr [rsp+140h+var_E0], rax
0x1800926d6  lea     r9, asc_1802EE7AC; ": {}"
0x1800926dd  lea     rax, [rsp+140h+var_E0]
0x1800926e2  mov     dl, r15b
0x1800926e5  lea     r8d, [r15+2]
0x1800926e9  mov     [rsp+140h+var_120], rax
0x1800926ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800926f3  mov     edx, 117h
0x1800926f8  jmp     loc_180092625
0x1800926fd  cmp     [rbp+40h+arg_20], ebx
0x180092700  jz      short loc_18009276E
0x180092702  mov     rcx, rdi; this
0x180092705  call    ?IsLocked@CCbsSession@@QEAAHXZ; CCbsSession::IsLocked(void)
0x18009270a  test    eax, eax
0x18009270c  jz      short loc_18009276E
0x18009270e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092715  mov     edi, 800F0842h
0x18009271a  mov     [rbp+40h+var_60], edi
0x18009271d  test    rcx, rcx
0x180092720  jz      short loc_180092764
0x180092722  mov     ebx, 3
0x180092727  lea     r9, aAttemptToChang; "Attempt to change a finalized session"
0x18009272e  mov     r8d, ebx
0x180092731  xor     edx, edx
0x180092733  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180092738  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009273f  lea     rax, [rbp+40h+var_60]
0x180092743  mov     qword ptr [rsp+140h+var_E0], rax
0x180092748  lea     r9, asc_1802EE7AC; ": {}"
0x18009274f  lea     rax, [rsp+140h+var_E0]
0x180092754  mov     r8d, ebx
0x180092757  mov     dl, r15b
0x18009275a  mov     [rsp+140h+var_120], rax
0x18009275f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092764  mov     edx, 119h
0x180092769  jmp     loc_180092625
0x18009276e  mov     ecx, r9d
0x180092771  mov     dword ptr [rbp+40h+var_50], 0FFFFFFFFh
0x180092778  mov     [rsp+140h+var_D0], rbx
0x18009277d  mov     [rbp+40h+var_60], ebx
0x180092780  call    ?CbsSelectionToString@@YAPEB_WW4UpdateSelection@@@Z; CbsSelectionToString(UpdateSelection)
0x180092785  cmp     [rsi+20h], rbx
0x180092789  lea     r14, qword_1802EB518
0x180092790  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092797  mov     rcx, r14
0x18009279a  mov     qword ptr [rsp+140h+var_E0], rax
0x18009279f  mov     rax, r14
0x1800927a2  cmovnz  rax, [rsi+20h]
0x1800927a7  mov     [rsp+140h+var_D8], rax
0x1800927ac  mov     rax, [rsi+18h]
0x1800927b0  cmp     [rax+78h], rbx
0x1800927b4  cmovnz  rcx, [rax+78h]
0x1800927b9  mov     qword ptr [rsp+140h+var_F0], rcx
0x1800927be  test    r10, r10
0x1800927c1  jz      short loc_180092801
0x1800927c3  lea     rax, [rsp+140h+var_E0]
0x1800927c8  mov     r8d, r15d
0x1800927cb  mov     [rsp+140h+var_110], rax
0x1800927d0  lea     r9, aUpdateSettingI; "Update: Setting Install State, Package:"...
0x1800927d7  lea     rax, [rsp+140h+var_D8]
0x1800927dc  mov     dl, r15b
0x1800927df  mov     [rsp+140h+var_118], rax
0x1800927e4  mov     rcx, r10
0x1800927e7  lea     rax, [rsp+140h+var_F0]
0x1800927ec  mov     [rsp+140h+var_120], rax
0x1800927f1  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x1800927f6  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800927fd  mov     r9d, [rbp+40h+var_58]
0x180092801  mov     rcx, rsi; this
0x180092804  call    ?IsSelectable@CCbsUpdate@@QEBAHXZ; CCbsUpdate::IsSelectable(void)
0x180092809  test    eax, eax
0x18009280b  jnz     short loc_180092881
0x18009280d  mov     edi, 800F0813h
0x180092812  mov     [rbp+40h+var_60], edi
0x180092815  test    r10, r10
0x180092818  jz      short loc_180092877
0x18009281a  cmp     [rsi+20h], rbx
0x18009281e  lea     rax, [rsp+140h+var_F0]
0x180092823  mov     ebx, 3
0x180092828  mov     [rsp+140h+var_120], rax
0x18009282d  cmovnz  r14, [rsi+20h]
0x180092832  lea     r9, aCannotChangeSt; "Cannot change state of Update because U"...
0x180092839  xor     edx, edx
0x18009283b  mov     qword ptr [rsp+140h+var_F0], r14
0x180092840  mov     r8d, ebx
0x180092843  mov     rcx, r10
0x180092846  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18009284b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092852  lea     rax, [rbp+40h+var_60]
0x180092856  mov     [rsp+140h+var_D8], rax
0x18009285b  lea     r9, asc_1802EE7AC; ": {}"
0x180092862  lea     rax, [rsp+140h+var_D8]
0x180092867  mov     r8d, ebx
0x18009286a  mov     dl, r15b
0x18009286d  mov     [rsp+140h+var_120], rax
0x180092872  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092877  mov     edx, 128h
0x18009287c  jmp     loc_180092625
0x180092881  test    r9d, r9d
0x180092884  jnz     loc_1800929E3
0x18009288a  mov     rdx, [rdi+288h]
0x180092891  test    rdx, rdx
0x180092894  jz      loc_1800929E3
0x18009289a  cmp     bx, [rdx]
0x18009289d  jz      loc_1800929E3
0x1800928a3  lea     rcx, [rbp+40h+var_78]
0x1800928a7  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x1800928ac  lea     rdx, aWindowsOptiona; "Windows Optional Component Manager"
0x1800928b3  lea     rcx, [rbp+40h+var_A8]
0x1800928b7  movups  xmm1, xmmword ptr [rax]
0x1800928ba  movsd   xmm0, qword ptr [rax+10h]
0x1800928bf  movups  [rbp+40h+var_90], xmm1
0x1800928c3  movsd   [rbp+40h+var_80], xmm0
0x1800928c8  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x1800928cd  lea     rdx, [rbp+40h+var_90]
0x1800928d1  lea     rcx, [rbp+40h+var_C0]
0x1800928d5  movups  xmm1, xmmword ptr [rax]
0x1800928d8  movsd   xmm0, qword ptr [rax+10h]
0x1800928dd  movups  [rbp+40h+var_C0], xmm1
0x1800928e1  movsd   [rbp+40h+var_B0], xmm0
0x1800928e6  call    ??$IsStringPrefixEqualByOrdinalCaseInvariant@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0PEAU2@@Z; Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,_LUNICODE_STRING *)
0x1800928eb  test    al, al
0x1800928ed  jz      loc_1800929E3
0x1800928f3  mov     rcx, rsi
0x1800928f6  call    ?GetDeploymentType@CCbsUpdate@@QEBA?AW4DEPLOYMENT_TYPE@UPDATE_TYPE@@XZ; CCbsUpdate::GetDeploymentType(void)
0x1800928fb  cmp     eax, 5
0x1800928fe  jz      loc_1800929E3
0x180092904  mov     rbx, [rsi+18h]
0x180092908  lea     rcx, [rbp+40h+var_A8]
0x18009290c  mov     rdx, [rbx+70h]
0x180092910  add     rdx, 1Eh
0x180092914  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180092919  lea     rcx, [rbp+40h+var_C0]
0x18009291d  movups  xmm1, xmmword ptr [rax]
0x180092920  movsd   xmm0, qword ptr [rax+10h]
0x180092925  movups  [rbp+40h+var_C0], xmm1
0x180092929  movsd   [rbp+40h+var_B0], xmm0
0x18009292e  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@$$BY0BO@_W@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@AEAY0BO@$$CB_W@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [30]>(_LUNICODE_STRING const &,wchar_t const (&)[30])
0x180092933  test    al, al
0x180092935  jz      loc_1800929E1
0x18009293b  cmp     qword ptr [rsi+20h], 0
0x180092940  lea     rcx, [rbp+40h+var_A8]
0x180092944  mov     rdx, r14
0x180092947  cmovnz  rdx, [rsi+20h]
0x18009294c  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x180092951  lea     rcx, [rbp+40h+var_C0]
0x180092955  movups  xmm1, xmmword ptr [rax]
0x180092958  movsd   xmm0, qword ptr [rax+10h]
0x18009295d  movups  [rbp+40h+var_C0], xmm1
0x180092961  movsd   [rbp+40h+var_B0], xmm0
0x180092966  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@$$BY06_W@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@AEAY06$$CB_W@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,wchar_t [7]>(_LUNICODE_STRING const &,wchar_t const (&)[7])
0x18009296b  test    al, al
0x18009296d  jz      short loc_1800929E1
0x18009296f  cmp     qword ptr [rbx+78h], 0
0x180092974  mov     rax, r14
0x180092977  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009297e  cmovnz  rax, [rbx+78h]
0x180092983  xor     ebx, ebx
0x180092985  cmp     [rsi+20h], rbx
0x180092989  mov     qword ptr [rsp+140h+var_F0], rax
0x18009298e  mov     rax, r14
0x180092991  cmovnz  rax, [rsi+20h]
0x180092996  mov     [rsp+140h+var_D8], rax
0x18009299b  mov     rax, [rdi+288h]
0x1800929a2  mov     qword ptr [rsp+140h+var_E0], rax
0x1800929a7  test    rcx, rcx
0x1800929aa  jz      short loc_1800929DC
0x1800929ac  lea     rax, [rsp+140h+var_F0]
0x1800929b1  mov     r8d, r15d
0x1800929b4  mov     [rsp+140h+var_110], rax
0x1800929b9  lea     r9, aUpdateInferrin; "Update: Inferring removal for disable r"...
0x1800929c0  lea     rax, [rsp+140h+var_D8]
0x1800929c5  mov     dl, r15b
0x1800929c8  mov     [rsp+140h+var_118], rax
0x1800929cd  lea     rax, [rsp+140h+var_E0]
0x1800929d2  mov     [rsp+140h+var_120], rax
0x1800929d7  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x1800929dc  or      r13d, r15d
0x1800929df  jmp     short loc_1800929E3
0x1800929e1  xor     ebx, ebx
0x1800929e3  test    r15b, r13b
0x1800929e6  jz      loc_180092BFF
0x1800929ec  lea     r8, [rsp+140h+var_E8]
0x1800929f1  mov     [rsp+140h+var_E8], bl
0x1800929f5  mov     rdx, rsi; CCbsUpdate *
0x1800929f8  mov     rcx, rdi; this
0x1800929fb  call    IsSelectablePayloadRemovable
0x180092a00  mov     r12d, eax
0x180092a03  test    eax, eax
0x180092a05  jns     loc_180092AB6
0x180092a0b  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a12  mov     [rbp+40h+var_60], eax
0x180092a15  test    r10, r10
0x180092a18  jz      short loc_180092A96
0x180092a1a  cmp     [rsi+20h], rbx
0x180092a1e  lea     r9, aUpdateFailedTo; "Update: Failed to check if the payload "...
0x180092a25  mov     rax, [rsi+18h]
0x180092a29  mov     rcx, r14
0x180092a2c  cmovnz  rcx, [rsi+20h]
0x180092a31  mov     qword ptr [rsp+140h+var_F0], rcx
0x180092a36  mov     rcx, r10
0x180092a39  cmp     [rax+78h], rbx
0x180092a3d  mov     ebx, 3
0x180092a42  mov     r8d, ebx
0x180092a45  cmovnz  r14, [rax+78h]
0x180092a4a  lea     rax, [rsp+140h+var_F0]
0x180092a4f  mov     [rsp+140h+var_118], rax
0x180092a54  xor     edx, edx
0x180092a56  lea     rax, [rsp+140h+var_D8]
0x180092a5b  mov     [rsp+140h+var_D8], r14
0x180092a60  mov     [rsp+140h+var_120], rax
0x180092a65  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x180092a6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a71  lea     rax, [rbp+40h+var_60]
0x180092a75  mov     qword ptr [rsp+140h+var_E0], rax
0x180092a7a  lea     r9, asc_1802EE7AC; ": {}"
0x180092a81  lea     rax, [rsp+140h+var_E0]
0x180092a86  mov     r8d, ebx
0x180092a89  mov     dl, r15b
0x180092a8c  mov     [rsp+140h+var_120], rax; int
0x180092a91  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092a96  mov     edx, 140h; void *
0x180092a9b  mov     rcx, [rbp+48h]; this
0x180092a9f  lea     r8, aOnecoreBaseCbs_96; "onecore\\base\\cbs\\core\\cbsupdate.cpp"
  ... truncated ...
```
