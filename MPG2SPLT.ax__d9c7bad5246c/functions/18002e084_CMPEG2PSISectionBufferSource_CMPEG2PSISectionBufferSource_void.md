# CMPEG2PSISectionBufferSource::~CMPEG2PSISectionBufferSource(void)

- ea: `0x18002e084`
- end: `0x18002e13d`
- name: `??1CMPEG2PSISectionBufferSource@@UEAA@XZ`
- size: `185`
- prototype: `void __fastcall(CMPEG2PSISectionBufferSource *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002e620`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002e084`
- `0x18002ec18`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e0f7`
- `KERNEL32!DeleteCriticalSection` at `0x18002e0f7`

## pseudocode

```c
void __fastcall CMPEG2PSISectionBufferSource::~CMPEG2PSISectionBufferSource(struct _RTL_CRITICAL_SECTION *this)
{
  volatile signed __int32 *OwningThread; // rdi
  __int64 *v3; // rcx
  __int64 v4; // rdx
  __int64 *v5; // rax
  volatile signed __int32 *v7; // rbx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CMPEG2PSISectionBufferSource::`vftable';
  CMPEG2PSISectionBufferSource::Clear((CMPEG2PSISectionBufferSource *)this);
  OwningThread = (volatile signed __int32 *)this->OwningThread;
  if ( _InterlockedExchangeAdd(OwningThread + 10, 0xFFFFFFFF) == 1 && OwningThread )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)OwningThread);
    operator delete((void *)OwningThread, 0x2530u);
  }
  if ( LODWORD(this[1].SpinCount) )
  {
    do
    {
      v3 = (__int64 *)this[1].OwningThread;
      v4 = *v3;
      v5 = (__int64 *)v3[1];
      *v5 = *v3;
      *(_QWORD *)(v4 + 8) = v5;
      operator delete(v3, 0x1048u);
    }
    while ( LODWORD(this[1].SpinCount)-- != 1 );
  }
  DeleteCriticalSection(this + 2);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CBufferSource::`vftable';
  v7 = (volatile signed __int32 *)this->OwningThread;
  if ( _InterlockedExchangeAdd(v7 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v7 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v7);
      operator delete((void *)v7, 0x2530u);
    }
  }
}

```

## disassembly

```asm
0x18002e084  mov     [rsp+arg_8], rbx
0x18002e089  push    rdi
0x18002e08a  sub     rsp, 20h
0x18002e08e  lea     rax, ??_7CMPEG2PSISectionBufferSource@@6B@; const CMPEG2PSISectionBufferSource::`vftable'
0x18002e095  mov     rbx, rcx
0x18002e098  mov     [rcx], rax
0x18002e09b  call    ?Clear@CMPEG2PSISectionBufferSource@@QEAAXXZ; CMPEG2PSISectionBufferSource::Clear(void)
0x18002e0a0  mov     rdi, [rbx+10h]
0x18002e0a4  or      eax, 0FFFFFFFFh
0x18002e0a7  lock xadd [rdi+28h], eax
0x18002e0ac  cmp     eax, 1
0x18002e0af  jnz     short loc_18002E0CB
0x18002e0b1  test    rdi, rdi
0x18002e0b4  jz      short loc_18002E0CB
0x18002e0b6  mov     rcx, rdi; this
0x18002e0b9  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002e0be  mov     edx, 2530h; unsigned __int64
0x18002e0c3  mov     rcx, rdi; void *
0x18002e0c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e0cb  cmp     dword ptr [rbx+48h], 0
0x18002e0cf  jbe     short loc_18002E0F3
0x18002e0d1  mov     rcx, [rbx+38h]; void *
0x18002e0d5  mov     rdx, [rcx]
0x18002e0d8  mov     rax, [rcx+8]
0x18002e0dc  mov     [rax], rdx
0x18002e0df  mov     [rdx+8], rax
0x18002e0e3  mov     edx, 1048h; unsigned __int64
0x18002e0e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e0ed  sub     dword ptr [rbx+48h], 1
0x18002e0f1  jnz     short loc_18002E0D1
0x18002e0f3  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002e0f7  call    cs:__imp_DeleteCriticalSection
0x18002e0fd  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002e104  mov     [rbx], rax
0x18002e107  or      eax, 0FFFFFFFFh
0x18002e10a  mov     rbx, [rbx+10h]
0x18002e10e  lock xadd [rbx+28h], eax
0x18002e113  cmp     eax, 1
0x18002e116  jnz     short loc_18002E132
0x18002e118  test    rbx, rbx
0x18002e11b  jz      short loc_18002E132
0x18002e11d  mov     rcx, rbx; this
0x18002e120  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002e125  mov     edx, 2530h; unsigned __int64
0x18002e12a  mov     rcx, rbx; void *
0x18002e12d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e132  mov     rbx, [rsp+28h+arg_8]
0x18002e137  add     rsp, 20h
0x18002e13b  pop     rdi
0x18002e13c  retn
```
