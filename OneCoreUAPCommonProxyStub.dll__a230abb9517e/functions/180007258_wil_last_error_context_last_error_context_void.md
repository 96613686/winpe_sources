# wil::last_error_context::last_error_context(void)

- ea: `0x180007258`
- end: `0x180007276`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008c1c`
- `0x180009e40`
- `0x180009e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007261`

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
0x180007258  push    rbx
0x18000725a  sub     rsp, 20h
0x18000725e  mov     rbx, rcx
0x180007261  call    cs:__imp_GetLastError
0x180007267  mov     [rbx+4], eax
0x18000726a  mov     rax, rbx
0x18000726d  mov     byte ptr [rbx], 0
0x180007270  add     rsp, 20h
0x180007274  pop     rbx
0x180007275  retn
```
