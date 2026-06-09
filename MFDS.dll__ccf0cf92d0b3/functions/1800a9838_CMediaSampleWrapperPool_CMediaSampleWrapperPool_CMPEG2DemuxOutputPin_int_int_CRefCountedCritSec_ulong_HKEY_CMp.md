# CMediaSampleWrapperPool::CMediaSampleWrapperPool(CMPEG2DemuxOutputPin *,int,int,CRefCountedCritSec *,ulong,HKEY__ *,CMpeg2Stats *,long *)

- ea: `0x1800a9838`
- end: `0x1800a9937`
- name: `??0CMediaSampleWrapperPool@@QEAA@PEAVCMPEG2DemuxOutputPin@@HHPEAVCRefCountedCritSec@@KPEAUHKEY__@@PEAVCMpeg2Stats@@PEAJ@Z`
- size: `255`
- prototype: `CMediaSampleWrapperPool *__fastcall(CMediaSampleWrapperPool *__hidden this, struct CMPEG2DemuxOutputPin *, int, int, struct CRefCountedCritSec *, unsigned int, HKEY, struct CMpeg2Stats *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b21c`

## callees

- `0x180043498`
- `0x1800a9838`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a98b4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a98b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a98eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a98eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9900`

## pseudocode

```c
CMediaSampleWrapperPool *__fastcall CMediaSampleWrapperPool::CMediaSampleWrapperPool(
        CMediaSampleWrapperPool *this,
        struct CMPEG2DemuxOutputPin *a2,
        int a3,
        int a4,
        struct CRefCountedCritSec *a5,
        unsigned int a6,
        HKEY a7,
        struct CMpeg2Stats *a8,
        int *a9)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v15; // ecx

  CBufferSource::CBufferSource(this, 0, a8, 1);
  *((_DWORD *)this + 12) = 0;
  *(_QWORD *)this = &CMediaSampleWrapperPool::`vftable';
  *((_DWORD *)this + 13) = a6;
  *((_QWORD *)this + 16) = a5;
  *((_QWORD *)this + 5) = (char *)this + 32;
  *((_QWORD *)this + 4) = (char *)this + 32;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = a2;
  *((_DWORD *)this + 30) = a3;
  *((_DWORD *)this + 31) = a4;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 16) + 40LL));
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 14) + 8LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 14)
                                                                                                 + 8LL));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 12) = EventW;
  if ( EventW )
  {
    v15 = 0;
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  *a9 = v15;
  return this;
}

```

## disassembly

```asm
0x1800a9838  push    rbx
0x1800a983a  push    rsi
0x1800a983b  push    rdi
0x1800a983c  push    r14
0x1800a983e  sub     rsp, 28h
0x1800a9842  mov     esi, r9d
0x1800a9845  mov     edi, r8d
0x1800a9848  mov     r8, [rsp+48h+arg_38]; struct CMpeg2Stats *
0x1800a9850  mov     rbx, rdx
0x1800a9853  mov     r9d, 1; int
0x1800a9859  xor     edx, edx; int
0x1800a985b  mov     r14, rcx
0x1800a985e  call    ??0CBufferSource@@QEAA@HPEAVCMpeg2Stats@@H@Z; CBufferSource::CBufferSource(int,CMpeg2Stats *,int)
0x1800a9863  lea     rax, ??_7CMediaSampleWrapperPool@@6B@; const CMediaSampleWrapperPool::`vftable'
0x1800a986a  mov     dword ptr [r14+30h], 0
0x1800a9872  mov     [r14], rax
0x1800a9875  lea     rcx, [r14+38h]; lpCriticalSection
0x1800a9879  mov     eax, [rsp+48h+arg_28]
0x1800a987d  mov     [r14+34h], eax
0x1800a9881  mov     rax, [rsp+48h+arg_20]
0x1800a9886  mov     [r14+80h], rax
0x1800a988d  lea     rax, [r14+20h]
0x1800a9891  mov     [r14+28h], rax
0x1800a9895  mov     [rax], rax
0x1800a9898  mov     qword ptr [r14+60h], 0
0x1800a98a0  mov     dword ptr [r14+68h], 0
0x1800a98a8  mov     [r14+70h], rbx
0x1800a98ac  mov     [r14+78h], edi
0x1800a98b0  mov     [r14+7Ch], esi
0x1800a98b4  call    cs:__imp_InitializeCriticalSection
0x1800a98bb  nop     dword ptr [rax+rax+00h]
0x1800a98c0  mov     rax, [r14+80h]
0x1800a98c7  lock inc dword ptr [rax+28h]
0x1800a98cb  mov     rax, [r14+70h]
0x1800a98cf  mov     rcx, [rax+8]
0x1800a98d3  mov     rax, [rcx]
0x1800a98d6  mov     rax, [rax+8]
0x1800a98da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98df  xor     r9d, r9d; lpName
0x1800a98e2  xor     r8d, r8d; bInitialState
0x1800a98e5  xor     ecx, ecx; lpEventAttributes
0x1800a98e7  lea     edx, [r9+1]; bManualReset
0x1800a98eb  call    cs:__imp_CreateEventW
0x1800a98f2  nop     dword ptr [rax+rax+00h]
0x1800a98f7  mov     [r14+60h], rax
0x1800a98fb  test    rax, rax
0x1800a98fe  jnz     short loc_1800A991D
0x1800a9900  call    cs:__imp_GetLastError
0x1800a9907  nop     dword ptr [rax+rax+00h]
0x1800a990c  mov     ecx, eax
0x1800a990e  test    eax, eax
0x1800a9910  jle     short loc_1800A991F
0x1800a9912  movzx   ecx, ax
0x1800a9915  or      ecx, 80070000h
0x1800a991b  jmp     short loc_1800A991F
0x1800a991d  xor     ecx, ecx
0x1800a991f  mov     rax, [rsp+48h+arg_40]
0x1800a9927  mov     [rax], ecx
0x1800a9929  mov     rax, r14
0x1800a992c  add     rsp, 28h
0x1800a9930  pop     r14
0x1800a9932  pop     rdi
0x1800a9933  pop     rsi
0x1800a9934  pop     rbx
0x1800a9935  retn
```
