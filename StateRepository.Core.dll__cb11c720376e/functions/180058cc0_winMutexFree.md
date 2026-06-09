# winMutexFree

- ea: `0x180058cc0`
- end: `0x180058cfd`
- name: `winMutexFree`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000aac0`
- `0x180058cc0`
- `0x180060134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058ccf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058ccf`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) > 1u )
    return sqlite3ReportError(21, 30312, "misuse");
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  return sqlite3_free(a1);
}

```

## disassembly

```asm
0x180058cc0  push    rbx
0x180058cc2  sub     rsp, 20h
0x180058cc6  cmp     dword ptr [rcx+28h], 1
0x180058cca  mov     rbx, rcx
0x180058ccd  ja      short loc_180058CE2
0x180058ccf  call    cs:__imp_DeleteCriticalSection
0x180058cd5  mov     rcx, rbx
0x180058cd8  add     rsp, 20h
0x180058cdc  pop     rbx
0x180058cdd  jmp     sqlite3_free
0x180058ce2  lea     r8, aMisuse; "misuse"
0x180058ce9  mov     edx, 7668h
0x180058cee  mov     ecx, 15h
0x180058cf3  add     rsp, 20h
0x180058cf7  pop     rbx
0x180058cf8  jmp     sqlite3ReportError
```
