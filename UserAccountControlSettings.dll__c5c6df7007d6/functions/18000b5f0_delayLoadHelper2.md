# __delayLoadHelper2

- ea: `0x18000b5f0`
- end: `0x18000b626`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023f0`
- `0x1800024c3`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b61b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b61b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000b5fa`

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
0x18000b5f0  sub     rsp, 38h
0x18000b5f4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000b5fa  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000b601  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000b608  mov     [rsp+38h+var_10], eax
0x18000b60c  mov     [rsp+38h+var_18], rdx
0x18000b611  mov     rdx, rcx
0x18000b614  lea     rcx, __ImageBase
0x18000b61b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000b621  add     rsp, 38h
0x18000b625  retn
```
