# ept_mgmt_delete

- ea: `0x1800072a0`
- end: `0x1800072b0`
- name: `ept_mgmt_delete`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800072a9`
- `RPCRT4!RpcRaiseException` at `0x1800072a9`

## pseudocode

```c
void __noreturn ept_mgmt_delete()
{
  RpcRaiseException(1752);
}

```

## disassembly

```asm
0x1800072a0  sub     rsp, 28h
0x1800072a4  mov     ecx, 6D8h; exception
0x1800072a9  call    cs:__imp_RpcRaiseException
```
