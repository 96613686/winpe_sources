# SSPI_USER_CONTEXT::~SSPI_USER_CONTEXT(void)

- ea: `0x180001ad0`
- end: `0x180001b45`
- name: `??1SSPI_USER_CONTEXT@@EEAA@XZ`
- size: `117`
- prototype: `void __fastcall(SSPI_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cc0`

## callees

- `0x180001ad0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b03`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001b18`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001b2f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001b18`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001b2f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b25`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b25`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b3e`

## pseudocode

```c
void __fastcall SSPI_USER_CONTEXT::~SSPI_USER_CONTEXT(SSPI_USER_CONTEXT *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &SSPI_USER_CONTEXT::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 3) = 0;
  }
  STRA::~STRA((SSPI_USER_CONTEXT *)((char *)this + 224));
  STRU::~STRU((SSPI_USER_CONTEXT *)((char *)this + 144));
  STRA::~STRA((SSPI_USER_CONTEXT *)((char *)this + 88));
  STRU::~STRU((SSPI_USER_CONTEXT *)((char *)this + 32));
}

```

## disassembly

```asm
0x180001ad0  push    rbx
0x180001ad2  sub     rsp, 20h
0x180001ad6  lea     rax, ??_7SSPI_USER_CONTEXT@@6B@; const SSPI_USER_CONTEXT::`vftable'
0x180001add  mov     rbx, rcx
0x180001ae0  mov     [rcx], rax
0x180001ae3  mov     rcx, [rcx+10h]; hObject
0x180001ae7  test    rcx, rcx
0x180001aea  jz      short loc_180001AFA
0x180001aec  call    cs:__imp_CloseHandle
0x180001af2  mov     qword ptr [rbx+10h], 0
0x180001afa  mov     rcx, [rbx+18h]; hObject
0x180001afe  test    rcx, rcx
0x180001b01  jz      short loc_180001B11
0x180001b03  call    cs:__imp_CloseHandle
0x180001b09  mov     qword ptr [rbx+18h], 0
0x180001b11  lea     rcx, [rbx+0E0h]
0x180001b18  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001b1e  lea     rcx, [rbx+90h]
0x180001b25  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001b2b  lea     rcx, [rbx+58h]
0x180001b2f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001b35  lea     rcx, [rbx+20h]
0x180001b39  add     rsp, 20h
0x180001b3d  pop     rbx
0x180001b3e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
