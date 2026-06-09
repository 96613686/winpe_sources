# DllCanUnloadNow

- ea: `0x180010200`
- end: `0x18001022a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010200`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001020b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001020b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return HIDWORD(qword_18009A048) != 0;
  return result;
}

```

## disassembly

```asm
0x180010200  sub     rsp, 28h
0x180010204  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001020b  call    cs:__imp_NdrDllCanUnloadNow
0x180010212  nop     dword ptr [rax+rax+00h]
0x180010217  test    eax, eax
0x180010219  jnz     short loc_180010224
0x18001021b  cmp     dword ptr cs:qword_18009A048+4, eax
0x180010221  setnz   al
0x180010224  add     rsp, 28h
0x180010228  retn
```
