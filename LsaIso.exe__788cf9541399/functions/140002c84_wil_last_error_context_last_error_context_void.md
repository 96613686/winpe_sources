# wil::last_error_context::last_error_context(void)

- ea: `0x140002c84`
- end: `0x140002ca2`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140002aa4`
- `0x140002b9c`
- `0x140009428`
- `0x14000db64`
- `0x14000dc08`
- `0x14000dc5c`
- `0x1400170e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c8d`

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
0x140002c84  push    rbx
0x140002c86  sub     rsp, 20h
0x140002c8a  mov     rbx, rcx
0x140002c8d  call    cs:__imp_GetLastError
0x140002c93  mov     [rbx+4], eax
0x140002c96  mov     rax, rbx
0x140002c99  mov     byte ptr [rbx], 0
0x140002c9c  add     rsp, 20h
0x140002ca0  pop     rbx
0x140002ca1  retn
```
