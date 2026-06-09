# NetworkIsolationFreeAppContainers

- ea: `0x180057ca0`
- end: `0x180057d5f`
- name: `NetworkIsolationFreeAppContainers`
- size: `191`
- prototype: `DWORD __stdcall(PINET_FIREWALL_APP_CONTAINER pPublicAppCs)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180057ca0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x180057cb5`
- `fwbase!FwBaseFree` at `0x180057cc5`
- `fwbase!FwBaseFree` at `0x180057cd5`
- `fwbase!FwBaseFree` at `0x180057ce5`
- `fwbase!FwBaseFree` at `0x180057cf5`
- `fwbase!FwBaseFree` at `0x180057d2b`
- `fwbase!FwBaseFree` at `0x180057d3b`
- `fwbase!FwBaseFree` at `0x180057d4a`
- `fwbase!FwBaseFree` at `0x180057cb5`
- `fwbase!FwBaseFree` at `0x180057cc5`
- `fwbase!FwBaseFree` at `0x180057cd5`
- `fwbase!FwBaseFree` at `0x180057ce5`
- `fwbase!FwBaseFree` at `0x180057cf5`
- `fwbase!FwBaseFree` at `0x180057d2b`
- `fwbase!FwBaseFree` at `0x180057d3b`
- `fwbase!FwBaseFree` at `0x180057d4a`
- `FWPolicyIOMgr!FwBinariesFree` at `0x180057d1b`
- `FWPolicyIOMgr!FwBinariesFree` at `0x180057d1b`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x180057d08`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x180057d08`

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
0x180057ca0  push    rbx
0x180057ca2  sub     rsp, 20h
0x180057ca6  mov     rbx, rcx
0x180057ca9  test    rcx, rcx
0x180057cac  jz      loc_180057D56
0x180057cb2  mov     rcx, [rcx]
0x180057cb5  call    cs:__imp_FwBaseFree
0x180057cbc  nop     dword ptr [rax+rax+00h]
0x180057cc1  mov     rcx, [rbx+8]
0x180057cc5  call    cs:__imp_FwBaseFree
0x180057ccc  nop     dword ptr [rax+rax+00h]
0x180057cd1  mov     rcx, [rbx+10h]
0x180057cd5  call    cs:__imp_FwBaseFree
0x180057cdc  nop     dword ptr [rax+rax+00h]
0x180057ce1  mov     rcx, [rbx+18h]
0x180057ce5  call    cs:__imp_FwBaseFree
0x180057cec  nop     dword ptr [rax+rax+00h]
0x180057cf1  mov     rcx, [rbx+20h]
0x180057cf5  call    cs:__imp_FwBaseFree
0x180057cfc  nop     dword ptr [rax+rax+00h]
0x180057d01  mov     rdx, [rbx+30h]
0x180057d05  mov     ecx, [rbx+28h]
0x180057d08  call    cs:__imp_FwSidAndAttributesFree
0x180057d0f  nop     dword ptr [rax+rax+00h]
0x180057d14  mov     rdx, [rbx+40h]
0x180057d18  mov     ecx, [rbx+38h]
0x180057d1b  call    cs:__imp_FwBinariesFree
0x180057d22  nop     dword ptr [rax+rax+00h]
0x180057d27  mov     rcx, [rbx+48h]
0x180057d2b  call    cs:__imp_FwBaseFree
0x180057d32  nop     dword ptr [rax+rax+00h]
0x180057d37  mov     rcx, [rbx+50h]
0x180057d3b  call    cs:__imp_FwBaseFree
0x180057d42  nop     dword ptr [rax+rax+00h]
0x180057d47  mov     rcx, rbx
0x180057d4a  call    cs:__imp_FwBaseFree
0x180057d51  nop     dword ptr [rax+rax+00h]
0x180057d56  xor     eax, eax
0x180057d58  add     rsp, 20h
0x180057d5c  pop     rbx
0x180057d5d  retn
```
