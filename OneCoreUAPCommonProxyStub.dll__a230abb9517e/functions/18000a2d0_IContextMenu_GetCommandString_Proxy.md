# IContextMenu_GetCommandString_Proxy

- ea: `0x18000a2d0`
- end: `0x18000a316`
- name: `IContextMenu_GetCommandString_Proxy`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a30b`
- `RPCRT4!NdrClientCall3` at `0x18000a30b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall IContextMenu_GetCommandString_Proxy(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1801FD350, 5u, 0, a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18000a2d0  mov     r11, rsp
0x18000a2d3  sub     rsp, 58h
0x18000a2d7  mov     eax, [rsp+58h+arg_28]
0x18000a2de  mov     [rsp+58h+var_18], eax
0x18000a2e2  mov     rax, [rsp+58h+arg_20]
0x18000a2ea  mov     [r11-20h], rax
0x18000a2ee  mov     [r11-28h], r9
0x18000a2f2  mov     r9, rcx
0x18000a2f5  mov     [r11-30h], r8d
0x18000a2f9  lea     rcx, stru_1801FD350; pProxyInfo
0x18000a300  xor     r8d, r8d; pReturnValue
0x18000a303  mov     [r11-38h], rdx
0x18000a307  lea     edx, [r8+5]; nProcNum
0x18000a30b  call    cs:__imp_NdrClientCall3
0x18000a311  add     rsp, 58h
0x18000a315  retn
```
