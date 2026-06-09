# wil::last_error_context::last_error_context(void)

- ea: `0x140004d20`
- end: `0x140004d3e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140004250`
- `0x1400042cc`
- `0x140005818`
- `0x140009814`
- `0x1400098b8`
- `0x14000990c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d29`

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
0x140004d20  push    rbx
0x140004d22  sub     rsp, 20h
0x140004d26  mov     rbx, rcx
0x140004d29  call    cs:__imp_GetLastError
0x140004d2f  mov     [rbx+4], eax
0x140004d32  mov     rax, rbx
0x140004d35  mov     byte ptr [rbx], 0
0x140004d38  add     rsp, 20h
0x140004d3c  pop     rbx
0x140004d3d  retn
```
