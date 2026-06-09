# __Mtxdst

- ea: `0x41e066`
- end: `0x41e074`
- name: `__Mtxdst`
- size: `14`
- prototype: `void __cdecl(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x421230`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x41e06c`
- `KERNEL32!DeleteCriticalSection` at `0x41e06c`

## pseudocode

```c
void __cdecl _Mtxdst(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x41e066  push    ebp
0x41e067  mov     ebp, esp
0x41e069  push    [ebp+lpCriticalSection]; lpCriticalSection
0x41e06c  call    ds:DeleteCriticalSection
0x41e072  pop     ebp
0x41e073  retn
```
