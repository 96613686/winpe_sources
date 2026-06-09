# wil::last_error_context::last_error_context(void)

- ea: `0x1400047f8`
- end: `0x140004816`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140007b34`
- `0x140007b88`
- `0x140007bdc`
- `0x140008a50`
- `0x140008acc`
- `0x14000b36c`
- `0x1400114dc`
- `0x140011584`
- `0x1400115d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004801`

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
0x1400047f8  push    rbx
0x1400047fa  sub     rsp, 20h
0x1400047fe  mov     rbx, rcx
0x140004801  call    cs:__imp_GetLastError
0x140004807  mov     [rbx+4], eax
0x14000480a  mov     rax, rbx
0x14000480d  mov     byte ptr [rbx], 0
0x140004810  add     rsp, 20h
0x140004814  pop     rbx
0x140004815  retn
```
