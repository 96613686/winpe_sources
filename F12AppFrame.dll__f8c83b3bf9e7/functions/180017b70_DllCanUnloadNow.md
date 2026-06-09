# DllCanUnloadNow

- ea: `0x180017b70`
- end: `0x180017baa`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180017b70`
- `0x180035010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180017b7b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180017b7b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(void *))(_Module + 24LL))(&_Module) != 0;
  return result;
}

```

## disassembly

```asm
0x180017b70  sub     rsp, 28h
0x180017b74  lea     rcx, gPFactory; pPSFactoryBuffer
0x180017b7b  call    cs:__imp_NdrDllCanUnloadNow
0x180017b81  test    eax, eax
0x180017b83  jnz     short loc_180017BA5
0x180017b85  mov     rax, cs:?_Module@@3VCAppModule@WTL@@A; WTL::CAppModule _Module
0x180017b8c  lea     rcx, ?_Module@@3VCAppModule@WTL@@A; WTL::CAppModule _Module
0x180017b93  mov     rax, [rax+18h]
0x180017b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b9c  xor     ecx, ecx
0x180017b9e  test    eax, eax
0x180017ba0  setnz   cl
0x180017ba3  mov     eax, ecx
0x180017ba5  add     rsp, 28h
0x180017ba9  retn
```
