# CMpeg2PESStreamParser::CMpeg2PESStreamParser(CBufferSource *,CIPTSConvert *,CMpeg2StreamContentManager *,ulong,CMPEG2DemuxOutputPin *,CMpeg2Stats *,AUDIO_FILTER_INFO *,HKEY__ *,int,long *)

- ea: `0x18004abac`
- end: `0x18004af28`
- name: `??0CMpeg2PESStreamParser@@QEAA@PEAVCBufferSource@@PEAVCIPTSConvert@@PEAVCMpeg2StreamContentManager@@KPEAVCMPEG2DemuxOutputPin@@PEAVCMpeg2Stats@@PEAUAUDIO_FILTER_INFO@@PEAUHKEY__@@HPEAJ@Z`
- size: `892`
- prototype: `CMpeg2PESStreamParser *__fastcall(CMpeg2PESStreamParser *this, struct CBufferSource *, struct CIPTSConvert *, struct CMpeg2StreamContentManager *, DWORD cbData, __int64 Type, struct CMpeg2Stats *lpData, struct AUDIO_FILTER_INFO *, HKEY hKey, unsigned int Data, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001aa48`
- `0x1800a7fb8`
- `0x1800ac308`

## callees

- `0x180002820`
- `0x180004fd8`
- `0x18000b8c0`
- `0x18004abac`
- `0x1800551e8`
- `0x180076738`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ae19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aeb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ae19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aeb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ade4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ae79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ade4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ae79`

## pseudocode

```c
CMpeg2PESStreamParser *__fastcall CMpeg2PESStreamParser::CMpeg2PESStreamParser(
        CMpeg2PESStreamParser *this,
        struct CBufferSource *a2,
        struct CIPTSConvert *a3,
        struct CMpeg2StreamContentManager *a4,
        DWORD cbData,
        __int64 Type,
        struct CMpeg2Stats *lpData,
        struct AUDIO_FILTER_INFO *a8,
        HKEY hKey,
        unsigned int Data,
        int *a11)
{
  struct CMpeg2Stats *v11; // rbx
  struct AUDIO_FILTER_INFO *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v19; // r9d
  HKEY v20; // rbx
  unsigned int v21; // eax
  int v22; // edi
  __int64 v23; // rcx
  unsigned int v24; // eax

  v11 = lpData;
  CStreamParser::CStreamParser(this, (unsigned int)a2, a2, lpData, 0x10000);
  *((_QWORD *)this + 67) = v11;
  *((_DWORD *)this + 123) = 0;
  *(_QWORD *)this = &CMpeg2PESStreamParser::`vftable'{for `CDemuxBaseParser'};
  *((_DWORD *)this + 128) = 0;
  *((_QWORD *)this + 6) = &CMpeg1PESStreamParser::`vftable'{for `CBufferSourceManager'};
  *((_QWORD *)this + 68) = a3;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 74) = 0x10000000;
  *((_DWORD *)this + 151) = *((_DWORD *)a2 + 3);
  *((_DWORD *)this + 162) = Data;
  *((_DWORD *)this + 167) = cbData;
  *((_QWORD *)this + 84) = Type;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_DWORD *)this + 166) = 0;
  *((_BYTE *)this + 680) = 0;
  *((_QWORD *)this + 86) = a4;
  *((_QWORD *)this + 87) = (char *)this + 720;
  *((_QWORD *)this + 88) = (char *)this + 720;
  *((_QWORD *)this + 89) = 219;
  *((_DWORD *)this + 236) = 1;
  LODWORD(lpData) = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&Data,
    "CMpeg2PESStreamParser::CMpeg2PESStreamParser",
    1745);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      64,
      &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
      this,
      *((_DWORD *)this + 167),
      *((_DWORD *)this + 151));
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 67) + 32LL));
  v16 = a8;
  *((_OWORD *)this + 31) = 0;
  *(_OWORD *)((char *)this + 516) = 0;
  if ( v16 )
  {
    if ( *((_DWORD *)v16 + 1) > 0xAu || (v17 = *(_DWORD *)v16, (*(_DWORD *)v16 & 0xFFFFFF00) != 0) && v17 != 0x10000000 )
    {
      v18 = -2147024809;
      goto LABEL_23;
    }
    *((_DWORD *)this + 148) = v17;
    v19 = *((_DWORD *)v16 + 1);
    *((_DWORD *)this + 149) = v19;
    if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        65,
        &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
        this,
        v19,
        v17);
  }
  v20 = hKey;
  v21 = 0;
  Data = 0;
  LODWORD(lpData) = 0;
  v22 = 1000;
  if ( hKey )
  {
    cbData = 4;
    LODWORD(Type) = 4;
    if ( RegQueryValueExW(hKey, L"AudioPTSOffsetMs", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) )
    {
      RegSetValueExW(v20, L"AudioPTSOffsetMs", 0, 4u, (const BYTE *)&lpData, 4u);
      v21 = (unsigned int)lpData;
    }
    else
    {
      v21 = Data;
    }
    if ( v21 >= 0x3E8 )
      v21 = 1000;
  }
  v23 = 10000 * v21;
  v24 = 0;
  Data = 0;
  LODWORD(lpData) = 0;
  *((_QWORD *)this + 77) = v23;
  if ( !v20
    || ((cbData = 4,
         LODWORD(Type) = 4,
         RegQueryValueExW(v20, L"VideoPTSOffsetMs", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData))
      ? (RegSetValueExW(v20, L"VideoPTSOffsetMs", 0, 4u, (const BYTE *)&lpData, 4u), v24 = (unsigned int)lpData)
      : (v24 = Data, LODWORD(lpData) = Data),
        v24 < 0x3E8) )
  {
    v22 = v24;
  }
  *((_QWORD *)this + 79) = (unsigned int)(10000 * v22);
  CMpeg2PESStreamParser::ResetAndWaitForNextPESPacket_(this);
  v18 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, char *))this + 68))(
          *((_QWORD *)this + 68),
          *((unsigned int *)this + 167),
          (char *)this + 552);
  *((_QWORD *)this + 73) = 0;
LABEL_23:
  *a11 = v18;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Data);
  return this;
}

```

## disassembly

```asm
0x18004abac  push    rbp
0x18004abae  push    rbx
0x18004abaf  push    rsi
0x18004abb0  push    rdi
0x18004abb1  push    r12
0x18004abb3  push    r13
0x18004abb5  push    r14
0x18004abb7  push    r15
0x18004abb9  mov     rbp, rsp
0x18004abbc  sub     rsp, 38h
0x18004abc0  mov     rbx, [rbp+arg_30]
0x18004abc4  mov     r14, r9
0x18004abc7  mov     rdi, r8
0x18004abca  mov     dword ptr [rsp+38h+lpData], 10000h; int
0x18004abd2  mov     r9, rbx; struct CMpeg2Stats *
0x18004abd5  mov     r8, rdx; struct CBufferSource *
0x18004abd8  mov     rsi, rdx
0x18004abdb  mov     r15, rcx
0x18004abde  call    ??0CStreamParser@@QEAA@KPEAVCBufferSource@@PEAVCMpeg2Stats@@H@Z; CStreamParser::CStreamParser(ulong,CBufferSource *,CMpeg2Stats *,int)
0x18004abe3  xor     r13d, r13d
0x18004abe6  mov     [r15+218h], rbx
0x18004abed  mov     [r15+1ECh], r13d
0x18004abf4  lea     rax, ??_7CMpeg2PESStreamParser@@6BCDemuxBaseParser@@@; const CMpeg2PESStreamParser::`vftable'{for `CDemuxBaseParser'}
0x18004abfb  mov     [r15], rax
0x18004abfe  lea     r12, [r15+228h]
0x18004ac05  mov     [r15+200h], r13d
0x18004ac0c  lea     rax, ??_7CMpeg1PESStreamParser@@6BCBufferSourceManager@@@; const CMpeg1PESStreamParser::`vftable'{for `CBufferSourceManager'}
0x18004ac13  mov     [r15+30h], rax
0x18004ac17  lea     rdx, aCmpeg2pesstrea_0; "CMpeg2PESStreamParser::CMpeg2PESStreamP"...
0x18004ac1e  mov     [r15+220h], rdi
0x18004ac25  lea     rcx, [rbp+Data]; this
0x18004ac2c  mov     [r12], r13
0x18004ac30  mov     ebx, 10000000h
0x18004ac35  mov     [r15+250h], rbx
0x18004ac3c  mov     r8d, 6D1h; int
0x18004ac42  mov     eax, [rsi+0Ch]
0x18004ac45  mov     [r15+25Ch], eax
0x18004ac4c  mov     eax, dword ptr [rbp+Data]
0x18004ac52  mov     [r15+288h], eax
0x18004ac59  mov     eax, [rbp+cbData]
0x18004ac5c  mov     [r15+29Ch], eax
0x18004ac63  mov     rax, [rbp+Type]
0x18004ac67  mov     [r15+2A0h], rax
0x18004ac6e  lea     rax, [r15+2D0h]
0x18004ac75  mov     [r15+280h], r13
0x18004ac7c  mov     [r15+290h], r13
0x18004ac83  mov     [r15+298h], r13d
0x18004ac8a  mov     [r15+2A8h], r13b
0x18004ac91  mov     [r15+2B0h], r14
0x18004ac98  mov     [r15+2B8h], rax
0x18004ac9f  mov     [r15+2C0h], rax
0x18004aca6  mov     qword ptr [r15+2C8h], 0DBh
0x18004acb1  mov     dword ptr [r15+3B0h], 1
0x18004acbc  mov     dword ptr [rbp+arg_30], r13d
0x18004acc0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004acc5  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18004accc  jb      short loc_18004AD05
0x18004acce  mov     eax, [r15+25Ch]
0x18004acd5  lea     edx, [r13+40h]
0x18004acd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ace0  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18004ace7  mov     dword ptr [rsp+38h+lpcbData], eax
0x18004aceb  mov     r9, r15
0x18004acee  mov     eax, [r15+29Ch]
0x18004acf5  mov     dword ptr [rsp+38h+lpData], eax
0x18004acf9  mov     rcx, [rcx+88h]
0x18004ad00  call    WPP_SF_qDD
0x18004ad05  mov     rax, [r15+218h]
0x18004ad0c  lock inc dword ptr [rax+20h]
0x18004ad10  mov     rcx, [rbp+arg_38]
0x18004ad17  xorps   xmm0, xmm0
0x18004ad1a  xorps   xmm1, xmm1
0x18004ad1d  movups  xmmword ptr [r15+1F0h], xmm0
0x18004ad25  movups  xmmword ptr [r15+204h], xmm1
0x18004ad2d  test    rcx, rcx
0x18004ad30  jz      short loc_18004AD95
0x18004ad32  cmp     dword ptr [rcx+4], 0Ah
0x18004ad36  ja      short loc_18004AD45
0x18004ad38  mov     eax, [rcx]
0x18004ad3a  test    eax, 0FFFFFF00h
0x18004ad3f  jz      short loc_18004AD4F
0x18004ad41  cmp     eax, ebx
0x18004ad43  jz      short loc_18004AD4F
0x18004ad45  mov     eax, 80070057h
0x18004ad4a  jmp     loc_18004AEFE
0x18004ad4f  mov     [r15+250h], eax
0x18004ad56  mov     r9d, [rcx+4]
0x18004ad5a  mov     [r15+254h], r9d
0x18004ad61  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18004ad68  jb      short loc_18004AD95
0x18004ad6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad71  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18004ad78  mov     dword ptr [rsp+38h+lpcbData], eax
0x18004ad7c  mov     edx, 41h ; 'A'
0x18004ad81  mov     dword ptr [rsp+38h+lpData], r9d
0x18004ad86  mov     r9, r15
0x18004ad89  mov     rcx, [rcx+88h]
0x18004ad90  call    WPP_SF_qDD
0x18004ad95  mov     rbx, [rbp+hKey]
0x18004ad9c  mov     eax, r13d
0x18004ad9f  mov     dword ptr [rbp+Data], r13d
0x18004ada6  mov     esi, 4
0x18004adab  mov     dword ptr [rbp+arg_30], eax
0x18004adae  mov     edi, 3E8h
0x18004adb3  test    rbx, rbx
0x18004adb6  jz      short loc_18004AE2E
0x18004adb8  lea     rax, [rbp+cbData]
0x18004adbc  mov     [rbp+cbData], esi
0x18004adbf  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004adc4  lea     r9, [rbp+Type]; lpType
0x18004adc8  lea     rax, [rbp+Data]
0x18004adcf  mov     dword ptr [rbp+Type], esi
0x18004add2  xor     r8d, r8d; lpReserved
0x18004add5  mov     [rsp+38h+lpData], rax; lpData
0x18004adda  lea     rdx, aAudioptsoffset; "AudioPTSOffsetMs"
0x18004ade1  mov     rcx, rbx; hKey
0x18004ade4  call    cs:__imp_RegQueryValueExW
0x18004adeb  nop     dword ptr [rax+rax+00h]
0x18004adf0  test    eax, eax
0x18004adf2  jnz     short loc_18004ADFC
0x18004adf4  mov     eax, dword ptr [rbp+Data]
0x18004adfa  jmp     short loc_18004AE28
0x18004adfc  lea     rax, [rbp+arg_30]
0x18004ae00  mov     dword ptr [rsp+38h+lpcbData], esi; cbData
0x18004ae04  mov     r9d, esi; dwType
0x18004ae07  mov     [rsp+38h+lpData], rax; lpData
0x18004ae0c  xor     r8d, r8d; Reserved
0x18004ae0f  lea     rdx, aAudioptsoffset; "AudioPTSOffsetMs"
0x18004ae16  mov     rcx, rbx; hKey
0x18004ae19  call    cs:__imp_RegSetValueExW
0x18004ae20  nop     dword ptr [rax+rax+00h]
0x18004ae25  mov     eax, dword ptr [rbp+arg_30]
0x18004ae28  cmp     eax, edi
0x18004ae2a  jb      short loc_18004AE2E
0x18004ae2c  mov     eax, edi
0x18004ae2e  imul    ecx, eax, 2710h
0x18004ae34  mov     eax, r13d
0x18004ae37  mov     dword ptr [rbp+Data], r13d
0x18004ae3e  mov     dword ptr [rbp+arg_30], eax
0x18004ae41  mov     [r15+268h], rcx
0x18004ae48  test    rbx, rbx
0x18004ae4b  jz      short loc_18004AEC4
0x18004ae4d  lea     rax, [rbp+cbData]
0x18004ae51  mov     [rbp+cbData], esi
0x18004ae54  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18004ae59  lea     r9, [rbp+Type]; lpType
0x18004ae5d  lea     rax, [rbp+Data]
0x18004ae64  mov     dword ptr [rbp+Type], esi
0x18004ae67  xor     r8d, r8d; lpReserved
0x18004ae6a  mov     [rsp+38h+lpData], rax; lpData
0x18004ae6f  lea     rdx, aVideoptsoffset; "VideoPTSOffsetMs"
0x18004ae76  mov     rcx, rbx; hKey
0x18004ae79  call    cs:__imp_RegQueryValueExW
0x18004ae80  nop     dword ptr [rax+rax+00h]
0x18004ae85  test    eax, eax
0x18004ae87  jnz     short loc_18004AE94
0x18004ae89  mov     eax, dword ptr [rbp+Data]
0x18004ae8f  mov     dword ptr [rbp+arg_30], eax
0x18004ae92  jmp     short loc_18004AEC0
0x18004ae94  lea     rax, [rbp+arg_30]
0x18004ae98  mov     dword ptr [rsp+38h+lpcbData], esi; cbData
0x18004ae9c  mov     r9d, esi; dwType
0x18004ae9f  mov     [rsp+38h+lpData], rax; lpData
0x18004aea4  xor     r8d, r8d; Reserved
0x18004aea7  lea     rdx, aVideoptsoffset; "VideoPTSOffsetMs"
0x18004aeae  mov     rcx, rbx; hKey
0x18004aeb1  call    cs:__imp_RegSetValueExW
0x18004aeb8  nop     dword ptr [rax+rax+00h]
0x18004aebd  mov     eax, dword ptr [rbp+arg_30]
0x18004aec0  cmp     eax, edi
0x18004aec2  jnb     short loc_18004AEC6
0x18004aec4  mov     edi, eax
0x18004aec6  imul    ecx, edi, 2710h
0x18004aecc  mov     [r15+278h], rcx
0x18004aed3  mov     rcx, r15; this
0x18004aed6  call    ?ResetAndWaitForNextPESPacket_@CMpeg2PESStreamParser@@IEAAXXZ; CMpeg2PESStreamParser::ResetAndWaitForNextPESPacket_(void)
0x18004aedb  mov     rcx, [r15+220h]
0x18004aee2  mov     r8, r12
0x18004aee5  mov     edx, [r15+29Ch]
0x18004aeec  mov     rax, [rcx]
0x18004aeef  mov     rax, [rax]
0x18004aef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aef7  mov     [r15+248h], r13
0x18004aefe  mov     rcx, [rbp+arg_50]
0x18004af05  mov     [rcx], eax
0x18004af07  lea     rcx, [rbp+Data]; this
0x18004af0e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004af13  mov     rax, r15
0x18004af16  add     rsp, 38h
0x18004af1a  pop     r15
0x18004af1c  pop     r14
0x18004af1e  pop     r13
0x18004af20  pop     r12
0x18004af22  pop     rdi
0x18004af23  pop     rsi
0x18004af24  pop     rbx
0x18004af25  pop     rbp
0x18004af26  retn
```
