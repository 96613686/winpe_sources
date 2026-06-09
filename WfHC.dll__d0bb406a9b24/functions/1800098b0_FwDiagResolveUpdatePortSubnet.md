# FwDiagResolveUpdatePortSubnet

- ea: `0x1800098b0`
- end: `0x180009932`
- name: `FwDiagResolveUpdatePortSubnet`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1800098b0`
- `0x180009c20`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x1800098fc`
- `FirewallAPI!FWGetGlobalConfig` at `0x1800098fc`

## pseudocode

```c
__int64 __fastcall FwDiagResolveUpdatePortSubnet(__int64 a1)
{
  __int64 result; // rax
  int v3; // edx
  int v4; // [rsp+50h] [rbp+8h] BYREF
  int v5; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 || !*(_QWORD *)(a1 + 16) )
    return 87;
  v5 = 4;
  v4 = 0;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, &v4, &v5);
  if ( !(_DWORD)result )
    return FwDiagUpdatePortExceptionSubnet(*(unsigned __int16 *)(a1 + 16), v3, v4, *(_DWORD *)(a1 + 8), a1 + 24);
  return result;
}

```

## disassembly

```asm
0x1800098b0  push    rbx
0x1800098b2  sub     rsp, 40h
0x1800098b6  mov     rbx, rcx
0x1800098b9  test    rcx, rcx
0x1800098bc  jz      short loc_180009927
0x1800098be  cmp     qword ptr [rcx+10h], 0
0x1800098c3  jz      short loc_180009927
0x1800098c5  xor     edx, edx
0x1800098c7  mov     [rsp+48h+arg_8], 4
0x1800098cf  lea     rax, [rsp+48h+arg_8]
0x1800098d4  mov     [rsp+48h+arg_0], edx
0x1800098d8  mov     [rsp+48h+var_18], rax
0x1800098dd  mov     ecx, 221h
0x1800098e2  lea     rax, [rsp+48h+arg_0]
0x1800098e7  mov     r9d, 2
0x1800098ed  mov     [rsp+48h+var_20], rax
0x1800098f2  mov     r8d, 5
0x1800098f8  mov     dword ptr [rsp+48h+var_28], edx
0x1800098fc  call    cs:__imp_FWGetGlobalConfig
0x180009902  test    eax, eax
0x180009904  jnz     short loc_18000992C
0x180009906  mov     r9d, [rbx+8]
0x18000990a  lea     rax, [rbx+18h]
0x18000990e  mov     r8d, [rsp+48h+arg_0]
0x180009913  movzx   ecx, word ptr [rbx+10h]
0x180009917  mov     [rsp+48h+var_28], rax
0x18000991c  call    FwDiagUpdatePortExceptionSubnet
0x180009921  add     rsp, 40h
0x180009925  pop     rbx
0x180009926  retn
0x180009927  mov     eax, 57h ; 'W'
0x18000992c  add     rsp, 40h
0x180009930  pop     rbx
0x180009931  retn
```
