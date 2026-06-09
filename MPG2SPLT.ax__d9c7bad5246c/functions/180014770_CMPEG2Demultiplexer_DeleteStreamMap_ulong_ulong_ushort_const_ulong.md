# CMPEG2Demultiplexer::DeleteStreamMap_(ulong,ulong *,ushort const *,ulong)

- ea: `0x180014770`
- end: `0x180014895`
- name: `?DeleteStreamMap_@CMPEG2Demultiplexer@@AEAAJKPEAKPEBGK@Z`
- size: `293`
- prototype: `__int64 __usercall@<rax>(CMPEG2Demultiplexer *__hidden this@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, const unsigned __int16 *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001cdb0`
- `0x18001cdf0`

## callees

- `0x180001048`
- `0x180014770`
- `0x180014998`
- `0x180021d08`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001485d`
- `KERNEL32!LeaveCriticalSection` at `0x180014876`
- `KERNEL32!LeaveCriticalSection` at `0x18001485d`
- `KERNEL32!LeaveCriticalSection` at `0x180014876`
- `KERNEL32!EnterCriticalSection` at `0x1800147a5`
- `KERNEL32!EnterCriticalSection` at `0x1800147af`
- `KERNEL32!EnterCriticalSection` at `0x1800147a5`
- `KERNEL32!EnterCriticalSection` at `0x1800147af`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::DeleteStreamMap_(
        CMPEG2Demultiplexer *this,
        unsigned int a2,
        unsigned int *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  int PinRecordLocked; // eax
  volatile signed __int32 *v11; // rbx
  int v12; // esi
  struct CMPEG2DemuxOutputPin *v13; // r15
  __int64 i; // rbp
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  struct DEMUX_PIN_RECORD *v17; // [rsp+50h] [rbp+8h] BYREF

  v9 = *(struct _RTL_CRITICAL_SECTION **)(*((_QWORD *)this + 42) + 184LL);
  if ( v9 )
    EnterCriticalSection(v9);
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v17 = 0;
  PinRecordLocked = CMPEG2Demultiplexer::FindPinRecordLocked_(this, a4, &v17, 0);
  v11 = (volatile signed __int32 *)v17;
  v12 = PinRecordLocked;
  if ( PinRecordLocked >= 0 )
  {
    v13 = *(struct CMPEG2DemuxOutputPin **)v17;
    v12 = 0;
    for ( i = 0; (unsigned int)i < a2; *((_DWORD *)this + 33) = 1 )
    {
      v12 = CMPEG2Controller::UnmapStream(*((CMPEG2Controller **)this + 42), a5 & a3[i], v13);
      if ( v12 < 0 )
        break;
      i = (unsigned int)(i + 1);
    }
  }
  if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
  {
    operator delete(*((void **)v11 + 2));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v11 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v11 + 8LL));
    operator delete((void *)v11);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v15 = *(struct _RTL_CRITICAL_SECTION **)(*((_QWORD *)this + 42) + 184LL);
  if ( v15 )
    LeaveCriticalSection(v15);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014770  mov     [rsp+arg_8], rbx
0x180014775  mov     [rsp+arg_10], rbp
0x18001477a  push    rsi
0x18001477b  push    rdi
0x18001477c  push    r12
0x18001477e  push    r14
0x180014780  push    r15
0x180014782  sub     rsp, 20h
0x180014786  mov     rax, [rcx+150h]
0x18001478d  mov     rdi, rcx
0x180014790  mov     rbx, r9
0x180014793  mov     r12, r8
0x180014796  mov     r14d, edx
0x180014799  mov     rcx, [rax+0B8h]; lpCriticalSection
0x1800147a0  test    rcx, rcx
0x1800147a3  jz      short loc_1800147AB
0x1800147a5  call    cs:__imp_EnterCriticalSection
0x1800147ab  mov     rcx, [rdi+50h]; lpCriticalSection
0x1800147af  call    cs:__imp_EnterCriticalSection
0x1800147b5  xor     r9d, r9d; unsigned int *
0x1800147b8  mov     [rsp+48h+arg_0], 0
0x1800147c1  lea     r8, [rsp+48h+arg_0]; struct DEMUX_PIN_RECORD **
0x1800147c6  mov     rdx, rbx; unsigned __int16 *
0x1800147c9  mov     rcx, rdi; this
0x1800147cc  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x1800147d1  mov     rbx, [rsp+48h+arg_0]
0x1800147d6  mov     esi, eax
0x1800147d8  test    eax, eax
0x1800147da  js      short loc_180014816
0x1800147dc  mov     r15, [rbx]
0x1800147df  xor     esi, esi
0x1800147e1  xor     ebp, ebp
0x1800147e3  test    r14d, r14d
0x1800147e6  jz      short loc_180014816
0x1800147e8  mov     edx, [r12+rbp*4]
0x1800147ec  mov     r8, r15; struct CMPEG2DemuxOutputPin *
0x1800147ef  and     edx, [rsp+48h+arg_20]; unsigned int
0x1800147f3  mov     rcx, [rdi+150h]; this
0x1800147fa  call    ?UnmapStream@CMPEG2Controller@@QEAAJKPEAVCMPEG2DemuxOutputPin@@@Z; CMPEG2Controller::UnmapStream(ulong,CMPEG2DemuxOutputPin *)
0x1800147ff  mov     esi, eax
0x180014801  test    eax, eax
0x180014803  js      short loc_180014816
0x180014805  inc     ebp
0x180014807  mov     dword ptr [rdi+84h], 1
0x180014811  cmp     ebp, r14d
0x180014814  jb      short loc_1800147E8
0x180014816  test    rbx, rbx
0x180014819  jz      short loc_180014859
0x18001481b  or      eax, 0FFFFFFFFh
0x18001481e  lock xadd [rbx+8], eax
0x180014823  cmp     eax, 1
0x180014826  jnz     short loc_180014859
0x180014828  test    rbx, rbx
0x18001482b  jz      short loc_180014859
0x18001482d  mov     rcx, [rbx+10h]; void *
0x180014831  lea     edx, [rax+1]; unsigned __int64
0x180014834  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014839  mov     rax, [rbx]
0x18001483c  mov     rcx, [rax+8]
0x180014840  mov     rax, [rcx]
0x180014843  mov     rax, [rax+10h]
0x180014847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001484c  mov     edx, 18h; unsigned __int64
0x180014851  mov     rcx, rbx; void *
0x180014854  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014859  mov     rcx, [rdi+50h]; lpCriticalSection
0x18001485d  call    cs:__imp_LeaveCriticalSection
0x180014863  mov     rax, [rdi+150h]
0x18001486a  mov     rcx, [rax+0B8h]; lpCriticalSection
0x180014871  test    rcx, rcx
0x180014874  jz      short loc_18001487C
0x180014876  call    cs:__imp_LeaveCriticalSection
0x18001487c  mov     rbx, [rsp+48h+arg_8]
0x180014881  mov     eax, esi
0x180014883  mov     rbp, [rsp+48h+arg_10]
0x180014888  add     rsp, 20h
0x18001488c  pop     r15
0x18001488e  pop     r14
0x180014890  pop     r12
0x180014892  pop     rdi
0x180014893  pop     rsi
0x180014894  retn
```
