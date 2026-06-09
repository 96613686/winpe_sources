# wil::last_error_context::last_error_context(void)

- ea: `0x18000db60`
- end: `0x18000db7e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d0e8`
- `0x18000d884`
- `0x18000d92c`
- `0x18000da14`
- `0x18000db84`
- `0x180010be4`
- `0x18001439c`
- `0x1800143f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db69`

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
0x18000db60  push    rbx
0x18000db62  sub     rsp, 20h
0x18000db66  mov     rbx, rcx
0x18000db69  call    cs:__imp_GetLastError
0x18000db6f  mov     [rbx+4], eax
0x18000db72  mov     rax, rbx
0x18000db75  mov     byte ptr [rbx], 0
0x18000db78  add     rsp, 20h
0x18000db7c  pop     rbx
0x18000db7d  retn
```
