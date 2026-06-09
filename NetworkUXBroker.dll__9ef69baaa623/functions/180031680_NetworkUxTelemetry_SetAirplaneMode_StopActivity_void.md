# NetworkUxTelemetry::SetAirplaneMode::StopActivity(void)

- ea: `0x180031680`
- end: `0x180031903`
- name: `?StopActivity@SetAirplaneMode@NetworkUxTelemetry@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(NetworkUxTelemetry::SetAirplaneMode *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001010`
- `0x180001dfc`
- `0x180001e28`
- `0x180002520`
- `0x18002d5a0`
- `0x180031680`
- `0x1800356dc`
- `0x180037a40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031864`

## pseudocode

```c
void __fastcall NetworkUxTelemetry::SetAirplaneMode::StopActivity(NetworkUxTelemetry::SetAirplaneMode *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r8
  _DWORD *v6; // r9
  __int64 v7; // r9
  __int64 v8; // r8
  _DWORD *v9; // rdi
  __int64 v10; // r8
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // [rsp+A0h] [rbp-80h] BYREF
  DWORD v14; // [rsp+A4h] [rbp-7Ch] BYREF
  int v15; // [rsp+A8h] [rbp-78h] BYREF
  int v16; // [rsp+ACh] [rbp-74h] BYREF
  int v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v19; // [rsp+B8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v28; // [rsp+100h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+110h] [rbp-10h] BYREF
  __int64 *v30; // [rsp+130h] [rbp+10h]
  __int64 v31; // [rsp+138h] [rbp+18h]
  int *v32; // [rsp+140h] [rbp+20h]
  __int64 v33; // [rsp+148h] [rbp+28h]
  DWORD *v34; // [rsp+150h] [rbp+30h]
  __int64 v35; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
    if ( *v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v5) )
    {
      v8 = *((_QWORD *)this + 34);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v15 = v4[26];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v16 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v17 = v4[8];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v18 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v28 = 0x1000000;
      v19 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_180074FC9,
        v8 + 8,
        v7,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v14,
        &v27,
        (__int64)&v13,
        &v26,
        (__int64)&v18,
        &v25,
        (__int64)&v17,
        &v24,
        (__int64)&v16,
        &v23,
        &v22,
        (__int64)&v15,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
    if ( *v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v14 = CurrentThreadId;
      v35 = 4;
      v33 = 4;
      v13 = *(_DWORD *)(v12 + 72);
      v34 = &v14;
      v32 = &v13;
      v30 = &v19;
      v19 = 0;
      v31 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v9,
        (unsigned __int8 *)qword_1800750F0,
        (const GUID *)(v12 + 8),
        0,
        5u,
        &v29);
    }
  }
  wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180031680  mov     [rsp-8+arg_8], rbx
0x180031685  mov     [rsp-8+arg_10], rdi
0x18003168a  push    rbp
0x18003168b  lea     rbp, [rsp-50h]
0x180031690  sub     rsp, 170h
0x180031697  mov     rax, cs:__security_cookie
0x18003169e  xor     rax, rsp
0x1800316a1  mov     [rbp+50h+var_10], rax
0x1800316a5  mov     rdi, [rcx+110h]
0x1800316ac  mov     rbx, rcx
0x1800316af  mov     eax, [rdi+48h]
0x1800316b2  test    eax, eax
0x1800316b4  jns     loc_180031835
0x1800316ba  add     rdi, 50h ; 'P'
0x1800316be  cmp     eax, [rdi+8]
0x1800316c1  jnz     loc_180031835
0x1800316c7  test    rdi, rdi
0x1800316ca  jz      loc_180031835
0x1800316d0  call    ?zInternalStop@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800316d5  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x1800316da  mov     r9, [rax+8]
0x1800316de  mov     eax, [r9]
0x1800316e1  cmp     eax, 5
0x1800316e4  jbe     loc_1800318DA
0x1800316ea  mov     rdx, 400000000000h
0x1800316f4  mov     rcx, r9
0x1800316f7  call    _tlgKeywordOn
0x1800316fc  test    al, al
0x1800316fe  jz      loc_1800318DA
0x180031704  mov     rax, [rdi+78h]
0x180031708  lea     rdx, byte_180074FC9
0x18003170f  mov     r8, [rbx+110h]
0x180031716  mov     rcx, r9
0x180031719  mov     [rbp+50h+var_B0], rax
0x18003171d  add     r8, 8
0x180031721  mov     rax, [rdi+70h]
0x180031725  mov     [rbp+50h+var_A8], rax
0x180031729  mov     eax, [rdi+68h]
0x18003172c  mov     [rbp+50h+var_C8], eax
0x18003172f  mov     rax, [rdi+60h]
0x180031733  mov     [rbp+50h+var_A0], rax
0x180031737  mov     rax, [rdi+58h]
0x18003173b  mov     [rbp+50h+var_98], rax
0x18003173f  mov     eax, [rdi+50h]
0x180031742  mov     [rbp+50h+var_C4], eax
0x180031745  mov     rax, [rdi+48h]
0x180031749  mov     [rbp+50h+var_90], rax
0x18003174d  mov     eax, [rdi+20h]
0x180031750  mov     [rbp+50h+var_C0], eax
0x180031753  mov     rax, [rdi+18h]
0x180031757  mov     [rbp+50h+var_88], rax
0x18003175b  mov     eax, [rdi]
0x18003175d  mov     [rbp+50h+var_BC], eax
0x180031760  mov     rax, [rdi+80h]
0x180031767  mov     [rbp+50h+var_80], rax
0x18003176b  mov     eax, [rdi+40h]
0x18003176e  mov     [rbp+50h+var_D0], eax
0x180031771  mov     rax, [rdi+38h]
0x180031775  mov     [rbp+50h+var_78], rax
0x180031779  mov     eax, [rdi+8]
0x18003177c  mov     [rbp+50h+var_CC], eax
0x18003177f  lea     rax, [rbp+50h+var_B0]
0x180031783  mov     [rsp+170h+var_D8], rax
0x18003178b  lea     rax, [rbp+50h+var_A8]
0x18003178f  mov     [rsp+170h+var_E0], rax
0x180031797  lea     rax, [rbp+50h+var_C8]
0x18003179b  mov     [rsp+170h+var_E8], rax
0x1800317a3  lea     rax, [rbp+50h+var_A0]
0x1800317a7  mov     [rsp+170h+var_F0], rax
0x1800317af  lea     rax, [rbp+50h+var_98]
0x1800317b3  mov     [rsp+170h+var_F8], rax
0x1800317b8  lea     rax, [rbp+50h+var_C4]
0x1800317bc  mov     [rsp+170h+var_100], rax
0x1800317c1  lea     rax, [rbp+50h+var_90]
0x1800317c5  mov     [rsp+170h+var_108], rax
0x1800317ca  lea     rax, [rbp+50h+var_C0]
0x1800317ce  mov     [rsp+170h+var_110], rax
0x1800317d3  lea     rax, [rbp+50h+var_88]
0x1800317d7  mov     [rsp+170h+var_118], rax
0x1800317dc  lea     rax, [rbp+50h+var_BC]
0x1800317e0  mov     [rsp+170h+var_120], rax
0x1800317e5  lea     rax, [rbp+50h+var_80]
0x1800317e9  mov     [rsp+170h+var_128], rax
0x1800317ee  lea     rax, [rbp+50h+var_D0]
0x1800317f2  mov     [rsp+170h+var_130], rax
0x1800317f7  lea     rax, [rbp+50h+var_78]
0x1800317fb  mov     [rsp+170h+var_138], rax
0x180031800  lea     rax, [rbp+50h+var_CC]
0x180031804  mov     [rsp+170h+var_140], rax
0x180031809  lea     rax, [rbp+50h+var_70]
0x18003180d  mov     [rsp+170h+var_148], rax
0x180031812  lea     rax, [rbp+50h+var_B8]
0x180031816  mov     [rsp+170h+var_150], rax
0x18003181b  mov     [rbp+50h+var_70], 1000000h
0x180031823  mov     [rbp+50h+var_B8], 0
0x18003182b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180031830  jmp     loc_1800318DA
0x180031835  call    ?zInternalStop@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003183a  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x18003183f  mov     rdi, [rax+8]
0x180031843  mov     eax, [rdi]
0x180031845  cmp     eax, 5
0x180031848  jbe     loc_1800318DA
0x18003184e  mov     rdx, 400000000000h
0x180031858  mov     rcx, rdi
0x18003185b  call    _tlgKeywordOn
0x180031860  test    al, al
0x180031862  jz      short loc_1800318DA
0x180031864  call    cs:__imp_GetCurrentThreadId
0x18003186a  mov     r8, [rbx+110h]
0x180031871  lea     rdx, qword_1800750F0
0x180031878  mov     [rbp+50h+var_CC], eax
0x18003187b  xor     r9d, r9d
0x18003187e  mov     rcx, rdi
0x180031881  mov     [rbp+50h+var_18], 4
0x180031889  mov     [rbp+50h+var_28], 4
0x180031891  mov     eax, [r8+48h]
0x180031895  add     r8, 8
0x180031899  mov     [rbp+50h+var_D0], eax
0x18003189c  lea     rax, [rbp+50h+var_CC]
0x1800318a0  mov     [rbp+50h+var_20], rax
0x1800318a4  lea     rax, [rbp+50h+var_D0]
0x1800318a8  mov     [rbp+50h+var_30], rax
0x1800318ac  lea     rax, [rbp+50h+var_B8]
0x1800318b0  mov     [rbp+50h+var_40], rax
0x1800318b4  lea     rax, [rbp+50h+var_60]
0x1800318b8  mov     [rsp+170h+var_148], rax
0x1800318bd  mov     dword ptr [rsp+170h+var_150], 5
0x1800318c5  mov     [rbp+50h+var_B8], 0
0x1800318cd  mov     [rbp+50h+var_38], 8
0x1800318d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800318da  mov     rcx, rbx
0x1800318dd  call    ?IgnoreCurrentThread@?$ActivityBase@VNetworkUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800318e2  mov     rcx, [rbp+50h+var_10]
0x1800318e6  xor     rcx, rsp; StackCookie
0x1800318e9  call    __security_check_cookie
0x1800318ee  lea     r11, [rsp+170h+var_s0]
0x1800318f6  mov     rbx, [r11+18h]
0x1800318fa  mov     rdi, [r11+20h]
0x1800318fe  mov     rsp, r11
0x180031901  pop     rbp
0x180031902  retn
```
