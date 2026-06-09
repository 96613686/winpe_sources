# CMPEG2Demultiplexer::CMPEG2Demultiplexer(ushort const *,IUnknown *,_GUID const &,long *)

- ea: `0x180012acc`
- end: `0x180013061`
- name: `??0CMPEG2Demultiplexer@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z`
- size: `1429`
- prototype: `CMPEG2Demultiplexer *__usercall@<rax>(CMPEG2Demultiplexer *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, const struct _GUID *@<r9>, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180013ea0`
- `0x180013f20`

## callees

- `0x180001008`
- `0x1800103c8`
- `0x180012acc`
- `0x180013a58`
- `0x1800176e8`
- `0x1800197f8`
- `0x18001991c`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180012bfa`
- `KERNEL32!GetProcessHeap` at `0x180012bfa`
- `KERNEL32!QueryPerformanceFrequency` at `0x180012db5`
- `KERNEL32!QueryPerformanceFrequency` at `0x180012db5`
- `KERNEL32!SetEvent` at `0x180012f4b`
- `KERNEL32!SetEvent` at `0x180012f4b`
- `KERNEL32!InitializeCriticalSection` at `0x180012b0b`
- `KERNEL32!InitializeCriticalSection` at `0x180012c0e`
- `KERNEL32!InitializeCriticalSection` at `0x180012c64`
- `KERNEL32!InitializeCriticalSection` at `0x180012cb7`
- `KERNEL32!InitializeCriticalSection` at `0x180012cec`
- `KERNEL32!InitializeCriticalSection` at `0x180012b0b`
- `KERNEL32!InitializeCriticalSection` at `0x180012c0e`
- `KERNEL32!InitializeCriticalSection` at `0x180012c64`
- `KERNEL32!InitializeCriticalSection` at `0x180012cb7`
- `KERNEL32!InitializeCriticalSection` at `0x180012cec`
- `ADVAPI32!RegCloseKey` at `0x180012fc4`
- `ADVAPI32!RegCloseKey` at `0x180012fc4`
- `ADVAPI32!RegCreateKeyExW` at `0x180012ed2`
- `ADVAPI32!RegCreateKeyExW` at `0x180012ed2`

## string_xrefs

- `0x180012f2e`: `WriteCapture`
- `0x180012f5c`: `WriteCaptureDir`
- `0x180012f80`: `WriteCapturePath`

## pseudocode

```c
CMPEG2Demultiplexer *__fastcall CMPEG2Demultiplexer::CMPEG2Demultiplexer(
        CMPEG2Demultiplexer *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        int *a5)
{
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int128 v10; // xmm0
  struct _RTL_CRITICAL_SECTION *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  GUID *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  int v17; // ecx
  _QWORD *v18; // rax
  char *v19; // rax
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  _DWORD *v22; // rbx
  int v23; // ecx
  DWORD dwDisposition; // [rsp+A0h] [rbp+48h] BYREF
  const unsigned __int16 *v26; // [rsp+A8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+58h] BYREF
  LARGE_INTEGER Frequency; // [rsp+B8h] [rbp+60h] BYREF

  v26 = a2;
  v8 = (struct _RTL_CRITICAL_SECTION *)operator new(0x30u);
  v9 = v8;
  if ( v8 )
  {
    InitializeCriticalSection(v8);
    LODWORD(v9[1].DebugInfo) = 1;
  }
  else
  {
    v9 = 0;
  }
  _InterlockedAdd(&CBaseObject::m_cObjects, 1u);
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( !a3 )
    a3 = (struct IUnknown *)this;
  *((_QWORD *)this + 1) = a3;
  *((_DWORD *)this + 4) = 0;
  v10 = (__int128)*a4;
  *(_QWORD *)this = &CMPEG2Demultiplexer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 10) = v9;
  *((_OWORD *)this + 4) = v10;
  *((_QWORD *)this + 3) = &CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CBaseSplitterFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 15) = &CMPEG2Demultiplexer::`vftable'{for `CPersistStream'};
  *((_QWORD *)this + 17) = &CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'};
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 18) = &CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'};
  *((_QWORD *)this + 19) = &CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'};
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 1;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_DWORD *)this + 49) = 2;
  *((_DWORD *)this + 50) = 4;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 26) = GetProcessHeap();
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 356) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 36);
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 179) = &CDShowESEventEx::`vftable';
  *((_QWORD *)this + 186) = 0;
  *((_DWORD *)this + 374) = 1;
  *((_DWORD *)this + 375) = 100;
  *((_QWORD *)this + 188) = 0;
  LODWORD(v26) = 0;
  Frequency.QuadPart = 0;
  hKey = 0;
  dwDisposition = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  *((_WORD *)this + 192) = 0;
  *((_WORD *)this + 452) = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)operator new(0x30u);
  v12 = v11;
  if ( !v11 )
  {
    *((_QWORD *)this + 44) = 0;
    goto LABEL_43;
  }
  InitializeCriticalSection(v11);
  LODWORD(v12[1].DebugInfo) = 1;
  *((_QWORD *)this + 44) = v12;
  if ( !*((_QWORD *)this + 10) )
  {
LABEL_43:
    v17 = -2147024882;
    goto LABEL_44;
  }
  v13 = (GUID *)operator new(0x38u);
  if ( !v13 )
  {
    *((_QWORD *)this + 43) = 0;
    goto LABEL_43;
  }
  v14 = *((_QWORD *)this + 44);
  *(_QWORD *)&v13[1].Data1 = -1;
  *(_QWORD *)v13[1].Data4 = -1;
  *(_QWORD *)&v13[3].Data1 = 0x3FF0000000000000LL;
  *v13 = TIME_FORMAT_MEDIA_TIME;
  *(_QWORD *)&v13[2].Data1 = v14;
  *(_QWORD *)v13[2].Data4 = this;
  _InterlockedIncrement((volatile signed __int32 *)(v14 + 40));
  *((_QWORD *)this + 43) = v13;
  v15 = operator new(0x2530u);
  v16 = v15;
  if ( !v15 )
  {
    *((_QWORD *)this + 33) = 0;
    goto LABEL_43;
  }
  *v15 = 0;
  v15[1] = 0;
  v15[2] = 0;
  v15[3] = 0;
  v15[4] = 0;
  *((_DWORD *)v15 + 10) = 1;
  v15[6] = 0;
  v15[1031] = 0;
  Mpeg2DemuxTrace::CeHomeETWDemultiplexer::CeHomeETWDemultiplexer((Mpeg2DemuxTrace::CeHomeETWDemultiplexer *)(v15 + 1032));
  v16[1189] = 0;
  *((_QWORD *)this + 33) = v16;
  if ( !QueryPerformanceFrequency(&Frequency) )
  {
    v17 = -2147467259;
    goto LABEL_44;
  }
  v18 = operator new(0x28u);
  if ( !v18 )
  {
    *((_QWORD *)this + 21) = 0;
    goto LABEL_43;
  }
  v18[3] = this;
  *v18 = &CDShowMPEG2Demux::`vftable'{for `IMpeg2Demultiplexer'};
  *((_DWORD *)v18 + 8) = 1;
  v18[1] = &CDShowMPEG2Demux::`vftable'{for `ISpecifyPropertyPages'};
  v18[2] = &CDShowMPEG2Demux::`vftable'{for `IMpeg2DemultiplexerTesting'};
  *((_QWORD *)this + 21) = v18;
  v19 = (char *)operator new(0x58u);
  if ( !v19 )
  {
    *((_QWORD *)this + 22) = 0;
    goto LABEL_43;
  }
  *((_QWORD *)v19 + 3) = this;
  *(_QWORD *)v19 = &CBDAMPEG2Demux::`vftable'{for `IBDA_DeviceControl'};
  *((_QWORD *)v19 + 1) = &CBDAMPEG2Demux::`vftable'{for `IBDA_SignalProperties'};
  *((_QWORD *)v19 + 2) = &CBDAMPEG2Demux::`vftable'{for `IBDA_Topology'};
  *((_DWORD *)v19 + 12) = 0;
  *((GUID *)v19 + 2) = GUID_00000000_0000_0000_0000_000000000000;
  *(_QWORD *)(v19 + 68) = 1;
  *((_QWORD *)v19 + 10) = 0;
  *(GUID *)(v19 + 52) = GUID_00000000_0000_0000_0000_000000000000;
  *((_QWORD *)this + 22) = v19;
  *((_QWORD *)this + 47) = CreateBufferWriterEvent();
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&CLSID_MPEG2Demultiplexer_NoClock.Data1
    && *(_QWORD *)a4->Data4 == *(_QWORD *)CLSID_MPEG2Demultiplexer_NoClock.Data4 )
  {
    *((_DWORD *)this + 73) = 1;
  }
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
    if ( !(unsigned int)RegGetValIfExist(hKey, L"StreamType", 0, 1, (unsigned int *)&v26) && (_DWORD)v26 )
      CMPEG2Demultiplexer::SetStreamType(this, (unsigned int)v26);
    if ( *((_QWORD *)this + 47)
      && !(unsigned int)RegGetValIfExist(hKey, L"WriteCapture", 0, 1, (unsigned int *)&v26)
      && (_DWORD)v26 )
    {
      SetEvent(*((HANDLE *)this + 47));
    }
    if ( (unsigned int)RegGetValIfExist(
                         hKey,
                         L"WriteCaptureDir",
                         (BYTE *)L"c:\\dm.capture\\",
                         v20,
                         (unsigned __int16 *)this + 192) )
      *((_WORD *)this + 192) = 0;
    if ( (unsigned int)RegGetValIfExist(
                         hKey,
                         L"WriteCapturePath",
                         (BYTE *)&qword_18003A0A0,
                         v21,
                         (unsigned __int16 *)this + 452) )
      *((_WORD *)this + 452) = 0;
    if ( (unsigned int)RegGetValIfExist(hKey, L"TransportStatisticWindowSize", 0x64u, 0, (unsigned int *)this + 375) )
      *((_DWORD *)this + 375) = 100;
    RegCloseKey(hKey);
  }
  v22 = (_DWORD *)*((_QWORD *)this + 42);
  if ( v22 && (v23 = v22[32]) != 0 && (unsigned int)(v23 - 1) <= 1 )
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 48LL))(*((_QWORD *)this + 42));
    if ( v17 >= 0 )
      v17 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v22 + 56LL))(v22);
  }
  else
  {
    v17 = 0;
  }
LABEL_44:
  *a5 = v17;
  return this;
}

```

## disassembly

```asm
0x180012acc  mov     [rsp-40h+arg_8], rdx
0x180012ad1  push    rbp
0x180012ad2  push    rbx
0x180012ad3  push    rsi
0x180012ad4  push    rdi
0x180012ad5  push    r12
0x180012ad7  push    r13
0x180012ad9  push    r14
0x180012adb  push    r15
0x180012add  mov     rbp, rsp
0x180012ae0  sub     rsp, 58h
0x180012ae4  mov     rdi, rcx
0x180012ae7  mov     rsi, r9
0x180012aea  mov     ecx, 30h ; '0'; Size
0x180012aef  mov     r14, r8
0x180012af2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012af7  xor     r13d, r13d
0x180012afa  mov     rbx, rax
0x180012afd  mov     r15d, 1
0x180012b03  test    rax, rax
0x180012b06  jz      short loc_180012B17
0x180012b08  mov     rcx, rax; lpCriticalSection
0x180012b0b  call    cs:__imp_InitializeCriticalSection
0x180012b11  mov     [rbx+28h], r15d
0x180012b15  jmp     short loc_180012B1A
0x180012b17  mov     rbx, r13
0x180012b1a  lock add cs:?m_cObjects@CBaseObject@@0JA, r15d; long CBaseObject::m_cObjects
0x180012b22  mov     [rdi+38h], r13
0x180012b26  lea     rax, ??_7CMPEG2Demultiplexer@@6BCUnknown@@@; const CMPEG2Demultiplexer::`vftable'{for `CUnknown'}
0x180012b2d  mov     [rdi+28h], r13d
0x180012b31  test    r14, r14
0x180012b34  mov     [rdi+30h], r13
0x180012b38  cmovz   r14, rdi
0x180012b3c  mov     [rdi+8], r14
0x180012b40  mov     [rdi+10h], r13d
0x180012b44  movups  xmm0, xmmword ptr [rsi]
0x180012b47  mov     [rdi], rax
0x180012b4a  lea     rax, ??_7CMPEG2Demultiplexer@@6BIBaseFilter@@@; const CMPEG2Demultiplexer::`vftable'{for `IBaseFilter'}
0x180012b51  mov     [rdi+50h], rbx
0x180012b55  movdqu  xmmword ptr [rdi+40h], xmm0
0x180012b5a  mov     [rdi+18h], rax
0x180012b5e  lea     rax, ??_7CBaseSplitterFilter@@6BIAMovieSetup@@@; const CBaseSplitterFilter::`vftable'{for `IAMovieSetup'}
0x180012b65  mov     [rdi+20h], rax
0x180012b69  lea     rax, ??_7CMPEG2Demultiplexer@@6BCPersistStream@@@; const CMPEG2Demultiplexer::`vftable'{for `CPersistStream'}
0x180012b70  mov     [rdi+78h], rax
0x180012b74  lea     rax, ??_7CMPEG2Demultiplexer@@6BIAMFilterMiscFlags@@@; const CMPEG2Demultiplexer::`vftable'{for `IAMFilterMiscFlags'}
0x180012b7b  mov     [rdi+88h], rax
0x180012b82  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIInputStreamEvent@@@; const CMPEG2Demultiplexer::`vftable'{for `CIInputStreamEvent'}
0x180012b89  mov     [rdi+80h], r13
0x180012b90  mov     [rdi+0A8h], r13
0x180012b97  mov     [rdi+0B0h], r13
0x180012b9e  mov     [rdi+90h], rax
0x180012ba5  lea     rax, ??_7CMPEG2Demultiplexer@@6BCIProgramInfo@@@; const CMPEG2Demultiplexer::`vftable'{for `CIProgramInfo'}
0x180012bac  mov     [rdi+98h], rax
0x180012bb3  mov     [rdi+58h], r13
0x180012bb7  mov     [rdi+60h], r13
0x180012bbb  mov     [rdi+68h], r13
0x180012bbf  mov     [rdi+70h], r15d
0x180012bc3  mov     [rdi+0A0h], r13
0x180012bca  mov     [rdi+0D0h], r13
0x180012bd1  mov     [rdi+0B8h], r13
0x180012bd8  mov     [rdi+0C0h], r13d
0x180012bdf  mov     dword ptr [rdi+0C4h], 2
0x180012be9  mov     dword ptr [rdi+0C8h], 4
0x180012bf3  mov     [rdi+0D8h], r13d
0x180012bfa  call    cs:__imp_GetProcessHeap
0x180012c00  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180012c07  mov     [rdi+0D0h], rax
0x180012c0e  call    cs:__imp_InitializeCriticalSection
0x180012c14  lea     rbx, [rdi+5A0h]
0x180012c1b  mov     [rdi+108h], r13
0x180012c22  mov     rcx, rbx; lpCriticalSection
0x180012c25  mov     [rdi+110h], r13
0x180012c2c  mov     [rdi+118h], r13
0x180012c33  mov     [rdi+120h], r13
0x180012c3a  mov     [rdi+150h], r13
0x180012c41  mov     [rdi+158h], r13
0x180012c48  mov     [rdi+160h], r13
0x180012c4f  mov     [rdi+170h], r13
0x180012c56  mov     [rdi+178h], r13
0x180012c5d  mov     [rdi+590h], r13d
0x180012c64  call    cs:__imp_InitializeCriticalSection
0x180012c6a  mov     [rbx+28h], r13
0x180012c6e  lea     rax, ??_7CDShowESEventEx@@6B@; const CDShowESEventEx::`vftable'
0x180012c75  mov     [rdi+598h], rax
0x180012c7c  lea     r12, [rdi+5DCh]
0x180012c83  mov     [rdi+5D0h], r13
0x180012c8a  lea     rcx, [rdi+128h]; lpCriticalSection
0x180012c91  mov     [rdi+5D8h], r15d
0x180012c98  mov     dword ptr [r12], 64h ; 'd'
0x180012ca0  mov     [rdi+5E0h], r13
0x180012ca7  mov     dword ptr [rbp+arg_8], r13d
0x180012cab  mov     qword ptr [rbp+Frequency], r13
0x180012caf  mov     [rbp+hKey], r13
0x180012cb3  mov     [rbp+dwDisposition], r13d
0x180012cb7  call    cs:__imp_InitializeCriticalSection
0x180012cbd  lea     r14, [rdi+180h]
0x180012cc4  mov     ecx, 30h ; '0'; Size
0x180012cc9  lea     r15, [rdi+388h]
0x180012cd0  mov     [r14], r13w
0x180012cd4  mov     [r15], r13w
0x180012cd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012cdd  mov     rbx, rax
0x180012ce0  test    rax, rax
0x180012ce3  jz      loc_18001303B
0x180012ce9  mov     rcx, rax; lpCriticalSection
0x180012cec  call    cs:__imp_InitializeCriticalSection
0x180012cf2  mov     dword ptr [rbx+28h], 1
0x180012cf9  mov     [rdi+160h], rbx
0x180012d00  cmp     [rdi+50h], r13
0x180012d04  jz      loc_180013042
0x180012d0a  mov     ecx, 38h ; '8'; Size
0x180012d0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012d14  test    rax, rax
0x180012d17  jz      loc_180013032
0x180012d1d  mov     rcx, [rdi+160h]
0x180012d24  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012d28  movups  xmm0, xmmword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180012d2f  mov     [rax+10h], rdx
0x180012d33  mov     [rax+18h], rdx
0x180012d37  mov     rdx, 3FF0000000000000h
0x180012d41  mov     [rax+30h], rdx
0x180012d45  movdqu  xmmword ptr [rax], xmm0
0x180012d49  mov     [rax+20h], rcx
0x180012d4d  mov     [rax+28h], rdi
0x180012d51  lock inc dword ptr [rcx+28h]
0x180012d55  mov     ecx, 2530h; Size
0x180012d5a  mov     [rdi+158h], rax
0x180012d61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012d66  mov     rbx, rax
0x180012d69  test    rax, rax
0x180012d6c  jz      loc_180013029
0x180012d72  lea     rcx, [rax+2040h]; this
0x180012d79  mov     [rax], r13
0x180012d7c  mov     [rax+8], r13
0x180012d80  mov     [rax+10h], r13
0x180012d84  mov     [rax+18h], r13
0x180012d88  mov     [rax+20h], r13
0x180012d8c  mov     dword ptr [rax+28h], 1
0x180012d93  mov     [rax+30h], r13
0x180012d97  mov     [rax+2038h], r13
0x180012d9e  call    ??0CeHomeETWDemultiplexer@Mpeg2DemuxTrace@@QEAA@XZ; Mpeg2DemuxTrace::CeHomeETWDemultiplexer::CeHomeETWDemultiplexer(void)
0x180012da3  mov     [rbx+2528h], r13
0x180012daa  lea     rcx, [rbp+Frequency]; lpFrequency
0x180012dae  mov     [rdi+108h], rbx
0x180012db5  call    cs:__imp_QueryPerformanceFrequency
0x180012dbb  test    eax, eax
0x180012dbd  jnz     short loc_180012DC9
0x180012dbf  mov     ecx, 80004005h
0x180012dc4  jmp     loc_180013047
0x180012dc9  mov     ecx, 28h ; '('; Size
0x180012dce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012dd3  test    rax, rax
0x180012dd6  jz      loc_180013020
0x180012ddc  lea     rcx, ??_7CDShowMPEG2Demux@@6BIMpeg2Demultiplexer@@@; const CDShowMPEG2Demux::`vftable'{for `IMpeg2Demultiplexer'}
0x180012de3  mov     [rax+18h], rdi
0x180012de7  mov     [rax], rcx
0x180012dea  mov     ebx, 1
0x180012def  lea     rcx, ??_7CDShowMPEG2Demux@@6BISpecifyPropertyPages@@@; const CDShowMPEG2Demux::`vftable'{for `ISpecifyPropertyPages'}
0x180012df6  mov     [rax+20h], ebx
0x180012df9  mov     [rax+8], rcx
0x180012dfd  lea     rcx, ??_7CDShowMPEG2Demux@@6BIMpeg2DemultiplexerTesting@@@; const CDShowMPEG2Demux::`vftable'{for `IMpeg2DemultiplexerTesting'}
0x180012e04  mov     [rax+10h], rcx
0x180012e08  lea     ecx, [rbx+57h]; Size
0x180012e0b  mov     [rdi+0A8h], rax
0x180012e12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012e17  test    rax, rax
0x180012e1a  jz      loc_180013017
0x180012e20  mov     [rax+18h], rdi
0x180012e24  lea     rcx, ??_7CBDAMPEG2Demux@@6BIBDA_DeviceControl@@@; const CBDAMPEG2Demux::`vftable'{for `IBDA_DeviceControl'}
0x180012e2b  mov     [rax], rcx
0x180012e2e  lea     rcx, ??_7CBDAMPEG2Demux@@6BIBDA_SignalProperties@@@; const CBDAMPEG2Demux::`vftable'{for `IBDA_SignalProperties'}
0x180012e35  mov     [rax+8], rcx
0x180012e39  lea     rcx, ??_7CBDAMPEG2Demux@@6BIBDA_Topology@@@; const CBDAMPEG2Demux::`vftable'{for `IBDA_Topology'}
0x180012e40  mov     [rax+10h], rcx
0x180012e44  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180012e4b  mov     [rax+30h], r13d
0x180012e4f  movdqu  xmmword ptr [rax+20h], xmm0
0x180012e54  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180012e5b  mov     [rax+44h], rbx
0x180012e5f  mov     [rax+50h], r13
0x180012e63  movdqu  xmmword ptr [rax+34h], xmm1
0x180012e68  mov     [rdi+0B0h], rax
0x180012e6f  call    CreateBufferWriterEvent
0x180012e74  mov     [rdi+178h], rax
0x180012e7b  mov     rax, [rsi]
0x180012e7e  cmp     rax, qword ptr cs:CLSID_MPEG2Demultiplexer_NoClock.Data1
0x180012e85  jnz     short loc_180012E9A
0x180012e87  mov     rax, [rsi+8]
0x180012e8b  cmp     rax, qword ptr cs:CLSID_MPEG2Demultiplexer_NoClock.Data4
0x180012e92  jnz     short loc_180012E9A
0x180012e94  mov     [rdi+124h], ebx
0x180012e9a  lea     rax, [rbp+dwDisposition]
0x180012e9e  xor     r9d, r9d; lpClass
0x180012ea1  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180012ea6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"
0x180012ead  lea     rax, [rbp+hKey]
0x180012eb1  xor     r8d, r8d; Reserved
0x180012eb4  mov     [rsp+58h+phkResult], rax; phkResult
0x180012eb9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180012ec0  mov     [rsp+58h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180012ec5  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180012ecd  mov     [rsp+58h+dwOptions], r13d; dwOptions
0x180012ed2  call    cs:__imp_RegCreateKeyExW
0x180012ed8  test    eax, eax
0x180012eda  jnz     loc_180012FCA
0x180012ee0  mov     rcx, [rbp+hKey]; hKey
0x180012ee4  lea     rax, [rbp+arg_8]
0x180012ee8  mov     r9d, ebx; int
0x180012eeb  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int *
0x180012ef0  xor     r8d, r8d; unsigned int
0x180012ef3  lea     rdx, aStreamtype; "StreamType"
0x180012efa  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180012eff  test    eax, eax
0x180012f01  jnz     short loc_180012F12
0x180012f03  mov     edx, dword ptr [rbp+arg_8]; unsigned int
0x180012f06  test    edx, edx
0x180012f08  jz      short loc_180012F12
0x180012f0a  mov     rcx, rdi; this
0x180012f0d  call    ?SetStreamType@CMPEG2Demultiplexer@@QEAAJK@Z; CMPEG2Demultiplexer::SetStreamType(ulong)
0x180012f12  cmp     [rdi+178h], r13
0x180012f19  jz      short loc_180012F51
0x180012f1b  mov     rcx, [rbp+hKey]; hKey
0x180012f1f  lea     rax, [rbp+arg_8]
0x180012f23  mov     r9d, ebx; int
0x180012f26  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int *
0x180012f2b  xor     r8d, r8d; unsigned int
0x180012f2e  lea     rdx, aWritecapture; "WriteCapture"
0x180012f35  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180012f3a  test    eax, eax
0x180012f3c  jnz     short loc_180012F51
0x180012f3e  cmp     dword ptr [rbp+arg_8], r13d
0x180012f42  jz      short loc_180012F51
0x180012f44  mov     rcx, [rdi+178h]; hEvent
0x180012f4b  call    cs:__imp_SetEvent
0x180012f51  mov     rcx, [rbp+hKey]; hKey
0x180012f55  lea     r8, Data; "c:\\dm.capture\\"
0x180012f5c  lea     rdx, aWritecapturedi; "WriteCaptureDir"
0x180012f63  mov     qword ptr [rsp+58h+dwOptions], r14; unsigned __int16 *
0x180012f68  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEAG1K1@Z; RegGetValIfExist(HKEY__ *,ushort *,ushort *,ulong,ushort *)
0x180012f6d  test    eax, eax
0x180012f6f  jz      short loc_180012F75
0x180012f71  mov     [r14], r13w
0x180012f75  mov     rcx, [rbp+hKey]; hKey
0x180012f79  lea     r8, qword_18003A0A0; lpData
0x180012f80  lea     rdx, aWritecapturepa; "WriteCapturePath"
0x180012f87  mov     qword ptr [rsp+58h+dwOptions], r15; unsigned __int16 *
0x180012f8c  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEAG1K1@Z; RegGetValIfExist(HKEY__ *,ushort *,ushort *,ulong,ushort *)
0x180012f91  test    eax, eax
0x180012f93  jz      short loc_180012F99
0x180012f95  mov     [r15], r13w
0x180012f99  mov     rcx, [rbp+hKey]; hKey
0x180012f9d  lea     rdx, aTransportstati; "TransportStatisticWindowSize"
0x180012fa4  xor     r9d, r9d; int
0x180012fa7  mov     qword ptr [rsp+58h+dwOptions], r12; unsigned int *
0x180012fac  lea     ebx, [r9+64h]
0x180012fb0  mov     r8d, ebx; unsigned int
0x180012fb3  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180012fb8  test    eax, eax
0x180012fba  jz      short loc_180012FC0
0x180012fbc  mov     [r12], ebx
0x180012fc0  mov     rcx, [rbp+hKey]; hKey
0x180012fc4  call    cs:__imp_RegCloseKey
0x180012fca  mov     rbx, [rdi+150h]
0x180012fd1  test    rbx, rbx
0x180012fd4  jz      short loc_180013012
0x180012fd6  mov     ecx, [rbx+80h]
0x180012fdc  test    ecx, ecx
0x180012fde  jz      short loc_180013012
0x180012fe0  sub     ecx, 1
0x180012fe3  jz      short loc_180012FEA
0x180012fe5  cmp     ecx, 1
0x180012fe8  jnz     short loc_180013012
0x180012fea  mov     rax, [rbx]
0x180012fed  mov     rcx, rbx
0x180012ff0  mov     rax, [rax+30h]
0x180012ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff9  mov     ecx, eax
0x180012ffb  test    eax, eax
0x180012ffd  js      short loc_180013047
0x180012fff  mov     rax, [rbx]
0x180013002  mov     rcx, rbx
0x180013005  mov     rax, [rax+38h]
0x180013009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001300e  mov     ecx, eax
0x180013010  jmp     short loc_180013047
0x180013012  mov     ecx, r13d
0x180013015  jmp     short loc_180013047
0x180013017  mov     [rdi+0B0h], r13
0x18001301e  jmp     short loc_180013042
0x180013020  mov     [rdi+0A8h], r13
0x180013027  jmp     short loc_180013042
0x180013029  mov     [rdi+108h], r13
0x180013030  jmp     short loc_180013042
0x180013032  mov     [rdi+158h], r13
0x180013039  jmp     short loc_180013042
0x18001303b  mov     [rdi+160h], r13
0x180013042  mov     ecx, 8007000Eh
0x180013047  mov     rax, [rbp+arg_20]
0x18001304b  mov     [rax], ecx
  ... truncated ...
```
