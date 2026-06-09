# CSmallSpinLock::IsWriteLocked(void)

- ea: `0x180003cd0`
- end: `0x180003cec`
- name: `?IsWriteLocked@CSmallSpinLock@@QEBA_NXZ`
- size: `28`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cd9`

## pseudocode

```c
bool __fastcall CSmallSpinLock::IsWriteLocked(CSmallSpinLock *this)
{
  return *(_DWORD *)this == GetCurrentThreadId();
}

```

## disassembly

```asm
0x180003cd0  push    rbx
0x180003cd2  sub     rsp, 20h
0x180003cd6  mov     rbx, rcx
0x180003cd9  call    cs:__imp_GetCurrentThreadId
0x180003cdf  mov     ecx, [rbx]
0x180003ce1  cmp     ecx, eax
0x180003ce3  setz    al
0x180003ce6  add     rsp, 20h
0x180003cea  pop     rbx
0x180003ceb  retn
```
