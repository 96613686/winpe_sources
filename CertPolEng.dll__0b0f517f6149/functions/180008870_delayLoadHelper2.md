# __delayLoadHelper2

- ea: `0x180008870`
- end: `0x1800088a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eb00`
- `0x18000eb8b`
- `0x18000ec16`
- `0x18000eca1`
- `0x18000ed2c`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000889b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000889b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000887a`

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
0x180008870  sub     rsp, 38h
0x180008874  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000887a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180008881  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180008888  mov     [rsp+38h+var_10], eax
0x18000888c  mov     [rsp+38h+var_18], rdx
0x180008891  mov     rdx, rcx
0x180008894  lea     rcx, __ImageBase
0x18000889b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800088a1  add     rsp, 38h
0x1800088a5  retn
```
