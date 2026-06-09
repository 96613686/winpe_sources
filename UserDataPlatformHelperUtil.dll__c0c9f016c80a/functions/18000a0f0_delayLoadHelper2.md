# __delayLoadHelper2

- ea: `0x18000a0f0`
- end: `0x18000a126`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d5f`
- `0x180001dea`
- `0x180001e87`
- `0x180001f12`
- `0x180001faf`
- `0x18000205e`
- `0x1800020e9`
- `0x180002174`
- `0x1800021ff`
- `0x180002308`
- `0x1800023a5`
- `0x180002430`
- `0x180002512`
- `0x180002609`
- `0x1800026b2`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a11b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a11b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000a0fa`

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
0x18000a0f0  sub     rsp, 38h
0x18000a0f4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000a0fa  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000a101  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000a108  mov     [rsp+38h+var_10], eax
0x18000a10c  mov     [rsp+38h+var_18], rdx
0x18000a111  mov     rdx, rcx
0x18000a114  lea     rcx, __ImageBase
0x18000a11b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000a121  add     rsp, 38h
0x18000a125  retn
```
