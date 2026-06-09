# wil::last_error_context::last_error_context(void)

- ea: `0x180005318`
- end: `0x180005336`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180008e38`
- `0x18000a9e4`
- `0x18000aa38`
- `0x18000aa8c`
- `0x18000bb08`
- `0x18000c098`
- `0x18000f258`
- `0x18000fed4`
- `0x180010ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005321`

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
0x180005318  push    rbx
0x18000531a  sub     rsp, 20h
0x18000531e  mov     rbx, rcx
0x180005321  call    cs:__imp_GetLastError
0x180005327  mov     [rbx+4], eax
0x18000532a  mov     rax, rbx
0x18000532d  mov     byte ptr [rbx], 0
0x180005330  add     rsp, 20h
0x180005334  pop     rbx
0x180005335  retn
```
