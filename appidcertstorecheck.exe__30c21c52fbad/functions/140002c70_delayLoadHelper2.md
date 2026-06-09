# __delayLoadHelper2

- ea: `0x140002c70`
- end: `0x140002ca6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001820`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140002c9b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140002c9b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x140002c7a`

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
0x140002c70  sub     rsp, 38h
0x140002c74  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140002c7a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140002c81  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140002c88  mov     [rsp+38h+var_10], eax
0x140002c8c  mov     [rsp+38h+var_18], rdx
0x140002c91  mov     rdx, rcx
0x140002c94  lea     rcx, __ImageBase
0x140002c9b  call    cs:__imp_ResolveDelayLoadedAPI
0x140002ca1  add     rsp, 38h
0x140002ca5  retn
```
