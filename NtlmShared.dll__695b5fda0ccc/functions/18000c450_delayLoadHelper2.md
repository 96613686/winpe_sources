# __delayLoadHelper2

- ea: `0x18000c450`
- end: `0x18000c486`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001990`
- `0x180001a2d`
- `0x180001b24`
- `0x180001bf7`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000c47b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000c47b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000c45a`

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
0x18000c450  sub     rsp, 38h
0x18000c454  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000c45a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000c461  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000c468  mov     [rsp+38h+var_10], eax
0x18000c46c  mov     [rsp+38h+var_18], rdx
0x18000c471  mov     rdx, rcx
0x18000c474  lea     rcx, __ImageBase
0x18000c47b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000c481  add     rsp, 38h
0x18000c485  retn
```
