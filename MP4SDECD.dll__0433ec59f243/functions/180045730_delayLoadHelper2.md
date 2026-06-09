# __delayLoadHelper2

- ea: `0x180045730`
- end: `0x180045766`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002b41c`
- `0x18002b4a7`
- `0x18002b532`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18004575b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18004575b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18004573a`

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
0x180045730  sub     rsp, 38h
0x180045734  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18004573a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180045741  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180045748  mov     [rsp+38h+var_10], eax
0x18004574c  mov     [rsp+38h+var_18], rdx
0x180045751  mov     rdx, rcx
0x180045754  lea     rcx, __ImageBase
0x18004575b  call    cs:__imp_ResolveDelayLoadedAPI
0x180045761  add     rsp, 38h
0x180045765  retn
```
