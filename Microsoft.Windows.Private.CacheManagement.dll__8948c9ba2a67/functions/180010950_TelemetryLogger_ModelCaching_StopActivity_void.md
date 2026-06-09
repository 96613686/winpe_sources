# TelemetryLogger::ModelCaching::StopActivity(void)

- ea: `0x180010950`
- end: `0x180010c4a`
- name: `?StopActivity@ModelCaching@TelemetryLogger@@MEAAXXZ`
- size: `762`
- prototype: `void __fastcall(TelemetryLogger::ModelCaching *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001970`
- `0x180010830`
- `0x1800108d0`
- `0x180010950`
- `0x1800116f0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010b4f`
- `KERNEL32!GetCurrentThreadId` at `0x180010b4f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010c17`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010c17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::ModelCaching::StopActivity(TelemetryLogger::ModelCaching *this)
{
  __int64 v1; // rsi
  int v3; // eax
  __int64 v4; // rsi
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  unsigned int v10; // [rsp+A0h] [rbp-80h] BYREF
  int v11; // [rsp+A4h] [rbp-7Ch] BYREF
  DWORD v12; // [rsp+A8h] [rbp-78h] BYREF
  int v13; // [rsp+ACh] [rbp-74h] BYREF
  int v14; // [rsp+B0h] [rbp-70h] BYREF
  int v15; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v16; // [rsp+B8h] [rbp-68h] BYREF
  const wchar_t *v17; // [rsp+C0h] [rbp-60h] BYREF
  const wchar_t *v18; // [rsp+C8h] [rbp-58h] BYREF
  const wchar_t *v19; // [rsp+D0h] [rbp-50h] BYREF
  const wchar_t *v20; // [rsp+D8h] [rbp-48h] BYREF
  const wchar_t *v21; // [rsp+E0h] [rbp-40h] BYREF
  const wchar_t *v22; // [rsp+E8h] [rbp-38h] BYREF
  const wchar_t *v23; // [rsp+F0h] [rbp-30h] BYREF
  const wchar_t *v24; // [rsp+F8h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+100h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+110h] [rbp-10h] BYREF
  __int16 *v27; // [rsp+120h] [rbp+0h]
  int v28; // [rsp+128h] [rbp+8h]
  int v29; // [rsp+12Ch] [rbp+Ch]
  __int64 *v30; // [rsp+130h] [rbp+10h]
  __int64 v31; // [rsp+138h] [rbp+18h]
  int *v32; // [rsp+140h] [rbp+20h]
  __int64 v33; // [rsp+148h] [rbp+28h]
  DWORD *v34; // [rsp+150h] [rbp+30h]
  __int64 v35; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = v1 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v6 = *((_QWORD *)this + 34);
      v17 = *(const wchar_t **)(v4 + 120);
      v18 = *(const wchar_t **)(v4 + 112);
      v13 = *(_DWORD *)(v4 + 104);
      v19 = *(const wchar_t **)(v4 + 96);
      v20 = *(const wchar_t **)(v4 + 88);
      v14 = *(_DWORD *)(v4 + 80);
      v21 = *(const wchar_t **)(v4 + 72);
      v15 = *(_DWORD *)(v4 + 32);
      v22 = *(const wchar_t **)(v4 + 24);
      v10 = *(_DWORD *)v4;
      v23 = *(const wchar_t **)(v4 + 128);
      v11 = *(_DWORD *)(v4 + 64);
      v24 = *(const wchar_t **)(v4 + 56);
      v12 = *(_DWORD *)(v4 + 8);
      *(_QWORD *)&EventDescriptor.Id = 0x1000000;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v5,
        (unsigned __int8 *)byte_180027493,
        (const GUID *)(v6 + 8),
        v5,
        (__int64)&v16,
        (__int64)&EventDescriptor,
        (__int64)&v12,
        &v24,
        (__int64)&v11,
        &v23,
        (__int64)&v10,
        &v22,
        (__int64)&v15,
        &v21,
        (__int64)&v14,
        &v20,
        &v19,
        (__int64)&v13,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v12 = CurrentThreadId;
      v35 = 4;
      v33 = 4;
      v11 = *(_DWORD *)(v9 + 72);
      v34 = &v12;
      v32 = &v11;
      v30 = &v16;
      *(_DWORD *)&EventDescriptor.Level = 517;
      UserData.Ptr = *(_QWORD *)(v7 + 8);
      v16 = 0x1000000;
      v31 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v27 = word_1800275C2;
      UserData.Reserved = 2;
      v28 = 65;
      v29 = 1;
      v10 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v9 + 8), 0, 5u, &UserData);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180010950  mov     [rsp-8+arg_8], rbx
0x180010955  mov     [rsp-8+arg_10], rsi
0x18001095a  mov     [rsp-8+arg_18], rdi
0x18001095f  push    rbp
0x180010960  lea     rbp, [rsp-50h]
0x180010965  sub     rsp, 170h
0x18001096c  mov     rax, cs:__security_cookie
0x180010973  xor     rax, rsp
0x180010976  mov     [rbp+50h+var_10], rax
0x18001097a  mov     rsi, [rcx+110h]
0x180010981  mov     rdi, rcx
0x180010984  mov     eax, [rsi+48h]
0x180010987  test    eax, eax
0x180010989  jns     loc_180010B13
0x18001098f  add     rsi, 50h ; 'P'
0x180010993  cmp     eax, [rsi+8]
0x180010996  jnz     loc_180010B13
0x18001099c  test    rsi, rsi
0x18001099f  jz      loc_180010B13
0x1800109a5  call    ?zInternalStop@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800109aa  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800109af  mov     r9, [rax+8]
0x1800109b3  cmp     dword ptr [r9], 5
0x1800109b7  jbe     loc_180010C1D
0x1800109bd  mov     rbx, 400000000000h
0x1800109c7  test    [r9+10h], rbx
0x1800109cb  jz      loc_180010C1D
0x1800109d1  mov     rax, [r9+18h]
0x1800109d5  and     rax, rbx
0x1800109d8  cmp     rax, [r9+18h]
0x1800109dc  jnz     loc_180010C1D
0x1800109e2  mov     rax, [rsi+78h]
0x1800109e6  lea     rdx, byte_180027493
0x1800109ed  mov     r8, [rdi+110h]
0x1800109f4  mov     rcx, r9
0x1800109f7  mov     [rbp+50h+var_B0], rax
0x1800109fb  add     r8, 8
0x1800109ff  mov     rax, [rsi+70h]
0x180010a03  mov     [rbp+50h+var_A8], rax
0x180010a07  mov     eax, [rsi+68h]
0x180010a0a  mov     [rbp+50h+var_C4], eax
0x180010a0d  mov     rax, [rsi+60h]
0x180010a11  mov     [rbp+50h+var_A0], rax
0x180010a15  mov     rax, [rsi+58h]
0x180010a19  mov     [rbp+50h+var_98], rax
0x180010a1d  mov     eax, [rsi+50h]
0x180010a20  mov     [rbp+50h+var_C0], eax
0x180010a23  mov     rax, [rsi+48h]
0x180010a27  mov     [rbp+50h+var_90], rax
0x180010a2b  mov     eax, [rsi+20h]
0x180010a2e  mov     [rbp+50h+var_BC], eax
0x180010a31  mov     rax, [rsi+18h]
0x180010a35  mov     [rbp+50h+var_88], rax
0x180010a39  mov     eax, [rsi]
0x180010a3b  mov     [rbp+50h+var_D0], eax
0x180010a3e  mov     rax, [rsi+80h]
0x180010a45  mov     [rbp+50h+var_80], rax
0x180010a49  mov     eax, [rsi+40h]
0x180010a4c  mov     [rbp+50h+var_CC], eax
0x180010a4f  mov     rax, [rsi+38h]
0x180010a53  mov     [rbp+50h+var_78], rax
0x180010a57  mov     eax, [rsi+8]
0x180010a5a  mov     [rbp+50h+var_C8], eax
0x180010a5d  lea     rax, [rbp+50h+var_B0]
0x180010a61  mov     [rsp+170h+var_D8], rax
0x180010a69  lea     rax, [rbp+50h+var_A8]
0x180010a6d  mov     [rsp+170h+var_E0], rax
0x180010a75  lea     rax, [rbp+50h+var_C4]
0x180010a79  mov     [rsp+170h+var_E8], rax
0x180010a81  lea     rax, [rbp+50h+var_A0]
0x180010a85  mov     [rsp+170h+var_F0], rax
0x180010a8d  lea     rax, [rbp+50h+var_98]
0x180010a91  mov     [rsp+170h+var_F8], rax
0x180010a96  lea     rax, [rbp+50h+var_C0]
0x180010a9a  mov     [rsp+170h+var_100], rax
0x180010a9f  lea     rax, [rbp+50h+var_90]
0x180010aa3  mov     [rsp+170h+var_108], rax
0x180010aa8  lea     rax, [rbp+50h+var_BC]
0x180010aac  mov     [rsp+170h+var_110], rax
0x180010ab1  lea     rax, [rbp+50h+var_88]
0x180010ab5  mov     [rsp+170h+var_118], rax
0x180010aba  lea     rax, [rbp+50h+var_D0]
0x180010abe  mov     [rsp+170h+var_120], rax
0x180010ac3  lea     rax, [rbp+50h+var_80]
0x180010ac7  mov     [rsp+170h+var_128], rax
0x180010acc  lea     rax, [rbp+50h+var_CC]
0x180010ad0  mov     [rsp+170h+var_130], rax
0x180010ad5  lea     rax, [rbp+50h+var_78]
0x180010ad9  mov     [rsp+170h+var_138], rax
0x180010ade  lea     rax, [rbp+50h+var_C8]
0x180010ae2  mov     [rsp+170h+var_140], rax
0x180010ae7  lea     rax, [rbp+50h+EventDescriptor]
0x180010aeb  mov     [rsp+170h+UserData], rax
0x180010af0  lea     rax, [rbp+50h+var_B8]
0x180010af4  mov     qword ptr [rsp+170h+UserDataCount], rax
0x180010af9  mov     qword ptr [rbp+50h+EventDescriptor.Id], 1000000h
0x180010b01  mov     [rbp+50h+var_B8], 1000000h
0x180010b09  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180010b0e  jmp     loc_180010C1D
0x180010b13  call    ?zInternalStop@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180010b18  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180010b1d  mov     rsi, [rax+8]
0x180010b21  cmp     dword ptr [rsi], 5
0x180010b24  jbe     loc_180010C1D
0x180010b2a  mov     rbx, 400000000000h
0x180010b34  test    [rsi+10h], rbx
0x180010b38  jz      loc_180010C1D
0x180010b3e  mov     rax, [rsi+18h]
0x180010b42  and     rax, rbx
0x180010b45  cmp     rax, [rsi+18h]
0x180010b49  jnz     loc_180010C1D
0x180010b4f  call    cs:__imp_GetCurrentThreadId
0x180010b55  mov     r8, [rdi+110h]
0x180010b5c  lea     rcx, _TraceLoggingMetadata
0x180010b63  mov     [rbp+50h+var_C8], eax
0x180010b66  lea     rdx, [rbp+50h+EventDescriptor]; EventDescriptor
0x180010b6a  mov     [rbp+50h+var_18], 4
0x180010b72  xor     r9d, r9d; RelatedActivityId
0x180010b75  mov     [rbp+50h+var_28], 4
0x180010b7d  mov     eax, [r8+48h]
0x180010b81  add     r8, 8; ActivityId
0x180010b85  mov     [rbp+50h+var_CC], eax
0x180010b88  lea     rax, [rbp+50h+var_C8]
0x180010b8c  mov     [rbp+50h+var_20], rax
0x180010b90  lea     rax, [rbp+50h+var_CC]
0x180010b94  mov     [rbp+50h+var_30], rax
0x180010b98  lea     rax, [rbp+50h+var_B8]
0x180010b9c  mov     [rbp+50h+var_40], rax
0x180010ba0  movzx   eax, cs:word_1800275B8
0x180010ba7  mov     dword ptr [rbp+50h+EventDescriptor.Level], eax
0x180010baa  mov     rax, [rsi+8]
0x180010bae  mov     [rbp+50h+var_60.Ptr], rax
0x180010bb2  mov     [rbp+50h+var_B8], 1000000h
0x180010bba  mov     [rbp+50h+var_38], 8
0x180010bc2  mov     dword ptr [rbp+50h+EventDescriptor.Id], 0B000000h
0x180010bc9  mov     [rbp+50h+EventDescriptor.Keyword], rbx
0x180010bcd  movzx   eax, word ptr [rax]
0x180010bd0  mov     [rbp+50h+var_60.Size], eax
0x180010bd3  lea     rax, word_1800275C2
0x180010bda  mov     [rbp+50h+var_50], rax
0x180010bde  lea     rax, _TraceLoggingMetadataEnd
0x180010be5  sub     eax, ecx
0x180010be7  mov     dword ptr [rbp+50h+var_60.0Ch], 2
0x180010bee  mov     [rbp+50h+var_48], 41h ; 'A'
0x180010bf5  mov     [rbp+50h+var_44], 1
0x180010bfc  mov     [rbp+50h+var_D0], eax
0x180010bff  mov     eax, [rbp+50h+var_D0]
0x180010c02  mov     rcx, [rsi+20h]; RegHandle
0x180010c06  lea     rax, [rbp+50h+var_60]
0x180010c0a  mov     [rsp+170h+UserData], rax; UserData
0x180010c0f  mov     [rsp+170h+UserDataCount], 5; UserDataCount
0x180010c17  call    cs:__imp_EventWriteTransfer
0x180010c1d  mov     rcx, rdi
0x180010c20  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180010c25  mov     rcx, [rbp+50h+var_10]
0x180010c29  xor     rcx, rsp; StackCookie
0x180010c2c  call    __security_check_cookie
0x180010c31  lea     r11, [rsp+170h+var_s0]
0x180010c39  mov     rbx, [r11+18h]
0x180010c3d  mov     rsi, [r11+20h]
0x180010c41  mov     rdi, [r11+28h]
0x180010c45  mov     rsp, r11
0x180010c48  pop     rbp
0x180010c49  retn
```
