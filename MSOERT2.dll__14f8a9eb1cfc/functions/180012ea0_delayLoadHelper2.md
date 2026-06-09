# __delayLoadHelper2

- ea: `0x180012ea0`
- end: `0x180012ed6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800029d0`
- `0x180002ab5`
- `0x180002b40`
- `0x180002c6d`
- `0x180002d1c`
- `0x180002e01`
- `0x180002e9e`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x180012eaa`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180012ecb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180012ecb`

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
0x180012ea0  sub     rsp, 38h
0x180012ea4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180012eaa  mov     r9, cs:__imp_DelayLoadFailureHook
0x180012eb1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180012eb8  mov     [rsp+38h+var_10], eax
0x180012ebc  mov     [rsp+38h+var_18], rdx
0x180012ec1  mov     rdx, rcx
0x180012ec4  lea     rcx, __ImageBase
0x180012ecb  call    cs:__imp_ResolveDelayLoadedAPI
0x180012ed1  add     rsp, 38h
0x180012ed5  retn
```
