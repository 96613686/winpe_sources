# FSStream::LogFirstFrameTimeout(void)

- ea: `0x1800acbcc`
- end: `0x1800ad4f0`
- name: `?LogFirstFrameTimeout@FSStream@@IEAAXXZ`
- size: `2340`
- prototype: `void __fastcall(FSStream *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800a8b40`

## callees

- `0x18000162c`
- `0x180002e28`
- `0x180003e20`
- `0x180073610`
- `0x1800acbcc`
- `0x1800b27b4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800acc22`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800acc22`
- `MFPlat!MFGetSystemTime` at `0x1800acbfc`
- `MFPlat!MFGetSystemTime` at `0x1800acbfc`

## pseudocode

```c
void __fastcall FSStream::LogFirstFrameTimeout(FSStream *this)
{
  MFTIME v2; // rsi
  __int64 v3; // r14
  int v4; // r8d
  int v5; // edx
  __int16 v6; // r15
  char IsEnabled; // al
  __int128 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+370h] [rbp+E0h] BYREF
  _QWORD v14[15]; // [rsp+380h] [rbp+F0h] BYREF
  GUID v15; // [rsp+3F8h] [rbp+168h]
  __int64 v16; // [rsp+408h] [rbp+178h]
  int v17; // [rsp+410h] [rbp+180h]
  GUID v18; // [rsp+414h] [rbp+184h]
  __int64 v19; // [rsp+424h] [rbp+194h]
  __int64 v20; // [rsp+42Ch] [rbp+19Ch]
  int v21; // [rsp+434h] [rbp+1A4h]
  _QWORD v22[15]; // [rsp+440h] [rbp+1B0h] BYREF
  GUID v23; // [rsp+4B8h] [rbp+228h]
  __int64 v24; // [rsp+4C8h] [rbp+238h]
  int v25; // [rsp+4D0h] [rbp+240h]
  GUID v26; // [rsp+4D4h] [rbp+244h]
  __int64 v27; // [rsp+4E4h] [rbp+254h]
  __int64 v28; // [rsp+4ECh] [rbp+25Ch]
  int v29; // [rsp+4F4h] [rbp+264h]
  __int128 *v30; // [rsp+500h] [rbp+270h] BYREF
  __int16 v31; // [rsp+508h] [rbp+278h]
  GUID v32; // [rsp+510h] [rbp+280h]
  __int128 v33; // [rsp+520h] [rbp+290h] BYREF

  v2 = MFGetSystemTime() - *((_QWORD *)this + 86);
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  GetSystemPowerStatus(&SystemPowerStatus);
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 40LL))(*((_QWORD *)this + 42));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 176LL))(*((_QWORD *)this + 42));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 72LL))(*((_QWORD *)this + 42));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 80LL))(*((_QWORD *)this + 42));
  v5 = 0;
  v6 = 0;
  v33 = 0;
  if ( *((_QWORD *)this + 24) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl'::`2'::impl);
    v5 = 0;
    if ( IsEnabled )
    {
      v8 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 304LL))(
                         *((_QWORD *)this + 24),
                         0);
      v5 = 0;
      v6 = 1;
      v33 = *v8;
    }
  }
  v9 = *((_QWORD *)this + 93);
  memset(v22, 0, sizeof(v22));
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset(v14, 0, sizeof(v14));
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v23 = GUID_00000000_0000_0000_0000_000000000000;
  v26 = GUID_00000000_0000_0000_0000_000000000000;
  v15 = GUID_00000000_0000_0000_0000_000000000000;
  v18 = GUID_00000000_0000_0000_0000_000000000000;
  v32 = GUID_00000000_0000_0000_0000_000000000000;
  if ( v9 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)v9 + 88LL))(v9, 1, 0, v22);
  v10 = *((_QWORD *)this + 94);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)v10 + 88LL))(v10, 1, 0, v14);
    v32 = *(GUID *)(*(__int64 (__fastcall **)(_QWORD, __int128 **))(**((_QWORD **)this + 94) + 32LL))(
                     *((_QWORD *)this + 94),
                     &v30);
  }
  if ( byte_18010EC4D )
    WPP_SF_qDDiS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v5,
      v4,
      (_DWORD)this,
      *((_DWORD *)this + 22),
      *((_DWORD *)this + 23),
      v2,
      v3);
  if ( dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
  {
    v11 = *((_QWORD *)this + 24);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 136LL))(v11);
    v12 = *((_QWORD *)this + 24);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 144LL))(v12);
    v30 = &v33;
    v31 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperArray<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v12,
      &unk_18010369D);
  }
}

```

## disassembly

```asm
0x1800acbcc  push    rbp
0x1800acbce  push    rbx
0x1800acbcf  push    rsi
0x1800acbd0  push    rdi
0x1800acbd1  push    r12
0x1800acbd3  push    r13
0x1800acbd5  push    r14
0x1800acbd7  push    r15
0x1800acbd9  lea     rbp, [rsp-2B8h]
0x1800acbe1  sub     rsp, 548h
0x1800acbe8  mov     rax, cs:__security_cookie
0x1800acbef  xor     rax, rsp
0x1800acbf2  mov     [rbp+2F0h+var_50], rax
0x1800acbf9  mov     rbx, rcx
0x1800acbfc  call    cs:__imp_MFGetSystemTime
0x1800acc02  mov     rsi, rax
0x1800acc05  lea     rcx, [rbp+2F0h+SystemPowerStatus]; lpSystemPowerStatus
0x1800acc0c  sub     rsi, [rbx+2B0h]
0x1800acc13  xor     eax, eax
0x1800acc15  mov     qword ptr [rbp+2F0h+SystemPowerStatus.ACLineStatus], rax
0x1800acc1c  mov     [rbp+2F0h+SystemPowerStatus.BatteryFullLifeTime], eax
0x1800acc22  call    cs:__imp_GetSystemPowerStatus
0x1800acc28  mov     rcx, [rbx+150h]
0x1800acc2f  mov     rdx, [rcx]
0x1800acc32  mov     rax, [rdx+28h]
0x1800acc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc3b  mov     rcx, [rbx+150h]
0x1800acc42  mov     r14, rax
0x1800acc45  mov     rdx, [rcx]
0x1800acc48  mov     rax, [rdx+0B0h]
0x1800acc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc54  mov     rcx, [rbx+150h]
0x1800acc5b  mov     r12, rax
0x1800acc5e  mov     rdx, [rcx]
0x1800acc61  mov     rax, [rdx+18h]
0x1800acc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc6a  mov     rcx, [rbx+150h]
0x1800acc71  mov     r13d, eax
0x1800acc74  mov     rdx, [rcx]
0x1800acc77  mov     rax, [rdx+48h]
0x1800acc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc80  mov     rcx, [rbx+150h]
0x1800acc87  mov     dword ptr [rbp+2F0h+var_360], eax
0x1800acc8a  mov     rdx, [rcx]
0x1800acc8d  mov     rax, [rdx+50h]
0x1800acc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc96  xor     edx, edx
0x1800acc98  mov     dword ptr [rbp+2F0h+var_368], eax
0x1800acc9b  xorps   xmm0, xmm0
0x1800acc9e  mov     r15d, edx
0x1800acca1  movups  [rbp+2F0h+var_60], xmm0
0x1800acca8  lea     r10d, [rdx+1]
0x1800accac  cmp     [rbx+0C0h], rdx
0x1800accb3  jz      short loc_1800ACCFC
0x1800accb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry> `wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl(void)'::`2'::impl
0x1800accbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerErrorTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(void)
0x1800accc1  xor     edx, edx
0x1800accc3  test    al, al
0x1800accc5  jz      short loc_1800ACCF6
0x1800accc7  mov     rcx, [rbx+0C0h]
0x1800accce  mov     rax, [rcx]
0x1800accd1  mov     rax, [rax+130h]
0x1800accd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800accdd  mov     r10d, 1
0x1800acce3  xor     edx, edx
0x1800acce5  movzx   r15d, r10w
0x1800acce9  movups  xmm0, xmmword ptr [rax]
0x1800accec  movdqu  [rbp+2F0h+var_60], xmm0
0x1800accf4  jmp     short loc_1800ACCFC
0x1800accf6  mov     r10d, 1
0x1800accfc  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800acd03  lea     rax, aSoftware; "Software"
0x1800acd0a  cmp     [rbx+130h], rdx
0x1800acd11  lea     rdi, aDx11; "DX11"
0x1800acd18  mov     rcx, [rbx+2E8h]
0x1800acd1f  cmovz   rdi, rax
0x1800acd23  mov     [rbp+2F0h+var_140], 0
0x1800acd2e  xor     eax, eax
0x1800acd30  mov     [rbp+2F0h+var_138], rdx
0x1800acd37  mov     [rbp+2F0h+var_130], rdx
0x1800acd3e  mov     [rbp+2F0h+var_128], rdx
0x1800acd45  mov     [rbp+2F0h+var_120], rdx
0x1800acd4c  mov     [rbp+2F0h+var_118], 0
0x1800acd57  mov     [rbp+2F0h+var_110], rdx
0x1800acd5e  mov     [rbp+2F0h+var_108], rdx
0x1800acd65  mov     [rbp+2F0h+var_100], 0
0x1800acd70  mov     [rbp+2F0h+var_F8], rdx
0x1800acd77  mov     [rbp+2F0h+var_F0], rdx
0x1800acd7e  mov     [rbp+2F0h+var_E8], 0
0x1800acd89  mov     [rbp+2F0h+var_E0], rdx
0x1800acd90  mov     [rbp+2F0h+var_D8], rdx
0x1800acd97  mov     [rbp+2F0h+var_D0], rdx
0x1800acd9e  mov     [rbp+2F0h+var_B8], 0
0x1800acda9  mov     [rbp+2F0h+var_B0], 0
0x1800acdb3  mov     [rbp+2F0h+var_9C], 0
0x1800acdbe  mov     [rbp+2F0h+var_94], 0
0x1800acdc9  mov     [rbp+2F0h+var_8C], eax
0x1800acdcf  mov     [rbp+2F0h+var_200], rax
0x1800acdd6  mov     [rbp+2F0h+var_1F8], rdx
0x1800acddd  mov     [rbp+2F0h+var_1F0], rdx
0x1800acde4  mov     [rbp+2F0h+var_1E8], rdx
0x1800acdeb  mov     [rbp+2F0h+var_1E0], rdx
0x1800acdf2  mov     [rbp+2F0h+var_1D8], rax
0x1800acdf9  mov     [rbp+2F0h+var_1D0], rdx
0x1800ace00  mov     [rbp+2F0h+var_1C8], rdx
0x1800ace07  mov     [rbp+2F0h+var_1C0], rax
0x1800ace0e  mov     [rbp+2F0h+var_1B8], rdx
0x1800ace15  mov     [rbp+2F0h+var_1B0], rdx
0x1800ace1c  mov     [rbp+2F0h+var_1A8], rax
0x1800ace23  mov     [rbp+2F0h+var_1A0], rdx
0x1800ace2a  mov     [rbp+2F0h+var_198], rdx
0x1800ace31  mov     [rbp+2F0h+var_190], rdx
0x1800ace38  mov     [rbp+2F0h+var_178], rax
0x1800ace3f  mov     [rbp+2F0h+var_170], eax
0x1800ace45  mov     [rbp+2F0h+var_15C], rax
0x1800ace4c  mov     [rbp+2F0h+var_154], rax
0x1800ace53  mov     [rbp+2F0h+var_14C], eax
0x1800ace59  movdqu  [rbp+2F0h+var_C8], xmm0
0x1800ace61  movdqu  [rbp+2F0h+var_AC], xmm0
0x1800ace69  movdqu  [rbp+2F0h+var_188], xmm0
0x1800ace71  movdqu  [rbp+2F0h+var_16C], xmm0
0x1800ace79  movdqu  [rbp+2F0h+var_70], xmm0
0x1800ace81  test    rcx, rcx
0x1800ace84  jz      short loc_1800ACE9F
0x1800ace86  mov     rax, [rcx]
0x1800ace89  lea     r9, [rbp+2F0h+var_140]
0x1800ace90  xor     r8d, r8d
0x1800ace93  mov     edx, r10d
0x1800ace96  mov     rax, [rax+58h]
0x1800ace9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace9f  mov     rcx, [rbx+2F0h]
0x1800acea6  test    rcx, rcx
0x1800acea9  jz      short loc_1800ACEEA
0x1800aceab  mov     rax, [rcx]
0x1800aceae  lea     r9, [rbp+2F0h+var_200]
0x1800aceb5  xor     r8d, r8d
0x1800aceb8  mov     rax, [rax+58h]
0x1800acebc  lea     edx, [r8+1]
0x1800acec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acec5  mov     rcx, [rbx+2F0h]
0x1800acecc  lea     rdx, [rbp+2F0h+var_80]
0x1800aced3  mov     rax, [rcx]
0x1800aced6  mov     rax, [rax+20h]
0x1800aceda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acedf  movups  xmm0, xmmword ptr [rax]
0x1800acee2  movdqu  [rbp+2F0h+var_70], xmm0
0x1800aceea  cmp     cs:byte_18010EC4D, 1
0x1800acef1  jb      short loc_1800ACF21
0x1800acef3  mov     eax, [rbx+5Ch]
0x1800acef6  mov     r9, rbx
0x1800acef9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acf00  mov     [rsp+580h+var_548], r14
0x1800acf05  mov     [rsp+580h+var_550], rsi
0x1800acf0a  mov     dword ptr [rsp+580h+var_558], eax
0x1800acf0e  mov     eax, [rbx+58h]
0x1800acf11  mov     rcx, [rcx+0D8h]
0x1800acf18  mov     dword ptr [rsp+580h+var_560], eax
0x1800acf1c  call    WPP_SF_qDDiS
0x1800acf21  mov     eax, cs:dword_18010C208
0x1800acf27  test    eax, eax
0x1800acf29  jz      loc_1800AD4CD
0x1800acf2f  mov     rdx, 400000000000h
0x1800acf39  lea     rcx, dword_18010C208
0x1800acf40  call    _tlgKeywordOn
0x1800acf45  test    al, al
0x1800acf47  jz      loc_1800AD4CD
0x1800acf4d  mov     eax, dword ptr [rbp+2F0h+var_1A8]
0x1800acf53  mov     [rbp+2F0h+var_358], eax
0x1800acf56  mov     rax, [rbp+2F0h+var_1B0]
0x1800acf5d  mov     [rbp+2F0h+var_2F0], rax
0x1800acf61  mov     rax, [rbp+2F0h+var_1B8]
0x1800acf68  mov     [rbp+2F0h+var_2E8], rax
0x1800acf6c  mov     eax, dword ptr [rbp+2F0h+var_1D8]
0x1800acf72  mov     [rbp+2F0h+var_354], eax
0x1800acf75  mov     rax, [rbp+2F0h+var_1E0]
0x1800acf7c  mov     [rbp+2F0h+var_2E0], rax
0x1800acf80  mov     rax, [rbp+2F0h+var_1E8]
0x1800acf87  mov     [rbp+2F0h+var_2D8], rax
0x1800acf8b  mov     eax, dword ptr [rbp+2F0h+var_154]
0x1800acf91  mov     rcx, [rbx+0C0h]
0x1800acf98  mov     [rbp+2F0h+var_350], eax
0x1800acf9b  mov     eax, dword ptr [rbp+2F0h+var_15C+4]
0x1800acfa1  mov     [rbp+2F0h+var_34C], eax
0x1800acfa4  mov     eax, dword ptr [rbp+2F0h+var_15C]
0x1800acfaa  mov     [rbp+2F0h+var_348], eax
0x1800acfad  lea     rax, [rbp+2F0h+var_16C]
0x1800acfb4  mov     [rbp+2F0h+var_2D0], rax
0x1800acfb8  mov     eax, [rbp+2F0h+var_170]
0x1800acfbe  mov     [rbp+2F0h+var_344], eax
0x1800acfc1  mov     eax, dword ptr [rbp+2F0h+var_178+4]
0x1800acfc7  mov     [rbp+2F0h+var_340], eax
0x1800acfca  mov     eax, dword ptr [rbp+2F0h+var_178]
0x1800acfd0  mov     [rbp+2F0h+var_33C], eax
0x1800acfd3  lea     rax, [rbp+2F0h+var_188]
0x1800acfda  mov     [rbp+2F0h+var_2C8], rax
0x1800acfde  mov     eax, dword ptr [rbp+2F0h+var_154+4]
0x1800acfe4  mov     [rbp+2F0h+var_338], eax
0x1800acfe7  mov     rax, [rbp+2F0h+var_190]
0x1800acfee  mov     [rbp+2F0h+var_2C0], rax
0x1800acff2  mov     rax, [rbp+2F0h+var_198]
0x1800acff9  mov     [rbp+2F0h+var_2B8], rax
0x1800acffd  mov     rax, [rbp+2F0h+var_1A0]
0x1800ad004  mov     [rbp+2F0h+var_2B0], rax
0x1800ad008  lea     rax, [rbp+2F0h+var_70]
0x1800ad00f  mov     [rbp+2F0h+var_2A8], rax
0x1800ad013  mov     eax, dword ptr [rbp+2F0h+var_E8]
0x1800ad019  mov     [rbp+2F0h+var_334], eax
0x1800ad01c  mov     rax, [rbp+2F0h+var_F0]
0x1800ad023  mov     [rbp+2F0h+var_2A0], rax
0x1800ad027  mov     rax, [rbp+2F0h+var_F8]
0x1800ad02e  mov     [rbp+2F0h+var_298], rax
0x1800ad032  mov     eax, dword ptr [rbp+2F0h+var_118]
0x1800ad038  mov     [rbp+2F0h+var_330], eax
0x1800ad03b  mov     rax, [rbp+2F0h+var_120]
0x1800ad042  mov     [rbp+2F0h+var_290], rax
0x1800ad046  mov     rax, [rbp+2F0h+var_128]
0x1800ad04d  mov     [rbp+2F0h+var_288], rax
0x1800ad051  mov     eax, dword ptr [rbp+2F0h+var_94]
0x1800ad057  mov     [rbp+2F0h+var_32C], eax
0x1800ad05a  mov     eax, dword ptr [rbp+2F0h+var_9C+4]
0x1800ad060  mov     [rbp+2F0h+var_328], eax
0x1800ad063  mov     eax, dword ptr [rbp+2F0h+var_9C]
0x1800ad069  mov     [rbp+2F0h+var_324], eax
0x1800ad06c  lea     rax, [rbp+2F0h+var_AC]
0x1800ad073  mov     [rbp+2F0h+var_280], rax
0x1800ad077  mov     eax, [rbp+2F0h+var_B0]
0x1800ad07d  mov     [rbp+2F0h+var_320], eax
0x1800ad080  mov     eax, dword ptr [rbp+2F0h+var_B8+4]
0x1800ad086  mov     [rbp+2F0h+var_31C], eax
0x1800ad089  mov     eax, dword ptr [rbp+2F0h+var_B8]
0x1800ad08f  mov     [rbp+2F0h+var_318], eax
0x1800ad092  lea     rax, [rbp+2F0h+var_C8]
0x1800ad099  mov     [rbp+2F0h+var_278], rax
0x1800ad09d  mov     eax, dword ptr [rbp+2F0h+var_94+4]
0x1800ad0a3  mov     [rbp+2F0h+var_314], eax
0x1800ad0a6  mov     rax, [rbp+2F0h+var_D0]
0x1800ad0ad  mov     [rbp+2F0h+var_270], rax
0x1800ad0b4  mov     rax, [rbp+2F0h+var_D8]
0x1800ad0bb  mov     [rbp+2F0h+var_268], rax
0x1800ad0c2  mov     rax, [rbp+2F0h+var_E0]
0x1800ad0c9  mov     [rbp+2F0h+var_260], rax
0x1800ad0d0  test    rcx, rcx
0x1800ad0d3  jz      short loc_1800AD0E6
0x1800ad0d5  mov     rax, [rcx]
0x1800ad0d8  mov     rax, [rax+88h]
0x1800ad0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0e4  jmp     short loc_1800AD0E8
0x1800ad0e6  xor     eax, eax
0x1800ad0e8  mov     rcx, [rbx+0C0h]
0x1800ad0ef  mov     [rbp+2F0h+var_310], eax
0x1800ad0f2  test    rcx, rcx
0x1800ad0f5  jz      short loc_1800AD108
0x1800ad0f7  mov     rax, [rcx]
0x1800ad0fa  mov     rax, [rax+90h]
0x1800ad101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad106  jmp     short loc_1800AD10F
0x1800ad108  lea     rax, _GUID_00000000_0000_0000_0000_000000000000
0x1800ad10f  mov     [rbp+2F0h+var_258], rax
0x1800ad116  mov     eax, dword ptr [rbp+2F0h+var_368]
0x1800ad119  mov     [rbp+2F0h+var_30C], eax
0x1800ad11c  mov     eax, dword ptr [rbp+2F0h+var_360]
0x1800ad11f  mov     [rbp+2F0h+var_308], eax
0x1800ad122  mov     al, [rbx+2DCh]
0x1800ad128  mov     [rbp+2F0h+var_370], al
0x1800ad12b  mov     eax, [rbx+0A0h]
0x1800ad131  mov     [rbp+2F0h+var_300], eax
0x1800ad134  mov     rax, [rbx+2B0h]
0x1800ad13b  mov     [rbp+2F0h+var_240], rax
0x1800ad142  lea     rax, [rbp+2F0h+var_60]
0x1800ad149  mov     [rbp+2F0h+var_80], rax
0x1800ad150  lea     rax, [rbx+88h]
0x1800ad157  mov     [rbp+2F0h+var_368], rax
0x1800ad15b  mov     eax, [rbx+58h]
0x1800ad15e  mov     [rbp+2F0h+var_2FC], eax
0x1800ad161  mov     eax, [rbx+5Ch]
0x1800ad164  mov     [rbp+2F0h+var_2F8], eax
0x1800ad167  mov     al, [rbp+2F0h+SystemPowerStatus.SystemStatusFlag]
0x1800ad16d  mov     [rbp+2F0h+var_36F], al
0x1800ad170  mov     al, [rbp+2F0h+SystemPowerStatus.BatteryLifePercent]
0x1800ad176  mov     [rbp+2F0h+var_36E], al
0x1800ad179  mov     al, [rbp+2F0h+SystemPowerStatus.BatteryFlag]
0x1800ad17f  mov     [rbp+2F0h+var_36D], al
0x1800ad182  mov     al, [rbp+2F0h+SystemPowerStatus.ACLineStatus]
0x1800ad188  mov     [rbp+2F0h+var_36C], al
0x1800ad18b  lea     rax, [rbx+118h]
0x1800ad192  mov     [rbp+2F0h+var_228], rax
0x1800ad199  lea     rax, [rbx+108h]
0x1800ad1a0  mov     [rbp+2F0h+var_218], rax
0x1800ad1a7  lea     rax, [rbp+2F0h+var_358]
0x1800ad1ab  mov     [rsp+580h+var_380], rax
0x1800ad1b3  lea     rax, [rbp+2F0h+var_2F0]
0x1800ad1b7  mov     [rsp+580h+var_388], rax
0x1800ad1bf  lea     rax, [rbp+2F0h+var_2E8]
0x1800ad1c3  mov     [rsp+580h+var_390], rax
0x1800ad1cb  lea     rax, [rbp+2F0h+var_354]
0x1800ad1cf  mov     [rsp+580h+var_398], rax
0x1800ad1d7  lea     rax, [rbp+2F0h+var_2E0]
0x1800ad1db  mov     [rsp+580h+var_3A0], rax
0x1800ad1e3  lea     rax, [rbp+2F0h+var_2D8]
0x1800ad1e7  mov     [rsp+580h+var_3A8], rax
  ... truncated ...
```
