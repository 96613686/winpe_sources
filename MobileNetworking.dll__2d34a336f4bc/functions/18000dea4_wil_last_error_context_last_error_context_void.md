# wil::last_error_context::last_error_context(void)

- ea: `0x18000dea4`
- end: `0x18000dec2`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e5f4`
- `0x180010d80`
- `0x1800116a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dead`

## pseudocode

```c
wil::last_error_context *__fastcall wil::last_error_context::last_error_context(wil::last_error_context *this)
{
  DWORD LastError; // eax

  LastError = GetLastError();
  *(_BYTE *)this = 0;
  *((_DWORD *)this + 1) = LastError;
  return this;
}

```

## disassembly

```asm
0x18000dea4  push    rbx
0x18000dea6  sub     rsp, 20h
0x18000deaa  mov     rbx, rcx
0x18000dead  call    cs:__imp_GetLastError
0x18000deb3  mov     byte ptr [rbx], 0
0x18000deb6  mov     [rbx+4], eax
0x18000deb9  mov     rax, rbx
0x18000debc  add     rsp, 20h
0x18000dec0  pop     rbx
0x18000dec1  retn
```
