# __delayLoadHelper2

- ea: `0x180004570`
- end: `0x1800045a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800051e0`
- `0x18000528f`
- `0x18000531a`
- `0x1800053a5`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x18000457a`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18000459b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18000459b`

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
0x180004570  sub     rsp, 38h
0x180004574  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000457a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180004581  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180004588  mov     [rsp+38h+var_10], eax
0x18000458c  mov     [rsp+38h+var_18], rdx
0x180004591  mov     rdx, rcx
0x180004594  lea     rcx, __ImageBase
0x18000459b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800045a1  add     rsp, 38h
0x1800045a5  retn
```
