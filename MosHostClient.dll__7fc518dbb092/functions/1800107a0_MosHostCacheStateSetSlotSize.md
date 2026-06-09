# MosHostCacheStateSetSlotSize

- ea: `0x1800107a0`
- end: `0x1800107c9`
- name: `MosHostCacheStateSetSlotSize`
- size: `41`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800107be`
- `RPCRT4!NdrClientCall3` at `0x1800107be`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateSetSlotSize(__int64 a1, int a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0xCu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x1800107a0  sub     rsp, 38h
0x1800107a4  mov     [rsp+38h+var_10], r8d
0x1800107a9  mov     r9, rcx
0x1800107ac  xor     r8d, r8d; pReturnValue
0x1800107af  mov     [rsp+38h+var_18], edx
0x1800107b3  lea     rcx, stru_1800140C0; pProxyInfo
0x1800107ba  lea     edx, [r8+0Ch]; nProcNum
0x1800107be  call    cs:__imp_NdrClientCall3
0x1800107c4  add     rsp, 38h
0x1800107c8  retn
```
