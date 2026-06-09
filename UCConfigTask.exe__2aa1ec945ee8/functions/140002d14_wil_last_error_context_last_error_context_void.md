# wil::last_error_context::last_error_context(void)

- ea: `0x140002d14`
- end: `0x140002d32`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003998`
- `0x140005370`
- `0x14000572c`
- `0x14000740c`
- `0x1400074b4`
- `0x140007508`
- `0x14000755c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d1d`

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
0x140002d14  push    rbx
0x140002d16  sub     rsp, 20h
0x140002d1a  mov     rbx, rcx
0x140002d1d  call    cs:__imp_GetLastError
0x140002d23  mov     [rbx+4], eax
0x140002d26  mov     rax, rbx
0x140002d29  mov     byte ptr [rbx], 0
0x140002d2c  add     rsp, 20h
0x140002d30  pop     rbx
0x140002d31  retn
```
