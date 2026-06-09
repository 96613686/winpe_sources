# AVIFileCreateStreamW

- ea: `0x180007960`
- end: `0x180007973`
- name: `AVIFileCreateStreamW`
- size: `19`
- prototype: `HRESULT __stdcall(PAVIFILE pfile, PAVISTREAM *ppavi, AVISTREAMINFOW *psi)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIFileCreateStreamW(PAVIFILE pfile, PAVISTREAM *ppavi, AVISTREAMINFOW *psi)
{
  *ppavi = 0;
  return ((__int64 (__fastcall *)(PAVIFILE, PAVISTREAM *, AVISTREAMINFOW *))pfile->lpVtbl->CreateStream)(
           pfile,
           ppavi,
           psi);
}

```

## disassembly

```asm
0x180007960  mov     qword ptr [rdx], 0; AVIFileCreateStream
0x180007967  mov     rax, [rcx]
0x18000796a  mov     rax, [rax+28h]
0x18000796e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
