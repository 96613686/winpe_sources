# __delayLoadHelper2

- ea: `0x140012e70`
- end: `0x140012ea6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x140001aa0`
- `0x140001ba9`
- `0x140001c34`
- `0x140001cbf`
- `0x140001e06`
- `0x140001ea3`
- `0x140001f2e`
- `0x140001fb9`
- `0x14000207a`
- `0x140002105`
- `0x140002190`
- `0x14000223f`
- `0x140002332`
- `0x1400023e1`
- `0x14000247e`
- `0x14000252d`
- `0x1400025b8`
- `0x14000269d`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140012e9b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140012e9b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x140012e7a`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(__int64 a1, __int64 a2)
{
  return ResolveDelayLoadedAPI(
           &_ImageBase,
           a1,
           _pfnDefaultDliFailureHook2,
           DelayLoadFailureHook,
           a2,
           _ResolveDelayLoadedAPIFlags);
}

```

## disassembly

```asm
0x140012e70  sub     rsp, 38h
0x140012e74  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140012e7a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140012e81  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140012e88  mov     [rsp+38h+var_10], eax
0x140012e8c  mov     [rsp+38h+var_18], rdx
0x140012e91  mov     rdx, rcx
0x140012e94  lea     rcx, __ImageBase
0x140012e9b  call    cs:__imp_ResolveDelayLoadedAPI
0x140012ea1  add     rsp, 38h
0x140012ea5  retn
```
