# __delayLoadHelper2

- ea: `0x180009440`
- end: `0x180009476`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002590`
- `0x180002687`
- `0x1800027b4`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000946b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000946b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000944a`

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
0x180009440  sub     rsp, 38h
0x180009444  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000944a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180009451  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180009458  mov     [rsp+38h+var_10], eax
0x18000945c  mov     [rsp+38h+var_18], rdx
0x180009461  mov     rdx, rcx
0x180009464  lea     rcx, __ImageBase
0x18000946b  call    cs:__imp_ResolveDelayLoadedAPI
0x180009471  add     rsp, 38h
0x180009475  retn
```
