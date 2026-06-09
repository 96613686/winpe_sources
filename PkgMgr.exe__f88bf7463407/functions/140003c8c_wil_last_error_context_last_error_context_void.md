# wil::last_error_context::last_error_context(void)

- ea: `0x140003c8c`
- end: `0x140003caa`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400063c8`
- `0x14000641c`
- `0x14000e29c`
- `0x14000e318`
- `0x14000ebdc`
- `0x140010870`
- `0x140010918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c95`

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
0x140003c8c  push    rbx
0x140003c8e  sub     rsp, 20h
0x140003c92  mov     rbx, rcx
0x140003c95  call    cs:__imp_GetLastError
0x140003c9b  mov     [rbx+4], eax
0x140003c9e  mov     rax, rbx
0x140003ca1  mov     byte ptr [rbx], 0
0x140003ca4  add     rsp, 20h
0x140003ca8  pop     rbx
0x140003ca9  retn
```
