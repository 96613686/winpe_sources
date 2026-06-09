# NetSetupTraceLogging::ReinitializeTransaction::StopActivity(void)

- ea: `0x180047530`
- end: `0x180047782`
- name: `?StopActivity@ReinitializeTransaction@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::ReinitializeTransaction *__hidden this)`
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
- `0x180047530`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047723`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::ReinitializeTransaction::StopActivity(
        NetSetupTraceLogging::ReinitializeTransaction *this)
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
        (int)&word_1800B2882,
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
        (int)word_1800B282A,
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
0x180047530  push    rbp
0x180047532  push    rbx
0x180047533  push    rdi
0x180047534  lea     rbp, [rsp+10h]
0x180047539  sub     rsp, 130h
0x180047540  mov     rdi, [rcx+110h]
0x180047547  mov     rbx, rcx
0x18004754a  mov     eax, [rdi+48h]
0x18004754d  test    eax, eax
0x18004754f  jns     loc_1800476FE
0x180047555  add     rdi, 50h ; 'P'
0x180047559  cmp     eax, [rdi+8]
0x18004755c  jnz     loc_1800476FE
0x180047562  test    rdi, rdi
0x180047565  jz      loc_1800476FE
0x18004756b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180047570  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180047575  mov     r9, rax
0x180047578  mov     ecx, [rax]
0x18004757a  cmp     ecx, 5
0x18004757d  jbe     loc_180047770
0x180047583  mov     edx, 1
0x180047588  mov     rcx, rax
0x18004758b  call    _tlgKeywordOn
0x180047590  test    al, al
0x180047592  jz      loc_180047770
0x180047598  mov     rax, [rdi+30h]
0x18004759c  lea     rdx, word_1800B2882; int
0x1800475a3  mov     [rbp+var_70], rax
0x1800475a7  mov     rcx, r9; int
0x1800475aa  mov     eax, [rdi+44h]
0x1800475ad  mov     dword ptr [rbp+arg_0], eax
0x1800475b0  mov     eax, [rdi+10h]
0x1800475b3  mov     dword ptr [rbp+arg_8], eax
0x1800475b6  mov     rax, [rdi+78h]
0x1800475ba  mov     [rbp+var_68], rax
0x1800475be  mov     rax, [rdi+70h]
0x1800475c2  mov     [rbp+var_60], rax
0x1800475c6  mov     eax, [rdi+68h]
0x1800475c9  mov     r8, [rbx+110h]
0x1800475d0  mov     dword ptr [rbp+arg_10], eax
0x1800475d3  add     r8, 8; int
0x1800475d7  mov     rax, [rdi+60h]
0x1800475db  mov     [rbp+var_58], rax
0x1800475df  mov     rax, [rdi+58h]
0x1800475e3  mov     [rbp+var_50], rax
0x1800475e7  mov     eax, [rdi+50h]
0x1800475ea  mov     dword ptr [rbp+arg_18], eax
0x1800475ed  mov     rax, [rdi+48h]
0x1800475f1  mov     [rbp+var_48], rax
0x1800475f5  mov     eax, [rdi+20h]
0x1800475f8  mov     dword ptr [rbp+var_80], eax
0x1800475fb  mov     rax, [rdi+18h]
0x1800475ff  mov     [rbp+var_40], rax
0x180047603  mov     eax, [rdi]
0x180047605  mov     dword ptr [rbp+var_80+4], eax
0x180047608  mov     rax, [rdi+80h]
0x18004760f  mov     [rbp+var_38], rax
0x180047613  mov     eax, [rdi+40h]
0x180047616  mov     dword ptr [rbp+var_78], eax
0x180047619  mov     rax, [rdi+38h]
0x18004761d  mov     [rbp+var_30], rax
0x180047621  mov     eax, [rdi+8]
0x180047624  mov     dword ptr [rbp+var_78+4], eax
0x180047627  lea     rax, [rbp+var_70]
0x18004762b  mov     [rsp+140h+var_90], rax; __int64
0x180047633  lea     rax, [rbp+arg_0]
0x180047637  mov     [rsp+140h+var_98], rax; __int64
0x18004763f  lea     rax, [rbp+arg_8]
0x180047643  mov     [rsp+140h+var_A0], rax; __int64
0x18004764b  lea     rax, [rbp+var_68]
0x18004764f  mov     [rsp+140h+var_A8], rax; __int64
0x180047657  lea     rax, [rbp+var_60]
0x18004765b  mov     [rsp+140h+var_B0], rax; __int64
0x180047663  lea     rax, [rbp+arg_10]
0x180047667  mov     [rsp+140h+var_B8], rax; __int64
0x18004766f  lea     rax, [rbp+var_58]
0x180047673  mov     [rsp+140h+var_C0], rax; __int64
0x18004767b  lea     rax, [rbp+var_50]
0x18004767f  mov     [rsp+140h+var_C8], rax; __int64
0x180047684  lea     rax, [rbp+arg_18]
0x180047688  mov     [rsp+140h+var_D0], rax; __int64
0x18004768d  lea     rax, [rbp+var_48]
0x180047691  mov     [rsp+140h+var_D8], rax; __int64
0x180047696  lea     rax, [rbp+var_80]
0x18004769a  mov     [rsp+140h+var_E0], rax; __int64
0x18004769f  lea     rax, [rbp+var_40]
0x1800476a3  mov     [rsp+140h+var_E8], rax; __int64
0x1800476a8  lea     rax, [rbp+var_80+4]
0x1800476ac  mov     [rsp+140h+var_F0], rax; __int64
0x1800476b1  lea     rax, [rbp+var_38]
0x1800476b5  mov     [rsp+140h+var_F8], rax; __int64
0x1800476ba  lea     rax, [rbp+var_78]
0x1800476be  mov     [rsp+140h+var_100], rax; __int64
0x1800476c3  lea     rax, [rbp+var_30]
0x1800476c7  mov     [rsp+140h+var_108], rax; __int64
0x1800476cc  lea     rax, [rbp+var_78+4]
0x1800476d0  mov     [rsp+140h+var_110], rax; __int64
0x1800476d5  lea     rax, [rbp+var_28]
0x1800476d9  mov     [rsp+140h+var_118], rax; __int64
0x1800476de  lea     rax, [rbp+var_20]
0x1800476e2  mov     [rsp+140h+var_120], rax; __int64
0x1800476e7  mov     [rbp+var_28], 1000000h
0x1800476ef  mov     [rbp+var_20], 0
0x1800476f7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800476fc  jmp     short loc_180047770
0x1800476fe  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180047703  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180047708  mov     rdi, rax
0x18004770b  mov     ecx, [rax]
0x18004770d  cmp     ecx, 5
0x180047710  jbe     short loc_180047770
0x180047712  mov     edx, 1
0x180047717  mov     rcx, rax
0x18004771a  call    _tlgKeywordOn
0x18004771f  test    al, al
0x180047721  jz      short loc_180047770
0x180047723  call    cs:__imp_GetCurrentThreadId
0x180047729  mov     r8, [rbx+110h]
0x180047730  lea     rdx, word_1800B282A
0x180047737  mov     dword ptr [rbp+arg_0], eax
0x18004773a  mov     rcx, rdi
0x18004773d  mov     eax, [r8+48h]
0x180047741  add     r8, 8
0x180047745  mov     dword ptr [rbp+arg_8], eax
0x180047748  lea     rax, [rbp+arg_0]
0x18004774c  mov     [rsp+140h+var_110], rax
0x180047751  lea     rax, [rbp+arg_8]
0x180047755  mov     [rsp+140h+var_118], rax
0x18004775a  lea     rax, [rbp+arg_10]
0x18004775e  mov     [rsp+140h+var_120], rax
0x180047763  mov     [rbp+arg_10], 0
0x18004776b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180047770  mov     rcx, rbx
0x180047773  add     rsp, 130h
0x18004777a  pop     rdi
0x18004777b  pop     rbx
0x18004777c  pop     rbp
0x18004777d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
