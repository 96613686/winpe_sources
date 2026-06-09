# __delayLoadHelper2

- ea: `0x180013920`
- end: `0x180013956`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800026ae`
- `0x18000274b`
- `0x1800027d6`
- `0x180002861`
- `0x1800028ec`
- `0x180002977`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001394b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001394b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001392a`

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
0x180013920  sub     rsp, 38h
0x180013924  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001392a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180013931  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180013938  mov     [rsp+38h+var_10], eax
0x18001393c  mov     [rsp+38h+var_18], rdx
0x180013941  mov     rdx, rcx
0x180013944  lea     rcx, __ImageBase
0x18001394b  call    cs:__imp_ResolveDelayLoadedAPI
0x180013951  add     rsp, 38h
0x180013955  retn
```
