# NetSetupTraceLogging::RpcNetSetupGetObjectProperties::StopActivity(void)

- ea: `0x180015840`
- end: `0x180015a92`
- name: `?StopActivity@RpcNetSetupGetObjectProperties@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupGetObjectProperties *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001420`
- `0x180001734`
- `0x180001b50`
- `0x180013aa4`
- `0x180014090`
- `0x180015840`
- `0x1800170d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a33`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupGetObjectProperties::StopActivity(
        NetSetupTraceLogging::RpcNetSetupGetObjectProperties *this)
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
        (int)&byte_1800404C3,
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
        (int)&dword_180040464,
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
0x180015840  push    rbp
0x180015842  push    rbx
0x180015843  push    rdi
0x180015844  lea     rbp, [rsp+10h]
0x180015849  sub     rsp, 130h
0x180015850  mov     rdi, [rcx+110h]
0x180015857  mov     rbx, rcx
0x18001585a  mov     eax, [rdi+48h]
0x18001585d  test    eax, eax
0x18001585f  jns     loc_180015A0E
0x180015865  add     rdi, 50h ; 'P'
0x180015869  cmp     eax, [rdi+8]
0x18001586c  jnz     loc_180015A0E
0x180015872  test    rdi, rdi
0x180015875  jz      loc_180015A0E
0x18001587b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015880  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180015885  mov     r9, rax
0x180015888  mov     ecx, [rax]
0x18001588a  cmp     ecx, 5
0x18001588d  jbe     loc_180015A80
0x180015893  mov     edx, 1
0x180015898  mov     rcx, rax
0x18001589b  call    _tlgKeywordOn
0x1800158a0  test    al, al
0x1800158a2  jz      loc_180015A80
0x1800158a8  mov     rax, [rdi+30h]
0x1800158ac  lea     rdx, byte_1800404C3; int
0x1800158b3  mov     [rbp+var_70], rax
0x1800158b7  mov     rcx, r9; int
0x1800158ba  mov     eax, [rdi+44h]
0x1800158bd  mov     dword ptr [rbp+arg_0], eax
0x1800158c0  mov     eax, [rdi+10h]
0x1800158c3  mov     dword ptr [rbp+arg_8], eax
0x1800158c6  mov     rax, [rdi+78h]
0x1800158ca  mov     [rbp+var_68], rax
0x1800158ce  mov     rax, [rdi+70h]
0x1800158d2  mov     [rbp+var_60], rax
0x1800158d6  mov     eax, [rdi+68h]
0x1800158d9  mov     r8, [rbx+110h]
0x1800158e0  mov     dword ptr [rbp+arg_10], eax
0x1800158e3  add     r8, 8; int
0x1800158e7  mov     rax, [rdi+60h]
0x1800158eb  mov     [rbp+var_58], rax
0x1800158ef  mov     rax, [rdi+58h]
0x1800158f3  mov     [rbp+var_50], rax
0x1800158f7  mov     eax, [rdi+50h]
0x1800158fa  mov     dword ptr [rbp+arg_18], eax
0x1800158fd  mov     rax, [rdi+48h]
0x180015901  mov     [rbp+var_48], rax
0x180015905  mov     eax, [rdi+20h]
0x180015908  mov     dword ptr [rbp+var_80], eax
0x18001590b  mov     rax, [rdi+18h]
0x18001590f  mov     [rbp+var_40], rax
0x180015913  mov     eax, [rdi]
0x180015915  mov     dword ptr [rbp+var_80+4], eax
0x180015918  mov     rax, [rdi+80h]
0x18001591f  mov     [rbp+var_38], rax
0x180015923  mov     eax, [rdi+40h]
0x180015926  mov     dword ptr [rbp+var_78], eax
0x180015929  mov     rax, [rdi+38h]
0x18001592d  mov     [rbp+var_30], rax
0x180015931  mov     eax, [rdi+8]
0x180015934  mov     dword ptr [rbp+var_78+4], eax
0x180015937  lea     rax, [rbp+var_70]
0x18001593b  mov     [rsp+140h+var_90], rax; __int64
0x180015943  lea     rax, [rbp+arg_0]
0x180015947  mov     [rsp+140h+var_98], rax; __int64
0x18001594f  lea     rax, [rbp+arg_8]
0x180015953  mov     [rsp+140h+var_A0], rax; __int64
0x18001595b  lea     rax, [rbp+var_68]
0x18001595f  mov     [rsp+140h+var_A8], rax; __int64
0x180015967  lea     rax, [rbp+var_60]
0x18001596b  mov     [rsp+140h+var_B0], rax; __int64
0x180015973  lea     rax, [rbp+arg_10]
0x180015977  mov     [rsp+140h+var_B8], rax; __int64
0x18001597f  lea     rax, [rbp+var_58]
0x180015983  mov     [rsp+140h+var_C0], rax; __int64
0x18001598b  lea     rax, [rbp+var_50]
0x18001598f  mov     [rsp+140h+var_C8], rax; __int64
0x180015994  lea     rax, [rbp+arg_18]
0x180015998  mov     [rsp+140h+var_D0], rax; __int64
0x18001599d  lea     rax, [rbp+var_48]
0x1800159a1  mov     [rsp+140h+var_D8], rax; __int64
0x1800159a6  lea     rax, [rbp+var_80]
0x1800159aa  mov     [rsp+140h+var_E0], rax; __int64
0x1800159af  lea     rax, [rbp+var_40]
0x1800159b3  mov     [rsp+140h+var_E8], rax; __int64
0x1800159b8  lea     rax, [rbp+var_80+4]
0x1800159bc  mov     [rsp+140h+var_F0], rax; __int64
0x1800159c1  lea     rax, [rbp+var_38]
0x1800159c5  mov     [rsp+140h+var_F8], rax; __int64
0x1800159ca  lea     rax, [rbp+var_78]
0x1800159ce  mov     [rsp+140h+var_100], rax; __int64
0x1800159d3  lea     rax, [rbp+var_30]
0x1800159d7  mov     [rsp+140h+var_108], rax; __int64
0x1800159dc  lea     rax, [rbp+var_78+4]
0x1800159e0  mov     [rsp+140h+var_110], rax; __int64
0x1800159e5  lea     rax, [rbp+var_28]
0x1800159e9  mov     [rsp+140h+var_118], rax; __int64
0x1800159ee  lea     rax, [rbp+var_20]
0x1800159f2  mov     [rsp+140h+var_120], rax; __int64
0x1800159f7  mov     [rbp+var_28], 1000000h
0x1800159ff  mov     [rbp+var_20], 0
0x180015a07  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180015a0c  jmp     short loc_180015A80
0x180015a0e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015a13  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180015a18  mov     rdi, rax
0x180015a1b  mov     ecx, [rax]
0x180015a1d  cmp     ecx, 5
0x180015a20  jbe     short loc_180015A80
0x180015a22  mov     edx, 1
0x180015a27  mov     rcx, rax
0x180015a2a  call    _tlgKeywordOn
0x180015a2f  test    al, al
0x180015a31  jz      short loc_180015A80
0x180015a33  call    cs:__imp_GetCurrentThreadId
0x180015a39  mov     r8, [rbx+110h]
0x180015a40  lea     rdx, dword_180040464
0x180015a47  mov     dword ptr [rbp+arg_0], eax
0x180015a4a  mov     rcx, rdi
0x180015a4d  mov     eax, [r8+48h]
0x180015a51  add     r8, 8
0x180015a55  mov     dword ptr [rbp+arg_8], eax
0x180015a58  lea     rax, [rbp+arg_0]
0x180015a5c  mov     [rsp+140h+var_110], rax
0x180015a61  lea     rax, [rbp+arg_8]
0x180015a65  mov     [rsp+140h+var_118], rax
0x180015a6a  lea     rax, [rbp+arg_10]
0x180015a6e  mov     [rsp+140h+var_120], rax
0x180015a73  mov     [rbp+arg_10], 0
0x180015a7b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180015a80  mov     rcx, rbx
0x180015a83  add     rsp, 130h
0x180015a8a  pop     rdi
0x180015a8b  pop     rbx
0x180015a8c  pop     rbp
0x180015a8d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
