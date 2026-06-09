# CPCRRecordBufferSource::~CPCRRecordBufferSource(void)

- ea: `0x18002e198`
- end: `0x18002e224`
- name: `??1CPCRRecordBufferSource@@UEAA@XZ`
- size: `140`
- prototype: `void __fastcall(CPCRRecordBufferSource *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002e6a0`
- `0x18002e6e0`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002e198`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e1de`
- `KERNEL32!DeleteCriticalSection` at `0x18002e1de`

## pseudocode

```c
void __fastcall CPCRRecordBufferSource::~CPCRRecordBufferSource(CPCRRecordBufferSource *this)
{
  volatile signed __int32 *v1; // rbx
  volatile signed __int32 *v3; // rbx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  *(_QWORD *)this = &CPCRRecordBufferSource::`vftable';
  if ( _InterlockedExchangeAdd(v1 + 10, 0xFFFFFFFF) == 1 && v1 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v1);
    operator delete((void *)v1, 0x2530u);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *(_QWORD *)this = &CBufferSource::`vftable';
  if ( _InterlockedExchangeAdd(v3 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v3 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v3);
      operator delete((void *)v3, 0x2530u);
    }
  }
}

```

## disassembly

```asm
0x18002e198  mov     [rsp+arg_8], rbx
0x18002e19d  push    rdi
0x18002e19e  sub     rsp, 20h
0x18002e1a2  mov     rbx, [rcx+20h]
0x18002e1a6  lea     rax, ??_7CPCRRecordBufferSource@@6B@; const CPCRRecordBufferSource::`vftable'
0x18002e1ad  mov     [rcx], rax
0x18002e1b0  mov     rdi, rcx
0x18002e1b3  or      eax, 0FFFFFFFFh
0x18002e1b6  lock xadd [rbx+28h], eax
0x18002e1bb  cmp     eax, 1
0x18002e1be  jnz     short loc_18002E1DA
0x18002e1c0  test    rbx, rbx
0x18002e1c3  jz      short loc_18002E1DA
0x18002e1c5  mov     rcx, rbx; this
0x18002e1c8  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002e1cd  mov     edx, 2530h; unsigned __int64
0x18002e1d2  mov     rcx, rbx; void *
0x18002e1d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e1da  lea     rcx, [rdi+30h]; lpCriticalSection
0x18002e1de  call    cs:__imp_DeleteCriticalSection
0x18002e1e4  mov     rbx, [rdi+10h]
0x18002e1e8  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002e1ef  mov     [rdi], rax
0x18002e1f2  or      eax, 0FFFFFFFFh
0x18002e1f5  lock xadd [rbx+28h], eax
0x18002e1fa  cmp     eax, 1
0x18002e1fd  jnz     short loc_18002E219
0x18002e1ff  test    rbx, rbx
0x18002e202  jz      short loc_18002E219
0x18002e204  mov     rcx, rbx; this
0x18002e207  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002e20c  mov     edx, 2530h; unsigned __int64
0x18002e211  mov     rcx, rbx; void *
0x18002e214  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e219  mov     rbx, [rsp+28h+arg_8]
0x18002e21e  add     rsp, 20h
0x18002e222  pop     rdi
0x18002e223  retn
```
