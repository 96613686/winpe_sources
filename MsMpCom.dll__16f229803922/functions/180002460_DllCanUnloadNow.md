# DllCanUnloadNow

- ea: `0x180002460`
- end: `0x180002489`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(__int64 *))(_AtlModule + 24))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180002460  sub     rsp, 28h
0x180002464  mov     rax, cs:?_AtlModule@@3VCMpComExportsModule@@A; CMpComExportsModule _AtlModule
0x18000246b  lea     rcx, ?_AtlModule@@3VCMpComExportsModule@@A; CMpComExportsModule _AtlModule
0x180002472  mov     rax, [rax+18h]
0x180002476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247b  xor     ecx, ecx
0x18000247d  test    eax, eax
0x18000247f  setnz   cl
0x180002482  mov     eax, ecx
0x180002484  add     rsp, 28h
0x180002488  retn
```
