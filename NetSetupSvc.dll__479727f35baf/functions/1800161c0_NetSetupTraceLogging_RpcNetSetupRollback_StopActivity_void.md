# NetSetupTraceLogging::RpcNetSetupRollback::StopActivity(void)

- ea: `0x1800161c0`
- end: `0x180016412`
- name: `?StopActivity@RpcNetSetupRollback@NetSetupTraceLogging@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(NetSetupTraceLogging::RpcNetSetupRollback *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001420`
- `0x180001734`
- `0x180001b50`
- `0x180013aa4`
- `0x180014090`
- `0x1800161c0`
- `0x1800170d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800163b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800163b3`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::RpcNetSetupRollback::StopActivity(
        NetSetupTraceLogging::RpcNetSetupRollback *this)
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
        (int)&word_1800410E6,
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
        (int)word_180041092,
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
0x1800161c0  push    rbp
0x1800161c2  push    rbx
0x1800161c3  push    rdi
0x1800161c4  lea     rbp, [rsp+10h]
0x1800161c9  sub     rsp, 130h
0x1800161d0  mov     rdi, [rcx+110h]
0x1800161d7  mov     rbx, rcx
0x1800161da  mov     eax, [rdi+48h]
0x1800161dd  test    eax, eax
0x1800161df  jns     loc_18001638E
0x1800161e5  add     rdi, 50h ; 'P'
0x1800161e9  cmp     eax, [rdi+8]
0x1800161ec  jnz     loc_18001638E
0x1800161f2  test    rdi, rdi
0x1800161f5  jz      loc_18001638E
0x1800161fb  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016200  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180016205  mov     r9, rax
0x180016208  mov     ecx, [rax]
0x18001620a  cmp     ecx, 5
0x18001620d  jbe     loc_180016400
0x180016213  mov     edx, 1
0x180016218  mov     rcx, rax
0x18001621b  call    _tlgKeywordOn
0x180016220  test    al, al
0x180016222  jz      loc_180016400
0x180016228  mov     rax, [rdi+30h]
0x18001622c  lea     rdx, word_1800410E6; int
0x180016233  mov     [rbp+var_70], rax
0x180016237  mov     rcx, r9; int
0x18001623a  mov     eax, [rdi+44h]
0x18001623d  mov     dword ptr [rbp+arg_0], eax
0x180016240  mov     eax, [rdi+10h]
0x180016243  mov     dword ptr [rbp+arg_8], eax
0x180016246  mov     rax, [rdi+78h]
0x18001624a  mov     [rbp+var_68], rax
0x18001624e  mov     rax, [rdi+70h]
0x180016252  mov     [rbp+var_60], rax
0x180016256  mov     eax, [rdi+68h]
0x180016259  mov     r8, [rbx+110h]
0x180016260  mov     dword ptr [rbp+arg_10], eax
0x180016263  add     r8, 8; int
0x180016267  mov     rax, [rdi+60h]
0x18001626b  mov     [rbp+var_58], rax
0x18001626f  mov     rax, [rdi+58h]
0x180016273  mov     [rbp+var_50], rax
0x180016277  mov     eax, [rdi+50h]
0x18001627a  mov     dword ptr [rbp+arg_18], eax
0x18001627d  mov     rax, [rdi+48h]
0x180016281  mov     [rbp+var_48], rax
0x180016285  mov     eax, [rdi+20h]
0x180016288  mov     dword ptr [rbp+var_80], eax
0x18001628b  mov     rax, [rdi+18h]
0x18001628f  mov     [rbp+var_40], rax
0x180016293  mov     eax, [rdi]
0x180016295  mov     dword ptr [rbp+var_80+4], eax
0x180016298  mov     rax, [rdi+80h]
0x18001629f  mov     [rbp+var_38], rax
0x1800162a3  mov     eax, [rdi+40h]
0x1800162a6  mov     dword ptr [rbp+var_78], eax
0x1800162a9  mov     rax, [rdi+38h]
0x1800162ad  mov     [rbp+var_30], rax
0x1800162b1  mov     eax, [rdi+8]
0x1800162b4  mov     dword ptr [rbp+var_78+4], eax
0x1800162b7  lea     rax, [rbp+var_70]
0x1800162bb  mov     [rsp+140h+var_90], rax; __int64
0x1800162c3  lea     rax, [rbp+arg_0]
0x1800162c7  mov     [rsp+140h+var_98], rax; __int64
0x1800162cf  lea     rax, [rbp+arg_8]
0x1800162d3  mov     [rsp+140h+var_A0], rax; __int64
0x1800162db  lea     rax, [rbp+var_68]
0x1800162df  mov     [rsp+140h+var_A8], rax; __int64
0x1800162e7  lea     rax, [rbp+var_60]
0x1800162eb  mov     [rsp+140h+var_B0], rax; __int64
0x1800162f3  lea     rax, [rbp+arg_10]
0x1800162f7  mov     [rsp+140h+var_B8], rax; __int64
0x1800162ff  lea     rax, [rbp+var_58]
0x180016303  mov     [rsp+140h+var_C0], rax; __int64
0x18001630b  lea     rax, [rbp+var_50]
0x18001630f  mov     [rsp+140h+var_C8], rax; __int64
0x180016314  lea     rax, [rbp+arg_18]
0x180016318  mov     [rsp+140h+var_D0], rax; __int64
0x18001631d  lea     rax, [rbp+var_48]
0x180016321  mov     [rsp+140h+var_D8], rax; __int64
0x180016326  lea     rax, [rbp+var_80]
0x18001632a  mov     [rsp+140h+var_E0], rax; __int64
0x18001632f  lea     rax, [rbp+var_40]
0x180016333  mov     [rsp+140h+var_E8], rax; __int64
0x180016338  lea     rax, [rbp+var_80+4]
0x18001633c  mov     [rsp+140h+var_F0], rax; __int64
0x180016341  lea     rax, [rbp+var_38]
0x180016345  mov     [rsp+140h+var_F8], rax; __int64
0x18001634a  lea     rax, [rbp+var_78]
0x18001634e  mov     [rsp+140h+var_100], rax; __int64
0x180016353  lea     rax, [rbp+var_30]
0x180016357  mov     [rsp+140h+var_108], rax; __int64
0x18001635c  lea     rax, [rbp+var_78+4]
0x180016360  mov     [rsp+140h+var_110], rax; __int64
0x180016365  lea     rax, [rbp+var_28]
0x180016369  mov     [rsp+140h+var_118], rax; __int64
0x18001636e  lea     rax, [rbp+var_20]
0x180016372  mov     [rsp+140h+var_120], rax; __int64
0x180016377  mov     [rbp+var_28], 1000000h
0x18001637f  mov     [rbp+var_20], 0
0x180016387  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001638c  jmp     short loc_180016400
0x18001638e  call    ?zInternalStop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016393  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180016398  mov     rdi, rax
0x18001639b  mov     ecx, [rax]
0x18001639d  cmp     ecx, 5
0x1800163a0  jbe     short loc_180016400
0x1800163a2  mov     edx, 1
0x1800163a7  mov     rcx, rax
0x1800163aa  call    _tlgKeywordOn
0x1800163af  test    al, al
0x1800163b1  jz      short loc_180016400
0x1800163b3  call    cs:__imp_GetCurrentThreadId
0x1800163b9  mov     r8, [rbx+110h]
0x1800163c0  lea     rdx, word_180041092
0x1800163c7  mov     dword ptr [rbp+arg_0], eax
0x1800163ca  mov     rcx, rdi
0x1800163cd  mov     eax, [r8+48h]
0x1800163d1  add     r8, 8
0x1800163d5  mov     dword ptr [rbp+arg_8], eax
0x1800163d8  lea     rax, [rbp+arg_0]
0x1800163dc  mov     [rsp+140h+var_110], rax
0x1800163e1  lea     rax, [rbp+arg_8]
0x1800163e5  mov     [rsp+140h+var_118], rax
0x1800163ea  lea     rax, [rbp+arg_10]
0x1800163ee  mov     [rsp+140h+var_120], rax
0x1800163f3  mov     [rbp+arg_10], 0
0x1800163fb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016400  mov     rcx, rbx
0x180016403  add     rsp, 130h
0x18001640a  pop     rdi
0x18001640b  pop     rbx
0x18001640c  pop     rbp
0x18001640d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
