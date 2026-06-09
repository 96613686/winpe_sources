# __delayLoadHelper2

- ea: `0x140013380`
- end: `0x1400133b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002240`
- `0x1400022dd`
- `0x14000237a`
- `0x140002417`
- `0x1400024fc`
- `0x1400025ab`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1400133ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1400133ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14001338a`

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
0x140013380  sub     rsp, 38h
0x140013384  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14001338a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140013391  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140013398  mov     [rsp+38h+var_10], eax
0x14001339c  mov     [rsp+38h+var_18], rdx
0x1400133a1  mov     rdx, rcx
0x1400133a4  lea     rcx, __ImageBase
0x1400133ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1400133b1  add     rsp, 38h
0x1400133b5  retn
```
