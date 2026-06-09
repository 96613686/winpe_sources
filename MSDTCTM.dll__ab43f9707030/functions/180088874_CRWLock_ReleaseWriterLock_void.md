# CRWLock::ReleaseWriterLock(void)

- ea: `0x180088874`
- end: `0x180088942`
- name: `?ReleaseWriterLock@CRWLock@@QEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800256a8`
- `0x180088784`

## callees

- `0x1800846c0`
- `0x1800886c4`
- `0x180088710`
- `0x18008875c`
- `0x180088874`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088880`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800888c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800888c5`

## string_xrefs

- `0x180088935`: `Attempt to release writer lock on a wrong thread`

## pseudocode

```c
__int64 __fastcall CRWLock::ReleaseWriterLock(CRWLock *this)
{
  signed __int32 v3; // edi
  void *ReaderEvent; // rsi
  void *WriterEvent; // rbp
  signed __int32 v6; // edx
  int v7; // eax
  void *v8; // rcx

  if ( *((_DWORD *)this + 21) != GetCurrentThreadId() )
    DtcInternalErrorW(L"Attempt to release writer lock on a wrong thread");
  if ( (*((_WORD *)this + 47))-- != 1 )
    return 0;
  v3 = *((_DWORD *)this + 20);
  ReaderEvent = 0;
  WriterEvent = 0;
  *((_DWORD *)this + 21) = 0;
  do
  {
    if ( (v3 & 0x7FE000) != 0 )
    {
      ReaderEvent = CRWLock::GetReaderEvent(this);
      if ( !ReaderEvent )
        goto LABEL_6;
      v7 = -3072;
    }
    else
    {
      v7 = -4096;
      if ( (v3 & 0xFF800000) != 0 )
      {
        WriterEvent = CRWLock::GetWriterEvent(this);
        if ( !WriterEvent )
        {
LABEL_6:
          Sleep(0x64u);
          v3 = *((_DWORD *)this + 20);
          v6 = 0;
          continue;
        }
        v7 = -2048;
      }
    }
    v6 = v3;
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v7 + v3, v3);
  }
  while ( v3 != v6 );
  if ( (v6 & 0x7FE000) != 0 )
  {
    v8 = ReaderEvent;
    goto LABEL_17;
  }
  if ( (v6 & 0xFF800000) != 0 )
  {
    v8 = WriterEvent;
LABEL_17:
    CRWLock::RWSetEvent(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180088874  push    rbx
0x180088876  push    rbp
0x180088877  push    rsi
0x180088878  push    rdi
0x180088879  sub     rsp, 28h
0x18008887d  mov     rbx, rcx
0x180088880  call    cs:__imp_GetCurrentThreadId
0x180088886  cmp     [rbx+54h], eax
0x180088889  jnz     loc_180088935
0x18008888f  mov     eax, 0FFFFh
0x180088894  add     [rbx+5Eh], ax
0x180088898  jnz     loc_18008892A
0x18008889e  mov     edi, [rbx+50h]
0x1800888a1  xor     esi, esi
0x1800888a3  xor     ebp, ebp
0x1800888a5  mov     [rbx+54h], esi
0x1800888a8  test    edi, 7FE000h
0x1800888ae  jz      short loc_1800888D9
0x1800888b0  mov     rcx, rbx; this
0x1800888b3  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x1800888b8  mov     rsi, rax
0x1800888bb  test    rax, rax
0x1800888be  jnz     short loc_1800888D2
0x1800888c0  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800888c5  call    cs:__imp_Sleep
0x1800888cb  mov     edi, [rbx+50h]
0x1800888ce  xor     edx, edx
0x1800888d0  jmp     short loc_180088909
0x1800888d2  mov     eax, 0FFFFF400h
0x1800888d7  jmp     short loc_1800888FB
0x1800888d9  mov     eax, 0FFFFF000h
0x1800888de  test    edi, 0FF800000h
0x1800888e4  jz      short loc_1800888FB
0x1800888e6  mov     rcx, rbx; this
0x1800888e9  call    ?GetWriterEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetWriterEvent(void)
0x1800888ee  mov     rbp, rax
0x1800888f1  test    rax, rax
0x1800888f4  jz      short loc_1800888C0
0x1800888f6  mov     eax, 0FFFFF800h
0x1800888fb  lea     ecx, [rax+rdi]
0x1800888fe  mov     edx, edi
0x180088900  mov     eax, edi
0x180088902  lock cmpxchg [rbx+50h], ecx
0x180088907  mov     edi, eax
0x180088909  cmp     edi, edx
0x18008890b  jnz     short loc_1800888A8
0x18008890d  test    edx, 7FE000h
0x180088913  jz      short loc_18008891A
0x180088915  mov     rcx, rsi
0x180088918  jmp     short loc_180088925
0x18008891a  test    edx, 0FF800000h
0x180088920  jz      short loc_18008892A
0x180088922  mov     rcx, rbp; void *
0x180088925  call    ?RWSetEvent@CRWLock@@CAXPEAX@Z; CRWLock::RWSetEvent(void *)
0x18008892a  xor     eax, eax
0x18008892c  add     rsp, 28h
0x180088930  pop     rdi
0x180088931  pop     rsi
0x180088932  pop     rbp
0x180088933  pop     rbx
0x180088934  retn
0x180088935  lea     rcx, aAttemptToRelea; "Attempt to release writer lock on a wro"...
0x18008893c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
