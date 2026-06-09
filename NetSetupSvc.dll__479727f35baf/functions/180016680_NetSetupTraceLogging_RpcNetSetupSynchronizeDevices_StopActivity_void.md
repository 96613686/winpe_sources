# NetSetupTraceLogging::RpcNetSetupSynchronizeDevices::StopActivity(void)

- ea: `0x180016680`
- end: `0x1800168d2`
- name: `?StopActivity@RpcNetSetupSynchronizeDevices@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupSynchronizeDevices *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001420`
- `0x180001734`
- `0x180001b50`
- `0x180013aa4`
- `0x180014090`
- `0x180016680`
- `0x1800170d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016873`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016873`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupSynchronizeDevices::StopActivity(
        NetSetupTraceLogging::RpcNetSetupSynchronizeDevices *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v22; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+100h] [rbp-40h] BYREF
  __int64 v28; // [rsp+108h] [rbp-38h] BYREF
  __int64 v29; // [rsp+110h] [rbp-30h] BYREF
  __int64 v30; // [rsp+118h] [rbp-28h] BYREF
  __int64 v31[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v32; // [rsp+150h] [rbp+10h] BYREF
  __int64 v33; // [rsp+158h] [rbp+18h] BYREF
  __int64 v34; // [rsp+160h] [rbp+20h] BYREF
  __int64 v35; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = NetSetupTraceLogging::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 1, v7) )
    {
      v21 = *((_QWORD *)v4 + 6);
      LODWORD(v32) = v4[17];
      LODWORD(v33) = v4[4];
      v22 = *((_QWORD *)v4 + 15);
      v23 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v34) = v4[26];
      v24 = *((_QWORD *)v4 + 12);
      v25 = *((_QWORD *)v4 + 11);
      LODWORD(v35) = v4[20];
      v26 = *((_QWORD *)v4 + 9);
      v17 = v4[8];
      v27 = *((_QWORD *)v4 + 3);
      v18 = *v4;
      v28 = *((_QWORD *)v4 + 16);
      v19 = v4[16];
      v29 = *((_QWORD *)v4 + 7);
      v20 = v4[2];
      v30 = 0x1000000;
      v31[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (int)&unk_18003FE88,
        v9 + 8,
        v8,
        (__int64)v31,
        (__int64)&v30,
        (__int64)&v20,
        (const wchar_t **)&v29,
        (__int64)&v19,
        (const wchar_t **)&v28,
        (__int64)&v18,
        (__int64 **)&v27,
        (__int64)&v17,
        (const wchar_t **)&v26,
        (__int64)&v35,
        (const wchar_t **)&v25,
        (__int64 **)&v24,
        (__int64)&v34,
        (const wchar_t **)&v23,
        (__int64 **)&v22,
        (__int64)&v33,
        (__int64)&v32,
        (const wchar_t **)&v21);
    }
  }
  else
  {
    wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = NetSetupTraceLogging::Provider(v10);
    v13 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 1, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      LODWORD(v32) = CurrentThreadId;
      LODWORD(v33) = *(_DWORD *)(v15 + 72);
      v34 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (int)word_18003FE2A,
        v15 + 8,
        v16,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180016680  push    rbp
0x180016682  push    rbx
0x180016683  push    rdi
0x180016684  lea     rbp, [rsp+10h]
0x180016689  sub     rsp, 130h
0x180016690  mov     rdi, [rcx+110h]
0x180016697  mov     rbx, rcx
0x18001669a  mov     eax, [rdi+48h]
0x18001669d  test    eax, eax
0x18001669f  jns     loc_18001684E
0x1800166a5  add     rdi, 50h ; 'P'
0x1800166a9  cmp     eax, [rdi+8]
0x1800166ac  jnz     loc_18001684E
0x1800166b2  test    rdi, rdi
0x1800166b5  jz      loc_18001684E
0x1800166bb  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800166c0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800166c5  mov     r9, rax
0x1800166c8  mov     ecx, [rax]
0x1800166ca  cmp     ecx, 5
0x1800166cd  jbe     loc_1800168C0
0x1800166d3  mov     edx, 1
0x1800166d8  mov     rcx, rax
0x1800166db  call    _tlgKeywordOn
0x1800166e0  test    al, al
0x1800166e2  jz      loc_1800168C0
0x1800166e8  mov     rax, [rdi+30h]
0x1800166ec  lea     rdx, unk_18003FE88; int
0x1800166f3  mov     [rbp+var_70], rax
0x1800166f7  mov     rcx, r9; int
0x1800166fa  mov     eax, [rdi+44h]
0x1800166fd  mov     dword ptr [rbp+arg_0], eax
0x180016700  mov     eax, [rdi+10h]
0x180016703  mov     dword ptr [rbp+arg_8], eax
0x180016706  mov     rax, [rdi+78h]
0x18001670a  mov     [rbp+var_68], rax
0x18001670e  mov     rax, [rdi+70h]
0x180016712  mov     [rbp+var_60], rax
0x180016716  mov     eax, [rdi+68h]
0x180016719  mov     r8, [rbx+110h]
0x180016720  mov     dword ptr [rbp+arg_10], eax
0x180016723  add     r8, 8; int
0x180016727  mov     rax, [rdi+60h]
0x18001672b  mov     [rbp+var_58], rax
0x18001672f  mov     rax, [rdi+58h]
0x180016733  mov     [rbp+var_50], rax
0x180016737  mov     eax, [rdi+50h]
0x18001673a  mov     dword ptr [rbp+arg_18], eax
0x18001673d  mov     rax, [rdi+48h]
0x180016741  mov     [rbp+var_48], rax
0x180016745  mov     eax, [rdi+20h]
0x180016748  mov     dword ptr [rbp+var_80], eax
0x18001674b  mov     rax, [rdi+18h]
0x18001674f  mov     [rbp+var_40], rax
0x180016753  mov     eax, [rdi]
0x180016755  mov     dword ptr [rbp+var_80+4], eax
0x180016758  mov     rax, [rdi+80h]
0x18001675f  mov     [rbp+var_38], rax
0x180016763  mov     eax, [rdi+40h]
0x180016766  mov     dword ptr [rbp+var_78], eax
0x180016769  mov     rax, [rdi+38h]
0x18001676d  mov     [rbp+var_30], rax
0x180016771  mov     eax, [rdi+8]
0x180016774  mov     dword ptr [rbp+var_78+4], eax
0x180016777  lea     rax, [rbp+var_70]
0x18001677b  mov     [rsp+140h+var_90], rax; __int64
0x180016783  lea     rax, [rbp+arg_0]
0x180016787  mov     [rsp+140h+var_98], rax; __int64
0x18001678f  lea     rax, [rbp+arg_8]
0x180016793  mov     [rsp+140h+var_A0], rax; __int64
0x18001679b  lea     rax, [rbp+var_68]
0x18001679f  mov     [rsp+140h+var_A8], rax; __int64
0x1800167a7  lea     rax, [rbp+var_60]
0x1800167ab  mov     [rsp+140h+var_B0], rax; __int64
0x1800167b3  lea     rax, [rbp+arg_10]
0x1800167b7  mov     [rsp+140h+var_B8], rax; __int64
0x1800167bf  lea     rax, [rbp+var_58]
0x1800167c3  mov     [rsp+140h+var_C0], rax; __int64
0x1800167cb  lea     rax, [rbp+var_50]
0x1800167cf  mov     [rsp+140h+var_C8], rax; __int64
0x1800167d4  lea     rax, [rbp+arg_18]
0x1800167d8  mov     [rsp+140h+var_D0], rax; __int64
0x1800167dd  lea     rax, [rbp+var_48]
0x1800167e1  mov     [rsp+140h+var_D8], rax; __int64
0x1800167e6  lea     rax, [rbp+var_80]
0x1800167ea  mov     [rsp+140h+var_E0], rax; __int64
0x1800167ef  lea     rax, [rbp+var_40]
0x1800167f3  mov     [rsp+140h+var_E8], rax; __int64
0x1800167f8  lea     rax, [rbp+var_80+4]
0x1800167fc  mov     [rsp+140h+var_F0], rax; __int64
0x180016801  lea     rax, [rbp+var_38]
0x180016805  mov     [rsp+140h+var_F8], rax; __int64
0x18001680a  lea     rax, [rbp+var_78]
0x18001680e  mov     [rsp+140h+var_100], rax; __int64
0x180016813  lea     rax, [rbp+var_30]
0x180016817  mov     [rsp+140h+var_108], rax; __int64
0x18001681c  lea     rax, [rbp+var_78+4]
0x180016820  mov     [rsp+140h+var_110], rax; __int64
0x180016825  lea     rax, [rbp+var_28]
0x180016829  mov     [rsp+140h+var_118], rax; __int64
0x18001682e  lea     rax, [rbp+var_20]
0x180016832  mov     [rsp+140h+var_120], rax; __int64
0x180016837  mov     [rbp+var_28], 1000000h
0x18001683f  mov     [rbp+var_20], 0
0x180016847  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001684c  jmp     short loc_1800168C0
0x18001684e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016853  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180016858  mov     rdi, rax
0x18001685b  mov     ecx, [rax]
0x18001685d  cmp     ecx, 5
0x180016860  jbe     short loc_1800168C0
0x180016862  mov     edx, 1
0x180016867  mov     rcx, rax
0x18001686a  call    _tlgKeywordOn
0x18001686f  test    al, al
0x180016871  jz      short loc_1800168C0
0x180016873  call    cs:__imp_GetCurrentThreadId
0x180016879  mov     r8, [rbx+110h]
0x180016880  lea     rdx, word_18003FE2A
0x180016887  mov     dword ptr [rbp+arg_0], eax
0x18001688a  mov     rcx, rdi
0x18001688d  mov     eax, [r8+48h]
0x180016891  add     r8, 8
0x180016895  mov     dword ptr [rbp+arg_8], eax
0x180016898  lea     rax, [rbp+arg_0]
0x18001689c  mov     [rsp+140h+var_110], rax
0x1800168a1  lea     rax, [rbp+arg_8]
0x1800168a5  mov     [rsp+140h+var_118], rax
0x1800168aa  lea     rax, [rbp+arg_10]
0x1800168ae  mov     [rsp+140h+var_120], rax
0x1800168b3  mov     [rbp+arg_10], 0
0x1800168bb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800168c0  mov     rcx, rbx
0x1800168c3  add     rsp, 130h
0x1800168ca  pop     rdi
0x1800168cb  pop     rbx
0x1800168cc  pop     rbp
0x1800168cd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
