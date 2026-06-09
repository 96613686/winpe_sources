# wil::last_error_context::last_error_context(void)

- ea: `0x1400051ec`
- end: `0x14000520a`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140007884`
- `0x1400078d8`
- `0x14000ca7c`
- `0x14000d884`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051f5`

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
0x1400051ec  push    rbx
0x1400051ee  sub     rsp, 20h
0x1400051f2  mov     rbx, rcx
0x1400051f5  call    cs:__imp_GetLastError
0x1400051fb  mov     [rbx+4], eax
0x1400051fe  mov     rax, rbx
0x140005201  mov     byte ptr [rbx], 0
0x140005204  add     rsp, 20h
0x140005208  pop     rbx
0x140005209  retn
```
