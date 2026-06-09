# CMidiXProc::~CMidiXProc(void)

- ea: `0x18003c59c`
- end: `0x18003c689`
- name: `??1CMidiXProc@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CMidiXProc *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800279cc`
- `0x180027a48`
- `0x180028bc8`
- `0x180029038`
- `0x180029db0`
- `0x18002a280`

## callees

- `0x180004434`
- `0x18000bb04`
- `0x180010f30`
- `0x18003c59c`
- `0x18003dd1c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c66c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c5ed`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c658`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c658`

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
0x18003c59c  mov     [rsp+arg_0], rbx
0x18003c5a1  push    rdi
0x18003c5a2  sub     rsp, 20h
0x18003c5a6  mov     rbx, rcx
0x18003c5a9  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x18003c5ae  mov     rcx, [rbx+88h]; hObject
0x18003c5b5  lea     rax, [rcx-1]
0x18003c5b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003c5bd  ja      short loc_18003C5C5
0x18003c5bf  call    cs:__imp_CloseHandle
0x18003c5c5  mov     rcx, [rbx+80h]; hObject
0x18003c5cc  test    rcx, rcx
0x18003c5cf  jz      short loc_18003C5E4
0x18003c5d1  call    cs:__imp_CloseHandle
0x18003c5d7  mov     rcx, [rsp+28h]; this
0x18003c5dc  test    eax, eax
0x18003c5de  jz      loc_18003C67E
0x18003c5e4  mov     rcx, [rbx+78h]; hObject
0x18003c5e8  test    rcx, rcx
0x18003c5eb  jz      short loc_18003C5FC
0x18003c5ed  call    cs:__imp_CloseHandle
0x18003c5f3  mov     rcx, [rsp+28h]; this
0x18003c5f8  test    eax, eax
0x18003c5fa  jz      short loc_18003C673
0x18003c5fc  mov     rdi, [rbx+70h]
0x18003c600  test    rdi, rdi
0x18003c603  jz      short loc_18003C61A
0x18003c605  mov     rcx, rdi; this
0x18003c608  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18003c60d  mov     edx, 68h ; 'h'
0x18003c612  mov     rcx, rdi; Block
0x18003c615  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c61a  mov     rdi, [rbx+68h]
0x18003c61e  test    rdi, rdi
0x18003c621  jz      short loc_18003C639
0x18003c623  mov     rcx, rdi; this
0x18003c626  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18003c62b  mov     edx, 68h ; 'h'
0x18003c630  mov     rcx, rdi; Block
0x18003c633  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003c638  nop
0x18003c639  mov     rcx, [rbx+58h]
0x18003c63d  test    rcx, rcx
0x18003c640  jz      short loc_18003C64F
0x18003c642  mov     rax, [rcx]
0x18003c645  mov     rax, [rax+10h]
0x18003c649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c64e  nop
0x18003c64f  mov     rcx, [rbx+48h]; AvrtHandle
0x18003c653  test    rcx, rcx
0x18003c656  jz      short loc_18003C65E
0x18003c658  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18003c65e  lea     rcx, [rbx+8]
0x18003c662  mov     rbx, [rsp+28h+arg_0]
0x18003c667  add     rsp, 20h
0x18003c66b  pop     rdi
0x18003c66c  jmp     cs:__imp_DeleteCriticalSection
0x18003c673  mov     edx, 0A0Bh; void *
0x18003c678  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003c67e  mov     edx, 0A0Bh; void *
0x18003c683  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
