# wil::last_error_context::~last_error_context(void)

- ea: `0x180006818`
- end: `0x18000682f`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d04`
- `0x180005fb8`
- `0x18000fa58`
- `0x180013464`
- `0x1800175ac`

## callees

- `0x180006818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006824`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006824`

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
0x180006818  sub     rsp, 28h
0x18000681c  cmp     byte ptr [rcx], 0
0x18000681f  jnz     short loc_18000682A
0x180006821  mov     ecx, [rcx+4]; dwErrCode
0x180006824  call    cs:__imp_SetLastError
0x18000682a  add     rsp, 28h
0x18000682e  retn
```
