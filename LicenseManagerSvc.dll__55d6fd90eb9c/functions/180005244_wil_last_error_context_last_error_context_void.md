# wil::last_error_context::~last_error_context(void)

- ea: `0x180005244`
- end: `0x18000525b`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001aa0`
- `0x180002c80`
- `0x180007694`
- `0x180008528`
- `0x1800097e8`
- `0x1800098d4`
- `0x180009cc0`
- `0x18000b478`

## callees

- `0x180005244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005250`

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
0x180005244  sub     rsp, 28h
0x180005248  cmp     byte ptr [rcx], 0
0x18000524b  jnz     short loc_180005256
0x18000524d  mov     ecx, [rcx+4]; dwErrCode
0x180005250  call    cs:__imp_SetLastError
0x180005256  add     rsp, 28h
0x18000525a  retn
```
