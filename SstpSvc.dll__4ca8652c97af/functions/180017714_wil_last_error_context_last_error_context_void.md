# wil::last_error_context::~last_error_context(void)

- ea: `0x180017714`
- end: `0x18001772b`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180017d18`
- `0x1800196c8`
- `0x180019a9c`
- `0x18001b450`
- `0x18001b4f8`
- `0x18001b54c`
- `0x18001b5a0`

## callees

- `0x180017714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017720`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017720`

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
0x180017714  sub     rsp, 28h
0x180017718  cmp     byte ptr [rcx], 0
0x18001771b  jnz     short loc_180017726
0x18001771d  mov     ecx, [rcx+4]; dwErrCode
0x180017720  call    cs:__imp_SetLastError
0x180017726  add     rsp, 28h
0x18001772a  retn
```
