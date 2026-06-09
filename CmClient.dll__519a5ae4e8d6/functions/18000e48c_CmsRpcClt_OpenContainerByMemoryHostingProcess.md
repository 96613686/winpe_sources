# CmsRpcClt_OpenContainerByMemoryHostingProcess

- ea: `0x18000e48c`
- end: `0x18000e4eb`
- name: `CmsRpcClt_OpenContainerByMemoryHostingProcess`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023f0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e4e0`
- `RPCRT4!NdrClientCall3` at `0x18000e4e0`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenContainerByMemoryHostingProcess(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, a1, a2, a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x18000e48c  mov     r11, rsp
0x18000e48f  sub     rsp, 68h
0x18000e493  mov     rax, [rsp+68h+arg_38]
0x18000e49b  mov     [r11-18h], rax
0x18000e49f  mov     rax, [rsp+68h+arg_30]
0x18000e4a7  mov     [r11-20h], rax
0x18000e4ab  mov     rax, [rsp+68h+arg_28]
0x18000e4b3  mov     [r11-28h], rax
0x18000e4b7  mov     rax, [rsp+68h+arg_20]
0x18000e4bf  mov     [r11-30h], rax
0x18000e4c3  mov     [r11-38h], r9d
0x18000e4c7  mov     r9, rcx
0x18000e4ca  mov     [r11-40h], r8d
0x18000e4ce  lea     rcx, pProxyInfo; pProxyInfo
0x18000e4d5  xor     r8d, r8d; pReturnValue
0x18000e4d8  mov     [r11-48h], rdx
0x18000e4dc  lea     edx, [r8+3]; nProcNum
0x18000e4e0  call    cs:__imp_NdrClientCall3
0x18000e4e6  add     rsp, 68h
0x18000e4ea  retn
```
