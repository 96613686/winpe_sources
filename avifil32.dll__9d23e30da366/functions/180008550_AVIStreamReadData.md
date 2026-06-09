# AVIStreamReadData

- ea: `0x180008550`
- end: `0x180008565`
- name: `AVIStreamReadData`
- size: `21`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, DWORD fcc, LPVOID lp, LONG *lpcb)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamReadData(PAVISTREAM pavi, DWORD fcc, LPVOID lp, LONG *lpcb)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, DWORD, LPVOID, LONG *))pavi->lpVtbl->ReadData)(pavi, fcc, lp, lpcb);
}

```

## disassembly

```asm
0x180008550  sub     rsp, 38h
0x180008554  mov     rax, [rcx]
0x180008557  mov     rax, [rax+58h]
0x18000855b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008560  add     rsp, 38h
0x180008564  retn
```
