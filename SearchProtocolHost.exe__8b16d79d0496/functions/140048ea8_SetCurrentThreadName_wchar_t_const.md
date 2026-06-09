# SetCurrentThreadName(wchar_t const *)

- ea: `0x140048ea8`
- end: `0x140048ec9`
- name: `?SetCurrentThreadName@@YAXPEB_W@Z`
- size: `33`
- prototype: `void __fastcall(const wchar_t *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14002a090`
- `0x14002d100`
- `0x14002d394`
- `0x14003a8e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140048eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140048eb1`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x140048ec2`

## pseudocode

```c
void __fastcall SetCurrentThreadName(const wchar_t *a1)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, a1);
}

```

## disassembly

```asm
0x140048ea8  push    rbx
0x140048eaa  sub     rsp, 20h
0x140048eae  mov     rbx, rcx
0x140048eb1  call    cs:__imp_GetCurrentThread
0x140048eb7  mov     rcx, rax
0x140048eba  mov     rdx, rbx
0x140048ebd  add     rsp, 20h
0x140048ec1  pop     rbx
0x140048ec2  jmp     cs:__imp_SetThreadDescription
```
