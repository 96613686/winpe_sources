# Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledFallback

- ea: `0x14003b0cc`
- end: `0x14003b0e2`
- name: `Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledFallback`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14003b090`

## callees

- `0x140008bd0`

## pseudocode

```c
__int64 __fastcall Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_IsEnabledFallback(
        __int64 a1,
        __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_descriptor);
}

```

## disassembly

```asm
0x14003b0cc  sub     rsp, 28h
0x14003b0d0  lea     r8, Feature_MbbCx_Fix_OutOfScopeReadsInResponseHandlers__private_descriptor
0x14003b0d7  call    wil_details_IsEnabledFallback
0x14003b0dc  add     rsp, 28h
0x14003b0e0  retn
```
