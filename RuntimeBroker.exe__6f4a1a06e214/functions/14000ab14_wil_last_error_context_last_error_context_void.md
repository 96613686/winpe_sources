# wil::last_error_context::last_error_context(void)

- ea: `0x14000ab14`
- end: `0x14000ab32`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140006f5c`
- `0x140007474`
- `0x1400082f4`
- `0x14000850c`
- `0x14000a1ac`
- `0x14000bb9c`
- `0x14000ce7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab1d`

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
0x14000ab14  push    rbx
0x14000ab16  sub     rsp, 20h
0x14000ab1a  mov     rbx, rcx
0x14000ab1d  call    cs:__imp_GetLastError
0x14000ab23  mov     [rbx+4], eax
0x14000ab26  mov     rax, rbx
0x14000ab29  mov     byte ptr [rbx], 0
0x14000ab2c  add     rsp, 20h
0x14000ab30  pop     rbx
0x14000ab31  retn
```
