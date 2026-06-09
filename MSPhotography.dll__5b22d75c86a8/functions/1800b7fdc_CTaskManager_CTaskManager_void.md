# CTaskManager::~CTaskManager(void)

- ea: `0x1800b7fdc`
- end: `0x1800b8087`
- name: `??1CTaskManager@@IEAA@XZ`
- size: `171`
- prototype: `void __fastcall(CTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800b80b8`

## callees

- `0x1800028cc`
- `0x1800b6960`
- `0x1800b6b54`
- `0x1800b7f50`
- `0x1800b7fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b806e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b806e`

## pseudocode

```c
void __fastcall CTaskManager::~CTaskManager(CTaskManager *this)
{
  __int64 i; // rax
  __int64 v3; // rsi
  vt::CSystem::CThreadPool::CThreadPoolInternal *v4; // rcx
  void *v5; // rbx
  CTaskManager::CTask *v6; // [rsp+30h] [rbp+8h]

  for ( i = *((_QWORD *)this + 7); i; i = *((_QWORD *)this + 7) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)this + 7) + 184LL);
    v6 = (CTaskManager::CTask *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      CTaskManager::CTask::~CTask(v6);
      operator delete(v6, (const struct std::nothrow_t *)0xC0);
    }
    *((_QWORD *)this + 7) = v3;
  }
  v4 = (vt::CSystem::CThreadPool::CThreadPoolInternal *)*((_QWORD *)this + 6);
  if ( v4 )
    vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(v4);
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    vt::CSystem::CThreadPool::CThreadPoolInternal::~CThreadPoolInternal(*((vt::CSystem::CThreadPool::CThreadPoolInternal **)this
                                                                        + 6));
    operator delete(v5, (const struct std::nothrow_t *)0x58);
  }
  if ( *(_BYTE *)this )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x1800b7fdc  mov     [rsp+arg_8], rbx
0x1800b7fe1  mov     [rsp+arg_10], rsi
0x1800b7fe6  push    rdi
0x1800b7fe7  sub     rsp, 20h
0x1800b7feb  mov     rax, [rcx+38h]
0x1800b7fef  mov     rdi, rcx
0x1800b7ff2  jmp     short loc_1800B8034
0x1800b7ff4  mov     rax, [rdi+38h]
0x1800b7ff8  mov     rsi, [rax+0B8h]
0x1800b7fff  mov     rax, [rdi+38h]
0x1800b8003  mov     [rsp+28h+arg_0], rax
0x1800b8008  mov     rax, [rsp+28h+arg_0]
0x1800b800d  test    rax, rax
0x1800b8010  jz      short loc_1800B802C
0x1800b8012  mov     rbx, [rsp+28h+arg_0]
0x1800b8017  mov     rcx, rbx; this
0x1800b801a  call    ??1CTask@CTaskManager@@QEAA@XZ; CTaskManager::CTask::~CTask(void)
0x1800b801f  mov     edx, 0C0h; struct std::nothrow_t *
0x1800b8024  mov     rcx, rbx; void *
0x1800b8027  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b802c  mov     [rdi+38h], rsi
0x1800b8030  mov     rax, [rdi+38h]
0x1800b8034  test    rax, rax
0x1800b8037  jnz     short loc_1800B7FF4
0x1800b8039  mov     rcx, [rdi+30h]; this
0x1800b803d  test    rcx, rcx
0x1800b8040  jz      short loc_1800B8047
0x1800b8042  call    ?Shutdown@CThreadPoolInternal@CThreadPool@CSystem@vt@@QEAAJXZ; vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(void)
0x1800b8047  mov     rbx, [rdi+30h]
0x1800b804b  test    rbx, rbx
0x1800b804e  jz      short loc_1800B8065
0x1800b8050  mov     rcx, rbx; this
0x1800b8053  call    ??1CThreadPoolInternal@CThreadPool@CSystem@vt@@QEAA@XZ; vt::CSystem::CThreadPool::CThreadPoolInternal::~CThreadPoolInternal(void)
0x1800b8058  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800b805d  mov     rcx, rbx; void *
0x1800b8060  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b8065  cmp     byte ptr [rdi], 0
0x1800b8068  jz      short loc_1800B8077
0x1800b806a  lea     rcx, [rdi+8]; lpCriticalSection
0x1800b806e  call    cs:__imp_DeleteCriticalSection
0x1800b8074  mov     byte ptr [rdi], 0
0x1800b8077  mov     rbx, [rsp+28h+arg_8]
0x1800b807c  mov     rsi, [rsp+28h+arg_10]
0x1800b8081  add     rsp, 20h
0x1800b8085  pop     rdi
0x1800b8086  retn
```
