# winMutexFree

- ea: `0x1800a3950`
- end: `0x1800a398d`
- name: `winMutexFree`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180012470`
- `0x18003a860`
- `0x1800a3950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a397a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a397a`

## pseudocode

```c
__int64 __fastcall winMutexFree(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) > 1u )
    return sqlite3ReportError(21, 30081, "misuse");
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  return sqlite3_free(a1);
}

```

## disassembly

```asm
0x1800a3950  push    rbx
0x1800a3952  sub     rsp, 20h
0x1800a3956  cmp     dword ptr [rcx+28h], 1
0x1800a395a  mov     rbx, rcx
0x1800a395d  jbe     short loc_1800A397A
0x1800a395f  lea     r8, aMisuse; "misuse"
0x1800a3966  mov     edx, 7581h
0x1800a396b  mov     ecx, 15h; lpCriticalSection
0x1800a3970  add     rsp, 20h
0x1800a3974  pop     rbx
0x1800a3975  jmp     sqlite3ReportError
0x1800a397a  call    cs:__imp_DeleteCriticalSection
0x1800a3980  mov     rcx, rbx
0x1800a3983  add     rsp, 20h
0x1800a3987  pop     rbx
0x1800a3988  jmp     sqlite3_free
```
