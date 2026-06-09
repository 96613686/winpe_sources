# __delayLoadHelper2

- ea: `0x180001ee0`
- end: `0x180001f16`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c86`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180001f0b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180001f0b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180001eea`

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
0x180001ee0  sub     rsp, 38h
0x180001ee4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180001eea  mov     r9, cs:__imp_DelayLoadFailureHook
0x180001ef1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180001ef8  mov     [rsp+38h+var_10], eax
0x180001efc  mov     [rsp+38h+var_18], rdx
0x180001f01  mov     rdx, rcx
0x180001f04  lea     rcx, __ImageBase
0x180001f0b  call    cs:__imp_ResolveDelayLoadedAPI
0x180001f11  add     rsp, 38h
0x180001f15  retn
```
