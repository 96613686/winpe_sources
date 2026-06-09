# wil::last_error_context::last_error_context(void)

- ea: `0x140003174`
- end: `0x140003192`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140005a1c`
- `0x140006930`
- `0x140007e64`
- `0x140007eb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000317d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000317d`

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
0x140003174  push    rbx
0x140003176  sub     rsp, 20h
0x14000317a  mov     rbx, rcx
0x14000317d  call    cs:__imp_GetLastError
0x140003183  mov     [rbx+4], eax
0x140003186  mov     rax, rbx
0x140003189  mov     byte ptr [rbx], 0
0x14000318c  add     rsp, 20h
0x140003190  pop     rbx
0x140003191  retn
```
