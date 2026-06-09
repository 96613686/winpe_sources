# __delayLoadHelper2

- ea: `0x14000ea00`
- end: `0x14000ea36`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x14000402b`
- `0x1400040b6`
- `0x140004141`
- `0x140004226`
- `0x1400042b1`
- `0x140004360`
- `0x14000440f`
- `0x14000449a`
- `0x140004525`
- `0x1400045b0`
- `0x14000463b`
- `0x1400046c6`
- `0x140004751`
- `0x1400047dc`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000ea2b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000ea2b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000ea0a`

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
0x14000ea00  sub     rsp, 38h
0x14000ea04  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000ea0a  mov     r9, cs:__imp_DelayLoadFailureHook
0x14000ea11  mov     r8, cs:__pfnDefaultDliFailureHook2
0x14000ea18  mov     [rsp+38h+var_10], eax
0x14000ea1c  mov     [rsp+38h+var_18], rdx
0x14000ea21  mov     rdx, rcx
0x14000ea24  lea     rcx, __ImageBase
0x14000ea2b  call    cs:__imp_ResolveDelayLoadedAPI
0x14000ea31  add     rsp, 38h
0x14000ea35  retn
```
