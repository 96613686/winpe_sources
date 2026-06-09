# TOKEN_ENTRY::~TOKEN_ENTRY(void)

- ea: `0x180003ba4`
- end: `0x180003c26`
- name: `??1TOKEN_ENTRY@@EEAA@XZ`
- size: `130`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c30`

## callees

- `0x180003ba4`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c08`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c08`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003c1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf3`

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
0x180003ba4  mov     [rsp+arg_0], rbx
0x180003ba9  push    rdi
0x180003baa  sub     rsp, 20h
0x180003bae  mov     rbx, rcx
0x180003bb1  mov     dword ptr [rcx+8], 6E6B6F74h
0x180003bb8  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180003bbf  mov     [rcx], rax
0x180003bc2  mov     rcx, [rcx+10h]; hObject
0x180003bc6  lea     rdi, [rbx+104h]
0x180003bcd  test    rcx, rcx
0x180003bd0  jz      short loc_180003BE5
0x180003bd2  test    byte ptr [rdi], 1
0x180003bd5  jz      short loc_180003BDD
0x180003bd7  call    cs:__imp_CloseHandle
0x180003bdd  mov     qword ptr [rbx+10h], 0
0x180003be5  mov     rcx, [rbx+18h]; hObject
0x180003be9  test    rcx, rcx
0x180003bec  jz      short loc_180003C01
0x180003bee  test    byte ptr [rdi], 2
0x180003bf1  jz      short loc_180003BF9
0x180003bf3  call    cs:__imp_CloseHandle
0x180003bf9  mov     qword ptr [rbx+18h], 0
0x180003c01  lea     rcx, [rbx+0B8h]
0x180003c08  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003c0e  lea     rcx, [rbx+80h]
0x180003c15  mov     rbx, [rsp+28h+arg_0]
0x180003c1a  add     rsp, 20h
0x180003c1e  pop     rdi
0x180003c1f  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
