# __delayLoadHelper2

- ea: `0x180003e00`
- end: `0x180003e36`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001930`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003e2b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003e2b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180003e0a`

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
0x180003e00  sub     rsp, 38h
0x180003e04  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180003e0a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003e11  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003e18  mov     [rsp+38h+var_10], eax
0x180003e1c  mov     [rsp+38h+var_18], rdx
0x180003e21  mov     rdx, rcx
0x180003e24  lea     rcx, __ImageBase
0x180003e2b  call    cs:__imp_ResolveDelayLoadedAPI
0x180003e31  add     rsp, 38h
0x180003e35  retn
```
