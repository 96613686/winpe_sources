# wil::last_error_context::last_error_context(void)

- ea: `0x140003218`
- end: `0x14000323d`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140005d34`
- `0x140006d38`
- `0x140008294`
- `0x1400082f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003221`

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
0x140003218  push    rbx
0x14000321a  sub     rsp, 20h
0x14000321e  mov     rbx, rcx
0x140003221  call    cs:__imp_GetLastError
0x140003228  nop     dword ptr [rax+rax+00h]
0x14000322d  mov     [rbx+4], eax
0x140003230  mov     rax, rbx
0x140003233  mov     byte ptr [rbx], 0
0x140003236  add     rsp, 20h
0x14000323a  pop     rbx
0x14000323b  retn
```
