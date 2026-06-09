# NetSetupTraceLogging::NewBindGraphCalculation::StopActivity(void)

- ea: `0x180047d00`
- end: `0x180047f52`
- name: `?StopActivity@NewBindGraphCalculation@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::NewBindGraphCalculation *__hidden this)`
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
- `0x180047d00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047ef3`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::NewBindGraphCalculation::StopActivity(
        NetSetupTraceLogging::NewBindGraphCalculation *this)
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
        (int)&byte_1800B367B,
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
        (int)byte_1800B3623,
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
0x180047d00  push    rbp
0x180047d02  push    rbx
0x180047d03  push    rdi
0x180047d04  lea     rbp, [rsp+10h]
0x180047d09  sub     rsp, 130h
0x180047d10  mov     rdi, [rcx+110h]
0x180047d17  mov     rbx, rcx
0x180047d1a  mov     eax, [rdi+48h]
0x180047d1d  test    eax, eax
0x180047d1f  jns     loc_180047ECE
0x180047d25  add     rdi, 50h ; 'P'
0x180047d29  cmp     eax, [rdi+8]
0x180047d2c  jnz     loc_180047ECE
0x180047d32  test    rdi, rdi
0x180047d35  jz      loc_180047ECE
0x180047d3b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180047d40  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180047d45  mov     r9, rax
0x180047d48  mov     ecx, [rax]
0x180047d4a  cmp     ecx, 5
0x180047d4d  jbe     loc_180047F40
0x180047d53  mov     edx, 1
0x180047d58  mov     rcx, rax
0x180047d5b  call    _tlgKeywordOn
0x180047d60  test    al, al
0x180047d62  jz      loc_180047F40
0x180047d68  mov     rax, [rdi+30h]
0x180047d6c  lea     rdx, byte_1800B367B; int
0x180047d73  mov     [rbp+var_70], rax
0x180047d77  mov     rcx, r9; int
0x180047d7a  mov     eax, [rdi+44h]
0x180047d7d  mov     dword ptr [rbp+arg_0], eax
0x180047d80  mov     eax, [rdi+10h]
0x180047d83  mov     dword ptr [rbp+arg_8], eax
0x180047d86  mov     rax, [rdi+78h]
0x180047d8a  mov     [rbp+var_68], rax
0x180047d8e  mov     rax, [rdi+70h]
0x180047d92  mov     [rbp+var_60], rax
0x180047d96  mov     eax, [rdi+68h]
0x180047d99  mov     r8, [rbx+110h]
0x180047da0  mov     dword ptr [rbp+arg_10], eax
0x180047da3  add     r8, 8; int
0x180047da7  mov     rax, [rdi+60h]
0x180047dab  mov     [rbp+var_58], rax
0x180047daf  mov     rax, [rdi+58h]
0x180047db3  mov     [rbp+var_50], rax
0x180047db7  mov     eax, [rdi+50h]
0x180047dba  mov     dword ptr [rbp+arg_18], eax
0x180047dbd  mov     rax, [rdi+48h]
0x180047dc1  mov     [rbp+var_48], rax
0x180047dc5  mov     eax, [rdi+20h]
0x180047dc8  mov     dword ptr [rbp+var_80], eax
0x180047dcb  mov     rax, [rdi+18h]
0x180047dcf  mov     [rbp+var_40], rax
0x180047dd3  mov     eax, [rdi]
0x180047dd5  mov     dword ptr [rbp+var_80+4], eax
0x180047dd8  mov     rax, [rdi+80h]
0x180047ddf  mov     [rbp+var_38], rax
0x180047de3  mov     eax, [rdi+40h]
0x180047de6  mov     dword ptr [rbp+var_78], eax
0x180047de9  mov     rax, [rdi+38h]
0x180047ded  mov     [rbp+var_30], rax
0x180047df1  mov     eax, [rdi+8]
0x180047df4  mov     dword ptr [rbp+var_78+4], eax
0x180047df7  lea     rax, [rbp+var_70]
0x180047dfb  mov     [rsp+140h+var_90], rax; __int64
0x180047e03  lea     rax, [rbp+arg_0]
0x180047e07  mov     [rsp+140h+var_98], rax; __int64
0x180047e0f  lea     rax, [rbp+arg_8]
0x180047e13  mov     [rsp+140h+var_A0], rax; __int64
0x180047e1b  lea     rax, [rbp+var_68]
0x180047e1f  mov     [rsp+140h+var_A8], rax; __int64
0x180047e27  lea     rax, [rbp+var_60]
0x180047e2b  mov     [rsp+140h+var_B0], rax; __int64
0x180047e33  lea     rax, [rbp+arg_10]
0x180047e37  mov     [rsp+140h+var_B8], rax; __int64
0x180047e3f  lea     rax, [rbp+var_58]
0x180047e43  mov     [rsp+140h+var_C0], rax; __int64
0x180047e4b  lea     rax, [rbp+var_50]
0x180047e4f  mov     [rsp+140h+var_C8], rax; __int64
0x180047e54  lea     rax, [rbp+arg_18]
0x180047e58  mov     [rsp+140h+var_D0], rax; __int64
0x180047e5d  lea     rax, [rbp+var_48]
0x180047e61  mov     [rsp+140h+var_D8], rax; __int64
0x180047e66  lea     rax, [rbp+var_80]
0x180047e6a  mov     [rsp+140h+var_E0], rax; __int64
0x180047e6f  lea     rax, [rbp+var_40]
0x180047e73  mov     [rsp+140h+var_E8], rax; __int64
0x180047e78  lea     rax, [rbp+var_80+4]
0x180047e7c  mov     [rsp+140h+var_F0], rax; __int64
0x180047e81  lea     rax, [rbp+var_38]
0x180047e85  mov     [rsp+140h+var_F8], rax; __int64
0x180047e8a  lea     rax, [rbp+var_78]
0x180047e8e  mov     [rsp+140h+var_100], rax; __int64
0x180047e93  lea     rax, [rbp+var_30]
0x180047e97  mov     [rsp+140h+var_108], rax; __int64
0x180047e9c  lea     rax, [rbp+var_78+4]
0x180047ea0  mov     [rsp+140h+var_110], rax; __int64
0x180047ea5  lea     rax, [rbp+var_28]
0x180047ea9  mov     [rsp+140h+var_118], rax; __int64
0x180047eae  lea     rax, [rbp+var_20]
0x180047eb2  mov     [rsp+140h+var_120], rax; __int64
0x180047eb7  mov     [rbp+var_28], 1000000h
0x180047ebf  mov     [rbp+var_20], 0
0x180047ec7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180047ecc  jmp     short loc_180047F40
0x180047ece  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180047ed3  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180047ed8  mov     rdi, rax
0x180047edb  mov     ecx, [rax]
0x180047edd  cmp     ecx, 5
0x180047ee0  jbe     short loc_180047F40
0x180047ee2  mov     edx, 1
0x180047ee7  mov     rcx, rax
0x180047eea  call    _tlgKeywordOn
0x180047eef  test    al, al
0x180047ef1  jz      short loc_180047F40
0x180047ef3  call    cs:__imp_GetCurrentThreadId
0x180047ef9  mov     r8, [rbx+110h]
0x180047f00  lea     rdx, byte_1800B3623
0x180047f07  mov     dword ptr [rbp+arg_0], eax
0x180047f0a  mov     rcx, rdi
0x180047f0d  mov     eax, [r8+48h]
0x180047f11  add     r8, 8
0x180047f15  mov     dword ptr [rbp+arg_8], eax
0x180047f18  lea     rax, [rbp+arg_0]
0x180047f1c  mov     [rsp+140h+var_110], rax
0x180047f21  lea     rax, [rbp+arg_8]
0x180047f25  mov     [rsp+140h+var_118], rax
0x180047f2a  lea     rax, [rbp+arg_10]
0x180047f2e  mov     [rsp+140h+var_120], rax
0x180047f33  mov     [rbp+arg_10], 0
0x180047f3b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180047f40  mov     rcx, rbx
0x180047f43  add     rsp, 130h
0x180047f4a  pop     rdi
0x180047f4b  pop     rbx
0x180047f4c  pop     rbp
0x180047f4d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
