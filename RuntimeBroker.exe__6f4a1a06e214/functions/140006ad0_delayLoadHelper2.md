# __delayLoadHelper2

- ea: `0x140006ad0`
- end: `0x140006b06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x14000969a`
- `0x140009725`
- `0x1400097c2`
- `0x14000984d`
- `0x1400098ea`
- `0x1400099e1`
- `0x140009b7a`
- `0x140009c3b`
- `0x140009cd8`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140006afb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x140006afb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x140006ada`

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
0x140006ad0  sub     rsp, 38h
0x140006ad4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140006ada  mov     r9, cs:__imp_DelayLoadFailureHook
0x140006ae1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140006ae8  mov     [rsp+38h+var_10], eax
0x140006aec  mov     [rsp+38h+var_18], rdx
0x140006af1  mov     rdx, rcx
0x140006af4  lea     rcx, __ImageBase
0x140006afb  call    cs:__imp_ResolveDelayLoadedAPI
0x140006b01  add     rsp, 38h
0x140006b05  retn
```
