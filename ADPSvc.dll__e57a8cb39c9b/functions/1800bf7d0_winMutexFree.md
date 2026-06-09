# winMutexFree

- ea: `0x1800bf7d0`
- end: `0x1800bf7f3`
- name: `winMutexFree`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800a98a0`
- `0x1800bf7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bf7df`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bf7df`

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
0x1800bf7d0  push    rbx
0x1800bf7d2  sub     rsp, 20h
0x1800bf7d6  cmp     dword ptr [rcx+28h], 1
0x1800bf7da  mov     rbx, rcx
0x1800bf7dd  ja      short loc_1800BF7ED
0x1800bf7df  call    cs:__imp_DeleteCriticalSection
0x1800bf7e5  mov     rcx, rbx
0x1800bf7e8  call    sqlite3_free
0x1800bf7ed  add     rsp, 20h
0x1800bf7f1  pop     rbx
0x1800bf7f2  retn
```
