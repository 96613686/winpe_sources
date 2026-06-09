# wil::last_error_context::last_error_context(void)

- ea: `0x180002e60`
- end: `0x180002e85`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004af4`
- `0x180006544`
- `0x1800080f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e69`

## pseudocode

```c
wil::last_error_context *__fastcall wil::last_error_context::last_error_context(wil::last_error_context *this)
{
  wil::last_error_context *result; // rax

  *((_DWORD *)this + 1) = GetLastError();
  result = this;
  *(_BYTE *)this = 0;
  return result;
}

```

## disassembly

```asm
0x180002e60  push    rbx
0x180002e62  sub     rsp, 20h
0x180002e66  mov     rbx, rcx
0x180002e69  call    cs:__imp_GetLastError
0x180002e70  nop     dword ptr [rax+rax+00h]
0x180002e75  mov     [rbx+4], eax
0x180002e78  mov     rax, rbx
0x180002e7b  mov     byte ptr [rbx], 0
0x180002e7e  add     rsp, 20h
0x180002e82  pop     rbx
0x180002e83  retn
```
