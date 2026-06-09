# DwDeleteServerIpSecFilter

- ea: `0x18009cd70`
- end: `0x18009ceb7`
- name: `DwDeleteServerIpSecFilter`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d230`
- `0x180039d54`
- `0x18003d82c`

## callees

- `0x18009cd70`
- `0x18009d558`
- `0x18009d698`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x18009ce1c`
- `RPCRT4!UuidIsNil` at `0x18009ce58`
- `RPCRT4!UuidIsNil` at `0x18009ce1c`
- `RPCRT4!UuidIsNil` at `0x18009ce58`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18009cdee`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x18009cdee`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009ce8f`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18009ce8f`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ce34`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ce70`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ce34`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x18009ce70`

## string_xrefs

- `0x18009cdfa`: `FwpmFilterDelete0: dwStatus=0x%x`
- `0x18009cd78`: `DwDeleteServerIpSecFilter`
- `0x18009ce7c`: `FwpmProviderContextDelete0 MM: dwStatus=0x%x`
- `0x18009ce40`: `FwpmProviderContextDelete0 QM: dwStatus=0x%x`
- `0x18009cea3`: `DwDeleteServerIpSecFilter: rc=0x%x`

## pseudocode

```c
__int64 DwDeleteServerIpSecFilter()
{
  DWORD v0; // ebx
  unsigned int i; // ebx
  RPC_STATUS Status; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  Status = 0;
  RasIpsecTrace("DwDeleteServerIpSecFilter");
  if ( (unsigned int)geServerEncryption < 4 || (unsigned int)(geServerEncryption - 4) <= 1 )
  {
    v0 = FwpmTransactionBegin0Wrapper();
    if ( v0 )
    {
      RasIpsecTrace("FwpmTransactionBegin0 failed with 0x%x");
    }
    else
    {
      for ( i = 0; i < gNumServerFilterIds; ++i )
      {
        if ( FwpmFilterDeleteByKey0(gFwpEngineHandle, (const GUID *)&gServerFilterIds[2 * i]) )
          RasIpsecTrace("FwpmFilterDelete0: dwStatus=0x%x");
      }
      if ( !UuidIsNil(&gServerQMPolicyGuid, &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, &gServerQMPolicyGuid) )
      {
        RasIpsecTrace("FwpmProviderContextDelete0 QM: dwStatus=0x%x");
      }
      if ( !UuidIsNil(&gServerMMPolicyGuid, &Status)
        && FwpmProviderContextDeleteByKey0(gFwpEngineHandle, &gServerMMPolicyGuid) )
      {
        RasIpsecTrace("FwpmProviderContextDelete0 MM: dwStatus=0x%x");
      }
      v0 = FwpmTransactionCommit0(gFwpEngineHandle);
    }
    gNumServerFilterIds = 0;
  }
  RasIpsecTrace("DwDeleteServerIpSecFilter: rc=0x%x");
  return v0;
}

```

## disassembly

```asm
0x18009cd70  push    rbx
0x18009cd72  sub     rsp, 20h
0x18009cd76  xor     ebx, ebx
0x18009cd78  lea     rcx, aDwdeleteserver_0; "DwDeleteServerIpSecFilter"
0x18009cd7f  mov     [rsp+28h+Status], ebx
0x18009cd83  call    RasIpsecTrace
0x18009cd88  mov     ecx, cs:geServerEncryption
0x18009cd8e  test    ecx, ecx
0x18009cd90  jz      short loc_18009CDAF
0x18009cd92  sub     ecx, 1
0x18009cd95  jz      short loc_18009CDAF
0x18009cd97  sub     ecx, 1
0x18009cd9a  jz      short loc_18009CDAF
0x18009cd9c  sub     ecx, 1
0x18009cd9f  jz      short loc_18009CDAF
0x18009cda1  sub     ecx, 1
0x18009cda4  jz      short loc_18009CDAF
0x18009cda6  cmp     ecx, 1
0x18009cda9  jnz     loc_18009CEA1
0x18009cdaf  call    FwpmTransactionBegin0Wrapper
0x18009cdb4  mov     ebx, eax
0x18009cdb6  test    eax, eax
0x18009cdb8  jz      short loc_18009CDCD
0x18009cdba  mov     edx, eax
0x18009cdbc  lea     rcx, aFwpmtransactio_0; "FwpmTransactionBegin0 failed with 0x%x"
0x18009cdc3  call    RasIpsecTrace
0x18009cdc8  jmp     loc_18009CE97
0x18009cdcd  xor     ebx, ebx
0x18009cdcf  cmp     cs:gNumServerFilterIds, ebx
0x18009cdd5  jbe     short loc_18009CE10
0x18009cdd7  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009cdde  lea     rax, gServerFilterIds
0x18009cde5  mov     edx, ebx
0x18009cde7  shl     rdx, 4
0x18009cdeb  add     rdx, rax; key
0x18009cdee  call    cs:__imp_FwpmFilterDeleteByKey0
0x18009cdf4  test    eax, eax
0x18009cdf6  jz      short loc_18009CE06
0x18009cdf8  mov     edx, eax
0x18009cdfa  lea     rcx, aFwpmfilterdele; "FwpmFilterDelete0: dwStatus=0x%x"
0x18009ce01  call    RasIpsecTrace
0x18009ce06  inc     ebx
0x18009ce08  cmp     ebx, cs:gNumServerFilterIds
0x18009ce0e  jb      short loc_18009CDD7
0x18009ce10  lea     rdx, [rsp+28h+Status]; Status
0x18009ce15  lea     rcx, gServerQMPolicyGuid; Uuid
0x18009ce1c  call    cs:__imp_UuidIsNil
0x18009ce22  test    eax, eax
0x18009ce24  jnz     short loc_18009CE4C
0x18009ce26  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009ce2d  lea     rdx, gServerQMPolicyGuid; key
0x18009ce34  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18009ce3a  test    eax, eax
0x18009ce3c  jz      short loc_18009CE4C
0x18009ce3e  mov     edx, eax
0x18009ce40  lea     rcx, aFwpmproviderco_3; "FwpmProviderContextDelete0 QM: dwStatus"...
0x18009ce47  call    RasIpsecTrace
0x18009ce4c  lea     rdx, [rsp+28h+Status]; Status
0x18009ce51  lea     rcx, gServerMMPolicyGuid; Uuid
0x18009ce58  call    cs:__imp_UuidIsNil
0x18009ce5e  test    eax, eax
0x18009ce60  jnz     short loc_18009CE88
0x18009ce62  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009ce69  lea     rdx, gServerMMPolicyGuid; key
0x18009ce70  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18009ce76  test    eax, eax
0x18009ce78  jz      short loc_18009CE88
0x18009ce7a  mov     edx, eax
0x18009ce7c  lea     rcx, aFwpmproviderco_2; "FwpmProviderContextDelete0 MM: dwStatus"...
0x18009ce83  call    RasIpsecTrace
0x18009ce88  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18009ce8f  call    cs:__imp_FwpmTransactionCommit0
0x18009ce95  mov     ebx, eax
0x18009ce97  mov     cs:gNumServerFilterIds, 0
0x18009cea1  mov     edx, ebx
0x18009cea3  lea     rcx, aDwdeleteserver; "DwDeleteServerIpSecFilter: rc=0x%x"
0x18009ceaa  call    RasIpsecTrace
0x18009ceaf  mov     eax, ebx
0x18009ceb1  add     rsp, 20h
0x18009ceb5  pop     rbx
0x18009ceb6  retn
```
