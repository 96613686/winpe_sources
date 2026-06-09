# __delayLoadHelper2

- ea: `0x180008820`
- end: `0x180008856`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a20`
- `0x180001acf`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000884b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000884b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000882a`

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
0x180008820  sub     rsp, 38h
0x180008824  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000882a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180008831  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180008838  mov     [rsp+38h+var_10], eax
0x18000883c  mov     [rsp+38h+var_18], rdx
0x180008841  mov     rdx, rcx
0x180008844  lea     rcx, __ImageBase
0x18000884b  call    cs:__imp_ResolveDelayLoadedAPI
0x180008851  add     rsp, 38h
0x180008855  retn
```
