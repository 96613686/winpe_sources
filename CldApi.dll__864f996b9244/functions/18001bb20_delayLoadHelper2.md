# __delayLoadHelper2

- ea: `0x18001bb20`
- end: `0x18001bb56`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002300`
- `0x1800023f7`
- `0x1800024a6`
- `0x180002543`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001bb4b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001bb4b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001bb2a`

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
0x18001bb20  sub     rsp, 38h
0x18001bb24  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001bb2a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18001bb31  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001bb38  mov     [rsp+38h+var_10], eax
0x18001bb3c  mov     [rsp+38h+var_18], rdx
0x18001bb41  mov     rdx, rcx
0x18001bb44  lea     rcx, __ImageBase
0x18001bb4b  call    cs:__imp_ResolveDelayLoadedAPI
0x18001bb51  add     rsp, 38h
0x18001bb55  retn
```
