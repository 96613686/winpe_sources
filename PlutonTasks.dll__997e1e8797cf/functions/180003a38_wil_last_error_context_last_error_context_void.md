# wil::last_error_context::~last_error_context(void)

- ea: `0x180003a38`
- end: `0x180003a4f`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048d0`
- `0x1800064e4`
- `0x1800068ac`
- `0x180008cec`
- `0x180008d94`
- `0x180008de8`
- `0x180008e3c`

## callees

- `0x180003a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a44`

## pseudocode

```c
void __fastcall wil::last_error_context::~last_error_context(wil::last_error_context *this)
{
  if ( !*(_BYTE *)this )
    SetLastError(*((_DWORD *)this + 1));
}

```

## disassembly

```asm
0x180003a38  sub     rsp, 28h
0x180003a3c  cmp     byte ptr [rcx], 0
0x180003a3f  jnz     short loc_180003A4A
0x180003a41  mov     ecx, [rcx+4]; dwErrCode
0x180003a44  call    cs:__imp_SetLastError
0x180003a4a  add     rsp, 28h
0x180003a4e  retn
```
