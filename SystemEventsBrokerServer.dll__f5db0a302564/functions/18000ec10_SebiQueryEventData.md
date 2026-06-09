# _SebiQueryEventData

- ea: `0x18000ec10`
- end: `0x18000f367`
- name: `_SebiQueryEventData`
- size: `1879`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000b168`
- `0x18000b180`
- `0x18000bbc0`
- `0x18000beb4`
- `0x18000da40`
- `0x18000e880`
- `0x18000ec10`
- `0x18000f370`
- `0x18001732c`
- `0x180019130`
- `0x1800195e0`
- `0x18001ab64`
- `0x18001cf50`
- `0x18001d364`
- `0x18001d9ac`
- `0x18001e0d8`
- `0x18001e3bc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f306`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2e9`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000ed88`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000ed88`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000edd3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000edd3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f135`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f135`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ec9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ec9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef58`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000f1a3`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000f1a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SebiQueryEventData(
        __int64 a1,
        __int128 *a2,
        const struct _GUID *a3,
        struct _SebiSystemEventCreationParameter *a4)
{
  struct _SebiSystemEventCreationParameter *v4; // r13
  const struct _GUID *v5; // r12
  BOOL v6; // eax
  DWORD LastError; // eax
  Broker::SebBroker *v8; // r14
  struct _GENERIC_MAPPING v9; // xmm6
  __int64 PackageFullName; // rsi
  __int128 *v11; // rbx
  void *v12; // rsi
  size_t LengthSid; // r9
  __int64 v14; // r8
  LONG v15; // eax
  __int64 v16; // r8
  PSECURITY_DESCRIPTOR v17; // rcx
  volatile signed __int32 *v18; // xmm6_8
  DWORD v19; // eax
  unsigned int v21; // [rsp+44h] [rbp-314h]
  DWORD packageFamilyNameLength; // [rsp+48h] [rbp-310h] BYREF
  DWORD AccessMask; // [rsp+50h] [rbp-308h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-300h] BYREF
  WINBOOL AccessStatus; // [rsp+60h] [rbp-2F8h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+68h] [rbp-2F0h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+70h] [rbp-2E8h] BYREF
  char v28[8]; // [rsp+78h] [rbp-2E0h] BYREF
  HANDLE ClientToken; // [rsp+80h] [rbp-2D8h]
  struct _SebiSystemEventCreationParameter *v30; // [rsp+88h] [rbp-2D0h]
  __int128 *v31; // [rsp+90h] [rbp-2C8h]
  Broker::BILayer::Failure *v32; // [rsp+98h] [rbp-2C0h] BYREF
  Broker::Win32Error *v33; // [rsp+A0h] [rbp-2B8h] BYREF
  void **v34; // [rsp+A8h] [rbp-2B0h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-2A8h]
  int v36; // [rsp+C0h] [rbp-298h]
  _QWORD pExceptionObject[3]; // [rsp+C8h] [rbp-290h] BYREF
  int v38; // [rsp+E0h] [rbp-278h]
  DWORD v39; // [rsp+E8h] [rbp-270h]
  void **v40; // [rsp+F0h] [rbp-268h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-260h]
  int v42; // [rsp+108h] [rbp-250h]
  DWORD v43; // [rsp+110h] [rbp-248h]
  _BYTE v44[40]; // [rsp+118h] [rbp-240h] BYREF
  const struct _GUID *v45; // [rsp+140h] [rbp-218h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+148h] [rbp-210h] BYREF
  __int128 v47; // [rsp+158h] [rbp-200h] BYREF
  __m128i si128; // [rsp+168h] [rbp-1F0h]
  void **v49; // [rsp+178h] [rbp-1E0h] BYREF
  __int128 v50; // [rsp+180h] [rbp-1D8h]
  unsigned __int64 v51; // [rsp+190h] [rbp-1C8h]
  DWORD v52; // [rsp+198h] [rbp-1C0h]
  _BYTE *v53[3]; // [rsp+1A0h] [rbp-1B8h] BYREF
  __int128 v54; // [rsp+1B8h] [rbp-1A0h] BYREF
  __int64 v55; // [rsp+1C8h] [rbp-190h]
  __int64 v56; // [rsp+1D0h] [rbp-188h]
  __int128 v57; // [rsp+1D8h] [rbp-180h] BYREF
  __int64 v58; // [rsp+1E8h] [rbp-170h]
  __int64 v59; // [rsp+1F0h] [rbp-168h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+200h] [rbp-158h] BYREF

  try
  {
    v4 = a4;
    v5 = a3;
    v11 = a2;
    v31 = a2;
    v45 = a3;
    v30 = a4;
    v21 = 0;
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v28);
    AccessMask = 0x80000000;
    SecurityDescriptorSize = 0;
    SecurityDescriptor = 0;
    v6 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;RC;;;S-1-5-80-5077831-2848399648-2133836502-3232794944-2981604943)(A;;R"
            "C;;;S-1-5-80-2226967063-754826275-1661302337-2802353169-2369347280)(A;;RC;;;S-1-5-80-2995899262-2131376444-1"
            "860748247-2210972999-1941275431)(A;;RC;;;S-1-5-11)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize);
    try
    {
      if ( !v6 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)&v49);
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v52);
        std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)&v49);
        v38 = v51;
        pExceptionObject[0] = &Broker::Win32Error::`vftable';
        v39 = v52;
        throw (Broker::Win32Error *)pExceptionObject;
      }
      packageFamilyNameLength = 0;
      AccessStatus = 0;
      PrivilegeSetLength[0] = 256;
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
              PrivilegeSetLength,
              &packageFamilyNameLength,
              &AccessStatus) )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)&v49);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v52);
        Broker::Win32Error::Win32Error((Broker::Win32Error *)v44);
        throw (Broker::Win32Error *)v44;
      }
      if ( !AccessStatus )
      {
        v50 = 0;
        LODWORD(v51) = 1;
        v49 = &Broker::Win32Error::`vftable';
        LastError = GetLastError();
        v52 = LastError;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
        v41 = 0;
        v42 = 1;
        v40 = &Broker::Win32Error::`vftable';
        v43 = GetLastError();
        throw (Broker::Win32Error *)&v40;
      }
      if ( packageFamilyNameLength != AccessMask )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids,
            packageFamilyNameLength);
        v35 = 0;
        v36 = 5;
        v34 = &Broker::AccessDenied::`vftable';
        throw (Broker::AccessDenied *)&v34;
      }
      LocalFree(SecurityDescriptor);
    }
    catch ( ... )
    {
      v5 = v45;
      v4 = v30;
      v11 = v31;
    }
    v8 = Broker::SebBroker::Instance;
    if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
    {
      if ( *(&Broker::SebBroker::Instance + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
        v8 = Broker::SebBroker::Instance;
      }
      v9 = *(struct _GENERIC_MAPPING *)&Broker::SebBroker::Instance;
    }
    else
    {
      v9 = 0;
      v8 = 0;
    }
    GenericMapping = v9;
    v47 = 0;
    si128 = 0;
    std::wstring::_Construct_empty((__int64)&v47);
    PackageFullName = Broker::RpcClientToken::GetPackageFullName((__int64)v28, (__int64)&v49);
    if ( &v47 != (__int128 *)PackageFullName )
    {
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>((void *)v47, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v47) = 0;
      v47 = *(_OWORD *)PackageFullName;
      si128 = *(__m128i *)(PackageFullName + 16);
      *(_QWORD *)(PackageFullName + 16) = 0;
      *(_QWORD *)(PackageFullName + 24) = 7;
      *(_WORD *)PackageFullName = 0;
    }
    if ( v51 > 7 )
      std::_Deallocate<16>(v49, 2 * v51 + 2);
    if ( si128.m128i_i64[0] )
    {
      v11 = &v47;
      if ( si128.m128i_i64[1] > 7uLL )
        v11 = (__int128 *)v47;
    }
    v12 = (void *)*Broker::RpcClientToken::GetUserSid((__int64)v28, &v49);
    std::vector<_GUID>::vector<_GUID>(v53);
    v54 = 0;
    v55 = 0;
    v56 = 0;
    std::wstring::_Construct_empty((__int64)&v54);
    v57 = 0;
    v58 = 0;
    v59 = 0;
    std::wstring::_Construct_empty((__int64)&v57);
    if ( v12 )
    {
      LengthSid = GetLengthSid(v12);
      std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)v53, v53[0], v12, LengthSid);
    }
    if ( v11 )
    {
      packageFamilyNameLength = 0;
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v11 + v14) );
      std::wstring::_Assign<unsigned short>((char **)&v57, v11, (char *)v14);
      packageFamilyNameLength = 128;
      v15 = PackageFamilyNameFromFullName((PCWSTR)v11, &packageFamilyNameLength, (PWSTR)&PrivilegeSet);
      v16 = -1;
      if ( v15 )
      {
        do
          ++v16;
        while ( *((_WORD *)v11 + v16) );
        std::wstring::_Assign<unsigned short>((char **)&v54, v11, (char *)v16);
      }
      else
      {
        do
          ++v16;
        while ( *((_WORD *)&PrivilegeSet.PrivilegeCount + v16) );
        std::wstring::_Assign<unsigned short>((char **)&v54, &PrivilegeSet, (char *)v16);
      }
    }
    v17 = v49;
    if ( v49 )
    {
      *(_QWORD *)PrivilegeSetLength = *((_QWORD *)&v50 + 1) - (_QWORD)v49;
      SecurityDescriptor = v49;
      if ( *((_QWORD *)&v50 + 1) - (_QWORD)v49 >= 0x1000u )
      {
        std::_Adjust_manually_vector_aligned(&SecurityDescriptor, (unsigned __int64 *)PrivilegeSetLength);
        v17 = SecurityDescriptor;
      }
      operator delete(v17);
    }
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v47, 2 * si128.m128i_i64[1] + 2);
    Broker::SebBroker::QueryEventData(v8, (const struct Broker::ApplicationIdentity *)v53, v5, v4, 1);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v53);
    v18 = (volatile signed __int32 *)_mm_srli_si128((__m128i)v9, 8).m128i_u64[0];
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( !CloseHandle(ClientToken)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v19);
    }
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( Broker::NotFound )
  {
    return 2;
  }
  catch ( Broker::AccessDenied )
  {
    return 5;
  }
  catch ( Broker::BILayer::Failure *v32 )
  {
    return RtlNtStatusToDosError(*((_DWORD *)v32 + 8));
  }
  catch ( Broker::Win32Error *v33 )
  {
    return *((unsigned int *)v33 + 8);
  }
  catch ( ... )
  {
    return 1359;
  }
  return v21;
}

```

## disassembly

```asm
0x18000ec10  push    rbx
0x18000ec12  push    rsi
0x18000ec13  push    rdi
0x18000ec14  push    r12
0x18000ec16  push    r13
0x18000ec18  push    r14
0x18000ec1a  push    r15
0x18000ec1c  sub     rsp, 320h
0x18000ec23  movaps  [rsp+358h+var_48], xmm6
0x18000ec2b  mov     rax, cs:__security_cookie
0x18000ec32  xor     rax, rsp
0x18000ec35  mov     [rsp+358h+var_58], rax
0x18000ec3d  mov     r13, r9
0x18000ec40  mov     r12, r8
0x18000ec43  mov     rbx, rdx
0x18000ec46  mov     [rsp+358h+var_2C8], rdx
0x18000ec4e  mov     [rsp+358h+var_218], r8
0x18000ec56  mov     [rsp+358h+var_2D0], r9
0x18000ec5e  xor     edi, edi
0x18000ec60  mov     [rsp+358h+var_314], edi
0x18000ec64  mov     [rsp+358h+var_318], dil
0x18000ec69  lea     rcx, [rsp+358h+var_2E0]; this
0x18000ec6e  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18000ec73  nop
0x18000ec74  mov     [rsp+358h+AccessMask], 80000000h
0x18000ec7c  mov     [rsp+358h+SecurityDescriptorSize], edi
0x18000ec80  mov     [rsp+358h+SecurityDescriptor], rdi
0x18000ec85  lea     r9, [rsp+358h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18000ec8a  lea     r8, [rsp+358h+SecurityDescriptor]; SecurityDescriptor
0x18000ec8f  mov     edx, 1; StringSDRevision
0x18000ec94  lea     rcx, aOSygSydARcSyAR_0; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;R"...
0x18000ec9b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000eca1  test    eax, eax
0x18000eca3  jnz     loc_18000ED3F
0x18000eca9  lea     rcx, [rsp+358h+var_1E0]; this
0x18000ecb1  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000ecb6  nop
0x18000ecb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecbe  test    dword ptr [rcx+1Ch], 400h
0x18000ecc5  jz      short loc_18000ECEA
0x18000ecc7  cmp     byte ptr [rcx+19h], 2
0x18000eccb  jb      short loc_18000ECEA
0x18000eccd  mov     edx, 0Ah
0x18000ecd2  mov     r9d, [rsp+358h+var_1C0]
0x18000ecda  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x18000ece1  mov     rcx, [rcx+10h]
0x18000ece5  call    WPP_SF_d
0x18000ecea  lea     rdx, [rsp+358h+var_1E0]; struct std::exception *
0x18000ecf2  lea     rcx, [rsp+358h+pExceptionObject]; this
0x18000ecfa  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000ecff  mov     eax, dword ptr [rsp+358h+var_1C8]
0x18000ed06  mov     [rsp+358h+var_278], eax
0x18000ed0d  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ed14  mov     [rsp+358h+pExceptionObject], rbx
0x18000ed1c  mov     eax, [rsp+358h+var_1C0]
0x18000ed23  mov     [rsp+358h+var_270], eax
0x18000ed2a  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ed31  lea     rcx, [rsp+358h+pExceptionObject]; pExceptionObject
0x18000ed39  call    _CxxThrowException_0
0x18000ed3f  mov     [rsp+358h+packageFamilyNameLength], edi
0x18000ed43  mov     [rsp+358h+var_2F8], edi
0x18000ed47  mov     [rsp+358h+var_2F0], 100h
0x18000ed4f  mov     [rsp+358h+GenericMapping.GenericRead], 20000h
0x18000ed5a  mov     [rsp+358h+GenericMapping.GenericWrite], 20000h
0x18000ed65  mov     [rsp+358h+GenericMapping.GenericExecute], 20000h
0x18000ed70  mov     [rsp+358h+GenericMapping.GenericAll], 1F0000h
0x18000ed7b  lea     rdx, [rsp+358h+GenericMapping]; GenericMapping
0x18000ed83  lea     rcx, [rsp+358h+AccessMask]; AccessMask
0x18000ed88  call    cs:__imp_MapGenericMask
0x18000ed8e  lea     rax, [rsp+358h+var_2F8]
0x18000ed93  mov     [rsp+358h+AccessStatus], rax; AccessStatus
0x18000ed98  lea     rax, [rsp+358h+packageFamilyNameLength]
0x18000ed9d  mov     [rsp+358h+GrantedAccess], rax; GrantedAccess
0x18000eda2  lea     rax, [rsp+358h+var_2F0]
0x18000eda7  mov     [rsp+358h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000edac  lea     rax, [rsp+358h+var_158]
0x18000edb4  mov     [rsp+358h+PrivilegeSet], rax; PrivilegeSet
0x18000edb9  lea     r9, [rsp+358h+GenericMapping]; GenericMapping
0x18000edc1  mov     r8d, [rsp+358h+AccessMask]; DesiredAccess
0x18000edc6  mov     rdx, [rsp+358h+ClientToken]; ClientToken
0x18000edce  mov     rcx, [rsp+358h+SecurityDescriptor]; pSecurityDescriptor
0x18000edd3  call    cs:__imp_AccessCheck
0x18000edd9  test    eax, eax
0x18000eddb  jnz     short loc_18000EE3D
0x18000eddd  lea     rcx, [rsp+358h+var_1E0]; this
0x18000ede5  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000edea  nop
0x18000edeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edf2  test    byte ptr [rcx+1Ch], 8
0x18000edf6  jz      short loc_18000EE1B
0x18000edf8  cmp     byte ptr [rcx+19h], 2
0x18000edfc  jb      short loc_18000EE1B
0x18000edfe  mov     edx, 18h
0x18000ee03  mov     r9d, [rsp+358h+var_1C0]
0x18000ee0b  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000ee12  mov     rcx, [rcx+10h]
0x18000ee16  call    WPP_SF_d
0x18000ee1b  lea     rcx, [rsp+358h+var_240]; this
0x18000ee23  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000ee28  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ee2f  lea     rcx, [rsp+358h+var_240]; pExceptionObject
0x18000ee37  call    _CxxThrowException_0
0x18000ee3d  cmp     [rsp+358h+var_2F8], 0
0x18000ee42  jnz     loc_18000EEE5
0x18000ee48  xorps   xmm0, xmm0
0x18000ee4b  movups  [rsp+358h+var_1D8], xmm0
0x18000ee53  mov     dword ptr [rsp+358h+var_1C8], 1
0x18000ee5e  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ee65  mov     [rsp+358h+var_1E0], rbx
0x18000ee6d  call    cs:__imp_GetLastError
0x18000ee73  mov     [rsp+358h+var_1C0], eax
0x18000ee7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee81  test    byte ptr [rcx+1Ch], 8
0x18000ee85  jz      short loc_18000EEA5
0x18000ee87  cmp     byte ptr [rcx+19h], 2
0x18000ee8b  jb      short loc_18000EEA5
0x18000ee8d  mov     edx, 19h
0x18000ee92  mov     r9d, eax
0x18000ee95  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000ee9c  mov     rcx, [rcx+10h]
0x18000eea0  call    WPP_SF_d
0x18000eea5  xorps   xmm0, xmm0
0x18000eea8  movups  [rsp+358h+var_260], xmm0
0x18000eeb0  mov     [rsp+358h+var_250], 1
0x18000eebb  mov     [rsp+358h+var_268], rbx
0x18000eec3  call    cs:__imp_GetLastError
0x18000eec9  mov     [rsp+358h+var_248], eax
0x18000eed0  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000eed7  lea     rcx, [rsp+358h+var_268]; pExceptionObject
0x18000eedf  call    _CxxThrowException_0
0x18000eee5  mov     r9d, [rsp+358h+packageFamilyNameLength]
0x18000eeea  cmp     r9d, [rsp+358h+AccessMask]
0x18000eeef  jz      short loc_18000EF53
0x18000eef1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eef8  test    byte ptr [rcx+1Ch], 8
0x18000eefc  jz      short loc_18000EF19
0x18000eefe  cmp     byte ptr [rcx+19h], 2
0x18000ef02  jb      short loc_18000EF19
0x18000ef04  mov     edx, 1Ah
0x18000ef09  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000ef10  mov     rcx, [rcx+10h]
0x18000ef14  call    WPP_SF_d
0x18000ef19  xorps   xmm0, xmm0
0x18000ef1c  movups  [rsp+358h+var_2A8], xmm0
0x18000ef24  mov     [rsp+358h+var_298], 5
0x18000ef2f  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000ef36  mov     [rsp+358h+var_2B0], rax
0x18000ef3e  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000ef45  lea     rcx, [rsp+358h+var_2B0]; pExceptionObject
0x18000ef4d  call    _CxxThrowException_0
0x18000ef53  mov     rcx, [rsp+358h+SecurityDescriptor]; hMem
0x18000ef58  call    cs:__imp_LocalFree
0x18000ef5e  mov     r15b, 1
0x18000ef61  mov     [rsp+358h+var_318], r15b
0x18000ef66  jmp     short loc_18000EF88
0x18000ef68  xor     edi, edi
0x18000ef6a  movzx   r15d, [rsp+358h+var_318]
0x18000ef70  mov     r12, [rsp+358h+var_218]
0x18000ef78  mov     r13, [rsp+358h+var_2D0]
0x18000ef80  mov     rbx, [rsp+358h+var_2C8]
0x18000ef88  mov     r14, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000ef8f  test    r14, r14
0x18000ef92  jz      short loc_18000EFBA
0x18000ef94  cmp     byte ptr [r14], 0
0x18000ef98  jz      short loc_18000EFBA
0x18000ef9a  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000efa1  test    rax, rax
0x18000efa4  jz      short loc_18000EFB1
0x18000efa6  lock inc dword ptr [rax+8]
0x18000efaa  mov     r14, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000efb1  movups  xmm6, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18000efb8  jmp     short loc_18000EFC0
0x18000efba  xorps   xmm6, xmm6
0x18000efbd  mov     r14, rdi
0x18000efc0  movdqu  xmmword ptr [rsp+358h+GenericMapping.GenericRead], xmm6
0x18000efc9  xorps   xmm0, xmm0
0x18000efcc  movups  [rsp+358h+var_200], xmm0
0x18000efd4  xorps   xmm1, xmm1
0x18000efd7  movdqu  [rsp+358h+var_1F0], xmm1
0x18000efe0  lea     rcx, [rsp+358h+var_200]
0x18000efe8  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000efed  nop
0x18000efee  lea     rdx, [rsp+358h+var_1E0]
0x18000eff6  lea     rcx, [rsp+358h+var_2E0]
0x18000effb  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000f000  mov     rsi, rax
0x18000f003  lea     rax, [rsp+358h+var_200]
0x18000f00b  cmp     rax, rsi
0x18000f00e  jz      short loc_18000F072
0x18000f010  mov     rdx, qword ptr [rsp+358h+var_1F0+8]
0x18000f018  cmp     rdx, 7
0x18000f01c  jbe     short loc_18000F033
0x18000f01e  lea     rdx, ds:2[rdx*2]
0x18000f026  mov     rcx, qword ptr [rsp+358h+var_200]
0x18000f02e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f033  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000f03b  movdqu  [rsp+358h+var_1F0], xmm0
0x18000f044  mov     word ptr [rsp+358h+var_200], di
0x18000f04c  movups  xmm0, xmmword ptr [rsi]
0x18000f04f  movups  [rsp+358h+var_200], xmm0
0x18000f057  movups  xmm1, xmmword ptr [rsi+10h]
0x18000f05b  movups  [rsp+358h+var_1F0], xmm1
0x18000f063  mov     [rsi+10h], rdi
0x18000f067  mov     qword ptr [rsi+18h], 7
0x18000f06f  mov     [rsi], di
0x18000f072  mov     rdx, [rsp+358h+var_1C8]
0x18000f07a  cmp     rdx, 7
0x18000f07e  jbe     short loc_18000F095
0x18000f080  lea     rdx, ds:2[rdx*2]
0x18000f088  mov     rcx, [rsp+358h+var_1E0]
0x18000f090  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f095  cmp     qword ptr [rsp+358h+var_1F0], 0
0x18000f09e  jz      short loc_18000F0BA
0x18000f0a0  lea     rbx, [rsp+358h+var_200]
0x18000f0a8  cmp     qword ptr [rsp+358h+var_1F0+8], 7
0x18000f0b1  cmova   rbx, qword ptr [rsp+358h+var_200]
0x18000f0ba  lea     rdx, [rsp+358h+var_1E0]
0x18000f0c2  lea     rcx, [rsp+358h+var_2E0]
0x18000f0c7  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x18000f0cc  nop
0x18000f0cd  mov     rsi, [rax]
0x18000f0d0  lea     rcx, [rsp+358h+var_1B8]
0x18000f0d8  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000f0dd  nop
0x18000f0de  xorps   xmm0, xmm0
0x18000f0e1  movups  [rsp+358h+var_1A0], xmm0
0x18000f0e9  mov     [rsp+358h+var_190], rdi
0x18000f0f1  mov     [rsp+358h+var_188], rdi
0x18000f0f9  lea     rcx, [rsp+358h+var_1A0]
0x18000f101  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000f106  nop
0x18000f107  movups  [rsp+358h+var_180], xmm0
0x18000f10f  mov     [rsp+358h+var_170], rdi
0x18000f117  mov     [rsp+358h+var_168], rdi
0x18000f11f  lea     rcx, [rsp+358h+var_180]
0x18000f127  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000f12c  nop
0x18000f12d  test    rsi, rsi
0x18000f130  jz      short loc_18000F156
0x18000f132  mov     rcx, rsi; pSid
0x18000f135  call    cs:__imp_GetLengthSid
0x18000f13b  mov     r9d, eax
0x18000f13e  mov     r8, rsi
0x18000f141  mov     rdx, [rsp+358h+var_1B8]
0x18000f149  lea     rcx, [rsp+358h+var_1B8]
0x18000f151  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000f156  test    rbx, rbx
0x18000f159  jz      loc_18000F1FF
0x18000f15f  mov     [rsp+358h+packageFamilyNameLength], edi
0x18000f163  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f16a  mov     r8, rdi
0x18000f16d  nop     dword ptr [rax]
0x18000f170  inc     r8
0x18000f173  cmp     word ptr [rbx+r8*2], 0
0x18000f179  jnz     short loc_18000F170
0x18000f17b  mov     rdx, rbx
0x18000f17e  lea     rcx, [rsp+358h+var_180]
0x18000f186  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f18b  mov     [rsp+358h+packageFamilyNameLength], 80h
0x18000f193  lea     r8, [rsp+358h+var_158]; packageFamilyName
0x18000f19b  lea     rdx, [rsp+358h+packageFamilyNameLength]; packageFamilyNameLength
0x18000f1a0  mov     rcx, rbx; packageFullName
0x18000f1a3  call    cs:__imp_PackageFamilyNameFromFullName
0x18000f1a9  mov     r8, rdi
0x18000f1ac  test    eax, eax
0x18000f1ae  jnz     short loc_18000F1E2
0x18000f1b0  lea     rax, [rsp+358h+var_158]
0x18000f1b8  nop     dword ptr [rax+rax+00000000h]
0x18000f1c0  inc     r8
0x18000f1c3  cmp     word ptr [rax+r8*2], 0
0x18000f1c9  jnz     short loc_18000F1C0
0x18000f1cb  lea     rdx, [rsp+358h+var_158]
0x18000f1d3  lea     rcx, [rsp+358h+var_1A0]
0x18000f1db  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f1e0  jmp     short loc_18000F206
0x18000f1e2  inc     r8
0x18000f1e5  cmp     word ptr [rbx+r8*2], 0
0x18000f1eb  jnz     short loc_18000F1E2
0x18000f1ed  mov     rdx, rbx
0x18000f1f0  lea     rcx, [rsp+358h+var_1A0]
0x18000f1f8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f1fd  jmp     short loc_18000F206
0x18000f1ff  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f206  mov     rcx, [rsp+358h+var_1E0]
0x18000f20e  test    rcx, rcx
0x18000f211  jz      short loc_18000F250
0x18000f213  mov     rdx, qword ptr [rsp+358h+var_1D8+8]
0x18000f21b  sub     rdx, rcx
0x18000f21e  mov     qword ptr [rsp+358h+var_2F0], rdx
0x18000f223  mov     [rsp+358h+SecurityDescriptor], rcx
0x18000f228  cmp     rdx, 1000h
0x18000f22f  jb      short loc_18000F24A
0x18000f231  lea     rdx, [rsp+358h+var_2F0]; unsigned __int64 *
0x18000f236  lea     rcx, [rsp+358h+SecurityDescriptor]; void **
0x18000f23b  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000f240  mov     rcx, [rsp+358h+SecurityDescriptor]; void *
0x18000f245  mov     rdx, qword ptr [rsp+358h+var_2F0]; unsigned __int64
0x18000f24a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f24f  nop
0x18000f250  mov     rdx, qword ptr [rsp+358h+var_1F0+8]
  ... truncated ...
```
