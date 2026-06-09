# SSPI_USER_CONTEXT::~SSPI_USER_CONTEXT(void)

- ea: `0x180001d9c`
- end: `0x180001e11`
- name: `??1SSPI_USER_CONTEXT@@EEAA@XZ`
- size: `117`
- prototype: `void __fastcall(SSPI_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ef0`

## callees

- `0x180001d9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dcf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001df1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001df1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001e0a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001de4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001dfb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001de4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001dfb`

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
0x180001d9c  push    rbx
0x180001d9e  sub     rsp, 20h
0x180001da2  lea     rax, ??_7SSPI_USER_CONTEXT@@6B@; const SSPI_USER_CONTEXT::`vftable'
0x180001da9  mov     rbx, rcx
0x180001dac  mov     [rcx], rax
0x180001daf  mov     rcx, [rcx+10h]; hObject
0x180001db3  test    rcx, rcx
0x180001db6  jz      short loc_180001DC6
0x180001db8  call    cs:__imp_CloseHandle
0x180001dbe  mov     qword ptr [rbx+10h], 0
0x180001dc6  mov     rcx, [rbx+18h]; hObject
0x180001dca  test    rcx, rcx
0x180001dcd  jz      short loc_180001DDD
0x180001dcf  call    cs:__imp_CloseHandle
0x180001dd5  mov     qword ptr [rbx+18h], 0
0x180001ddd  lea     rcx, [rbx+0E0h]
0x180001de4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001dea  lea     rcx, [rbx+90h]
0x180001df1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001df7  lea     rcx, [rbx+58h]
0x180001dfb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001e01  lea     rcx, [rbx+20h]
0x180001e05  add     rsp, 20h
0x180001e09  pop     rbx
0x180001e0a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
