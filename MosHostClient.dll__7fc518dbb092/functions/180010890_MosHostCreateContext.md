# MosHostCreateContext

- ea: `0x180010890`
- end: `0x1800108bc`
- name: `MosHostCreateContext`
- size: `44`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800108b1`
- `RPCRT4!NdrClientCall3` at `0x1800108b1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCreateContext(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010890  sub     rsp, 48h
0x180010894  mov     [rsp+48h+var_18], r9
0x180010899  mov     r9, rcx
0x18001089c  mov     [rsp+48h+var_20], r8
0x1800108a1  lea     rcx, stru_1800140C0; pProxyInfo
0x1800108a8  mov     [rsp+48h+var_28], edx
0x1800108ac  xor     r8d, r8d; pReturnValue
0x1800108af  xor     edx, edx; nProcNum
0x1800108b1  call    cs:__imp_NdrClientCall3
0x1800108b7  add     rsp, 48h
0x1800108bb  retn
```
