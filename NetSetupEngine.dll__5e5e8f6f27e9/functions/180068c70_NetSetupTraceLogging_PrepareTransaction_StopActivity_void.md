# NetSetupTraceLogging::PrepareTransaction::StopActivity(void)

- ea: `0x180068c70`
- end: `0x180068ec2`
- name: `?StopActivity@PrepareTransaction@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::PrepareTransaction *__hidden this)`
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
- `0x180068c70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068e63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068e63`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::PrepareTransaction::StopActivity(NetSetupTraceLogging::PrepareTransaction *this)
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
        (int)&word_1800B222A,
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
        (int)&byte_1800B21D7,
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
0x180068c70  push    rbp
0x180068c72  push    rbx
0x180068c73  push    rdi
0x180068c74  lea     rbp, [rsp+10h]
0x180068c79  sub     rsp, 130h
0x180068c80  mov     rdi, [rcx+110h]
0x180068c87  mov     rbx, rcx
0x180068c8a  mov     eax, [rdi+48h]
0x180068c8d  test    eax, eax
0x180068c8f  jns     loc_180068E3E
0x180068c95  add     rdi, 50h ; 'P'
0x180068c99  cmp     eax, [rdi+8]
0x180068c9c  jnz     loc_180068E3E
0x180068ca2  test    rdi, rdi
0x180068ca5  jz      loc_180068E3E
0x180068cab  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180068cb0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180068cb5  mov     r9, rax
0x180068cb8  mov     ecx, [rax]
0x180068cba  cmp     ecx, 5
0x180068cbd  jbe     loc_180068EB0
0x180068cc3  mov     edx, 1
0x180068cc8  mov     rcx, rax
0x180068ccb  call    _tlgKeywordOn
0x180068cd0  test    al, al
0x180068cd2  jz      loc_180068EB0
0x180068cd8  mov     rax, [rdi+30h]
0x180068cdc  lea     rdx, word_1800B222A; int
0x180068ce3  mov     [rbp+var_70], rax
0x180068ce7  mov     rcx, r9; int
0x180068cea  mov     eax, [rdi+44h]
0x180068ced  mov     dword ptr [rbp+arg_0], eax
0x180068cf0  mov     eax, [rdi+10h]
0x180068cf3  mov     dword ptr [rbp+arg_8], eax
0x180068cf6  mov     rax, [rdi+78h]
0x180068cfa  mov     [rbp+var_68], rax
0x180068cfe  mov     rax, [rdi+70h]
0x180068d02  mov     [rbp+var_60], rax
0x180068d06  mov     eax, [rdi+68h]
0x180068d09  mov     r8, [rbx+110h]
0x180068d10  mov     dword ptr [rbp+arg_10], eax
0x180068d13  add     r8, 8; int
0x180068d17  mov     rax, [rdi+60h]
0x180068d1b  mov     [rbp+var_58], rax
0x180068d1f  mov     rax, [rdi+58h]
0x180068d23  mov     [rbp+var_50], rax
0x180068d27  mov     eax, [rdi+50h]
0x180068d2a  mov     dword ptr [rbp+arg_18], eax
0x180068d2d  mov     rax, [rdi+48h]
0x180068d31  mov     [rbp+var_48], rax
0x180068d35  mov     eax, [rdi+20h]
0x180068d38  mov     dword ptr [rbp+var_80], eax
0x180068d3b  mov     rax, [rdi+18h]
0x180068d3f  mov     [rbp+var_40], rax
0x180068d43  mov     eax, [rdi]
0x180068d45  mov     dword ptr [rbp+var_80+4], eax
0x180068d48  mov     rax, [rdi+80h]
0x180068d4f  mov     [rbp+var_38], rax
0x180068d53  mov     eax, [rdi+40h]
0x180068d56  mov     dword ptr [rbp+var_78], eax
0x180068d59  mov     rax, [rdi+38h]
0x180068d5d  mov     [rbp+var_30], rax
0x180068d61  mov     eax, [rdi+8]
0x180068d64  mov     dword ptr [rbp+var_78+4], eax
0x180068d67  lea     rax, [rbp+var_70]
0x180068d6b  mov     [rsp+140h+var_90], rax; __int64
0x180068d73  lea     rax, [rbp+arg_0]
0x180068d77  mov     [rsp+140h+var_98], rax; __int64
0x180068d7f  lea     rax, [rbp+arg_8]
0x180068d83  mov     [rsp+140h+var_A0], rax; __int64
0x180068d8b  lea     rax, [rbp+var_68]
0x180068d8f  mov     [rsp+140h+var_A8], rax; __int64
0x180068d97  lea     rax, [rbp+var_60]
0x180068d9b  mov     [rsp+140h+var_B0], rax; __int64
0x180068da3  lea     rax, [rbp+arg_10]
0x180068da7  mov     [rsp+140h+var_B8], rax; __int64
0x180068daf  lea     rax, [rbp+var_58]
0x180068db3  mov     [rsp+140h+var_C0], rax; __int64
0x180068dbb  lea     rax, [rbp+var_50]
0x180068dbf  mov     [rsp+140h+var_C8], rax; __int64
0x180068dc4  lea     rax, [rbp+arg_18]
0x180068dc8  mov     [rsp+140h+var_D0], rax; __int64
0x180068dcd  lea     rax, [rbp+var_48]
0x180068dd1  mov     [rsp+140h+var_D8], rax; __int64
0x180068dd6  lea     rax, [rbp+var_80]
0x180068dda  mov     [rsp+140h+var_E0], rax; __int64
0x180068ddf  lea     rax, [rbp+var_40]
0x180068de3  mov     [rsp+140h+var_E8], rax; __int64
0x180068de8  lea     rax, [rbp+var_80+4]
0x180068dec  mov     [rsp+140h+var_F0], rax; __int64
0x180068df1  lea     rax, [rbp+var_38]
0x180068df5  mov     [rsp+140h+var_F8], rax; __int64
0x180068dfa  lea     rax, [rbp+var_78]
0x180068dfe  mov     [rsp+140h+var_100], rax; __int64
0x180068e03  lea     rax, [rbp+var_30]
0x180068e07  mov     [rsp+140h+var_108], rax; __int64
0x180068e0c  lea     rax, [rbp+var_78+4]
0x180068e10  mov     [rsp+140h+var_110], rax; __int64
0x180068e15  lea     rax, [rbp+var_28]
0x180068e19  mov     [rsp+140h+var_118], rax; __int64
0x180068e1e  lea     rax, [rbp+var_20]
0x180068e22  mov     [rsp+140h+var_120], rax; __int64
0x180068e27  mov     [rbp+var_28], 1000000h
0x180068e2f  mov     [rbp+var_20], 0
0x180068e37  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180068e3c  jmp     short loc_180068EB0
0x180068e3e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180068e43  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180068e48  mov     rdi, rax
0x180068e4b  mov     ecx, [rax]
0x180068e4d  cmp     ecx, 5
0x180068e50  jbe     short loc_180068EB0
0x180068e52  mov     edx, 1
0x180068e57  mov     rcx, rax
0x180068e5a  call    _tlgKeywordOn
0x180068e5f  test    al, al
0x180068e61  jz      short loc_180068EB0
0x180068e63  call    cs:__imp_GetCurrentThreadId
0x180068e69  mov     r8, [rbx+110h]
0x180068e70  lea     rdx, byte_1800B21D7
0x180068e77  mov     dword ptr [rbp+arg_0], eax
0x180068e7a  mov     rcx, rdi
0x180068e7d  mov     eax, [r8+48h]
0x180068e81  add     r8, 8
0x180068e85  mov     dword ptr [rbp+arg_8], eax
0x180068e88  lea     rax, [rbp+arg_0]
0x180068e8c  mov     [rsp+140h+var_110], rax
0x180068e91  lea     rax, [rbp+arg_8]
0x180068e95  mov     [rsp+140h+var_118], rax
0x180068e9a  lea     rax, [rbp+arg_10]
0x180068e9e  mov     [rsp+140h+var_120], rax
0x180068ea3  mov     [rbp+arg_10], 0
0x180068eab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180068eb0  mov     rcx, rbx
0x180068eb3  add     rsp, 130h
0x180068eba  pop     rdi
0x180068ebb  pop     rbx
0x180068ebc  pop     rbp
0x180068ebd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
