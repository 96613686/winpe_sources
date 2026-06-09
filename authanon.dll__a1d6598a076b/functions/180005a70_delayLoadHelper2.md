# __delayLoadHelper2

- ea: `0x180005a70`
- end: `0x180005aa6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032d0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180005a9b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180005a9b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180005a7a`

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
0x180005a70  sub     rsp, 38h
0x180005a74  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180005a7a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180005a81  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180005a88  mov     [rsp+38h+var_10], eax
0x180005a8c  mov     [rsp+38h+var_18], rdx
0x180005a91  mov     rdx, rcx
0x180005a94  lea     rcx, __ImageBase
0x180005a9b  call    cs:__imp_ResolveDelayLoadedAPI
0x180005aa1  add     rsp, 38h
0x180005aa5  retn
```
