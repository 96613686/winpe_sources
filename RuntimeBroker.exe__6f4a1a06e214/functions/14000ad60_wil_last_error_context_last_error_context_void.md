# wil::last_error_context::~last_error_context(void)

- ea: `0x14000ad60`
- end: `0x14000ad77`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f5c`
- `0x140007474`
- `0x1400082f4`
- `0x14000850c`
- `0x14000a1ac`
- `0x14000bb9c`
- `0x14000ce7c`

## callees

- `0x14000ad60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad6c`

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
0x14000ad60  sub     rsp, 28h
0x14000ad64  cmp     byte ptr [rcx], 0
0x14000ad67  jnz     short loc_14000AD72
0x14000ad69  mov     ecx, [rcx+4]; dwErrCode
0x14000ad6c  call    cs:__imp_SetLastError
0x14000ad72  add     rsp, 28h
0x14000ad76  retn
```
