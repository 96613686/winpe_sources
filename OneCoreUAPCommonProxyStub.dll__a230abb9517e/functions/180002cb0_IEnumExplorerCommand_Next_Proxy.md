# IEnumExplorerCommand_Next_Proxy

- ea: `0x180002cb0`
- end: `0x180002d0d`
- name: `IEnumExplorerCommand_Next_Proxy`
- size: `93`
- prototype: `HRESULT __stdcall(IEnumExplorerCommand *This, ULONG celt, IExplorerCommand **pUICommand, ULONG *pceltFetched)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002cb0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002cf6`
- `RPCRT4!NdrClientCall3` at `0x180002cf6`

## pseudocode

```c
HRESULT __stdcall IEnumExplorerCommand_Next_Proxy(
        IEnumExplorerCommand *This,
        ULONG celt,
        IExplorerCommand **pUICommand,
        ULONG *pceltFetched)
{
  HRESULT result; // eax
  ULONG v6; // [rsp+58h] [rbp+10h] BYREF

  if ( celt > 1 && !pceltFetched )
    return -2147024809;
  v6 = 0;
  result = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800AAB90, 3u, 0, This, celt, pUICommand, &v6).Pointer;
  if ( pceltFetched )
    *pceltFetched = v6;
  return result;
}

```

## disassembly

```asm
0x180002cb0  push    rbx
0x180002cb2  sub     rsp, 40h
0x180002cb6  mov     rbx, r9
0x180002cb9  cmp     edx, 1
0x180002cbc  jbe     short loc_180002CCA
0x180002cbe  test    rbx, rbx
0x180002cc1  jnz     short loc_180002CCA
0x180002cc3  mov     eax, 80070057h
0x180002cc8  jmp     short loc_180002D07
0x180002cca  lea     rax, [rsp+48h+arg_8]
0x180002ccf  mov     [rsp+48h+arg_8], 0
0x180002cd7  mov     [rsp+48h+var_18], rax
0x180002cdc  mov     r9, rcx
0x180002cdf  mov     [rsp+48h+var_20], r8
0x180002ce4  lea     rcx, stru_1800AAB90; pProxyInfo
0x180002ceb  xor     r8d, r8d; pReturnValue
0x180002cee  mov     [rsp+48h+var_28], edx
0x180002cf2  lea     edx, [r8+3]; nProcNum
0x180002cf6  call    cs:__imp_NdrClientCall3
0x180002cfc  test    rbx, rbx
0x180002cff  jz      short loc_180002D07
0x180002d01  mov     ecx, [rsp+48h+arg_8]
0x180002d05  mov     [rbx], ecx
0x180002d07  add     rsp, 40h
0x180002d0b  pop     rbx
0x180002d0c  retn
```
