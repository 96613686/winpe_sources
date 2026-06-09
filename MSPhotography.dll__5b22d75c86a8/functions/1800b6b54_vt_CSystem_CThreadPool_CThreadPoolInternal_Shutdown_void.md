# vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(void)

- ea: `0x1800b6b54`
- end: `0x1800b6bde`
- name: `?Shutdown@CThreadPoolInternal@CThreadPool@CSystem@vt@@QEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(vt::CSystem::CThreadPool::CThreadPoolInternal *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b6960`
- `0x1800b7fdc`

## callees

- `0x180003985`
- `0x1800b6b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b6b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b6b65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b6bcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b6bcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b6b78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b6b78`

## pseudocode

```c
__int64 __fastcall vt::CSystem::CThreadPool::CThreadPoolInternal::Shutdown(
        vt::CSystem::CThreadPool::CThreadPoolInternal *this)
{
  PTP_WORK *v2; // rcx
  char *v3; // r14
  char *i; // rsi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  while ( 1 )
  {
    v2 = (PTP_WORK *)*((_QWORD *)this + 3);
    if ( *((PTP_WORK **)this + 4) == v2 )
      break;
    CloseThreadpoolWork(*v2);
    v3 = (char *)*((_QWORD *)this + 3);
    for ( i = v3; i < v3 + 8; i += 8 )
    {
      if ( (unsigned __int64)i >= *((_QWORD *)this + 4) )
        break;
    }
    memmove_0(*((void **)this + 3), i, (*((_QWORD *)this + 4) - (_QWORD)i) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 4) = &v3[8 * ((__int64)(*((_QWORD *)this + 4) - (_QWORD)i) >> 3)];
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return 0;
}

```

## disassembly

```asm
0x1800b6b54  push    rbx
0x1800b6b56  push    rsi
0x1800b6b57  push    rdi
0x1800b6b58  push    r14
0x1800b6b5a  sub     rsp, 28h
0x1800b6b5e  mov     rdi, rcx
0x1800b6b61  add     rcx, 30h ; '0'; lpCriticalSection
0x1800b6b65  call    cs:__imp_EnterCriticalSection
0x1800b6b6b  mov     rcx, [rdi+18h]
0x1800b6b6f  cmp     [rdi+20h], rcx
0x1800b6b73  jz      short loc_1800B6BC8
0x1800b6b75  mov     rcx, [rcx]; pwk
0x1800b6b78  call    cs:__imp_CloseThreadpoolWork
0x1800b6b7e  mov     r14, [rdi+18h]
0x1800b6b82  mov     rsi, r14
0x1800b6b85  lea     rax, [r14+8]
0x1800b6b89  cmp     r14, rax
0x1800b6b8c  jnb     short loc_1800B6B9D
0x1800b6b8e  cmp     rsi, [rdi+20h]
0x1800b6b92  jnb     short loc_1800B6B9D
0x1800b6b94  add     rsi, 8
0x1800b6b98  cmp     rsi, rax
0x1800b6b9b  jb      short loc_1800B6B8E
0x1800b6b9d  mov     r8, [rdi+20h]
0x1800b6ba1  mov     rdx, rsi; Src
0x1800b6ba4  sub     r8, rsi
0x1800b6ba7  mov     rcx, r14; void *
0x1800b6baa  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800b6bae  call    memmove_0
0x1800b6bb3  mov     rax, [rdi+20h]
0x1800b6bb7  sub     rax, rsi
0x1800b6bba  sar     rax, 3
0x1800b6bbe  lea     rax, [r14+rax*8]
0x1800b6bc2  mov     [rdi+20h], rax
0x1800b6bc6  jmp     short loc_1800B6B6B
0x1800b6bc8  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800b6bcc  call    cs:__imp_LeaveCriticalSection
0x1800b6bd2  xor     eax, eax
0x1800b6bd4  add     rsp, 28h
0x1800b6bd8  pop     r14
0x1800b6bda  pop     rdi
0x1800b6bdb  pop     rsi
0x1800b6bdc  pop     rbx
0x1800b6bdd  retn
```
