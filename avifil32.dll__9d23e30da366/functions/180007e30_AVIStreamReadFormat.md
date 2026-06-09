# AVIStreamReadFormat

- ea: `0x180007e30`
- end: `0x180007e45`
- name: `AVIStreamReadFormat`
- size: `21`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LONG lPos, LPVOID lpFormat, LONG *lpcbFormat)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamReadFormat(PAVISTREAM pavi, LONG lPos, LPVOID lpFormat, LONG *lpcbFormat)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, LONG, LPVOID, LONG *))pavi->lpVtbl->ReadFormat)(
           pavi,
           lPos,
           lpFormat,
           lpcbFormat);
}

```

## disassembly

```asm
0x180007e30  sub     rsp, 38h; AVIFileWriteData
0x180007e34  mov     rax, [rcx]
0x180007e37  mov     rax, [rax+30h]
0x180007e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e40  add     rsp, 38h
0x180007e44  retn
```
