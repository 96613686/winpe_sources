# wil::last_error_context::last_error_context(void)

- ea: `0x18000bb20`
- end: `0x18000bb3e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a978`
- `0x18000b4d0`
- `0x18000b8bc`
- `0x18000b9b0`
- `0x18000ba78`
- `0x18000bb44`
- `0x1800129f4`
- `0x180012a98`
- `0x180017554`
- `0x180018a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb29`

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
0x18000bb20  push    rbx
0x18000bb22  sub     rsp, 20h
0x18000bb26  mov     rbx, rcx
0x18000bb29  call    cs:__imp_GetLastError
0x18000bb2f  mov     [rbx+4], eax
0x18000bb32  mov     rax, rbx
0x18000bb35  mov     byte ptr [rbx], 0
0x18000bb38  add     rsp, 20h
0x18000bb3c  pop     rbx
0x18000bb3d  retn
```
