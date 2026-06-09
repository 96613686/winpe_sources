# _SebiEnumerateEventsByType

- ea: `0x18000cc40`
- end: `0x18000da2e`
- name: `_SebiEnumerateEventsByType`
- size: `3566`
- prototype: `__int64 __fastcall(__int64, WCHAR *, int, int, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000b168`
- `0x18000b180`
- `0x18000bbc0`
- `0x18000beb4`
- `0x18000cc40`
- `0x18000da40`
- `0x18000dc40`
- `0x18001732c`
- `0x180019130`
- `0x1800195e0`
- `0x18001ab64`
- `0x18001cf50`
- `0x18001d364`
- `0x18001d9ac`
- `0x18001e0d8`
- `0x18001e3bc`
- `0x18002244c`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d455`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d41c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d41c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d037`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000d037`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000cd72`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000cefa`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000cd72`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000cefa`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000cdbd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000cf48`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000cdbd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000cf48`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d4b3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d4b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cd1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cea0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cd1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cff7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cff7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000d218`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000d218`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SebiEnumerateEventsByType(__int64 a1, WCHAR *a2, int a3, int a4, _DWORD *a5, _QWORD *a6)
{
  const WCHAR *v7; // rdi
  int v8; // r8d
  DWORD LastError; // eax
  DWORD v10; // eax
  int v11; // r12d
  struct _GENERIC_MAPPING v12; // xmm6
  __int64 PackageFullName; // rsi
  void *v14; // rsi
  __int128 v15; // xmm0
  __int64 v16; // r8
  LONG v17; // eax
  __int64 v18; // r8
  void *v19; // rcx
  PSECURITY_DESCRIPTOR v20; // rdx
  __int64 v21; // rdi
  PSECURITY_DESCRIPTOR v22; // rcx
  void *v23; // rdx
  volatile signed __int32 *v24; // xmm6_8
  _DWORD *v25; // r14
  __int64 v26; // rdi
  void *v27; // rsi
  __int64 v28; // rcx
  void *v29; // rax
  DWORD LengthSid; // eax
  DWORD v31; // eax
  unsigned int v33; // [rsp+50h] [rbp-3E8h]
  DWORD AccessMask; // [rsp+58h] [rbp-3E0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-3D8h] BYREF
  WINBOOL AccessStatus; // [rsp+68h] [rbp-3D0h] BYREF
  DWORD GrantedAccess; // [rsp+6Ch] [rbp-3CCh] BYREF
  UINT32 packageFamilyNameLength; // [rsp+70h] [rbp-3C8h] BYREF
  DWORD PrivilegeSetLength; // [rsp+74h] [rbp-3C4h] BYREF
  void *v40; // [rsp+78h] [rbp-3C0h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp-3B8h] BYREF
  int v42; // [rsp+84h] [rbp-3B4h]
  int v43; // [rsp+88h] [rbp-3B0h]
  int v44; // [rsp+90h] [rbp-3A8h]
  int v45; // [rsp+94h] [rbp-3A4h]
  _DWORD *v46; // [rsp+98h] [rbp-3A0h]
  void *Src; // [rsp+A0h] [rbp-398h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-390h]
  __int64 v49; // [rsp+B0h] [rbp-388h]
  char v50[8]; // [rsp+B8h] [rbp-380h] BYREF
  HANDLE ClientToken; // [rsp+C0h] [rbp-378h]
  _QWORD *v52; // [rsp+C8h] [rbp-370h]
  __int64 v53; // [rsp+D0h] [rbp-368h] BYREF
  __int128 v54; // [rsp+D8h] [rbp-360h]
  void **v55; // [rsp+F8h] [rbp-340h] BYREF
  __int128 v56; // [rsp+100h] [rbp-338h]
  int v57; // [rsp+110h] [rbp-328h]
  void **v58; // [rsp+118h] [rbp-320h] BYREF
  __int128 v59; // [rsp+120h] [rbp-318h]
  int v60; // [rsp+130h] [rbp-308h]
  _QWORD v61[3]; // [rsp+138h] [rbp-300h] BYREF
  int v62; // [rsp+150h] [rbp-2E8h]
  DWORD v63; // [rsp+158h] [rbp-2E0h]
  void **pExceptionObject; // [rsp+160h] [rbp-2D8h] BYREF
  __int128 v65; // [rsp+168h] [rbp-2D0h]
  int v66; // [rsp+178h] [rbp-2C0h]
  DWORD v67; // [rsp+180h] [rbp-2B8h]
  _QWORD v68[3]; // [rsp+188h] [rbp-2B0h] BYREF
  int v69; // [rsp+1A0h] [rbp-298h]
  DWORD v70; // [rsp+1A8h] [rbp-290h]
  void **v71; // [rsp+1B0h] [rbp-288h] BYREF
  __int128 v72; // [rsp+1B8h] [rbp-280h]
  int v73; // [rsp+1C8h] [rbp-270h]
  DWORD v74; // [rsp+1D0h] [rbp-268h]
  _BYTE v75[40]; // [rsp+1D8h] [rbp-260h] BYREF
  _BYTE v76[40]; // [rsp+200h] [rbp-238h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+228h] [rbp-210h] BYREF
  void *v78; // [rsp+238h] [rbp-200h] BYREF
  __int128 v79; // [rsp+240h] [rbp-1F8h]
  unsigned __int64 v80; // [rsp+250h] [rbp-1E8h]
  DWORD v81; // [rsp+258h] [rbp-1E0h]
  __int128 v82; // [rsp+260h] [rbp-1D8h] BYREF
  __m128i si128; // [rsp+270h] [rbp-1C8h]
  void *v84[2]; // [rsp+280h] [rbp-1B8h] BYREF
  __int64 v85; // [rsp+290h] [rbp-1A8h]
  __int128 v86; // [rsp+298h] [rbp-1A0h] BYREF
  __int64 v87; // [rsp+2A8h] [rbp-190h]
  unsigned __int64 v88; // [rsp+2B0h] [rbp-188h]
  __int128 v89; // [rsp+2B8h] [rbp-180h] BYREF
  __int64 v90; // [rsp+2C8h] [rbp-170h]
  unsigned __int64 v91; // [rsp+2D0h] [rbp-168h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+2E0h] [rbp-158h] BYREF

  v7 = a2;
  v40 = a2;
  v43 = a3;
  v46 = a5;
  v52 = a6;
  std::vector<_GUID>::vector<_GUID>(&Src);
  *a5 = 0;
  v33 = 0;
  packageFamilyNameLength = 0;
  v42 = 0;
  if ( v8 >= 76 )
  {
    v33 = 87;
  }
  else
  {
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v50);
    v45 = 0;
    v44 = 0;
    AccessMask = 0x80000000;
    SecurityDescriptorSize = 0;
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;RC;;;S-1-5-80-5077831-2848399648-2133836502-3232794944-2981604943)(A;;"
             "RC;;;S-1-5-80-2226967063-754826275-1661302337-2802353169-2369347280)(A;;RC;;;S-1-5-80-2995899262-2131376444"
             "-1860748247-2210972999-1941275431)(A;;RC;;;S-1-5-80-2636612206-2079418197-1004231589-1812192203-4197254245)",
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)&v78);
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v81);
      std::exception::exception((std::exception *)v61, (const struct std::exception *)&v78);
      v62 = v80;
      v61[0] = &Broker::Win32Error::`vftable';
      v63 = v81;
      throw (Broker::Win32Error *)v61;
    }
    GrantedAccess = 0;
    AccessStatus = 0;
    PrivilegeSetLength = 256;
    GenericMapping.GenericRead = 0x20000;
    GenericMapping.GenericWrite = 0x20000;
    GenericMapping.GenericExecute = 0x20000;
    GenericMapping.GenericAll = 2031616;
    MapGenericMask(&AccessMask, &GenericMapping);
    if ( !AccessCheck(
            SecurityDescriptor,
            ClientToken,
            AccessMask,
            &GenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)&v78);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v81);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v75);
      throw (Broker::Win32Error *)v75;
    }
    if ( !AccessStatus )
    {
      v79 = 0;
      LODWORD(v80) = 1;
      v78 = &Broker::Win32Error::`vftable';
      LastError = GetLastError();
      v81 = LastError;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
      v65 = 0;
      v66 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v67 = GetLastError();
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    if ( GrantedAccess != AccessMask )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids,
          GrantedAccess);
      v56 = 0;
      v57 = 5;
      v55 = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)&v55;
    }
    LocalFree(SecurityDescriptor);
    v44 = 1;
    packageFamilyNameLength = 1;
    AccessMask = 0x80000000;
    PrivilegeSetLength = 0;
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;RC;;;S-1-5-80-5077831-2848399648-2133836502-3232794944-2981604943)(A;;"
             "RC;;;S-1-5-80-2226967063-754826275-1661302337-2802353169-2369347280)(A;;RC;;;S-1-5-80-2995899262-2131376444"
             "-1860748247-2210972999-1941275431)(A;;RC;;;S-1-5-11)",
            1u,
            &SecurityDescriptor,
            &PrivilegeSetLength) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)&v78);
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v81);
      std::exception::exception((std::exception *)v68, (const struct std::exception *)&v78);
      v69 = v80;
      v68[0] = &Broker::Win32Error::`vftable';
      v70 = v81;
      throw (Broker::Win32Error *)v68;
    }
    AccessStatus = 0;
    GrantedAccess = 0;
    SecurityDescriptorSize = 256;
    GenericMapping.GenericRead = 0x20000;
    GenericMapping.GenericWrite = 0x20000;
    GenericMapping.GenericExecute = 0x20000;
    GenericMapping.GenericAll = 2031616;
    MapGenericMask(&AccessMask, &GenericMapping);
    if ( !AccessCheck(
            SecurityDescriptor,
            ClientToken,
            AccessMask,
            &GenericMapping,
            &PrivilegeSet,
            &SecurityDescriptorSize,
            (LPDWORD)&AccessStatus,
            (LPBOOL)&GrantedAccess) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)&v78);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v81);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v76);
      throw (Broker::Win32Error *)v76;
    }
    if ( !GrantedAccess )
    {
      v79 = 0;
      LODWORD(v80) = 1;
      v78 = &Broker::Win32Error::`vftable';
      v10 = GetLastError();
      v81 = v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v10);
      v72 = 0;
      v73 = 1;
      v71 = &Broker::Win32Error::`vftable';
      v74 = GetLastError();
      throw (Broker::Win32Error *)&v71;
    }
    if ( AccessStatus != AccessMask )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids,
          (unsigned int)AccessStatus);
      v59 = 0;
      v60 = 5;
      v58 = &Broker::AccessDenied::`vftable';
      throw (Broker::AccessDenied *)&v58;
    }
    LocalFree(SecurityDescriptor);
    v42 = 1;
    if ( CompareStringEx(&LocaleName, 1u, L"*.*", -1, v7, -1, 0, 0, 0) == 2 )
    {
      v45 = 1;
      v7 = 0;
      v40 = 0;
    }
    v11 = (int)Broker::SebBroker::Instance;
    if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
    {
      if ( *(&Broker::SebBroker::Instance + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
        v11 = (int)Broker::SebBroker::Instance;
      }
      v12 = *(struct _GENERIC_MAPPING *)&Broker::SebBroker::Instance;
    }
    else
    {
      v12 = 0;
      v11 = 0;
    }
    GenericMapping = v12;
    v82 = 0;
    si128 = 0;
    std::wstring::_Construct_empty(&v82);
    PackageFullName = Broker::RpcClientToken::GetPackageFullName(v50, &v78);
    if ( &v82 != (__int128 *)PackageFullName )
    {
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v82, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v82) = 0;
      v82 = *(_OWORD *)PackageFullName;
      si128 = *(__m128i *)(PackageFullName + 16);
      *(_QWORD *)(PackageFullName + 16) = 0;
      *(_QWORD *)(PackageFullName + 24) = 7;
      *(_WORD *)PackageFullName = 0;
    }
    if ( v80 > 7 )
      std::_Deallocate<16>(v78, 2 * v80 + 2);
    if ( !a4 )
    {
      if ( si128.m128i_i64[0] )
      {
        v7 = (const WCHAR *)&v82;
        if ( si128.m128i_i64[1] > 7uLL )
          v7 = (const WCHAR *)v82;
      }
    }
    v14 = *(void **)Broker::RpcClientToken::GetUserSid(v50, &v78);
    std::vector<_GUID>::vector<_GUID>(v84);
    v15 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 0;
    *(double *)&v15 = std::wstring::_Construct_empty(&v86);
    v89 = v15;
    v90 = 0;
    v91 = 0;
    std::wstring::_Construct_empty(&v89);
    if ( v14 )
    {
      LengthSid = GetLengthSid(v14);
      std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(v84, v84[0], v14, LengthSid);
    }
    if ( v7 )
    {
      packageFamilyNameLength = 0;
      v16 = -1;
      do
        ++v16;
      while ( v7[v16] );
      std::wstring::_Assign<unsigned short>(&v89, v7);
      packageFamilyNameLength = 128;
      v17 = PackageFamilyNameFromFullName(v7, &packageFamilyNameLength, (PWSTR)&PrivilegeSet);
      v18 = -1;
      if ( v17 )
      {
        do
          ++v18;
        while ( v7[v18] );
        std::wstring::_Assign<unsigned short>(&v86, v7);
      }
      else
      {
        do
          ++v18;
        while ( *((_WORD *)&PrivilegeSet.PrivilegeCount + v18) );
        std::wstring::_Assign<unsigned short>(&v86, &PrivilegeSet);
      }
    }
    v19 = v78;
    if ( v78 )
    {
      v20 = (PSECURITY_DESCRIPTOR)(*((_QWORD *)&v79 + 1) - (_QWORD)v78);
      SecurityDescriptor = (PSECURITY_DESCRIPTOR)(*((_QWORD *)&v79 + 1) - (_QWORD)v78);
      v40 = v78;
      if ( *((_QWORD *)&v79 + 1) - (_QWORD)v78 >= 0x1000u )
      {
        std::_Adjust_manually_vector_aligned(&v40, (unsigned __int64 *)&SecurityDescriptor);
        v19 = v40;
        v20 = SecurityDescriptor;
      }
      operator delete(v19, (unsigned __int64)v20);
    }
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v82, 2 * si128.m128i_i64[1] + 2);
    v21 = Broker::SebBroker::EnumerateEvents(v11, (unsigned int)&v53, (unsigned int)v84, a3, v45, v44);
    if ( &Src != (void **)v21 )
    {
      if ( Src )
        std::_Deallocate<16>(Src, (v49 - (_QWORD)Src) & 0xFFFFFFFFFFFFFFF0uLL);
      Src = *(void **)v21;
      v48 = *(_QWORD *)(v21 + 8);
      v49 = *(_QWORD *)(v21 + 16);
      *(_QWORD *)v21 = 0;
      *(_QWORD *)(v21 + 8) = 0;
      *(_QWORD *)(v21 + 16) = 0;
    }
    if ( v53 )
    {
      std::_Deallocate<16>(v53, (*((_QWORD *)&v54 + 1) - v53) & 0xFFFFFFFFFFFFFFF0uLL);
      v53 = 0;
      v54 = 0;
    }
    if ( v91 > 7 )
      std::_Deallocate<16>(v89, 2 * v91 + 2);
    v90 = 0;
    v91 = 7;
    LOWORD(v89) = 0;
    if ( v88 > 7 )
      std::_Deallocate<16>(v86, 2 * v88 + 2);
    v87 = 0;
    v88 = 7;
    LOWORD(v86) = 0;
    v22 = v84[0];
    if ( v84[0] )
    {
      v23 = (void *)(v85 - (unsigned __int64)v84[0]);
      v40 = (void *)(v85 - (unsigned __int64)v84[0]);
      SecurityDescriptor = v84[0];
      if ( v85 - (unsigned __int64)v84[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&SecurityDescriptor, (unsigned __int64 *)&v40);
        v23 = v40;
        v22 = SecurityDescriptor;
      }
      operator delete(v22, (unsigned __int64)v23);
      *(_OWORD *)v84 = 0;
      v85 = 0;
    }
    v24 = (volatile signed __int32 *)_mm_srli_si128((__m128i)v12, 8).m128i_u64[0];
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    if ( !CloseHandle(ClientToken)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v31);
    }
    v25 = v46;
    v26 = v48;
    v27 = Src;
    v28 = (unsigned int)((v48 - (__int64)Src) >> 4);
    *v46 = v28;
    v29 = malloc(16 * v28);
    *v52 = v29;
    if ( v29 )
    {
      memmove_0(v29, v27, v26 - (_QWORD)v27);
    }
    else
    {
      *v25 = 0;
      v33 = 14;
    }
  }
  if ( Src )
    std::_Deallocate<16>(Src, (v49 - (_QWORD)Src) & 0xFFFFFFFFFFFFFFF0uLL);
  return v33;
}

```

## disassembly

```asm
0x18000cc40  mov     [rsp+arg_18], r9d
0x18000cc45  push    rbx
0x18000cc46  push    rsi
0x18000cc47  push    rdi
0x18000cc48  push    r12
0x18000cc4a  push    r13
0x18000cc4c  push    r14
0x18000cc4e  push    r15
0x18000cc50  sub     rsp, 400h
0x18000cc57  movaps  [rsp+438h+var_48], xmm6
0x18000cc5f  mov     rax, cs:__security_cookie
0x18000cc66  xor     rax, rsp
0x18000cc69  mov     [rsp+438h+var_58], rax
0x18000cc71  mov     r13d, r8d
0x18000cc74  mov     rdi, rdx
0x18000cc77  mov     [rsp+438h+var_3C0], rdx
0x18000cc7c  mov     [rsp+438h+var_3B0], r8d
0x18000cc84  mov     r15, [rsp+438h+arg_20]
0x18000cc8c  mov     [rsp+438h+var_3A0], r15
0x18000cc94  mov     rax, [rsp+438h+arg_28]
0x18000cc9c  mov     [rsp+438h+var_370], rax
0x18000cca4  xor     ebx, ebx
0x18000cca6  lea     rcx, [rsp+438h+Src]
0x18000ccae  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000ccb3  nop
0x18000ccb4  mov     [r15], ebx
0x18000ccb7  mov     [rsp+438h+var_3E8], ebx
0x18000ccbb  mov     [rsp+438h+packageFamilyNameLength], ebx
0x18000ccbf  mov     [rsp+438h+var_3B4], ebx
0x18000ccc6  cmp     r8d, 4Ch ; 'L'
0x18000ccca  jge     loc_18000D5CE
0x18000ccd0  lea     rcx, [rsp+438h+var_380]; this
0x18000ccd8  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18000ccdd  nop
0x18000ccde  mov     [rsp+438h+var_3A4], ebx
0x18000cce5  mov     [rsp+438h+var_3A8], ebx
0x18000ccec  mov     [rsp+438h+AccessMask], 80000000h
0x18000ccf4  mov     [rsp+438h+SecurityDescriptorSize], ebx
0x18000ccfb  mov     [rsp+438h+SecurityDescriptor], rbx
0x18000cd00  lea     r9, [rsp+438h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000cd08  lea     r8, [rsp+438h+SecurityDescriptor]; SecurityDescriptor
0x18000cd0d  mov     esi, 1
0x18000cd12  mov     edx, esi; StringSDRevision
0x18000cd14  lea     rcx, aOSygSydARcSyAR_1; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;R"...
0x18000cd1b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000cd21  test    eax, eax
0x18000cd23  jz      loc_18000D629
0x18000cd29  mov     [rsp+438h+var_3CC], ebx
0x18000cd2d  mov     [rsp+438h+var_3D0], ebx
0x18000cd31  mov     [rsp+438h+var_3C4], 100h
0x18000cd39  mov     [rsp+438h+GenericMapping.GenericRead], 20000h
0x18000cd44  mov     [rsp+438h+GenericMapping.GenericWrite], 20000h
0x18000cd4f  mov     [rsp+438h+GenericMapping.GenericExecute], 20000h
0x18000cd5a  mov     [rsp+438h+GenericMapping.GenericAll], 1F0000h
0x18000cd65  lea     rdx, [rsp+438h+GenericMapping]; GenericMapping
0x18000cd6d  lea     rcx, [rsp+438h+AccessMask]; AccessMask
0x18000cd72  call    cs:__imp_MapGenericMask
0x18000cd78  lea     rax, [rsp+438h+var_3D0]
0x18000cd7d  mov     [rsp+438h+AccessStatus], rax; AccessStatus
0x18000cd82  lea     rax, [rsp+438h+var_3CC]
0x18000cd87  mov     [rsp+438h+GrantedAccess], rax; GrantedAccess
0x18000cd8c  lea     rax, [rsp+438h+var_3C4]
0x18000cd91  mov     [rsp+438h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000cd96  lea     rax, [rsp+438h+var_158]
0x18000cd9e  mov     [rsp+438h+PrivilegeSet], rax; PrivilegeSet
0x18000cda3  lea     r9, [rsp+438h+GenericMapping]; GenericMapping
0x18000cdab  mov     r8d, [rsp+438h+AccessMask]; DesiredAccess
0x18000cdb0  mov     rdx, [rsp+438h+ClientToken]; ClientToken
0x18000cdb8  mov     rcx, [rsp+438h+SecurityDescriptor]; pSecurityDescriptor
0x18000cdbd  call    cs:__imp_AccessCheck
0x18000cdc3  test    eax, eax
0x18000cdc5  jz      loc_18000D6BF
0x18000cdcb  cmp     [rsp+438h+var_3D0], ebx
0x18000cdcf  jnz     loc_18000CE56
0x18000cdd5  xorps   xmm0, xmm0
0x18000cdd8  movups  [rsp+438h+var_1F8], xmm0
0x18000cde0  mov     dword ptr [rsp+438h+var_1E8], esi
0x18000cde7  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000cdee  mov     [rsp+438h+var_200], rbx
0x18000cdf6  call    cs:__imp_GetLastError
0x18000cdfc  mov     [rsp+438h+var_1E0], eax
0x18000ce03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce0a  test    byte ptr [rcx+1Ch], 8
0x18000ce0e  jz      short loc_18000CE1A
0x18000ce10  cmp     byte ptr [rcx+19h], 2
0x18000ce14  jnb     loc_18000D5DB
0x18000ce1a  xorps   xmm0, xmm0
0x18000ce1d  movups  [rsp+438h+var_2D0], xmm0
0x18000ce25  mov     [rsp+438h+var_2C0], esi
0x18000ce2c  mov     [rsp+438h+pExceptionObject], rbx
0x18000ce34  call    cs:__imp_GetLastError
0x18000ce3a  mov     [rsp+438h+var_2B8], eax
0x18000ce41  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ce48  lea     rcx, [rsp+438h+pExceptionObject]; pExceptionObject
0x18000ce50  call    _CxxThrowException_0
0x18000ce56  mov     r9d, [rsp+438h+var_3CC]
0x18000ce5b  cmp     r9d, [rsp+438h+AccessMask]
0x18000ce60  jnz     loc_18000D71F
0x18000ce66  mov     rcx, [rsp+438h+SecurityDescriptor]; hMem
0x18000ce6b  call    cs:__imp_LocalFree
0x18000ce71  mov     [rsp+438h+var_3A8], esi
0x18000ce78  mov     [rsp+438h+packageFamilyNameLength], esi
0x18000ce7c  mov     [rsp+438h+AccessMask], 80000000h
0x18000ce84  mov     [rsp+438h+var_3C4], ebx
0x18000ce88  mov     [rsp+438h+SecurityDescriptor], rbx
0x18000ce8d  lea     r9, [rsp+438h+var_3C4]; SecurityDescriptorSize
0x18000ce92  lea     r8, [rsp+438h+SecurityDescriptor]; SecurityDescriptor
0x18000ce97  mov     edx, esi; StringSDRevision
0x18000ce99  lea     rcx, aOSygSydARcSyAR_0; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;R"...
0x18000cea0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000cea6  test    eax, eax
0x18000cea8  jz      loc_18000D79A
0x18000ceae  mov     [rsp+438h+var_3D0], ebx
0x18000ceb2  mov     [rsp+438h+var_3CC], ebx
0x18000ceb6  mov     [rsp+438h+SecurityDescriptorSize], 100h
0x18000cec1  mov     [rsp+438h+GenericMapping.GenericRead], 20000h
0x18000cecc  mov     [rsp+438h+GenericMapping.GenericWrite], 20000h
0x18000ced7  mov     [rsp+438h+GenericMapping.GenericExecute], 20000h
0x18000cee2  mov     [rsp+438h+GenericMapping.GenericAll], 1F0000h
0x18000ceed  lea     rdx, [rsp+438h+GenericMapping]; GenericMapping
0x18000cef5  lea     rcx, [rsp+438h+AccessMask]; AccessMask
0x18000cefa  call    cs:__imp_MapGenericMask
0x18000cf00  lea     rax, [rsp+438h+var_3CC]
0x18000cf05  mov     [rsp+438h+AccessStatus], rax; AccessStatus
0x18000cf0a  lea     rax, [rsp+438h+var_3D0]
0x18000cf0f  mov     [rsp+438h+GrantedAccess], rax; GrantedAccess
0x18000cf14  lea     rax, [rsp+438h+SecurityDescriptorSize]
0x18000cf1c  mov     [rsp+438h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000cf21  lea     rax, [rsp+438h+var_158]
0x18000cf29  mov     [rsp+438h+PrivilegeSet], rax; PrivilegeSet
0x18000cf2e  lea     r9, [rsp+438h+GenericMapping]; GenericMapping
0x18000cf36  mov     r8d, [rsp+438h+AccessMask]; DesiredAccess
0x18000cf3b  mov     rdx, [rsp+438h+ClientToken]; ClientToken
0x18000cf43  mov     rcx, [rsp+438h+SecurityDescriptor]; pSecurityDescriptor
0x18000cf48  call    cs:__imp_AccessCheck
0x18000cf4e  test    eax, eax
0x18000cf50  jz      loc_18000D830
0x18000cf56  cmp     [rsp+438h+var_3CC], 0
0x18000cf5b  jnz     loc_18000CFE2
0x18000cf61  xorps   xmm0, xmm0
0x18000cf64  movups  [rsp+438h+var_1F8], xmm0
0x18000cf6c  mov     dword ptr [rsp+438h+var_1E8], esi
0x18000cf73  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000cf7a  mov     [rsp+438h+var_200], rbx
0x18000cf82  call    cs:__imp_GetLastError
0x18000cf88  mov     [rsp+438h+var_1E0], eax
0x18000cf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf96  test    byte ptr [rcx+1Ch], 8
0x18000cf9a  jz      short loc_18000CFA6
0x18000cf9c  cmp     byte ptr [rcx+19h], 2
0x18000cfa0  jnb     loc_18000D5F8
0x18000cfa6  xorps   xmm0, xmm0
0x18000cfa9  movups  [rsp+438h+var_280], xmm0
0x18000cfb1  mov     [rsp+438h+var_270], esi
0x18000cfb8  mov     [rsp+438h+var_288], rbx
0x18000cfc0  call    cs:__imp_GetLastError
0x18000cfc6  mov     [rsp+438h+var_268], eax
0x18000cfcd  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000cfd4  lea     rcx, [rsp+438h+var_288]; pExceptionObject
0x18000cfdc  call    _CxxThrowException_0
0x18000cfe2  mov     r9d, [rsp+438h+var_3D0]
0x18000cfe7  cmp     r9d, [rsp+438h+AccessMask]
0x18000cfec  jnz     loc_18000D890
0x18000cff2  mov     rcx, [rsp+438h+SecurityDescriptor]; hMem
0x18000cff7  call    cs:__imp_LocalFree
0x18000cffd  mov     [rsp+438h+var_3B4], esi
0x18000d004  mov     [rsp+438h+lParam], rbx; lParam
0x18000d009  mov     [rsp+438h+AccessStatus], rbx; lpReserved
0x18000d00e  mov     [rsp+438h+GrantedAccess], rbx; lpVersionInformation
0x18000d013  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000d01a  mov     dword ptr [rsp+438h+PrivilegeSetLength], r14d; cchCount2
0x18000d01f  mov     [rsp+438h+PrivilegeSet], rdi; lpString2
0x18000d024  mov     r9d, r14d; cchCount1
0x18000d027  lea     r8, String1; "*.*"
0x18000d02e  mov     edx, esi; dwCmpFlags
0x18000d030  lea     rcx, LocaleName; lpLocaleName
0x18000d037  call    cs:__imp_CompareStringEx
0x18000d03d  cmp     eax, 2
0x18000d040  jz      loc_18000D615
0x18000d046  cmp     [rsp+438h+arg_18], 0
0x18000d04e  jnz     loc_18000D914
0x18000d054  xor     r15b, r15b
0x18000d057  mov     r12, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000d05e  test    r12, r12
0x18000d061  jz      loc_18000D4A5
0x18000d067  cmp     byte ptr [r12], 0
0x18000d06c  jz      loc_18000D4A5
0x18000d072  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000d079  test    rax, rax
0x18000d07c  jz      short loc_18000D089
0x18000d07e  lock inc dword ptr [rax+8]
0x18000d082  mov     r12, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000d089  movups  xmm6, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000d090  movdqu  xmmword ptr [rsp+438h+GenericMapping.GenericRead], xmm6
0x18000d099  xorps   xmm0, xmm0
0x18000d09c  movups  [rsp+438h+var_1D8], xmm0
0x18000d0a4  xorps   xmm1, xmm1
0x18000d0a7  movdqu  [rsp+438h+var_1C8], xmm1
0x18000d0b0  lea     rcx, [rsp+438h+var_1D8]
0x18000d0b8  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000d0bd  nop
0x18000d0be  lea     rdx, [rsp+438h+var_200]
0x18000d0c6  lea     rcx, [rsp+438h+var_380]
0x18000d0ce  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000d0d3  mov     rsi, rax
0x18000d0d6  lea     rax, [rsp+438h+var_1D8]
0x18000d0de  cmp     rax, rsi
0x18000d0e1  jz      short loc_18000D134
0x18000d0e3  mov     rdx, qword ptr [rsp+438h+var_1C8+8]
0x18000d0eb  cmp     rdx, 7
0x18000d0ef  ja      loc_18000D92B
0x18000d0f5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000d0fd  movdqu  [rsp+438h+var_1C8], xmm0
0x18000d106  mov     word ptr [rsp+438h+var_1D8], bx
0x18000d10e  movups  xmm0, xmmword ptr [rsi]
0x18000d111  movups  [rsp+438h+var_1D8], xmm0
0x18000d119  movups  xmm1, xmmword ptr [rsi+10h]
0x18000d11d  movups  [rsp+438h+var_1C8], xmm1
0x18000d125  mov     [rsi+10h], rbx
0x18000d129  mov     qword ptr [rsi+18h], 7
0x18000d131  mov     [rsi], bx
0x18000d134  mov     rdx, [rsp+438h+var_1E8]
0x18000d13c  cmp     rdx, 7
0x18000d140  ja      loc_18000D945
0x18000d146  test    r15b, r15b
0x18000d149  jnz     short loc_18000D15A
0x18000d14b  cmp     qword ptr [rsp+438h+var_1C8], 0
0x18000d154  jnz     loc_18000D95F
0x18000d15a  lea     rdx, [rsp+438h+var_200]
0x18000d162  lea     rcx, [rsp+438h+var_380]
0x18000d16a  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x18000d16f  nop
0x18000d170  mov     rsi, [rax]
0x18000d173  lea     rcx, [rsp+438h+var_1B8]
0x18000d17b  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000d180  nop
0x18000d181  xorps   xmm0, xmm0
0x18000d184  movups  [rsp+438h+var_1A0], xmm0
0x18000d18c  mov     [rsp+438h+var_190], rbx
0x18000d194  mov     [rsp+438h+var_188], rbx
0x18000d19c  lea     rcx, [rsp+438h+var_1A0]
0x18000d1a4  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000d1a9  nop
0x18000d1aa  movups  [rsp+438h+var_180], xmm0
0x18000d1b2  mov     [rsp+438h+var_170], rbx
0x18000d1ba  mov     [rsp+438h+var_168], rbx
0x18000d1c2  lea     rcx, [rsp+438h+var_180]
0x18000d1ca  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000d1cf  nop
0x18000d1d0  test    rsi, rsi
0x18000d1d3  jnz     loc_18000D4B0
0x18000d1d9  test    rdi, rdi
0x18000d1dc  jz      short loc_18000D252
0x18000d1de  mov     [rsp+438h+packageFamilyNameLength], ebx
0x18000d1e2  mov     r8, r14
0x18000d1e5  inc     r8
0x18000d1e8  cmp     word ptr [rdi+r8*2], 0
0x18000d1ee  jnz     short loc_18000D1E5
0x18000d1f0  mov     rdx, rdi
0x18000d1f3  lea     rcx, [rsp+438h+var_180]
0x18000d1fb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000d200  mov     [rsp+438h+packageFamilyNameLength], 80h
0x18000d208  lea     r8, [rsp+438h+var_158]; packageFamilyName
0x18000d210  lea     rdx, [rsp+438h+packageFamilyNameLength]; packageFamilyNameLength
0x18000d215  mov     rcx, rdi; packageFullName
0x18000d218  call    cs:__imp_PackageFamilyNameFromFullName
0x18000d21e  mov     r8, r14
0x18000d221  test    eax, eax
0x18000d223  jnz     loc_18000D485
0x18000d229  lea     rax, [rsp+438h+var_158]
0x18000d231  inc     r8
0x18000d234  cmp     word ptr [rax+r8*2], 0
0x18000d23a  jnz     short loc_18000D231
0x18000d23c  lea     rdx, [rsp+438h+var_158]
0x18000d244  lea     rcx, [rsp+438h+var_1A0]
0x18000d24c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000d251  nop
0x18000d252  mov     rcx, [rsp+438h+var_200]; void *
0x18000d25a  test    rcx, rcx
0x18000d25d  jz      short loc_18000D287
0x18000d25f  mov     rdx, qword ptr [rsp+438h+var_1F8+8]
0x18000d267  sub     rdx, rcx; unsigned __int64
0x18000d26a  mov     [rsp+438h+SecurityDescriptor], rdx
0x18000d26f  mov     [rsp+438h+var_3C0], rcx
0x18000d274  cmp     rdx, 1000h
0x18000d27b  jnb     loc_18000D97E
0x18000d281  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d286  nop
0x18000d287  mov     rdx, qword ptr [rsp+438h+var_1C8+8]
0x18000d28f  cmp     rdx, 7
0x18000d293  ja      loc_18000D99C
0x18000d299  mov     eax, [rsp+438h+var_3A8]
0x18000d2a0  mov     dword ptr [rsp+438h+PrivilegeSetLength], eax
0x18000d2a4  mov     eax, [rsp+438h+var_3A4]
0x18000d2ab  mov     dword ptr [rsp+438h+PrivilegeSet], eax
0x18000d2af  mov     r9d, r13d
0x18000d2b2  lea     r8, [rsp+438h+var_1B8]
0x18000d2ba  lea     rdx, [rsp+438h+var_368]
0x18000d2c2  mov     rcx, r12
0x18000d2c5  call    ?EnumerateEvents@SebBroker@Broker@@QEAA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBUApplicationIdentity@2@W4_SebiEventType@@KK@Z; Broker::SebBroker::EnumerateEvents(Broker::ApplicationIdentity const &,_SebiEventType,ulong,ulong)
  ... truncated ...
```
