# __delayLoadHelper2

- ea: `0x180006880`
- end: `0x1800068b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dd6`
- `0x180001efa`
- `0x180001fa9`
- `0x180002034`
- `0x18000210d`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800068ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800068ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000688a`

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
0x180006880  sub     rsp, 38h
0x180006884  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000688a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006891  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006898  mov     [rsp+38h+var_10], eax
0x18000689c  mov     [rsp+38h+var_18], rdx
0x1800068a1  mov     rdx, rcx
0x1800068a4  lea     rcx, __ImageBase
0x1800068ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1800068b1  add     rsp, 38h
0x1800068b5  retn
```
