# MosHostReportCacheMiss

- ea: `0x180010a60`
- end: `0x180010aab`
- name: `MosHostReportCacheMiss`
- size: `75`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010aa0`
- `RPCRT4!NdrClientCall3` at `0x180010aa0`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MosHostReportCacheMiss(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v7; // [rsp+20h] [rbp-38h]

  v7 = a2;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800140C0, 5u, 0, a1, v7, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180010a60  mov     r11, rsp
0x180010a63  sub     rsp, 58h
0x180010a67  mov     rax, [rsp+58h+arg_28]
0x180010a6f  mov     [r11-18h], rax
0x180010a73  mov     rax, [rsp+58h+arg_20]
0x180010a7b  mov     [r11-20h], rax
0x180010a7f  mov     [r11-28h], r9
0x180010a83  mov     r9, rcx
0x180010a86  mov     [r11-30h], r8
0x180010a8a  lea     rcx, stru_1800140C0; pProxyInfo
0x180010a91  movzx   r10d, dx
0x180010a95  xor     r8d, r8d; pReturnValue
0x180010a98  mov     [r11-38h], r10d
0x180010a9c  lea     edx, [r8+5]; nProcNum
0x180010aa0  call    cs:__imp_NdrClientCall3
0x180010aa6  add     rsp, 58h
0x180010aaa  retn
```
