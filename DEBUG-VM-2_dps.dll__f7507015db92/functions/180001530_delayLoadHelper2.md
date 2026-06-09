# __delayLoadHelper2

- ea: `0x180001530`
- end: `0x180001566`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a8b2`
- `0x18000a93d`
- `0x18000a9ec`
- `0x18000aa9b`
- `0x18000ab26`
- `0x18000abb1`
- `0x18000ac72`
- `0x18000acfd`
- `0x18000ad88`
- `0x18000ae49`
- `0x18000af40`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000155b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000155b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000153a`

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
0x180001530  sub     rsp, 38h
0x180001534  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000153a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180001541  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180001548  mov     [rsp+38h+var_10], eax
0x18000154c  mov     [rsp+38h+var_18], rdx
0x180001551  mov     rdx, rcx
0x180001554  lea     rcx, __ImageBase
0x18000155b  call    cs:__imp_ResolveDelayLoadedAPI
0x180001561  add     rsp, 38h
0x180001565  retn
```
