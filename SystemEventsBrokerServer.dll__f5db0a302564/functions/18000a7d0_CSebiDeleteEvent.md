# _CSebiDeleteEvent

- ea: `0x18000a7d0`
- end: `0x18000b161`
- name: `_CSebiDeleteEvent`
- size: `2449`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x1800092f0`
- `0x18000a7d0`
- `0x18000b168`
- `0x18000b180`
- `0x18000b340`
- `0x18000b3d0`
- `0x18000bb50`
- `0x18000bbc0`
- `0x18000beb4`
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

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ac9c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ac9c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000acae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000acae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac0a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ad03`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ad03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aca2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aca2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a850`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a850`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a869`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a869`
- `RPCRT4!RpcImpersonateClient` at `0x18000a82d`
- `RPCRT4!RpcImpersonateClient` at `0x18000a82d`
- `RPCRT4!RpcRevertToSelf` at `0x18000a877`
- `RPCRT4!RpcRevertToSelf` at `0x18000a877`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a842`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a842`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000aa93`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000aa93`

## string_xrefs

- `0x18000a8b4`: `Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall CSebiDeleteEvent(__int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  unsigned __int64 v4; // rdi
  unsigned int v5; // eax
  HANDLE CurrentThread; // rax
  _QWORD *v7; // r10
  _DWORD *v8; // rcx
  CBroker::SebBroker *v9; // rbx
  __m128i v10; // xmm6
  __int64 v11; // rbx
  WCHAR *v12; // rbx
  void *v13; // rdi
  __int64 v14; // r8
  LONG v15; // eax
  __int64 v16; // r8
  void *v17; // rcx
  void *v18; // rcx
  volatile signed __int32 *v19; // xmm6_8
  __int64 v20; // r8
  void *v21; // rbx
  char *v23; // rdi
  char v24; // bl
  DWORD LengthSid; // eax
  DWORD v26; // eax
  DWORD LastError; // eax
  UINT32 packageFamilyNameLength[2]; // [rsp+38h] [rbp-400h] BYREF
  unsigned __int64 v29; // [rsp+40h] [rbp-3F8h] BYREF
  _QWORD *v30; // [rsp+48h] [rbp-3F0h]
  unsigned int Pid; // [rsp+50h] [rbp-3E8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-3E0h] BYREF
  __m128i v33; // [rsp+60h] [rbp-3D8h]
  void **v34; // [rsp+80h] [rbp-3B8h] BYREF
  __int128 v35; // [rsp+88h] [rbp-3B0h]
  int v36; // [rsp+98h] [rbp-3A0h]
  void **pExceptionObject; // [rsp+A0h] [rbp-398h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-390h]
  int v39; // [rsp+B8h] [rbp-380h]
  int v40; // [rsp+C0h] [rbp-378h]
  _QWORD v41[3]; // [rsp+C8h] [rbp-370h] BYREF
  int v42; // [rsp+E0h] [rbp-358h]
  unsigned int v43; // [rsp+E8h] [rbp-350h]
  _QWORD v44[3]; // [rsp+F0h] [rbp-348h] BYREF
  int v45; // [rsp+108h] [rbp-330h]
  unsigned int v46; // [rsp+110h] [rbp-328h]
  void **v47; // [rsp+118h] [rbp-320h] BYREF
  __int128 v48; // [rsp+120h] [rbp-318h]
  int v49; // [rsp+130h] [rbp-308h]
  int v50; // [rsp+138h] [rbp-300h]
  void *v51; // [rsp+140h] [rbp-2F8h] BYREF
  __int128 v52; // [rsp+148h] [rbp-2F0h]
  unsigned __int64 v53; // [rsp+158h] [rbp-2E0h]
  unsigned int v54; // [rsp+160h] [rbp-2D8h]
  __int128 v55; // [rsp+168h] [rbp-2D0h] BYREF
  __m128i si128; // [rsp+178h] [rbp-2C0h]
  struct _GUID v57; // [rsp+188h] [rbp-2B0h] BYREF
  void *v58[2]; // [rsp+1A0h] [rbp-298h] BYREF
  __int64 v59; // [rsp+1B0h] [rbp-288h]
  __int128 v60; // [rsp+1B8h] [rbp-280h] BYREF
  __int64 v61; // [rsp+1C8h] [rbp-270h]
  unsigned __int64 v62; // [rsp+1D0h] [rbp-268h]
  __int128 v63; // [rsp+1D8h] [rbp-260h] BYREF
  __int64 v64; // [rsp+1E8h] [rbp-250h]
  unsigned __int64 v65; // [rsp+1F0h] [rbp-248h]
  WCHAR packageFamilyName[128]; // [rsp+200h] [rbp-238h] BYREF
  WCHAR packageFullName[132]; // [rsp+300h] [rbp-138h] BYREF

  v3 = a2;
  v4 = HIDWORD(a2);
  v30 = a3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  v57 = 0;
  if ( RpcImpersonateClient(0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
    v38 = 0;
    v39 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v40 = 5;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v5 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v5 )
  {
    v52 = 0;
    LODWORD(v53) = 1;
    v51 = &Broker::Win32Error::`vftable';
    v54 = v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v5);
    std::exception::exception((std::exception *)v41, (const struct std::exception *)&v51);
    v42 = v53;
    v41[0] = &Broker::Win32Error::`vftable';
    v43 = v54;
    throw (Broker::Win32Error *)v41;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v52 = 0;
    LODWORD(v53) = 1;
    v51 = &Broker::Win32Error::`vftable';
    v54 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    std::exception::exception((std::exception *)v44, (const struct std::exception *)&v51);
    v45 = v53;
    v44[0] = &Broker::Win32Error::`vftable';
    v46 = v54;
    throw (Broker::Win32Error *)v44;
  }
  if ( !RpcRevertToSelf() )
    goto LABEL_6;
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
LABEL_6:
    v7 = WPP_GLOBAL_Control;
  }
  v8 = (_DWORD *)*v30;
  if ( *(_DWORD *)*v30 != v3 || v8[1] != (_DWORD)v4 || v8[2] != Pid )
  {
    if ( (*((_BYTE *)v7 + 28) & 0x20) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_(v7[2], 28, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
    v35 = 0;
    v36 = 5;
    v34 = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&v34;
  }
  StringCchPrintfW(packageFullName, 0x7Fu, L"Microsoft.ProcessID%x_1.0.0.1_neutral__8wekyb3d8bbwe");
  *(_QWORD *)v57.Data4 = 0;
  v57.Data1 = v3;
  *(_DWORD *)&v57.Data2 = v4;
  v9 = CBroker::SebBroker::Instance;
  if ( CBroker::SebBroker::Instance
    && (v23 = (char *)CBroker::SebBroker::Instance + 8,
        RtlAcquireSRWLockExclusive((char *)CBroker::SebBroker::Instance + 8),
        GetCurrentThreadId(),
        v24 = *(_BYTE *)v9,
        RtlReleaseSRWLockExclusive(v23),
        v24) )
  {
    if ( *(&CBroker::SebBroker::Instance + 1) )
      _InterlockedIncrement((volatile signed __int32 *)*(&CBroker::SebBroker::Instance + 1) + 2);
    v10 = *(__m128i *)&CBroker::SebBroker::Instance;
  }
  else
  {
    v10 = 0;
  }
  v33 = v10;
  if ( !v10.m128i_i64[0] )
  {
    v48 = 0;
    v49 = 1;
    v47 = &Broker::Win32Error::`vftable';
    v50 = 21;
    throw (Broker::Win32Error *)&v47;
  }
  v55 = 0;
  si128 = 0;
  std::wstring::_Construct_empty((__int64)&v55);
  v11 = Broker::RpcClientToken::GetPackageFullName((__int64)&Pid, (__int64)&v51);
  if ( &v55 != (__int128 *)v11 )
  {
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v55, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v55) = 0;
    v55 = *(_OWORD *)v11;
    si128 = *(__m128i *)(v11 + 16);
    *(_QWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 24) = 7;
    *(_WORD *)v11 = 0;
  }
  if ( v53 > 7 )
    std::_Deallocate<16>(v51, 2 * v53 + 2);
  if ( si128.m128i_i64[0] )
  {
    v12 = (WCHAR *)&v55;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = (WCHAR *)v55;
  }
  else
  {
    v12 = packageFullName;
  }
  v13 = (void *)*Broker::RpcClientToken::GetUserSid((__int64)&Pid, &v51);
  std::vector<_GUID>::vector<_GUID>(v58);
  v60 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct_empty((__int64)&v60);
  v63 = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct_empty((__int64)&v63);
  if ( v13 )
  {
    LengthSid = GetLengthSid(v13);
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)v58, (_BYTE *)v58[0], v13, LengthSid);
  }
  if ( v12 )
  {
    packageFamilyNameLength[0] = 0;
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    std::wstring::_Assign<unsigned short>((char **)&v63, v12, (char *)v14);
    packageFamilyNameLength[0] = 128;
    v15 = PackageFamilyNameFromFullName(v12, packageFamilyNameLength, packageFamilyName);
    v16 = -1;
    if ( v15 )
    {
      do
        ++v16;
      while ( v12[v16] );
      std::wstring::_Assign<unsigned short>((char **)&v60, v12, (char *)v16);
    }
    else
    {
      do
        ++v16;
      while ( packageFamilyName[v16] );
      std::wstring::_Assign<unsigned short>((char **)&v60, packageFamilyName, (char *)v16);
    }
  }
  v17 = v51;
  if ( v51 )
  {
    v29 = *((_QWORD *)&v52 + 1) - (_QWORD)v51;
    *(_QWORD *)packageFamilyNameLength = v51;
    if ( *((_QWORD *)&v52 + 1) - (_QWORD)v51 >= 0x1000u )
    {
      std::_Adjust_manually_vector_aligned((void **)packageFamilyNameLength, &v29);
      v17 = *(void **)packageFamilyNameLength;
    }
    operator delete(v17);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((void *)v55, 2 * si128.m128i_i64[1] + 2);
  CBroker::SebBroker::DeleteEvent((CBroker::SebBroker *)v10.m128i_i64[0], v58, &v57);
  if ( v65 > 7 )
    std::_Deallocate<16>((void *)v63, 2 * v65 + 2);
  v64 = 0;
  v65 = 7;
  LOWORD(v63) = 0;
  if ( v62 > 7 )
    std::_Deallocate<16>((void *)v60, 2 * v62 + 2);
  v61 = 0;
  v62 = 7;
  LOWORD(v60) = 0;
  v18 = v58[0];
  if ( v58[0] )
  {
    v29 = v59 - (unsigned __int64)v58[0];
    *(void **)packageFamilyNameLength = v58[0];
    if ( v59 - (unsigned __int64)v58[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)packageFamilyNameLength, &v29);
      v18 = *(void **)packageFamilyNameLength;
    }
    operator delete(v18);
  }
  v19 = (volatile signed __int32 *)_mm_srli_si128(v10, 8).m128i_u64[0];
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  if ( !CloseHandle(TokenHandle)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v26);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v20, *v30);
  v21 = (void *)*v30;
  if ( *v30 )
  {
    std::vector<unsigned char>::_Tidy((__int64)v21 + 16);
    operator delete(v21);
  }
  *v30 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000a7d0  mov     [rsp+arg_0], rbx
0x18000a7d5  push    rsi
0x18000a7d6  push    rdi
0x18000a7d7  push    r14
0x18000a7d9  sub     rsp, 420h
0x18000a7e0  movaps  [rsp+438h+var_28], xmm6
0x18000a7e8  mov     rax, cs:__security_cookie
0x18000a7ef  xor     rax, rsp
0x18000a7f2  mov     [rsp+438h+var_30], rax
0x18000a7fa  mov     rbx, rdx
0x18000a7fd  mov     rdi, rdx
0x18000a800  shr     rdi, 20h
0x18000a804  mov     [rsp+438h+var_3F0], r8
0x18000a809  xor     esi, esi
0x18000a80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a812  test    byte ptr [rcx+1Ch], 8
0x18000a816  jnz     loc_18000AD4E
0x18000a81c  xorps   xmm0, xmm0
0x18000a81f  movups  xmmword ptr [rsp+438h+var_2B0.Data1], xmm0
0x18000a827  mov     [rsp+438h+var_408], esi
0x18000a82b  xor     ecx, ecx; BindingHandle
0x18000a82d  call    cs:__imp_RpcImpersonateClient
0x18000a833  test    eax, eax
0x18000a835  jnz     loc_18000AE17
0x18000a83b  lea     rdx, [rsp+438h+Pid]; Pid
0x18000a840  xor     ecx, ecx; Binding
0x18000a842  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000a848  test    eax, eax
0x18000a84a  jnz     loc_18000AE84
0x18000a850  call    cs:__imp_GetCurrentThread
0x18000a856  mov     rcx, rax; ThreadHandle
0x18000a859  lea     r9, [rsp+438h+TokenHandle]; TokenHandle
0x18000a85e  mov     edx, 8; DesiredAccess
0x18000a863  mov     r8d, 1; OpenAsSelf
0x18000a869  call    cs:__imp_OpenThreadToken
0x18000a86f  test    eax, eax
0x18000a871  jz      loc_18000AF29
0x18000a877  call    cs:__imp_RpcRevertToSelf
0x18000a87d  test    eax, eax
0x18000a87f  jnz     loc_18000ADB7
0x18000a885  mov     r10, cs:WPP_GLOBAL_Control
0x18000a88c  mov     rax, [rsp+438h+var_3F0]
0x18000a891  mov     rcx, [rax]
0x18000a894  cmp     [rcx], ebx
0x18000a896  jnz     loc_18000B0F3
0x18000a89c  cmp     [rcx+4], edi
0x18000a89f  jnz     loc_18000B0F3
0x18000a8a5  mov     r9d, [rsp+438h+Pid]
0x18000a8aa  cmp     [rcx+8], r9d
0x18000a8ae  jnz     loc_18000B0F3
0x18000a8b4  lea     r8, aMicrosoftProce; "Microsoft.ProcessID%x_1.0.0.1_neutral__"...
0x18000a8bb  mov     edx, 7Fh; unsigned __int64
0x18000a8c0  lea     rcx, [rsp+438h+packageFullName]; unsigned __int16 *
0x18000a8c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a8cd  mov     qword ptr [rsp+438h+var_2B0.Data4], rsi
0x18000a8d5  mov     [rsp+438h+var_2B0.Data1], ebx
0x18000a8dc  mov     dword ptr [rsp+438h+var_2B0.Data2], edi
0x18000a8e3  mov     rbx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000a8ea  test    rbx, rbx
0x18000a8ed  jnz     loc_18000AC95
0x18000a8f3  xorps   xmm6, xmm6
0x18000a8f6  movdqu  [rsp+438h+var_3D8], xmm6
0x18000a8fc  movq    r14, xmm6
0x18000a901  xorps   xmm0, xmm0
0x18000a904  test    r14, r14
0x18000a907  jz      loc_18000AFD4
0x18000a90d  movups  [rsp+438h+var_2D0], xmm0
0x18000a915  xorps   xmm1, xmm1
0x18000a918  movdqu  [rsp+438h+var_2C0], xmm1
0x18000a921  lea     rcx, [rsp+438h+var_2D0]
0x18000a929  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000a92e  nop
0x18000a92f  lea     rdx, [rsp+438h+var_2F8]
0x18000a937  lea     rcx, [rsp+438h+Pid]
0x18000a93c  call    ?GetPackageFullName@RpcClientToken@Broker@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Broker::RpcClientToken::GetPackageFullName(void)
0x18000a941  mov     rbx, rax
0x18000a944  lea     rax, [rsp+438h+var_2D0]
0x18000a94c  cmp     rax, rbx
0x18000a94f  jz      short loc_18000A9A2
0x18000a951  mov     rdx, qword ptr [rsp+438h+var_2C0+8]
0x18000a959  cmp     rdx, 7
0x18000a95d  ja      loc_18000B016
0x18000a963  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000a96b  movdqu  [rsp+438h+var_2C0], xmm0
0x18000a974  mov     word ptr [rsp+438h+var_2D0], si
0x18000a97c  movups  xmm0, xmmword ptr [rbx]
0x18000a97f  movups  [rsp+438h+var_2D0], xmm0
0x18000a987  movups  xmm1, xmmword ptr [rbx+10h]
0x18000a98b  movups  [rsp+438h+var_2C0], xmm1
0x18000a993  mov     [rbx+10h], rsi
0x18000a997  mov     qword ptr [rbx+18h], 7
0x18000a99f  mov     [rbx], si
0x18000a9a2  mov     rdx, [rsp+438h+var_2E0]
0x18000a9aa  cmp     rdx, 7
0x18000a9ae  ja      loc_18000B030
0x18000a9b4  cmp     qword ptr [rsp+438h+var_2C0], 0
0x18000a9bd  jnz     loc_18000B04A
0x18000a9c3  lea     rbx, [rsp+438h+packageFullName]
0x18000a9cb  lea     rdx, [rsp+438h+var_2F8]
0x18000a9d3  lea     rcx, [rsp+438h+Pid]
0x18000a9d8  call    ?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; Broker::RpcClientToken::GetUserSid(void)
0x18000a9dd  nop
0x18000a9de  mov     rdi, [rax]
0x18000a9e1  lea     rcx, [rsp+438h+var_298]
0x18000a9e9  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000a9ee  nop
0x18000a9ef  xorps   xmm0, xmm0
0x18000a9f2  movups  [rsp+438h+var_280], xmm0
0x18000a9fa  mov     [rsp+438h+var_270], rsi
0x18000aa02  mov     [rsp+438h+var_268], rsi
0x18000aa0a  lea     rcx, [rsp+438h+var_280]
0x18000aa12  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000aa17  nop
0x18000aa18  movups  [rsp+438h+var_260], xmm0
0x18000aa20  mov     [rsp+438h+var_250], rsi
0x18000aa28  mov     [rsp+438h+var_248], rsi
0x18000aa30  lea     rcx, [rsp+438h+var_260]
0x18000aa38  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000aa3d  nop
0x18000aa3e  test    rdi, rdi
0x18000aa41  jnz     loc_18000AD00
0x18000aa47  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000aa4e  test    rbx, rbx
0x18000aa51  jz      short loc_18000AAD1
0x18000aa53  mov     [rsp+438h+packageFamilyNameLength], esi
0x18000aa57  mov     r8, rdi
0x18000aa5a  nop     word ptr [rax+rax+00h]
0x18000aa60  inc     r8
0x18000aa63  cmp     word ptr [rbx+r8*2], 0
0x18000aa69  jnz     short loc_18000AA60
0x18000aa6b  mov     rdx, rbx
0x18000aa6e  lea     rcx, [rsp+438h+var_260]
0x18000aa76  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000aa7b  mov     [rsp+438h+packageFamilyNameLength], 80h
0x18000aa83  lea     r8, [rsp+438h+packageFamilyName]; packageFamilyName
0x18000aa8b  lea     rdx, [rsp+438h+packageFamilyNameLength]; packageFamilyNameLength
0x18000aa90  mov     rcx, rbx; packageFullName
0x18000aa93  call    cs:__imp_PackageFamilyNameFromFullName
0x18000aa99  mov     r8, rdi
0x18000aa9c  test    eax, eax
0x18000aa9e  jnz     loc_18000ACE0
0x18000aaa4  lea     rax, [rsp+438h+packageFamilyName]
0x18000aaac  nop     dword ptr [rax+00h]
0x18000aab0  inc     r8
0x18000aab3  cmp     word ptr [rax+r8*2], 0
0x18000aab9  jnz     short loc_18000AAB0
0x18000aabb  lea     rdx, [rsp+438h+packageFamilyName]
0x18000aac3  lea     rcx, [rsp+438h+var_280]
0x18000aacb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000aad0  nop
0x18000aad1  mov     rcx, [rsp+438h+var_2F8]; void *
0x18000aad9  test    rcx, rcx
0x18000aadc  jz      short loc_18000AB06
0x18000aade  mov     rdx, [rsp+438h+var_2E8]
0x18000aae6  sub     rdx, rcx; unsigned __int64
0x18000aae9  mov     [rsp+438h+var_3F8], rdx
0x18000aaee  mov     qword ptr [rsp+438h+packageFamilyNameLength], rcx
0x18000aaf3  cmp     rdx, 1000h
0x18000aafa  jnb     loc_18000B069
0x18000ab00  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab05  nop
0x18000ab06  mov     rdx, qword ptr [rsp+438h+var_2C0+8]
0x18000ab0e  cmp     rdx, 7
0x18000ab12  ja      loc_18000B087
0x18000ab18  lea     r8, [rsp+438h+var_2B0]; struct _GUID *
0x18000ab20  lea     rdx, [rsp+438h+var_298]; struct Broker::ApplicationIdentity *
0x18000ab28  mov     rcx, r14; this
0x18000ab2b  call    ?DeleteEvent@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@_N2@Z; CBroker::SebBroker::DeleteEvent(Broker::ApplicationIdentity const &,_GUID const &,bool,bool)
0x18000ab30  nop
0x18000ab31  mov     rdx, [rsp+438h+var_248]
0x18000ab39  cmp     rdx, 7
0x18000ab3d  ja      loc_18000B0A1
0x18000ab43  mov     [rsp+438h+var_250], rsi
0x18000ab4b  mov     [rsp+438h+var_248], 7
0x18000ab57  mov     word ptr [rsp+438h+var_260], si
0x18000ab5f  mov     rdx, [rsp+438h+var_268]
0x18000ab67  cmp     rdx, 7
0x18000ab6b  ja      loc_18000B0BB
0x18000ab71  mov     [rsp+438h+var_270], rsi
0x18000ab79  mov     [rsp+438h+var_268], 7
0x18000ab85  mov     word ptr [rsp+438h+var_280], si
0x18000ab8d  mov     rcx, [rsp+438h+var_298]; void *
0x18000ab95  test    rcx, rcx
0x18000ab98  jz      short loc_18000ABC2
0x18000ab9a  mov     rdx, [rsp+438h+var_288]
0x18000aba2  sub     rdx, rcx; unsigned __int64
0x18000aba5  mov     [rsp+438h+var_3F8], rdx
0x18000abaa  mov     qword ptr [rsp+438h+packageFamilyNameLength], rcx
0x18000abaf  cmp     rdx, 1000h
0x18000abb6  jnb     loc_18000B0D5
0x18000abbc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000abc1  nop
0x18000abc2  psrldq  xmm6, 8
0x18000abc7  movq    rbx, xmm6
0x18000abcc  test    rbx, rbx
0x18000abcf  jz      short loc_18000AC05
0x18000abd1  mov     eax, edi
0x18000abd3  lock xadd [rbx+8], eax
0x18000abd8  cmp     eax, 1
0x18000abdb  jnz     short loc_18000AC05
0x18000abdd  mov     rax, [rbx]
0x18000abe0  mov     rcx, rbx
0x18000abe3  mov     rax, [rax]
0x18000abe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abeb  lock xadd [rbx+0Ch], edi
0x18000abf0  cmp     edi, 1
0x18000abf3  jnz     short loc_18000AC05
0x18000abf5  mov     rax, [rbx]
0x18000abf8  mov     rcx, rbx
0x18000abfb  mov     rax, [rax+8]
0x18000abff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac04  nop
0x18000ac05  mov     rcx, [rsp+438h+TokenHandle]; hObject
0x18000ac0a  call    cs:__imp_CloseHandle
0x18000ac10  test    eax, eax
0x18000ac12  jz      loc_18000AD72
0x18000ac18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac1f  test    byte ptr [rcx+1Ch], 8
0x18000ac23  jnz     loc_18000AD29
0x18000ac29  mov     rax, [rsp+438h+var_3F0]
0x18000ac2e  mov     rbx, [rax]
0x18000ac31  test    rbx, rbx
0x18000ac34  jz      short loc_18000AC4C
0x18000ac36  lea     rcx, [rbx+10h]
0x18000ac3a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000ac3f  mov     edx, 28h ; '('; unsigned __int64
0x18000ac44  mov     rcx, rbx; void *
0x18000ac47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac4c  mov     rax, [rsp+438h+var_3F0]
0x18000ac51  mov     [rax], rsi
0x18000ac54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac5b  test    byte ptr [rcx+1Ch], 8
0x18000ac5f  jnz     loc_18000ADEE
0x18000ac65  mov     eax, [rsp+438h+var_408]
0x18000ac69  mov     rcx, [rsp+438h+var_30]
0x18000ac71  xor     rcx, rsp; StackCookie
0x18000ac74  call    __security_check_cookie
0x18000ac79  mov     rbx, [rsp+438h+arg_0]
0x18000ac81  movaps  xmm6, [rsp+438h+var_28]
0x18000ac89  add     rsp, 420h
0x18000ac90  pop     r14
0x18000ac92  pop     rdi
0x18000ac93  pop     rsi
0x18000ac94  retn
0x18000ac95  lea     rdi, [rbx+8]
0x18000ac99  mov     rcx, rdi
0x18000ac9c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000aca2  call    cs:__imp_GetCurrentThreadId
0x18000aca8  movzx   ebx, byte ptr [rbx]
0x18000acab  mov     rcx, rdi
0x18000acae  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000acb4  test    bl, bl
0x18000acb6  jz      loc_18000A8F3
0x18000acbc  mov     rax, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000acc3  test    rax, rax
0x18000acc6  jz      short loc_18000ACCC
0x18000acc8  lock inc dword ptr [rax+8]
0x18000accc  movups  xmm6, cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18000acd3  jmp     loc_18000A8F6
0x18000ace0  inc     r8
0x18000ace3  cmp     word ptr [rbx+r8*2], 0
0x18000ace9  jnz     short loc_18000ACE0
0x18000aceb  mov     rdx, rbx
0x18000acee  lea     rcx, [rsp+438h+var_280]
0x18000acf6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000acfb  jmp     loc_18000AAD1
0x18000ad00  mov     rcx, rdi; pSid
0x18000ad03  call    cs:__imp_GetLengthSid
0x18000ad09  mov     r9d, eax
0x18000ad0c  mov     r8, rdi
0x18000ad0f  mov     rdx, [rsp+438h+var_298]
0x18000ad17  lea     rcx, [rsp+438h+var_298]
0x18000ad1f  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000ad24  jmp     loc_18000AA47
0x18000ad29  cmp     byte ptr [rcx+19h], 4
0x18000ad2d  jb      loc_18000AC29
0x18000ad33  mov     edx, 1Dh
0x18000ad38  mov     r9, [rsp+438h+var_3F0]
0x18000ad3d  mov     r9, [r9]
0x18000ad40  mov     rcx, [rcx+10h]
0x18000ad44  call    WPP_SF_q
0x18000ad49  jmp     loc_18000AC29
0x18000ad4e  cmp     byte ptr [rcx+19h], 4
0x18000ad52  jb      loc_18000A81C
0x18000ad58  mov     edx, 1Bh
0x18000ad5d  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18000ad64  mov     rcx, [rcx+10h]
0x18000ad68  call    WPP_SF_
0x18000ad6d  jmp     loc_18000A81C
0x18000ad72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad79  test    byte ptr [rcx+1Ch], 8
0x18000ad7d  jz      loc_18000AC18
0x18000ad83  cmp     byte ptr [rcx+19h], 2
0x18000ad87  jb      loc_18000AC18
0x18000ad8d  call    cs:__imp_GetLastError
0x18000ad93  mov     edx, 12h
0x18000ad98  mov     r9d, eax
0x18000ad9b  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000ada2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ada9  mov     rcx, [rcx+10h]
  ... truncated ...
```
