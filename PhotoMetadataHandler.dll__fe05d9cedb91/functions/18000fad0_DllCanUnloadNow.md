# DllCanUnloadNow

- ea: `0x18000fad0`
- end: `0x18000faf3`
- name: `DllCanUnloadNow`
- size: `35`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000fad0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000fadb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000fadb`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return HIDWORD(qword_180098F58) != 0;
  return result;
}

```

## disassembly

```asm
0x18000fad0  sub     rsp, 28h
0x18000fad4  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000fadb  call    cs:__imp_NdrDllCanUnloadNow
0x18000fae1  test    eax, eax
0x18000fae3  jnz     short loc_18000FAEE
0x18000fae5  cmp     dword ptr cs:qword_180098F58+4, eax
0x18000faeb  setnz   al
0x18000faee  add     rsp, 28h
0x18000faf2  retn
```
