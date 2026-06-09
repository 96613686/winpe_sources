# CMPEG2Demultiplexer::DeletePin_(ushort const *)

- ea: `0x180014608`
- end: `0x180014769`
- name: `?DeletePin_@CMPEG2Demultiplexer@@AEAAJPEBG@Z`
- size: `353`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180014564`
- `0x18001c1b0`
- `0x18001e880`

## callees

- `0x180001048`
- `0x180014608`
- `0x180014998`
- `0x180017020`
- `0x180021bfc`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014708`
- `KERNEL32!LeaveCriticalSection` at `0x180014754`
- `KERNEL32!LeaveCriticalSection` at `0x180014708`
- `KERNEL32!LeaveCriticalSection` at `0x180014754`
- `KERNEL32!EnterCriticalSection` at `0x180014626`
- `KERNEL32!EnterCriticalSection` at `0x1800146ee`
- `KERNEL32!EnterCriticalSection` at `0x180014626`
- `KERNEL32!EnterCriticalSection` at `0x1800146ee`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::DeletePin_(CMPEG2Demultiplexer *this, const unsigned __int16 *a2)
{
  int PinRecordLocked; // ebx
  void **v5; // rdi
  __int64 v6; // rcx
  LPCRITICAL_SECTION *v7; // rbp
  struct CMPEG2DemuxOutputPin *v8; // rbx
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  struct DEMUX_PIN_RECORD *v11; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v11 = 0;
  PinRecordLocked = CMPEG2Demultiplexer::FindPinRecordLocked_(this, a2, &v11, &v10);
  if ( PinRecordLocked >= 0 )
  {
    v5 = (void **)v11;
    v6 = *(_QWORD *)(*(_QWORD *)v11 + 48LL);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
      (*(void (__fastcall **)(__int64))(*((_QWORD *)*v5 + 3) + 40LL))((__int64)*v5 + 24);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 && v5 )
    {
      operator delete(v5[2]);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v5 + 1) + 16LL))(*((_QWORD *)*v5 + 1));
      operator delete(v5);
    }
    TSimpleVector<CPCRValue *>::Remove((char *)this + 184, v10);
    v7 = (LPCRITICAL_SECTION *)*((_QWORD *)this + 42);
    if ( v7 && *((_DWORD *)v5 + 3) == 1 )
    {
      v8 = (struct CMPEG2DemuxOutputPin *)*v5;
      EnterCriticalSection(v7[23]);
      PinRecordLocked = CMPEG2Controller::UnmapAllStreamsLocked_((CMPEG2Controller *)v7, v8);
      LeaveCriticalSection(v7[23]);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 && v5 )
    {
      operator delete(v5[2]);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v5 + 1) + 16LL))(*((_QWORD *)*v5 + 1));
      operator delete(v5);
    }
    _InterlockedIncrement((volatile signed __int32 *)this + 28);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  return (unsigned int)PinRecordLocked;
}

```

## disassembly

```asm
0x180014608  mov     [rsp+arg_8], rbx
0x18001460d  push    rbp
0x18001460e  push    rsi
0x18001460f  push    rdi
0x180014610  sub     rsp, 20h
0x180014614  mov     rsi, rcx
0x180014617  mov     [rsp+38h+arg_0], 0
0x18001461f  mov     rcx, [rcx+50h]; lpCriticalSection
0x180014623  mov     rbx, rdx
0x180014626  call    cs:__imp_EnterCriticalSection
0x18001462c  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x180014631  mov     [rsp+38h+arg_10], 0
0x18001463a  lea     r8, [rsp+38h+arg_10]; struct DEMUX_PIN_RECORD **
0x18001463f  mov     rdx, rbx; unsigned __int16 *
0x180014642  mov     rcx, rsi; this
0x180014645  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x18001464a  mov     ebx, eax
0x18001464c  test    eax, eax
0x18001464e  js      loc_180014750
0x180014654  mov     rdi, [rsp+38h+arg_10]
0x180014659  mov     rcx, [rdi]
0x18001465c  mov     rcx, [rcx+30h]
0x180014660  test    rcx, rcx
0x180014663  jz      short loc_180014684
0x180014665  mov     rdx, [rcx]
0x180014668  mov     rax, [rdx+28h]
0x18001466c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014671  mov     rcx, [rdi]
0x180014674  add     rcx, 18h
0x180014678  mov     rax, [rcx]
0x18001467b  mov     rax, [rax+28h]
0x18001467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014684  or      eax, 0FFFFFFFFh
0x180014687  lock xadd [rdi+8], eax
0x18001468c  cmp     eax, 1
0x18001468f  jnz     short loc_1800146C2
0x180014691  test    rdi, rdi
0x180014694  jz      short loc_1800146C2
0x180014696  mov     rcx, [rdi+10h]; void *
0x18001469a  lea     edx, [rax+1]; unsigned __int64
0x18001469d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800146a2  mov     rax, [rdi]
0x1800146a5  mov     rcx, [rax+8]
0x1800146a9  mov     rax, [rcx]
0x1800146ac  mov     rax, [rax+10h]
0x1800146b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146b5  mov     edx, 18h; unsigned __int64
0x1800146ba  mov     rcx, rdi; void *
0x1800146bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800146c2  mov     edx, [rsp+38h+arg_0]
0x1800146c6  lea     rcx, [rsi+0B8h]
0x1800146cd  call    ?Remove@?$TSimpleVector@PEAVCPCRValue@@@@QEAAJKPEAPEAVCPCRValue@@@Z; TSimpleVector<CPCRValue *>::Remove(ulong,CPCRValue * *)
0x1800146d2  mov     rbp, [rsi+150h]
0x1800146d9  test    rbp, rbp
0x1800146dc  jz      short loc_18001470E
0x1800146de  cmp     dword ptr [rdi+0Ch], 1
0x1800146e2  jnz     short loc_18001470E
0x1800146e4  mov     rcx, [rbp+0B8h]; lpCriticalSection
0x1800146eb  mov     rbx, [rdi]
0x1800146ee  call    cs:__imp_EnterCriticalSection
0x1800146f4  mov     rdx, rbx; struct CMPEG2DemuxOutputPin *
0x1800146f7  mov     rcx, rbp; this
0x1800146fa  call    ?UnmapAllStreamsLocked_@CMPEG2Controller@@AEAAJPEAVCMPEG2DemuxOutputPin@@@Z; CMPEG2Controller::UnmapAllStreamsLocked_(CMPEG2DemuxOutputPin *)
0x1800146ff  mov     rcx, [rbp+0B8h]; lpCriticalSection
0x180014706  mov     ebx, eax
0x180014708  call    cs:__imp_LeaveCriticalSection
0x18001470e  or      eax, 0FFFFFFFFh
0x180014711  lock xadd [rdi+8], eax
0x180014716  cmp     eax, 1
0x180014719  jnz     short loc_18001474C
0x18001471b  test    rdi, rdi
0x18001471e  jz      short loc_18001474C
0x180014720  mov     rcx, [rdi+10h]; void *
0x180014724  lea     edx, [rax+1]; unsigned __int64
0x180014727  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001472c  mov     rax, [rdi]
0x18001472f  mov     rcx, [rax+8]
0x180014733  mov     rax, [rcx]
0x180014736  mov     rax, [rax+10h]
0x18001473a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001473f  mov     edx, 18h; unsigned __int64
0x180014744  mov     rcx, rdi; void *
0x180014747  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001474c  lock inc dword ptr [rsi+70h]
0x180014750  mov     rcx, [rsi+50h]; lpCriticalSection
0x180014754  call    cs:__imp_LeaveCriticalSection
0x18001475a  mov     eax, ebx
0x18001475c  mov     rbx, [rsp+38h+arg_8]
0x180014761  add     rsp, 20h
0x180014765  pop     rdi
0x180014766  pop     rsi
0x180014767  pop     rbp
0x180014768  retn
```
