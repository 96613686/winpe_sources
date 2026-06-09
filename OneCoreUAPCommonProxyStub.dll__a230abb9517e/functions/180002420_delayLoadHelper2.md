# __delayLoadHelper2

- ea: `0x180002420`
- end: `0x180002456`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180004736`
- `0x180004a56`
- `0x180005396`
- `0x180005433`
- `0x18000558e`
- `0x180005619`
- `0x1800056fa`
- `0x1800057ec`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000244b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000244b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000242a`

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
0x180002420  sub     rsp, 38h
0x180002424  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000242a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180002431  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180002438  mov     [rsp+38h+var_10], eax
0x18000243c  mov     [rsp+38h+var_18], rdx
0x180002441  mov     rdx, rcx
0x180002444  lea     rcx, __ImageBase
0x18000244b  call    cs:__imp_ResolveDelayLoadedAPI
0x180002451  add     rsp, 38h
0x180002455  retn
```
