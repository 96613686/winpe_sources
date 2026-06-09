# __delayLoadHelper2

- ea: `0x180011cc0`
- end: `0x180011cf6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002346`
- `0x1800023f5`
- `0x1800024d6`
- `0x180002561`
- `0x180002658`
- `0x180002719`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180011ceb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180011ceb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180011cca`

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
0x180011cc0  sub     rsp, 38h
0x180011cc4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180011cca  mov     r9, cs:__imp_DelayLoadFailureHook
0x180011cd1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180011cd8  mov     [rsp+38h+var_10], eax
0x180011cdc  mov     [rsp+38h+var_18], rdx
0x180011ce1  mov     rdx, rcx
0x180011ce4  lea     rcx, __ImageBase
0x180011ceb  call    cs:__imp_ResolveDelayLoadedAPI
0x180011cf1  add     rsp, 38h
0x180011cf5  retn
```
