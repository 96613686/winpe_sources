# __delayLoadHelper2

- ea: `0x140004270`
- end: `0x1400042a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400023f0`
- `0x14000247b`
- `0x140002518`
- `0x1400025b5`
- `0x1400026ca`
- `0x14000278b`
- `0x140002828`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000429b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000429b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000427a`

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
0x140004270  sub     rsp, 38h
0x140004274  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000427a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140004281  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140004288  mov     [rsp+38h+var_10], eax
0x14000428c  mov     [rsp+38h+var_18], rdx
0x140004291  mov     rdx, rcx
0x140004294  lea     rcx, __ImageBase
0x14000429b  call    cs:__imp_ResolveDelayLoadedAPI
0x1400042a1  add     rsp, 38h
0x1400042a5  retn
```
