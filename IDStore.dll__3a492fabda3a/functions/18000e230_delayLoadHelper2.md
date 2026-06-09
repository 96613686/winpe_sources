# __delayLoadHelper2

- ea: `0x18000e230`
- end: `0x18000e266`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fe4f`
- `0x18000feec`
- `0x18001004a`
- `0x1800100d5`
- `0x180010184`
- `0x1800102b1`
- `0x18001033c`
- `0x18001042d`
- `0x180010512`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000e25b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000e25b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000e23a`

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
0x18000e230  sub     rsp, 38h
0x18000e234  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000e23a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000e241  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000e248  mov     [rsp+38h+var_10], eax
0x18000e24c  mov     [rsp+38h+var_18], rdx
0x18000e251  mov     rdx, rcx
0x18000e254  lea     rcx, __ImageBase
0x18000e25b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000e261  add     rsp, 38h
0x18000e265  retn
```
