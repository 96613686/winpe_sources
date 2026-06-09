# DllCanUnloadNow

- ea: `0x18000cbe0`
- end: `0x18000cc09`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001b010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x18000cbe0  sub     rsp, 28h
0x18000cbe4  mov     rax, cs:?_AtlModule@@3VCIdentityStoreModule@@A; CIdentityStoreModule _AtlModule
0x18000cbeb  lea     rcx, ?_AtlModule@@3VCIdentityStoreModule@@A; CIdentityStoreModule _AtlModule
0x18000cbf2  mov     rax, [rax+18h]
0x18000cbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbfb  xor     ecx, ecx
0x18000cbfd  test    eax, eax
0x18000cbff  setnz   cl
0x18000cc02  mov     eax, ecx
0x18000cc04  add     rsp, 28h
0x18000cc08  retn
```
