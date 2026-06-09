# NetworkUxTelemetry::SetAirplaneMode::Stop(bool)

- ea: `0x1800313dc`
- end: `0x180031679`
- name: `?Stop@SetAirplaneMode@NetworkUxTelemetry@@QEAAX_N@Z`
- size: `669`
- prototype: `void __fastcall(NetworkUxTelemetry::SetAirplaneMode *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180029380`

## callees

- `0x180001444`
- `0x180001dfc`
- `0x180001e28`
- `0x180002520`
- `0x18002d5a0`
- `0x1800313dc`
- `0x1800356dc`
- `0x180037a40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800315d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800315d3`

## pseudocode

```c
void __fastcall NetworkUxTelemetry::SetAirplaneMode::Stop(
        NetworkUxTelemetry::SetAirplaneMode *this,
        unsigned __int8 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // r8
  _DWORD *v8; // r9
  __int64 v9; // r9
  __int64 v10; // r8
  _DWORD *v11; // rdi
  __int64 v12; // r8
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v16; // [rsp+B4h] [rbp-7Ch] BYREF
  int v17; // [rsp+B8h] [rbp-78h] BYREF
  int v18; // [rsp+BCh] [rbp-74h] BYREF
  int v19; // [rsp+C0h] [rbp-70h] BYREF
  int v20; // [rsp+C4h] [rbp-6Ch] BYREF
  int v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+110h] [rbp-20h] BYREF
  __int64 v31; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v33; // [rsp+140h] [rbp+10h]
  __int64 v34; // [rsp+148h] [rbp+18h]
  int *v35; // [rsp+150h] [rbp+20h]
  __int64 v36; // [rsp+158h] [rbp+28h]
  DWORD *v37; // [rsp+160h] [rbp+30h]
  __int64 v38; // [rsp+168h] [rbp+38h]
  int *v39; // [rsp+170h] [rbp+40h]
  __int64 v40; // [rsp+178h] [rbp+48h]

  v2 = *((_QWORD *)this + 34);
  v4 = a2;
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
    if ( *v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v7) )
    {
      v10 = *((_QWORD *)this + 34);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 15);
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v19 = v6[26];
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 12);
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v20 = v6[20];
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v21 = v6[8];
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 3);
      v15 = *v6;
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v16 = v6[16];
      v30 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v17 = v6[2];
      v18 = v4;
      v31 = 0x1000000;
      v22 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)byte_180074819,
        v10 + 8,
        v9,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v17,
        &v30,
        (__int64)&v16,
        &v29,
        (__int64)&v15,
        &v28,
        (__int64)&v21,
        &v27,
        (__int64)&v20,
        &v26,
        &v25,
        (__int64)&v19,
        &v24,
        &v23,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
    if ( *v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12) )
    {
      v17 = v4;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v16 = CurrentThreadId;
      v40 = 4;
      v38 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      v39 = &v17;
      v37 = &v16;
      v35 = &v15;
      v33 = &v22;
      v22 = 0;
      v36 = 4;
      v34 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v11,
        (unsigned __int8 *)word_18007494A,
        (const GUID *)(v14 + 8),
        0,
        6u,
        &v32);
    }
  }
  wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800313dc  push    rbp
0x1800313de  push    rbx
0x1800313df  push    rsi
0x1800313e0  push    rdi
0x1800313e1  lea     rbp, [rsp-68h]
0x1800313e6  sub     rsp, 198h
0x1800313ed  mov     rax, cs:__security_cookie
0x1800313f4  xor     rax, rsp
0x1800313f7  mov     [rbp+80h+var_30], rax
0x1800313fb  mov     rdi, [rcx+110h]
0x180031402  mov     rbx, rcx
0x180031405  movzx   esi, dl
0x180031408  mov     eax, [rdi+48h]
0x18003140b  test    eax, eax
0x18003140d  jns     loc_18003159D
0x180031413  add     rdi, 50h ; 'P'
0x180031417  cmp     eax, [rdi+8]
0x18003141a  jnz     loc_18003159D
0x180031420  test    rdi, rdi
0x180031423  jz      loc_18003159D
0x180031429  call    ?zInternalStop@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003142e  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x180031433  mov     r9, [rax+8]
0x180031437  mov     eax, [r9]
0x18003143a  cmp     eax, 5
0x18003143d  jbe     loc_180031659
0x180031443  mov     rdx, 400000000000h
0x18003144d  mov     rcx, r9
0x180031450  call    _tlgKeywordOn
0x180031455  test    al, al
0x180031457  jz      loc_180031659
0x18003145d  mov     rax, [rdi+78h]
0x180031461  lea     rdx, byte_180074819
0x180031468  mov     r8, [rbx+110h]
0x18003146f  mov     rcx, r9
0x180031472  mov     [rbp+80h+var_D8], rax
0x180031476  add     r8, 8
0x18003147a  mov     rax, [rdi+70h]
0x18003147e  mov     [rbp+80h+var_D0], rax
0x180031482  mov     eax, [rdi+68h]
0x180031485  mov     [rbp+80h+var_F0], eax
0x180031488  mov     rax, [rdi+60h]
0x18003148c  mov     [rbp+80h+var_C8], rax
0x180031490  mov     rax, [rdi+58h]
0x180031494  mov     [rbp+80h+var_C0], rax
0x180031498  mov     eax, [rdi+50h]
0x18003149b  mov     [rbp+80h+var_EC], eax
0x18003149e  mov     rax, [rdi+48h]
0x1800314a2  mov     [rbp+80h+var_B8], rax
0x1800314a6  mov     eax, [rdi+20h]
0x1800314a9  mov     [rbp+80h+var_E8], eax
0x1800314ac  mov     rax, [rdi+18h]
0x1800314b0  mov     [rbp+80h+var_B0], rax
0x1800314b4  mov     eax, [rdi]
0x1800314b6  mov     [rbp+80h+var_100], eax
0x1800314b9  mov     rax, [rdi+80h]
0x1800314c0  mov     [rbp+80h+var_A8], rax
0x1800314c4  mov     eax, [rdi+40h]
0x1800314c7  mov     [rbp+80h+var_FC], eax
0x1800314ca  mov     rax, [rdi+38h]
0x1800314ce  mov     [rbp+80h+var_A0], rax
0x1800314d2  mov     eax, [rdi+8]
0x1800314d5  mov     [rbp+80h+var_F8], eax
0x1800314d8  lea     rax, [rbp+80h+var_F4]
0x1800314dc  mov     [rsp+1B0h+var_110], rax
0x1800314e4  lea     rax, [rbp+80h+var_D8]
0x1800314e8  mov     [rsp+1B0h+var_118], rax
0x1800314f0  lea     rax, [rbp+80h+var_D0]
0x1800314f4  mov     [rsp+1B0h+var_120], rax
0x1800314fc  lea     rax, [rbp+80h+var_F0]
0x180031500  mov     [rsp+1B0h+var_128], rax
0x180031508  lea     rax, [rbp+80h+var_C8]
0x18003150c  mov     [rsp+1B0h+var_130], rax
0x180031514  lea     rax, [rbp+80h+var_C0]
0x180031518  mov     [rsp+1B0h+var_138], rax
0x18003151d  lea     rax, [rbp+80h+var_EC]
0x180031521  mov     [rsp+1B0h+var_140], rax
0x180031526  lea     rax, [rbp+80h+var_B8]
0x18003152a  mov     [rsp+1B0h+var_148], rax
0x18003152f  lea     rax, [rbp+80h+var_E8]
0x180031533  mov     [rsp+1B0h+var_150], rax
0x180031538  lea     rax, [rbp+80h+var_B0]
0x18003153c  mov     [rsp+1B0h+var_158], rax
0x180031541  lea     rax, [rbp+80h+var_100]
0x180031545  mov     [rsp+1B0h+var_160], rax
0x18003154a  lea     rax, [rbp+80h+var_A8]
0x18003154e  mov     [rsp+1B0h+var_168], rax
0x180031553  lea     rax, [rbp+80h+var_FC]
0x180031557  mov     [rsp+1B0h+var_170], rax
0x18003155c  lea     rax, [rbp+80h+var_A0]
0x180031560  mov     [rsp+1B0h+var_178], rax
0x180031565  lea     rax, [rbp+80h+var_F8]
0x180031569  mov     [rsp+1B0h+var_180], rax
0x18003156e  lea     rax, [rbp+80h+var_98]
0x180031572  mov     [rsp+1B0h+var_188], rax
0x180031577  lea     rax, [rbp+80h+var_E0]
0x18003157b  mov     [rsp+1B0h+var_190], rax
0x180031580  mov     [rbp+80h+var_F4], esi
0x180031583  mov     [rbp+80h+var_98], 1000000h
0x18003158b  mov     [rbp+80h+var_E0], 0
0x180031593  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180031598  jmp     loc_180031659
0x18003159d  call    ?zInternalStop@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800315a2  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x1800315a7  mov     rdi, [rax+8]
0x1800315ab  mov     eax, [rdi]
0x1800315ad  cmp     eax, 5
0x1800315b0  jbe     loc_180031659
0x1800315b6  mov     rdx, 400000000000h
0x1800315c0  mov     rcx, rdi
0x1800315c3  call    _tlgKeywordOn
0x1800315c8  test    al, al
0x1800315ca  jz      loc_180031659
0x1800315d0  mov     [rbp+80h+var_F8], esi
0x1800315d3  call    cs:__imp_GetCurrentThreadId
0x1800315d9  mov     r8, [rbx+110h]
0x1800315e0  lea     rdx, word_18007494A
0x1800315e7  mov     [rbp+80h+var_FC], eax
0x1800315ea  xor     r9d, r9d
0x1800315ed  mov     rcx, rdi
0x1800315f0  mov     [rbp+80h+var_38], 4
0x1800315f8  mov     [rbp+80h+var_48], 4
0x180031600  mov     eax, [r8+48h]
0x180031604  add     r8, 8
0x180031608  mov     [rbp+80h+var_100], eax
0x18003160b  lea     rax, [rbp+80h+var_F8]
0x18003160f  mov     [rbp+80h+var_40], rax
0x180031613  lea     rax, [rbp+80h+var_FC]
0x180031617  mov     [rbp+80h+var_50], rax
0x18003161b  lea     rax, [rbp+80h+var_100]
0x18003161f  mov     [rbp+80h+var_60], rax
0x180031623  lea     rax, [rbp+80h+var_E0]
0x180031627  mov     [rbp+80h+var_70], rax
0x18003162b  lea     rax, [rbp+80h+var_90]
0x18003162f  mov     [rsp+1B0h+var_188], rax
0x180031634  mov     dword ptr [rsp+1B0h+var_190], 6
0x18003163c  mov     [rbp+80h+var_E0], 0
0x180031644  mov     [rbp+80h+var_58], 4
0x18003164c  mov     [rbp+80h+var_68], 8
0x180031654  call    _tlgWriteTransfer_EventWriteTransfer
0x180031659  mov     rcx, rbx
0x18003165c  call    ?IgnoreCurrentThread@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180031661  mov     rcx, [rbp+80h+var_30]
0x180031665  xor     rcx, rsp; StackCookie
0x180031668  call    __security_check_cookie
0x18003166d  add     rsp, 198h
0x180031674  pop     rdi
0x180031675  pop     rsi
0x180031676  pop     rbx
0x180031677  pop     rbp
0x180031678  retn
```
