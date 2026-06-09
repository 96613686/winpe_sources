# IsPseudoHandle(void *)

- ea: `0x1800235a0`
- end: `0x1800235cb`
- name: `?IsPseudoHandle@@YA_NPEAX@Z`
- size: `43`
- prototype: `bool __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180021570`
- `0x180023f70`

## callees

- `0x1800235a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800235b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800235b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800235a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800235a9`

## pseudocode

```c
bool __fastcall IsPseudoHandle(HANDLE a1)
{
  return a1 == GetCurrentProcess() || a1 == GetCurrentThread();
}

```

## disassembly

```asm
0x1800235a0  push    rbx
0x1800235a2  sub     rsp, 20h
0x1800235a6  mov     rbx, rcx
0x1800235a9  call    cs:__imp_GetCurrentProcess
0x1800235af  cmp     rbx, rax
0x1800235b2  jz      short loc_1800235C3
0x1800235b4  call    cs:__imp_GetCurrentThread
0x1800235ba  cmp     rbx, rax
0x1800235bd  jz      short loc_1800235C3
0x1800235bf  xor     al, al
0x1800235c1  jmp     short loc_1800235C5
0x1800235c3  mov     al, 1
0x1800235c5  add     rsp, 20h
0x1800235c9  pop     rbx
0x1800235ca  retn
```
