# CDsmAdminControl::GetServiceInfo(DSM_SERVICEINFO *)

- ea: `0x1800097a0`
- end: `0x1800097fc`
- name: `?GetServiceInfo@CDsmAdminControl@@UEAAJPEAUDSM_SERVICEINFO@@@Z`
- size: `92`
- prototype: `CLIENT_CALL_RETURN __fastcall(CDsmAdminControl *this, struct DSM_SERVICEINFO *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800097a0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800097ce`
- `RPCRT4!NdrClientCall3` at `0x1800097ce`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CDsmAdminControl::GetServiceInfo(CDsmAdminControl *this, struct DSM_SERVICEINFO *a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, DsmRpcAdmin_v1_0_c_ifspec, a2);
}

```

## disassembly

```asm
0x1800097a0  push    rbx
0x1800097a2  sub     rsp, 40h
0x1800097a6  mov     [rsp+48h+var_18], 80004005h
0x1800097ae  xor     ebx, ebx
0x1800097b0  mov     [rsp+48h+arg_10], rbx
0x1800097b5  mov     [rsp+48h+var_28], rdx
0x1800097ba  mov     r9, cs:DsmRpcAdmin_v1_0_c_ifspec
0x1800097c1  xor     r8d, r8d; pReturnValue
0x1800097c4  lea     edx, [rbx+3]; nProcNum
0x1800097c7  lea     rcx, pProxyInfo; pProxyInfo
0x1800097ce  call    cs:__imp_NdrClientCall3
0x1800097d4  mov     [rsp+48h+arg_10], rax
0x1800097d9  mov     [rsp+48h+var_18], eax
0x1800097dd  jmp     short loc_1800097E5
0x1800097df  mov     ebx, eax
0x1800097e1  mov     eax, [rsp+48h+var_18]
0x1800097e5  test    ebx, ebx
0x1800097e7  jz      short loc_1800097F6
0x1800097e9  jle     short loc_1800097F4
0x1800097eb  movzx   ebx, bx
0x1800097ee  or      ebx, 80070000h
0x1800097f4  mov     eax, ebx
0x1800097f6  add     rsp, 40h
0x1800097fa  pop     rbx
0x1800097fb  retn
```
