# SecurePhoneRpcServer::_RpcInitialize(ushort const *)

- ea: `0x18004d180`
- end: `0x18004d9da`
- name: `?_RpcInitialize@SecurePhoneRpcServer@@AEAAJPEBG@Z`
- size: `2138`
- prototype: `__int64 __fastcall(SecurePhoneRpcServer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c324`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x180007780`
- `0x18004c0a0`
- `0x18004c51c`
- `0x18004c528`
- `0x18004c6e4`
- `0x18004c908`
- `0x18004ced4`
- `0x18004d180`
- `0x180078d6c`
- `0x180078fa0`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d33f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d540`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d62d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d63b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d902`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d33f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d540`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d62d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d63b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d8f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d902`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d978`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d6cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d6cb`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18004d781`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18004d781`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18004d75a`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18004d75a`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18004d2bb`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18004d69e`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18004d2bb`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18004d69e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18004d774`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18004d857`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18004d774`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18004d857`

## string_xrefs

- `0x18004d30c`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d453`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d4a1`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d510`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d583`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d5fe`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d7ca`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d874`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d939`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`
- `0x18004d692`: `DefaultRpcAccess`

## pseudocode

```c
__int64 __fastcall SecurePhoneRpcServer::_RpcInitialize(SecurePhoneRpcServer *this, const unsigned __int16 *a2)
{
  __int64 v2; // rsi
  HLOCAL v3; // rdi
  HLOCAL v4; // rbx
  unsigned int v5; // r13d
  char *v6; // r14
  void *v7; // r15
  __int128 v8; // xmm7
  __int64 v9; // rax
  int TransientObjectSecurityDescriptor; // eax
  __int64 *v11; // rax
  SecurePhoneRpcServer *v12; // rcx
  void *v13; // r8
  void *v14; // rdx
  int UpdatedPublicInterfaceSecurityDescriptor; // eax
  BackTraceCollection *v16; // rcx
  unsigned int v17; // edi
  SecurePhoneRpcServer *v18; // rcx
  void *v19; // rdx
  int UpdatedInternalInterfaceSecurityDescriptor; // eax
  BackTraceCollection *v21; // rcx
  unsigned int v22; // r12d
  __int128 v23; // xmm0
  char *v24; // r12
  BackTraceCollection *v25; // rcx
  char *v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  _QWORD *v29; // rbx
  _QWORD *v30; // rbx
  _QWORD *v32; // rbx
  unsigned int v33; // r14d
  _QWORD *v34; // rbx
  unsigned __int64 v35; // r14
  __int64 v36; // rax
  PSECURITY_DESCRIPTOR *v37; // rax
  signed int LastError; // eax
  BackTraceCollection *v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  int v42; // eax
  BackTraceCollection *v43; // rcx
  int v44; // eax
  BackTraceCollection *v45; // rcx
  __int64 v46; // r8
  BackTraceCollection *v47; // rcx
  _QWORD *v48; // rbx
  BackTraceCollection *v49; // rcx
  _QWORD *v50; // rbx
  _QWORD *v51; // rbx
  _QWORD *v52; // rbx
  _OWORD v54[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v55; // [rsp+98h] [rbp-70h]
  __int128 v56; // [rsp+A8h] [rbp-60h]
  __int128 v57; // [rsp+C8h] [rbp-40h]
  __int128 v58; // [rsp+D8h] [rbp-30h]
  HLOCAL hMem; // [rsp+F8h] [rbp-10h] BYREF
  void *Block[2]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v61; // [rsp+110h] [rbp+8h]
  HLOCAL v62; // [rsp+118h] [rbp+10h]
  int v63; // [rsp+120h] [rbp+18h]
  __int64 *v64; // [rsp+128h] [rbp+20h]
  const wchar_t *v65; // [rsp+130h] [rbp+28h]
  void *v66[10]; // [rsp+138h] [rbp+30h] BYREF
  _QWORD v67[13]; // [rsp+188h] [rbp+80h] BYREF

  v64 = qword_180095E10;
  v56 = 0u;
  v65 = L"PhoneRpc\\InternalInterface";
  v2 = 4;
  v66[1] = qword_180096680;
  LODWORD(v57) = 41;
  v66[2] = L"ExternalPhoneRpc\\Interface";
  v3 = 0;
  *(_QWORD *)((char *)&v57 + 4) = 1234;
  v66[4] = qword_1800968B0;
  v4 = 0;
  v58 = 0u;
  v66[5] = L"PhoneRpc\\ExternalPhoneCallScreen";
  v5 = 0;
  v66[7] = qword_180097A50;
  *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v6 = (char *)Block[1];
  v7 = Block[0];
  v66[8] = L"PhoneRpc\\PublicInterface";
  HIDWORD(v57) = 0;
  v8 = v57;
  v66[0] = 0;
  v66[3] = 0;
  v66[6] = 0;
  v66[9] = 0;
  v61 = -1;
  while ( 1 )
  {
    v9 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&v66[3 * v5]);
    TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(9, v66[3 * v5 - 1], v9);
    if ( TransientObjectSecurityDescriptor >= 0 )
      break;
    Log_HREvent_8(
      TransientObjectSecurityDescriptor | 0x10000000u,
      0,
      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
      156);
LABEL_26:
    if ( ++v5 >= 4 )
    {
      v27 = RpcSecurityHelper::Initialize((RpcSecurityHelper *)&dword_1800B4180, a2);
      v22 = v27;
      if ( v27 < 0 )
      {
        BackTraceCollection::Capture(v28, v27);
        Log_HREvent_8(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 164);
        if ( v7 != (void *)-1LL )
          operator delete(v7);
        if ( v4 )
          LocalFree(v4);
        if ( v3 )
          LocalFree(v3);
        v29 = v67;
        do
        {
          v29 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v29);
          --v2;
        }
        while ( v2 );
        return v22;
      }
      v35 = 0xCCCCCCCCCCCCCCCDuLL * ((v6 - (_BYTE *)v7) >> 4);
      if ( v35 > 0xFFFFFFFF )
      {
        v33 = -2147024362;
        BackTraceCollection::Capture(v28, -2147024362);
        Log_HREvent_8(
          2147942934LL,
          1,
          "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
          167);
        if ( v7 != (void *)-1LL )
          operator delete(v7);
        if ( v4 )
          LocalFree(v4);
        if ( v3 )
          LocalFree(v3);
        v52 = v67;
        do
        {
          v52 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v52);
          --v2;
        }
        while ( v2 );
        return v33;
      }
      hMem = 0;
      v36 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&hMem);
      if ( (unsigned int)QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", v36) != -1073741772
        || (v37 = (PSECURITY_DESCRIPTOR *)tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&hMem),
            ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GR;;;IU)(A;;GR;;;AC)(A;;GR;;;AU)", 1u, v37, 0)) )
      {
        LODWORD(Block[0]) = 0;
        Block[1] = (void *)L"ncalrpc";
        v62 = hMem;
        v61 = 0;
        v63 = 10;
        v42 = RpcServerInterfaceGroupCreateW(
                v7,
                (unsigned int)v35,
                Block,
                1,
                -1,
                SecurePhoneRpcServer::_IdleCallback,
                &g_phoneRpcServer,
                &xmmword_1800B41A0);
        v33 = v42;
        if ( !v42 )
        {
          if ( hMem )
            FreeTransientObjectSecurityDescriptor();
          goto LABEL_73;
        }
        if ( v42 > 0 )
          v33 = (unsigned __int16)v42 | 0x80070000;
        BackTraceCollection::Capture(v43, v33);
        v41 = 112;
      }
      else
      {
        LastError = GetLastError();
        v33 = LastError;
        if ( LastError > 0 )
          v33 = (unsigned __int16)LastError | 0x80070000;
        BackTraceCollection::Capture(v39, v33);
        v41 = 99;
      }
      Log_HREvent_21(v33, 0, v40, v41);
      v49 = (BackTraceCollection *)hMem;
      if ( hMem )
        FreeTransientObjectSecurityDescriptor();
      if ( (v33 & 0x80000000) != 0 )
      {
        BackTraceCollection::Capture(v49, v33);
        Log_HREvent_8(v33, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 171);
        if ( v7 != (void *)-1LL )
          operator delete(v7);
        if ( v4 )
          LocalFree(v4);
        if ( v3 )
          LocalFree(v3);
        v50 = v67;
        do
        {
          v50 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v50);
          --v2;
        }
        while ( v2 );
        return v33;
      }
LABEL_73:
      v44 = RpcServerInterfaceGroupActivate(xmmword_1800B41A0);
      v33 = v44;
      if ( !v44 )
        goto LABEL_101;
      if ( v44 > 0 )
        v33 = (unsigned __int16)v44 | 0x80070000;
      BackTraceCollection::Capture(v45, v33);
      Log_HREvent_21(v33, 0, v46, 132);
      if ( (v33 & 0x80000000) == 0 )
      {
LABEL_101:
        if ( v7 != (void *)-1LL )
          operator delete(v7);
        if ( v4 )
          LocalFree(v4);
        if ( v3 )
          LocalFree(v3);
        v51 = v67;
        do
        {
          v51 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v51);
          --v2;
        }
        while ( v2 );
        return 0;
      }
      BackTraceCollection::Capture(v47, v33);
      Log_HREvent_8(v33, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 173);
      if ( v7 != (void *)-1LL )
        operator delete(v7);
      if ( v4 )
        LocalFree(v4);
      if ( v3 )
        LocalFree(v3);
      v48 = v67;
      do
      {
        v48 -= 3;
        SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v48);
        --v2;
      }
      while ( v2 );
      return v33;
    }
  }
  v11 = (&v64)[3 * v5];
  v12 = (SecurePhoneRpcServer *)qword_180097A50;
  *(_QWORD *)&v54[0] = 0;
  v54[1] = 0;
  v54[2] = v8;
  v54[3] = 0u;
  v55 = 0;
  *((_QWORD *)&v54[0] + 1) = v11;
  if ( v11 != qword_180097A50 )
  {
    v18 = (SecurePhoneRpcServer *)qword_180095E10;
    if ( v11 == qword_180095E10 )
    {
      if ( v4 )
        LocalFree(v4);
      v19 = v66[3 * v5];
      hMem = 0;
      UpdatedInternalInterfaceSecurityDescriptor = SecurePhoneRpcServer::_GetUpdatedInternalInterfaceSecurityDescriptor(
                                                     v18,
                                                     v19,
                                                     (struct _SECURITY_DESCRIPTOR **)&hMem);
      v22 = UpdatedInternalInterfaceSecurityDescriptor;
      if ( UpdatedInternalInterfaceSecurityDescriptor < 0 )
      {
        BackTraceCollection::Capture(v21, UpdatedInternalInterfaceSecurityDescriptor);
        Log_HREvent_8(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 143);
        if ( v7 != (void *)-1LL )
          operator delete(v7);
        if ( hMem )
          LocalFree(hMem);
        if ( v3 )
          LocalFree(v3);
        v32 = v67;
        do
        {
          v32 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v32);
          --v2;
        }
        while ( v2 );
        return v22;
      }
      v4 = hMem;
      *((_QWORD *)&v55 + 1) = hMem;
    }
    else
    {
      *((_QWORD *)&v55 + 1) = v66[3 * v5];
    }
    goto LABEL_18;
  }
  if ( v64 != qword_180095E10 )
  {
    Log_AssertionEvent_4(
      qword_180097A50,
      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
      127);
    if ( v64 != qword_180095E10 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v13 = v66[0];
  if ( !v66[0] )
  {
LABEL_18:
    if ( v6 == (char *)v61 )
    {
      v24 = (char *)((char *)v54 - (_BYTE *)v7);
      if ( !(unsigned __int8)utl::vector<RPC_INTERFACE_TEMPLATEW,utl::allocator<RPC_INTERFACE_TEMPLATEW>>::_Grow(Block) )
      {
        v33 = -2147024882;
        BackTraceCollection::Capture(v25, -2147024882);
        Log_HREvent_8(
          2147942414LL,
          0,
          "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp",
          152);
        if ( Block[0] != (void *)-1LL )
          operator delete(Block[0]);
        if ( v4 )
          LocalFree(v4);
        if ( v3 )
          LocalFree(v3);
        v34 = v67;
        do
        {
          v34 -= 3;
          SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v34);
          --v2;
        }
        while ( v2 );
        return v33;
      }
      v6 = (char *)Block[1];
      v26 = (char *)v54;
      v7 = Block[0];
      if ( v24 < (char *)((char *)Block[1] - (char *)Block[0]) )
        v26 = &v24[(unsigned __int64)Block[0]];
      *(_OWORD *)Block[1] = *(_OWORD *)v26;
      *((_OWORD *)v6 + 1) = *((_OWORD *)v26 + 1);
      *((_OWORD *)v6 + 2) = *((_OWORD *)v26 + 2);
      *((_OWORD *)v6 + 3) = *((_OWORD *)v26 + 3);
      v23 = *((_OWORD *)v26 + 4);
    }
    else
    {
      *(_OWORD *)v6 = v54[0];
      v23 = v55;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = v8;
      *((_OWORD *)v6 + 3) = 0u;
    }
    *((_OWORD *)v6 + 4) = v23;
    v6 += 80;
    Block[1] = v6;
    goto LABEL_26;
  }
  if ( v3 )
  {
    LocalFree(v3);
    v13 = v66[0];
  }
  v14 = v66[3 * v5];
  hMem = 0;
  UpdatedPublicInterfaceSecurityDescriptor = SecurePhoneRpcServer::_GetUpdatedPublicInterfaceSecurityDescriptor(
                                               v12,
                                               v14,
                                               v13,
                                               (struct _SECURITY_DESCRIPTOR **)&hMem);
  v17 = UpdatedPublicInterfaceSecurityDescriptor;
  if ( UpdatedPublicInterfaceSecurityDescriptor >= 0 )
  {
    v3 = hMem;
    *((_QWORD *)&v55 + 1) = hMem;
    goto LABEL_18;
  }
  BackTraceCollection::Capture(v16, UpdatedPublicInterfaceSecurityDescriptor);
  Log_HREvent_8(v17, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\securephonerpcserver.cpp", 134);
  if ( v7 != (void *)-1LL )
    operator delete(v7);
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
    LocalFree(hMem);
  v30 = v67;
  do
  {
    v30 -= 3;
    SecurePhoneRpcServer::_RpcInitialize_::_2_::RpcInterfaceWithSecurityDescriptor::_RpcInterfaceWithSecurityDescriptor(v30);
    --v2;
  }
  while ( v2 );
  return v17;
}

```

## disassembly

```asm
0x18004d180  mov     rax, rsp
0x18004d183  push    rbp
0x18004d184  push    rbx
0x18004d185  push    rsi
0x18004d186  push    rdi
0x18004d187  push    r12
0x18004d189  push    r13
0x18004d18b  push    r14
0x18004d18d  push    r15
0x18004d18f  lea     rbp, [rax-128h]
0x18004d196  sub     rsp, 1E8h
0x18004d19d  movaps  xmmword ptr [rax-58h], xmm6
0x18004d1a1  movaps  xmmword ptr [rax-68h], xmm7
0x18004d1a5  movaps  xmmword ptr [rax-78h], xmm8
0x18004d1aa  movaps  xmmword ptr [rax-88h], xmm9
0x18004d1b2  movaps  xmmword ptr [rax-98h], xmm10
0x18004d1ba  mov     rax, cs:__security_cookie
0x18004d1c1  xor     rax, rsp
0x18004d1c4  mov     [rbp+120h+var_A0], rax
0x18004d1cb  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004d1d3  lea     rax, qword_180095E10
0x18004d1da  xor     ecx, ecx
0x18004d1dc  mov     [rbp+120h+var_100], rax
0x18004d1e0  lea     rax, aPhonerpcIntern; "PhoneRpc\\InternalInterface"
0x18004d1e7  mov     qword ptr [rbp+120h+var_180], rcx
0x18004d1eb  mov     [rbp+120h+var_F8], rax
0x18004d1ef  xorps   xmm6, xmm6
0x18004d1f2  lea     rax, qword_180096680
0x18004d1f9  mov     qword ptr [rbp+120h+var_180+8], rcx
0x18004d1fd  movaps  xmm10, [rbp+120h+var_180]
0x18004d202  lea     esi, [rcx+4]
0x18004d205  mov     [rbp+120h+var_E8], rax
0x18004d209  xorps   xmm9, xmm9
0x18004d20d  lea     rax, aExternalphoner; "ExternalPhoneRpc\\Interface"
0x18004d214  mov     dword ptr [rbp+120h+var_160], 29h ; ')'
0x18004d21b  mov     [rbp+120h+var_E0], rax
0x18004d21f  mov     edi, ecx
0x18004d221  lea     rax, qword_1800968B0
0x18004d228  mov     qword ptr [rbp+120h+var_160+4], 4D2h
0x18004d230  mov     [rbp+120h+var_D0], rax
0x18004d234  mov     ebx, ecx
0x18004d236  lea     rax, aPhonerpcExtern; "PhoneRpc\\ExternalPhoneCallScreen"
0x18004d23d  mov     qword ptr [rbp+120h+var_150], rcx
0x18004d241  mov     [rbp+120h+var_C8], rax
0x18004d245  mov     r13d, ecx
0x18004d248  lea     rax, qword_180097A50
0x18004d24f  mov     qword ptr [rbp+120h+var_150+8], rcx
0x18004d253  movaps  xmm8, [rbp+120h+var_150]
0x18004d258  mov     [rbp+120h+var_B8], rax
0x18004d25c  lea     rax, aPhonerpcPublic; "PhoneRpc\\PublicInterface"
0x18004d263  movdqu  xmmword ptr [rbp+120h+Block], xmm0
0x18004d268  mov     r14, [rbp+120h+Block+8]
0x18004d26c  mov     r15, [rbp+120h+Block]
0x18004d270  mov     [rbp+120h+var_B0], rax
0x18004d274  xor     eax, eax
0x18004d276  mov     dword ptr [rbp+120h+var_160+0Ch], eax
0x18004d279  movaps  xmm7, [rbp+120h+var_160]
0x18004d27d  mov     [rsp+220h+var_1E0], rdx
0x18004d282  mov     [rbp+120h+var_F0], rcx
0x18004d286  mov     [rbp+120h+var_D8], rcx
0x18004d28a  mov     [rbp+120h+var_C0], rcx
0x18004d28e  mov     [rbp+120h+var_A8], rcx
0x18004d292  mov     [rbp+120h+var_118], 0FFFFFFFFFFFFFFFFh
0x18004d29a  mov     eax, r13d
0x18004d29d  lea     rcx, [rbp+120h+var_F0]
0x18004d2a1  lea     r12, [rax+rax*2]
0x18004d2a5  lea     rcx, [rcx+r12*8]
0x18004d2a9  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x18004d2ae  mov     rdx, [rbp+r12*8+120h+var_F8]
0x18004d2b3  mov     r8, rax
0x18004d2b6  mov     ecx, 9
0x18004d2bb  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18004d2c1  test    eax, eax
0x18004d2c3  js      loc_18004D44F
0x18004d2c9  mov     rax, [rbp+r12*8+120h+var_100]
0x18004d2ce  lea     rcx, qword_180097A50
0x18004d2d5  movaps  [rsp+220h+var_1D8+8], xmm10
0x18004d2db  movaps  [rsp+220h+var_1C8+8], xmm6
0x18004d2e0  movaps  [rsp+220h+var_1B8+8], xmm7
0x18004d2e5  movaps  [rbp+120h+var_1A0], xmm8
0x18004d2ea  movaps  [rbp+120h+var_190], xmm9
0x18004d2ef  mov     qword ptr [rsp+220h+var_1C8], rax
0x18004d2f4  cmp     rax, rcx
0x18004d2f7  jnz     short loc_18004D373
0x18004d2f9  lea     rax, qword_180095E10
0x18004d300  cmp     [rbp+120h+var_100], rax
0x18004d304  jz      short loc_18004D32A
0x18004d306  mov     r8d, 7Fh
0x18004d30c  lea     rdx, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d313  call    Log_AssertionEvent_4
0x18004d318  lea     rax, qword_180095E10
0x18004d31f  cmp     [rbp+120h+var_100], rax
0x18004d323  jz      short loc_18004D32A
0x18004d325  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004d32a  mov     r8, [rbp+120h+var_F0]
0x18004d32e  test    r8, r8
0x18004d331  jz      loc_18004D3C1
0x18004d337  test    rdi, rdi
0x18004d33a  jz      short loc_18004D349
0x18004d33c  mov     rcx, rdi; hMem
0x18004d33f  call    cs:__imp_LocalFree
0x18004d345  mov     r8, [rbp+120h+var_F0]; void *
0x18004d349  mov     rdx, [rbp+r12*8+120h+var_F0]; void *
0x18004d34e  lea     r9, [rbp+120h+hMem]; struct _SECURITY_DESCRIPTOR **
0x18004d352  mov     [rbp+120h+hMem], 0
0x18004d35a  call    ?_GetUpdatedPublicInterfaceSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAX0PEAPEAU_SECURITY_DESCRIPTOR@@@Z; SecurePhoneRpcServer::_GetUpdatedPublicInterfaceSecurityDescriptor(void *,void *,_SECURITY_DESCRIPTOR * *)
0x18004d35f  mov     edi, eax
0x18004d361  test    eax, eax
0x18004d363  js      loc_18004D503
0x18004d369  mov     rdi, [rbp+120h+hMem]
0x18004d36d  mov     qword ptr [rbp+120h+var_190+8], rdi
0x18004d371  jmp     short loc_18004D3C1
0x18004d373  lea     rcx, qword_180095E10
0x18004d37a  cmp     rax, rcx
0x18004d37d  jnz     short loc_18004D3B8
0x18004d37f  test    rbx, rbx
0x18004d382  jz      short loc_18004D38D
0x18004d384  mov     rcx, rbx; hMem
0x18004d387  call    cs:__imp_LocalFree
0x18004d38d  mov     rdx, [rbp+r12*8+120h+var_F0]; void *
0x18004d392  lea     r8, [rbp+120h+hMem]; struct _SECURITY_DESCRIPTOR **
0x18004d396  mov     [rbp+120h+hMem], 0
0x18004d39e  call    ?_GetUpdatedInternalInterfaceSecurityDescriptor@SecurePhoneRpcServer@@AEAAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@@Z; SecurePhoneRpcServer::_GetUpdatedInternalInterfaceSecurityDescriptor(void *,_SECURITY_DESCRIPTOR * *)
0x18004d3a3  mov     r12d, eax
0x18004d3a6  test    eax, eax
0x18004d3a8  js      loc_18004D575
0x18004d3ae  mov     rbx, [rbp+120h+hMem]
0x18004d3b2  mov     qword ptr [rbp+120h+var_190+8], rbx
0x18004d3b6  jmp     short loc_18004D3C1
0x18004d3b8  mov     rax, [rbp+r12*8+120h+var_F0]
0x18004d3bd  mov     qword ptr [rbp+120h+var_190+8], rax
0x18004d3c1  cmp     r14, [rbp+120h+var_118]
0x18004d3c5  jz      short loc_18004D3E5
0x18004d3c7  movaps  xmm0, [rsp+220h+var_1D8+8]
0x18004d3cc  movups  xmmword ptr [r14], xmm0
0x18004d3d0  movaps  xmm0, [rbp+120h+var_190]
0x18004d3d4  movups  xmmword ptr [r14+10h], xmm6
0x18004d3d9  movups  xmmword ptr [r14+20h], xmm7
0x18004d3de  movups  xmmword ptr [r14+30h], xmm8
0x18004d3e3  jmp     short loc_18004D440
0x18004d3e5  lea     r12, [rsp+220h+var_1D8+8]
0x18004d3ea  lea     rcx, [rbp+120h+Block]
0x18004d3ee  sub     r12, r15
0x18004d3f1  call    ?_Grow@?$vector@URPC_INTERFACE_TEMPLATEW@@V?$allocator@URPC_INTERFACE_TEMPLATEW@@@utl@@@utl@@AEAA_NXZ; utl::vector<RPC_INTERFACE_TEMPLATEW,utl::allocator<RPC_INTERFACE_TEMPLATEW>>::_Grow(void)
0x18004d3f6  test    al, al
0x18004d3f8  jz      loc_18004D5EA
0x18004d3fe  mov     r14, [rbp+120h+Block+8]
0x18004d402  lea     rcx, [rsp+220h+var_1D8+8]
0x18004d407  mov     r15, [rbp+120h+Block]
0x18004d40b  mov     rax, r14
0x18004d40e  sub     rax, r15
0x18004d411  cmp     r12, rax
0x18004d414  jnb     short loc_18004D41A
0x18004d416  lea     rcx, [r12+r15]
0x18004d41a  movups  xmm0, xmmword ptr [rcx]
0x18004d41d  movups  xmmword ptr [r14], xmm0
0x18004d421  movups  xmm1, xmmword ptr [rcx+10h]
0x18004d425  movups  xmmword ptr [r14+10h], xmm1
0x18004d42a  movups  xmm0, xmmword ptr [rcx+20h]
0x18004d42e  movups  xmmword ptr [r14+20h], xmm0
0x18004d433  movups  xmm1, xmmword ptr [rcx+30h]
0x18004d437  movups  xmmword ptr [r14+30h], xmm1
0x18004d43c  movups  xmm0, xmmword ptr [rcx+40h]
0x18004d440  movups  xmmword ptr [r14+40h], xmm0
0x18004d445  add     r14, 50h ; 'P'
0x18004d449  mov     [rbp+120h+Block+8], r14
0x18004d44d  jmp     short loc_18004D469
0x18004d44f  bts     eax, 1Ch
0x18004d453  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d45a  mov     ecx, eax
0x18004d45c  mov     r9d, 9Ch
0x18004d462  xor     edx, edx
0x18004d464  call    Log_HREvent_8
0x18004d469  inc     r13d
0x18004d46c  cmp     r13d, esi
0x18004d46f  jb      loc_18004D29A
0x18004d475  mov     rdx, [rsp+220h+var_1E0]; unsigned __int16 *
0x18004d47a  lea     rcx, dword_1800B4180; this
0x18004d481  call    ?Initialize@RpcSecurityHelper@@QEAAJPEBG@Z; RpcSecurityHelper::Initialize(ushort const *)
0x18004d486  xor     r13d, r13d
0x18004d489  mov     r12d, eax
0x18004d48c  test    eax, eax
0x18004d48e  jns     loc_18004D65F
0x18004d494  mov     edx, eax; int
0x18004d496  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004d49b  mov     r9d, 0A4h
0x18004d4a1  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d4a8  lea     edx, [r13+1]
0x18004d4ac  mov     ecx, r12d
0x18004d4af  call    Log_HREvent_8
0x18004d4b4  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18004d4b8  jz      short loc_18004D4C9
0x18004d4ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004d4c1  mov     rcx, r15; Block
0x18004d4c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004d4c9  test    rbx, rbx
0x18004d4cc  jz      short loc_18004D4D7
0x18004d4ce  mov     rcx, rbx; hMem
0x18004d4d1  call    cs:__imp_LocalFree
0x18004d4d7  test    rdi, rdi
0x18004d4da  jz      short loc_18004D4E5
0x18004d4dc  mov     rcx, rdi; hMem
0x18004d4df  call    cs:__imp_LocalFree
0x18004d4e5  lea     rbx, [rbp+120h+var_A0]
0x18004d4ec  sub     rbx, 18h
0x18004d4f0  mov     rcx, rbx
0x18004d4f3  call    _SecurePhoneRpcServer___RpcInitialize____2___RpcInterfaceWithSecurityDescriptor___RpcInterfaceWithSecurityDescriptor
0x18004d4f8  sub     rsi, 1
0x18004d4fc  jnz     short loc_18004D4EC
0x18004d4fe  jmp     loc_18004D5E2
0x18004d503  mov     edx, edi; int
0x18004d505  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004d50a  mov     r9d, 86h
0x18004d510  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d517  mov     edx, 1
0x18004d51c  mov     ecx, edi
0x18004d51e  call    Log_HREvent_8
0x18004d523  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18004d527  jz      short loc_18004D538
0x18004d529  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004d530  mov     rcx, r15; Block
0x18004d533  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004d538  test    rbx, rbx
0x18004d53b  jz      short loc_18004D546
0x18004d53d  mov     rcx, rbx; hMem
0x18004d540  call    cs:__imp_LocalFree
0x18004d546  mov     rcx, [rbp+120h+hMem]; hMem
0x18004d54a  test    rcx, rcx
0x18004d54d  jz      short loc_18004D555
0x18004d54f  call    cs:__imp_LocalFree
0x18004d555  lea     rbx, [rbp+120h+var_A0]
0x18004d55c  sub     rbx, 18h
0x18004d560  mov     rcx, rbx
0x18004d563  call    _SecurePhoneRpcServer___RpcInitialize____2___RpcInterfaceWithSecurityDescriptor___RpcInterfaceWithSecurityDescriptor
0x18004d568  sub     rsi, 1
0x18004d56c  jnz     short loc_18004D55C
0x18004d56e  mov     eax, edi
0x18004d570  jmp     loc_18004D99A
0x18004d575  mov     edx, r12d; int
0x18004d578  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004d57d  mov     r9d, 8Fh
0x18004d583  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d58a  mov     edx, 1
0x18004d58f  mov     ecx, r12d
0x18004d592  call    Log_HREvent_8
0x18004d597  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18004d59b  jz      short loc_18004D5AC
0x18004d59d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004d5a4  mov     rcx, r15; Block
0x18004d5a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004d5ac  mov     rcx, [rbp+120h+hMem]; hMem
0x18004d5b0  test    rcx, rcx
0x18004d5b3  jz      short loc_18004D5BB
0x18004d5b5  call    cs:__imp_LocalFree
0x18004d5bb  test    rdi, rdi
0x18004d5be  jz      short loc_18004D5C9
0x18004d5c0  mov     rcx, rdi; hMem
0x18004d5c3  call    cs:__imp_LocalFree
0x18004d5c9  lea     rbx, [rbp+120h+var_A0]
0x18004d5d0  sub     rbx, 18h
0x18004d5d4  mov     rcx, rbx
0x18004d5d7  call    _SecurePhoneRpcServer___RpcInitialize____2___RpcInterfaceWithSecurityDescriptor___RpcInterfaceWithSecurityDescriptor
0x18004d5dc  sub     rsi, 1
0x18004d5e0  jnz     short loc_18004D5D0
0x18004d5e2  mov     eax, r12d
0x18004d5e5  jmp     loc_18004D99A
0x18004d5ea  mov     r14d, 8007000Eh
0x18004d5f0  mov     edx, r14d; int
0x18004d5f3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004d5f8  mov     r9d, 98h
0x18004d5fe  lea     r8, aOnecoreuapNetP_11; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004d605  xor     edx, edx
0x18004d607  mov     ecx, r14d
0x18004d60a  call    Log_HREvent_8
0x18004d60f  mov     rcx, [rbp+120h+Block]; Block
0x18004d613  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004d617  jz      short loc_18004D625
0x18004d619  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004d620  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004d625  test    rbx, rbx
0x18004d628  jz      short loc_18004D633
0x18004d62a  mov     rcx, rbx; hMem
0x18004d62d  call    cs:__imp_LocalFree
0x18004d633  test    rdi, rdi
0x18004d636  jz      short loc_18004D641
0x18004d638  mov     rcx, rdi; hMem
0x18004d63b  call    cs:__imp_LocalFree
0x18004d641  lea     rbx, [rbp+120h+var_A0]
0x18004d648  sub     rbx, 18h
0x18004d64c  mov     rcx, rbx
0x18004d64f  call    _SecurePhoneRpcServer___RpcInitialize____2___RpcInterfaceWithSecurityDescriptor___RpcInterfaceWithSecurityDescriptor
0x18004d654  sub     rsi, 1
0x18004d658  jnz     short loc_18004D648
0x18004d65a  jmp     loc_18004D997
0x18004d65f  sub     r14, r15
0x18004d662  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004d66c  sar     r14, 4
0x18004d670  imul    r14, rax
0x18004d674  mov     eax, 0FFFFFFFFh
0x18004d679  cmp     r14, rax
  ... truncated ...
```
