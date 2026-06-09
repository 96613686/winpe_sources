# wil::last_error_context::~last_error_context(void)

- ea: `0x180004cac`
- end: `0x180004cc3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006684`
- `0x18000713c`
- `0x180008100`

## callees

- `0x180004cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004cb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004cb8`

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
0x180004cac  sub     rsp, 28h
0x180004cb0  cmp     byte ptr [rcx], 0
0x180004cb3  jnz     short loc_180004CBE
0x180004cb5  mov     ecx, [rcx+4]; dwErrCode
0x180004cb8  call    cs:__imp_SetLastError
0x180004cbe  add     rsp, 28h
0x180004cc2  retn
```
