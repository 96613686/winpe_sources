# winMutexFree

- ea: `0x180021a00`
- end: `0x180021a28`
- name: `winMutexFree`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005980`
- `0x180021a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021a0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021a0f`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 40) <= 1u )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)a1);
    return sqlite3_free(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180021a00  push    rbx
0x180021a02  sub     rsp, 20h
0x180021a06  cmp     dword ptr [rcx+28h], 1
0x180021a0a  mov     rbx, rcx
0x180021a0d  ja      short loc_180021A22
0x180021a0f  call    cs:__imp_DeleteCriticalSection
0x180021a15  mov     rcx, rbx
0x180021a18  add     rsp, 20h
0x180021a1c  pop     rbx
0x180021a1d  jmp     sqlite3_free
0x180021a22  add     rsp, 20h
0x180021a26  pop     rbx
0x180021a27  retn
```
