# winMutexFree

- ea: `0x14009fdb0`
- end: `0x14009fde1`
- name: `winMutexFree`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140063280`
- `0x14008ac90`
- `0x14009fdb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14009fdce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14009fdce`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) > 1u )
    return sqlite3MisuseError(29404);
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  return sqlite3_free(a1);
}

```

## disassembly

```asm
0x14009fdb0  push    rbx
0x14009fdb2  sub     rsp, 20h
0x14009fdb6  cmp     dword ptr [rcx+28h], 1
0x14009fdba  mov     rbx, rcx
0x14009fdbd  jbe     short loc_14009FDCE
0x14009fdbf  mov     ecx, 72DCh; lpCriticalSection
0x14009fdc4  add     rsp, 20h
0x14009fdc8  pop     rbx
0x14009fdc9  jmp     sqlite3MisuseError
0x14009fdce  call    cs:__imp_DeleteCriticalSection
0x14009fdd4  mov     rcx, rbx
0x14009fdd7  add     rsp, 20h
0x14009fddb  pop     rbx
0x14009fddc  jmp     sqlite3_free
```
