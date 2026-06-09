# NetSetupTraceLogging::RpcNetSetupInitialize::StopActivity(void)

- ea: `0x180015f60`
- end: `0x1800161b2`
- name: `?StopActivity@RpcNetSetupInitialize@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupInitialize *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001420`
- `0x180001734`
- `0x180001b50`
- `0x180013aa4`
- `0x180014090`
- `0x180015f60`
- `0x1800170d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016153`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupInitialize::StopActivity(
        NetSetupTraceLogging::RpcNetSetupInitialize *this)
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
        (int)&byte_180041503,
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
        (int)byte_1800414AD,
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
0x180015f60  push    rbp
0x180015f62  push    rbx
0x180015f63  push    rdi
0x180015f64  lea     rbp, [rsp+10h]
0x180015f69  sub     rsp, 130h
0x180015f70  mov     rdi, [rcx+110h]
0x180015f77  mov     rbx, rcx
0x180015f7a  mov     eax, [rdi+48h]
0x180015f7d  test    eax, eax
0x180015f7f  jns     loc_18001612E
0x180015f85  add     rdi, 50h ; 'P'
0x180015f89  cmp     eax, [rdi+8]
0x180015f8c  jnz     loc_18001612E
0x180015f92  test    rdi, rdi
0x180015f95  jz      loc_18001612E
0x180015f9b  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015fa0  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180015fa5  mov     r9, rax
0x180015fa8  mov     ecx, [rax]
0x180015faa  cmp     ecx, 5
0x180015fad  jbe     loc_1800161A0
0x180015fb3  mov     edx, 1
0x180015fb8  mov     rcx, rax
0x180015fbb  call    _tlgKeywordOn
0x180015fc0  test    al, al
0x180015fc2  jz      loc_1800161A0
0x180015fc8  mov     rax, [rdi+30h]
0x180015fcc  lea     rdx, byte_180041503; int
0x180015fd3  mov     [rbp+var_70], rax
0x180015fd7  mov     rcx, r9; int
0x180015fda  mov     eax, [rdi+44h]
0x180015fdd  mov     dword ptr [rbp+arg_0], eax
0x180015fe0  mov     eax, [rdi+10h]
0x180015fe3  mov     dword ptr [rbp+arg_8], eax
0x180015fe6  mov     rax, [rdi+78h]
0x180015fea  mov     [rbp+var_68], rax
0x180015fee  mov     rax, [rdi+70h]
0x180015ff2  mov     [rbp+var_60], rax
0x180015ff6  mov     eax, [rdi+68h]
0x180015ff9  mov     r8, [rbx+110h]
0x180016000  mov     dword ptr [rbp+arg_10], eax
0x180016003  add     r8, 8; int
0x180016007  mov     rax, [rdi+60h]
0x18001600b  mov     [rbp+var_58], rax
0x18001600f  mov     rax, [rdi+58h]
0x180016013  mov     [rbp+var_50], rax
0x180016017  mov     eax, [rdi+50h]
0x18001601a  mov     dword ptr [rbp+arg_18], eax
0x18001601d  mov     rax, [rdi+48h]
0x180016021  mov     [rbp+var_48], rax
0x180016025  mov     eax, [rdi+20h]
0x180016028  mov     dword ptr [rbp+var_80], eax
0x18001602b  mov     rax, [rdi+18h]
0x18001602f  mov     [rbp+var_40], rax
0x180016033  mov     eax, [rdi]
0x180016035  mov     dword ptr [rbp+var_80+4], eax
0x180016038  mov     rax, [rdi+80h]
0x18001603f  mov     [rbp+var_38], rax
0x180016043  mov     eax, [rdi+40h]
0x180016046  mov     dword ptr [rbp+var_78], eax
0x180016049  mov     rax, [rdi+38h]
0x18001604d  mov     [rbp+var_30], rax
0x180016051  mov     eax, [rdi+8]
0x180016054  mov     dword ptr [rbp+var_78+4], eax
0x180016057  lea     rax, [rbp+var_70]
0x18001605b  mov     [rsp+140h+var_90], rax; __int64
0x180016063  lea     rax, [rbp+arg_0]
0x180016067  mov     [rsp+140h+var_98], rax; __int64
0x18001606f  lea     rax, [rbp+arg_8]
0x180016073  mov     [rsp+140h+var_A0], rax; __int64
0x18001607b  lea     rax, [rbp+var_68]
0x18001607f  mov     [rsp+140h+var_A8], rax; __int64
0x180016087  lea     rax, [rbp+var_60]
0x18001608b  mov     [rsp+140h+var_B0], rax; __int64
0x180016093  lea     rax, [rbp+arg_10]
0x180016097  mov     [rsp+140h+var_B8], rax; __int64
0x18001609f  lea     rax, [rbp+var_58]
0x1800160a3  mov     [rsp+140h+var_C0], rax; __int64
0x1800160ab  lea     rax, [rbp+var_50]
0x1800160af  mov     [rsp+140h+var_C8], rax; __int64
0x1800160b4  lea     rax, [rbp+arg_18]
0x1800160b8  mov     [rsp+140h+var_D0], rax; __int64
0x1800160bd  lea     rax, [rbp+var_48]
0x1800160c1  mov     [rsp+140h+var_D8], rax; __int64
0x1800160c6  lea     rax, [rbp+var_80]
0x1800160ca  mov     [rsp+140h+var_E0], rax; __int64
0x1800160cf  lea     rax, [rbp+var_40]
0x1800160d3  mov     [rsp+140h+var_E8], rax; __int64
0x1800160d8  lea     rax, [rbp+var_80+4]
0x1800160dc  mov     [rsp+140h+var_F0], rax; __int64
0x1800160e1  lea     rax, [rbp+var_38]
0x1800160e5  mov     [rsp+140h+var_F8], rax; __int64
0x1800160ea  lea     rax, [rbp+var_78]
0x1800160ee  mov     [rsp+140h+var_100], rax; __int64
0x1800160f3  lea     rax, [rbp+var_30]
0x1800160f7  mov     [rsp+140h+var_108], rax; __int64
0x1800160fc  lea     rax, [rbp+var_78+4]
0x180016100  mov     [rsp+140h+var_110], rax; __int64
0x180016105  lea     rax, [rbp+var_28]
0x180016109  mov     [rsp+140h+var_118], rax; __int64
0x18001610e  lea     rax, [rbp+var_20]
0x180016112  mov     [rsp+140h+var_120], rax; __int64
0x180016117  mov     [rbp+var_28], 1000000h
0x18001611f  mov     [rbp+var_20], 0
0x180016127  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001612c  jmp     short loc_1800161A0
0x18001612e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016133  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180016138  mov     rdi, rax
0x18001613b  mov     ecx, [rax]
0x18001613d  cmp     ecx, 5
0x180016140  jbe     short loc_1800161A0
0x180016142  mov     edx, 1
0x180016147  mov     rcx, rax
0x18001614a  call    _tlgKeywordOn
0x18001614f  test    al, al
0x180016151  jz      short loc_1800161A0
0x180016153  call    cs:__imp_GetCurrentThreadId
0x180016159  mov     r8, [rbx+110h]
0x180016160  lea     rdx, byte_1800414AD
0x180016167  mov     dword ptr [rbp+arg_0], eax
0x18001616a  mov     rcx, rdi
0x18001616d  mov     eax, [r8+48h]
0x180016171  add     r8, 8
0x180016175  mov     dword ptr [rbp+arg_8], eax
0x180016178  lea     rax, [rbp+arg_0]
0x18001617c  mov     [rsp+140h+var_110], rax
0x180016181  lea     rax, [rbp+arg_8]
0x180016185  mov     [rsp+140h+var_118], rax
0x18001618a  lea     rax, [rbp+arg_10]
0x18001618e  mov     [rsp+140h+var_120], rax
0x180016193  mov     [rbp+arg_10], 0
0x18001619b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800161a0  mov     rcx, rbx
0x1800161a3  add     rsp, 130h
0x1800161aa  pop     rdi
0x1800161ab  pop     rbx
0x1800161ac  pop     rbp
0x1800161ad  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
