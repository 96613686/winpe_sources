# ABO_WRAPPER::~ABO_WRAPPER(void)

- ea: `0x180003d18`
- end: `0x180003e40`
- name: `??1ABO_WRAPPER@@UEAA@XZ`
- size: `296`
- prototype: `void __fastcall(ABO_WRAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003e90`

## callees

- `0x1800029d0`
- `0x180003d18`
- `0x180003f14`
- `0x18000adb0`
- `0x18002a070`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180003daf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180003daf`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003e10`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003e25`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003e10`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003e25`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180003e39`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003d97`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003d97`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003d7c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003d7c`

## pseudocode

```c
void __fastcall ABO_WRAPPER::~ABO_WRAPPER(ABO_WRAPPER *this)
{
  volatile signed __int32 *v1; // rbx
  void *v3; // rbx
  HANDLE_ENTRY *v4; // rcx
  __int64 v5; // rcx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 30);
  *(_QWORD *)this = &ABO_WRAPPER::`vftable'{for `IAboWrapper'};
  *((_QWORD *)this + 1) = &ABO_WRAPPER::`vftable'{for `INativeChangeListener'};
  if ( v1 )
  {
    if ( _InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF) == 1 )
    {
      NOTIFY_ITEM::~NOTIFY_ITEM((NOTIFY_ITEM *)v1);
      operator delete((void *)v1);
    }
    *((_QWORD *)this + 30) = 0;
  }
  if ( *((_QWORD *)this + 28) )
  {
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
    LAZY_WRITER::CommitChanges(*((LAZY_WRITER **)this + 28), 1);
    CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    v3 = (void *)*((_QWORD *)this + 28);
    if ( v3 )
    {
      DeleteTimerQueueEx(0, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      operator delete(v3);
    }
    *((_QWORD *)this + 28) = 0;
  }
  v4 = (HANDLE_ENTRY *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    HANDLE_ENTRY::DereferenceHandleEntry(v4);
    *((_QWORD *)this + 3) = 0;
  }
  v5 = *((_QWORD *)this + 15);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 15) = 0;
  }
  *((_QWORD *)this + 18) = &HANDLE_TABLE::`vftable';
  CLKRHashTable::~CLKRHashTable((ABO_WRAPPER *)((char *)this + 152));
  *((_QWORD *)this + 5) = &HANDLE_TABLE::`vftable';
  CLKRHashTable::~CLKRHashTable((ABO_WRAPPER *)((char *)this + 48));
  CReaderWriterLock3::~CReaderWriterLock3((ABO_WRAPPER *)((char *)this + 32));
}

```

## disassembly

```asm
0x180003d18  mov     [rsp+arg_0], rbx
0x180003d1d  push    rdi
0x180003d1e  sub     rsp, 20h
0x180003d22  mov     rbx, [rcx+0F0h]
0x180003d29  lea     rax, ??_7ABO_WRAPPER@@6BIAboWrapper@@@; const ABO_WRAPPER::`vftable'{for `IAboWrapper'}
0x180003d30  mov     [rcx], rax
0x180003d33  lea     rax, ??_7ABO_WRAPPER@@6BINativeChangeListener@@@; const ABO_WRAPPER::`vftable'{for `INativeChangeListener'}
0x180003d3a  mov     [rcx+8], rax
0x180003d3e  mov     rdi, rcx
0x180003d41  test    rbx, rbx
0x180003d44  jz      short loc_180003D6E
0x180003d46  or      eax, 0FFFFFFFFh
0x180003d49  lock xadd [rbx+10h], eax
0x180003d4e  cmp     eax, 1
0x180003d51  jnz     short loc_180003D63
0x180003d53  mov     rcx, rbx; this
0x180003d56  call    ??1NOTIFY_ITEM@@QEAA@XZ; NOTIFY_ITEM::~NOTIFY_ITEM(void)
0x180003d5b  mov     rcx, rbx; Block
0x180003d5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003d63  mov     qword ptr [rdi+0F0h], 0
0x180003d6e  cmp     qword ptr [rdi+0E0h], 0
0x180003d76  jz      short loc_180003DC8
0x180003d78  lea     rcx, [rdi+20h]
0x180003d7c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180003d82  mov     rcx, [rdi+0E0h]; this
0x180003d89  mov     edx, 1; int
0x180003d8e  call    ?CommitChanges@LAZY_WRITER@@QEAAJH@Z; LAZY_WRITER::CommitChanges(int)
0x180003d93  lea     rcx, [rdi+20h]
0x180003d97  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003d9d  mov     rbx, [rdi+0E0h]
0x180003da4  test    rbx, rbx
0x180003da7  jz      short loc_180003DBD
0x180003da9  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003dad  xor     ecx, ecx; TimerQueue
0x180003daf  call    cs:__imp_DeleteTimerQueueEx
0x180003db5  mov     rcx, rbx; Block
0x180003db8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003dbd  mov     qword ptr [rdi+0E0h], 0
0x180003dc8  mov     rcx, [rdi+18h]; this
0x180003dcc  test    rcx, rcx
0x180003dcf  jz      short loc_180003DDE
0x180003dd1  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180003dd6  mov     qword ptr [rdi+18h], 0
0x180003dde  mov     rcx, [rdi+78h]
0x180003de2  test    rcx, rcx
0x180003de5  jz      short loc_180003DFB
0x180003de7  mov     rax, [rcx]
0x180003dea  mov     rax, [rax+10h]
0x180003dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df3  mov     qword ptr [rdi+78h], 0
0x180003dfb  lea     rax, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x180003e02  lea     rcx, [rdi+98h]
0x180003e09  mov     [rdi+90h], rax
0x180003e10  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180003e16  lea     rax, ??_7HANDLE_TABLE@@6B@; const HANDLE_TABLE::`vftable'
0x180003e1d  lea     rcx, [rdi+30h]
0x180003e21  mov     [rdi+28h], rax
0x180003e25  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180003e2b  lea     rcx, [rdi+20h]
0x180003e2f  mov     rbx, [rsp+28h+arg_0]
0x180003e34  add     rsp, 20h
0x180003e38  pop     rdi
0x180003e39  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
