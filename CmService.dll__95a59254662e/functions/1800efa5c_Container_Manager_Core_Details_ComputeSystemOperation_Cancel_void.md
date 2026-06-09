# Container::Manager::Core::Details::ComputeSystemOperation::Cancel(void)

- ea: `0x1800efa5c`
- end: `0x1800efb5b`
- name: `?Cancel@ComputeSystemOperation@Details@Core@Manager@Container@@QEAAJXZ`
- size: `255`
- prototype: `int(Container::Manager::Core::Details::ComputeSystemOperation *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800de470`
- `0x1800e3af8`
- `0x1800e84a8`
- `0x1800ef76c`
- `0x1800f1cf8`

## callees

- `0x18000da88`
- `0x1800efa5c`
- `0x1800f8d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800efa75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800efacb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800efa75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800efacb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efaac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efb1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efb3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efaac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efb1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efb3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efa81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efad7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efa81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efad7`

## string_xrefs

- `0x1800efafa`: `onecore\base\gendrv\silos\clem\core\lib\computesystemoperation.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemOperation::Cancel(
        Container::Manager::Core::Details::ComputeSystemOperation *this)
{
  char *v1; // rbx
  int v3; // esi
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (char *)this + 40;
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  *((_DWORD *)v1 + 2) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 60) )
    goto LABEL_9;
  ++*((_DWORD *)this + 14);
  if ( v1 )
  {
    *((_DWORD *)v1 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v1);
  }
  v3 = Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(*((PSRWLOCK *)this + 17), 0);
  AcquireSRWLockExclusive((PSRWLOCK)v1);
  *((_DWORD *)v1 + 2) = GetCurrentThreadId();
  if ( v3 >= 0 || (--*((_DWORD *)this + 14), v3 == -2147019873) )
  {
LABEL_9:
    if ( v1 )
    {
      *((_DWORD *)v1 + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v1);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\computesystemoperation.cpp",
      (const char *)(unsigned int)v3,
      v5);
    if ( v1 )
    {
      *((_DWORD *)v1 + 2) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v1);
    }
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x1800efa5c  mov     [rsp+arg_0], rbx
0x1800efa61  mov     [rsp+arg_8], rsi
0x1800efa66  push    rdi; int
0x1800efa67  sub     rsp, 20h
0x1800efa6b  lea     rbx, [rcx+28h]
0x1800efa6f  mov     rdi, rcx
0x1800efa72  mov     rcx, rbx; SRWLock
0x1800efa75  call    cs:__imp_AcquireSRWLockExclusive
0x1800efa7c  nop     dword ptr [rax+rax+00h]
0x1800efa81  call    cs:__imp_GetCurrentThreadId
0x1800efa88  nop     dword ptr [rax+rax+00h]
0x1800efa8d  mov     [rbx+8], eax
0x1800efa90  cmp     byte ptr [rdi+3Ch], 0
0x1800efa94  jnz     loc_1800EFB2D
0x1800efa9a  inc     dword ptr [rdi+38h]
0x1800efa9d  test    rbx, rbx
0x1800efaa0  jz      short loc_1800EFAB8
0x1800efaa2  mov     rcx, rbx; SRWLock
0x1800efaa5  mov     dword ptr [rbx+8], 0
0x1800efaac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800efab3  nop     dword ptr [rax+rax+00h]
0x1800efab8  mov     rcx, [rdi+88h]; SRWLock
0x1800efabf  xor     edx, edx; bool
0x1800efac1  call    ?Terminate@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@QEAAJ_N@Z; Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::Terminate(bool)
0x1800efac6  mov     rcx, rbx; SRWLock
0x1800efac9  mov     esi, eax
0x1800efacb  call    cs:__imp_AcquireSRWLockExclusive
0x1800efad2  nop     dword ptr [rax+rax+00h]
0x1800efad7  call    cs:__imp_GetCurrentThreadId
0x1800efade  nop     dword ptr [rax+rax+00h]
0x1800efae3  mov     [rbx+8], eax
0x1800efae6  test    esi, esi
0x1800efae8  jns     short loc_1800EFB2D
0x1800efaea  dec     dword ptr [rdi+38h]
0x1800efaed  cmp     esi, 8007139Fh
0x1800efaf3  jz      short loc_1800EFB2D
0x1800efaf5  mov     rcx, [rsp+28h]; this
0x1800efafa  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800efb01  mov     r9d, esi; char *
0x1800efb04  mov     edx, 19Eh; void *
0x1800efb09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800efb0e  test    rbx, rbx
0x1800efb11  jz      short loc_1800EFB29
0x1800efb13  mov     rcx, rbx; SRWLock
0x1800efb16  mov     dword ptr [rbx+8], 0
0x1800efb1d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800efb24  nop     dword ptr [rax+rax+00h]
0x1800efb29  mov     eax, esi
0x1800efb2b  jmp     short loc_1800EFB4A
0x1800efb2d  test    rbx, rbx
0x1800efb30  jz      short loc_1800EFB48
0x1800efb32  mov     rcx, rbx; SRWLock
0x1800efb35  mov     dword ptr [rbx+8], 0
0x1800efb3c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800efb43  nop     dword ptr [rax+rax+00h]
0x1800efb48  xor     eax, eax
0x1800efb4a  mov     rbx, [rsp+28h+arg_0]
0x1800efb4f  mov     rsi, [rsp+28h+arg_8]
0x1800efb54  add     rsp, 20h
0x1800efb58  pop     rdi
0x1800efb59  retn
```
