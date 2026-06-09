# __delayLoadHelper2

- ea: `0x18001a560`
- end: `0x18001a596`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002039`
- `0x18000218a`
- `0x180002215`
- `0x1800023c0`
- `0x180002559`
- `0x1800025e4`
- `0x180002723`
- `0x1800027ae`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001a58b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001a58b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001a56a`

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
0x18001a560  sub     rsp, 38h
0x18001a564  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001a56a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18001a571  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001a578  mov     [rsp+38h+var_10], eax
0x18001a57c  mov     [rsp+38h+var_18], rdx
0x18001a581  mov     rdx, rcx
0x18001a584  lea     rcx, __ImageBase
0x18001a58b  call    cs:__imp_ResolveDelayLoadedAPI
0x18001a591  add     rsp, 38h
0x18001a595  retn
```
