# CSpinLock::_IsLocked(void)

- ea: `0x180005150`
- end: `0x180005172`
- name: `?_IsLocked@CSpinLock@@AEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a60`
- `0x180003b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005159`

## pseudocode

```c
bool __fastcall CSpinLock::_IsLocked(CSpinLock *this)
{
  return (*(_DWORD *)this & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC);
}

```

## disassembly

```asm
0x180005150  push    rbx
0x180005152  sub     rsp, 20h
0x180005156  mov     rbx, rcx
0x180005159  call    cs:__imp_GetCurrentThreadId
0x18000515f  mov     ecx, [rbx]
0x180005161  and     eax, 0FFFFFFFCh
0x180005164  and     ecx, 0FFFFFFFCh
0x180005167  cmp     ecx, eax
0x180005169  setz    al
0x18000516c  add     rsp, 20h
0x180005170  pop     rbx
0x180005171  retn
```
