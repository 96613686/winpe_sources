# __acrt_lowio_unlock_fh

- ea: `0x14001e538`
- end: `0x14001e55f`
- name: `__acrt_lowio_unlock_fh`
- size: `39`
- prototype: `void __fastcall(int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14001bb14`
- `0x140020db4`
- `0x140021798`
- `0x140022078`
- `0x140023ffc`
- `0x14002b27d`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001e558`

## pseudocode

```c
void __fastcall _acrt_lowio_unlock_fh(int a1)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)(qword_14003E600[(__int64)a1 >> 6] + 72LL * (a1 & 0x3F)));
}

```

## disassembly

```asm
0x14001e538  movsxd  rdx, ecx
0x14001e53b  lea     r8, qword_14003E600
0x14001e542  mov     rax, rdx
0x14001e545  and     edx, 3Fh
0x14001e548  sar     rax, 6
0x14001e54c  lea     rcx, [rdx+rdx*8]
0x14001e550  mov     rax, [r8+rax*8]
0x14001e554  lea     rcx, [rax+rcx*8]
0x14001e558  jmp     cs:__imp_LeaveCriticalSection
```
