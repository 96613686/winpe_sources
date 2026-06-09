# wil::last_error_context::~last_error_context(void)

- ea: `0x1400050ac`
- end: `0x1400050c3`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004250`
- `0x1400042cc`
- `0x140005818`
- `0x140009814`
- `0x1400098b8`
- `0x14000990c`

## callees

- `0x1400050ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050b8`

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
0x1400050ac  sub     rsp, 28h
0x1400050b0  cmp     byte ptr [rcx], 0
0x1400050b3  jnz     short loc_1400050BE
0x1400050b5  mov     ecx, [rcx+4]; dwErrCode
0x1400050b8  call    cs:__imp_SetLastError
0x1400050be  add     rsp, 28h
0x1400050c2  retn
```
