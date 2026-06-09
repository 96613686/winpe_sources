# DllCanUnloadNow

- ea: `0x18000c2e0`
- end: `0x18000c309`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x18000c2e0  sub     rsp, 28h
0x18000c2e4  mov     rax, cs:?_AtlModule@@3VCRemoveDeviceContextHandlerModule@@A; CRemoveDeviceContextHandlerModule _AtlModule
0x18000c2eb  lea     rcx, ?_AtlModule@@3VCRemoveDeviceContextHandlerModule@@A; CRemoveDeviceContextHandlerModule _AtlModule
0x18000c2f2  mov     rax, [rax+18h]
0x18000c2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2fb  xor     ecx, ecx
0x18000c2fd  test    eax, eax
0x18000c2ff  setnz   cl
0x18000c302  mov     eax, ecx
0x18000c304  add     rsp, 28h
0x18000c308  retn
```
