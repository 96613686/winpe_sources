# __delayLoadHelper2

- ea: `0x180017cd0`
- end: `0x180017d06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a8e`
- `0x180002b19`
- `0x180002bb6`
- `0x180002c65`
- `0x180002cf0`
- `0x180002e63`
- `0x180002f24`
- `0x180003038`
- `0x1800030c3`
- `0x180003196`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180017cfb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180017cfb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180017cda`

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
0x180017cd0  sub     rsp, 38h
0x180017cd4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180017cda  mov     r9, cs:__imp_DelayLoadFailureHook
0x180017ce1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180017ce8  mov     [rsp+38h+var_10], eax
0x180017cec  mov     [rsp+38h+var_18], rdx
0x180017cf1  mov     rdx, rcx
0x180017cf4  lea     rcx, __ImageBase
0x180017cfb  call    cs:__imp_ResolveDelayLoadedAPI
0x180017d01  add     rsp, 38h
0x180017d05  retn
```
