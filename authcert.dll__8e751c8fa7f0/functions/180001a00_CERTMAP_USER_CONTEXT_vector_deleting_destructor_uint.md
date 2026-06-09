# CERTMAP_USER_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x180001a00`
- end: `0x180001a6d`
- name: `??_ECERTMAP_USER_CONTEXT@@EEAAPEAXI@Z`
- size: `109`
- prototype: `void *__fastcall(CERTMAP_USER_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001a00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a4b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001a4b`

## pseudocode

```c
CERTMAP_USER_CONTEXT *__fastcall CERTMAP_USER_CONTEXT::`vector deleting destructor'(
        CERTMAP_USER_CONTEXT *this,
        char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CERTMAP_USER_CONTEXT::`vftable';
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 10) = 0;
  }
  STRU::~STRU((CERTMAP_USER_CONTEXT *)((char *)this + 16));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001a00  mov     [rsp+arg_0], rbx
0x180001a05  push    rdi
0x180001a06  sub     rsp, 20h
0x180001a0a  lea     rax, ??_7CERTMAP_USER_CONTEXT@@6B@; const CERTMAP_USER_CONTEXT::`vftable'
0x180001a11  mov     rbx, rcx
0x180001a14  mov     [rcx], rax
0x180001a17  mov     edi, edx
0x180001a19  mov     rcx, [rcx+48h]; hObject
0x180001a1d  test    rcx, rcx
0x180001a20  jz      short loc_180001A30
0x180001a22  call    cs:__imp_CloseHandle
0x180001a28  mov     qword ptr [rbx+48h], 0
0x180001a30  mov     rcx, [rbx+50h]; hObject
0x180001a34  test    rcx, rcx
0x180001a37  jz      short loc_180001A47
0x180001a39  call    cs:__imp_CloseHandle
0x180001a3f  mov     qword ptr [rbx+50h], 0
0x180001a47  lea     rcx, [rbx+10h]
0x180001a4b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001a51  test    dil, 1
0x180001a55  jz      short loc_180001A5F
0x180001a57  mov     rcx, rbx; Block
0x180001a5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001a5f  mov     rax, rbx
0x180001a62  mov     rbx, [rsp+28h+arg_0]
0x180001a67  add     rsp, 20h
0x180001a6b  pop     rdi
0x180001a6c  retn
```
