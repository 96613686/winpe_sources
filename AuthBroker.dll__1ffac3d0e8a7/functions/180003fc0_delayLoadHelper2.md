# __delayLoadHelper2

- ea: `0x180003fc0`
- end: `0x180003ff6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `void *__fastcall(const _IMAGE_DELAYLOAD_DESCRIPTOR *DelayloadDescriptor, _IMAGE_THUNK_DATA64 *ThunkAddress)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180008570`
- `0x180008643`
- `0x1800087be`
- `0x180008849`
- `0x180008940`
- `0x180008a37`
- `0x180008b64`
- `0x180008c76`
- `0x180008d01`
- `0x180008dc2`
- `0x180008e4d`
- `0x180008ed8`
- `0x180008f63`
- `0x180009056`
- `0x180009136`
- `0x18000921b`
- `0x1800092dc`
- `0x180009367`
- `0x18000944c`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003feb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003feb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180003fca`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(
        const _IMAGE_DELAYLOAD_DESCRIPTOR *DelayloadDescriptor,
        _IMAGE_THUNK_DATA64 *ThunkAddress)
{
  return ResolveDelayLoadedAPI(
           &_ImageBase,
           DelayloadDescriptor,
           _pfnDefaultDliFailureHook2,
           DelayLoadFailureHook,
           ThunkAddress,
           _ResolveDelayLoadedAPIFlags);
}

```

## disassembly

```asm
0x180003fc0  sub     rsp, 38h
0x180003fc4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180003fca  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003fd1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003fd8  mov     [rsp+38h+var_10], eax
0x180003fdc  mov     [rsp+38h+var_18], ThunkAddress
0x180003fe1  mov     ThunkAddress, DelayloadDescriptor
0x180003fe4  lea     DelayloadDescriptor, __ImageBase
0x180003feb  call    cs:__imp_ResolveDelayLoadedAPI
0x180003ff1  add     rsp, 38h
0x180003ff5  retn
```
