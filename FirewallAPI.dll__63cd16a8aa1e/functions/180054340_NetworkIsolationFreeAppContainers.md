# NetworkIsolationFreeAppContainers

- ea: `0x180054340`
- end: `0x1800543be`
- name: `NetworkIsolationFreeAppContainers`
- size: `126`
- prototype: `DWORD __stdcall(PINET_FIREWALL_APP_CONTAINER pPublicAppCs)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180054340`

## import_xrefs

- `fwbase!FwBaseFree` at `0x180054351`
- `fwbase!FwBaseFree` at `0x18005435b`
- `fwbase!FwBaseFree` at `0x180054365`
- `fwbase!FwBaseFree` at `0x18005436f`
- `fwbase!FwBaseFree` at `0x180054379`
- `fwbase!FwBaseFree` at `0x18005439d`
- `fwbase!FwBaseFree` at `0x1800543a7`
- `fwbase!FwBaseFree` at `0x1800543b0`
- `fwbase!FwBaseFree` at `0x180054351`
- `fwbase!FwBaseFree` at `0x18005435b`
- `fwbase!FwBaseFree` at `0x180054365`
- `fwbase!FwBaseFree` at `0x18005436f`
- `fwbase!FwBaseFree` at `0x180054379`
- `fwbase!FwBaseFree` at `0x18005439d`
- `fwbase!FwBaseFree` at `0x1800543a7`
- `fwbase!FwBaseFree` at `0x1800543b0`
- `FWPolicyIOMgr!FwBinariesFree` at `0x180054393`
- `FWPolicyIOMgr!FwBinariesFree` at `0x180054393`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x180054386`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x180054386`

## pseudocode

```c
DWORD __stdcall NetworkIsolationFreeAppContainers(PINET_FIREWALL_APP_CONTAINER pPublicAppCs)
{
  if ( pPublicAppCs )
  {
    FwBaseFree(pPublicAppCs->appContainerSid);
    FwBaseFree(pPublicAppCs->userSid);
    FwBaseFree(pPublicAppCs->appContainerName);
    FwBaseFree(pPublicAppCs->displayName);
    FwBaseFree(pPublicAppCs->description);
    FwSidAndAttributesFree(pPublicAppCs->capabilities.count, pPublicAppCs->capabilities.capabilities);
    FwBinariesFree(pPublicAppCs->binaries.count, pPublicAppCs->binaries.binaries);
    FwBaseFree(pPublicAppCs->workingDirectory);
    FwBaseFree(pPublicAppCs->packageFullName);
    FwBaseFree(pPublicAppCs);
  }
  return 0;
}

```

## disassembly

```asm
0x180054340  push    rbx
0x180054342  sub     rsp, 20h
0x180054346  mov     rbx, rcx
0x180054349  test    rcx, rcx
0x18005434c  jz      short loc_1800543B6
0x18005434e  mov     rcx, [rcx]
0x180054351  call    cs:__imp_FwBaseFree
0x180054357  mov     rcx, [rbx+8]
0x18005435b  call    cs:__imp_FwBaseFree
0x180054361  mov     rcx, [rbx+10h]
0x180054365  call    cs:__imp_FwBaseFree
0x18005436b  mov     rcx, [rbx+18h]
0x18005436f  call    cs:__imp_FwBaseFree
0x180054375  mov     rcx, [rbx+20h]
0x180054379  call    cs:__imp_FwBaseFree
0x18005437f  mov     rdx, [rbx+30h]
0x180054383  mov     ecx, [rbx+28h]
0x180054386  call    cs:__imp_FwSidAndAttributesFree
0x18005438c  mov     rdx, [rbx+40h]
0x180054390  mov     ecx, [rbx+38h]
0x180054393  call    cs:__imp_FwBinariesFree
0x180054399  mov     rcx, [rbx+48h]
0x18005439d  call    cs:__imp_FwBaseFree
0x1800543a3  mov     rcx, [rbx+50h]
0x1800543a7  call    cs:__imp_FwBaseFree
0x1800543ad  mov     rcx, rbx
0x1800543b0  call    cs:__imp_FwBaseFree
0x1800543b6  xor     eax, eax
0x1800543b8  add     rsp, 20h
0x1800543bc  pop     rbx
0x1800543bd  retn
```
