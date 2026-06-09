# __delayLoadHelper2

- ea: `0x140001eb0`
- end: `0x140001ee6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001820`
- `0x1400018ab`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x140001edb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x140001edb`
- `KERNEL32!DelayLoadFailureHook` at `0x140001eba`

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
0x140001eb0  sub     rsp, 38h
0x140001eb4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140001eba  mov     r9, cs:__imp_DelayLoadFailureHook
0x140001ec1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140001ec8  mov     [rsp+38h+var_10], eax
0x140001ecc  mov     [rsp+38h+var_18], rdx
0x140001ed1  mov     rdx, rcx
0x140001ed4  lea     rcx, __ImageBase
0x140001edb  call    cs:__imp_ResolveDelayLoadedAPI
0x140001ee1  add     rsp, 38h
0x140001ee5  retn
```
