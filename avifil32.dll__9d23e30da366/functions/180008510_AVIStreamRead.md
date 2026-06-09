# AVIStreamRead

- ea: `0x180008510`
- end: `0x180008546`
- name: `AVIStreamRead`
- size: `54`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LONG lStart, LONG lSamples, LPVOID lpBuffer, LONG cbBuffer, LONG *plBytes, LONG *plSamples)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamRead(
        PAVISTREAM pavi,
        LONG lStart,
        LONG lSamples,
        LPVOID lpBuffer,
        LONG cbBuffer,
        LONG *plBytes,
        LONG *plSamples)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, LONG, LONG, LPVOID, LONG, LONG *, LONG *))pavi->lpVtbl->Read)(
           pavi,
           lStart,
           lSamples,
           lpBuffer,
           cbBuffer,
           plBytes,
           plSamples);
}

```

## disassembly

```asm
0x180008510  sub     rsp, 48h
0x180008514  mov     r10, [rsp+48h+plSamples]
0x18000851c  mov     rax, [rcx]
0x18000851f  mov     [rsp+48h+var_18], r10
0x180008524  mov     r10, [rsp+48h+plBytes]
0x180008529  mov     [rsp+48h+var_20], r10
0x18000852e  mov     r10d, [rsp+48h+cbBuffer]
0x180008533  mov     rax, [rax+40h]
0x180008537  mov     [rsp+48h+var_28], r10d
0x18000853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008541  add     rsp, 48h
0x180008545  retn
```
