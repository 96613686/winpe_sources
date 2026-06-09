# DllCanUnloadNow

- ea: `0x180012d90`
- end: `0x180012dca`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012d90`
- `0x180014010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180012d9b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180012d9b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return (*(__int64 (__fastcall **)(__int64 *))(g_comServer + 24))(&g_comServer) != 0;
  return result;
}

```

## disassembly

```asm
0x180012d90  sub     rsp, 28h
0x180012d94  lea     rcx, gPFactory; pPSFactoryBuffer
0x180012d9b  call    cs:__imp_NdrDllCanUnloadNow
0x180012da1  test    eax, eax
0x180012da3  jnz     short loc_180012DC5
0x180012da5  mov     rax, cs:?g_comServer@@3VDmrcComServer@@A; DmrcComServer g_comServer
0x180012dac  lea     rcx, ?g_comServer@@3VDmrcComServer@@A; DmrcComServer g_comServer
0x180012db3  mov     rax, [rax+18h]
0x180012db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dbc  xor     ecx, ecx
0x180012dbe  test    eax, eax
0x180012dc0  setnz   cl
0x180012dc3  mov     eax, ecx
0x180012dc5  add     rsp, 28h
0x180012dc9  retn
```
