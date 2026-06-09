# __delayLoadHelper2

- ea: `0x180006cb0`
- end: `0x180006ce6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001930`
- `0x180001a40`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006cdb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006cdb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180006cba`

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
0x180006cb0  sub     rsp, 38h
0x180006cb4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180006cba  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006cc1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006cc8  mov     [rsp+38h+var_10], eax
0x180006ccc  mov     [rsp+38h+var_18], rdx
0x180006cd1  mov     rdx, rcx
0x180006cd4  lea     rcx, __ImageBase
0x180006cdb  call    cs:__imp_ResolveDelayLoadedAPI
0x180006ce1  add     rsp, 38h
0x180006ce5  retn
```
