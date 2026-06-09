# DllCanUnloadNow

- ea: `0x180004890`
- end: `0x1800048b9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180004890  sub     rsp, 28h
0x180004894  mov     rax, cs:?_AtlModule@@3VCommsPlatformHelperUtilModule@@A; CommsPlatformHelperUtilModule _AtlModule
0x18000489b  lea     rcx, ?_AtlModule@@3VCommsPlatformHelperUtilModule@@A; CommsPlatformHelperUtilModule _AtlModule
0x1800048a2  mov     rax, [rax+18h]
0x1800048a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ab  xor     ecx, ecx
0x1800048ad  test    eax, eax
0x1800048af  setnz   cl
0x1800048b2  mov     eax, ecx
0x1800048b4  add     rsp, 28h
0x1800048b8  retn
```
