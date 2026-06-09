# wil::last_error_context::last_error_context(void)

- ea: `0x140001c64`
- end: `0x140001c82`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140001684`
- `0x140001988`
- `0x140001a30`
- `0x140001b18`
- `0x140001c88`
- `0x1400043a4`
- `0x1400071bc`
- `0x140007210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001c6d`

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
0x140001c64  push    rbx
0x140001c66  sub     rsp, 20h
0x140001c6a  mov     rbx, rcx
0x140001c6d  call    cs:__imp_GetLastError
0x140001c73  mov     [rbx+4], eax
0x140001c76  mov     rax, rbx
0x140001c79  mov     byte ptr [rbx], 0
0x140001c7c  add     rsp, 20h
0x140001c80  pop     rbx
0x140001c81  retn
```
