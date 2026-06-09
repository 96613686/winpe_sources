# NetSetupTraceLogging::InvokePlugins::StopActivity(void)

- ea: `0x180046bf0`
- end: `0x180046e42`
- name: `?StopActivity@InvokePlugins@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::InvokePlugins *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x18000154c`
- `0x180001860`
- `0x18000e54c`
- `0x180033720`
- `0x18003a95c`
- `0x180046bf0`
- `0x180046ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046de3`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::InvokePlugins::StopActivity(NetSetupTraceLogging::InvokePlugins *this)
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
        (int)&word_1800B1E46,
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
        (int)qword_1800B1DF8,
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
0x180046bf0  push    rbp
0x180046bf2  push    rbx
0x180046bf3  push    rdi
0x180046bf4  lea     rbp, [rsp+10h]
0x180046bf9  sub     rsp, 130h
0x180046c00  mov     rdi, [rcx+110h]
0x180046c07  mov     rbx, rcx
0x180046c0a  mov     eax, [rdi+48h]
0x180046c0d  test    eax, eax
0x180046c0f  jns     loc_180046DBE
0x180046c15  add     rdi, 50h ; 'P'
0x180046c19  cmp     eax, [rdi+8]
0x180046c1c  jnz     loc_180046DBE
0x180046c22  test    rdi, rdi
0x180046c25  jz      loc_180046DBE
0x180046c2b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046c30  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180046c35  mov     r9, rax
0x180046c38  mov     ecx, [rax]
0x180046c3a  cmp     ecx, 5
0x180046c3d  jbe     loc_180046E30
0x180046c43  mov     edx, 4
0x180046c48  mov     rcx, rax
0x180046c4b  call    _tlgKeywordOn
0x180046c50  test    al, al
0x180046c52  jz      loc_180046E30
0x180046c58  mov     rax, [rdi+30h]
0x180046c5c  lea     rdx, word_1800B1E46; int
0x180046c63  mov     [rbp+var_70], rax
0x180046c67  mov     rcx, r9; int
0x180046c6a  mov     eax, [rdi+44h]
0x180046c6d  mov     dword ptr [rbp+arg_0], eax
0x180046c70  mov     eax, [rdi+10h]
0x180046c73  mov     dword ptr [rbp+arg_8], eax
0x180046c76  mov     rax, [rdi+78h]
0x180046c7a  mov     [rbp+var_68], rax
0x180046c7e  mov     rax, [rdi+70h]
0x180046c82  mov     [rbp+var_60], rax
0x180046c86  mov     eax, [rdi+68h]
0x180046c89  mov     r8, [rbx+110h]
0x180046c90  mov     dword ptr [rbp+arg_10], eax
0x180046c93  add     r8, 8; int
0x180046c97  mov     rax, [rdi+60h]
0x180046c9b  mov     [rbp+var_58], rax
0x180046c9f  mov     rax, [rdi+58h]
0x180046ca3  mov     [rbp+var_50], rax
0x180046ca7  mov     eax, [rdi+50h]
0x180046caa  mov     dword ptr [rbp+arg_18], eax
0x180046cad  mov     rax, [rdi+48h]
0x180046cb1  mov     [rbp+var_48], rax
0x180046cb5  mov     eax, [rdi+20h]
0x180046cb8  mov     dword ptr [rbp+var_80], eax
0x180046cbb  mov     rax, [rdi+18h]
0x180046cbf  mov     [rbp+var_40], rax
0x180046cc3  mov     eax, [rdi]
0x180046cc5  mov     dword ptr [rbp+var_80+4], eax
0x180046cc8  mov     rax, [rdi+80h]
0x180046ccf  mov     [rbp+var_38], rax
0x180046cd3  mov     eax, [rdi+40h]
0x180046cd6  mov     dword ptr [rbp+var_78], eax
0x180046cd9  mov     rax, [rdi+38h]
0x180046cdd  mov     [rbp+var_30], rax
0x180046ce1  mov     eax, [rdi+8]
0x180046ce4  mov     dword ptr [rbp+var_78+4], eax
0x180046ce7  lea     rax, [rbp+var_70]
0x180046ceb  mov     [rsp+140h+var_90], rax; __int64
0x180046cf3  lea     rax, [rbp+arg_0]
0x180046cf7  mov     [rsp+140h+var_98], rax; __int64
0x180046cff  lea     rax, [rbp+arg_8]
0x180046d03  mov     [rsp+140h+var_A0], rax; __int64
0x180046d0b  lea     rax, [rbp+var_68]
0x180046d0f  mov     [rsp+140h+var_A8], rax; __int64
0x180046d17  lea     rax, [rbp+var_60]
0x180046d1b  mov     [rsp+140h+var_B0], rax; __int64
0x180046d23  lea     rax, [rbp+arg_10]
0x180046d27  mov     [rsp+140h+var_B8], rax; __int64
0x180046d2f  lea     rax, [rbp+var_58]
0x180046d33  mov     [rsp+140h+var_C0], rax; __int64
0x180046d3b  lea     rax, [rbp+var_50]
0x180046d3f  mov     [rsp+140h+var_C8], rax; __int64
0x180046d44  lea     rax, [rbp+arg_18]
0x180046d48  mov     [rsp+140h+var_D0], rax; __int64
0x180046d4d  lea     rax, [rbp+var_48]
0x180046d51  mov     [rsp+140h+var_D8], rax; __int64
0x180046d56  lea     rax, [rbp+var_80]
0x180046d5a  mov     [rsp+140h+var_E0], rax; __int64
0x180046d5f  lea     rax, [rbp+var_40]
0x180046d63  mov     [rsp+140h+var_E8], rax; __int64
0x180046d68  lea     rax, [rbp+var_80+4]
0x180046d6c  mov     [rsp+140h+var_F0], rax; __int64
0x180046d71  lea     rax, [rbp+var_38]
0x180046d75  mov     [rsp+140h+var_F8], rax; __int64
0x180046d7a  lea     rax, [rbp+var_78]
0x180046d7e  mov     [rsp+140h+var_100], rax; __int64
0x180046d83  lea     rax, [rbp+var_30]
0x180046d87  mov     [rsp+140h+var_108], rax; __int64
0x180046d8c  lea     rax, [rbp+var_78+4]
0x180046d90  mov     [rsp+140h+var_110], rax; __int64
0x180046d95  lea     rax, [rbp+var_28]
0x180046d99  mov     [rsp+140h+var_118], rax; __int64
0x180046d9e  lea     rax, [rbp+var_20]
0x180046da2  mov     [rsp+140h+var_120], rax; __int64
0x180046da7  mov     [rbp+var_28], 1000000h
0x180046daf  mov     [rbp+var_20], 0
0x180046db7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180046dbc  jmp     short loc_180046E30
0x180046dbe  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180046dc3  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180046dc8  mov     rdi, rax
0x180046dcb  mov     ecx, [rax]
0x180046dcd  cmp     ecx, 5
0x180046dd0  jbe     short loc_180046E30
0x180046dd2  mov     edx, 4
0x180046dd7  mov     rcx, rax
0x180046dda  call    _tlgKeywordOn
0x180046ddf  test    al, al
0x180046de1  jz      short loc_180046E30
0x180046de3  call    cs:__imp_GetCurrentThreadId
0x180046de9  mov     r8, [rbx+110h]
0x180046df0  lea     rdx, qword_1800B1DF8
0x180046df7  mov     dword ptr [rbp+arg_0], eax
0x180046dfa  mov     rcx, rdi
0x180046dfd  mov     eax, [r8+48h]
0x180046e01  add     r8, 8
0x180046e05  mov     dword ptr [rbp+arg_8], eax
0x180046e08  lea     rax, [rbp+arg_0]
0x180046e0c  mov     [rsp+140h+var_110], rax
0x180046e11  lea     rax, [rbp+arg_8]
0x180046e15  mov     [rsp+140h+var_118], rax
0x180046e1a  lea     rax, [rbp+arg_10]
0x180046e1e  mov     [rsp+140h+var_120], rax
0x180046e23  mov     [rbp+arg_10], 0
0x180046e2b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046e30  mov     rcx, rbx
0x180046e33  add     rsp, 130h
0x180046e3a  pop     rdi
0x180046e3b  pop     rbx
0x180046e3c  pop     rbp
0x180046e3d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
