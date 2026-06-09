# __delayLoadHelper2

- ea: `0x180020f30`
- end: `0x180020f66`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800021ce`
- `0x180002259`
- `0x1800022e4`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180020f5b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180020f5b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180020f3a`

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
0x180020f30  sub     rsp, 38h
0x180020f34  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180020f3a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180020f41  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180020f48  mov     [rsp+38h+var_10], eax
0x180020f4c  mov     [rsp+38h+var_18], rdx
0x180020f51  mov     rdx, rcx
0x180020f54  lea     rcx, __ImageBase
0x180020f5b  call    cs:__imp_ResolveDelayLoadedAPI
0x180020f61  add     rsp, 38h
0x180020f65  retn
```
