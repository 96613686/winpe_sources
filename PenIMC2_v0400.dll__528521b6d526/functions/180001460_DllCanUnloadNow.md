# DllCanUnloadNow

- ea: `0x180001460`
- end: `0x18000149e`
- name: `DllCanUnloadNow`
- size: `62`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001460`
- `0x18000e4a0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000146d`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000146d`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax
  HRESULT v1; // ebx

  result = NdrDllCanUnloadNow(&gPFactory);
  v1 = 0;
  if ( !result )
  {
    LOBYTE(v1) = (*(unsigned int (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180001460  push    rbx
0x180001462  sub     rsp, 20h
0x180001466  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000146d  call    cs:__imp_NdrDllCanUnloadNow
0x180001473  xor     ebx, ebx
0x180001475  test    eax, eax
0x180001477  jnz     short loc_180001498
0x180001479  mov     rcx, cs:?_AtlModule@@3VCPenImcModule@@A; CPenImcModule _AtlModule
0x180001480  mov     rax, [rcx+18h]
0x180001484  lea     rcx, ?_AtlModule@@3VCPenImcModule@@A; CPenImcModule _AtlModule
0x18000148b  call    cs:__guard_dispatch_icall_fptr
0x180001491  test    eax, eax
0x180001493  setnz   bl
0x180001496  mov     eax, ebx
0x180001498  add     rsp, 20h
0x18000149c  pop     rbx
0x18000149d  retn
```
