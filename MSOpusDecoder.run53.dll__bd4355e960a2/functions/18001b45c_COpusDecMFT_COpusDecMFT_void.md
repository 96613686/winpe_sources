# COpusDecMFT::~COpusDecMFT(void)

- ea: `0x18001b45c`
- end: `0x18001b55b`
- name: `??1COpusDecMFT@@UEAA@XZ`
- size: `255`
- prototype: `void __fastcall(COpusDecMFT *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b6a0`
- `0x18001ef40`
- `0x18001efb0`

## callees

- `0x1800011dc`
- `0x1800018f0`
- `0x180003ab0`
- `0x18001b258`
- `0x18001b34c`
- `0x18001b45c`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall COpusDecMFT::~COpusDecMFT(COpusDecMFT *this, __int64 a2)
{
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  COpusDecMFT *v6; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-40h] BYREF
  COpusDecMFT **v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  *(_QWORD *)this = &COpusDecMFT::`vftable'{for `CMFTSimpleBase'};
  *((_QWORD *)this + 19) = &COpusDecMFT::`vftable'{for `IMFTelemetryComponent'};
  if ( (unsigned int)dword_180035090 > 4 )
  {
    v6 = this;
    v8 = &v6;
    v9 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180035090, byte_180030A8D, 0, 0, 3u, &v7);
  }
  v3 = (void *)*((_QWORD *)this + 23);
  if ( v3 )
    opus_decoder_destroy(v3);
  *((_QWORD *)this + 23) = 0;
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 9) = 0;
  }
  *((_QWORD *)this + 34) = &COpusDecTlmAggregator::`vftable';
  CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>(
    (__int64)this + 272,
    a2);
  v5 = *((_QWORD *)this + 33);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  CMFTSimpleBase::~CMFTSimpleBase(this);
}

```

## disassembly

```asm
0x18001b45c  mov     r11, rsp
0x18001b45f  push    rbx
0x18001b460  sub     rsp, 70h
0x18001b464  mov     rax, cs:__security_cookie
0x18001b46b  xor     rax, rsp
0x18001b46e  mov     [rsp+78h+var_10], rax
0x18001b473  mov     rbx, rcx
0x18001b476  lea     rax, ??_7COpusDecMFT@@6BCMFTSimpleBase@@@; const COpusDecMFT::`vftable'{for `CMFTSimpleBase'}
0x18001b47d  mov     [rcx], rax
0x18001b480  lea     rax, ??_7COpusDecMFT@@6BIMFTelemetryComponent@@@; const COpusDecMFT::`vftable'{for `IMFTelemetryComponent'}
0x18001b487  mov     [rcx+98h], rax
0x18001b48e  mov     eax, cs:dword_180035090
0x18001b494  cmp     eax, 4
0x18001b497  jbe     short loc_18001B4D6
0x18001b499  mov     [r11-48h], rcx
0x18001b49d  lea     rax, [r11-48h]
0x18001b4a1  mov     [r11-20h], rax
0x18001b4a5  mov     qword ptr [r11-18h], 8
0x18001b4ad  lea     rax, [r11-40h]
0x18001b4b1  mov     [r11-50h], rax
0x18001b4b5  mov     [rsp+78h+var_58], 3
0x18001b4bd  xor     r9d, r9d
0x18001b4c0  xor     r8d, r8d
0x18001b4c3  lea     rdx, byte_180030A8D
0x18001b4ca  lea     rcx, dword_180035090
0x18001b4d1  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b4d6  mov     rcx, [rbx+0B8h]; Block
0x18001b4dd  test    rcx, rcx
0x18001b4e0  jz      short loc_18001B4E7
0x18001b4e2  call    opus_decoder_destroy
0x18001b4e7  mov     qword ptr [rbx+0B8h], 0
0x18001b4f2  mov     rcx, [rbx+48h]
0x18001b4f6  test    rcx, rcx
0x18001b4f9  jz      short loc_18001B50F
0x18001b4fb  mov     rax, [rcx]
0x18001b4fe  mov     rax, [rax+10h]
0x18001b502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b507  mov     qword ptr [rbx+48h], 0
0x18001b50f  lea     rcx, [rbx+110h]
0x18001b516  lea     rax, ??_7COpusDecTlmAggregator@@6B@; const COpusDecTlmAggregator::`vftable'
0x18001b51d  mov     [rcx], rax
0x18001b520  call    ??1?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>(void)
0x18001b525  nop
0x18001b526  mov     rcx, [rbx+108h]
0x18001b52d  test    rcx, rcx
0x18001b530  jz      short loc_18001B53F
0x18001b532  mov     rax, [rcx]
0x18001b535  mov     rax, [rax+10h]
0x18001b539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b53e  nop
0x18001b53f  mov     rcx, rbx; this
0x18001b542  call    ??1CMFTSimpleBase@@UEAA@XZ; CMFTSimpleBase::~CMFTSimpleBase(void)
0x18001b547  nop
0x18001b548  mov     rcx, [rsp+78h+var_10]
0x18001b54d  xor     rcx, rsp; StackCookie
0x18001b550  call    __security_check_cookie
0x18001b555  add     rsp, 70h
0x18001b559  pop     rbx
0x18001b55a  retn
```
