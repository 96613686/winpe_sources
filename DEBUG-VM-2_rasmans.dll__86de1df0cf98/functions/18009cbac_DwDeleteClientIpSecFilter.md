# DwDeleteClientIpSecFilter

- ea: `0x18009cbac`
- end: `0x18009cd68`
- name: `DwDeleteClientIpSecFilter`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180039c00`

## callees

- `0x18009cbac`
- `0x18009d4d4`
- `0x18009d558`
- `0x18009d698`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x18009cc79`
- `RPCRT4!UuidIsNil` at `0x18009ccae`
- `RPCRT4!UuidIsNil` at `0x18009cc79`
- `RPCRT4!UuidIsNil` at `0x18009ccae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd3b`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18009cc51`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18009cc51`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009cce1`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009cce1`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009cc8e`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ccc2`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009cc8e`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ccc2`

## string_xrefs

- `0x18009cc5d`: `FwpmFilterDeleteByKey0: dwStatus=0x%x`
- `0x18009ccce`: `FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x`
- `0x18009cc9a`: `FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x`
- `0x18009cd4a`: `DwDeleteClientIpSecFilter: dwStatus=0x%x`

## pseudocode

```c
__int64 __fastcall DwDeleteClientIpSecFilter(__int128 *a1)
{
  __int64 ServerNode; // rax
  __int64 v2; // rbx
  DWORD v3; // esi
  unsigned int v4; // eax
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // edi
  unsigned int i; // edi
  __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  void *v13; // rcx
  __int128 v14; // [rsp+20h] [rbp-28h] BYREF
  int v15; // [rsp+30h] [rbp-18h]
  RPC_STATUS Status; // [rsp+50h] [rbp+8h] BYREF

  v14 = *a1;
  Status = 0;
  v15 = *((_DWORD *)a1 + 4);
  ServerNode = FindServerNode(a1, &v14);
  v2 = ServerNode;
  if ( ServerNode )
  {
    v4 = *(_DWORD *)(ServerNode + 52);
    v3 = 0;
    if ( v4 > 1 )
    {
      *(_DWORD *)(v2 + 52) = v4 - 1;
LABEL_33:
      RasIpsecTrace("DwDeleteClientIpSecFilter: dwStatus=0x%x");
      return v3;
    }
    v5 = *(_DWORD *)(v2 + 76);
    if ( !v5 || (v6 = v5 - 1) == 0 || (unsigned int)(v6 - 1) <= 1 )
    {
      v7 = FwpmTransactionBegin0Wrapper();
      if ( v7 )
      {
        RasIpsecTrace("FwpmTransactionBegin0 failed with 0x%x");
        return v7;
      }
      for ( i = 0; i < *(_DWORD *)(v2 + 48); ++i )
      {
        if ( FwpmFilterDeleteByKey0(gFwpEngineHandle, (const GUID *)(*(_QWORD *)(v2 + 32) + 16LL * i)) )
          RasIpsecTrace("FwpmFilterDeleteByKey0: dwStatus=0x%x");
      }
      if ( !UuidIsNil((UUID *)(v2 + 16), &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)(v2 + 16)) )
      {
        RasIpsecTrace("FwpmProviderContextDeleteByKey0 QM: dwStatus=0x%x");
      }
      if ( !UuidIsNil((UUID *)v2, &Status) && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, (const GUID *)v2) )
        RasIpsecTrace("FwpmProviderContextDeleteByKey0 MM: dwStatus=0x%x");
      v3 = FwpmTransactionCommit0(gFwpEngineHandle);
    }
    --*(_DWORD *)(v2 + 52);
    v10 = gpIpSecSrvList;
    if ( gpIpSecSrvList )
    {
      if ( v2 == gpIpSecSrvList )
      {
        v10 = *(_QWORD *)(gpIpSecSrvList + 80);
LABEL_29:
        v13 = *(void **)(v2 + 32);
        if ( v13 )
          LocalFree(v13);
        LocalFree((HLOCAL)v2);
        goto LABEL_32;
      }
      v11 = gpIpSecSrvList;
      if ( *(_QWORD *)(gpIpSecSrvList + 80) )
      {
        while ( 1 )
        {
          v12 = (_QWORD *)(v11 + 80);
          v11 = *(_QWORD *)(v11 + 80);
          if ( v11 == v2 )
            break;
          if ( !*(_QWORD *)(v11 + 80) )
            goto LABEL_32;
        }
        *v12 = *(_QWORD *)(v11 + 80);
        goto LABEL_29;
      }
    }
LABEL_32:
    gpIpSecSrvList = v10;
    goto LABEL_33;
  }
  return 87;
}

```

## disassembly

```asm
0x18009cbac  mov     rax, rsp
0x18009cbaf  mov     [rax+10h], rbx
0x18009cbb3  mov     [rax+18h], rsi
0x18009cbb7  push    rdi
0x18009cbb8  sub     rsp, 40h
0x18009cbbc  movaps  xmm0, xmmword ptr [rcx]
0x18009cbbf  lea     rdx, [rsp+48h+var_28]
0x18009cbc4  movaps  xmmword ptr [rax-28h], xmm0
0x18009cbc8  mov     dword ptr [rax+8], 0
0x18009cbcf  mov     eax, [rcx+10h]
0x18009cbd2  mov     [rsp+48h+var_18], eax
0x18009cbd6  call    FindServerNode
0x18009cbdb  mov     rbx, rax
0x18009cbde  test    rax, rax
0x18009cbe1  jnz     short loc_18009CBEB
0x18009cbe3  lea     esi, [rax+57h]
0x18009cbe6  jmp     loc_18009CD56
0x18009cbeb  mov     eax, [rax+34h]
0x18009cbee  xor     esi, esi
0x18009cbf0  cmp     eax, 1
0x18009cbf3  jbe     short loc_18009CBFF
0x18009cbf5  dec     eax
0x18009cbf7  mov     [rbx+34h], eax
0x18009cbfa  jmp     loc_18009CD48
0x18009cbff  mov     ecx, [rbx+4Ch]
0x18009cc02  test    ecx, ecx
0x18009cc04  jz      short loc_18009CC19
0x18009cc06  sub     ecx, 1
0x18009cc09  jz      short loc_18009CC19
0x18009cc0b  sub     ecx, 1
0x18009cc0e  jz      short loc_18009CC19
0x18009cc10  cmp     ecx, 1
0x18009cc13  jnz     loc_18009CCE9
0x18009cc19  call    FwpmTransactionBegin0Wrapper
0x18009cc1e  mov     edi, eax
0x18009cc20  test    eax, eax
0x18009cc22  jz      short loc_18009CC39
0x18009cc24  mov     edx, eax
0x18009cc26  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18009cc2d  call    RasIpsecTrace
0x18009cc32  mov     eax, edi
0x18009cc34  jmp     loc_18009CD58
0x18009cc39  xor     edi, edi
0x18009cc3b  cmp     [rbx+30h], esi
0x18009cc3e  jbe     short loc_18009CC70
0x18009cc40  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009cc47  mov     edx, edi
0x18009cc49  shl     rdx, 4
0x18009cc4d  add     rdx, [rbx+20h]; key
0x18009cc51  call    cs:__imp_FwpmFilterDeleteByKey0
0x18009cc57  test    eax, eax
0x18009cc59  jz      short loc_18009CC69
0x18009cc5b  mov     edx, eax
0x18009cc5d  lea     rcx, aFwpmfilterdele_0; "FwpmFilterDeleteByKey0: dwStatus=0x%x"
0x18009cc64  call    RasIpsecTrace
0x18009cc69  inc     edi
0x18009cc6b  cmp     edi, [rbx+30h]
0x18009cc6e  jb      short loc_18009CC40
0x18009cc70  lea     rdx, [rsp+48h+Status]; Status
0x18009cc75  lea     rcx, [rbx+10h]; Uuid
0x18009cc79  call    cs:__imp_UuidIsNil
0x18009cc7f  test    eax, eax
0x18009cc81  jnz     short loc_18009CCA6
0x18009cc83  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009cc8a  lea     rdx, [rbx+10h]; key
0x18009cc8e  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18009cc94  test    eax, eax
0x18009cc96  jz      short loc_18009CCA6
0x18009cc98  mov     edx, eax
0x18009cc9a  lea     rcx, aFwpmproviderco_4; "FwpmProviderContextDeleteByKey0 QM: dwS"...
0x18009cca1  call    RasIpsecTrace
0x18009cca6  lea     rdx, [rsp+48h+Status]; Status
0x18009ccab  mov     rcx, rbx; Uuid
0x18009ccae  call    cs:__imp_UuidIsNil
0x18009ccb4  test    eax, eax
0x18009ccb6  jnz     short loc_18009CCDA
0x18009ccb8  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009ccbf  mov     rdx, rbx; key
0x18009ccc2  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18009ccc8  test    eax, eax
0x18009ccca  jz      short loc_18009CCDA
0x18009cccc  mov     edx, eax
0x18009ccce  lea     rcx, aFwpmproviderco_0; "FwpmProviderContextDeleteByKey0 MM: dwS"...
0x18009ccd5  call    RasIpsecTrace
0x18009ccda  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009cce1  call    cs:__imp_FwpmTransactionCommit0
0x18009cce7  mov     esi, eax
0x18009cce9  dec     dword ptr [rbx+34h]
0x18009ccec  mov     rdi, cs:gpIpSecSrvList
0x18009ccf3  test    rdi, rdi
0x18009ccf6  jz      short loc_18009CD41
0x18009ccf8  cmp     rbx, rdi
0x18009ccfb  jnz     short loc_18009CD03
0x18009ccfd  mov     rdi, [rdi+50h]
0x18009cd01  jmp     short loc_18009CD29
0x18009cd03  cmp     qword ptr [rdi+50h], 0
0x18009cd08  mov     rax, rdi
0x18009cd0b  jz      short loc_18009CD41
0x18009cd0d  lea     rcx, [rax+50h]
0x18009cd11  mov     rax, [rcx]
0x18009cd14  cmp     rax, rbx
0x18009cd17  jz      short loc_18009CD22
0x18009cd19  cmp     qword ptr [rax+50h], 0
0x18009cd1e  jnz     short loc_18009CD0D
0x18009cd20  jmp     short loc_18009CD41
0x18009cd22  mov     rax, [rax+50h]
0x18009cd26  mov     [rcx], rax
0x18009cd29  mov     rcx, [rbx+20h]; hMem
0x18009cd2d  test    rcx, rcx
0x18009cd30  jz      short loc_18009CD38
0x18009cd32  call    cs:__imp_LocalFree
0x18009cd38  mov     rcx, rbx; hMem
0x18009cd3b  call    cs:__imp_LocalFree
0x18009cd41  mov     cs:gpIpSecSrvList, rdi
0x18009cd48  mov     edx, esi
0x18009cd4a  lea     rcx, aDwdeleteclient; "DwDeleteClientIpSecFilter: dwStatus=0x%"...
0x18009cd51  call    RasIpsecTrace
0x18009cd56  mov     eax, esi
0x18009cd58  mov     rbx, [rsp+48h+arg_8]
0x18009cd5d  mov     rsi, [rsp+48h+arg_10]
0x18009cd62  add     rsp, 40h
0x18009cd66  pop     rdi
0x18009cd67  retn
```
