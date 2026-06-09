# wil::last_error_context::~last_error_context(void)

- ea: `0x140004c60`
- end: `0x140004c77`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140007b34`
- `0x140007b88`
- `0x140007bdc`
- `0x140008a50`
- `0x140008acc`
- `0x14000b36c`
- `0x1400114dc`
- `0x140011584`
- `0x1400115d8`

## callees

- `0x140004c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c6c`

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
0x140004c60  sub     rsp, 28h
0x140004c64  cmp     byte ptr [rcx], 0
0x140004c67  jnz     short loc_140004C72
0x140004c69  mov     ecx, [rcx+4]; dwErrCode
0x140004c6c  call    cs:__imp_SetLastError
0x140004c72  add     rsp, 28h
0x140004c76  retn
```
