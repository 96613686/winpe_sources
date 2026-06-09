# CMidiXProc::~CMidiXProc(void)

- ea: `0x14004616c`
- end: `0x140046259`
- name: `??1CMidiXProc@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CMidiXProc *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140014198`
- `0x14001fe88`
- `0x140021470`

## callees

- `0x140005868`
- `0x14000c55c`
- `0x14001fbec`
- `0x14004616c`
- `0x140047b08`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14004623c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004618f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400461a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400461bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004618f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400461a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400461bd`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046228`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046228`

## pseudocode

```c
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
0x14004616c  mov     [rsp+arg_0], rbx
0x140046171  push    rdi
0x140046172  sub     rsp, 20h
0x140046176  mov     rbx, rcx
0x140046179  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x14004617e  mov     rcx, [rbx+88h]; hObject
0x140046185  lea     rax, [rcx-1]
0x140046189  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004618d  ja      short loc_140046195
0x14004618f  call    cs:__imp_CloseHandle
0x140046195  mov     rcx, [rbx+80h]; hObject
0x14004619c  test    rcx, rcx
0x14004619f  jz      short loc_1400461B4
0x1400461a1  call    cs:__imp_CloseHandle
0x1400461a7  mov     rcx, [rsp+28h]; this
0x1400461ac  test    eax, eax
0x1400461ae  jz      loc_14004624E
0x1400461b4  mov     rcx, [rbx+78h]; hObject
0x1400461b8  test    rcx, rcx
0x1400461bb  jz      short loc_1400461CC
0x1400461bd  call    cs:__imp_CloseHandle
0x1400461c3  mov     rcx, [rsp+28h]; this
0x1400461c8  test    eax, eax
0x1400461ca  jz      short loc_140046243
0x1400461cc  mov     rdi, [rbx+70h]
0x1400461d0  test    rdi, rdi
0x1400461d3  jz      short loc_1400461EA
0x1400461d5  mov     rcx, rdi; this
0x1400461d8  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x1400461dd  mov     edx, 68h ; 'h'
0x1400461e2  mov     rcx, rdi; Block
0x1400461e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400461ea  mov     rdi, [rbx+68h]
0x1400461ee  test    rdi, rdi
0x1400461f1  jz      short loc_140046209
0x1400461f3  mov     rcx, rdi; this
0x1400461f6  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x1400461fb  mov     edx, 68h ; 'h'
0x140046200  mov     rcx, rdi; Block
0x140046203  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140046208  nop
0x140046209  mov     rcx, [rbx+58h]
0x14004620d  test    rcx, rcx
0x140046210  jz      short loc_14004621F
0x140046212  mov     rax, [rcx]
0x140046215  mov     rax, [rax+10h]
0x140046219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004621e  nop
0x14004621f  mov     rcx, [rbx+48h]; AvrtHandle
0x140046223  test    rcx, rcx
0x140046226  jz      short loc_14004622E
0x140046228  call    cs:__imp_AvRevertMmThreadCharacteristics
0x14004622e  lea     rcx, [rbx+8]
0x140046232  mov     rbx, [rsp+28h+arg_0]
0x140046237  add     rsp, 20h
0x14004623b  pop     rdi
0x14004623c  jmp     cs:__imp_DeleteCriticalSection
0x140046243  mov     edx, 0A0Bh; void *
0x140046248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14004624e  mov     edx, 0A0Bh; void *
0x140046253  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
