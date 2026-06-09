# NgcHandlerRpcEnumContainers(std::shared_ptr<NgcUtils::RpcClient> const &,std::vector<std::unique_ptr<NgcTransportContainerInfo,std::default_delete<NgcTransportContainerInfo>>,std::allocator<std::unique_ptr<NgcTransportContainerInfo,std::default_delete<NgcTransportContainerInfo>>>> *)

- ea: `0x180005fd0`
- end: `0x180006782`
- name: `?NgcHandlerRpcEnumContainers@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEAV?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@2@@Z`
- size: `1970`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005e90`

## callees

- `0x1800049e0`
- `0x180004e34`
- `0x180005970`
- `0x180005b20`
- `0x180005fd0`
- `0x180006788`
- `0x1800067f0`
- `0x180006860`
- `0x1800068c0`
- `0x1800069f0`
- `0x180006aa0`
- `0x180006acc`
- `0x180006b2c`
- `0x18000782c`
- `0x180007964`
- `0x180010d1c`
- `0x1800527ac`
- `0x180052e98`
- `0x1800533a4`
- `0x18005d2b0`
- `0x18005d2ec`
- `0x1800c155c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000649b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006568`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000649b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006568`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000659b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000659b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000648d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000655a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000658d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000648d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000655a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000658d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006170`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006170`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000619b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000619b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000615e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006306`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000661c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000615e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006306`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000661c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000613d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000613d`

## string_xrefs

- `0x18000650c`: `onecore\ds\security\ngc\ctnrsvc\client\ngc\ngchandlerclient.cpp`
- `0x18000653f`: `onecore\ds\security\ngc\ctnrsvc\client\ngc\ngchandlerclient.cpp`
- `0x1800065ac`: `onecore\ds\security\ngc\ctnrsvc\client\ngc\ngchandlerclient.cpp`
- `0x1800065c6`: `onecore\ds\security\ngc\ctnrsvc\client\ngc\ngchandlerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall NgcHandlerRpcEnumContainers(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  int v4; // eax
  unsigned int LastError; // ebx
  void *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rdi
  size_t size_of; // rax
  __int64 *v10; // rbx
  __int64 *v11; // r8
  __int64 *v12; // rdx
  __int64 *v13; // rcx
  unsigned __int64 v14; // r8
  unsigned int k; // edi
  __int64 v16; // r15
  BOOL v17; // ebx
  const char *v18; // r9
  PSID v19; // rcx
  DWORD LengthSid; // eax
  const char *v21; // r9
  char *v22; // rsi
  PSID *v23; // rbx
  PSID v24; // rcx
  void *v25; // rdx
  _QWORD *v26; // rbx
  void *v27; // rcx
  void *v28; // rdx
  PSID v29; // rcx
  void *v30; // rdx
  PSID v31; // rcx
  bool v32; // zf
  _QWORD **v33; // rbx
  _QWORD **m; // rsi
  _QWORD *v35; // rdi
  void *v36; // rcx
  void *v37; // rdx
  _QWORD **v38; // rcx
  void *v39; // rdx
  char *v40; // rbx
  char *v41; // rsi
  _QWORD *v42; // rdi
  void *v43; // rcx
  void *v44; // rdx
  void *v45; // rdx
  void *v46; // rbx
  HANDLE v47; // rax
  SIZE_T v48; // rax
  _BYTE *n; // rcx
  HANDLE v50; // rax
  void *v52; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v54; // rax
  _BYTE *i; // rcx
  HANDLE v56; // rax
  PSID v57; // rcx
  void *v58; // rdx
  PSID v59; // rcx
  __int64 v60; // rax
  LPCVOID lpMem; // [rsp+20h] [rbp-79h] BYREF
  void *v62[2]; // [rsp+28h] [rbp-71h] BYREF
  __int64 *v63; // [rsp+38h] [rbp-61h]
  PSID pSid; // [rsp+40h] [rbp-59h] BYREF
  void *v65; // [rsp+48h] [rbp-51h] BYREF
  PSID pDestinationSid[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v67; // [rsp+60h] [rbp-39h]
  int v68; // [rsp+68h] [rbp-31h]
  PSID *p_pSid; // [rsp+70h] [rbp-29h]
  PSID Sid; // [rsp+78h] [rbp-21h] BYREF
  char v71; // [rsp+80h] [rbp-19h]
  _BYTE v72[16]; // [rsp+88h] [rbp-11h] BYREF
  __int64 *v73; // [rsp+98h] [rbp-1h]
  __int64 *v74; // [rsp+A0h] [rbp+7h]
  void **j; // [rsp+A8h] [rbp+Fh]
  void **v76; // [rsp+B0h] [rbp+17h] BYREF
  __int64 *v77; // [rsp+B8h] [rbp+1Fh]
  __int64 v78; // [rsp+C0h] [rbp+27h]
  char *v79; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  void *p_lpMem; // [rsp+110h] [rbp+77h] BYREF
  void *v82; // [rsp+118h] [rbp+7Fh] BYREF

  v68 = 0;
  rpcmem<_NGC_RPC_KEY_INFO_LIST>::get_unique_ptr(&lpMem, a2, a1);
  p_lpMem = 0;
  v4 = I_NgcHandlerRpcEnumContainers(v3, &p_lpMem);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x538,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\ngc\\ngchandlerclient.cpp",
      (const char *)(unsigned int)v4,
      (int)lpMem);
    v52 = (void *)lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      v54 = HeapSize(ProcessHeap, 0, v52);
      if ( v54 != -1 )
      {
        for ( i = v52; v54; --v54 )
          *i++ = 0;
      }
      v56 = GetProcessHeap();
      HeapFree(v56, 0, v52);
    }
    return LastError;
  }
  v68 = 2;
  v82 = 0;
  v6 = (void *)lpMem;
  lpMem = p_lpMem;
  if ( v6 )
    MIDL_user_free(v6);
  v68 = 0;
  p_lpMem = &lpMem;
  wil::ScopeExitIgnore__lambda_53333d2fd512deb7784680597741ccc7___(v72, &p_lpMem);
  if ( !lpMem )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !lpMem )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x554,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\ngc\\ngchandlerclient.cpp",
        (const char *)0x8000FFFFLL,
        0);
      wil::details::ScopeExitFnGuard__lambda_53333d2fd512deb7784680597741ccc7___::operator()(v72);
      std::unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>::~unique_ptr<_NGC_RPC_CONTAINER_INFO,rpcmem_delete<_NGC_RPC_CONTAINER_INFO>>(&lpMem);
      return 2147549183LL;
    }
  }
  *(_OWORD *)v62 = 0;
  v63 = 0;
  v7 = lpMem;
  v8 = *(unsigned int *)lpMem;
  if ( *(_DWORD *)lpMem )
  {
    size_of = std::_Get_size_of_n<8>((unsigned int)v8);
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v76 = v62;
    v77 = v10;
    v78 = v8;
    v11 = (__int64 *)v62[1];
    v12 = (__int64 *)v62[0];
    v73 = v10;
    v13 = v10;
    v74 = v10;
    for ( j = v62; v12 != v11; ++v12 )
    {
      v60 = *v12;
      *v12 = 0;
      *v13++ = v60;
      v74 = v13;
    }
    v73 = v13;
    std::_Destroy_range<std::allocator<std::unique_ptr<NgcTransportContainerInfo>>>(v13, v13, (unsigned __int64)v11);
    v77 = 0;
    if ( v62[0] )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<NgcTransportContainerInfo>>>(
        (__int64 *)v62[0],
        (__int64 *)v62[1],
        v14);
      std::_Deallocate<16>(v62[0], ((char *)v63 - (char *)v62[0]) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    v62[0] = v10;
    v62[1] = v10;
    v63 = &v10[v8];
    std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(&v76);
    v7 = lpMem;
  }
  for ( k = 0; ; ++k )
  {
    if ( k >= *(_DWORD *)v7 )
    {
      if ( (void **)a2 != v62 )
      {
        v33 = *(_QWORD ***)a2;
        if ( *(_QWORD *)a2 )
        {
          for ( m = *(_QWORD ***)(a2 + 8); v33 != m; ++v33 )
          {
            v35 = *v33;
            if ( *v33 )
            {
              v36 = (void *)v35[2];
              if ( v36 )
              {
                v37 = (void *)(v35[4] - (_QWORD)v36);
                p_lpMem = v37;
                v82 = v36;
                if ( (unsigned __int64)v37 >= 0x1000 )
                {
                  std::_Adjust_manually_vector_aligned(&v82, (unsigned __int64 *)&p_lpMem);
                  v37 = p_lpMem;
                  v36 = v82;
                }
                operator delete(v36, (unsigned __int64)v37);
                v35[2] = 0;
                v35[3] = 0;
                v35[4] = 0;
              }
              operator delete(v35, 0x38u);
            }
          }
          v38 = *(_QWORD ***)a2;
          v39 = (void *)((*(_QWORD *)(a2 + 16) - *(_QWORD *)a2) & 0xFFFFFFFFFFFFFFF8uLL);
          v82 = v39;
          p_lpMem = v38;
          if ( (unsigned __int64)v39 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(&p_lpMem, (unsigned __int64 *)&v82);
            v38 = (_QWORD **)p_lpMem;
            v39 = v82;
          }
          operator delete(v38, (unsigned __int64)v39);
        }
        *(void **)a2 = v62[0];
        *(void **)(a2 + 8) = v62[1];
        *(_QWORD *)(a2 + 16) = v63;
        *(_OWORD *)v62 = 0;
        v63 = 0;
      }
      v40 = (char *)v62[0];
      if ( v62[0] )
      {
        v41 = (char *)v62[1];
        if ( v62[0] != v62[1] )
        {
          do
          {
            v42 = *(_QWORD **)v40;
            if ( *(_QWORD *)v40 )
            {
              v43 = (void *)v42[2];
              if ( v43 )
              {
                v44 = (void *)(v42[4] - (_QWORD)v43);
                p_lpMem = v44;
                v82 = v43;
                if ( (unsigned __int64)v44 >= 0x1000 )
                {
                  std::_Adjust_manually_vector_aligned(&v82, (unsigned __int64 *)&p_lpMem);
                  v44 = p_lpMem;
                  v43 = v82;
                }
                operator delete(v43, (unsigned __int64)v44);
                v42[2] = 0;
                v42[3] = 0;
                v42[4] = 0;
              }
              operator delete(v42, 0x38u);
            }
            v40 += 8;
          }
          while ( v40 != v41 );
          v40 = (char *)v62[0];
        }
        v45 = (void *)(((char *)v63 - v40) & 0xFFFFFFFFFFFFFFF8uLL);
        v82 = v45;
        p_lpMem = v40;
        if ( (unsigned __int64)v45 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&p_lpMem, (unsigned __int64 *)&v82);
          v40 = (char *)p_lpMem;
          v45 = v82;
        }
        operator delete(v40, (unsigned __int64)v45);
        *(_OWORD *)v62 = 0;
        v63 = 0;
      }
      wil::details::ScopeExitFnGuard__lambda_53333d2fd512deb7784680597741ccc7___::operator()(v72);
      v46 = (void *)lpMem;
      if ( lpMem )
      {
        v47 = GetProcessHeap();
        v48 = HeapSize(v47, 0, v46);
        if ( v48 != -1 )
        {
          for ( n = v46; v48; --v48 )
            *n++ = 0;
        }
        v50 = GetProcessHeap();
        HeapFree(v50, 0, v46);
      }
      return 0;
    }
    v16 = v7[1] + 40LL * k;
    pSid = 0;
    p_pSid = &pSid;
    Sid = 0;
    v71 = 1;
    v17 = ConvertStringSidToSidW(*(LPCWSTR *)(v16 + 16), &Sid);
    if ( v71 )
    {
      v19 = *p_pSid;
      *p_pSid = Sid;
      if ( v19 )
        LocalFree(v19);
    }
    if ( !v17 )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x562,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\ngc\\ngchandlerclient.cpp",
        v18);
      goto LABEL_35;
    }
    LengthSid = GetLengthSid(pSid);
    *(_OWORD *)pDestinationSid = 0;
    v67 = 0;
    std::vector<unsigned char>::_Construct_n<>(pDestinationSid, LengthSid);
    if ( !CopySid(LODWORD(pDestinationSid[1]) - LODWORD(pDestinationSid[0]), pDestinationSid[0], pSid) )
      break;
    v22 = (char *)operator new(0x38u);
    v79 = v22;
    *(_OWORD *)v22 = 0;
    *((_OWORD *)v22 + 1) = 0;
    *((_OWORD *)v22 + 2) = 0;
    *((_QWORD *)v22 + 6) = 0;
    v23 = (PSID *)(v22 + 16);
    *((_QWORD *)v22 + 2) = 0;
    *((_QWORD *)v22 + 3) = 0;
    *((_QWORD *)v22 + 4) = 0;
    p_lpMem = v22;
    *(_OWORD *)v22 = *(_OWORD *)v16;
    if ( v22 + 16 != (char *)pDestinationSid )
    {
      v24 = *v23;
      if ( *v23 )
      {
        v25 = (void *)(*((_QWORD *)v22 + 4) - (_QWORD)v24);
        v82 = v25;
        v65 = v24;
        if ( (unsigned __int64)v25 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v65, (unsigned __int64 *)&v82);
          v25 = v82;
          v24 = v65;
        }
        operator delete(v24, (unsigned __int64)v25);
        *v23 = 0;
        *((_QWORD *)v22 + 3) = 0;
        *((_QWORD *)v22 + 4) = 0;
      }
      *v23 = pDestinationSid[0];
      *((PSID *)v22 + 3) = pDestinationSid[1];
      *((_QWORD *)v22 + 4) = v67;
      *(_OWORD *)pDestinationSid = 0;
      v67 = 0;
    }
    *((_DWORD *)v22 + 10) = *(_DWORD *)(v16 + 24);
    *((_DWORD *)v22 + 11) = *(_DWORD *)(v16 + 28);
    *((_DWORD *)v22 + 12) = *(_DWORD *)(v16 + 32);
    if ( v62[1] == v63 )
    {
      std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Emplace_reallocate<std::unique_ptr<NgcTransportContainerInfo>>(
        v62,
        (__int64)v62[1],
        (__int64 *)&p_lpMem);
      v26 = p_lpMem;
    }
    else
    {
      v26 = 0;
      p_lpMem = 0;
      *(_QWORD *)v62[1] = v22;
      v62[1] = (char *)v62[1] + 8;
    }
    if ( v26 )
    {
      v27 = (void *)v26[2];
      if ( v27 )
      {
        v28 = (void *)(v26[4] - (_QWORD)v27);
        v82 = v28;
        v65 = v27;
        if ( (unsigned __int64)v28 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v65, (unsigned __int64 *)&v82);
          v28 = v82;
          v27 = v65;
        }
        operator delete(v27, (unsigned __int64)v28);
        v26[2] = 0;
        v26[3] = 0;
        v26[4] = 0;
      }
      operator delete(v26, 0x38u);
    }
    v29 = pDestinationSid[0];
    if ( pDestinationSid[0] )
    {
      v30 = (void *)(v67 - (unsigned __int64)pDestinationSid[0]);
      v82 = (void *)(v67 - (unsigned __int64)pDestinationSid[0]);
      v65 = pDestinationSid[0];
      if ( v67 - (unsigned __int64)pDestinationSid[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v65, (unsigned __int64 *)&v82);
        v30 = v82;
        v29 = v65;
      }
      operator delete(v29, (unsigned __int64)v30);
      *(_OWORD *)pDestinationSid = 0;
      v67 = 0;
    }
LABEL_35:
    v31 = pSid;
    v32 = pSid == 0;
    pSid = 0;
    if ( !v32 )
      LocalFree(v31);
    v7 = lpMem;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x56E,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\ngc\\ngchandlerclient.cpp",
                v21);
  v57 = pDestinationSid[0];
  if ( pDestinationSid[0] )
  {
    v58 = (void *)(v67 - (unsigned __int64)pDestinationSid[0]);
    p_lpMem = (void *)(v67 - (unsigned __int64)pDestinationSid[0]);
    v82 = pDestinationSid[0];
    if ( v67 - (unsigned __int64)pDestinationSid[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v82, (unsigned __int64 *)&p_lpMem);
      v58 = p_lpMem;
      v57 = v82;
    }
    operator delete(v57, (unsigned __int64)v58);
    *(_OWORD *)pDestinationSid = 0;
    v67 = 0;
  }
  v59 = pSid;
  pSid = 0;
  if ( v59 )
    LocalFree(v59);
  std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(v62);
  wil::details::ScopeExitFnGuard__lambda_53333d2fd512deb7784680597741ccc7___::operator()(v72);
  if ( lpMem )
  {
    MIDL_user_free((void *)lpMem);
    return LastError;
  }
  return LastError;
}

```

## disassembly

```asm
0x180005fd0  mov     [rsp-8+arg_0], rbx
0x180005fd5  mov     [rsp-8+arg_8], rsi
0x180005fda  push    rbp
0x180005fdb  push    rdi
0x180005fdc  push    r12
0x180005fde  push    r14
0x180005fe0  push    r15
0x180005fe2  lea     rbp, [rsp-37h]
0x180005fe7  sub     rsp, 0D0h
0x180005fee  mov     r14, rdx
0x180005ff1  mov     r8, rcx
0x180005ff4  xor     r12d, r12d
0x180005ff7  mov     [rbp+57h+var_88], r12d
0x180005ffb  lea     rcx, [rbp+57h+lpMem]
0x180005fff  call    ?get_unique_ptr@?$rpcmem@U_NGC_RPC_KEY_INFO_LIST@@@@SA?AV?$unique_ptr@U_NGC_RPC_KEY_INFO_LIST@@U?$rpcmem_delete@U_NGC_RPC_KEY_INFO_LIST@@@@@std@@XZ; rpcmem<_NGC_RPC_KEY_INFO_LIST>::get_unique_ptr(void)
0x180006004  nop
0x180006005  mov     [rbp+57h+arg_10], r12
0x180006009  lea     rdx, [rbp+57h+arg_10]
0x18000600d  mov     rcx, r8
0x180006010  call    ?I_NgcHandlerRpcEnumContainers@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEAPEAU_NGC_RPC_CONTAINER_INFO_LIST@@@Z; I_NgcHandlerRpcEnumContainers(std::shared_ptr<NgcUtils::RpcClient> const &,_NGC_RPC_CONTAINER_INFO_LIST * *)
0x180006015  mov     ebx, eax
0x180006017  test    eax, eax
0x180006019  js      loc_180006538
0x18000601f  mov     rax, [rbp+57h+arg_10]
0x180006023  mov     [rbp+57h+arg_18], rax
0x180006027  mov     ebx, 2
0x18000602c  mov     [rbp+57h+var_88], ebx
0x18000602f  mov     [rbp+57h+arg_18], r12
0x180006033  mov     rcx, [rbp+57h+lpMem]; void *
0x180006037  mov     [rbp+57h+lpMem], rax
0x18000603b  test    rcx, rcx
0x18000603e  jnz     loc_180006650
0x180006044  and     ebx, 0FFFFFFFDh
0x180006047  mov     [rbp+57h+var_88], ebx
0x18000604a  lea     rax, [rbp+57h+lpMem]
0x18000604e  mov     [rbp+57h+arg_10], rax
0x180006052  lea     rdx, [rbp+57h+arg_10]
0x180006056  lea     rcx, [rbp+57h+var_68]
0x18000605a  call    wil__ScopeExitIgnore__lambda_53333d2fd512deb7784680597741ccc7___
0x18000605f  nop
0x180006060  mov     rax, [rbp+57h+lpMem]
0x180006064  test    rax, rax
0x180006067  jz      loc_1800064EF
0x18000606d  xorps   xmm0, xmm0
0x180006070  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x180006075  mov     [rbp+57h+var_B8], r12
0x180006079  mov     rax, [rbp+57h+lpMem]
0x18000607d  mov     edi, [rax]
0x18000607f  test    rdi, rdi
0x180006082  jz      loc_180006108
0x180006088  mov     ecx, edi
0x18000608a  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000608f  mov     rcx, rax
0x180006092  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180006097  mov     rbx, rax
0x18000609a  lea     rax, [rbp+57h+var_C8]
0x18000609e  mov     [rbp+57h+var_40], rax
0x1800060a2  mov     [rbp+57h+var_38], rbx
0x1800060a6  mov     [rbp+57h+var_30], rdi
0x1800060aa  mov     r8, [rbp+57h+var_C8+8]
0x1800060ae  mov     rdx, [rbp+57h+var_C8]
0x1800060b2  mov     [rbp+57h+var_58], rbx
0x1800060b6  mov     rcx, rbx
0x1800060b9  mov     [rbp+57h+var_50], rbx
0x1800060bd  lea     rax, [rbp+57h+var_C8]
0x1800060c1  mov     [rbp+57h+var_48], rax
0x1800060c5  cmp     rdx, r8
0x1800060c8  jnz     loc_18000665A
0x1800060ce  mov     [rbp+57h+var_58], rcx
0x1800060d2  mov     rdx, rcx
0x1800060d5  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NgcTransportContainerInfo>>>(std::unique_ptr<NgcTransportContainerInfo> *,std::unique_ptr<NgcTransportContainerInfo> * const,std::allocator<std::unique_ptr<NgcTransportContainerInfo>> &)
0x1800060da  mov     [rbp+57h+var_38], r12
0x1800060de  mov     rcx, [rbp+57h+var_C8]
0x1800060e2  test    rcx, rcx
0x1800060e5  jnz     loc_180006679
0x1800060eb  mov     [rbp+57h+var_C8], rbx
0x1800060ef  mov     [rbp+57h+var_C8+8], rbx
0x1800060f3  lea     rax, [rbx+rdi*8]
0x1800060f7  mov     [rbp+57h+var_B8], rax
0x1800060fb  lea     rcx, [rbp+57h+var_40]
0x1800060ff  call    ??1_Simple_reallocation_guard@?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x180006104  mov     rax, [rbp+57h+lpMem]
0x180006108  mov     edi, r12d
0x18000610b  cmp     edi, [rax]
0x18000610d  jnb     loc_180006317
0x180006113  mov     ecx, edi
0x180006115  lea     rdx, [rcx+rcx*4]
0x180006119  mov     rcx, [rax+8]
0x18000611d  lea     r15, [rcx+rdx*8]
0x180006121  mov     [rbp+57h+pSid], r12
0x180006125  lea     rax, [rbp+57h+pSid]
0x180006129  mov     [rbp+57h+var_80], rax
0x18000612d  mov     [rbp+57h+Sid], r12
0x180006131  mov     [rbp+57h+var_70], 1
0x180006135  lea     rdx, [rbp+57h+Sid]; Sid
0x180006139  mov     rcx, [r15+10h]; StringSid
0x18000613d  call    cs:__imp_ConvertStringSidToSidW
0x180006143  mov     ebx, eax
0x180006145  cmp     [rbp+57h+var_70], 0
0x180006149  jz      short loc_180006164
0x18000614b  mov     r8, [rbp+57h+var_80]
0x18000614f  mov     rcx, [r8]; hMem
0x180006152  mov     rdx, [rbp+57h+Sid]
0x180006156  mov     [r8], rdx
0x180006159  test    rcx, rcx
0x18000615c  jz      short loc_180006164
0x18000615e  call    cs:__imp_LocalFree
0x180006164  test    ebx, ebx
0x180006166  jz      loc_1800065A8
0x18000616c  mov     rcx, [rbp+57h+pSid]; pSid
0x180006170  call    cs:__imp_GetLengthSid
0x180006176  xorps   xmm0, xmm0
0x180006179  movdqu  xmmword ptr [rbp+57h+pDestinationSid], xmm0
0x18000617e  mov     [rbp+57h+var_90], r12
0x180006182  mov     edx, eax
0x180006184  lea     rcx, [rbp+57h+pDestinationSid]
0x180006188  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18000618d  nop
0x18000618e  mov     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x180006192  mov     ecx, dword ptr [rbp+57h+pDestinationSid+8]
0x180006195  sub     ecx, edx; nDestinationSidLength
0x180006197  mov     r8, [rbp+57h+pSid]; pSourceSid
0x18000619b  call    cs:__imp_CopySid
0x1800061a1  test    eax, eax
0x1800061a3  jz      loc_1800065C2
0x1800061a9  mov     ecx, 38h ; '8'; Size
0x1800061ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061b3  mov     rsi, rax
0x1800061b6  mov     [rbp+57h+var_28], rax
0x1800061ba  xorps   xmm0, xmm0
0x1800061bd  xor     eax, eax
0x1800061bf  movups  xmmword ptr [rsi], xmm0
0x1800061c2  movups  xmmword ptr [rsi+10h], xmm0
0x1800061c6  movups  xmmword ptr [rsi+20h], xmm0
0x1800061ca  mov     [rsi+30h], rax
0x1800061ce  lea     rbx, [rsi+10h]
0x1800061d2  mov     [rbx], r12
0x1800061d5  mov     [rbx+8], r12
0x1800061d9  mov     [rbx+10h], r12
0x1800061dd  mov     [rbp+57h+arg_10], rsi
0x1800061e1  movups  xmm0, xmmword ptr [r15]
0x1800061e5  movups  xmmword ptr [rsi], xmm0
0x1800061e8  lea     rax, [rbp+57h+pDestinationSid]
0x1800061ec  cmp     rbx, rax
0x1800061ef  jz      short loc_180006248
0x1800061f1  mov     rcx, [rbx]; void *
0x1800061f4  test    rcx, rcx
0x1800061f7  jz      short loc_180006225
0x1800061f9  mov     rdx, [rbx+10h]
0x1800061fd  sub     rdx, rcx; unsigned __int64
0x180006200  mov     [rbp+57h+arg_18], rdx
0x180006204  mov     [rbp+57h+var_A8], rcx
0x180006208  cmp     rdx, 1000h
0x18000620f  jnb     loc_18000669B
0x180006215  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000621a  mov     [rbx], r12
0x18000621d  mov     [rbx+8], r12
0x180006221  mov     [rbx+10h], r12
0x180006225  mov     rax, [rbp+57h+pDestinationSid]
0x180006229  mov     [rbx], rax
0x18000622c  mov     rax, [rbp+57h+pDestinationSid+8]
0x180006230  mov     [rbx+8], rax
0x180006234  mov     rax, [rbp+57h+var_90]
0x180006238  mov     [rbx+10h], rax
0x18000623c  xorps   xmm0, xmm0
0x18000623f  movdqu  xmmword ptr [rbp+57h+pDestinationSid], xmm0
0x180006244  mov     [rbp+57h+var_90], r12
0x180006248  mov     eax, [r15+18h]
0x18000624c  mov     [rsi+28h], eax
0x18000624f  mov     eax, [r15+1Ch]
0x180006253  mov     [rsi+2Ch], eax
0x180006256  mov     eax, [r15+20h]
0x18000625a  mov     [rsi+30h], eax
0x18000625d  mov     rdx, [rbp+57h+var_C8+8]
0x180006261  cmp     rdx, [rbp+57h+var_B8]
0x180006265  jz      loc_1800066B5
0x18000626b  mov     rbx, r12
0x18000626e  mov     [rbp+57h+arg_10], rbx
0x180006272  mov     [rdx], rsi
0x180006275  add     [rbp+57h+var_C8+8], 8
0x18000627a  test    rbx, rbx
0x18000627d  jz      short loc_1800062C3
0x18000627f  mov     rcx, [rbx+10h]; void *
0x180006283  test    rcx, rcx
0x180006286  jz      short loc_1800062B5
0x180006288  mov     rdx, [rbx+20h]
0x18000628c  sub     rdx, rcx; unsigned __int64
0x18000628f  mov     [rbp+57h+arg_18], rdx
0x180006293  mov     [rbp+57h+var_A8], rcx
0x180006297  cmp     rdx, 1000h
0x18000629e  jnb     loc_1800066CB
0x1800062a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800062a9  mov     [rbx+10h], r12
0x1800062ad  mov     [rbx+18h], r12
0x1800062b1  mov     [rbx+20h], r12
0x1800062b5  mov     edx, 38h ; '8'; unsigned __int64
0x1800062ba  mov     rcx, rbx; void *
0x1800062bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800062c2  nop
0x1800062c3  mov     rcx, [rbp+57h+pDestinationSid]; void *
0x1800062c7  test    rcx, rcx
0x1800062ca  jz      short loc_1800062F9
0x1800062cc  mov     rdx, [rbp+57h+var_90]
0x1800062d0  sub     rdx, rcx; unsigned __int64
0x1800062d3  mov     [rbp+57h+arg_18], rdx
0x1800062d7  mov     [rbp+57h+var_A8], rcx
0x1800062db  cmp     rdx, 1000h
0x1800062e2  jnb     loc_1800066E5
0x1800062e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800062ed  xorps   xmm0, xmm0
0x1800062f0  movdqu  xmmword ptr [rbp+57h+pDestinationSid], xmm0
0x1800062f5  mov     [rbp+57h+var_90], r12
0x1800062f9  mov     rcx, [rbp+57h+pSid]; hMem
0x1800062fd  test    rcx, rcx
0x180006300  mov     [rbp+57h+pSid], r12
0x180006304  jz      short loc_18000630C
0x180006306  call    cs:__imp_LocalFree
0x18000630c  inc     edi
0x18000630e  mov     rax, [rbp+57h+lpMem]
0x180006312  jmp     loc_18000610B
0x180006317  lea     rax, [rbp+57h+var_C8]
0x18000631b  cmp     r14, rax
0x18000631e  jz      loc_1800063D8
0x180006324  mov     rbx, [r14]
0x180006327  test    rbx, rbx
0x18000632a  jz      loc_1800063B5
0x180006330  mov     rsi, [r14+8]
0x180006334  cmp     rbx, rsi
0x180006337  jz      short loc_18000638D
0x180006339  mov     rdi, [rbx]
0x18000633c  test    rdi, rdi
0x18000633f  jz      short loc_180006384
0x180006341  mov     rcx, [rdi+10h]; void *
0x180006345  test    rcx, rcx
0x180006348  jz      short loc_180006377
0x18000634a  mov     rdx, [rdi+20h]
0x18000634e  sub     rdx, rcx; unsigned __int64
0x180006351  mov     [rbp+57h+arg_10], rdx
0x180006355  mov     [rbp+57h+arg_18], rcx
0x180006359  cmp     rdx, 1000h
0x180006360  jnb     loc_180006719
0x180006366  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000636b  mov     [rdi+10h], r12
0x18000636f  mov     [rdi+18h], r12
0x180006373  mov     [rdi+20h], r12
0x180006377  mov     edx, 38h ; '8'; unsigned __int64
0x18000637c  mov     rcx, rdi; void *
0x18000637f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006384  add     rbx, 8
0x180006388  cmp     rbx, rsi
0x18000638b  jnz     short loc_180006339
0x18000638d  mov     rcx, [r14]; void *
0x180006390  mov     rdx, [r14+10h]
0x180006394  sub     rdx, rcx
0x180006397  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000639b  mov     [rbp+57h+arg_18], rdx
0x18000639f  mov     [rbp+57h+arg_10], rcx
0x1800063a3  cmp     rdx, 1000h
0x1800063aa  jnb     loc_180006733
0x1800063b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063b5  mov     rax, [rbp+57h+var_C8]
0x1800063b9  mov     [r14], rax
0x1800063bc  mov     rax, [rbp+57h+var_C8+8]
0x1800063c0  mov     [r14+8], rax
0x1800063c4  mov     rax, [rbp+57h+var_B8]
0x1800063c8  mov     [r14+10h], rax
0x1800063cc  xorps   xmm0, xmm0
0x1800063cf  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x1800063d4  mov     [rbp+57h+var_B8], r12
0x1800063d8  mov     rbx, [rbp+57h+var_C8]
0x1800063dc  test    rbx, rbx
0x1800063df  jz      loc_18000647A
0x1800063e5  mov     rsi, [rbp+57h+var_C8+8]
0x1800063e9  cmp     rbx, rsi
0x1800063ec  jz      short loc_180006446
0x1800063ee  mov     rdi, [rbx]
0x1800063f1  test    rdi, rdi
0x1800063f4  jz      short loc_180006439
0x1800063f6  mov     rcx, [rdi+10h]; void *
0x1800063fa  test    rcx, rcx
0x1800063fd  jz      short loc_18000642C
0x1800063ff  mov     rdx, [rdi+20h]
0x180006403  sub     rdx, rcx; unsigned __int64
0x180006406  mov     [rbp+57h+arg_10], rdx
0x18000640a  mov     [rbp+57h+arg_18], rcx
0x18000640e  cmp     rdx, 1000h
0x180006415  jnb     loc_18000674D
0x18000641b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006420  mov     [rdi+10h], r12
0x180006424  mov     [rdi+18h], r12
0x180006428  mov     [rdi+20h], r12
0x18000642c  mov     edx, 38h ; '8'; unsigned __int64
0x180006431  mov     rcx, rdi; void *
0x180006434  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006439  add     rbx, 8
0x18000643d  cmp     rbx, rsi
0x180006440  jnz     short loc_1800063EE
0x180006442  mov     rbx, [rbp+57h+var_C8]
0x180006446  mov     rdx, [rbp+57h+var_B8]
0x18000644a  sub     rdx, rbx
  ... truncated ...
```
