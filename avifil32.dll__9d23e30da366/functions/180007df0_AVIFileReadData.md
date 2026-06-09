# AVIFileReadData

- ea: `0x180007df0`
- end: `0x180007e05`
- name: `AVIFileReadData`
- size: `21`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LONG lPos, LPVOID lpFormat, LONG cbFormat)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIFileReadData(PAVISTREAM pavi, LONG lPos, LPVOID lpFormat, LONG cbFormat)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, LONG, LPVOID, LONG))pavi->lpVtbl->SetFormat)(
           pavi,
           lPos,
           lpFormat,
           cbFormat);
}

```

## disassembly

```asm
0x180007df0  sub     rsp, 38h; AVIFileReadData
0x180007df4  mov     rax, [rcx]
0x180007df7  mov     rax, [rax+38h]
0x180007dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e00  add     rsp, 38h
0x180007e04  retn
```
