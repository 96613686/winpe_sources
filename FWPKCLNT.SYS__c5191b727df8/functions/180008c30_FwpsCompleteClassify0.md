# FwpsCompleteClassify0

- ea: `0x180008c30`
- end: `0x180008c4b`
- name: `FwpsCompleteClassify0`
- size: `27`
- prototype: `void __stdcall(UINT64 classifyHandle, UINT32 flags, const FWPS_CLASSIFY_OUT0 *classifyOut)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008c30`

## import_xrefs

- `NETIO!FeCompleteClassify` at `0x180008c39`
- `NETIO!FeCompleteClassify` at `0x180008c39`

## pseudocode

```c
void __stdcall FwpsCompleteClassify0(UINT64 classifyHandle, UINT32 flags, const FWPS_CLASSIFY_OUT0 *classifyOut)
{
  if ( classifyHandle )
    FeCompleteClassify(classifyHandle, flags, classifyOut);
}

```

## disassembly

```asm
0x180008c30  sub     rsp, 28h
0x180008c34  test    rcx, rcx
0x180008c37  jz      short loc_180008C45
0x180008c39  call    cs:__imp_FeCompleteClassify
0x180008c40  nop     dword ptr [rax+rax+00h]
0x180008c45  add     rsp, 28h
0x180008c49  retn
```
