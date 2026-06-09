# wil::last_error_context::~last_error_context(void)

- ea: `0x180003140`
- end: `0x18000315e`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004af4`
- `0x180006544`
- `0x1800080f8`

## callees

- `0x180003140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000314c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000314c`

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
0x180003140  sub     rsp, 28h
0x180003144  cmp     byte ptr [rcx], 0
0x180003147  jnz     short loc_180003158
0x180003149  mov     ecx, [rcx+4]; dwErrCode
0x18000314c  call    cs:__imp_SetLastError
0x180003153  nop     dword ptr [rax+rax+00h]
0x180003158  add     rsp, 28h
0x18000315c  retn
```
