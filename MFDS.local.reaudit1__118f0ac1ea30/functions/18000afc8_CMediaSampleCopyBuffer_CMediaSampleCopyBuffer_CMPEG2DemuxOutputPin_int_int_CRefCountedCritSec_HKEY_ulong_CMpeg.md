# CMediaSampleCopyBuffer::CMediaSampleCopyBuffer(CMPEG2DemuxOutputPin *,int,int,CRefCountedCritSec *,HKEY__ *,ulong,CMpeg2Stats *)

- ea: `0x18000afc8`
- end: `0x18000b215`
- name: `??0CMediaSampleCopyBuffer@@QEAA@PEAVCMPEG2DemuxOutputPin@@HHPEAVCRefCountedCritSec@@PEAUHKEY__@@KPEAVCMpeg2Stats@@@Z`
- size: `589`
- prototype: `CMediaSampleCopyBuffer *__fastcall(CMediaSampleCopyBuffer *__hidden this, struct CMPEG2DemuxOutputPin *, int, int, struct CRefCountedCritSec *, HKEY, unsigned int, struct CMpeg2Stats *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b21c`

## callees

- `0x180002820`
- `0x18000afc8`
- `0x18000b8c0`
- `0x180010350`
- `0x180023738`
- `0x18002d514`
- `0x18004c0d0`
- `0x180074160`
- `0x180074a06`
- `0x1800a4118`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b136`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b1e2`

## string_xrefs

- `0x18000b0be`: `CMediaSampleCopyBuffer::CMediaSampleCopyBuffer`

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
  __int64 v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  _BYTE v15[16]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v16[32]; // [rsp+40h] [rbp-59h] BYREF
  int v17; // [rsp+60h] [rbp-39h]
  int v18; // [rsp+68h] [rbp-31h]
  int v19; // [rsp+88h] [rbp-11h]
  LPVOID pv; // [rsp+90h] [rbp-9h]

  *(_QWORD *)this = &CBufferSource::`vftable';
  *((_QWORD *)this + 2) = a8;
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 3) = 1;
  *((_DWORD *)this + 6) = 1;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v15, "CBufferSource::CBufferSource", 75);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_99d91d446fe635ade03b8ca4e19bb98c_Traceguids, this);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 32LL), 1u);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v15);
  *((_DWORD *)this + 10) = a3;
  *(_QWORD *)this = &CMediaSampleCopyBuffer::`vftable';
  *((_QWORD *)this + 6) = a5;
  *((_DWORD *)this + 11) = a4;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = a7;
  memset_0(v16, 0, 0x58u);
  v18 = 1;
  v17 = 1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v15,
    "CMediaSampleCopyBuffer::CMediaSampleCopyBuffer",
    43);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, a2);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 6) + 40LL), 1u);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 4) + 8LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 4)
                                                                                                + 8LL));
  memset_0(v16, 0, 0x58u);
  v12 = *((_QWORD *)this + 4);
  v13 = *(struct _RTL_CRITICAL_SECTION **)(v12 + 64);
  EnterCriticalSection(v13);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v15, "CMPEG2DemuxOutputPin::GetMediaType", 350);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, &WPP_89c6d11f487739c3770de58ece25afb2_Traceguids, v12, 0, v16);
  CMediaType::Set((CMediaType *)v16, (const struct _AMMediaType *)(v12 + 272));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v15);
  LeaveCriticalSection(v13);
  *((_DWORD *)this + 21) = (unsigned __int8)_(v16, &GUID_455f176c_4b06_47ce_9aef_8caef73df7b5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v15);
  if ( v19 )
    CoTaskMemFree(pv);
  return this;
}

```

## disassembly

```asm
0x18000afc8  mov     [rsp-8+arg_10], rbx
0x18000afcd  push    rbp
0x18000afce  push    rsi
0x18000afcf  push    rdi
0x18000afd0  push    r14
0x18000afd2  push    r15
0x18000afd4  lea     rbp, [rsp-17h]
0x18000afd9  sub     rsp, 0B0h
0x18000afe0  mov     rax, cs:__security_cookie
0x18000afe7  xor     rax, rsp
0x18000afea  mov     [rbp+37h+var_30], rax
0x18000afee  mov     r15d, 1
0x18000aff4  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18000affb  mov     [rcx], rax
0x18000affe  mov     r14d, r8d
0x18000b001  mov     rax, [rbp+37h+arg_38]
0x18000b005  mov     rdi, rdx
0x18000b008  mov     [rcx+10h], rax
0x18000b00c  lea     rdx, aCbuffersourceC; "CBufferSource::CBufferSource"
0x18000b013  mov     rbx, rcx
0x18000b016  mov     [rcx+8], r15d
0x18000b01a  mov     [rcx+0Ch], r15d
0x18000b01e  lea     r8d, [r15+4Ah]; int
0x18000b022  mov     [rcx+18h], r15d
0x18000b026  mov     esi, r9d
0x18000b029  lea     rcx, [rbp+37h+var_A0]; this
0x18000b02d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b032  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000b039  jb      short loc_18000B05C
0x18000b03b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b042  lea     edx, [r15+9]
0x18000b046  mov     r9, rbx
0x18000b049  lea     r8, WPP_99d91d446fe635ade03b8ca4e19bb98c_Traceguids
0x18000b050  mov     rcx, [rcx+88h]
0x18000b057  call    WPP_SF_q
0x18000b05c  mov     rax, [rbx+10h]
0x18000b060  lock add [rax+20h], r15d
0x18000b065  lea     rcx, [rbp+37h+var_A0]; this
0x18000b069  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b06e  mov     [rbx+28h], r14d
0x18000b072  lea     rax, ??_7CMediaSampleCopyBuffer@@6B@; const CMediaSampleCopyBuffer::`vftable'
0x18000b079  xor     r14d, r14d
0x18000b07c  mov     [rbx], rax
0x18000b07f  mov     rax, [rbp+37h+arg_20]
0x18000b083  lea     rcx, [rbp+37h+var_90]; void *
0x18000b087  mov     [rbx+30h], rax
0x18000b08b  xor     edx, edx; Val
0x18000b08d  mov     eax, [rbp+37h+arg_30]
0x18000b090  mov     [rbx+2Ch], esi
0x18000b093  lea     esi, [r14+58h]
0x18000b097  mov     [rbx+20h], rdi
0x18000b09b  mov     r8d, esi; Size
0x18000b09e  mov     [rbx+38h], r14
0x18000b0a2  mov     [rbx+40h], r14
0x18000b0a6  mov     [rbx+48h], r14d
0x18000b0aa  mov     [rbx+50h], eax
0x18000b0ad  mov     [rbx+54h], r14d
0x18000b0b1  call    memset_0
0x18000b0b6  lea     r8d, [r14+2Bh]; int
0x18000b0ba  mov     [rbp+37h+var_68], r15d
0x18000b0be  lea     rdx, aCmediasampleco_1; "CMediaSampleCopyBuffer::CMediaSampleCop"...
0x18000b0c5  mov     [rbp+37h+var_70], r15d
0x18000b0c9  lea     rcx, [rbp+37h+var_A0]; this
0x18000b0cd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b0d2  cmp     cs:byte_1800EACCB, 8
0x18000b0d9  jb      short loc_18000B100
0x18000b0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e2  lea     edx, [rsi-4Eh]
0x18000b0e5  mov     r9, rbx
0x18000b0e8  mov     [rsp+0D0h+var_B0], rdi
0x18000b0ed  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18000b0f4  mov     rcx, [rcx+88h]
0x18000b0fb  call    WPP_SF_qq
0x18000b100  mov     rax, [rbx+30h]
0x18000b104  lock add [rax+28h], r15d
0x18000b109  mov     rax, [rbx+20h]
0x18000b10d  mov     rcx, [rax+8]
0x18000b111  mov     rax, [rcx]
0x18000b114  mov     rax, [rax+8]
0x18000b118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11d  mov     r8, rsi; Size
0x18000b120  lea     rcx, [rbp+37h+var_90]; void *
0x18000b124  xor     edx, edx; Val
0x18000b126  call    memset_0
0x18000b12b  mov     rdi, [rbx+20h]
0x18000b12f  mov     rsi, [rdi+40h]
0x18000b133  mov     rcx, rsi; lpCriticalSection
0x18000b136  call    cs:__imp_EnterCriticalSection
0x18000b13d  nop     dword ptr [rax+rax+00h]
0x18000b142  mov     r8d, 15Eh; int
0x18000b148  lea     rdx, aCmpeg2demuxout_22; "CMPEG2DemuxOutputPin::GetMediaType"
0x18000b14f  lea     rcx, [rbp+37h+var_A0]; this
0x18000b153  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b158  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000b15f  jb      short loc_18000B191
0x18000b161  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b168  lea     rax, [rbp+37h+var_90]
0x18000b16c  mov     [rsp+0D0h+var_A8], rax
0x18000b171  lea     r8, WPP_89c6d11f487739c3770de58ece25afb2_Traceguids
0x18000b178  mov     edx, 10h
0x18000b17d  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x18000b182  mov     r9, rdi
0x18000b185  mov     rcx, [rcx+88h]
0x18000b18c  call    WPP_SF_qDq
0x18000b191  lea     rdx, [rdi+110h]; struct _AMMediaType *
0x18000b198  lea     rcx, [rbp+37h+var_90]; this
0x18000b19c  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000b1a1  lea     rcx, [rbp+37h+var_A0]; this
0x18000b1a5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b1aa  mov     rcx, rsi; lpCriticalSection
0x18000b1ad  call    cs:__imp_LeaveCriticalSection
0x18000b1b4  nop     dword ptr [rax+rax+00h]
0x18000b1b9  lea     rdx, _GUID_455f176c_4b06_47ce_9aef_8caef73df7b5
0x18000b1c0  lea     rcx, [rbp+37h+var_90]
0x18000b1c4  call    __
0x18000b1c9  movzx   ecx, al
0x18000b1cc  mov     [rbx+54h], ecx
0x18000b1cf  lea     rcx, [rbp+37h+var_A0]; this
0x18000b1d3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b1d8  cmp     [rbp+37h+var_48], r14d
0x18000b1dc  jz      short loc_18000B1EE
0x18000b1de  mov     rcx, [rbp+37h+pv]; pv
0x18000b1e2  call    cs:__imp_CoTaskMemFree
0x18000b1e9  nop     dword ptr [rax+rax+00h]
0x18000b1ee  mov     rax, rbx
0x18000b1f1  mov     rcx, [rbp+37h+var_30]
0x18000b1f5  xor     rcx, rsp; StackCookie
0x18000b1f8  call    __security_check_cookie
0x18000b1fd  mov     rbx, [rsp+0D0h+arg_10]
0x18000b205  add     rsp, 0B0h
0x18000b20c  pop     r15
0x18000b20e  pop     r14
0x18000b210  pop     rdi
0x18000b211  pop     rsi
0x18000b212  pop     rbp
0x18000b213  retn
```
