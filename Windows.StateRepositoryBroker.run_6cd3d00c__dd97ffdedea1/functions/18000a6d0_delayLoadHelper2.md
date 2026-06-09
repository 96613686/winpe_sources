# __delayLoadHelper2

- ea: `0x18000a6d0`
- end: `0x18000a706`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002966`
- `0x180002b48`
- `0x180002c29`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a6fb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a6fb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000a6da`

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
0x18000a6d0  sub     rsp, 38h
0x18000a6d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000a6da  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000a6e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000a6e8  mov     [rsp+38h+var_10], eax
0x18000a6ec  mov     [rsp+38h+var_18], rdx
0x18000a6f1  mov     rdx, rcx
0x18000a6f4  lea     rcx, __ImageBase
0x18000a6fb  call    cs:__imp_ResolveDelayLoadedAPI
0x18000a701  add     rsp, 38h
0x18000a705  retn
```
