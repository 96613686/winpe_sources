# NetSetupTraceLogging::IfDescrAllocation::StopActivity(void)

- ea: `0x1800778a0`
- end: `0x180077af2`
- name: `?StopActivity@IfDescrAllocation@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::IfDescrAllocation *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000154c`
- `0x180001860`
- `0x18000e54c`
- `0x180033720`
- `0x18003ae24`
- `0x180046ed0`
- `0x1800778a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077a93`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::IfDescrAllocation::StopActivity(NetSetupTraceLogging::IfDescrAllocation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v30; // [rsp+150h] [rbp+10h] BYREF
  __int64 v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  __int64 v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = NetSetupTraceLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 1, v7, v5) )
    {
      v19 = *((_QWORD *)v4 + 6);
      LODWORD(v30) = v4[17];
      LODWORD(v31) = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      LODWORD(v33) = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (int)&byte_1800B4483,
        v9 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (const wchar_t **)&v27,
        (__int64)&v17,
        (const wchar_t **)&v26,
        (__int64)&v16,
        (const WCHAR **)&v25,
        (__int64)&v15,
        (const wchar_t **)&v24,
        (__int64)&v33,
        (const wchar_t **)&v23,
        (const WCHAR **)&v22,
        (__int64)&v32,
        (const wchar_t **)&v21,
        (const WCHAR **)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (const wchar_t **)&v19);
    }
  }
  else
  {
    wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = NetSetupTraceLogging::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 1, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(v30) = CurrentThreadId;
      LODWORD(v31) = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)byte_1800B4431,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1800778a0  push    rbp
0x1800778a2  push    rbx
0x1800778a3  push    rdi
0x1800778a4  lea     rbp, [rsp+10h]
0x1800778a9  sub     rsp, 130h
0x1800778b0  mov     rdi, [rcx+110h]
0x1800778b7  mov     rbx, rcx
0x1800778ba  mov     eax, [rdi+48h]
0x1800778bd  test    eax, eax
0x1800778bf  jns     loc_180077A6E
0x1800778c5  add     rdi, 50h ; 'P'
0x1800778c9  cmp     eax, [rdi+8]
0x1800778cc  jnz     loc_180077A6E
0x1800778d2  test    rdi, rdi
0x1800778d5  jz      loc_180077A6E
0x1800778db  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800778e0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800778e5  mov     r9, rax
0x1800778e8  mov     ecx, [rax]
0x1800778ea  cmp     ecx, 5
0x1800778ed  jbe     loc_180077AE0
0x1800778f3  mov     edx, 1
0x1800778f8  mov     rcx, rax
0x1800778fb  call    _tlgKeywordOn
0x180077900  test    al, al
0x180077902  jz      loc_180077AE0
0x180077908  mov     rax, [rdi+30h]
0x18007790c  lea     rdx, byte_1800B4483; int
0x180077913  mov     [rbp+var_70], rax
0x180077917  mov     rcx, r9; int
0x18007791a  mov     eax, [rdi+44h]
0x18007791d  mov     dword ptr [rbp+arg_0], eax
0x180077920  mov     eax, [rdi+10h]
0x180077923  mov     dword ptr [rbp+arg_8], eax
0x180077926  mov     rax, [rdi+78h]
0x18007792a  mov     [rbp+var_68], rax
0x18007792e  mov     rax, [rdi+70h]
0x180077932  mov     [rbp+var_60], rax
0x180077936  mov     eax, [rdi+68h]
0x180077939  mov     r8, [rbx+110h]
0x180077940  mov     dword ptr [rbp+arg_10], eax
0x180077943  add     r8, 8; int
0x180077947  mov     rax, [rdi+60h]
0x18007794b  mov     [rbp+var_58], rax
0x18007794f  mov     rax, [rdi+58h]
0x180077953  mov     [rbp+var_50], rax
0x180077957  mov     eax, [rdi+50h]
0x18007795a  mov     dword ptr [rbp+arg_18], eax
0x18007795d  mov     rax, [rdi+48h]
0x180077961  mov     [rbp+var_48], rax
0x180077965  mov     eax, [rdi+20h]
0x180077968  mov     dword ptr [rbp+var_80], eax
0x18007796b  mov     rax, [rdi+18h]
0x18007796f  mov     [rbp+var_40], rax
0x180077973  mov     eax, [rdi]
0x180077975  mov     dword ptr [rbp+var_80+4], eax
0x180077978  mov     rax, [rdi+80h]
0x18007797f  mov     [rbp+var_38], rax
0x180077983  mov     eax, [rdi+40h]
0x180077986  mov     dword ptr [rbp+var_78], eax
0x180077989  mov     rax, [rdi+38h]
0x18007798d  mov     [rbp+var_30], rax
0x180077991  mov     eax, [rdi+8]
0x180077994  mov     dword ptr [rbp+var_78+4], eax
0x180077997  lea     rax, [rbp+var_70]
0x18007799b  mov     [rsp+140h+var_90], rax; __int64
0x1800779a3  lea     rax, [rbp+arg_0]
0x1800779a7  mov     [rsp+140h+var_98], rax; __int64
0x1800779af  lea     rax, [rbp+arg_8]
0x1800779b3  mov     [rsp+140h+var_A0], rax; __int64
0x1800779bb  lea     rax, [rbp+var_68]
0x1800779bf  mov     [rsp+140h+var_A8], rax; __int64
0x1800779c7  lea     rax, [rbp+var_60]
0x1800779cb  mov     [rsp+140h+var_B0], rax; __int64
0x1800779d3  lea     rax, [rbp+arg_10]
0x1800779d7  mov     [rsp+140h+var_B8], rax; __int64
0x1800779df  lea     rax, [rbp+var_58]
0x1800779e3  mov     [rsp+140h+var_C0], rax; __int64
0x1800779eb  lea     rax, [rbp+var_50]
0x1800779ef  mov     [rsp+140h+var_C8], rax; __int64
0x1800779f4  lea     rax, [rbp+arg_18]
0x1800779f8  mov     [rsp+140h+var_D0], rax; __int64
0x1800779fd  lea     rax, [rbp+var_48]
0x180077a01  mov     [rsp+140h+var_D8], rax; __int64
0x180077a06  lea     rax, [rbp+var_80]
0x180077a0a  mov     [rsp+140h+var_E0], rax; __int64
0x180077a0f  lea     rax, [rbp+var_40]
0x180077a13  mov     [rsp+140h+var_E8], rax; __int64
0x180077a18  lea     rax, [rbp+var_80+4]
0x180077a1c  mov     [rsp+140h+var_F0], rax; __int64
0x180077a21  lea     rax, [rbp+var_38]
0x180077a25  mov     [rsp+140h+var_F8], rax; __int64
0x180077a2a  lea     rax, [rbp+var_78]
0x180077a2e  mov     [rsp+140h+var_100], rax; __int64
0x180077a33  lea     rax, [rbp+var_30]
0x180077a37  mov     [rsp+140h+var_108], rax; __int64
0x180077a3c  lea     rax, [rbp+var_78+4]
0x180077a40  mov     [rsp+140h+var_110], rax; __int64
0x180077a45  lea     rax, [rbp+var_28]
0x180077a49  mov     [rsp+140h+var_118], rax; __int64
0x180077a4e  lea     rax, [rbp+var_20]
0x180077a52  mov     [rsp+140h+var_120], rax; __int64
0x180077a57  mov     [rbp+var_28], 1000000h
0x180077a5f  mov     [rbp+var_20], 0
0x180077a67  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180077a6c  jmp     short loc_180077AE0
0x180077a6e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180077a73  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180077a78  mov     rdi, rax
0x180077a7b  mov     ecx, [rax]
0x180077a7d  cmp     ecx, 5
0x180077a80  jbe     short loc_180077AE0
0x180077a82  mov     edx, 1
0x180077a87  mov     rcx, rax
0x180077a8a  call    _tlgKeywordOn
0x180077a8f  test    al, al
0x180077a91  jz      short loc_180077AE0
0x180077a93  call    cs:__imp_GetCurrentThreadId
0x180077a99  mov     r8, [rbx+110h]
0x180077aa0  lea     rdx, byte_1800B4431
0x180077aa7  mov     dword ptr [rbp+arg_0], eax
0x180077aaa  mov     rcx, rdi
0x180077aad  mov     eax, [r8+48h]
0x180077ab1  add     r8, 8
0x180077ab5  mov     dword ptr [rbp+arg_8], eax
0x180077ab8  lea     rax, [rbp+arg_0]
0x180077abc  mov     [rsp+140h+var_110], rax
0x180077ac1  lea     rax, [rbp+arg_8]
0x180077ac5  mov     [rsp+140h+var_118], rax
0x180077aca  lea     rax, [rbp+arg_10]
0x180077ace  mov     [rsp+140h+var_120], rax
0x180077ad3  mov     [rbp+arg_10], 0
0x180077adb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180077ae0  mov     rcx, rbx
0x180077ae3  add     rsp, 130h
0x180077aea  pop     rdi
0x180077aeb  pop     rbx
0x180077aec  pop     rbp
0x180077aed  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
