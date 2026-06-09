# TOKEN_ENTRY::~TOKEN_ENTRY(void)

- ea: `0x180004e30`
- end: `0x180004eb2`
- name: `??1TOKEN_ENTRY@@EEAA@XZ`
- size: `130`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ec0`

## callees

- `0x180004e30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180004e94`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004e94`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004eab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e7f`

## pseudocode

```c
void __fastcall TOKEN_ENTRY::~TOKEN_ENTRY(TOKEN_ENTRY *this)
{
  void *v2; // rcx
  _BYTE *v3; // rdi
  void *v4; // rcx

  *((_DWORD *)this + 2) = 1852534644;
  *(_QWORD *)this = &TOKEN_ENTRY::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  v3 = (char *)this + 260;
  if ( v2 )
  {
    if ( (*v3 & 1) != 0 )
      CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    if ( (*v3 & 2) != 0 )
      CloseHandle(v4);
    *((_QWORD *)this + 3) = 0;
  }
  STRU::~STRU((TOKEN_ENTRY *)((char *)this + 184));
  STRU::~STRU((TOKEN_ENTRY *)((char *)this + 128));
}

```

## disassembly

```asm
0x180004e30  mov     [rsp+arg_0], rbx
0x180004e35  push    rdi
0x180004e36  sub     rsp, 20h
0x180004e3a  mov     rbx, rcx
0x180004e3d  mov     dword ptr [rcx+8], 6E6B6F74h
0x180004e44  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180004e4b  mov     [rcx], rax
0x180004e4e  mov     rcx, [rcx+10h]; hObject
0x180004e52  lea     rdi, [rbx+104h]
0x180004e59  test    rcx, rcx
0x180004e5c  jz      short loc_180004E71
0x180004e5e  test    byte ptr [rdi], 1
0x180004e61  jz      short loc_180004E69
0x180004e63  call    cs:__imp_CloseHandle
0x180004e69  mov     qword ptr [rbx+10h], 0
0x180004e71  mov     rcx, [rbx+18h]; hObject
0x180004e75  test    rcx, rcx
0x180004e78  jz      short loc_180004E8D
0x180004e7a  test    byte ptr [rdi], 2
0x180004e7d  jz      short loc_180004E85
0x180004e7f  call    cs:__imp_CloseHandle
0x180004e85  mov     qword ptr [rbx+18h], 0
0x180004e8d  lea     rcx, [rbx+0B8h]
0x180004e94  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004e9a  lea     rcx, [rbx+80h]
0x180004ea1  mov     rbx, [rsp+28h+arg_0]
0x180004ea6  add     rsp, 20h
0x180004eaa  pop     rdi
0x180004eab  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
