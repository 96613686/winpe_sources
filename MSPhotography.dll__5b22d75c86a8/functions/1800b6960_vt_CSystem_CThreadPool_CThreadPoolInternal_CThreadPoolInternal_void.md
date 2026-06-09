# vt::CSystem::CThreadPool::CThreadPoolInternal::~CThreadPoolInternal(void)

- ea: `0x1800b6960`
- end: `0x1800b6999`
- name: `??1CThreadPoolInternal@CThreadPool@CSystem@vt@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(vt::CSystem::CThreadPool::CThreadPoolInternal *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800b7fdc`

## callees

- `0x1800028cc`
- `0x1800b6b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b6972`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b6972`

## pseudocode

```c
void __fastcall vt::CSystem::CThreadPool::CThreadPoolInternal::~CThreadPoolInternal(
        vt::CSystem::CThreadPool::CThreadPoolInternal *this)
{
  const struct std::nothrow_t *v2; // rdx

  vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  operator delete(*((void **)this + 2), v2);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1800b6960  push    rbx
0x1800b6962  sub     rsp, 20h
0x1800b6966  mov     rbx, rcx
0x1800b6969  call    ?Shutdown@CThreadPoolInternal@CThreadPool@CSystem@vt@@QEAAJXZ; vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(void)
0x1800b696e  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800b6972  call    cs:__imp_DeleteCriticalSection
0x1800b6978  mov     rcx, [rbx+10h]; void *
0x1800b697c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b6981  xor     eax, eax
0x1800b6983  mov     [rbx+28h], rax
0x1800b6987  mov     [rbx+18h], rax
0x1800b698b  mov     [rbx+20h], rax
0x1800b698f  mov     [rbx+10h], rax
0x1800b6993  add     rsp, 20h
0x1800b6997  pop     rbx
0x1800b6998  retn
```
