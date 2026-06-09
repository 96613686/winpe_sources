# MosHostCacheStateUseSlot

- ea: `0x180010830`
- end: `0x180010861`
- name: `MosHostCacheStateUseSlot`
- size: `49`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, unsigned __int16, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010856`
- `RPCRT4!NdrClientCall3` at `0x180010856`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostCacheStateUseSlot(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4)
{
  int v5; // [rsp+20h] [rbp-28h]

  v5 = a2;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 0xAu, 0, a1, v5, a3, a4);
}

```

## disassembly

```asm
0x180010830  sub     rsp, 48h
0x180010834  mov     [rsp+48h+var_18], r9
0x180010839  mov     r9, rcx
0x18001083c  mov     [rsp+48h+var_20], r8
0x180010841  lea     rcx, stru_1800140C0; pProxyInfo
0x180010848  movzx   eax, dx
0x18001084b  xor     r8d, r8d; pReturnValue
0x18001084e  mov     [rsp+48h+var_28], eax
0x180010852  lea     edx, [r8+0Ah]; nProcNum
0x180010856  call    cs:__imp_NdrClientCall3
0x18001085c  add     rsp, 48h
0x180010860  retn
```
