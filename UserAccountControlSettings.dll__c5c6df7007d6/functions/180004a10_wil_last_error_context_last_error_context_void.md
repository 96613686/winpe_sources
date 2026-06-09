# wil::last_error_context::last_error_context(void)

- ea: `0x180004a10`
- end: `0x180004a2e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006684`
- `0x18000713c`
- `0x180008100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a19`

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
0x180004a10  push    rbx
0x180004a12  sub     rsp, 20h
0x180004a16  mov     rbx, rcx
0x180004a19  call    cs:__imp_GetLastError
0x180004a1f  mov     [rbx+4], eax
0x180004a22  mov     rax, rbx
0x180004a25  mov     byte ptr [rbx], 0
0x180004a28  add     rsp, 20h
0x180004a2c  pop     rbx
0x180004a2d  retn
```
