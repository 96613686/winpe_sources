# DllCanUnloadNow

- ea: `0x180004e60`
- end: `0x180004e9a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004e60`
- `0x180007010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180004e6b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180004e6b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
  return result;
}

```

## disassembly

```asm
0x180004e60  sub     rsp, 28h
0x180004e64  lea     rcx, gPFactory; pPSFactoryBuffer
0x180004e6b  call    cs:__imp_NdrDllCanUnloadNow
0x180004e71  test    eax, eax
0x180004e73  jnz     short loc_180004E95
0x180004e75  mov     rax, cs:?_AtlModule@@3VCUICOMModule@@A; CUICOMModule _AtlModule
0x180004e7c  lea     rcx, ?_AtlModule@@3VCUICOMModule@@A; CUICOMModule _AtlModule
0x180004e83  mov     rax, [rax+18h]
0x180004e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8c  xor     ecx, ecx
0x180004e8e  test    eax, eax
0x180004e90  setnz   cl
0x180004e93  mov     eax, ecx
0x180004e95  add     rsp, 28h
0x180004e99  retn
```
