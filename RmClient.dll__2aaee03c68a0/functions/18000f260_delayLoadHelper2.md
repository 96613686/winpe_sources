# __delayLoadHelper2

- ea: `0x18000f260`
- end: `0x18000f296`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800141f0`
- `0x18001427b`
- `0x18001432a`
- `0x1800143d9`
- `0x180014488`
- `0x180014513`
- `0x18001459e`
- `0x18001464d`
- `0x180014744`
- `0x180014947`
- `0x1800149f6`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f28b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000f28b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000f26a`

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
0x18000f260  sub     rsp, 38h
0x18000f264  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000f26a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000f271  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000f278  mov     [rsp+38h+var_10], eax
0x18000f27c  mov     [rsp+38h+var_18], rdx
0x18000f281  mov     rdx, rcx
0x18000f284  lea     rcx, __ImageBase
0x18000f28b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000f291  add     rsp, 38h
0x18000f295  retn
```
