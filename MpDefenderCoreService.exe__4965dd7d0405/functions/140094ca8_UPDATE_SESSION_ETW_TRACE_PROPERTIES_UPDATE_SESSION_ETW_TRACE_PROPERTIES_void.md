# UPDATE_SESSION_ETW_TRACE_PROPERTIES::UPDATE_SESSION_ETW_TRACE_PROPERTIES(void)

- ea: `0x140094ca8`
- end: `0x140094d48`
- name: `??0UPDATE_SESSION_ETW_TRACE_PROPERTIES@@QEAA@XZ`
- size: `160`
- prototype: `UPDATE_SESSION_ETW_TRACE_PROPERTIES *__fastcall(UPDATE_SESSION_ETW_TRACE_PROPERTIES *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140094d48`
- `0x1400960c0`

## callees

- `0x140059d40`
- `0x140166990`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140094cd6`
- `RPCRT4!UuidCreate` at `0x140094cd6`

## string_xrefs

- `0x140094cf6`: `UpdateSessionLoggerTrace`
- `0x140094d2e`: `C:\ProgramData\Microsoft\Windows Defender\Support\UpdateSession.etl`

## pseudocode

```c
UPDATE_SESSION_ETW_TRACE_PROPERTIES *__fastcall UPDATE_SESSION_ETW_TRACE_PROPERTIES::UPDATE_SESSION_ETW_TRACE_PROPERTIES(
        UPDATE_SESSION_ETW_TRACE_PROPERTIES *this)
{
  memset(this, 0, 0x488u);
  *(_DWORD *)this = 1160;
  *((_DWORD *)this + 11) = 0x20000;
  *((_DWORD *)this + 10) = 1;
  UuidCreate((UUID *)((char *)this + 24));
  *((_DWORD *)this + 16) = 258;
  *((_DWORD *)this + 15) = 16;
  *((_DWORD *)this + 14) = 16;
  *((_DWORD *)this + 12) = 64;
  *((_DWORD *)this + 13) = 4;
  *((_DWORD *)this + 29) = 120;
  *((_DWORD *)this + 28) = 640;
  wcsncpy_s((wchar_t *)this + 60, 0x104u, L"UpdateSessionLoggerTrace", 0xFFFFFFFFFFFFFFFFuLL);
  wcsncpy_s(
    (wchar_t *)this + 320,
    0x104u,
    L"C:\\ProgramData\\Microsoft\\Windows Defender\\Support\\UpdateSession.etl",
    0xFFFFFFFFFFFFFFFFuLL);
  return this;
}

```

## disassembly

```asm
0x140094ca8  push    rbx
0x140094caa  sub     rsp, 20h
0x140094cae  xor     edx, edx; Val
0x140094cb0  mov     r8d, 488h; Size
0x140094cb6  mov     rbx, rcx
0x140094cb9  call    memset
0x140094cbe  lea     rcx, [rbx+18h]; Uuid
0x140094cc2  mov     dword ptr [rbx], 488h
0x140094cc8  mov     dword ptr [rbx+2Ch], 20000h
0x140094ccf  mov     dword ptr [rbx+28h], 1
0x140094cd6  call    cs:__imp_UuidCreate
0x140094cdc  mov     eax, 10h
0x140094ce1  mov     dword ptr [rbx+40h], 102h
0x140094ce8  lea     rcx, [rbx+78h]; Destination
0x140094cec  mov     [rbx+3Ch], eax
0x140094cef  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140094cf3  mov     [rbx+38h], eax
0x140094cf6  lea     r8, aUpdatesessionl_0; "UpdateSessionLoggerTrace"
0x140094cfd  mov     dword ptr [rbx+30h], 40h ; '@'
0x140094d04  mov     edx, 104h; SizeInWords
0x140094d09  mov     dword ptr [rbx+34h], 4
0x140094d10  mov     dword ptr [rbx+74h], 78h ; 'x'
0x140094d17  mov     dword ptr [rbx+70h], 280h
0x140094d1e  call    wcsncpy_s
0x140094d23  lea     rcx, [rbx+280h]; Destination
0x140094d2a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140094d2e  lea     r8, aCProgramdataMi; "C:\\ProgramData\\Microsoft\\Windows Def"...
0x140094d35  mov     edx, 104h; SizeInWords
0x140094d3a  call    wcsncpy_s
0x140094d3f  mov     rax, rbx
0x140094d42  add     rsp, 20h
0x140094d46  pop     rbx
0x140094d47  retn
```
