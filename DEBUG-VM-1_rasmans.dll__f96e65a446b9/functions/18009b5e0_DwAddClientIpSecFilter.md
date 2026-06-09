# DwAddClientIpSecFilter

- ea: `0x18009b5e0`
- end: `0x18009bdab`
- name: `DwAddClientIpSecFilter`
- size: `1995`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dbf4`

## callees

- `0x18009a990`
- `0x18009aaec`
- `0x18009abdc`
- `0x18009acc4`
- `0x18009b07c`
- `0x18009b4f8`
- `0x18009b5e0`
- `0x18009d4d4`
- `0x18009d558`
- `0x18009d698`
- `0x18009d7cc`
- `0x18009d8e8`
- `0x18009e368`
- `0x1800e54d8`
- `0x1800e61bc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b874`
- `RPCRT4!UuidCreate` at `0x18009ba46`
- `RPCRT4!UuidCreate` at `0x18009ba6d`
- `RPCRT4!UuidCreate` at `0x18009ba46`
- `RPCRT4!UuidCreate` at `0x18009ba6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009b6f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009b866`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009b6f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009b866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bd46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bd5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bd46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009bd5c`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009bcce`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009bcce`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18009bb1a`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x18009bb1a`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18009bce7`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18009bce7`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18009baaa`
- `fwpuclnt!FwpmProviderContextAdd2` at `0x18009baaa`

## string_xrefs

- `0x18009b76d`: `DwAddClientIpSecFilter: Filter already exists.`
- `0x18009b757`: `DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.`
- `0x18009ba52`: `UuidCreate failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DwAddClientIpSecFilter(__int64 a1, unsigned int a2, int a3, __int64 a4, DWORD cbData, __int64 a6)
{
  _DWORD *v8; // rsi
  char *v9; // r12
  unsigned int v10; // r14d
  __int64 v11; // rcx
  DWORD LastError; // eax
  __int64 ServerNode; // rax
  __int64 v14; // rbx
  DWORD v15; // ebx
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rcx
  HLOCAL v19; // rbx
  const CHAR *v20; // rcx
  int v21; // r9d
  int v22; // r9d
  unsigned int i; // r15d
  int v25; // [rsp+50h] [rbp-408h]
  int v26; // [rsp+58h] [rbp-400h] BYREF
  int v27; // [rsp+5Ch] [rbp-3FCh] BYREF
  _DWORD v28[2]; // [rsp+60h] [rbp-3F8h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-3F0h] BYREF
  int v30; // [rsp+70h] [rbp-3E8h]
  int v31; // [rsp+74h] [rbp-3E4h] BYREF
  int v32; // [rsp+78h] [rbp-3E0h] BYREF
  int v33[4]; // [rsp+80h] [rbp-3D8h] BYREF
  int v34; // [rsp+90h] [rbp-3C8h]
  _DWORD *v35; // [rsp+A0h] [rbp-3B8h] BYREF
  char *v36; // [rsp+A8h] [rbp-3B0h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-3A8h] BYREF
  unsigned int v38; // [rsp+C8h] [rbp-390h]
  __int64 v39; // [rsp+D0h] [rbp-388h]
  __int64 v40; // [rsp+D8h] [rbp-380h] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-378h]
  __int128 v42; // [rsp+E8h] [rbp-370h] BYREF
  __int128 v43; // [rsp+F8h] [rbp-360h] BYREF
  __int128 v44; // [rsp+108h] [rbp-350h]
  __int128 v45; // [rsp+118h] [rbp-340h]
  __int64 v46; // [rsp+130h] [rbp-328h]
  _OWORD v47[2]; // [rsp+140h] [rbp-318h] BYREF
  int v48; // [rsp+160h] [rbp-2F8h]
  UUID v49; // [rsp+170h] [rbp-2E8h] BYREF
  const wchar_t *v50; // [rsp+180h] [rbp-2D8h]
  int v51; // [rsp+1B0h] [rbp-2A8h]
  __int128 *v52; // [rsp+1B8h] [rbp-2A0h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+1D0h] [rbp-288h] BYREF
  _BYTE Src[480]; // [rsp+230h] [rbp-228h] BYREF

  v46 = a1;
  v38 = a2;
  v39 = a6;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset_0(&v49, 0, 0x58u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v36 = 0;
  v10 = 0;
  v29 = 0;
  v28[0] = 0;
  v32 = 0;
  v31 = 0;
  v28[1] = 0;
  v27 = 0;
  v25 = 0;
  v40 = 0;
  RasIpsecTrace("DwAddClientIpSecFilter.");
  v42 = 0;
  v37 = 0;
  hMem = LocalAlloc(0x40u, 0x118u);
  if ( !hMem )
  {
    RasIpsecTrace("DwAddclientipsecfilter: failed to alloc");
    LastError = GetLastError();
LABEL_49:
    v15 = LastError;
    goto LABEL_50;
  }
  *(_OWORD *)v33 = *(_OWORD *)a1;
  v34 = *(_DWORD *)(a1 + 16);
  ServerNode = FindServerNode(v11, v33);
  v14 = ServerNode;
  if ( ServerNode )
  {
    if ( a2 == *(_DWORD *)(ServerNode + 76) )
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Filter already exists.");
      ++*(_DWORD *)(v14 + 52);
      v15 = 0;
    }
    else
    {
      RasIpsecTrace("DwAddClientIpSecFilter: Already a filter with a different encryption(%d) type exists for ths dest address.");
      v15 = 87;
    }
    goto LABEL_50;
  }
  v15 = 87;
  v30 = 87;
  if ( cbData > 0xA )
  {
    RasIpsecTrace("DwAddClientIpSecFilter: Invalid value of dwNumPolicy");
LABEL_50:
    v17 = 0;
    goto LABEL_51;
  }
  v26 = 0;
  if ( a2 >= 2 )
  {
    v16 = a2 - 2;
    if ( a2 - 2 > 1 )
      goto LABEL_48;
  }
  if ( !a3 )
  {
    v15 = GenerateCertificatesList(0, &v35, &v29, &v26);
    v30 = v15;
    v10 = v29;
    if ( v15 || !v29 || v26 )
    {
      RasIpsecTrace("Failed to generate certificate list. rc=0x%x, Count=%d, MyStoreEmpty=%d");
      if ( !v10 || v26 )
        v15 = 766;
      v8 = v35;
      goto LABEL_25;
    }
    v8 = v35;
    if ( v35 )
      v35[14] |= 2u;
    if ( !a3 )
    {
LABEL_27:
      v15 = BuildIpsecOffers(a2, &v36, v28);
      if ( v15 )
      {
        RasIpsecTrace("BuildIpsecOffers for ipsec proposals failed with 0x%x");
        v9 = v36;
        goto LABEL_25;
      }
      v9 = v36;
      BuildQMPolicy((unsigned int)&Uuid, (unsigned int)v47, a2, (_DWORD)v36, v28[0], g_dwIpsecUdpEncapsulation, cbData);
      v19 = hMem;
      BuildMMOffers((int)hMem, (int)&v32, (int)&v31, 0, v39, cbData, 0);
      LODWORD(v44) = 0;
      v45 = (unsigned int)v31;
      LODWORD(v43) = 28800;
      *((_QWORD *)&v44 + 1) = v19;
      DWORD1(v44) = v32;
      *((_QWORD *)&v43 + 1) = v8;
      DWORD1(v43) = v10;
      memset_0(&v49, 0, 0x58u);
      v51 = 5;
      v52 = &v43;
      v50 = L"L2TP Main Mode Policy";
      v15 = UuidCreate(&Uuid.providerContextKey);
      if ( v15 || (v15 = UuidCreate(&v49)) != 0 )
      {
        v20 = "UuidCreate failed with 0x%x";
LABEL_31:
        RasIpsecTrace(v20);
        goto LABEL_25;
      }
      v15 = FwpmTransactionBegin0Wrapper();
      if ( v15 )
      {
        v20 = "FwpmTransactionBegin0 failed with 0x%x";
        goto LABEL_31;
      }
      v25 = 1;
      v15 = FwpmProviderContextAdd2(gFwpEngineHandle, &v49, 0, 0);
      if ( v15 )
      {
        v20 = "FwpmProviderContextAdd0 for MM policy failed with 0x%x";
        goto LABEL_31;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v15 = BuildCMMFilter(&v42, &v49, v33);
      if ( v15 )
      {
        v20 = "BuildCMMFilter for MM filter failed with 0x%x";
        goto LABEL_31;
      }
      v15 = FwpmProviderContextAdd0(gFwpEngineHandle, &Uuid, 0, 0);
      if ( v15 )
      {
        v20 = "FwpmProviderContextAdd0 for QM policy failed with 0x%x";
        goto LABEL_31;
      }
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      v15 = BuildCTxFilter((unsigned int)&v37, (unsigned int)&Uuid, (unsigned int)v33, v21, 1);
      if ( v15 )
      {
        v20 = "BuildCTxFilter for QM filter failed with 0x%x";
        goto LABEL_31;
      }
      v15 = AddFilters(&v37, Src, &v27, 0);
      if ( v15
        || (WfpFilterListDestroy(&v37, (char *)&v37 + 8),
            v37 = 0,
            *(_OWORD *)v33 = *(_OWORD *)a1,
            v34 = *(_DWORD *)(a1 + 16),
            BuildCTxFilter((unsigned int)&v37, (unsigned int)&Uuid, (unsigned int)v33, v22, 0),
            (v15 = AddFilters(&v37, Src, &v27, &v40)) != 0) )
      {
        v20 = "AddFilters for QM filter failed with 0x%x";
        goto LABEL_31;
      }
      v15 = AddFilters(&v42, Src, &v27, 0);
      if ( v15 )
      {
        v20 = "AddFilters for MM filter failed with 0x%x";
        goto LABEL_31;
      }
LABEL_48:
      *(_OWORD *)v33 = *(_OWORD *)a1;
      v34 = *(_DWORD *)(a1 + 16);
      gpIpSecSrvList = AddNodeToServerList(v16, a2, (int)v33, (int)&v49, (__int64)&Uuid, Src, v27, v40);
      LastError = FwpmTransactionCommit0(gFwpEngineHandle);
      goto LABEL_49;
    }
  }
  if ( v8 || (v8 = LocalAlloc(0x40u, 0x40u)) != 0 )
  {
    v18 = 10LL * v10;
    v8[2 * v18] = 0;
    *(_QWORD *)&v8[2 * v18 + 4] = a4;
    v8[2 * v18 + 2] = a3;
    ++v10;
    goto LABEL_27;
  }
  v15 = GetLastError();
LABEL_25:
  v17 = v25;
LABEL_51:
  if ( v15 && v17 )
    FwpmTransactionAbort0(gFwpEngineHandle);
  WfpFilterListDestroy(&v37, (char *)&v37 + 8);
  WfpFilterListDestroy(&v42, (char *)&v42 + 8);
  if ( v9 )
  {
    for ( i = 0; i < v28[0]; ++i )
      WfpClearIpsecProposal(&v9[32 * i]);
    LocalFree(v9);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    FreeAuthInfoList(v8);
  RasIpsecTrace("DwAddClientIpSecFilter: rc=0x%x");
  return v15;
}

```

## disassembly

```asm
0x18009b5e0  mov     [rsp+arg_18], r9
0x18009b5e5  mov     [rsp+arg_10], r8d
0x18009b5ea  push    rbx
0x18009b5eb  push    rsi
0x18009b5ec  push    rdi
0x18009b5ed  push    r12
0x18009b5ef  push    r13
0x18009b5f1  push    r14
0x18009b5f3  push    r15
0x18009b5f5  sub     rsp, 420h
0x18009b5fc  mov     rax, cs:__security_cookie
0x18009b603  xor     rax, rsp
0x18009b606  mov     [rsp+458h+var_48], rax
0x18009b60e  mov     r13d, edx
0x18009b611  mov     r15, rcx
0x18009b614  mov     [rsp+458h+var_328], rcx
0x18009b61c  mov     [rsp+458h+var_390], edx
0x18009b623  mov     rax, [rsp+458h+arg_28]
0x18009b62b  mov     [rsp+458h+var_388], rax
0x18009b633  xor     eax, eax
0x18009b635  xorps   xmm0, xmm0
0x18009b638  movups  [rsp+458h+var_318], xmm0
0x18009b640  movups  [rsp+458h+var_308], xmm0
0x18009b648  mov     [rsp+458h+var_2F8], eax
0x18009b64f  xorps   xmm1, xmm1
0x18009b652  movups  [rsp+458h+var_360], xmm1
0x18009b65a  movups  [rsp+458h+var_350], xmm1
0x18009b662  movups  [rsp+458h+var_340], xmm1
0x18009b66a  lea     ebx, [rax+58h]
0x18009b66d  mov     r8d, ebx; Size
0x18009b670  xor     edx, edx; Val
0x18009b672  lea     rcx, [rsp+458h+var_2E8]; void *
0x18009b67a  call    memset_0
0x18009b67f  mov     r8d, ebx; Size
0x18009b682  xor     edx, edx; Val
0x18009b684  lea     rcx, [rsp+458h+Uuid]; void *
0x18009b68c  call    memset_0
0x18009b691  xor     edi, edi
0x18009b693  mov     esi, edi
0x18009b695  mov     [rsp+458h+var_3B8], rdi
0x18009b69d  mov     r12d, edi
0x18009b6a0  mov     [rsp+458h+var_3B0], rdi
0x18009b6a8  mov     r14d, edi
0x18009b6ab  mov     [rsp+458h+var_3F0], edi
0x18009b6af  mov     [rsp+458h+var_3F8], edi
0x18009b6b3  mov     [rsp+458h+var_3E0], edi
0x18009b6b7  mov     [rsp+458h+var_3E4], edi
0x18009b6bb  mov     [rsp+458h+var_3F4], edi
0x18009b6bf  mov     [rsp+458h+var_3FC], edi
0x18009b6c3  mov     [rsp+458h+var_408], edi
0x18009b6c7  mov     [rsp+458h+var_380], rdi
0x18009b6cf  lea     rcx, aDwaddclientips_1; "DwAddClientIpSecFilter."
0x18009b6d6  call    RasIpsecTrace
0x18009b6db  xorps   xmm0, xmm0
0x18009b6de  movups  [rsp+458h+var_370], xmm0
0x18009b6e6  xorps   xmm1, xmm1
0x18009b6e9  movups  [rsp+458h+var_3A8], xmm1
0x18009b6f1  mov     edx, 118h; uBytes
0x18009b6f6  lea     ecx, [rbx-18h]; uFlags
0x18009b6f9  call    cs:__imp_LocalAlloc
0x18009b6ff  mov     [rsp+458h+hMem], rax
0x18009b707  test    rax, rax
0x18009b70a  jnz     short loc_18009B723
0x18009b70c  lea     rcx, aDwaddclientips; "DwAddclientipsecfilter: failed to alloc"
0x18009b713  call    RasIpsecTrace
0x18009b718  call    cs:__imp_GetLastError
0x18009b71e  jmp     loc_18009BCD4
0x18009b723  movaps  xmm0, xmmword ptr [r15]
0x18009b727  movaps  xmmword ptr [rsp+458h+var_3D8], xmm0
0x18009b72f  mov     eax, [r15+10h]
0x18009b733  mov     [rsp+458h+var_3C8], eax
0x18009b73a  lea     rdx, [rsp+458h+var_3D8]
0x18009b742  call    FindServerNode
0x18009b747  mov     rbx, rax
0x18009b74a  test    rax, rax
0x18009b74d  jz      short loc_18009B783
0x18009b74f  mov     edx, [rax+4Ch]
0x18009b752  cmp     r13d, edx
0x18009b755  jz      short loc_18009B76D
0x18009b757  lea     rcx, aDwaddclientips_2; "DwAddClientIpSecFilter: Already a filte"...
0x18009b75e  call    RasIpsecTrace
0x18009b763  mov     ebx, 57h ; 'W'
0x18009b768  jmp     loc_18009BCD6
0x18009b76d  lea     rcx, aDwaddclientips_0; "DwAddClientIpSecFilter: Filter already "...
0x18009b774  call    RasIpsecTrace
0x18009b779  inc     dword ptr [rbx+34h]
0x18009b77c  mov     ebx, edi
0x18009b77e  jmp     loc_18009BCD6
0x18009b783  mov     ebx, 57h ; 'W'
0x18009b788  mov     [rsp+458h+var_3E8], ebx
0x18009b78c  cmp     [rsp+458h+cbData], 0Ah
0x18009b794  jbe     short loc_18009B7A7
0x18009b796  lea     rcx, aDwaddclientips_3; "DwAddClientIpSecFilter: Invalid value o"...
0x18009b79d  call    RasIpsecTrace
0x18009b7a2  jmp     loc_18009BCD6
0x18009b7a7  mov     [rsp+458h+var_400], edi
0x18009b7ab  mov     ecx, r13d
0x18009b7ae  test    r13d, r13d
0x18009b7b1  jz      short loc_18009B7C6
0x18009b7b3  sub     ecx, 1
0x18009b7b6  jz      short loc_18009B7C6
0x18009b7b8  sub     ecx, 1; int
0x18009b7bb  jz      short loc_18009B7C6
0x18009b7bd  cmp     ecx, 1
0x18009b7c0  jnz     loc_18009BC62
0x18009b7c6  mov     eax, [rsp+458h+arg_10]
0x18009b7cd  test    eax, eax
0x18009b7cf  jnz     loc_18009B85C
0x18009b7d5  lea     r9, [rsp+458h+var_400]
0x18009b7da  lea     r8, [rsp+458h+var_3F0]
0x18009b7df  lea     rdx, [rsp+458h+var_3B8]
0x18009b7e7  xor     ecx, ecx
0x18009b7e9  call    GenerateCertificatesList
0x18009b7ee  mov     ebx, eax
0x18009b7f0  mov     [rsp+458h+var_3E8], eax
0x18009b7f4  jmp     short loc_18009B828
0x18009b7f6  mov     edx, [rsp+458h+var_3F4]
0x18009b7fa  lea     rcx, aGeneratecertif; "GenerateCertificatesList raised excepti"...
0x18009b801  call    RasIpsecTrace
0x18009b806  xor     edi, edi
0x18009b808  mov     ebx, [rsp+458h+var_3E8]
0x18009b80c  mov     r12, [rsp+458h+var_3B0]
0x18009b814  mov     [rsp+458h+var_408], edi
0x18009b818  mov     r15, [rsp+458h+var_328]
0x18009b820  mov     r13d, [rsp+458h+var_390]
0x18009b828  mov     r14d, [rsp+458h+var_3F0]
0x18009b82d  test    ebx, ebx
0x18009b82f  jnz     short loc_18009B87E
0x18009b831  test    r14d, r14d
0x18009b834  jz      short loc_18009B87E
0x18009b836  cmp     [rsp+458h+var_400], edi
0x18009b83a  jnz     short loc_18009B87E
0x18009b83c  mov     rsi, [rsp+458h+var_3B8]
0x18009b844  mov     eax, [rsp+458h+arg_10]
0x18009b84b  test    rsi, rsi
0x18009b84e  jz      short loc_18009B854
0x18009b850  or      dword ptr [rsi+38h], 2
0x18009b854  test    eax, eax
0x18009b856  jz      loc_18009B8DD
0x18009b85c  test    rsi, rsi
0x18009b85f  jnz     short loc_18009B8B5
0x18009b861  lea     edx, [rsi+40h]; uBytes
0x18009b864  mov     ecx, edx; uFlags
0x18009b866  call    cs:__imp_LocalAlloc
0x18009b86c  mov     rsi, rax
0x18009b86f  test    rax, rax
0x18009b872  jnz     short loc_18009B8B5
0x18009b874  call    cs:__imp_GetLastError
0x18009b87a  mov     ebx, eax
0x18009b87c  jmp     short loc_18009B8AC
0x18009b87e  mov     r9d, [rsp+458h+var_400]
0x18009b883  mov     r8d, r14d
0x18009b886  mov     edx, ebx
0x18009b888  lea     rcx, aFailedToGenera; "Failed to generate certificate list. rc"...
0x18009b88f  call    RasIpsecTrace
0x18009b894  test    r14d, r14d
0x18009b897  jz      short loc_18009B89F
0x18009b899  cmp     [rsp+458h+var_400], edi
0x18009b89d  jz      short loc_18009B8A4
0x18009b89f  mov     ebx, 2FEh
0x18009b8a4  mov     rsi, [rsp+458h+var_3B8]
0x18009b8ac  mov     eax, [rsp+458h+var_408]
0x18009b8b0  jmp     loc_18009BCD8
0x18009b8b5  mov     eax, r14d
0x18009b8b8  lea     rcx, [rax+rax*4]
0x18009b8bc  add     rcx, rcx
0x18009b8bf  mov     [rsi+rcx*8], edi
0x18009b8c2  mov     rax, [rsp+458h+arg_18]
0x18009b8ca  mov     [rsi+rcx*8+10h], rax
0x18009b8cf  mov     eax, [rsp+458h+arg_10]
0x18009b8d6  mov     [rsi+rcx*8+8], eax
0x18009b8da  inc     r14d
0x18009b8dd  mov     eax, [rsp+458h+cbData]
0x18009b8e4  mov     [rsp+458h+var_410], eax
0x18009b8e8  mov     rax, [rsp+458h+var_388]
0x18009b8f0  mov     [rsp+458h+var_418], rax
0x18009b8f5  mov     dword ptr [rsp+458h+Src], 0E10h
0x18009b8fd  mov     dword ptr [rsp+458h+var_438], 3D090h
0x18009b905  lea     r8, [rsp+458h+var_3F8]
0x18009b90a  lea     rdx, [rsp+458h+var_3B0]
0x18009b912  mov     ecx, r13d
0x18009b915  call    BuildIpsecOffers
0x18009b91a  mov     ebx, eax
0x18009b91c  test    eax, eax
0x18009b91e  jz      short loc_18009B93B
0x18009b920  mov     edx, eax
0x18009b922  lea     rcx, aBuildipsecoffe; "BuildIpsecOffers for ipsec proposals fa"...
0x18009b929  call    RasIpsecTrace
0x18009b92e  mov     r12, [rsp+458h+var_3B0]
0x18009b936  jmp     loc_18009B8AC
0x18009b93b  mov     ebx, [rsp+458h+cbData]
0x18009b942  mov     dword ptr [rsp+458h+var_428], ebx
0x18009b946  mov     eax, cs:g_dwIpsecUdpEncapsulation
0x18009b94c  mov     dword ptr [rsp+458h+Src], eax
0x18009b950  mov     eax, [rsp+458h+var_3F8]
0x18009b954  mov     dword ptr [rsp+458h+var_438], eax
0x18009b958  mov     r12, [rsp+458h+var_3B0]
0x18009b960  mov     r9, r12
0x18009b963  mov     r8d, r13d
0x18009b966  lea     rdx, [rsp+458h+var_318]
0x18009b96e  lea     rcx, [rsp+458h+Uuid]
0x18009b976  call    BuildQMPolicy
0x18009b97b  mov     [rsp+458h+var_428], rdi; __int64
0x18009b980  mov     dword ptr [rsp+458h+Src], ebx; cbData
0x18009b984  mov     rax, [rsp+458h+var_388]
0x18009b98c  mov     [rsp+458h+var_438], rax; __int64
0x18009b991  xor     r9d, r9d; int
0x18009b994  lea     r8, [rsp+458h+var_3E4]; int
0x18009b999  lea     rdx, [rsp+458h+var_3E0]; int
0x18009b99e  mov     rbx, [rsp+458h+hMem]
0x18009b9a6  mov     rcx, rbx; int
0x18009b9a9  call    BuildMMOffers
0x18009b9ae  mov     dword ptr [rsp+458h+var_350], edi
0x18009b9b5  mov     dword ptr [rsp+458h+var_340+4], edi
0x18009b9bc  mov     qword ptr [rsp+458h+var_340+8], 708h
0x18009b9c8  mov     eax, [rsp+458h+var_3E4]
0x18009b9cc  mov     dword ptr [rsp+458h+var_340], eax
0x18009b9d3  mov     dword ptr [rsp+458h+var_360], 7080h
0x18009b9de  mov     qword ptr [rsp+458h+var_350+8], rbx
0x18009b9e6  mov     eax, [rsp+458h+var_3E0]
0x18009b9ea  mov     dword ptr [rsp+458h+var_350+4], eax
0x18009b9f1  mov     qword ptr [rsp+458h+var_360+8], rsi
0x18009b9f9  mov     dword ptr [rsp+458h+var_360+4], r14d
0x18009ba01  xor     edx, edx; Val
0x18009ba03  lea     r8d, [rdx+58h]; Size
0x18009ba07  lea     rcx, [rsp+458h+var_2E8]; void *
0x18009ba0f  call    memset_0
0x18009ba14  mov     [rsp+458h+var_2A8], 5
0x18009ba1f  lea     rax, [rsp+458h+var_360]
0x18009ba27  mov     [rsp+458h+var_2A0], rax
0x18009ba2f  lea     rax, aL2tpMainModePo; "L2TP Main Mode Policy"
0x18009ba36  mov     [rsp+458h+var_2D8], rax
0x18009ba3e  lea     rcx, [rsp+458h+Uuid]; Uuid
0x18009ba46  call    cs:__imp_UuidCreate
0x18009ba4c  mov     ebx, eax
0x18009ba4e  test    eax, eax
0x18009ba50  jz      short loc_18009BA65
0x18009ba52  lea     rcx, aUuidcreateFail; "UuidCreate failed with 0x%x"
0x18009ba59  mov     edx, eax
0x18009ba5b  call    RasIpsecTrace
0x18009ba60  jmp     loc_18009B8AC
0x18009ba65  lea     rcx, [rsp+458h+var_2E8]; Uuid
0x18009ba6d  call    cs:__imp_UuidCreate
0x18009ba73  mov     ebx, eax
0x18009ba75  test    eax, eax
0x18009ba77  jnz     short loc_18009BA52
0x18009ba79  call    FwpmTransactionBegin0Wrapper
0x18009ba7e  mov     ebx, eax
0x18009ba80  test    eax, eax
0x18009ba82  jz      short loc_18009BA8D
0x18009ba84  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18009ba8b  jmp     short loc_18009BA59
0x18009ba8d  mov     [rsp+458h+var_408], 1
0x18009ba95  xor     r9d, r9d
0x18009ba98  xor     r8d, r8d
0x18009ba9b  lea     rdx, [rsp+458h+var_2E8]
0x18009baa3  mov     rcx, cs:gFwpEngineHandle
0x18009baaa  call    cs:__imp_FwpmProviderContextAdd2
0x18009bab0  mov     ebx, eax
0x18009bab2  test    eax, eax
0x18009bab4  jz      short loc_18009BABF
0x18009bab6  lea     rcx, aFwpmproviderco; "FwpmProviderContextAdd0 for MM policy f"...
0x18009babd  jmp     short loc_18009BA59
0x18009babf  movaps  xmm0, xmmword ptr [r15]
0x18009bac3  movaps  xmmword ptr [rsp+458h+var_3D8], xmm0
0x18009bacb  mov     eax, [r15+10h]
0x18009bacf  mov     [rsp+458h+var_3C8], eax
0x18009bad6  lea     r8, [rsp+458h+var_3D8]
0x18009bade  lea     rdx, [rsp+458h+var_2E8]
0x18009bae6  lea     rcx, [rsp+458h+var_370]
0x18009baee  call    BuildCMMFilter
0x18009baf3  mov     ebx, eax
0x18009baf5  test    eax, eax
0x18009baf7  jz      short loc_18009BB05
0x18009baf9  lea     rcx, aBuildcmmfilter; "BuildCMMFilter for MM filter failed wit"...
0x18009bb00  jmp     loc_18009BA59
0x18009bb05  xor     r9d, r9d; id
0x18009bb08  xor     r8d, r8d; sd
0x18009bb0b  lea     rdx, [rsp+458h+Uuid]; providerContext
0x18009bb13  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009bb1a  call    cs:__imp_FwpmProviderContextAdd0
0x18009bb20  mov     ebx, eax
0x18009bb22  test    eax, eax
0x18009bb24  jz      short loc_18009BB32
0x18009bb26  lea     rcx, aFwpmproviderco_1; "FwpmProviderContextAdd0 for QM policy f"...
0x18009bb2d  jmp     loc_18009BA59
0x18009bb32  movaps  xmm0, xmmword ptr [r15]
0x18009bb36  movaps  xmmword ptr [rsp+458h+var_3D8], xmm0
0x18009bb3e  mov     eax, [r15+10h]
0x18009bb42  mov     [rsp+458h+var_3C8], eax
0x18009bb49  mov     dword ptr [rsp+458h+var_438], 1
0x18009bb51  lea     r8, [rsp+458h+var_3D8]
0x18009bb59  lea     rdx, [rsp+458h+Uuid]
0x18009bb61  lea     rcx, [rsp+458h+var_3A8]
0x18009bb69  call    BuildCTxFilter
0x18009bb6e  mov     ebx, eax
0x18009bb70  test    eax, eax
0x18009bb72  jz      short loc_18009BB80
0x18009bb74  lea     rcx, aBuildctxfilter; "BuildCTxFilter for QM filter failed wit"...
0x18009bb7b  jmp     loc_18009BA59
  ... truncated ...
```
