# wil::last_error_context::last_error_context(void)

- ea: `0x18000500c`
- end: `0x18000502a`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001aa0`
- `0x180002c80`
- `0x180007694`
- `0x180008528`
- `0x1800097e8`
- `0x1800098d4`
- `0x180009cc0`
- `0x18000b478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005015`

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
0x18000500c  push    rbx
0x18000500e  sub     rsp, 20h
0x180005012  mov     rbx, rcx
0x180005015  call    cs:__imp_GetLastError
0x18000501b  mov     [rbx+4], eax
0x18000501e  mov     rax, rbx
0x180005021  mov     byte ptr [rbx], 0
0x180005024  add     rsp, 20h
0x180005028  pop     rbx
0x180005029  retn
```
