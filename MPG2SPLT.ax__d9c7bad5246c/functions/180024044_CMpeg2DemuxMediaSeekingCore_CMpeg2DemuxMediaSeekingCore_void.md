# CMpeg2DemuxMediaSeekingCore::~CMpeg2DemuxMediaSeekingCore(void)

- ea: `0x180024044`
- end: `0x18002407c`
- name: `??1CMpeg2DemuxMediaSeekingCore@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CMpeg2DemuxMediaSeekingCore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180013168`

## callees

- `0x180001048`
- `0x180024044`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180024063`
- `KERNEL32!DeleteCriticalSection` at `0x180024063`

## pseudocode

```c
void __fastcall CMpeg2DemuxMediaSeekingCore::~CMpeg2DemuxMediaSeekingCore(CMpeg2DemuxMediaSeekingCore *this)
{
  __int64 v1; // rbx

  v1 = *((_QWORD *)this + 4);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 40), 0xFFFFFFFF) == 1 )
  {
    if ( v1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)v1);
      operator delete((void *)v1, 0x30u);
    }
  }
}

```

## disassembly

```asm
0x180024044  push    rbx
0x180024046  sub     rsp, 20h
0x18002404a  mov     rbx, [rcx+20h]
0x18002404e  or      eax, 0FFFFFFFFh
0x180024051  lock xadd [rbx+28h], eax
0x180024056  cmp     eax, 1
0x180024059  jnz     short loc_180024076
0x18002405b  test    rbx, rbx
0x18002405e  jz      short loc_180024076
0x180024060  mov     rcx, rbx; lpCriticalSection
0x180024063  call    cs:__imp_DeleteCriticalSection
0x180024069  mov     edx, 30h ; '0'; unsigned __int64
0x18002406e  mov     rcx, rbx; void *
0x180024071  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024076  add     rsp, 20h
0x18002407a  pop     rbx
0x18002407b  retn
```
