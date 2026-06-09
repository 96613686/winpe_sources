# BASIC_USER_CONTEXT::~BASIC_USER_CONTEXT(void)

- ea: `0x180001a28`
- end: `0x180001aa8`
- name: `??1BASIC_USER_CONTEXT@@EEAA@XZ`
- size: `128`
- prototype: `void __fastcall(BASIC_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b00`

## callees

- `0x180001a28`
- `0x180006010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001aa1`

## pseudocode

```c
void __fastcall BASIC_USER_CONTEXT::~BASIC_USER_CONTEXT(BASIC_USER_CONTEXT *this)
{
  __int64 v2; // rcx
  int v3; // eax
  bool v4; // zf
  __int64 v5; // rdx
  _BYTE *v6; // rax

  *(_QWORD *)this = &BASIC_USER_CONTEXT::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = *((_DWORD *)this + 32);
  if ( v3 )
  {
    v4 = 2 * v3 == 0;
    v5 = (unsigned int)(2 * v3);
    v6 = (_BYTE *)*((_QWORD *)this + 14);
    if ( !v4 )
    {
      do
      {
        *v6++ = 0;
        --v5;
      }
      while ( v5 );
    }
  }
  STRU::~STRU((BASIC_USER_CONTEXT *)((char *)this + 136));
  STRU::~STRU((BASIC_USER_CONTEXT *)((char *)this + 80));
  STRU::~STRU((BASIC_USER_CONTEXT *)((char *)this + 24));
}

```

## disassembly

```asm
0x180001a28  mov     [rsp+arg_0], rbx
0x180001a2d  push    rdi
0x180001a2e  sub     rsp, 20h
0x180001a32  lea     rax, ??_7BASIC_USER_CONTEXT@@6B@; const BASIC_USER_CONTEXT::`vftable'
0x180001a39  mov     rbx, rcx
0x180001a3c  mov     [rcx], rax
0x180001a3f  mov     rcx, [rcx+10h]
0x180001a43  test    rcx, rcx
0x180001a46  jz      short loc_180001A5C
0x180001a48  mov     rax, [rcx]
0x180001a4b  mov     rax, [rax+10h]
0x180001a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a54  mov     qword ptr [rbx+10h], 0
0x180001a5c  mov     eax, [rbx+80h]
0x180001a62  test    eax, eax
0x180001a64  jz      short loc_180001A7C
0x180001a66  add     eax, eax
0x180001a68  mov     edx, eax
0x180001a6a  mov     rax, [rbx+70h]
0x180001a6e  jz      short loc_180001A7C
0x180001a70  mov     byte ptr [rax], 0
0x180001a73  inc     rax
0x180001a76  sub     rdx, 1
0x180001a7a  jnz     short loc_180001A70
0x180001a7c  lea     rcx, [rbx+88h]
0x180001a83  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001a89  lea     rcx, [rbx+50h]
0x180001a8d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001a93  lea     rcx, [rbx+18h]
0x180001a97  mov     rbx, [rsp+28h+arg_0]
0x180001a9c  add     rsp, 20h
0x180001aa0  pop     rdi
0x180001aa1  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
