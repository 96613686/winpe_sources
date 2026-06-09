# __delayLoadHelper2

- ea: `0x18000a480`
- end: `0x18000a4b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a10`
- `0x180004aad`
- `0x180004b6e`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a4ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000a4ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000a48a`

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
0x18000a480  sub     rsp, 38h
0x18000a484  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000a48a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000a491  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000a498  mov     [rsp+38h+var_10], eax
0x18000a49c  mov     [rsp+38h+var_18], rdx
0x18000a4a1  mov     rdx, rcx
0x18000a4a4  lea     rcx, __ImageBase
0x18000a4ab  call    cs:__imp_ResolveDelayLoadedAPI
0x18000a4b1  add     rsp, 38h
0x18000a4b5  retn
```
