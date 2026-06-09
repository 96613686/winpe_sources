# CMPEG2Demultiplexer::CMPEG2Demultiplexer(ushort const *,IUnknown *,_GUID const &,long *)

- ea: `0x180050be0`
- end: `0x180051146`
- name: `??0CMPEG2Demultiplexer@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z`
- size: `1382`
- prototype: `CMPEG2Demultiplexer *__usercall@<rax>(CMPEG2Demultiplexer *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, const struct _GUID *@<r9>, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180042380`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180016d40`
- `0x18002bcac`
- `0x18002d514`
- `0x18003d078`
- `0x18003fd1c`
- `0x1800470d4`
- `0x1800479a4`
- `0x180049a40`
- `0x18004b9fc`
- `0x18004c124`
- `0x180050be0`
- `0x180053f24`
- `0x180073d0c`
- `0x180074a06`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180050d26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180050e4a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180050d26`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180050e4a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005105c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005105c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050d0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050d0c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050fdd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050fdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180050f25`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180050f25`

## string_xrefs

- `0x18005103f`: `WriteCapture`
- `0x180051073`: `WriteCaptureDir`
- `0x180051097`: `WriteCapturePath`

## pseudocode

```c
CMPEG2Demultiplexer *__fastcall CMPEG2Demultiplexer::CMPEG2Demultiplexer(
        CMPEG2Demultiplexer *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        int *a5)
{
  CRefCountedCritSec *v7; // rax
  struct IUnknown *v8; // rdx
  int *v9; // r8
  CRefCountedCritSec *v10; // rax
  _QWORD *v11; // rcx
  CRefCountedCritSec *v12; // rax
  CRefCountedCritSec *v13; // rax
  GUID *v14; // rax
  __int64 v15; // rcx
  CMpeg2Stats *v16; // rax
  CMpeg2Stats *v17; // rax
  int v18; // ecx
  CDShowMPEG2Demux *v19; // rax
  CDShowMPEG2Demux *v20; // rax
  CBDAMPEG2Demux *v21; // rax
  CBDAMPEG2Demux *v22; // rax
  unsigned int v23; // r9d
  unsigned int v24; // r9d
  LARGE_INTEGER Frequency; // [rsp+50h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+48h] BYREF
  const unsigned __int16 *v28; // [rsp+B8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+58h] BYREF
  char v30; // [rsp+C8h] [rbp+60h] BYREF

  v28 = a2;
  v7 = (CRefCountedCritSec *)operator new(0x30u);
  if ( v7 )
    v10 = CRefCountedCritSec::CRefCountedCritSec(v7);
  else
    v10 = 0;
  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( !a3 )
    a3 = (struct IUnknown *)this;
  *((_QWORD *)this + 1) = a3;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 10) = v10;
  *((_QWORD *)this + 11) = 0;
  *((GUID *)this + 4) = CLSID_MFMPEG2Demultiplexer;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 1;
  CPersistStream::CPersistStream((CMPEG2Demultiplexer *)((char *)this + 120), v8, v9);
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 3) = &CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'};
  *(_QWORD *)this = &CMPEG2Demultiplexer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 4) = &CPsiParserFilter::`vftable'{for `IAMovieSetup'};
  *v11 = &CMPEG2Demultiplexer::`vftable'{for `CPersistStream'};
  *((_QWORD *)this + 17) = &CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 18) = &CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'};
  *((_QWORD *)this + 19) = &CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'};
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_DWORD *)this + 49) = 2;
  *((_DWORD *)this + 50) = 4;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 26) = GetProcessHeap();
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 358) = 0;
  *((_QWORD *)this + 180) = &CDShowESEventEx::`vftable';
  *((_DWORD *)this + 362) = 1;
  *((_DWORD *)this + 363) = 100;
  *((_QWORD *)this + 182) = 0;
  memset_0((char *)this + 1464, 0, 0x58u);
  *((_DWORD *)this + 376) = 1;
  *((_DWORD *)this + 374) = 1;
  memset_0((char *)this + 1552, 0, 0x58u);
  *((_DWORD *)this + 398) = 1;
  *((_DWORD *)this + 396) = 1;
  *((_QWORD *)this + 205) = 0;
  *((_DWORD *)this + 412) = 0;
  LODWORD(v28) = 0;
  Frequency.QuadPart = 0;
  hKey = 0;
  dwDisposition = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "CMPEG2Demultiplexer::CMPEG2Demultiplexer", 889);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 18, &WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids, this);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  *((_WORD *)this + 196) = 0;
  *((_WORD *)this + 456) = 0;
  v12 = (CRefCountedCritSec *)operator new(0x30u);
  if ( !v12 )
  {
    *((_QWORD *)this + 45) = 0;
    goto LABEL_41;
  }
  v13 = CRefCountedCritSec::CRefCountedCritSec(v12);
  *((_QWORD *)this + 45) = v13;
  if ( !v13 || !*((_QWORD *)this + 10) )
    goto LABEL_41;
  v14 = (GUID *)operator new(0x38u);
  if ( !v14 )
  {
    *((_QWORD *)this + 44) = 0;
    goto LABEL_41;
  }
  v15 = *((_QWORD *)this + 45);
  *(_QWORD *)&v14[1].Data1 = -1;
  *(_QWORD *)v14[1].Data4 = -1;
  *(_QWORD *)&v14[3].Data1 = 0x3FF0000000000000LL;
  *v14 = TIME_FORMAT_MEDIA_TIME;
  *(_QWORD *)&v14[2].Data1 = v15;
  *(_QWORD *)v14[2].Data4 = this;
  _InterlockedAdd((volatile signed __int32 *)(v15 + 40), 1u);
  *((_QWORD *)this + 44) = v14;
  v16 = (CMpeg2Stats *)operator new(0x2530u);
  if ( !v16 )
  {
    *((_QWORD *)this + 33) = 0;
    goto LABEL_41;
  }
  v17 = CMpeg2Stats::CMpeg2Stats(v16);
  *((_QWORD *)this + 33) = v17;
  if ( !v17 )
    goto LABEL_41;
  if ( !QueryPerformanceFrequency(&Frequency) )
  {
    v18 = -2147467259;
    goto LABEL_42;
  }
  v19 = (CDShowMPEG2Demux *)operator new(0x38u);
  if ( !v19 )
  {
    *((_QWORD *)this + 21) = 0;
    goto LABEL_41;
  }
  v20 = CDShowMPEG2Demux::CDShowMPEG2Demux(v19, this);
  *((_QWORD *)this + 21) = v20;
  if ( !v20 )
    goto LABEL_41;
  v21 = (CBDAMPEG2Demux *)operator new(0x58u);
  if ( !v21 )
  {
    *((_QWORD *)this + 22) = 0;
    goto LABEL_41;
  }
  v22 = CBDAMPEG2Demux::CBDAMPEG2Demux(v21, this);
  *((_QWORD *)this + 22) = v22;
  if ( !v22 )
  {
LABEL_41:
    v18 = -2147024882;
    goto LABEL_42;
  }
  *((_QWORD *)this + 48) = CreateBufferWriterEvent();
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          &dwDisposition) )
  {
    if ( !(unsigned int)RegGetValIfExist(hKey, L"StreamType", 0, 1, (unsigned int *)&v28) && (_DWORD)v28 )
      CMPEG2Demultiplexer::SetStreamType(this, (unsigned int)v28);
    if ( *((_QWORD *)this + 48)
      && !(unsigned int)RegGetValIfExist(hKey, L"WriteCapture", 0, 1, (unsigned int *)&v28)
      && (_DWORD)v28 )
    {
      SetEvent(*((HANDLE *)this + 48));
    }
    if ( (unsigned int)RegGetValIfExist(
                         hKey,
                         L"WriteCaptureDir",
                         L"c:\\dm.capture\\",
                         v23,
                         (unsigned __int16 *)this + 196) )
      *((_WORD *)this + 196) = 0;
    if ( (unsigned int)RegGetValIfExist(
                         hKey,
                         L"WriteCapturePath",
                         (unsigned __int16 *)&dword_1800D37B4,
                         v24,
                         (unsigned __int16 *)this + 456) )
      *((_WORD *)this + 456) = 0;
    if ( (unsigned int)RegGetValIfExist(hKey, L"TransportStatisticWindowSize", 0x64u, 0, (unsigned int *)this + 363) )
      *((_DWORD *)this + 363) = 100;
    RegCloseKey(hKey);
  }
  v18 = CMPEG2Demultiplexer::Reset_(this);
LABEL_42:
  *a5 = v18;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  return this;
}

```

## disassembly

```asm
0x180050be0  mov     [rsp-40h+arg_8], rdx
0x180050be5  push    rbp
0x180050be6  push    rbx
0x180050be7  push    rsi
0x180050be8  push    rdi
0x180050be9  push    r12
0x180050beb  push    r13
0x180050bed  push    r14
0x180050bef  push    r15
0x180050bf1  mov     rbp, rsp
0x180050bf4  sub     rsp, 68h
0x180050bf8  mov     rdi, rcx
0x180050bfb  mov     r13d, 30h ; '0'
0x180050c01  mov     ecx, r13d; Size
0x180050c04  mov     rbx, r8
0x180050c07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050c0c  xor     r15d, r15d
0x180050c0f  test    rax, rax
0x180050c12  jz      short loc_180050C1E
0x180050c14  mov     rcx, rax; this
0x180050c17  call    ??0CRefCountedCritSec@@QEAA@XZ; CRefCountedCritSec::CRefCountedCritSec(void)
0x180050c1c  jmp     short loc_180050C21
0x180050c1e  mov     rax, r15
0x180050c21  mov     r12d, 1
0x180050c27  lock add cs:?m_cObjects@CBaseObject@@0JA, r12d; long CBaseObject::m_cObjects
0x180050c2f  mov     [rdi+28h], r15d
0x180050c33  lea     rcx, [rdi+78h]; this
0x180050c37  mov     [rdi+30h], r15
0x180050c3b  test    rbx, rbx
0x180050c3e  cmovz   rbx, rdi
0x180050c42  mov     [rdi+8], rbx
0x180050c46  mov     [rdi+10h], r15d
0x180050c4a  mov     [rdi+38h], r15
0x180050c4e  movups  xmm0, xmmword ptr cs:CLSID_MFMPEG2Demultiplexer.Data1
0x180050c55  mov     [rdi+50h], rax
0x180050c59  mov     [rdi+58h], r15
0x180050c5d  movdqu  xmmword ptr [rdi+40h], xmm0
0x180050c62  mov     [rdi+60h], r15
0x180050c66  mov     [rdi+68h], r15
0x180050c6a  mov     [rdi+70h], r12d
0x180050c6e  call    ??0CPersistStream@@QEAA@PEAUIUnknown@@PEAJ@Z; CPersistStream::CPersistStream(IUnknown *,long *)
0x180050c73  mov     [rdi+0A0h], r15
0x180050c7a  lea     rax, ??_7CMPEG2Demultiplexer@@6BIBaseFilter@@@; const CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'}
0x180050c81  mov     [rdi+18h], rax
0x180050c85  lea     rdx, ??_7CMPEG2Demultiplexer@@6BCUnknown@@@; const CMPEG2Demultiplexer::`vftable'{for `CUnknown'}
0x180050c8c  mov     [rdi], rdx
0x180050c8f  lea     rax, ??_7CPsiParserFilter@@6BIAMovieSetup@@@; const CPsiParserFilter::`vftable'{for `IAMovieSetup'}
0x180050c96  mov     [rdi+20h], rax
0x180050c9a  lea     rax, ??_7CMPEG2Demultiplexer@@6BCPersistStream@@@; const CMPEG2Demultiplexer::`vftable'{for `CPersistStream'}
0x180050ca1  mov     [rcx], rax
0x180050ca4  lea     rax, ??_7CMPEG2Demultiplexer@@6BIAMFilterMiscFlags@@@; const CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'}
0x180050cab  mov     [rdi+88h], rax
0x180050cb2  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIInputStreamEvent@@@; const CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'}
0x180050cb9  mov     [rdi+90h], rax
0x180050cc0  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIProgramInfo@@@; const CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'}
0x180050cc7  mov     [rdi+98h], rax
0x180050cce  mov     [rdi+0A8h], r15
0x180050cd5  mov     [rdi+0B0h], r15
0x180050cdc  mov     [rdi+0B8h], r15
0x180050ce3  mov     [rdi+0C0h], r15d
0x180050cea  mov     dword ptr [rdi+0C4h], 2
0x180050cf4  mov     dword ptr [rdi+0C8h], 4
0x180050cfe  mov     [rdi+0D0h], r15
0x180050d05  mov     [rdi+0D8h], r15d
0x180050d0c  call    cs:__imp_GetProcessHeap
0x180050d13  nop     dword ptr [rax+rax+00h]
0x180050d18  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180050d1f  mov     [rdi+0D0h], rax
0x180050d26  call    cs:__imp_InitializeCriticalSection
0x180050d2d  nop     dword ptr [rax+rax+00h]
0x180050d32  lea     rax, ??_7CDShowESEventEx@@6B@; const CDShowESEventEx::`vftable'
0x180050d39  mov     [rdi+108h], r15
0x180050d40  mov     [rdi+110h], r15
0x180050d47  lea     rbx, [rdi+5B8h]
0x180050d4e  mov     [rdi+118h], r15
0x180050d55  lea     esi, [r12+57h]
0x180050d5a  mov     [rdi+120h], r15
0x180050d61  lea     r14, [rdi+5ACh]
0x180050d68  mov     [rdi+128h], r15d
0x180050d6f  mov     r8d, esi; Size
0x180050d72  mov     [rdi+158h], r15
0x180050d79  xor     edx, edx; Val
0x180050d7b  mov     [rdi+160h], r15
0x180050d82  mov     rcx, rbx; void *
0x180050d85  mov     [rdi+168h], r15
0x180050d8c  mov     [rdi+178h], r15
0x180050d93  mov     [rdi+180h], r15
0x180050d9a  mov     [rdi+598h], r15d
0x180050da1  mov     [rdi+5A0h], rax
0x180050da8  mov     [rdi+5A8h], r12d
0x180050daf  mov     dword ptr [r14], 64h ; 'd'
0x180050db6  mov     [rdi+5B0h], r15
0x180050dbd  call    memset_0
0x180050dc2  mov     [rbx+28h], r12d
0x180050dc6  mov     r8d, esi; Size
0x180050dc9  mov     [rbx+20h], r12d
0x180050dcd  xor     edx, edx; Val
0x180050dcf  lea     rbx, [rdi+610h]
0x180050dd6  mov     rcx, rbx; void *
0x180050dd9  call    memset_0
0x180050dde  mov     [rbx+28h], r12d
0x180050de2  mov     [rbx+20h], r12d
0x180050de6  mov     [rdi+668h], r15
0x180050ded  mov     [rdi+670h], r15d
0x180050df4  mov     dword ptr [rbp+arg_8], r15d
0x180050df8  mov     qword ptr [rbp+Frequency], r15
0x180050dfc  mov     [rbp+hKey], r15
0x180050e00  mov     [rbp+dwDisposition], r15d
0x180050e04  mov     r8d, 379h; int
0x180050e0a  lea     rdx, aCmpeg2demultip_56; "CMPEG2Demultiplexer::CMPEG2Demultiplexe"...
0x180050e11  lea     rcx, [rbp+arg_18]; this
0x180050e15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180050e1a  cmp     cs:byte_1800EACCB, 8
0x180050e21  jb      short loc_180050E43
0x180050e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180050e2a  lea     edx, [rsi-46h]
0x180050e2d  mov     r9, rdi
0x180050e30  lea     r8, WPP_a94830b6bd5f3023efd6e0bdea57da03_Traceguids
0x180050e37  mov     rcx, [rcx+88h]
0x180050e3e  call    WPP_SF_q
0x180050e43  lea     rcx, [rdi+130h]; lpCriticalSection
0x180050e4a  call    cs:__imp_InitializeCriticalSection
0x180050e51  nop     dword ptr [rax+rax+00h]
0x180050e56  lea     rbx, [rdi+188h]
0x180050e5d  mov     rcx, r13; Size
0x180050e60  lea     rsi, [rdi+390h]
0x180050e67  mov     [rbx], r15w
0x180050e6b  mov     [rsi], r15w
0x180050e6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050e74  test    rax, rax
0x180050e77  jz      loc_180051116
0x180050e7d  mov     rcx, rax; this
0x180050e80  call    ??0CRefCountedCritSec@@QEAA@XZ; CRefCountedCritSec::CRefCountedCritSec(void)
0x180050e85  mov     [rdi+168h], rax
0x180050e8c  test    rax, rax
0x180050e8f  jz      loc_18005111D
0x180050e95  cmp     [rdi+50h], r15
0x180050e99  jz      loc_18005111D
0x180050e9f  mov     r13d, 38h ; '8'
0x180050ea5  mov     ecx, r13d; Size
0x180050ea8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050ead  test    rax, rax
0x180050eb0  jz      loc_18005110D
0x180050eb6  mov     rcx, [rdi+168h]
0x180050ebd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180050ec1  movups  xmm0, xmmword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180050ec8  mov     [rax+10h], rdx
0x180050ecc  mov     [rax+18h], rdx
0x180050ed0  mov     rdx, 3FF0000000000000h
0x180050eda  mov     [rax+30h], rdx
0x180050ede  movdqu  xmmword ptr [rax], xmm0
0x180050ee2  mov     [rax+20h], rcx
0x180050ee6  mov     [rax+28h], rdi
0x180050eea  lock add [rcx+28h], r12d
0x180050eef  mov     ecx, 2530h; Size
0x180050ef4  mov     [rdi+160h], rax
0x180050efb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050f00  test    rax, rax
0x180050f03  jz      loc_180051104
0x180050f09  mov     rcx, rax; this
0x180050f0c  call    ??0CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::CMpeg2Stats(void)
0x180050f11  mov     [rdi+108h], rax
0x180050f18  test    rax, rax
0x180050f1b  jz      loc_18005111D
0x180050f21  lea     rcx, [rbp+Frequency]; lpFrequency
0x180050f25  call    cs:__imp_QueryPerformanceFrequency
0x180050f2c  nop     dword ptr [rax+rax+00h]
0x180050f31  test    eax, eax
0x180050f33  jnz     short loc_180050F3F
0x180050f35  mov     ecx, 80004005h
0x180050f3a  jmp     loc_180051122
0x180050f3f  mov     rcx, r13; Size
0x180050f42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050f47  test    rax, rax
0x180050f4a  jz      loc_1800510FB
0x180050f50  mov     rdx, rdi; struct CMPEG2Demultiplexer *
0x180050f53  mov     rcx, rax; this
0x180050f56  call    ??0CDShowMPEG2Demux@@QEAA@PEAVCMPEG2Demultiplexer@@@Z; CDShowMPEG2Demux::CDShowMPEG2Demux(CMPEG2Demultiplexer *)
0x180050f5b  mov     [rdi+0A8h], rax
0x180050f62  test    rax, rax
0x180050f65  jz      loc_18005111D
0x180050f6b  mov     ecx, 58h ; 'X'; Size
0x180050f70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050f75  test    rax, rax
0x180050f78  jz      loc_1800510F2
0x180050f7e  mov     rdx, rdi; struct CMPEG2Demultiplexer *
0x180050f81  mov     rcx, rax; this
0x180050f84  call    ??0CBDAMPEG2Demux@@QEAA@PEAVCMPEG2Demultiplexer@@@Z; CBDAMPEG2Demux::CBDAMPEG2Demux(CMPEG2Demultiplexer *)
0x180050f89  mov     [rdi+0B0h], rax
0x180050f90  test    rax, rax
0x180050f93  jz      loc_18005111D
0x180050f99  call    CreateBufferWriterEvent
0x180050f9e  mov     [rdi+180h], rax
0x180050fa5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"
0x180050fac  lea     rax, [rbp+dwDisposition]
0x180050fb0  xor     r9d, r9d; lpClass
0x180050fb3  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180050fb8  xor     r8d, r8d; Reserved
0x180050fbb  lea     rax, [rbp+hKey]
0x180050fbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180050fc6  mov     [rsp+68h+phkResult], rax; phkResult
0x180050fcb  mov     [rsp+68h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180050fd0  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180050fd8  mov     [rsp+68h+dwOptions], r15d; dwOptions
0x180050fdd  call    cs:__imp_RegCreateKeyExW
0x180050fe4  nop     dword ptr [rax+rax+00h]
0x180050fe9  test    eax, eax
0x180050feb  jnz     loc_1800510E6
0x180050ff1  mov     rcx, [rbp+hKey]; hKey
0x180050ff5  lea     rax, [rbp+arg_8]
0x180050ff9  mov     r9d, r12d; int
0x180050ffc  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int *
0x180051001  xor     r8d, r8d; unsigned int
0x180051004  lea     rdx, aStreamtype; "StreamType"
0x18005100b  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180051010  test    eax, eax
0x180051012  jnz     short loc_180051023
0x180051014  mov     edx, dword ptr [rbp+arg_8]; unsigned int
0x180051017  test    edx, edx
0x180051019  jz      short loc_180051023
0x18005101b  mov     rcx, rdi; this
0x18005101e  call    ?SetStreamType@CMPEG2Demultiplexer@@QEAAJK@Z; CMPEG2Demultiplexer::SetStreamType(ulong)
0x180051023  cmp     [rdi+180h], r15
0x18005102a  jz      short loc_180051068
0x18005102c  mov     rcx, [rbp+hKey]; hKey
0x180051030  lea     rax, [rbp+arg_8]
0x180051034  mov     r9d, r12d; int
0x180051037  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int *
0x18005103c  xor     r8d, r8d; unsigned int
0x18005103f  lea     rdx, aWritecapture; "WriteCapture"
0x180051046  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x18005104b  test    eax, eax
0x18005104d  jnz     short loc_180051068
0x18005104f  cmp     dword ptr [rbp+arg_8], r15d
0x180051053  jz      short loc_180051068
0x180051055  mov     rcx, [rdi+180h]; hEvent
0x18005105c  call    cs:__imp_SetEvent
0x180051063  nop     dword ptr [rax+rax+00h]
0x180051068  mov     rcx, [rbp+hKey]; hKey
0x18005106c  lea     r8, aCDmCapture; "c:\\dm.capture\\"
0x180051073  lea     rdx, aWritecapturedi; "WriteCaptureDir"
0x18005107a  mov     qword ptr [rsp+68h+dwOptions], rbx; unsigned __int16 *
0x18005107f  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEAG1K1@Z; RegGetValIfExist(HKEY__ *,ushort *,ushort *,ulong,ushort *)
0x180051084  test    eax, eax
0x180051086  jz      short loc_18005108C
0x180051088  mov     [rbx], r15w
0x18005108c  mov     rcx, [rbp+hKey]; hKey
0x180051090  lea     r8, dword_1800D37B4; unsigned __int16 *
0x180051097  lea     rdx, aWritecapturepa; "WriteCapturePath"
0x18005109e  mov     qword ptr [rsp+68h+dwOptions], rsi; unsigned __int16 *
0x1800510a3  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEAG1K1@Z; RegGetValIfExist(HKEY__ *,ushort *,ushort *,ulong,ushort *)
0x1800510a8  test    eax, eax
0x1800510aa  jz      short loc_1800510B0
0x1800510ac  mov     [rsi], r15w
0x1800510b0  mov     rcx, [rbp+hKey]; hKey
0x1800510b4  lea     rdx, aTransportstati; "TransportStatisticWindowSize"
0x1800510bb  xor     r9d, r9d; int
0x1800510be  mov     qword ptr [rsp+68h+dwOptions], r14; unsigned int *
0x1800510c3  lea     ebx, [r9+64h]
0x1800510c7  mov     r8d, ebx; unsigned int
0x1800510ca  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x1800510cf  test    eax, eax
0x1800510d1  jz      short loc_1800510D6
0x1800510d3  mov     [r14], ebx
0x1800510d6  mov     rcx, [rbp+hKey]; hKey
0x1800510da  call    cs:__imp_RegCloseKey
0x1800510e1  nop     dword ptr [rax+rax+00h]
0x1800510e6  mov     rcx, rdi; this
0x1800510e9  call    ?Reset_@CMPEG2Demultiplexer@@AEAAJXZ; CMPEG2Demultiplexer::Reset_(void)
0x1800510ee  mov     ecx, eax
0x1800510f0  jmp     short loc_180051122
0x1800510f2  mov     [rdi+0B0h], r15
0x1800510f9  jmp     short loc_18005111D
0x1800510fb  mov     [rdi+0A8h], r15
0x180051102  jmp     short loc_18005111D
0x180051104  mov     [rdi+108h], r15
0x18005110b  jmp     short loc_18005111D
0x18005110d  mov     [rdi+160h], r15
0x180051114  jmp     short loc_18005111D
0x180051116  mov     [rdi+168h], r15
0x18005111d  mov     ecx, 8007000Eh
0x180051122  mov     rax, [rbp+arg_20]
0x180051126  mov     [rax], ecx
0x180051128  lea     rcx, [rbp+arg_18]; this
0x18005112c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180051131  mov     rax, rdi
0x180051134  add     rsp, 68h
0x180051138  pop     r15
0x18005113a  pop     r14
0x18005113c  pop     r13
0x18005113e  pop     r12
0x180051140  pop     rdi
0x180051141  pop     rsi
0x180051142  pop     rbx
0x180051143  pop     rbp
0x180051144  retn
```
