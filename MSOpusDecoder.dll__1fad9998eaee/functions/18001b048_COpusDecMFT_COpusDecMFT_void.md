# COpusDecMFT::COpusDecMFT(void)

- ea: `0x18001b048`
- end: `0x18001b251`
- name: `??0COpusDecMFT@@QEAA@XZ`
- size: `521`
- prototype: `COpusDecMFT *__fastcall(COpusDecMFT *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800202b4`
- `0x1800203ec`

## callees

- `0x1800011dc`
- `0x1800013f4`
- `0x1800018f0`
- `0x18001b048`
- `0x18001e8c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b0b5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b0b5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b217`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b217`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b16d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b16d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
COpusDecMFT *__fastcall COpusDecMFT::COpusDecMFT(COpusDecMFT *this)
{
  __int64 v2; // rdx
  char *v3; // rcx
  COpusDecMFT *v5; // [rsp+30h] [rbp-58h] BYREF
  char *v6; // [rsp+38h] [rbp-50h]
  char *v7; // [rsp+40h] [rbp-48h]
  _BYTE v8[32]; // [rsp+48h] [rbp-40h] BYREF
  COpusDecMFT **v9; // [rsp+68h] [rbp-20h]
  __int64 v10; // [rsp+70h] [rbp-18h]

  v5 = this;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 18) = 2;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *(_QWORD *)this = &COpusDecMFT::`vftable'{for `CMFTSimpleBase'};
  *((_QWORD *)this + 19) = &COpusDecMFT::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 33) = 0;
  v7 = (char *)this + 272;
  *((_QWORD *)this + 34) = &CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::`vftable';
  *((_QWORD *)this + 35) = 0;
  *((_BYTE *)this + 288) = 0;
  *((_QWORD *)this + 37) = 0;
  v3 = (char *)operator new(0x30u);
  v6 = v3;
  if ( v3 )
  {
    *(_QWORD *)v3 = &COpusAggregateData::`vftable';
    *(GUID *)(v3 + 8) = GUID_NULL;
    *((_QWORD *)v3 + 5) = 0;
    *((_DWORD *)v3 + 7) = 0;
    *((_WORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 4) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 35) = v3;
  *((_BYTE *)this + 289) = 1;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 34) = &COpusDecTlmAggregator::`vftable';
  v6 = 0;
  LOBYTE(v2) = 1;
  CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::ResetPeriod(
    (char *)this + 272,
    v2);
  *((_QWORD *)this + 38) = 60000;
  *((_QWORD *)this + 39) = GetTickCount64();
  if ( (unsigned int)dword_180035090 > 4 )
  {
    v9 = &v5;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180035090, &dword_180030634, 0, 0, 3, v8, this, v6);
  }
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_BYTE *)this + 208) = 0;
  *(_DWORD *)((char *)this + 210) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *(GUID *)((char *)this + 248) = GUID_NULL;
  CoCreateGuid((GUID *)((char *)this + 248));
  *(_OWORD *)(*((_QWORD *)this + 35) + 8LL) = *(_OWORD *)((char *)this + 248);
  return this;
}

```

## disassembly

```asm
0x18001b048  mov     [rsp+arg_8], rbx
0x18001b04d  mov     [rsp+arg_10], rsi
0x18001b052  push    rdi
0x18001b053  sub     rsp, 80h
0x18001b05a  mov     rax, cs:__security_cookie
0x18001b061  xor     rax, rsp
0x18001b064  mov     [rsp+88h+var_10], rax
0x18001b069  mov     rdi, rcx
0x18001b06c  mov     [rsp+88h+var_58], rcx
0x18001b071  xor     esi, esi
0x18001b073  mov     [rcx+0A0h], esi
0x18001b079  mov     [rcx+8], esi
0x18001b07c  mov     [rcx+10h], rsi
0x18001b080  mov     [rcx+18h], esi
0x18001b083  mov     [rcx+20h], rsi
0x18001b087  mov     [rcx+28h], rsi
0x18001b08b  mov     [rcx+30h], rsi
0x18001b08f  mov     [rcx+38h], rsi
0x18001b093  mov     [rcx+40h], rsi
0x18001b097  mov     [rcx+48h], rsi
0x18001b09b  mov     [rcx+50h], rsi
0x18001b09f  mov     [rcx+58h], rsi
0x18001b0a3  mov     [rcx+60h], esi
0x18001b0a6  mov     qword ptr [rcx+90h], 2
0x18001b0b1  add     rcx, 68h ; 'h'; lpCriticalSection
0x18001b0b5  call    cs:__imp_InitializeCriticalSection
0x18001b0bb  nop
0x18001b0bc  lea     rax, ??_7COpusDecMFT@@6BCMFTSimpleBase@@@; const COpusDecMFT::`vftable'{for `CMFTSimpleBase'}
0x18001b0c3  mov     [rdi], rax
0x18001b0c6  lea     rax, ??_7COpusDecMFT@@6BIMFTelemetryComponent@@@; const COpusDecMFT::`vftable'{for `IMFTelemetryComponent'}
0x18001b0cd  mov     [rdi+98h], rax
0x18001b0d4  mov     [rdi+108h], rsi
0x18001b0db  lea     rbx, [rdi+110h]
0x18001b0e2  mov     [rsp+88h+var_48], rbx
0x18001b0e7  lea     rax, ??_7?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@6B@; const CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::`vftable'
0x18001b0ee  mov     [rbx], rax
0x18001b0f1  mov     [rbx+8], rsi
0x18001b0f5  mov     [rbx+10h], sil
0x18001b0f9  mov     [rbx+18h], rsi
0x18001b0fd  lea     ecx, [rsi+30h]; Size
0x18001b100  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b105  mov     rcx, rax
0x18001b108  mov     [rsp+88h+var_50], rax
0x18001b10d  test    rax, rax
0x18001b110  jz      short loc_18001B139
0x18001b112  lea     rax, ??_7COpusAggregateData@@6B@; const COpusAggregateData::`vftable'
0x18001b119  mov     [rcx], rax
0x18001b11c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b123  movdqu  xmmword ptr [rcx+8], xmm0
0x18001b128  mov     [rcx+28h], rsi
0x18001b12c  mov     [rcx+1Ch], esi
0x18001b12f  mov     [rcx+18h], si
0x18001b133  mov     [rcx+20h], rsi
0x18001b137  jmp     short loc_18001B13C
0x18001b139  mov     rcx, rsi
0x18001b13c  mov     [rbx+8], rcx
0x18001b140  mov     byte ptr [rbx+11h], 1
0x18001b144  mov     [rbx+20h], rsi
0x18001b148  mov     [rbx+28h], rsi
0x18001b14c  lea     rax, ??_7COpusDecTlmAggregator@@6B@; const COpusDecTlmAggregator::`vftable'
0x18001b153  mov     [rbx], rax
0x18001b156  mov     [rsp+88h+var_50], rsi
0x18001b15b  mov     dl, 1
0x18001b15d  mov     rcx, rbx
0x18001b160  call    ?ResetPeriod@?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAX_N@Z; CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::ResetPeriod(bool)
0x18001b165  mov     qword ptr [rbx+20h], 0EA60h
0x18001b16d  call    cs:__imp_GetTickCount64
0x18001b173  mov     [rbx+28h], rax
0x18001b177  mov     eax, cs:dword_180035090
0x18001b17d  cmp     eax, 4
0x18001b180  jbe     short loc_18001B1C5
0x18001b182  mov     [rsp+88h+var_58], rdi
0x18001b187  lea     rax, [rsp+88h+var_58]
0x18001b18c  mov     [rsp+88h+var_20], rax
0x18001b191  mov     [rsp+88h+var_18], 8
0x18001b19a  lea     rax, [rsp+88h+var_40]
0x18001b19f  mov     [rsp+88h+var_60], rax
0x18001b1a4  mov     [rsp+88h+var_68], 3
0x18001b1ac  xor     r9d, r9d
0x18001b1af  xor     r8d, r8d
0x18001b1b2  lea     rdx, dword_180030634
0x18001b1b9  lea     rcx, dword_180035090
0x18001b1c0  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b1c5  mov     [rdi+0B8h], rsi
0x18001b1cc  mov     [rdi+0C0h], rsi
0x18001b1d3  mov     [rdi+0C8h], rsi
0x18001b1da  mov     [rdi+0E8h], rsi
0x18001b1e1  mov     [rdi+0F0h], rsi
0x18001b1e8  mov     [rdi+0D0h], sil
0x18001b1ef  mov     [rdi+0D2h], esi
0x18001b1f5  mov     [rdi+0D8h], rsi
0x18001b1fc  mov     [rdi+0E0h], esi
0x18001b202  lea     rbx, [rdi+0F8h]
0x18001b209  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b210  movdqu  xmmword ptr [rbx], xmm0
0x18001b214  mov     rcx, rbx; pguid
0x18001b217  call    cs:__imp_CoCreateGuid
0x18001b21d  movups  xmm0, xmmword ptr [rbx]
0x18001b220  mov     rcx, [rdi+118h]
0x18001b227  movdqu  xmmword ptr [rcx+8], xmm0
0x18001b22c  mov     rax, rdi
0x18001b22f  mov     rcx, [rsp+88h+var_10]
0x18001b234  xor     rcx, rsp; StackCookie
0x18001b237  call    __security_check_cookie
0x18001b23c  lea     r11, [rsp+88h+var_8]
0x18001b244  mov     rbx, [r11+18h]
0x18001b248  mov     rsi, [r11+20h]
0x18001b24c  mov     rsp, r11
0x18001b24f  pop     rdi
0x18001b250  retn
```
