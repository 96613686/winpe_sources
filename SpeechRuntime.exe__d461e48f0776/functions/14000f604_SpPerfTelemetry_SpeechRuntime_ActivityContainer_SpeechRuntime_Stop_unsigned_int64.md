# SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::Stop(unsigned __int64)

- ea: `0x14000f604`
- end: `0x14000f8a0`
- name: `?Stop@SpeechRuntime@ActivityContainer@1SpPerfTelemetry@@QEAAX_K@Z`
- size: `668`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000fae0`

## callees

- `0x140001058`
- `0x140001544`
- `0x140001ffc`
- `0x140002d30`
- `0x14000c224`
- `0x14000d3cc`
- `0x14000f604`
- `0x140011588`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f7fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f7fa`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::Stop(
        SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *this,
        __int64 a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v15; // [rsp+B4h] [rbp-7Ch] BYREF
  int v16; // [rsp+B8h] [rbp-78h] BYREF
  int v17; // [rsp+BCh] [rbp-74h] BYREF
  int v18; // [rsp+C0h] [rbp-70h] BYREF
  int v19; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v20; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+100h] [rbp-30h] BYREF
  __int64 v28; // [rsp+108h] [rbp-28h] BYREF
  __int64 v29; // [rsp+110h] [rbp-20h] BYREF
  __int64 v30; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v32; // [rsp+140h] [rbp+10h]
  __int64 v33; // [rsp+148h] [rbp+18h]
  int *v34; // [rsp+150h] [rbp+20h]
  __int64 v35; // [rsp+158h] [rbp+28h]
  DWORD *v36; // [rsp+160h] [rbp+30h]
  __int64 v37; // [rsp+168h] [rbp+38h]
  __int64 *v38; // [rsp+170h] [rbp+40h]
  __int64 v39; // [rsp+178h] [rbp+48h]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = FlightDataRecorderActivityClass::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 15);
      v24 = *((_QWORD *)v6 + 14);
      v16 = v6[26];
      v25 = *((_QWORD *)v6 + 12);
      v26 = *((_QWORD *)v6 + 11);
      v17 = v6[20];
      v27 = *((_QWORD *)v6 + 9);
      v18 = v6[8];
      v28 = *((_QWORD *)v6 + 3);
      v19 = *v6;
      v29 = *((_QWORD *)v6 + 16);
      v14 = v6[16];
      v30 = *((_QWORD *)v6 + 7);
      v15 = v6[2];
      v22 = a2;
      v20 = 0x1000000;
      v21 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v8,
        (unsigned int)byte_140042553,
        v9 + 8,
        v8,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v15,
        (__int64)&v30,
        (__int64)&v14,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = FlightDataRecorderActivityClass::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
    {
      v21 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v15 = CurrentThreadId;
      v39 = 8;
      v37 = 4;
      v14 = *(_DWORD *)(v13 + 72);
      v38 = &v21;
      v36 = &v15;
      v34 = &v14;
      v32 = &v20;
      v20 = 0;
      v35 = 4;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(v11, (unsigned __int8 *)byte_140042E8B, (const GUID *)(v13 + 8), 0, 6u, &v31);
    }
  }
  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x14000f604  push    rbp
0x14000f606  push    rbx
0x14000f607  push    rsi
0x14000f608  push    rdi
0x14000f609  lea     rbp, [rsp-68h]
0x14000f60e  sub     rsp, 198h
0x14000f615  mov     rax, cs:__security_cookie
0x14000f61c  xor     rax, rsp
0x14000f61f  mov     [rbp+80h+var_30], rax
0x14000f623  mov     rdi, [rcx+110h]
0x14000f62a  mov     rsi, rdx
0x14000f62d  mov     rbx, rcx
0x14000f630  mov     eax, [rdi+48h]
0x14000f633  test    eax, eax
0x14000f635  jns     loc_14000F7C4
0x14000f63b  add     rdi, 50h ; 'P'
0x14000f63f  cmp     eax, [rdi+8]
0x14000f642  jnz     loc_14000F7C4
0x14000f648  test    rdi, rdi
0x14000f64b  jz      loc_14000F7C4
0x14000f651  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000f656  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000f65b  mov     r9, rax
0x14000f65e  mov     ecx, [rax]
0x14000f660  cmp     ecx, 5
0x14000f663  jbe     loc_14000F880
0x14000f669  mov     rdx, 400000000000h
0x14000f673  mov     rcx, rax
0x14000f676  call    _tlgKeywordOn
0x14000f67b  test    al, al
0x14000f67d  jz      loc_14000F880
0x14000f683  mov     rax, [rdi+78h]
0x14000f687  lea     rdx, byte_140042553
0x14000f68e  mov     r8, [rbx+110h]
0x14000f695  mov     rcx, r9
0x14000f698  mov     [rbp+80h+var_D0], rax
0x14000f69c  add     r8, 8
0x14000f6a0  mov     rax, [rdi+70h]
0x14000f6a4  mov     [rbp+80h+var_C8], rax
0x14000f6a8  mov     eax, [rdi+68h]
0x14000f6ab  mov     [rbp+80h+var_F8], eax
0x14000f6ae  mov     rax, [rdi+60h]
0x14000f6b2  mov     [rbp+80h+var_C0], rax
0x14000f6b6  mov     rax, [rdi+58h]
0x14000f6ba  mov     [rbp+80h+var_B8], rax
0x14000f6be  mov     eax, [rdi+50h]
0x14000f6c1  mov     [rbp+80h+var_F4], eax
0x14000f6c4  mov     rax, [rdi+48h]
0x14000f6c8  mov     [rbp+80h+var_B0], rax
0x14000f6cc  mov     eax, [rdi+20h]
0x14000f6cf  mov     [rbp+80h+var_F0], eax
0x14000f6d2  mov     rax, [rdi+18h]
0x14000f6d6  mov     [rbp+80h+var_A8], rax
0x14000f6da  mov     eax, [rdi]
0x14000f6dc  mov     [rbp+80h+var_EC], eax
0x14000f6df  mov     rax, [rdi+80h]
0x14000f6e6  mov     [rbp+80h+var_A0], rax
0x14000f6ea  mov     eax, [rdi+40h]
0x14000f6ed  mov     [rbp+80h+var_100], eax
0x14000f6f0  mov     rax, [rdi+38h]
0x14000f6f4  mov     [rbp+80h+var_98], rax
0x14000f6f8  mov     eax, [rdi+8]
0x14000f6fb  mov     [rbp+80h+var_FC], eax
0x14000f6fe  lea     rax, [rbp+80h+var_D8]
0x14000f702  mov     [rsp+1B0h+var_110], rax
0x14000f70a  lea     rax, [rbp+80h+var_D0]
0x14000f70e  mov     [rsp+1B0h+var_118], rax
0x14000f716  lea     rax, [rbp+80h+var_C8]
0x14000f71a  mov     [rsp+1B0h+var_120], rax
0x14000f722  lea     rax, [rbp+80h+var_F8]
0x14000f726  mov     [rsp+1B0h+var_128], rax
0x14000f72e  lea     rax, [rbp+80h+var_C0]
0x14000f732  mov     [rsp+1B0h+var_130], rax
0x14000f73a  lea     rax, [rbp+80h+var_B8]
0x14000f73e  mov     [rsp+1B0h+var_138], rax
0x14000f743  lea     rax, [rbp+80h+var_F4]
0x14000f747  mov     [rsp+1B0h+var_140], rax
0x14000f74c  lea     rax, [rbp+80h+var_B0]
0x14000f750  mov     [rsp+1B0h+var_148], rax
0x14000f755  lea     rax, [rbp+80h+var_F0]
0x14000f759  mov     [rsp+1B0h+var_150], rax
0x14000f75e  lea     rax, [rbp+80h+var_A8]
0x14000f762  mov     [rsp+1B0h+var_158], rax
0x14000f767  lea     rax, [rbp+80h+var_EC]
0x14000f76b  mov     [rsp+1B0h+var_160], rax
0x14000f770  lea     rax, [rbp+80h+var_A0]
0x14000f774  mov     [rsp+1B0h+var_168], rax
0x14000f779  lea     rax, [rbp+80h+var_100]
0x14000f77d  mov     [rsp+1B0h+var_170], rax
0x14000f782  lea     rax, [rbp+80h+var_98]
0x14000f786  mov     [rsp+1B0h+var_178], rax
0x14000f78b  lea     rax, [rbp+80h+var_FC]
0x14000f78f  mov     [rsp+1B0h+var_180], rax
0x14000f794  lea     rax, [rbp+80h+var_E8]
0x14000f798  mov     [rsp+1B0h+var_188], rax
0x14000f79d  lea     rax, [rbp+80h+var_E0]
0x14000f7a1  mov     [rsp+1B0h+var_190], rax
0x14000f7a6  mov     [rbp+80h+var_D8], rsi
0x14000f7aa  mov     [rbp+80h+var_E8], 1000000h
0x14000f7b2  mov     [rbp+80h+var_E0], 0
0x14000f7ba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14000f7bf  jmp     loc_14000F880
0x14000f7c4  call    ?zInternalStop@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000f7c9  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000f7ce  mov     rdi, rax
0x14000f7d1  mov     ecx, [rax]
0x14000f7d3  cmp     ecx, 5
0x14000f7d6  jbe     loc_14000F880
0x14000f7dc  mov     rdx, 400000000000h
0x14000f7e6  mov     rcx, rax
0x14000f7e9  call    _tlgKeywordOn
0x14000f7ee  test    al, al
0x14000f7f0  jz      loc_14000F880
0x14000f7f6  mov     [rbp+80h+var_E0], rsi
0x14000f7fa  call    cs:__imp_GetCurrentThreadId
0x14000f800  mov     r8, [rbx+110h]
0x14000f807  lea     rdx, byte_140042E8B
0x14000f80e  mov     [rbp+80h+var_FC], eax
0x14000f811  xor     r9d, r9d
0x14000f814  mov     rcx, rdi
0x14000f817  mov     [rbp+80h+var_38], 8
0x14000f81f  mov     [rbp+80h+var_48], 4
0x14000f827  mov     eax, [r8+48h]
0x14000f82b  add     r8, 8
0x14000f82f  mov     [rbp+80h+var_100], eax
0x14000f832  lea     rax, [rbp+80h+var_E0]
0x14000f836  mov     [rbp+80h+var_40], rax
0x14000f83a  lea     rax, [rbp+80h+var_FC]
0x14000f83e  mov     [rbp+80h+var_50], rax
0x14000f842  lea     rax, [rbp+80h+var_100]
0x14000f846  mov     [rbp+80h+var_60], rax
0x14000f84a  lea     rax, [rbp+80h+var_E8]
0x14000f84e  mov     [rbp+80h+var_70], rax
0x14000f852  lea     rax, [rbp+80h+var_90]
0x14000f856  mov     [rsp+1B0h+var_188], rax
0x14000f85b  mov     dword ptr [rsp+1B0h+var_190], 6
0x14000f863  mov     [rbp+80h+var_E8], 0
0x14000f86b  mov     [rbp+80h+var_58], 4
0x14000f873  mov     [rbp+80h+var_68], 8
0x14000f87b  call    _tlgWriteTransfer_EventWriteTransfer
0x14000f880  mov     rcx, rbx
0x14000f883  call    ?IgnoreCurrentThread@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000f888  mov     rcx, [rbp+80h+var_30]
0x14000f88c  xor     rcx, rsp; StackCookie
0x14000f88f  call    __security_check_cookie
0x14000f894  add     rsp, 198h
0x14000f89b  pop     rdi
0x14000f89c  pop     rsi
0x14000f89d  pop     rbx
0x14000f89e  pop     rbp
0x14000f89f  retn
```
