# __delayLoadHelper2

- ea: `0x180014230`
- end: `0x180014266`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180015670`
- `0x1800156fb`
- `0x1800157bc`
- `0x18001586b`
- `0x18001592c`
- `0x1800159db`
- `0x180015a66`
- `0x180015b27`
- `0x180015bb2`
- `0x180015c61`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001425b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001425b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001423a`

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
0x180014230  sub     rsp, 38h
0x180014234  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001423a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180014241  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180014248  mov     [rsp+38h+var_10], eax
0x18001424c  mov     [rsp+38h+var_18], rdx
0x180014251  mov     rdx, rcx
0x180014254  lea     rcx, __ImageBase
0x18001425b  call    cs:__imp_ResolveDelayLoadedAPI
0x180014261  add     rsp, 38h
0x180014265  retn
```
