# wil::last_error_context::~last_error_context(void)

- ea: `0x1400032a8`
- end: `0x1400032bf`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003998`
- `0x140005370`
- `0x14000572c`
- `0x14000740c`
- `0x1400074b4`
- `0x140007508`
- `0x14000755c`

## callees

- `0x1400032a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400032b4`

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
0x1400032a8  sub     rsp, 28h
0x1400032ac  cmp     byte ptr [rcx], 0
0x1400032af  jnz     short loc_1400032BA
0x1400032b1  mov     ecx, [rcx+4]; dwErrCode
0x1400032b4  call    cs:__imp_SetLastError
0x1400032ba  add     rsp, 28h
0x1400032be  retn
```
