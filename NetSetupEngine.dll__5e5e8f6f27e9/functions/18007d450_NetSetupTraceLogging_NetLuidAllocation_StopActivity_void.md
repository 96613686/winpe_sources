# NetSetupTraceLogging::NetLuidAllocation::StopActivity(void)

- ea: `0x18007d450`
- end: `0x18007d6a2`
- name: `?StopActivity@NetLuidAllocation@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::NetLuidAllocation *__hidden this)`
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
- `0x18007d450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d643`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::NetLuidAllocation::StopActivity(NetSetupTraceLogging::NetLuidAllocation *this)
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
        (int)&word_1800B4C8E,
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
        (int)&dword_1800B4C3C,
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
0x18007d450  push    rbp
0x18007d452  push    rbx
0x18007d453  push    rdi
0x18007d454  lea     rbp, [rsp+10h]
0x18007d459  sub     rsp, 130h
0x18007d460  mov     rdi, [rcx+110h]
0x18007d467  mov     rbx, rcx
0x18007d46a  mov     eax, [rdi+48h]
0x18007d46d  test    eax, eax
0x18007d46f  jns     loc_18007D61E
0x18007d475  add     rdi, 50h ; 'P'
0x18007d479  cmp     eax, [rdi+8]
0x18007d47c  jnz     loc_18007D61E
0x18007d482  test    rdi, rdi
0x18007d485  jz      loc_18007D61E
0x18007d48b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18007d490  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18007d495  mov     r9, rax
0x18007d498  mov     ecx, [rax]
0x18007d49a  cmp     ecx, 5
0x18007d49d  jbe     loc_18007D690
0x18007d4a3  mov     edx, 1
0x18007d4a8  mov     rcx, rax
0x18007d4ab  call    _tlgKeywordOn
0x18007d4b0  test    al, al
0x18007d4b2  jz      loc_18007D690
0x18007d4b8  mov     rax, [rdi+30h]
0x18007d4bc  lea     rdx, word_1800B4C8E; int
0x18007d4c3  mov     [rbp+var_70], rax
0x18007d4c7  mov     rcx, r9; int
0x18007d4ca  mov     eax, [rdi+44h]
0x18007d4cd  mov     dword ptr [rbp+arg_0], eax
0x18007d4d0  mov     eax, [rdi+10h]
0x18007d4d3  mov     dword ptr [rbp+arg_8], eax
0x18007d4d6  mov     rax, [rdi+78h]
0x18007d4da  mov     [rbp+var_68], rax
0x18007d4de  mov     rax, [rdi+70h]
0x18007d4e2  mov     [rbp+var_60], rax
0x18007d4e6  mov     eax, [rdi+68h]
0x18007d4e9  mov     r8, [rbx+110h]
0x18007d4f0  mov     dword ptr [rbp+arg_10], eax
0x18007d4f3  add     r8, 8; int
0x18007d4f7  mov     rax, [rdi+60h]
0x18007d4fb  mov     [rbp+var_58], rax
0x18007d4ff  mov     rax, [rdi+58h]
0x18007d503  mov     [rbp+var_50], rax
0x18007d507  mov     eax, [rdi+50h]
0x18007d50a  mov     dword ptr [rbp+arg_18], eax
0x18007d50d  mov     rax, [rdi+48h]
0x18007d511  mov     [rbp+var_48], rax
0x18007d515  mov     eax, [rdi+20h]
0x18007d518  mov     dword ptr [rbp+var_80], eax
0x18007d51b  mov     rax, [rdi+18h]
0x18007d51f  mov     [rbp+var_40], rax
0x18007d523  mov     eax, [rdi]
0x18007d525  mov     dword ptr [rbp+var_80+4], eax
0x18007d528  mov     rax, [rdi+80h]
0x18007d52f  mov     [rbp+var_38], rax
0x18007d533  mov     eax, [rdi+40h]
0x18007d536  mov     dword ptr [rbp+var_78], eax
0x18007d539  mov     rax, [rdi+38h]
0x18007d53d  mov     [rbp+var_30], rax
0x18007d541  mov     eax, [rdi+8]
0x18007d544  mov     dword ptr [rbp+var_78+4], eax
0x18007d547  lea     rax, [rbp+var_70]
0x18007d54b  mov     [rsp+140h+var_90], rax; __int64
0x18007d553  lea     rax, [rbp+arg_0]
0x18007d557  mov     [rsp+140h+var_98], rax; __int64
0x18007d55f  lea     rax, [rbp+arg_8]
0x18007d563  mov     [rsp+140h+var_A0], rax; __int64
0x18007d56b  lea     rax, [rbp+var_68]
0x18007d56f  mov     [rsp+140h+var_A8], rax; __int64
0x18007d577  lea     rax, [rbp+var_60]
0x18007d57b  mov     [rsp+140h+var_B0], rax; __int64
0x18007d583  lea     rax, [rbp+arg_10]
0x18007d587  mov     [rsp+140h+var_B8], rax; __int64
0x18007d58f  lea     rax, [rbp+var_58]
0x18007d593  mov     [rsp+140h+var_C0], rax; __int64
0x18007d59b  lea     rax, [rbp+var_50]
0x18007d59f  mov     [rsp+140h+var_C8], rax; __int64
0x18007d5a4  lea     rax, [rbp+arg_18]
0x18007d5a8  mov     [rsp+140h+var_D0], rax; __int64
0x18007d5ad  lea     rax, [rbp+var_48]
0x18007d5b1  mov     [rsp+140h+var_D8], rax; __int64
0x18007d5b6  lea     rax, [rbp+var_80]
0x18007d5ba  mov     [rsp+140h+var_E0], rax; __int64
0x18007d5bf  lea     rax, [rbp+var_40]
0x18007d5c3  mov     [rsp+140h+var_E8], rax; __int64
0x18007d5c8  lea     rax, [rbp+var_80+4]
0x18007d5cc  mov     [rsp+140h+var_F0], rax; __int64
0x18007d5d1  lea     rax, [rbp+var_38]
0x18007d5d5  mov     [rsp+140h+var_F8], rax; __int64
0x18007d5da  lea     rax, [rbp+var_78]
0x18007d5de  mov     [rsp+140h+var_100], rax; __int64
0x18007d5e3  lea     rax, [rbp+var_30]
0x18007d5e7  mov     [rsp+140h+var_108], rax; __int64
0x18007d5ec  lea     rax, [rbp+var_78+4]
0x18007d5f0  mov     [rsp+140h+var_110], rax; __int64
0x18007d5f5  lea     rax, [rbp+var_28]
0x18007d5f9  mov     [rsp+140h+var_118], rax; __int64
0x18007d5fe  lea     rax, [rbp+var_20]
0x18007d602  mov     [rsp+140h+var_120], rax; __int64
0x18007d607  mov     [rbp+var_28], 1000000h
0x18007d60f  mov     [rbp+var_20], 0
0x18007d617  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007d61c  jmp     short loc_18007D690
0x18007d61e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18007d623  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18007d628  mov     rdi, rax
0x18007d62b  mov     ecx, [rax]
0x18007d62d  cmp     ecx, 5
0x18007d630  jbe     short loc_18007D690
0x18007d632  mov     edx, 1
0x18007d637  mov     rcx, rax
0x18007d63a  call    _tlgKeywordOn
0x18007d63f  test    al, al
0x18007d641  jz      short loc_18007D690
0x18007d643  call    cs:__imp_GetCurrentThreadId
0x18007d649  mov     r8, [rbx+110h]
0x18007d650  lea     rdx, dword_1800B4C3C
0x18007d657  mov     dword ptr [rbp+arg_0], eax
0x18007d65a  mov     rcx, rdi
0x18007d65d  mov     eax, [r8+48h]
0x18007d661  add     r8, 8
0x18007d665  mov     dword ptr [rbp+arg_8], eax
0x18007d668  lea     rax, [rbp+arg_0]
0x18007d66c  mov     [rsp+140h+var_110], rax
0x18007d671  lea     rax, [rbp+arg_8]
0x18007d675  mov     [rsp+140h+var_118], rax
0x18007d67a  lea     rax, [rbp+arg_10]
0x18007d67e  mov     [rsp+140h+var_120], rax
0x18007d683  mov     [rbp+arg_10], 0
0x18007d68b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007d690  mov     rcx, rbx
0x18007d693  add     rsp, 130h
0x18007d69a  pop     rdi
0x18007d69b  pop     rbx
0x18007d69c  pop     rbp
0x18007d69d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
