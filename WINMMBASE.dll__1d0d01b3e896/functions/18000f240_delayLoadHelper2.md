# __delayLoadHelper2

- ea: `0x18000f240`
- end: `0x18000f276`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180011086`
- `0x180011111`
- `0x18001119c`
- `0x180011239`
- `0x180011366`
- `0x1800113f1`
- `0x1800114b2`
- `0x18001154f`
- `0x1800115ec`
- `0x180011702`
- `0x180011818`
- `0x18001191e`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f26b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f26b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000f24a`

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
0x18000f240  sub     rsp, 38h
0x18000f244  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000f24a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000f251  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000f258  mov     [rsp+38h+var_10], eax
0x18000f25c  mov     [rsp+38h+var_18], rdx
0x18000f261  mov     rdx, rcx
0x18000f264  lea     rcx, __ImageBase
0x18000f26b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000f271  add     rsp, 38h
0x18000f275  retn
```
