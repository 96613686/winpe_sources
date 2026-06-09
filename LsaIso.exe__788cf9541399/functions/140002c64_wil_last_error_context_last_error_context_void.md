# wil::last_error_context::~last_error_context(void)

- ea: `0x140002c64`
- end: `0x140002c7b`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002aa4`
- `0x140002b9c`
- `0x140009428`
- `0x14000db64`
- `0x14000dc08`
- `0x14000dc5c`
- `0x1400170e0`

## callees

- `0x140002c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002c70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002c70`

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
0x140002c64  sub     rsp, 28h
0x140002c68  cmp     byte ptr [rcx], 0
0x140002c6b  jnz     short loc_140002C76
0x140002c6d  mov     ecx, [rcx+4]; dwErrCode
0x140002c70  call    cs:__imp_SetLastError
0x140002c76  add     rsp, 28h
0x140002c7a  retn
```
