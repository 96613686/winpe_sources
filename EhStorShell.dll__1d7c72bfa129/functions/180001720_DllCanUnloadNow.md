# DllCanUnloadNow

- ea: `0x180001720`
- end: `0x180001749`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180001720  sub     rsp, 28h
0x180001724  mov     rax, cs:?_AtlModule@@3VCEnhancedStorageApiModule@@A; CEnhancedStorageApiModule _AtlModule
0x18000172b  lea     rcx, ?_AtlModule@@3VCEnhancedStorageApiModule@@A; CEnhancedStorageApiModule _AtlModule
0x180001732  mov     rax, [rax+18h]
0x180001736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173b  xor     ecx, ecx
0x18000173d  test    eax, eax
0x18000173f  setnz   cl
0x180001742  mov     eax, ecx
0x180001744  add     rsp, 28h
0x180001748  retn
```
