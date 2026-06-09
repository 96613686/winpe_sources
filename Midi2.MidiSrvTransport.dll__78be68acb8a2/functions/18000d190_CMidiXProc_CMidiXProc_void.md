# CMidiXProc::~CMidiXProc(void)

- ea: `0x18000d190`
- end: `0x18000d27d`
- name: `??1CMidiXProc@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CMidiXProc *__hidden this)`
- caller_count: `14`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a9a0`
- `0x18000aa10`
- `0x18000b5f0`
- `0x18000b7f0`
- `0x18000b8c0`
- `0x18000bbb0`
- `0x18000bcb0`
- `0x18000bfc0`
- `0x18000c250`
- `0x18000c3b0`
- `0x18000c6d0`
- `0x18000c8d0`
- `0x180012b04`
- `0x1800138f8`

## callees

- `0x180002494`
- `0x180009014`
- `0x18000d190`
- `0x18000d3e4`
- `0x180010b10`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e1`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d24c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d24c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMidiXProc::~CMidiXProc(CMidiXProc *this)
{
  char *v2; // rcx
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rcx
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rdi
  void *v10; // rdi
  __int64 v11; // rcx
  void *v12; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CMidiXProc::Shutdown(this);
  v2 = (char *)*((_QWORD *)this + 17);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (void *)*((_QWORD *)this + 15);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
  v9 = (void *)*((_QWORD *)this + 14);
  if ( v9 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(*((MEMORY_MAPPED_PIPE **)this + 14));
    operator delete(v9);
  }
  v10 = (void *)*((_QWORD *)this + 13);
  if ( v10 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(*((MEMORY_MAPPED_PIPE **)this + 13));
    operator delete(v10);
  }
  v11 = *((_QWORD *)this + 11);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = (void *)*((_QWORD *)this + 9);
  if ( v12 )
    AvRevertMmThreadCharacteristics(v12);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000d190  mov     [rsp+arg_0], rbx
0x18000d195  push    rdi
0x18000d196  sub     rsp, 20h
0x18000d19a  mov     rbx, rcx
0x18000d19d  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x18000d1a2  mov     rcx, [rbx+88h]; hObject
0x18000d1a9  lea     rax, [rcx-1]
0x18000d1ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d1b1  ja      short loc_18000D1B9
0x18000d1b3  call    cs:__imp_CloseHandle
0x18000d1b9  mov     rcx, [rbx+80h]; hObject
0x18000d1c0  test    rcx, rcx
0x18000d1c3  jz      short loc_18000D1D8
0x18000d1c5  call    cs:__imp_CloseHandle
0x18000d1cb  mov     rcx, [rsp+28h]; this
0x18000d1d0  test    eax, eax
0x18000d1d2  jz      loc_18000D272
0x18000d1d8  mov     rcx, [rbx+78h]; hObject
0x18000d1dc  test    rcx, rcx
0x18000d1df  jz      short loc_18000D1F0
0x18000d1e1  call    cs:__imp_CloseHandle
0x18000d1e7  mov     rcx, [rsp+28h]; this
0x18000d1ec  test    eax, eax
0x18000d1ee  jz      short loc_18000D267
0x18000d1f0  mov     rdi, [rbx+70h]
0x18000d1f4  test    rdi, rdi
0x18000d1f7  jz      short loc_18000D20E
0x18000d1f9  mov     rcx, rdi; this
0x18000d1fc  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18000d201  mov     edx, 68h ; 'h'
0x18000d206  mov     rcx, rdi; Block
0x18000d209  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d20e  mov     rdi, [rbx+68h]
0x18000d212  test    rdi, rdi
0x18000d215  jz      short loc_18000D22D
0x18000d217  mov     rcx, rdi; this
0x18000d21a  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18000d21f  mov     edx, 68h ; 'h'
0x18000d224  mov     rcx, rdi; Block
0x18000d227  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d22c  nop
0x18000d22d  mov     rcx, [rbx+58h]
0x18000d231  test    rcx, rcx
0x18000d234  jz      short loc_18000D243
0x18000d236  mov     rax, [rcx]
0x18000d239  mov     rax, [rax+10h]
0x18000d23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d242  nop
0x18000d243  mov     rcx, [rbx+48h]; AvrtHandle
0x18000d247  test    rcx, rcx
0x18000d24a  jz      short loc_18000D252
0x18000d24c  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000d252  lea     rcx, [rbx+8]
0x18000d256  mov     rbx, [rsp+28h+arg_0]
0x18000d25b  add     rsp, 20h
0x18000d25f  pop     rdi
0x18000d260  jmp     cs:__imp_DeleteCriticalSection
0x18000d267  mov     edx, 0A0Bh; void *
0x18000d26c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d272  mov     edx, 0A0Bh; void *
0x18000d277  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
