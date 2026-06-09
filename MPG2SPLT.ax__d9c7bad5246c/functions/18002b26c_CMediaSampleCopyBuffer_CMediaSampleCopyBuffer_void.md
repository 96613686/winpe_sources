# CMediaSampleCopyBuffer::~CMediaSampleCopyBuffer(void)

- ea: `0x18002b26c`
- end: `0x18002b346`
- name: `??1CMediaSampleCopyBuffer@@UEAA@XZ`
- size: `218`
- prototype: `void __fastcall(CMediaSampleCopyBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002b470`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002b26c`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002b2ce`
- `KERNEL32!DeleteCriticalSection` at `0x18002b2ce`

## pseudocode

```c
void __fastcall CMediaSampleCopyBuffer::~CMediaSampleCopyBuffer(CMediaSampleCopyBuffer *this)
{
  volatile signed __int32 *v2; // rcx
  __int64 v3; // rdi
  unsigned __int64 v4; // rdx
  volatile signed __int32 *v5; // rbx

  *(_QWORD *)this = &CMediaSampleCopyBuffer::`vftable';
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 38, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v2 + 16LL))(v2, 1);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = *((_QWORD *)this + 6);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 40), 0xFFFFFFFF) == 1 && v3 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v3);
    operator delete((void *)v3, 0x30u);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 4) + 24LL) + 16LL))(*((_QWORD *)this + 4) + 24LL);
  operator delete(*((void **)this + 8), v4);
  *((_QWORD *)this + 8) = 0;
  *(_QWORD *)this = &CBufferSource::`vftable';
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( _InterlockedExchangeAdd(v5 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v5 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v5);
      operator delete((void *)v5, 0x2530u);
    }
  }
}

```

## disassembly

```asm
0x18002b26c  mov     [rsp+arg_8], rbx
0x18002b271  push    rdi
0x18002b272  sub     rsp, 20h
0x18002b276  lea     rax, ??_7CMediaSampleCopyBuffer@@6B@; const CMediaSampleCopyBuffer::`vftable'
0x18002b27d  mov     rbx, rcx
0x18002b280  mov     [rcx], rax
0x18002b283  mov     rcx, [rcx+38h]
0x18002b287  test    rcx, rcx
0x18002b28a  jz      short loc_18002B2B5
0x18002b28c  or      eax, 0FFFFFFFFh
0x18002b28f  lock xadd [rcx+98h], eax
0x18002b297  cmp     eax, 1
0x18002b29a  jnz     short loc_18002B2AD
0x18002b29c  mov     rax, [rcx]
0x18002b29f  mov     edx, 1
0x18002b2a4  mov     rax, [rax+10h]
0x18002b2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ad  mov     qword ptr [rbx+38h], 0
0x18002b2b5  mov     rdi, [rbx+30h]
0x18002b2b9  or      eax, 0FFFFFFFFh
0x18002b2bc  lock xadd [rdi+28h], eax
0x18002b2c1  cmp     eax, 1
0x18002b2c4  jnz     short loc_18002B2E1
0x18002b2c6  test    rdi, rdi
0x18002b2c9  jz      short loc_18002B2E1
0x18002b2cb  mov     rcx, rdi; lpCriticalSection
0x18002b2ce  call    cs:__imp_DeleteCriticalSection
0x18002b2d4  mov     edx, 30h ; '0'; unsigned __int64
0x18002b2d9  mov     rcx, rdi; void *
0x18002b2dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b2e1  mov     rcx, [rbx+20h]
0x18002b2e5  add     rcx, 18h
0x18002b2e9  mov     rax, [rcx]
0x18002b2ec  mov     rax, [rax+10h]
0x18002b2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2f5  mov     rcx, [rbx+40h]; void *
0x18002b2f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b2fe  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002b305  mov     qword ptr [rbx+40h], 0
0x18002b30d  mov     [rbx], rax
0x18002b310  or      eax, 0FFFFFFFFh
0x18002b313  mov     rbx, [rbx+10h]
0x18002b317  lock xadd [rbx+28h], eax
0x18002b31c  cmp     eax, 1
0x18002b31f  jnz     short loc_18002B33B
0x18002b321  test    rbx, rbx
0x18002b324  jz      short loc_18002B33B
0x18002b326  mov     rcx, rbx; this
0x18002b329  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002b32e  mov     edx, 2530h; unsigned __int64
0x18002b333  mov     rcx, rbx; void *
0x18002b336  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b33b  mov     rbx, [rsp+28h+arg_8]
0x18002b340  add     rsp, 20h
0x18002b344  pop     rdi
0x18002b345  retn
```
