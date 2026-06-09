# MosHostCacheStateSnapshot

- ea: `0x1800107d0`
- end: `0x1800107f7`
- name: `MosHostCacheStateSnapshot`
- size: `39`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, unsigned __int8)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800107ec`
- `RPCRT4!NdrClientCall3` at `0x1800107ec`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateSnapshot(__int64 a1, unsigned __int8 a2)
{
  int v3; // [rsp+20h] [rbp-18h]

  v3 = a2;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0xEu, 0, a1, v3);
}

```

## disassembly

```asm
0x1800107d0  sub     rsp, 38h
0x1800107d4  movzx   eax, dl
0x1800107d7  xor     r8d, r8d; pReturnValue
0x1800107da  mov     r9, rcx
0x1800107dd  mov     [rsp+38h+var_18], eax
0x1800107e1  lea     rcx, stru_1800140C0; pProxyInfo
0x1800107e8  lea     edx, [r8+0Eh]; nProcNum
0x1800107ec  call    cs:__imp_NdrClientCall3
0x1800107f2  add     rsp, 38h
0x1800107f6  retn
```
