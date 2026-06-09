# winMutexFree

- ea: `0x180063080`
- end: `0x1800630bd`
- name: `winMutexFree`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002619c`
- `0x180041eb0`
- `0x180063080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006308f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006308f`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) > 1u )
    return sqlite3ReportError(21, 30176, "misuse");
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  return sqlite3_free(a1);
}

```

## disassembly

```asm
0x180063080  push    rbx
0x180063082  sub     rsp, 20h
0x180063086  cmp     dword ptr [rcx+28h], 1
0x18006308a  mov     rbx, rcx
0x18006308d  ja      short loc_1800630A2
0x18006308f  call    cs:__imp_DeleteCriticalSection
0x180063095  mov     rcx, rbx
0x180063098  add     rsp, 20h
0x18006309c  pop     rbx
0x18006309d  jmp     sqlite3_free
0x1800630a2  lea     r8, aMisuse; "misuse"
0x1800630a9  mov     edx, 75E0h
0x1800630ae  mov     ecx, 15h
0x1800630b3  add     rsp, 20h
0x1800630b7  pop     rbx
0x1800630b8  jmp     sqlite3ReportError
```
