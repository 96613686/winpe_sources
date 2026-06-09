# wil::last_error_context::~last_error_context(void)

- ea: `0x14000358c`
- end: `0x1400035a3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005a1c`
- `0x140006930`
- `0x140007e64`
- `0x140007eb8`

## callees

- `0x14000358c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003598`

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
0x14000358c  sub     rsp, 28h
0x140003590  cmp     byte ptr [rcx], 0
0x140003593  jnz     short loc_14000359E
0x140003595  mov     ecx, [rcx+4]; dwErrCode
0x140003598  call    cs:__imp_SetLastError
0x14000359e  add     rsp, 28h
0x1400035a2  retn
```
