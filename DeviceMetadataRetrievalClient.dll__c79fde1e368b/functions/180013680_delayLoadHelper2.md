# __delayLoadHelper2

- ea: `0x180013680`
- end: `0x1800136b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001fff`
- `0x18000208a`
- `0x180002115`
- `0x1800021e8`
- `0x1800022a9`
- `0x180002442`
- `0x1800024cd`
- `0x180002558`
- `0x1800026bb`
- `0x180002746`
- `0x1800027f5`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800136ab`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800136ab`
- `KERNEL32!DelayLoadFailureHook` at `0x18001368a`

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
0x180013680  sub     rsp, 38h
0x180013684  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001368a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180013691  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180013698  mov     [rsp+38h+var_10], eax
0x18001369c  mov     [rsp+38h+var_18], rdx
0x1800136a1  mov     rdx, rcx
0x1800136a4  lea     rcx, __ImageBase
0x1800136ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1800136b1  add     rsp, 38h
0x1800136b5  retn
```
