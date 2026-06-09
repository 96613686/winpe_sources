# DllCanUnloadNow

- ea: `0x180008680`
- end: `0x1800086ba`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008680`
- `0x180017010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000868b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000868b`

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
0x180008680  sub     rsp, 28h
0x180008684  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000868b  call    cs:__imp_NdrDllCanUnloadNow
0x180008691  test    eax, eax
0x180008693  jnz     short loc_1800086B5
0x180008695  mov     rax, cs:?_AtlModule@@3VCSlayeruiModule@@A; CSlayeruiModule _AtlModule
0x18000869c  lea     rcx, ?_AtlModule@@3VCSlayeruiModule@@A; CSlayeruiModule _AtlModule
0x1800086a3  mov     rax, [rax+18h]
0x1800086a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ac  xor     ecx, ecx
0x1800086ae  test    eax, eax
0x1800086b0  setnz   cl
0x1800086b3  mov     eax, ecx
0x1800086b5  add     rsp, 28h
0x1800086b9  retn
```
