# __delayLoadHelper2

- ea: `0x180007cd0`
- end: `0x180007d06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a4f6`
- `0x18000a581`
- `0x18000a60c`
- `0x18000a697`
- `0x18000a830`
- `0x18000a903`
- `0x18000a9a0`
- `0x18000aacd`
- `0x18000ab58`
- `0x18000ac07`
- `0x18000acb6`
- `0x18000adbf`
- `0x18000ae6e`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007cfb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180007cfb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180007cda`

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
0x180007cd0  sub     rsp, 38h
0x180007cd4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180007cda  mov     r9, cs:__imp_DelayLoadFailureHook
0x180007ce1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180007ce8  mov     [rsp+38h+var_10], eax
0x180007cec  mov     [rsp+38h+var_18], rdx
0x180007cf1  mov     rdx, rcx
0x180007cf4  lea     rcx, __ImageBase
0x180007cfb  call    cs:__imp_ResolveDelayLoadedAPI
0x180007d01  add     rsp, 38h
0x180007d05  retn
```
