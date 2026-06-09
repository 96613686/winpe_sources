# AVIStreamWrite

- ea: `0x180008840`
- end: `0x180008888`
- name: `AVIStreamWrite`
- size: `72`
- prototype: `HRESULT __stdcall(PAVISTREAM pavi, LONG lStart, LONG lSamples, LPVOID lpBuffer, LONG cbBuffer, DWORD dwFlags, LONG *plSampWritten, LONG *plBytesWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
HRESULT __stdcall AVIStreamWrite(
        PAVISTREAM pavi,
        LONG lStart,
        LONG lSamples,
        LPVOID lpBuffer,
        LONG cbBuffer,
        DWORD dwFlags,
        LONG *plSampWritten,
        LONG *plBytesWritten)
{
  return ((__int64 (__fastcall *)(PAVISTREAM, LONG, LONG, LPVOID, LONG, DWORD, LONG *, LONG *))pavi->lpVtbl->Write)(
           pavi,
           lStart,
           lSamples,
           lpBuffer,
           cbBuffer,
           dwFlags,
           plSampWritten,
           plBytesWritten);
}

```

## disassembly

```asm
0x180008840  mov     r11, rsp
0x180008843  sub     rsp, 58h
0x180008847  mov     r10, [rsp+58h+plBytesWritten]
0x18000884f  mov     rax, [rcx]
0x180008852  mov     [r11-20h], r10
0x180008856  mov     r10, [rsp+58h+plSampWritten]
0x18000885e  mov     [r11-28h], r10
0x180008862  mov     r10d, [rsp+58h+dwFlags]
0x18000886a  mov     rax, [rax+48h]
0x18000886e  mov     [r11-30h], r10d
0x180008872  mov     r10d, [rsp+58h+cbBuffer]
0x18000887a  mov     [r11-38h], r10d
0x18000887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008883  add     rsp, 58h
0x180008887  retn
```
