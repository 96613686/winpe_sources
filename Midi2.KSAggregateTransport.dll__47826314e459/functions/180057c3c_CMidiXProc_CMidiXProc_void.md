# CMidiXProc::~CMidiXProc(void)

- ea: `0x180057c3c`
- end: `0x180057d29`
- name: `??1CMidiXProc@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CMidiXProc *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180048530`
- `0x1800485ac`
- `0x180049708`
- `0x180049b78`
- `0x18004a750`
- `0x18004ac20`

## callees

- `0x180005044`
- `0x18000c684`
- `0x180043a74`
- `0x180057c3c`
- `0x1800592dc`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180057d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057c8d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057cf8`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057cf8`

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
0x180057c3c  mov     [rsp+arg_0], rbx
0x180057c41  push    rdi
0x180057c42  sub     rsp, 20h
0x180057c46  mov     rbx, rcx
0x180057c49  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180057c4e  mov     rcx, [rbx+88h]; hObject
0x180057c55  lea     rax, [rcx-1]
0x180057c59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180057c5d  ja      short loc_180057C65
0x180057c5f  call    cs:__imp_CloseHandle
0x180057c65  mov     rcx, [rbx+80h]; hObject
0x180057c6c  test    rcx, rcx
0x180057c6f  jz      short loc_180057C84
0x180057c71  call    cs:__imp_CloseHandle
0x180057c77  mov     rcx, [rsp+28h]; this
0x180057c7c  test    eax, eax
0x180057c7e  jz      loc_180057D1E
0x180057c84  mov     rcx, [rbx+78h]; hObject
0x180057c88  test    rcx, rcx
0x180057c8b  jz      short loc_180057C9C
0x180057c8d  call    cs:__imp_CloseHandle
0x180057c93  mov     rcx, [rsp+28h]; this
0x180057c98  test    eax, eax
0x180057c9a  jz      short loc_180057D13
0x180057c9c  mov     rdi, [rbx+70h]
0x180057ca0  test    rdi, rdi
0x180057ca3  jz      short loc_180057CBA
0x180057ca5  mov     rcx, rdi; this
0x180057ca8  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180057cad  mov     edx, 68h ; 'h'
0x180057cb2  mov     rcx, rdi; Block
0x180057cb5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180057cba  mov     rdi, [rbx+68h]
0x180057cbe  test    rdi, rdi
0x180057cc1  jz      short loc_180057CD9
0x180057cc3  mov     rcx, rdi; this
0x180057cc6  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180057ccb  mov     edx, 68h ; 'h'
0x180057cd0  mov     rcx, rdi; Block
0x180057cd3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180057cd8  nop
0x180057cd9  mov     rcx, [rbx+58h]
0x180057cdd  test    rcx, rcx
0x180057ce0  jz      short loc_180057CEF
0x180057ce2  mov     rax, [rcx]
0x180057ce5  mov     rax, [rax+10h]
0x180057ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057cee  nop
0x180057cef  mov     rcx, [rbx+48h]; AvrtHandle
0x180057cf3  test    rcx, rcx
0x180057cf6  jz      short loc_180057CFE
0x180057cf8  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180057cfe  lea     rcx, [rbx+8]
0x180057d02  mov     rbx, [rsp+28h+arg_0]
0x180057d07  add     rsp, 20h
0x180057d0b  pop     rdi
0x180057d0c  jmp     cs:__imp_DeleteCriticalSection
0x180057d13  mov     edx, 0A0Bh; void *
0x180057d18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180057d1e  mov     edx, 0A0Bh; void *
0x180057d23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
