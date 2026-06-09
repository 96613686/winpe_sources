# SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::StopActivity(void)

- ea: `0x14000f8b0`
- end: `0x14000fad7`
- name: `?StopActivity@SpeechRuntime@ActivityContainer@1SpPerfTelemetry@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400012bc`
- `0x140001b28`
- `0x140001ffc`
- `0x14000c224`
- `0x14000d3cc`
- `0x14000f8b0`
- `0x140011588`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fa75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fa75`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::StopActivity(
        SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  int v6; // r9d
  __int64 v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  int v10; // edi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v25; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = FlightDataRecorderActivityClass::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v7 = *((_QWORD *)v4 + 15);
      v8 = *((_QWORD *)this + 34);
      v16 = *((_QWORD *)v4 + 14);
      v25 = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v14 = v4[2];
      v15 = v7;
      v23 = 0x1000000;
      v24[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&byte_1400434EF,
        v8 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = FlightDataRecorderActivityClass::Provider();
    v10 = (int)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v25 = CurrentThreadId;
      v26 = *(_DWORD *)(v12 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_14004339B,
        v12 + 8,
        0,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25);
    }
  }
  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x14000f8b0  push    rbp
0x14000f8b2  push    rbx
0x14000f8b3  push    rdi
0x14000f8b4  lea     rbp, [rsp-47h]
0x14000f8b9  sub     rsp, 100h
0x14000f8c0  mov     rdi, [rcx+110h]
0x14000f8c7  mov     rbx, rcx
0x14000f8ca  mov     eax, [rdi+48h]
0x14000f8cd  test    eax, eax
0x14000f8cf  jns     loc_14000FA4B
0x14000f8d5  add     rdi, 50h ; 'P'
0x14000f8d9  cmp     eax, [rdi+8]
0x14000f8dc  jnz     loc_14000FA4B
0x14000f8e2  test    rdi, rdi
0x14000f8e5  jz      loc_14000FA4B
0x14000f8eb  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000f8f0  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000f8f5  mov     r9, rax
0x14000f8f8  mov     ecx, [rax]
0x14000f8fa  cmp     ecx, 5
0x14000f8fd  jbe     loc_14000FAC5
0x14000f903  mov     rdx, 400000000000h
0x14000f90d  mov     rcx, rax
0x14000f910  call    _tlgKeywordOn
0x14000f915  test    al, al
0x14000f917  jz      loc_14000FAC5
0x14000f91d  mov     rax, [rdi+70h]
0x14000f921  lea     rdx, byte_1400434EF
0x14000f928  mov     rcx, [rdi+78h]
0x14000f92c  mov     r8, [rbx+110h]
0x14000f933  mov     [rbp+57h+var_60], rax
0x14000f937  add     r8, 8
0x14000f93b  mov     eax, [rdi+68h]
0x14000f93e  mov     [rbp+57h+arg_0], eax
0x14000f941  mov     rax, [rdi+60h]
0x14000f945  mov     [rbp+57h+var_58], rax
0x14000f949  mov     rax, [rdi+58h]
0x14000f94d  mov     [rbp+57h+var_50], rax
0x14000f951  mov     eax, [rdi+50h]
0x14000f954  mov     [rbp+57h+arg_8], eax
0x14000f957  mov     rax, [rdi+48h]
0x14000f95b  mov     [rbp+57h+var_48], rax
0x14000f95f  mov     eax, [rdi+20h]
0x14000f962  mov     dword ptr [rbp+57h+arg_10], eax
0x14000f965  mov     rax, [rdi+18h]
0x14000f969  mov     [rbp+57h+var_40], rax
0x14000f96d  mov     eax, [rdi]
0x14000f96f  mov     [rbp+57h+arg_18], eax
0x14000f972  mov     rax, [rdi+80h]
0x14000f979  mov     [rbp+57h+var_38], rax
0x14000f97d  mov     eax, [rdi+40h]
0x14000f980  mov     [rbp+57h+var_70], eax
0x14000f983  mov     rax, [rdi+38h]
0x14000f987  mov     [rbp+57h+var_30], rax
0x14000f98b  mov     eax, [rdi+8]
0x14000f98e  mov     [rbp+57h+var_6C], eax
0x14000f991  lea     rax, [rbp+57h+var_68]
0x14000f995  mov     [rsp+110h+var_78], rax
0x14000f99d  lea     rax, [rbp+57h+var_60]
0x14000f9a1  mov     [rsp+110h+var_80], rax
0x14000f9a9  lea     rax, [rbp+57h+arg_0]
0x14000f9ad  mov     [rsp+110h+var_88], rax
0x14000f9b5  lea     rax, [rbp+57h+var_58]
0x14000f9b9  mov     [rsp+110h+var_90], rax
0x14000f9c1  lea     rax, [rbp+57h+var_50]
0x14000f9c5  mov     [rsp+110h+var_98], rax
0x14000f9ca  lea     rax, [rbp+57h+arg_8]
0x14000f9ce  mov     [rsp+110h+var_A0], rax
0x14000f9d3  lea     rax, [rbp+57h+var_48]
0x14000f9d7  mov     [rsp+110h+var_A8], rax
0x14000f9dc  lea     rax, [rbp+57h+arg_10]
0x14000f9e0  mov     [rsp+110h+var_B0], rax
0x14000f9e5  lea     rax, [rbp+57h+var_40]
0x14000f9e9  mov     [rsp+110h+var_B8], rax
0x14000f9ee  lea     rax, [rbp+57h+arg_18]
0x14000f9f2  mov     [rsp+110h+var_C0], rax
0x14000f9f7  lea     rax, [rbp+57h+var_38]
0x14000f9fb  mov     [rsp+110h+var_C8], rax
0x14000fa00  lea     rax, [rbp+57h+var_70]
0x14000fa04  mov     [rsp+110h+var_D0], rax
0x14000fa09  lea     rax, [rbp+57h+var_30]
0x14000fa0d  mov     [rsp+110h+var_D8], rax
0x14000fa12  lea     rax, [rbp+57h+var_6C]
0x14000fa16  mov     [rsp+110h+var_E0], rax
0x14000fa1b  lea     rax, [rbp+57h+var_28]
0x14000fa1f  mov     [rsp+110h+var_E8], rax
0x14000fa24  lea     rax, [rbp+57h+var_20]
0x14000fa28  mov     [rbp+57h+var_68], rcx
0x14000fa2c  mov     rcx, r9
0x14000fa2f  mov     [rsp+110h+var_F0], rax
0x14000fa34  mov     [rbp+57h+var_28], 1000000h
0x14000fa3c  mov     [rbp+57h+var_20], 0
0x14000fa44  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000fa49  jmp     short loc_14000FAC5
0x14000fa4b  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000fa50  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000fa55  mov     rdi, rax
0x14000fa58  mov     ecx, [rax]
0x14000fa5a  cmp     ecx, 5
0x14000fa5d  jbe     short loc_14000FAC5
0x14000fa5f  mov     rdx, 400000000000h
0x14000fa69  mov     rcx, rax
0x14000fa6c  call    _tlgKeywordOn
0x14000fa71  test    al, al
0x14000fa73  jz      short loc_14000FAC5
0x14000fa75  call    cs:__imp_GetCurrentThreadId
0x14000fa7b  mov     r8, [rbx+110h]
0x14000fa82  lea     rdx, byte_14004339B
0x14000fa89  mov     [rbp+57h+arg_0], eax
0x14000fa8c  xor     r9d, r9d
0x14000fa8f  mov     rcx, rdi
0x14000fa92  mov     eax, [r8+48h]
0x14000fa96  add     r8, 8
0x14000fa9a  mov     [rbp+57h+arg_8], eax
0x14000fa9d  lea     rax, [rbp+57h+arg_0]
0x14000faa1  mov     [rsp+110h+var_E0], rax
0x14000faa6  lea     rax, [rbp+57h+arg_8]
0x14000faaa  mov     [rsp+110h+var_E8], rax
0x14000faaf  lea     rax, [rbp+57h+arg_10]
0x14000fab3  mov     [rsp+110h+var_F0], rax
0x14000fab8  mov     [rbp+57h+arg_10], 0
0x14000fac0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000fac5  mov     rcx, rbx
0x14000fac8  add     rsp, 100h
0x14000facf  pop     rdi
0x14000fad0  pop     rbx
0x14000fad1  pop     rbp
0x14000fad2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
