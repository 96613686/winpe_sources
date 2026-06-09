# wil::last_error_context::~last_error_context(void)

- ea: `0x1800087bc`
- end: `0x1800087d3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008678`
- `0x180008720`
- `0x180008800`
- `0x18000ccf0`
- `0x18000d9e8`

## callees

- `0x1800087bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087c8`

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
0x1800087bc  sub     rsp, 28h
0x1800087c0  cmp     byte ptr [rcx], 0
0x1800087c3  jnz     short loc_1800087CE
0x1800087c5  mov     ecx, [rcx+4]; dwErrCode
0x1800087c8  call    cs:__imp_SetLastError
0x1800087ce  add     rsp, 28h
0x1800087d2  retn
```
