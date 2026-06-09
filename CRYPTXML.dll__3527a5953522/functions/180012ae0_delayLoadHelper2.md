# __delayLoadHelper2

- ea: `0x180012ae0`
- end: `0x180012b1d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800156a6`
- `0x18001571f`
- `0x1800158a6`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180012b0b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180012b0b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180012aea`

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
0x180012ae0  sub     rsp, 38h
0x180012ae4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180012aea  mov     r9, cs:__imp_DelayLoadFailureHook
0x180012af1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180012af8  mov     [rsp+38h+var_10], eax
0x180012afc  mov     [rsp+38h+var_18], rdx
0x180012b01  mov     rdx, rcx
0x180012b04  lea     rcx, __ImageBase
0x180012b0b  call    cs:__imp_ResolveDelayLoadedAPI
0x180012b12  nop     dword ptr [rax+rax+00h]
0x180012b17  add     rsp, 38h
0x180012b1b  retn
```
