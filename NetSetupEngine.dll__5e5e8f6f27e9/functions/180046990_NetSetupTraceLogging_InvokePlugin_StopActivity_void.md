# NetSetupTraceLogging::InvokePlugin::StopActivity(void)

- ea: `0x180046990`
- end: `0x180046be2`
- name: `?StopActivity@InvokePlugin@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::InvokePlugin *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x18000154c`
- `0x180001860`
- `0x18000e54c`
- `0x180033720`
- `0x18003a95c`
- `0x180046990`
- `0x180046ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b83`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::InvokePlugin::StopActivity(NetSetupTraceLogging::InvokePlugin *this)
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
    wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = NetSetupTraceLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 4, v7, v5) )
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
        (int)&word_1800B1C4E,
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
    wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = NetSetupTraceLogging::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 4, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(v30) = CurrentThreadId;
      LODWORD(v31) = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)byte_1800B1C01,
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
0x180046990  push    rbp
0x180046992  push    rbx
0x180046993  push    rdi
0x180046994  lea     rbp, [rsp+10h]
0x180046999  sub     rsp, 130h
0x1800469a0  mov     rdi, [rcx+110h]
0x1800469a7  mov     rbx, rcx
0x1800469aa  mov     eax, [rdi+48h]
0x1800469ad  test    eax, eax
0x1800469af  jns     loc_180046B5E
0x1800469b5  add     rdi, 50h ; 'P'
0x1800469b9  cmp     eax, [rdi+8]
0x1800469bc  jnz     loc_180046B5E
0x1800469c2  test    rdi, rdi
0x1800469c5  jz      loc_180046B5E
0x1800469cb  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800469d0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800469d5  mov     r9, rax
0x1800469d8  mov     ecx, [rax]
0x1800469da  cmp     ecx, 5
0x1800469dd  jbe     loc_180046BD0
0x1800469e3  mov     edx, 4
0x1800469e8  mov     rcx, rax
0x1800469eb  call    _tlgKeywordOn
0x1800469f0  test    al, al
0x1800469f2  jz      loc_180046BD0
0x1800469f8  mov     rax, [rdi+30h]
0x1800469fc  lea     rdx, word_1800B1C4E; int
0x180046a03  mov     [rbp+var_70], rax
0x180046a07  mov     rcx, r9; int
0x180046a0a  mov     eax, [rdi+44h]
0x180046a0d  mov     dword ptr [rbp+arg_0], eax
0x180046a10  mov     eax, [rdi+10h]
0x180046a13  mov     dword ptr [rbp+arg_8], eax
0x180046a16  mov     rax, [rdi+78h]
0x180046a1a  mov     [rbp+var_68], rax
0x180046a1e  mov     rax, [rdi+70h]
0x180046a22  mov     [rbp+var_60], rax
0x180046a26  mov     eax, [rdi+68h]
0x180046a29  mov     r8, [rbx+110h]
0x180046a30  mov     dword ptr [rbp+arg_10], eax
0x180046a33  add     r8, 8; int
0x180046a37  mov     rax, [rdi+60h]
0x180046a3b  mov     [rbp+var_58], rax
0x180046a3f  mov     rax, [rdi+58h]
0x180046a43  mov     [rbp+var_50], rax
0x180046a47  mov     eax, [rdi+50h]
0x180046a4a  mov     dword ptr [rbp+arg_18], eax
0x180046a4d  mov     rax, [rdi+48h]
0x180046a51  mov     [rbp+var_48], rax
0x180046a55  mov     eax, [rdi+20h]
0x180046a58  mov     dword ptr [rbp+var_80], eax
0x180046a5b  mov     rax, [rdi+18h]
0x180046a5f  mov     [rbp+var_40], rax
0x180046a63  mov     eax, [rdi]
0x180046a65  mov     dword ptr [rbp+var_80+4], eax
0x180046a68  mov     rax, [rdi+80h]
0x180046a6f  mov     [rbp+var_38], rax
0x180046a73  mov     eax, [rdi+40h]
0x180046a76  mov     dword ptr [rbp+var_78], eax
0x180046a79  mov     rax, [rdi+38h]
0x180046a7d  mov     [rbp+var_30], rax
0x180046a81  mov     eax, [rdi+8]
0x180046a84  mov     dword ptr [rbp+var_78+4], eax
0x180046a87  lea     rax, [rbp+var_70]
0x180046a8b  mov     [rsp+140h+var_90], rax; __int64
0x180046a93  lea     rax, [rbp+arg_0]
0x180046a97  mov     [rsp+140h+var_98], rax; __int64
0x180046a9f  lea     rax, [rbp+arg_8]
0x180046aa3  mov     [rsp+140h+var_A0], rax; __int64
0x180046aab  lea     rax, [rbp+var_68]
0x180046aaf  mov     [rsp+140h+var_A8], rax; __int64
0x180046ab7  lea     rax, [rbp+var_60]
0x180046abb  mov     [rsp+140h+var_B0], rax; __int64
0x180046ac3  lea     rax, [rbp+arg_10]
0x180046ac7  mov     [rsp+140h+var_B8], rax; __int64
0x180046acf  lea     rax, [rbp+var_58]
0x180046ad3  mov     [rsp+140h+var_C0], rax; __int64
0x180046adb  lea     rax, [rbp+var_50]
0x180046adf  mov     [rsp+140h+var_C8], rax; __int64
0x180046ae4  lea     rax, [rbp+arg_18]
0x180046ae8  mov     [rsp+140h+var_D0], rax; __int64
0x180046aed  lea     rax, [rbp+var_48]
0x180046af1  mov     [rsp+140h+var_D8], rax; __int64
0x180046af6  lea     rax, [rbp+var_80]
0x180046afa  mov     [rsp+140h+var_E0], rax; __int64
0x180046aff  lea     rax, [rbp+var_40]
0x180046b03  mov     [rsp+140h+var_E8], rax; __int64
0x180046b08  lea     rax, [rbp+var_80+4]
0x180046b0c  mov     [rsp+140h+var_F0], rax; __int64
0x180046b11  lea     rax, [rbp+var_38]
0x180046b15  mov     [rsp+140h+var_F8], rax; __int64
0x180046b1a  lea     rax, [rbp+var_78]
0x180046b1e  mov     [rsp+140h+var_100], rax; __int64
0x180046b23  lea     rax, [rbp+var_30]
0x180046b27  mov     [rsp+140h+var_108], rax; __int64
0x180046b2c  lea     rax, [rbp+var_78+4]
0x180046b30  mov     [rsp+140h+var_110], rax; __int64
0x180046b35  lea     rax, [rbp+var_28]
0x180046b39  mov     [rsp+140h+var_118], rax; __int64
0x180046b3e  lea     rax, [rbp+var_20]
0x180046b42  mov     [rsp+140h+var_120], rax; __int64
0x180046b47  mov     [rbp+var_28], 1000000h
0x180046b4f  mov     [rbp+var_20], 0
0x180046b57  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180046b5c  jmp     short loc_180046BD0
0x180046b5e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046b63  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180046b68  mov     rdi, rax
0x180046b6b  mov     ecx, [rax]
0x180046b6d  cmp     ecx, 5
0x180046b70  jbe     short loc_180046BD0
0x180046b72  mov     edx, 4
0x180046b77  mov     rcx, rax
0x180046b7a  call    _tlgKeywordOn
0x180046b7f  test    al, al
0x180046b81  jz      short loc_180046BD0
0x180046b83  call    cs:__imp_GetCurrentThreadId
0x180046b89  mov     r8, [rbx+110h]
0x180046b90  lea     rdx, byte_1800B1C01
0x180046b97  mov     dword ptr [rbp+arg_0], eax
0x180046b9a  mov     rcx, rdi
0x180046b9d  mov     eax, [r8+48h]
0x180046ba1  add     r8, 8
0x180046ba5  mov     dword ptr [rbp+arg_8], eax
0x180046ba8  lea     rax, [rbp+arg_0]
0x180046bac  mov     [rsp+140h+var_110], rax
0x180046bb1  lea     rax, [rbp+arg_8]
0x180046bb5  mov     [rsp+140h+var_118], rax
0x180046bba  lea     rax, [rbp+arg_10]
0x180046bbe  mov     [rsp+140h+var_120], rax
0x180046bc3  mov     [rbp+arg_10], 0
0x180046bcb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046bd0  mov     rcx, rbx
0x180046bd3  add     rsp, 130h
0x180046bda  pop     rdi
0x180046bdb  pop     rbx
0x180046bdc  pop     rbp
0x180046bdd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
