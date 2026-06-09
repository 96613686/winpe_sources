# AVIStreamWriteData

- ea: `0x180008890`
- end: `0x1800088a5`
- name: `AVIStreamWriteData`
- size: `21`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, DWORD fcc, LPVOID lp, LONG cb)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamWriteData(PAVISTREAM pavi, DWORD fcc, LPVOID lp, LONG cb)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, DWORD, LPVOID, LONG))pavi->lpVtbl->WriteData)(pavi, fcc, lp, cb);
}

```

## disassembly

```asm
0x180008890  sub     rsp, 38h
0x180008894  mov     rax, [rcx]
0x180008897  mov     rax, [rax+60h]
0x18000889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088a0  add     rsp, 38h
0x1800088a4  retn
```
