# wil::last_error_context::last_error_context(void)

- ea: `0x1400027a0`
- end: `0x1400027be`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003f8c`
- `0x140004b0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400027a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400027a9`

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
0x1400027a0  push    rbx
0x1400027a2  sub     rsp, 20h
0x1400027a6  mov     rbx, rcx
0x1400027a9  call    cs:__imp_GetLastError
0x1400027af  mov     [rbx+4], eax
0x1400027b2  mov     rax, rbx
0x1400027b5  mov     byte ptr [rbx], 0
0x1400027b8  add     rsp, 20h
0x1400027bc  pop     rbx
0x1400027bd  retn
```
