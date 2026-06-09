# wil::last_error_context::last_error_context(void)

- ea: `0x180003364`
- end: `0x180003382`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800048d0`
- `0x1800064e4`
- `0x1800068ac`
- `0x180008cec`
- `0x180008d94`
- `0x180008de8`
- `0x180008e3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000336d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000336d`

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
0x180003364  push    rbx
0x180003366  sub     rsp, 20h
0x18000336a  mov     rbx, rcx
0x18000336d  call    cs:__imp_GetLastError
0x180003373  mov     [rbx+4], eax
0x180003376  mov     rax, rbx
0x180003379  mov     byte ptr [rbx], 0
0x18000337c  add     rsp, 20h
0x180003380  pop     rbx
0x180003381  retn
```
