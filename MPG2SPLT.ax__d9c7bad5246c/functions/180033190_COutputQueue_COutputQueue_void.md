# COutputQueue::~COutputQueue(void)

- ea: `0x180033190`
- end: `0x18003325d`
- name: `??1COutputQueue@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(COutputQueue *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000bda0`
- `0x18000cf40`
- `0x1800221c4`
- `0x180023310`

## callees

- `0x180001048`
- `0x18000676c`
- `0x180033190`
- `0x180033434`
- `0x180033630`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800331d0`
- `KERNEL32!WaitForSingleObject` at `0x1800331d0`
- `KERNEL32!CloseHandle` at `0x1800331da`
- `KERNEL32!CloseHandle` at `0x18003322b`
- `KERNEL32!CloseHandle` at `0x180033243`
- `KERNEL32!CloseHandle` at `0x1800331da`
- `KERNEL32!CloseHandle` at `0x18003322b`
- `KERNEL32!CloseHandle` at `0x180033243`
- `KERNEL32!DeleteCriticalSection` at `0x180033256`
- `KERNEL32!LeaveCriticalSection` at `0x1800331c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800331c3`
- `KERNEL32!EnterCriticalSection` at `0x1800331a4`
- `KERNEL32!EnterCriticalSection` at `0x1800331a4`

## pseudocode

```c
void __fastcall COutputQueue::~COutputQueue(COutputQueue *this)
{
  unsigned __int64 v2; // rdx
  void *v3; // rdi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  if ( *((_QWORD *)this + 11) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_DWORD *)this + 31) = 1;
    *((_DWORD *)this + 33) = 1;
    COutputQueue::NotifyThread(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 11));
    v3 = (void *)*((_QWORD *)this + 8);
    if ( v3 )
    {
      CBaseList::~CBaseList(*((CBaseList **)this + 8));
      operator delete(v3, 0x28u);
    }
  }
  else
  {
    COutputQueue::FreeSamples(this);
  }
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 6) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    CloseHandle(v5);
  operator delete(*((void **)this + 12), v2);
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
    CloseHandle(v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180033190  mov     [rsp+arg_0], rbx
0x180033195  push    rdi
0x180033196  sub     rsp, 20h
0x18003319a  cmp     qword ptr [rcx+58h], 0
0x18003319f  mov     rbx, rcx
0x1800331a2  jz      short loc_180033200
0x1800331a4  call    cs:__imp_EnterCriticalSection
0x1800331aa  mov     eax, 1
0x1800331af  mov     rcx, rbx; this
0x1800331b2  mov     [rbx+7Ch], eax
0x1800331b5  mov     [rbx+84h], eax
0x1800331bb  call    ?NotifyThread@COutputQueue@@IEAAXXZ; COutputQueue::NotifyThread(void)
0x1800331c0  mov     rcx, rbx; lpCriticalSection
0x1800331c3  call    cs:__imp_LeaveCriticalSection
0x1800331c9  mov     rcx, [rbx+58h]; hHandle
0x1800331cd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800331d0  call    cs:__imp_WaitForSingleObject
0x1800331d6  mov     rcx, [rbx+58h]; hObject
0x1800331da  call    cs:__imp_CloseHandle
0x1800331e0  mov     rdi, [rbx+40h]
0x1800331e4  test    rdi, rdi
0x1800331e7  jz      short loc_180033205
0x1800331e9  mov     rcx, rdi; this
0x1800331ec  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x1800331f1  mov     edx, 28h ; '('; unsigned __int64
0x1800331f6  mov     rcx, rdi; void *
0x1800331f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800331fe  jmp     short loc_180033205
0x180033200  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x180033205  mov     rcx, [rbx+30h]
0x180033209  test    rcx, rcx
0x18003320c  jz      short loc_180033222
0x18003320e  mov     rax, [rcx]
0x180033211  mov     rax, [rax+10h]
0x180033215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003321a  mov     qword ptr [rbx+30h], 0
0x180033222  mov     rcx, [rbx+48h]; hObject
0x180033226  test    rcx, rcx
0x180033229  jz      short loc_180033231
0x18003322b  call    cs:__imp_CloseHandle
0x180033231  mov     rcx, [rbx+60h]; void *
0x180033235  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003323a  mov     rcx, [rbx+50h]; hObject
0x18003323e  test    rcx, rcx
0x180033241  jz      short loc_180033249
0x180033243  call    cs:__imp_CloseHandle
0x180033249  mov     rcx, rbx
0x18003324c  mov     rbx, [rsp+28h+arg_0]
0x180033251  add     rsp, 20h
0x180033255  pop     rdi
0x180033256  jmp     cs:__imp_DeleteCriticalSection
```
