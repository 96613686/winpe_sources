# __delayLoadHelper2

- ea: `0x1400023e0`
- end: `0x140002416`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003e4e`
- `0x140003eeb`
- `0x140003fbe`
- `0x140004049`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000240b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000240b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1400023ea`

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
0x1400023e0  sub     rsp, 38h
0x1400023e4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1400023ea  mov     r9, cs:__imp_DelayLoadFailureHook
0x1400023f1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1400023f8  mov     [rsp+38h+var_10], eax
0x1400023fc  mov     [rsp+38h+var_18], rdx
0x140002401  mov     rdx, rcx
0x140002404  lea     rcx, __ImageBase
0x14000240b  call    cs:__imp_ResolveDelayLoadedAPI
0x140002411  add     rsp, 38h
0x140002415  retn
```
