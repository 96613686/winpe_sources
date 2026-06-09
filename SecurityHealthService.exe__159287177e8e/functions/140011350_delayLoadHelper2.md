# __delayLoadHelper2

- ea: `0x140011350`
- end: `0x140011386`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002056`
- `0x140002105`
- `0x1400021a2`
- `0x14000222d`
- `0x1400022ca`
- `0x1400023be`
- `0x14000264c`
- `0x1400026d7`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x14001137b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x14001137b`
- `KERNEL32!DelayLoadFailureHook` at `0x14001135a`

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
0x140011350  sub     rsp, 38h
0x140011354  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14001135a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140011361  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140011368  mov     [rsp+38h+var_10], eax
0x14001136c  mov     [rsp+38h+var_18], rdx
0x140011371  mov     rdx, rcx
0x140011374  lea     rcx, __ImageBase
0x14001137b  call    cs:__imp_ResolveDelayLoadedAPI
0x140011381  add     rsp, 38h
0x140011385  retn
```
