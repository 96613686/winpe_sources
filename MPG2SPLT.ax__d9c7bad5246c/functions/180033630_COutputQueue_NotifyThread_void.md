# COutputQueue::NotifyThread(void)

- ea: `0x180033630`
- end: `0x18003365a`
- name: `?NotifyThread@COutputQueue@@IEAAXXZ`
- size: `42`
- prototype: `void __fastcall(COutputQueue *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180033190`
- `0x180033264`
- `0x180033314`
- `0x18003354c`
- `0x180033660`
- `0x18003386c`

## callees

- `0x180033630`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180033647`
- `KERNEL32!ReleaseSemaphore` at `0x180033647`

## pseudocode

```c
void __fastcall COutputQueue::NotifyThread(COutputQueue *this)
{
  LONG v1; // edx

  v1 = *((_DWORD *)this + 27);
  if ( v1 )
  {
    ReleaseSemaphore(*((HANDLE *)this + 9), v1, 0);
    *((_DWORD *)this + 27) = 0;
  }
}

```

## disassembly

```asm
0x180033630  push    rbx
0x180033632  sub     rsp, 20h
0x180033636  mov     edx, [rcx+6Ch]; lReleaseCount
0x180033639  mov     rbx, rcx
0x18003363c  test    edx, edx
0x18003363e  jz      short loc_180033654
0x180033640  mov     rcx, [rcx+48h]; hSemaphore
0x180033644  xor     r8d, r8d; lpPreviousCount
0x180033647  call    cs:__imp_ReleaseSemaphore
0x18003364d  mov     dword ptr [rbx+6Ch], 0
0x180033654  add     rsp, 20h
0x180033658  pop     rbx
0x180033659  retn
```
