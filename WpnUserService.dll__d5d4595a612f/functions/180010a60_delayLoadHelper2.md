# __delayLoadHelper2

- ea: `0x180010a60`
- end: `0x180010a96`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035a6`
- `0x180003631`
- `0x1800036bc`
- `0x180003747`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180010a8b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180010a8b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180010a6a`

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
0x180010a60  sub     rsp, 38h
0x180010a64  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180010a6a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180010a71  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180010a78  mov     [rsp+38h+var_10], eax
0x180010a7c  mov     [rsp+38h+var_18], rdx
0x180010a81  mov     rdx, rcx
0x180010a84  lea     rcx, __ImageBase
0x180010a8b  call    cs:__imp_ResolveDelayLoadedAPI
0x180010a91  add     rsp, 38h
0x180010a95  retn
```
