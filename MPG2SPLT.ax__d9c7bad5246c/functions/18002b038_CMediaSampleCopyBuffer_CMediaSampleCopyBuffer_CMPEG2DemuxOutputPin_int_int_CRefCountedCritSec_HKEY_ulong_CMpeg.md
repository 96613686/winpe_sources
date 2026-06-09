# CMediaSampleCopyBuffer::CMediaSampleCopyBuffer(CMPEG2DemuxOutputPin *,int,int,CRefCountedCritSec *,HKEY__ *,ulong,CMpeg2Stats *)

- ea: `0x18002b038`
- end: `0x18002b178`
- name: `??0CMediaSampleCopyBuffer@@QEAA@PEAVCMPEG2DemuxOutputPin@@HHPEAVCRefCountedCritSec@@PEAUHKEY__@@KPEAVCMpeg2Stats@@@Z`
- size: `320`
- prototype: `CMediaSampleCopyBuffer *__fastcall(CMediaSampleCopyBuffer *__hidden this, struct CMPEG2DemuxOutputPin *, int, int, struct CRefCountedCritSec *, HKEY, unsigned int, struct CMpeg2Stats *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020a34`

## callees

- `0x180001460`
- `0x180001e98`
- `0x180006b18`
- `0x18002b038`
- `0x180033df1`
- `0x180034010`

## pseudocode

```c
CMediaSampleCopyBuffer *__fastcall CMediaSampleCopyBuffer::CMediaSampleCopyBuffer(
        CMediaSampleCopyBuffer *this,
        struct CMPEG2DemuxOutputPin *a2,
        int a3,
        int a4,
        struct CRefCountedCritSec *a5,
        HKEY a6,
        unsigned int a7,
        struct CMpeg2Stats *a8)
{
  __int64 v9; // rax
  struct _AMMediaType Buf1; // [rsp+20h] [rbp-78h] BYREF

  *(_QWORD *)this = &CBufferSource::`vftable';
  *((_QWORD *)this + 2) = a8;
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 3) = 1;
  *((_DWORD *)this + 6) = 1;
  _InterlockedAdd((volatile signed __int32 *)a8 + 10, 1u);
  *((_QWORD *)this + 4) = a2;
  *(_QWORD *)this = &CMediaSampleCopyBuffer::`vftable';
  *((_QWORD *)this + 6) = a5;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 10) = a3;
  *((_QWORD *)this + 10) = a7;
  *((_DWORD *)this + 11) = a4;
  *((_QWORD *)this + 7) = 0;
  memset_0(&Buf1, 0, sizeof(Buf1));
  v9 = *((_QWORD *)this + 6);
  Buf1.lSampleSize = 1;
  Buf1.bFixedSizeSamples = 1;
  _InterlockedAdd((volatile signed __int32 *)(v9 + 40), 1u);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 4) + 24LL) + 8LL))(*((_QWORD *)this + 4) + 24LL);
  memset_0(&Buf1, 0, sizeof(Buf1));
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *))(**((_QWORD **)this + 4) + 104LL))(
         *((_QWORD *)this + 4),
         0,
         &Buf1) >= 0 )
    *((_DWORD *)this + 21) = memcmp_0(&Buf1, &GUID_455f176c_4b06_47ce_9aef_8caef73df7b5, 0x10u) == 0;
  FreeMediaType(&Buf1);
  return this;
}

```

## disassembly

```asm
0x18002b038  mov     [rsp+arg_8], rbx
0x18002b03d  push    rsi
0x18002b03e  sub     rsp, 90h
0x18002b045  mov     rax, cs:__security_cookie
0x18002b04c  xor     rax, rsp
0x18002b04f  mov     [rsp+98h+var_18], rax
0x18002b057  mov     esi, 1
0x18002b05c  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002b063  mov     [rcx], rax
0x18002b066  mov     rbx, rcx
0x18002b069  mov     rax, [rsp+98h+arg_38]
0x18002b071  mov     [rcx+10h], rax
0x18002b075  mov     [rcx+8], esi
0x18002b078  mov     [rcx+0Ch], esi
0x18002b07b  mov     [rcx+18h], esi
0x18002b07e  lock add [rax+28h], esi
0x18002b082  mov     [rcx+20h], rdx
0x18002b086  lea     rax, ??_7CMediaSampleCopyBuffer@@6B@; const CMediaSampleCopyBuffer::`vftable'
0x18002b08d  mov     [rcx], rax
0x18002b090  xor     edx, edx; Val
0x18002b092  mov     rax, [rsp+98h+arg_20]
0x18002b09a  mov     [rcx+30h], rax
0x18002b09e  mov     eax, [rsp+98h+arg_30]
0x18002b0a5  mov     qword ptr [rcx+40h], 0
0x18002b0ad  mov     dword ptr [rcx+48h], 0
0x18002b0b4  mov     [rcx+28h], r8d
0x18002b0b8  lea     r8d, [rsi+57h]; Size
0x18002b0bc  mov     [rcx+50h], eax
0x18002b0bf  mov     dword ptr [rcx+54h], 0
0x18002b0c6  mov     [rcx+2Ch], r9d
0x18002b0ca  mov     qword ptr [rcx+38h], 0
0x18002b0d2  lea     rcx, [rsp+98h+Buf1]; void *
0x18002b0d7  call    memset_0
0x18002b0dc  mov     rax, [rbx+30h]
0x18002b0e0  mov     [rsp+98h+var_50], esi
0x18002b0e4  mov     [rsp+98h+var_58], esi
0x18002b0e8  lock add [rax+28h], esi
0x18002b0ec  mov     rcx, [rbx+20h]
0x18002b0f0  add     rcx, 18h
0x18002b0f4  mov     rax, [rcx]
0x18002b0f7  mov     rax, [rax+8]
0x18002b0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b100  xor     edx, edx; Val
0x18002b102  lea     r8d, [rsi+57h]; Size
0x18002b106  lea     rcx, [rsp+98h+Buf1]; void *
0x18002b10b  call    memset_0
0x18002b110  mov     rcx, [rbx+20h]
0x18002b114  lea     r8, [rsp+98h+Buf1]
0x18002b119  xor     edx, edx
0x18002b11b  mov     rax, [rcx]
0x18002b11e  mov     rax, [rax+68h]
0x18002b122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b127  test    eax, eax
0x18002b129  js      short loc_18002B14A
0x18002b12b  lea     r8d, [rsi+0Fh]; Size
0x18002b12f  lea     rdx, _GUID_455f176c_4b06_47ce_9aef_8caef73df7b5; Buf2
0x18002b136  lea     rcx, [rsp+98h+Buf1]; Buf1
0x18002b13b  call    memcmp_0
0x18002b140  xor     ecx, ecx
0x18002b142  test    eax, eax
0x18002b144  setz    cl
0x18002b147  mov     [rbx+54h], ecx
0x18002b14a  lea     rcx, [rsp+98h+Buf1]; struct _AMMediaType *
0x18002b14f  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18002b154  mov     rax, rbx
0x18002b157  mov     rcx, [rsp+98h+var_18]
0x18002b15f  xor     rcx, rsp; StackCookie
0x18002b162  call    __security_check_cookie
0x18002b167  mov     rbx, [rsp+98h+arg_8]
0x18002b16f  add     rsp, 90h
0x18002b176  pop     rsi
0x18002b177  retn
```
