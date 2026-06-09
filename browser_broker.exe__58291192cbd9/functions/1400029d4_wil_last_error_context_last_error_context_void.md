# wil::last_error_context::~last_error_context(void)

- ea: `0x1400029d4`
- end: `0x1400029eb`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f8c`
- `0x140004b0c`

## callees

- `0x1400029d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400029e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400029e0`

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
0x1400029d4  sub     rsp, 28h
0x1400029d8  cmp     byte ptr [rcx], 0
0x1400029db  jnz     short loc_1400029E6
0x1400029dd  mov     ecx, [rcx+4]; dwErrCode
0x1400029e0  call    cs:__imp_SetLastError
0x1400029e6  add     rsp, 28h
0x1400029ea  retn
```
