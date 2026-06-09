# _SebiCreateEvent(void *,_CSebiSystemEventCreationParameter,CBroker::_CustomData *,_CBROKERED_EVENT_ID *,void * *)

- ea: `0x180009740`
- end: `0x18000a7c9`
- name: `?_SebiCreateEvent@@YAKPEAXU_CSebiSystemEventCreationParameter@@PEAU_CustomData@CBroker@@PEAU_CBROKERED_EVENT_ID@@PEAPEAX@Z`
- size: `4233`
- prototype: `__int64 __fastcall(__int64, const struct _CSebiSystemEventCreationParameter *, const struct CBroker::_CustomData *, _QWORD *, void *)`
- caller_count: `3`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004040`
- `0x18001fea0`
- `0x1800200c0`

## callees

- `0x1800016c4`
- `0x1800030e0`
- `0x1800036f0`
- `0x180005a50`
- `0x180006e00`
- `0x180008c00`
- `0x180009740`
- `0x18000b168`
- `0x18000b180`
- `0x18000b340`
- `0x18000b3d0`
- `0x18000bb50`
- `0x18000bbc0`
- `0x18000beb4`
- `0x18000cb50`
- `0x18000df40`
- `0x180015c1c`
- `0x180019130`
- `0x180019340`
- `0x1800195e0`
- `0x18001ab64`
- `0x18001ab9c`
- `0x18001cf50`
- `0x18001cf74`
- `0x18001d364`
- `0x18001d9ac`
- `0x18001e0d8`
- `0x18001e3bc`
- `0x180022434`
- `0x18002244c`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a6c7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a6c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009d5b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009ea4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009d5b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009ea4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009d6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009ff7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009d6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a111`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180009f44`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180009f44`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a260`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009eaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009eaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800097ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800097ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800097e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800097e6`
- `RPCRT4!RpcImpersonateClient` at `0x1800097a4`
- `RPCRT4!RpcImpersonateClient` at `0x1800098a8`
- `RPCRT4!RpcImpersonateClient` at `0x1800097a4`
- `RPCRT4!RpcImpersonateClient` at `0x1800098a8`
- `RPCRT4!RpcRevertToSelf` at `0x1800097f8`
- `RPCRT4!RpcRevertToSelf` at `0x1800098bf`
- `RPCRT4!RpcRevertToSelf` at `0x1800097f8`
- `RPCRT4!RpcRevertToSelf` at `0x1800098bf`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800097bc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800097bc`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009a83`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009a83`

## string_xrefs

- `0x1800098d8`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall _SebiCreateEvent(
        __int64 a1,
        const struct _CSebiSystemEventCreationParameter *a2,
        const struct CBroker::_CustomData *a3,
        _QWORD *a4,
        void *a5)
{
  unsigned int v8; // eax
  HANDLE CurrentThread; // rax
  __int128 v10; // xmm0
  CBroker::SebBroker *v11; // rbx
  __int128 v12; // xmm0
  __int64 v13; // rbx
  unsigned int v14; // r13d
  __int64 v15; // rbx
  WCHAR *v16; // rbx
  void *v17; // rsi
  __int128 v18; // xmm0
  __int64 v19; // r8
  LONG v20; // eax
  __int64 v21; // r8
  void *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  void *v25; // rcx
  unsigned __int64 v26; // rdx
  __int64 v27; // rbx
  _OWORD *v28; // rax
  EventContext *v29; // rax
  EventContext *v30; // r14
  char *v31; // rsi
  char v32; // bl
  char *v33; // r12
  size_t v34; // r15
  char *v35; // r13
  unsigned __int64 v36; // rcx
  signed __int64 v37; // rbx
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  char *v40; // rbx
  char *v41; // rax
  CBroker::SebBroker *v42; // rbx
  char *v43; // r14
  __int64 v44; // rbx
  const WCHAR *v45; // rax
  const WCHAR *v46; // r8
  const void *v47; // rcx
  size_t v48; // r8
  volatile signed __int32 *v49; // rbx
  volatile signed __int32 *v50; // rbx
  void *v51; // rcx
  unsigned __int64 v52; // rdx
  size_t v54; // rax
  DWORD v55; // eax
  DWORD LengthSid; // eax
  bool v57; // r9
  DWORD LastError; // eax
  char *v59; // rbx
  size_t v60; // r15
  _QWORD *v61; // rbx
  __int64 v62; // rax
  bool lpString2; // [rsp+20h] [rbp-4F8h]
  unsigned int cchCount2; // [rsp+28h] [rbp-4F0h]
  ULONG v65; // [rsp+50h] [rbp-4C8h]
  UINT32 packageFamilyNameLength[2]; // [rsp+58h] [rbp-4C0h] BYREF
  char v67; // [rsp+60h] [rbp-4B8h]
  DWORD CurrentThreadId; // [rsp+64h] [rbp-4B4h]
  void *v69; // [rsp+68h] [rbp-4B0h] BYREF
  CBroker::SebBroker *v70[2]; // [rsp+70h] [rbp-4A8h]
  unsigned int Pid; // [rsp+80h] [rbp-498h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-490h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+90h] [rbp-488h] BYREF
  Broker::BILayer::Failure *v74; // [rsp+A8h] [rbp-470h] BYREF
  Broker::Win32Error *v75; // [rsp+B0h] [rbp-468h] BYREF
  Broker::BrokerCommonException *v76; // [rsp+B8h] [rbp-460h] BYREF
  __int128 v77; // [rsp+D0h] [rbp-448h] BYREF
  void **v78; // [rsp+E0h] [rbp-438h] BYREF
  __int128 v79; // [rsp+E8h] [rbp-430h]
  int v80; // [rsp+F8h] [rbp-420h]
  void **v81; // [rsp+100h] [rbp-418h] BYREF
  __int128 v82; // [rsp+108h] [rbp-410h]
  int v83; // [rsp+118h] [rbp-400h]
  int v84; // [rsp+120h] [rbp-3F8h]
  _QWORD v85[3]; // [rsp+128h] [rbp-3F0h] BYREF
  int v86; // [rsp+140h] [rbp-3D8h]
  unsigned int v87; // [rsp+148h] [rbp-3D0h]
  _QWORD v88[3]; // [rsp+150h] [rbp-3C8h] BYREF
  int v89; // [rsp+168h] [rbp-3B0h]
  unsigned int v90; // [rsp+170h] [rbp-3A8h]
  void **v91; // [rsp+178h] [rbp-3A0h] BYREF
  __int128 v92; // [rsp+180h] [rbp-398h]
  int v93; // [rsp+190h] [rbp-388h]
  int v94; // [rsp+198h] [rbp-380h]
  struct _GUID Src; // [rsp+1A0h] [rbp-378h] BYREF
  void *Buf2[2]; // [rsp+1B0h] [rbp-368h] BYREF
  __int64 v97; // [rsp+1C0h] [rbp-358h]
  LPCWCH v98[2]; // [rsp+1C8h] [rbp-350h] BYREF
  int v99[2]; // [rsp+1D8h] [rbp-340h]
  unsigned __int64 v100; // [rsp+1E0h] [rbp-338h]
  __int128 v101; // [rsp+1E8h] [rbp-330h] BYREF
  __int64 v102; // [rsp+1F8h] [rbp-320h]
  unsigned __int64 v103; // [rsp+200h] [rbp-318h]
  __int128 v104; // [rsp+210h] [rbp-308h] BYREF
  __int128 v105; // [rsp+220h] [rbp-2F8h]
  _BYTE v106[24]; // [rsp+230h] [rbp-2E8h] BYREF
  unsigned __int64 v107; // [rsp+248h] [rbp-2D0h]
  unsigned int v108; // [rsp+250h] [rbp-2C8h]
  struct _GUID Buf1; // [rsp+260h] [rbp-2B8h] BYREF
  void *v110[2]; // [rsp+270h] [rbp-2A8h] BYREF
  __int64 v111; // [rsp+280h] [rbp-298h]
  __int128 v112; // [rsp+288h] [rbp-290h] BYREF
  __int64 v113; // [rsp+298h] [rbp-280h]
  __int64 v114; // [rsp+2A0h] [rbp-278h]
  __int128 v115; // [rsp+2A8h] [rbp-270h] BYREF
  __int64 v116; // [rsp+2B8h] [rbp-260h]
  __int64 v117; // [rsp+2C0h] [rbp-258h]
  WCHAR packageFullName[128]; // [rsp+2D0h] [rbp-248h] BYREF
  WCHAR packageFamilyName[132]; // [rsp+3D0h] [rbp-148h] BYREF

  v69 = a5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  v77 = 0;
  Buf1 = 0;
  if ( RpcImpersonateClient(0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
    v82 = 0;
    v83 = 1;
    v81 = &Broker::Win32Error::`vftable';
    v84 = 5;
    throw (Broker::Win32Error *)&v81;
  }
  v8 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v8 )
  {
    *(_OWORD *)&v106[8] = 0;
    LODWORD(v107) = 1;
    *(_QWORD *)v106 = &Broker::Win32Error::`vftable';
    v108 = v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v8);
    std::exception::exception((std::exception *)v85, (const struct std::exception *)v106);
    v86 = v107;
    v85[0] = &Broker::Win32Error::`vftable';
    v87 = v108;
    throw (Broker::Win32Error *)v85;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    *(_OWORD *)&v106[8] = 0;
    LODWORD(v107) = 1;
    *(_QWORD *)v106 = &Broker::Win32Error::`vftable';
    v108 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    std::exception::exception((std::exception *)v88, (const struct std::exception *)v106);
    v89 = v107;
    v88[0] = &Broker::Win32Error::`vftable';
    v90 = v108;
    throw (Broker::Win32Error *)v88;
  }
  v65 = 0;
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
  std::vector<_GUID>::vector<_GUID>(Buf2);
  v10 = 0;
  *(_OWORD *)v98 = 0;
  *(_QWORD *)v99 = 0;
  v100 = 0;
  *(double *)&v10 = ((double (__fastcall *)(LPCWCH *))std::wstring::_Construct_empty)(v98);
  v101 = v10;
  v102 = 0;
  v103 = 0;
  std::wstring::_Construct_empty((__int64)&v101);
  *a4 = 0;
  *(_QWORD *)v69 = 0;
  v11 = CBroker::SebBroker::Instance;
  if ( CBroker::SebBroker::Instance
    && (v31 = (char *)CBroker::SebBroker::Instance + 8,
        RtlAcquireSRWLockExclusive((char *)CBroker::SebBroker::Instance + 8),
        GetCurrentThreadId(),
        v32 = *(_BYTE *)v11,
        RtlReleaseSRWLockExclusive(v31),
        v32) )
  {
    if ( *(&CBroker::SebBroker::Instance + 1) )
      _InterlockedIncrement((volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1) + 2);
    v12 = *(_OWORD *)&CBroker::SebBroker::Instance;
  }
  else
  {
    v12 = 0;
  }
  *(_OWORD *)v70 = v12;
  if ( !(_QWORD)v12 )
  {
    v65 = 21;
LABEL_167:
    if ( __eh34_try(-1, 4) )
    {
      __eh34_scope_strut(4);
      v61 = v69;
      if ( *(_QWORD *)v69 )
      {
        FreeContextHandle(*(void **)v69);
        *v61 = 0;
      }
      if ( memcmp_0(&Buf1, &v77, 0x10u) )
        CBroker::SebBroker::DeleteEvent(v70[0], (const struct Broker::ApplicationIdentity *)Buf2, &Buf1, v57, lpString2);
    }
    if ( __eh34_catch(4) )
    {
      if ( __eh34_catch_ellipsis(4) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
        __eh34_try_continuation(4, &loc_18000A769);
      }
    }
    goto LABEL_85;
  }
  v13 = *(_QWORD *)a2;
  if ( RpcImpersonateClient(0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
    v92 = 0;
    v93 = 1;
    v91 = &Broker::Win32Error::`vftable';
    v94 = 5;
    throw (Broker::Win32Error *)&v91;
  }
  ClientAccessCheck(v13);
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
  v14 = Pid;
  StringCchPrintfW(packageFullName, 0x7Fu, L"Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe", Pid);
  v104 = 0;
  v105 = 0u;
  std::wstring::_Construct_empty((__int64)&v104);
  v15 = Broker::RpcClientToken::GetPackageFullName(&Pid, v106);
  if ( &v104 != (__int128 *)v15 )
  {
    if ( *((_QWORD *)&v105 + 1) > 7u )
      std::_Deallocate<16>((void *)v104, 2LL * *((_QWORD *)&v105 + 1) + 2);
    *(_QWORD *)&v105 = 0;
    *((_QWORD *)&v105 + 1) = 7;
    LOWORD(v104) = 0;
    v104 = *(_OWORD *)v15;
    v105 = *(_OWORD *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
  }
  if ( v107 > 7 )
    std::_Deallocate<16>(*(void **)v106, 2 * v107 + 2);
  if ( (_QWORD)v105 )
  {
    v16 = (WCHAR *)&v104;
    if ( *((_QWORD *)&v105 + 1) > 7u )
      v16 = (WCHAR *)v104;
  }
  else
  {
    v16 = packageFullName;
  }
  v17 = *(void **)Broker::RpcClientToken::GetUserSid(&Pid, v106);
  std::vector<_GUID>::vector<_GUID>(v110);
  v18 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  *(double *)&v18 = ((double (__fastcall *)(__int128 *))std::wstring::_Construct_empty)(&v112);
  v115 = v18;
  v116 = 0;
  v117 = 0;
  std::wstring::_Construct_empty((__int64)&v115);
  if ( v17 )
  {
    LengthSid = GetLengthSid(v17);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)v110, (_BYTE *)v110[0], v17, LengthSid);
  }
  if ( v16 )
  {
    packageFamilyNameLength[0] = 0;
    v19 = -1;
    do
      ++v19;
    while ( v16[v19] );
    ((void (__fastcall *)(__int128 *, WCHAR *))std::wstring::_Assign<unsigned short>)(&v115, v16);
    packageFamilyNameLength[0] = 128;
    v20 = PackageFamilyNameFromFullName(v16, packageFamilyNameLength, packageFamilyName);
    v21 = -1;
    if ( v20 )
    {
      do
        ++v21;
      while ( v16[v21] );
      ((void (__fastcall *)(__int128 *, WCHAR *))std::wstring::_Assign<unsigned short>)(&v112, v16);
    }
    else
    {
      do
        ++v21;
      while ( packageFamilyName[v21] );
      ((void (__fastcall *)(__int128 *, WCHAR *))std::wstring::_Assign<unsigned short>)(&v112, packageFamilyName);
    }
  }
  v22 = *(void **)v106;
  if ( *(_QWORD *)v106 )
  {
    v23 = *(_QWORD *)&v106[16] - *(_QWORD *)v106;
    *(_QWORD *)&Src.Data1 = *(_QWORD *)&v106[16] - *(_QWORD *)v106;
    *(_QWORD *)packageFamilyNameLength = *(_QWORD *)v106;
    if ( *(_QWORD *)&v106[16] - *(_QWORD *)v106 >= 0x1000u )
    {
      std::_Adjust_manually_vector_aligned((void **)packageFamilyNameLength, (unsigned __int64 *)&Src.Data1);
      v22 = *(void **)packageFamilyNameLength;
      v23 = *(_QWORD *)&Src.Data1;
    }
    ((void (__fastcall *)(void *, unsigned __int64))operator delete)(v22, v23);
  }
  if ( *((_QWORD *)&v105 + 1) > 7u )
    std::_Deallocate<16>((void *)v104, 2LL * *((_QWORD *)&v105 + 1) + 2);
  std::vector<unsigned char>::_Tidy(Buf2);
  Buf2[0] = v110[0];
  Buf2[1] = v110[1];
  v97 = v111;
  *(_OWORD *)v110 = 0;
  v111 = 0;
  if ( v100 > 7 )
    std::_Deallocate<16>((void *)v98[0], 2 * v100 + 2);
  *(_OWORD *)v98 = v112;
  *(_QWORD *)v99 = v113;
  v100 = v114;
  v113 = 0;
  v24 = 7;
  v114 = 7;
  LOWORD(v112) = 0;
  if ( v103 > 7 )
  {
    std::_Deallocate<16>((void *)v101, 2 * v103 + 2);
    v24 = v114;
  }
  v101 = v115;
  v102 = v116;
  v103 = v117;
  v116 = 0;
  v117 = 7;
  LOWORD(v115) = 0;
  if ( v24 > 7 )
    std::_Deallocate<16>((void *)v112, 2 * v24 + 2);
  v113 = 0;
  v114 = 7;
  LOWORD(v112) = 0;
  v25 = v110[0];
  if ( v110[0] )
  {
    v26 = v111 - (unsigned __int64)v110[0];
    *(_QWORD *)packageFamilyNameLength = v111 - (unsigned __int64)v110[0];
    *(void **)&Src.Data1 = v110[0];
    if ( v111 - (unsigned __int64)v110[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&Src, (unsigned __int64 *)packageFamilyNameLength);
      v25 = *(void **)&Src.Data1;
      v26 = *(_QWORD *)packageFamilyNameLength;
    }
    ((void (__fastcall *)(void *, unsigned __int64))operator delete)(v25, v26);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, packageFullName);
  Buf1 = *CBroker::SebBroker::CreateEventW(
            v70[0],
            &Src,
            (const struct Broker::ApplicationIdentity *)Buf2,
            a2,
            a3,
            cchCount2);
  v27 = *(_QWORD *)&Buf1.Data1;
  *a4 = *(_QWORD *)&Buf1.Data1;
  v28 = operator new(0x28u);
  *v28 = 0;
  v28[1] = 0;
  *((_QWORD *)v28 + 4) = 0;
  v29 = EventContext::EventContext((EventContext *)v28);
  v30 = v29;
  if ( !v29 )
  {
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_QWORD *)v29 = v27;
  *((_DWORD *)v29 + 2) = v14;
  v33 = (char *)v29 + 16;
  if ( (void **)((char *)v29 + 16) != Buf2 )
  {
    *(void **)&Src.Data1 = Buf2[0];
    v34 = (char *)Buf2[1] - (char *)Buf2[0];
    v35 = *(char **)v33;
    v36 = *((_QWORD *)v29 + 4) - *((_QWORD *)v29 + 2);
    if ( (char *)Buf2[1] - (char *)Buf2[0] <= v36 )
    {
      v54 = *((_QWORD *)v29 + 3) - (_QWORD)v35;
      *(_QWORD *)packageFamilyNameLength = v54;
      if ( v34 > v54 )
      {
        memmove_0(v35, Buf2[0], v54);
        v59 = (char *)*((_QWORD *)v33 + 1);
        v60 = v34 - *(_QWORD *)packageFamilyNameLength;
        memmove_0(v59, (const void *)(*(_QWORD *)packageFamilyNameLength + *(_QWORD *)&Src.Data1), v60);
        v41 = &v59[v60];
      }
      else
      {
        memmove_0(v35, Buf2[0], (char *)Buf2[1] - (char *)Buf2[0]);
        v41 = &v35[v34];
      }
    }
    else
    {
      v37 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v34 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      v38 = v36 >> 1;
      if ( v36 <= 0x7FFFFFFFFFFFFFFFLL - (v36 >> 1) )
      {
        v37 = v36 + v38;
        if ( v36 + v38 < v34 )
          v37 = (char *)Buf2[1] - (char *)Buf2[0];
      }
      if ( v35 )
      {
        std::_Deallocate<16>(*((void **)v29 + 2), *((_QWORD *)v29 + 4) - (_QWORD)v35);
        *(_QWORD *)v33 = 0;
        *((_QWORD *)v33 + 1) = 0;
        *((_QWORD *)v33 + 2) = 0;
      }
      v39 = (__int64)std::_Allocate<16,std::_Default_allocate_traits>(v37);
      *(_QWORD *)v33 = v39;
      *((_QWORD *)v33 + 1) = v39;
      *((_QWORD *)v33 + 2) = v37 + v39;
      v40 = *(char **)v33;
      memmove_0(*(void **)v33, *(const void **)&Src.Data1, v34);
      v41 = &v40[v34];
    }
    *((_QWORD *)v33 + 1) = v41;
  }
  *(_QWORD *)v69 = v30;
  v42 = v70[0];
  *(_OWORD *)v106 = 0;
  v43 = (char *)v70[0] + 8;
  *(_QWORD *)packageFamilyNameLength = (char *)v70[0] + 8;
  RtlAcquireSRWLockExclusive((char *)v70[0] + 8);
  CurrentThreadId = GetCurrentThreadId();
  v67 = 1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, &Buf1);
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    Broker::BrokerEventTable<CBroker::SebEvent>::Find((char *)v42 + 16, &Src, &Buf1);
    v44 = *(_QWORD *)&Src.Data1;
    v45 = (const WCHAR *)v98;
    if ( v100 > 7 )
      v45 = v98[0];
    v46 = (const WCHAR *)(*(_QWORD *)&Src.Data1 + 32LL);
    if ( *(_QWORD *)(*(_QWORD *)&Src.Data1 + 56LL) > 7u )
      v46 = *(const WCHAR **)v46;
    if ( CompareStringEx(&LocaleName, 1u, v46, *(_DWORD *)(*(_QWORD *)&Src.Data1 + 48LL), v45, v99[0], 0, 0, 0) != 2
      || (v47 = *(const void **)(v44 + 8),
          v48 = *(_QWORD *)(v44 + 16) - (_QWORD)v47,
          v48 < (char *)Buf2[1] - (char *)Buf2[0])
      || v48 > (char *)Buf2[1] - (char *)Buf2[0]
      || memcmp_0(v47, Buf2[0], v48) )
    {
      v79 = 0;
      v80 = 5;
      v78 = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)&v78;
    }
    CBroker::SebEvent::OnEnable(*(CBroker::SebEvent **)&Src.Data1);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v65 = 14;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000A721);
      goto LABEL_167;
    }
    if ( __eh34_catch_type(2, &Broker::ApplicationLimitsExceeded `RTTI Type Descriptor', 0) )
    {
      v65 = 1816;
      __eh34_try_continuation(2, &Broker::ApplicationLimitsExceeded `RTTI Type Descriptor', &loc_18000A723);
      goto LABEL_167;
    }
    if ( __eh34_catch_type(2, &Broker::AccessDenied `RTTI Type Descriptor', 0) )
    {
      v65 = 5;
      __eh34_try_continuation(2, &Broker::AccessDenied `RTTI Type Descriptor', &loc_18000A725);
      goto LABEL_167;
    }
    if ( __eh34_catch_type(2, &Broker::BILayer::Failure `RTTI Type Descriptor', &v74) )
    {
      v65 = RtlNtStatusToDosError(*((_DWORD *)v74 + 8));
      __eh34_try_continuation(2, &Broker::BILayer::Failure `RTTI Type Descriptor', &loc_18000A727);
      goto LABEL_84;
    }
    if ( __eh34_catch_type(2, &Broker::Win32Error `RTTI Type Descriptor', &v75) )
    {
      v65 = *((_DWORD *)v75 + 8);
      __eh34_try_continuation(2, &Broker::Win32Error `RTTI Type Descriptor', &loc_18000A72C);
LABEL_84:
      if ( !v65 )
        goto LABEL_85;
      goto LABEL_167;
    }
    if ( __eh34_catch_type(2, &Broker::InvalidParameter `RTTI Type Descriptor', 0) )
    {
      v65 = 87;
      __eh34_try_continuation(2, &Broker::InvalidParameter `RTTI Type Descriptor', &loc_18000A731);
      goto LABEL_167;
    }
    if ( __eh34_catch_type(2, &Broker::BrokerCommonException `RTTI Type Descriptor', &v76) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v62 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v76 + 8LL))(v76);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v62);
      }
      v65 = 1359;
      __eh34_try_continuation(2, &Broker::BrokerCommonException `RTTI Type Descriptor', &loc_18000A733);
      goto LABEL_167;
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, &Buf1);
  v49 = *(volatile signed __int32 **)Src.Data4;
  if ( *(_QWORD *)Src.Data4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Src.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  RtlReleaseSRWLockExclusive(v43);
LABEL_85:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v65);
  v50 = (volatile signed __int32 *)v70[1];
  if ( v70[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v70[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
      if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
    }
  }
  if ( v103 > 7 )
    std::_Deallocate<16>((void *)v101, 2 * v103 + 2);
  v102 = 0;
  v103 = 7;
  LOWORD(v101) = 0;
  if ( v100 > 7 )
    std::_Deallocate<16>((void *)v98[0], 2 * v100 + 2);
  *(_QWORD *)v99 = 0;
  v100 = 7;
  LOWORD(v98[0]) = 0;
  v51 = Buf2[0];
  if ( Buf2[0] )
  {
    v52 = v97 - (unsigned __int64)Buf2[0];
    *(_QWORD *)&Src.Data1 = v97 - (unsigned __int64)Buf2[0];
    v69 = Buf2[0];
    if ( v97 - (unsigned __int64)Buf2[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v69, (unsigned __int64 *)&Src.Data1);
      v52 = *(_QWORD *)&Src.Data1;
      v51 = v69;
    }
    ((void (__fastcall *)(void *, unsigned __int64))operator delete)(v51, v52);
    *(_OWORD *)Buf2 = 0;
    v97 = 0;
  }
  if ( !CloseHandle(TokenHandle)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v55 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v55);
  }
  return v65;
}

```

## disassembly

```asm
0x180009740  push    rbx
0x180009742  push    rsi
0x180009743  push    rdi
0x180009744  push    r12
0x180009746  push    r13
0x180009748  push    r14
0x18000974a  push    r15
0x18000974c  sub     rsp, 4E0h
0x180009753  mov     rax, cs:__security_cookie
0x18000975a  xor     rax, rsp
0x18000975d  mov     [rsp+518h+var_40], rax
0x180009765  mov     r14, r9
0x180009768  mov     r12, r8
0x18000976b  mov     r15, rdx
0x18000976e  mov     rax, [rsp+518h+arg_20]
0x180009776  mov     [rsp+518h+var_4B0], rax
0x18000977b  xor     edi, edi
0x18000977d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009784  test    byte ptr [rcx+1Ch], 8
0x180009788  jnz     loc_180009D97
0x18000978e  xorps   xmm0, xmm0
0x180009791  movaps  [rsp+518h+var_448], xmm0
0x180009799  movdqa  [rsp+518h+Buf1], xmm0
0x1800097a2  xor     ecx, ecx; BindingHandle
0x1800097a4  call    cs:__imp_RpcImpersonateClient
0x1800097aa  test    eax, eax
0x1800097ac  jnz     loc_18000A38B
0x1800097b2  lea     rdx, [rsp+518h+Pid]; Pid
0x1800097ba  xor     ecx, ecx; Binding
0x1800097bc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800097c2  test    eax, eax
0x1800097c4  jnz     loc_18000A3F8
0x1800097ca  call    cs:__imp_GetCurrentThread
0x1800097d0  mov     rcx, rax; ThreadHandle
0x1800097d3  lea     r9, [rsp+518h+TokenHandle]; TokenHandle
0x1800097db  mov     edx, 8; DesiredAccess
0x1800097e0  mov     r8d, 1; OpenAsSelf
0x1800097e6  call    cs:__imp_OpenThreadToken
0x1800097ec  test    eax, eax
0x1800097ee  jz      loc_18000A49D
0x1800097f4  mov     [rsp+518h+var_4C8], edi
0x1800097f8  call    cs:__imp_RpcRevertToSelf
0x1800097fe  test    eax, eax
0x180009800  jnz     loc_18000A286
0x180009806  lea     rcx, [rsp+518h+Buf2]
0x18000980e  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009813  xorps   xmm0, xmm0
0x180009816  movups  xmmword ptr [rsp+518h+var_350], xmm0
0x18000981e  mov     qword ptr [rsp+518h+var_340], rdi
0x180009826  mov     [rsp+518h+var_338], rdi
0x18000982e  lea     rcx, [rsp+518h+var_350]
0x180009836  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000983b  movups  [rsp+518h+var_330], xmm0
0x180009843  mov     [rsp+518h+var_320], rdi
0x18000984b  mov     [rsp+518h+var_318], rdi
0x180009853  lea     rcx, [rsp+518h+var_330]
0x18000985b  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009860  nop
0x180009861  xor     eax, eax
0x180009863  mov     [r14], rax
0x180009866  mov     rax, [rsp+518h+var_4B0]
0x18000986b  mov     [rax], rdi
0x18000986e  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180009875  test    rbx, rbx
0x180009878  jnz     loc_180009D54
0x18000987e  xorps   xmm0, xmm0
0x180009881  movdqu  xmmword ptr [rsp+518h+var_4A8], xmm0
0x180009887  movq    rax, xmm0
0x18000988c  mov     [rsp+518h+var_4A8], rax
0x180009891  test    rax, rax
0x180009894  jnz     short loc_1800098A3
0x180009896  mov     [rsp+518h+var_4C8], 15h
0x18000989e  jmp     loc_18000A74B
0x1800098a3  mov     rbx, [r15]
0x1800098a6  xor     ecx, ecx; BindingHandle
0x1800098a8  call    cs:__imp_RpcImpersonateClient
0x1800098ae  test    eax, eax
0x1800098b0  jnz     loc_18000A548
0x1800098b6  mov     rcx, rbx
0x1800098b9  call    ClientAccessCheck
0x1800098be  nop
0x1800098bf  call    cs:__imp_RpcRevertToSelf
0x1800098c5  test    eax, eax
0x1800098c7  jnz     loc_18000A2BB
0x1800098cd  mov     r13d, [rsp+518h+Pid]
0x1800098d5  mov     r9d, r13d
0x1800098d8  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x1800098df  mov     edx, 7Fh; unsigned __int64
0x1800098e4  lea     rcx, [rsp+518h+packageFullName]; unsigned __int16 *
0x1800098ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800098f1  xorps   xmm0, xmm0
0x1800098f4  movups  [rsp+518h+var_308], xmm0
0x1800098fc  mov     qword ptr [rsp+518h+var_2F8], rdi
0x180009904  mov     qword ptr [rsp+518h+var_2F8+8], rdi
0x18000990c  lea     rcx, [rsp+518h+var_308]
0x180009914  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009919  nop
0x18000991a  lea     rdx, [rsp+518h+var_2E8]
0x180009922  lea     rcx, [rsp+518h+Pid]
0x18000992a  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000992f  mov     rbx, rax
0x180009932  lea     rax, [rsp+518h+var_308]
0x18000993a  cmp     rax, rbx
0x18000993d  jz      short loc_180009993
0x18000993f  mov     rdx, qword ptr [rsp+518h+var_2F8+8]
0x180009947  cmp     rdx, 7
0x18000994b  ja      loc_18000A5B5
0x180009951  mov     qword ptr [rsp+518h+var_2F8], rdi
0x180009959  mov     qword ptr [rsp+518h+var_2F8+8], 7
0x180009965  mov     word ptr [rsp+518h+var_308], di
0x18000996d  movups  xmm0, xmmword ptr [rbx]
0x180009970  movups  [rsp+518h+var_308], xmm0
0x180009978  movups  xmm1, xmmword ptr [rbx+10h]
0x18000997c  movups  [rsp+518h+var_2F8], xmm1
0x180009984  mov     [rbx+10h], rdi
0x180009988  mov     qword ptr [rbx+18h], 7
0x180009990  mov     [rbx], di
0x180009993  mov     rdx, [rsp+518h+var_2D0]
0x18000999b  cmp     rdx, 7
0x18000999f  ja      loc_18000A5CF
0x1800099a5  cmp     qword ptr [rsp+518h+var_2F8], 0
0x1800099ae  jnz     loc_18000A5E9
0x1800099b4  lea     rbx, [rsp+518h+packageFullName]
0x1800099bc  lea     rdx, [rsp+518h+var_2E8]
0x1800099c4  lea     rcx, [rsp+518h+Pid]
0x1800099cc  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x1800099d1  nop
0x1800099d2  mov     rsi, [rax]
0x1800099d5  lea     rcx, [rsp+518h+var_2A8]
0x1800099dd  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800099e2  nop
0x1800099e3  xorps   xmm0, xmm0
0x1800099e6  movups  [rsp+518h+var_290], xmm0
0x1800099ee  mov     [rsp+518h+var_280], rdi
0x1800099f6  mov     [rsp+518h+var_278], rdi
0x1800099fe  lea     rcx, [rsp+518h+var_290]
0x180009a06  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009a0b  nop
0x180009a0c  movups  [rsp+518h+var_270], xmm0
0x180009a14  mov     [rsp+518h+var_260], rdi
0x180009a1c  mov     [rsp+518h+var_258], rdi
0x180009a24  lea     rcx, [rsp+518h+var_270]
0x180009a2c  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009a31  nop
0x180009a32  test    rsi, rsi
0x180009a35  jnz     loc_18000A25D
0x180009a3b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180009a42  test    rbx, rbx
0x180009a45  jz      short loc_180009AC1
0x180009a47  mov     [rsp+518h+packageFamilyNameLength], edi
0x180009a4b  mov     r8, rsi
0x180009a4e  xchg    ax, ax
0x180009a50  inc     r8
0x180009a53  cmp     word ptr [rbx+r8*2], 0
0x180009a59  jnz     short loc_180009A50
0x180009a5b  mov     rdx, rbx
0x180009a5e  lea     rcx, [rsp+518h+var_270]
0x180009a66  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009a6b  mov     [rsp+518h+packageFamilyNameLength], 80h
0x180009a73  lea     r8, [rsp+518h+packageFamilyName]; packageFamilyName
0x180009a7b  lea     rdx, [rsp+518h+packageFamilyNameLength]; packageFamilyNameLength
0x180009a80  mov     rcx, rbx; packageFullName
0x180009a83  call    cs:__imp_PackageFamilyNameFromFullName
0x180009a89  mov     r8, rsi
0x180009a8c  test    eax, eax
0x180009a8e  jnz     loc_18000A180
0x180009a94  lea     rax, [rsp+518h+packageFamilyName]
0x180009a9c  nop     dword ptr [rax+00h]
0x180009aa0  inc     r8
0x180009aa3  cmp     word ptr [rax+r8*2], 0
0x180009aa9  jnz     short loc_180009AA0
0x180009aab  lea     rdx, [rsp+518h+packageFamilyName]
0x180009ab3  lea     rcx, [rsp+518h+var_290]
0x180009abb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180009ac0  nop
0x180009ac1  mov     rcx, [rsp+518h+var_2E8]; void *
0x180009ac9  test    rcx, rcx
0x180009acc  jz      short loc_180009AF9
0x180009ace  mov     rdx, [rsp+518h+var_2D8]
0x180009ad6  sub     rdx, rcx; unsigned __int64
0x180009ad9  mov     [rsp+518h+Src], rdx
0x180009ae1  mov     qword ptr [rsp+518h+packageFamilyNameLength], rcx
0x180009ae6  cmp     rdx, 1000h
0x180009aed  jnb     loc_18000A608
0x180009af3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009af8  nop
0x180009af9  mov     rdx, qword ptr [rsp+518h+var_2F8+8]
0x180009b01  cmp     rdx, 7
0x180009b05  ja      loc_18000A62C
0x180009b0b  lea     rcx, [rsp+518h+Buf2]
0x180009b13  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180009b18  mov     rax, [rsp+518h+var_2A8]
0x180009b20  mov     [rsp+518h+Buf2], rax
0x180009b28  mov     rax, [rsp+518h+var_2A8+8]
0x180009b30  mov     [rsp+518h+Buf2+8], rax
0x180009b38  mov     rax, [rsp+518h+var_298]
0x180009b40  mov     [rsp+518h+var_358], rax
0x180009b48  xorps   xmm0, xmm0
0x180009b4b  movdqa  xmmword ptr [rsp+518h+var_2A8], xmm0
0x180009b54  mov     [rsp+518h+var_298], rdi
0x180009b5c  mov     rdx, [rsp+518h+var_338]
0x180009b64  cmp     rdx, 7
0x180009b68  ja      loc_18000A646
0x180009b6e  mov     rax, qword ptr [rsp+518h+var_290]
0x180009b76  mov     [rsp+518h+var_350], rax
0x180009b7e  mov     rax, qword ptr [rsp+518h+var_290+8]
0x180009b86  mov     [rsp+518h+var_350+8], rax
0x180009b8e  mov     rax, [rsp+518h+var_280]
0x180009b96  mov     qword ptr [rsp+518h+var_340], rax
0x180009b9e  mov     rax, [rsp+518h+var_278]
0x180009ba6  mov     [rsp+518h+var_338], rax
0x180009bae  mov     [rsp+518h+var_280], rdi
0x180009bb6  mov     edx, 7
0x180009bbb  mov     [rsp+518h+var_278], rdx
0x180009bc3  mov     word ptr [rsp+518h+var_290], di
0x180009bcb  mov     rax, [rsp+518h+var_318]
0x180009bd3  cmp     rax, rdx
0x180009bd6  ja      loc_18000A660
0x180009bdc  mov     rax, qword ptr [rsp+518h+var_270]
0x180009be4  mov     qword ptr [rsp+518h+var_330], rax
0x180009bec  mov     rax, qword ptr [rsp+518h+var_270+8]
0x180009bf4  mov     qword ptr [rsp+518h+var_330+8], rax
0x180009bfc  mov     rax, [rsp+518h+var_260]
0x180009c04  mov     [rsp+518h+var_320], rax
0x180009c0c  mov     rax, [rsp+518h+var_258]
0x180009c14  mov     [rsp+518h+var_318], rax
0x180009c1c  mov     [rsp+518h+var_260], rdi
0x180009c24  mov     [rsp+518h+var_258], 7
0x180009c30  mov     word ptr [rsp+518h+var_270], di
0x180009c38  cmp     rdx, 7
0x180009c3c  ja      loc_18000A682
0x180009c42  mov     [rsp+518h+var_280], rdi
0x180009c4a  mov     [rsp+518h+var_278], 7
0x180009c56  mov     word ptr [rsp+518h+var_290], di
0x180009c5e  mov     rcx, [rsp+518h+var_2A8]; void *
0x180009c66  test    rcx, rcx
0x180009c69  jz      short loc_180009C95
0x180009c6b  mov     rdx, [rsp+518h+var_298]
0x180009c73  sub     rdx, rcx; unsigned __int64
0x180009c76  mov     qword ptr [rsp+518h+packageFamilyNameLength], rdx
0x180009c7b  mov     [rsp+518h+Src], rcx
0x180009c83  cmp     rdx, 1000h
0x180009c8a  jnb     loc_18000A69C
0x180009c90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9c  test    byte ptr [rcx+1Ch], 8
0x180009ca0  jz      short loc_180009CAC
0x180009ca2  cmp     byte ptr [rcx+19h], 4
0x180009ca6  jnb     loc_18000A1A0
0x180009cac  mov     [rsp+518h+lpString2], r12; struct CBroker::_CustomData *
0x180009cb1  mov     r9, r15; struct _CSebiSystemEventCreationParameter *
0x180009cb4  lea     r8, [rsp+518h+Buf2]; struct Broker::ApplicationIdentity *
0x180009cbc  lea     rdx, [rsp+518h+Src]; retstr
0x180009cc4  mov     rcx, [rsp+518h+var_4A8]; this
0x180009cc9  call    ?CreateEventW@SebBroker@CBroker@@QEAA?AU_GUID@@AEBUApplicationIdentity@Broker@@AEBU_CSebiSystemEventCreationParameter@@PEBU_CustomData@2@K@Z; CBroker::SebBroker::CreateEventW(Broker::ApplicationIdentity const &,_CSebiSystemEventCreationParameter const &,CBroker::_CustomData const *,ulong)
0x180009cce  movups  xmm0, xmmword ptr [rax]
0x180009cd1  movups  [rsp+518h+Buf1], xmm0
0x180009cd9  mov     rbx, qword ptr [rsp+518h+Buf1]
0x180009ce1  mov     [r14], rbx
0x180009ce4  mov     r15, rbx
0x180009ce7  shr     r15, 20h
0x180009ceb  mov     ecx, 28h ; '('; Size
0x180009cf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cf5  xorps   xmm0, xmm0
0x180009cf8  xor     ecx, ecx
0x180009cfa  movups  xmmword ptr [rax], xmm0
0x180009cfd  movups  xmmword ptr [rax+10h], xmm0
0x180009d01  mov     [rax+20h], rcx
0x180009d05  mov     rcx, rax; this
0x180009d08  call    ??0EventContext@@QEAA@XZ; EventContext::EventContext(void)
0x180009d0d  mov     r14, rax
0x180009d10  test    rax, rax
0x180009d13  jnz     loc_180009DBB
0x180009d19  movups  [rsp+518h+var_480], xmm0
0x180009d21  lea     rax, aBadAllocation; "bad allocation"
0x180009d28  mov     qword ptr [rsp+518h+var_480], rax
0x180009d30  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009d37  mov     [rsp+518h+pExceptionObject], rax
0x180009d3f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009d46  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x180009d4e  call    _CxxThrowException_0
0x180009d54  lea     rsi, [rbx+8]
0x180009d58  mov     rcx, rsi
0x180009d5b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009d61  call    cs:__imp_GetCurrentThreadId
0x180009d67  movzx   ebx, byte ptr [rbx]
0x180009d6a  mov     rcx, rsi
0x180009d6d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009d73  test    bl, bl
0x180009d75  jz      loc_18000987E
0x180009d7b  mov     rax, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180009d82  test    rax, rax
0x180009d85  jz      short loc_180009D8B
0x180009d87  lock inc dword ptr [rax+8]
0x180009d8b  movups  xmm0, cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180009d92  jmp     loc_180009881
0x180009d97  cmp     byte ptr [rcx+19h], 4
0x180009d9b  jb      loc_18000978E
0x180009da1  mov     edx, 0Fh
0x180009da6  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
  ... truncated ...
```
