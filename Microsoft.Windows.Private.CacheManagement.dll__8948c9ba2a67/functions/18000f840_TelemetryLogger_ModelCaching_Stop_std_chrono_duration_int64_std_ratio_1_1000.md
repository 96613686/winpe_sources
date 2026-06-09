# TelemetryLogger::ModelCaching::Stop(std::chrono::duration<__int64,std::ratio<1,1000>>)

- ea: `0x18000f840`
- end: `0x18000fb67`
- name: `?Stop@ModelCaching@TelemetryLogger@@QEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z`
- size: `807`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007410`

## callees

- `0x180001120`
- `0x18000f840`
- `0x180010830`
- `0x1800108d0`
- `0x1800116f0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000fa5d`
- `KERNEL32!GetCurrentThreadId` at `0x18000fa5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fb35`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fb35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::ModelCaching::Stop(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  int v5; // eax
  __int64 v6; // r14
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // r14
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  unsigned int v12; // [rsp+B0h] [rbp-80h] BYREF
  int v13; // [rsp+B4h] [rbp-7Ch] BYREF
  DWORD v14; // [rsp+B8h] [rbp-78h] BYREF
  int v15; // [rsp+BCh] [rbp-74h] BYREF
  int v16; // [rsp+C0h] [rbp-70h] BYREF
  int v17; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v18; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v21; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v22; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v23; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v24; // [rsp+F8h] [rbp-38h] BYREF
  const wchar_t *v25; // [rsp+100h] [rbp-30h] BYREF
  const wchar_t *v26; // [rsp+108h] [rbp-28h] BYREF
  const wchar_t *v27; // [rsp+110h] [rbp-20h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+130h] [rbp+0h] BYREF
  char *v30; // [rsp+140h] [rbp+10h]
  int v31; // [rsp+148h] [rbp+18h]
  int v32; // [rsp+14Ch] [rbp+1Ch]
  __int64 *v33; // [rsp+150h] [rbp+20h]
  __int64 v34; // [rsp+158h] [rbp+28h]
  int *v35; // [rsp+160h] [rbp+30h]
  __int64 v36; // [rsp+168h] [rbp+38h]
  DWORD *v37; // [rsp+170h] [rbp+40h]
  __int64 v38; // [rsp+178h] [rbp+48h]
  __int64 *v39; // [rsp+180h] [rbp+50h]
  __int64 v40; // [rsp+188h] [rbp+58h]

  v2 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = v2 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = *(_QWORD *)(a1 + 272);
      v21 = *(const wchar_t **)(v6 + 120);
      v22 = *(const wchar_t **)(v6 + 112);
      v15 = *(_DWORD *)(v6 + 104);
      v23 = *(const wchar_t **)(v6 + 96);
      v24 = *(const wchar_t **)(v6 + 88);
      v16 = *(_DWORD *)(v6 + 80);
      v25 = *(const wchar_t **)(v6 + 72);
      v17 = *(_DWORD *)(v6 + 32);
      v26 = *(const wchar_t **)(v6 + 24);
      v12 = *(_DWORD *)v6;
      v27 = *(const wchar_t **)(v6 + 128);
      v13 = *(_DWORD *)(v6 + 64);
      *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)(v6 + 56);
      v14 = *(_DWORD *)(v6 + 8);
      v20 = a2;
      v18 = 0x1000000;
      v19 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned __int8 *)byte_1800270A7,
        (const GUID *)(v8 + 8),
        v7,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v14,
        (const wchar_t **)&EventDescriptor,
        (__int64)&v13,
        &v27,
        (__int64)&v12,
        &v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        &v23,
        (__int64)&v15,
        &v22,
        &v21,
        (__int64)&v20);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      v19 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *(_QWORD *)(a1 + 272);
      v14 = CurrentThreadId;
      v40 = 8;
      v38 = 4;
      v13 = *(_DWORD *)(v11 + 72);
      v39 = &v19;
      v37 = &v14;
      v35 = &v13;
      v33 = &v18;
      *(_DWORD *)&EventDescriptor.Level = 517;
      UserData.Ptr = *(_QWORD *)(v9 + 8);
      v18 = 0x1000000;
      v36 = 4;
      v34 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v30 = byte_1800271ED;
      UserData.Reserved = 2;
      v31 = 88;
      v32 = 1;
      v12 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v9 + 32), &EventDescriptor, (LPCGUID)(v11 + 8), 0, 6u, &UserData);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18000f840  mov     [rsp-8+arg_8], rbx
0x18000f845  mov     [rsp-8+arg_10], rsi
0x18000f84a  push    rbp
0x18000f84b  push    rdi
0x18000f84c  push    r14
0x18000f84e  lea     rbp, [rsp-70h]
0x18000f853  sub     rsp, 1A0h
0x18000f85a  mov     rax, cs:__security_cookie
0x18000f861  xor     rax, rsp
0x18000f864  mov     [rbp+80h+var_20], rax
0x18000f868  mov     r14, [rcx+110h]
0x18000f86f  mov     rbx, rdx
0x18000f872  mov     rsi, rcx
0x18000f875  mov     eax, [r14+48h]
0x18000f879  test    eax, eax
0x18000f87b  jns     loc_18000FA1C
0x18000f881  add     r14, 50h ; 'P'
0x18000f885  cmp     eax, [r14+8]
0x18000f889  jnz     loc_18000FA1C
0x18000f88f  test    r14, r14
0x18000f892  jz      loc_18000FA1C
0x18000f898  call    ?zInternalStop@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f89d  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000f8a2  mov     r9, [rax+8]
0x18000f8a6  cmp     dword ptr [r9], 5
0x18000f8aa  jbe     loc_18000FB3B
0x18000f8b0  mov     rdi, 400000000000h
0x18000f8ba  test    [r9+10h], rdi
0x18000f8be  jz      loc_18000FB3B
0x18000f8c4  mov     rax, [r9+18h]
0x18000f8c8  and     rax, rdi
0x18000f8cb  cmp     rax, [r9+18h]
0x18000f8cf  jnz     loc_18000FB3B
0x18000f8d5  mov     rax, [r14+78h]
0x18000f8d9  lea     rdx, byte_1800270A7
0x18000f8e0  mov     r8, [rsi+110h]
0x18000f8e7  mov     rcx, r9
0x18000f8ea  mov     [rbp+80h+var_D0], rax
0x18000f8ee  add     r8, 8
0x18000f8f2  mov     rax, [r14+70h]
0x18000f8f6  mov     [rbp+80h+var_C8], rax
0x18000f8fa  mov     eax, [r14+68h]
0x18000f8fe  mov     [rbp+80h+var_F4], eax
0x18000f901  mov     rax, [r14+60h]
0x18000f905  mov     [rbp+80h+var_C0], rax
0x18000f909  mov     rax, [r14+58h]
0x18000f90d  mov     [rbp+80h+var_B8], rax
0x18000f911  mov     eax, [r14+50h]
0x18000f915  mov     [rbp+80h+var_F0], eax
0x18000f918  mov     rax, [r14+48h]
0x18000f91c  mov     [rbp+80h+var_B0], rax
0x18000f920  mov     eax, [r14+20h]
0x18000f924  mov     [rbp+80h+var_EC], eax
0x18000f927  mov     rax, [r14+18h]
0x18000f92b  mov     [rbp+80h+var_A8], rax
0x18000f92f  mov     eax, [r14]
0x18000f932  mov     [rbp+80h+var_100], eax
0x18000f935  mov     rax, [r14+80h]
0x18000f93c  mov     [rbp+80h+var_A0], rax
0x18000f940  mov     eax, [r14+40h]
0x18000f944  mov     [rbp+80h+var_FC], eax
0x18000f947  mov     rax, [r14+38h]
0x18000f94b  mov     qword ptr [rbp+80h+EventDescriptor.Id], rax
0x18000f94f  mov     eax, [r14+8]
0x18000f953  mov     [rbp+80h+var_F8], eax
0x18000f956  lea     rax, [rbp+80h+var_D8]
0x18000f95a  mov     [rsp+1B0h+var_110], rax
0x18000f962  lea     rax, [rbp+80h+var_D0]
0x18000f966  mov     [rsp+1B0h+var_118], rax
0x18000f96e  lea     rax, [rbp+80h+var_C8]
0x18000f972  mov     [rsp+1B0h+var_120], rax
0x18000f97a  lea     rax, [rbp+80h+var_F4]
0x18000f97e  mov     [rsp+1B0h+var_128], rax
0x18000f986  lea     rax, [rbp+80h+var_C0]
0x18000f98a  mov     [rsp+1B0h+var_130], rax
0x18000f992  lea     rax, [rbp+80h+var_B8]
0x18000f996  mov     [rsp+1B0h+var_138], rax
0x18000f99b  lea     rax, [rbp+80h+var_F0]
0x18000f99f  mov     [rsp+1B0h+var_140], rax
0x18000f9a4  lea     rax, [rbp+80h+var_B0]
0x18000f9a8  mov     [rsp+1B0h+var_148], rax
0x18000f9ad  lea     rax, [rbp+80h+var_EC]
0x18000f9b1  mov     [rsp+1B0h+var_150], rax
0x18000f9b6  lea     rax, [rbp+80h+var_A8]
0x18000f9ba  mov     [rsp+1B0h+var_158], rax
0x18000f9bf  lea     rax, [rbp+80h+var_100]
0x18000f9c3  mov     [rsp+1B0h+var_160], rax
0x18000f9c8  lea     rax, [rbp+80h+var_A0]
0x18000f9cc  mov     [rsp+1B0h+var_168], rax
0x18000f9d1  lea     rax, [rbp+80h+var_FC]
0x18000f9d5  mov     [rsp+1B0h+var_170], rax
0x18000f9da  lea     rax, [rbp+80h+EventDescriptor]
0x18000f9de  mov     [rsp+1B0h+var_178], rax
0x18000f9e3  lea     rax, [rbp+80h+var_F8]
0x18000f9e7  mov     [rsp+1B0h+var_180], rax
0x18000f9ec  lea     rax, [rbp+80h+var_E8]
0x18000f9f0  mov     [rsp+1B0h+UserData], rax
0x18000f9f5  lea     rax, [rbp+80h+var_E0]
0x18000f9f9  mov     qword ptr [rsp+1B0h+UserDataCount], rax
0x18000f9fe  mov     [rbp+80h+var_D8], rbx
0x18000fa02  mov     [rbp+80h+var_E8], 1000000h
0x18000fa0a  mov     [rbp+80h+var_E0], 1000000h
0x18000fa12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x18000fa17  jmp     loc_18000FB3B
0x18000fa1c  call    ?zInternalStop@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000fa21  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000fa26  mov     r14, [rax+8]
0x18000fa2a  cmp     dword ptr [r14], 5
0x18000fa2e  jbe     loc_18000FB3B
0x18000fa34  mov     rdi, 400000000000h
0x18000fa3e  test    [r14+10h], rdi
0x18000fa42  jz      loc_18000FB3B
0x18000fa48  mov     rax, [r14+18h]
0x18000fa4c  and     rax, rdi
0x18000fa4f  cmp     rax, [r14+18h]
0x18000fa53  jnz     loc_18000FB3B
0x18000fa59  mov     [rbp+80h+var_E0], rbx
0x18000fa5d  call    cs:__imp_GetCurrentThreadId
0x18000fa63  mov     r8, [rsi+110h]
0x18000fa6a  lea     rcx, _TraceLoggingMetadata
0x18000fa71  mov     [rbp+80h+var_F8], eax
0x18000fa74  lea     rdx, [rbp+80h+EventDescriptor]; EventDescriptor
0x18000fa78  mov     [rbp+80h+var_28], 8
0x18000fa80  xor     r9d, r9d; RelatedActivityId
0x18000fa83  mov     [rbp+80h+var_38], 4
0x18000fa8b  mov     eax, [r8+48h]
0x18000fa8f  add     r8, 8; ActivityId
0x18000fa93  mov     [rbp+80h+var_FC], eax
0x18000fa96  lea     rax, [rbp+80h+var_E0]
0x18000fa9a  mov     [rbp+80h+var_30], rax
0x18000fa9e  lea     rax, [rbp+80h+var_F8]
0x18000faa2  mov     [rbp+80h+var_40], rax
0x18000faa6  lea     rax, [rbp+80h+var_FC]
0x18000faaa  mov     [rbp+80h+var_50], rax
0x18000faae  lea     rax, [rbp+80h+var_E8]
0x18000fab2  mov     [rbp+80h+var_60], rax
0x18000fab6  movzx   eax, cs:word_1800271E3
0x18000fabd  mov     dword ptr [rbp+80h+EventDescriptor.Level], eax
0x18000fac0  mov     rax, [r14+8]
0x18000fac4  mov     [rbp+80h+var_80.Ptr], rax
0x18000fac8  mov     [rbp+80h+var_E8], 1000000h
0x18000fad0  mov     [rbp+80h+var_48], 4
0x18000fad8  mov     [rbp+80h+var_58], 8
0x18000fae0  mov     dword ptr [rbp+80h+EventDescriptor.Id], 0B000000h
0x18000fae7  mov     [rbp+80h+EventDescriptor.Keyword], rdi
0x18000faeb  movzx   eax, word ptr [rax]
0x18000faee  mov     [rbp+80h+var_80.Size], eax
0x18000faf1  lea     rax, byte_1800271ED
0x18000faf8  mov     [rbp+80h+var_70], rax
0x18000fafc  lea     rax, _TraceLoggingMetadataEnd
0x18000fb03  sub     eax, ecx
0x18000fb05  mov     dword ptr [rbp+80h+var_80.0Ch], 2
0x18000fb0c  mov     [rbp+80h+var_68], 58h ; 'X'
0x18000fb13  mov     [rbp+80h+var_64], 1
0x18000fb1a  mov     [rbp+80h+var_100], eax
0x18000fb1d  mov     eax, [rbp+80h+var_100]
0x18000fb20  mov     rcx, [r14+20h]; RegHandle
0x18000fb24  lea     rax, [rbp+80h+var_80]
0x18000fb28  mov     [rsp+1B0h+UserData], rax; UserData
0x18000fb2d  mov     [rsp+1B0h+UserDataCount], 6; UserDataCount
0x18000fb35  call    cs:__imp_EventWriteTransfer
0x18000fb3b  mov     rcx, rsi
0x18000fb3e  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000fb43  mov     rcx, [rbp+80h+var_20]
0x18000fb47  xor     rcx, rsp; StackCookie
0x18000fb4a  call    __security_check_cookie
0x18000fb4f  lea     r11, [rsp+1B0h+var_10]
0x18000fb57  mov     rbx, [r11+28h]
0x18000fb5b  mov     rsi, [r11+30h]
0x18000fb5f  mov     rsp, r11
0x18000fb62  pop     r14
0x18000fb64  pop     rdi
0x18000fb65  pop     rbp
0x18000fb66  retn
```
