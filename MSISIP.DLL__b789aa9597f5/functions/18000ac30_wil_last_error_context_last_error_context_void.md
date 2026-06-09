# wil::last_error_context::last_error_context(void)

- ea: `0x18000ac30`
- end: `0x18000ac4e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180006370`
- `0x1800069b4`
- `0x180006fac`
- `0x180007334`
- `0x180007cb8`
- `0x1800097c0`
- `0x18000afa0`
- `0x18000cc9c`
- `0x18000cd40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac39`

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
0x18000ac30  push    rbx
0x18000ac32  sub     rsp, 20h
0x18000ac36  mov     rbx, rcx
0x18000ac39  call    cs:__imp_GetLastError
0x18000ac3f  mov     [rbx+4], eax
0x18000ac42  mov     rax, rbx
0x18000ac45  mov     byte ptr [rbx], 0
0x18000ac48  add     rsp, 20h
0x18000ac4c  pop     rbx
0x18000ac4d  retn
```
