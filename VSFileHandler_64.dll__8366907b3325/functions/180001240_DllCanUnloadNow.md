# DllCanUnloadNow

- ea: `0x180001240`
- end: `0x180001263`
- name: `DllCanUnloadNow`
- size: `35`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180001240  sub     rsp, 28h
0x180001244  mov     rax, cs:?_AtlModule@@3VCVSFileHandlerModule@@A; CVSFileHandlerModule _AtlModule
0x18000124b  lea     rcx, ?_AtlModule@@3VCVSFileHandlerModule@@A; CVSFileHandlerModule _AtlModule
0x180001252  call    qword ptr [rax+18h]
0x180001255  xor     ecx, ecx
0x180001257  test    eax, eax
0x180001259  setnz   cl
0x18000125c  mov     eax, ecx
0x18000125e  add     rsp, 28h
0x180001262  retn
```
