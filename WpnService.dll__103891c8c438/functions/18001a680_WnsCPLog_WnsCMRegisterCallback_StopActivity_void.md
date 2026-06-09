# WnsCPLog::WnsCMRegisterCallback::StopActivity(void)

- ea: `0x18001a680`
- end: `0x18001a8af`
- name: `?StopActivity@WnsCMRegisterCallback@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMRegisterCallback *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18001a680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a84d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a84d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRegisterCallback::StopActivity(WnsCPLog::WnsCMRegisterCallback *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // [rsp+C0h] [rbp-80h] BYREF
  int v12; // [rsp+C4h] [rbp-7Ch] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v15; // [rsp+D0h] [rbp-70h] BYREF
  int *v16; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+E0h] [rbp-60h] BYREF
  int *v18; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v20; // [rsp+F8h] [rbp-48h] BYREF
  int *v21; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v23; // [rsp+110h] [rbp-30h] BYREF
  __int64 v24; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v25[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v26; // [rsp+150h] [rbp+10h] BYREF
  int v27; // [rsp+158h] [rbp+18h] BYREF
  __int64 v28; // [rsp+160h] [rbp+20h] BYREF
  int v29; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v28) = v4[26];
      v18 = (int *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v11 = v4[8];
      v21 = (int *)*((_QWORD *)v4 + 3);
      v12 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v15 = v6;
      v26 = v4[17];
      v27 = v4[4];
      v16 = (int *)*((_QWORD *)v4 + 15);
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (unsigned __int8 *)word_18003FCD2,
        (const GUID *)(v7 + 8),
        (__int64)v5,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v29,
        &v19,
        &v18,
        (__int64)&v28,
        &v17,
        &v16,
        (__int64)&v27,
        (__int64)&v26,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v10 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)&dword_18003FC7C,
        (const GUID *)(v10 + 8),
        0,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001a680  push    rbp
0x18001a682  push    rbx
0x18001a683  push    rdi
0x18001a684  lea     rbp, [rsp+10h]
0x18001a689  sub     rsp, 130h
0x18001a690  mov     rdi, [rcx+110h]
0x18001a697  mov     rbx, rcx
0x18001a69a  mov     eax, [rdi+48h]
0x18001a69d  test    eax, eax
0x18001a69f  jns     loc_18001A839
0x18001a6a5  add     rdi, 50h ; 'P'
0x18001a6a9  cmp     eax, [rdi+8]
0x18001a6ac  jnz     loc_18001A839
0x18001a6b2  test    rdi, rdi
0x18001a6b5  jz      loc_18001A839
0x18001a6bb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a6c0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001a6c5  mov     r9, rax
0x18001a6c8  mov     ecx, [rax]
0x18001a6ca  cmp     ecx, 5
0x18001a6cd  jbe     loc_18001A89D
0x18001a6d3  mov     rax, [rdi+70h]
0x18001a6d7  lea     rdx, word_18003FCD2
0x18001a6de  mov     rcx, [rdi+30h]
0x18001a6e2  mov     [rbp+var_60], rax
0x18001a6e6  mov     eax, [rdi+68h]
0x18001a6e9  mov     r8, [rbx+110h]
0x18001a6f0  mov     dword ptr [rbp+arg_10], eax
0x18001a6f3  add     r8, 8
0x18001a6f7  mov     rax, [rdi+60h]
0x18001a6fb  mov     [rbp+var_58], rax
0x18001a6ff  mov     rax, [rdi+58h]
0x18001a703  mov     [rbp+var_50], rax
0x18001a707  mov     eax, [rdi+50h]
0x18001a70a  mov     [rbp+arg_18], eax
0x18001a70d  mov     rax, [rdi+48h]
0x18001a711  mov     [rbp+var_48], rax
0x18001a715  mov     eax, [rdi+20h]
0x18001a718  mov     [rbp+var_80], eax
0x18001a71b  mov     rax, [rdi+18h]
0x18001a71f  mov     [rbp+var_40], rax
0x18001a723  mov     eax, [rdi]
0x18001a725  mov     [rbp+var_7C], eax
0x18001a728  mov     rax, [rdi+80h]
0x18001a72f  mov     [rbp+var_38], rax
0x18001a733  mov     eax, [rdi+40h]
0x18001a736  mov     [rbp+var_78], eax
0x18001a739  mov     rax, [rdi+38h]
0x18001a73d  mov     [rbp+var_30], rax
0x18001a741  mov     eax, [rdi+8]
0x18001a744  mov     [rbp+var_74], eax
0x18001a747  lea     rax, [rbp+var_70]
0x18001a74b  mov     [rsp+140h+var_90], rax
0x18001a753  lea     rax, [rbp+arg_0]
0x18001a757  mov     [rsp+140h+var_98], rax
0x18001a75f  lea     rax, [rbp+arg_8]
0x18001a763  mov     [rsp+140h+var_A0], rax
0x18001a76b  lea     rax, [rbp+var_68]
0x18001a76f  mov     [rsp+140h+var_A8], rax
0x18001a777  lea     rax, [rbp+var_60]
0x18001a77b  mov     [rsp+140h+var_B0], rax
0x18001a783  lea     rax, [rbp+arg_10]
0x18001a787  mov     [rsp+140h+var_B8], rax
0x18001a78f  lea     rax, [rbp+var_58]
0x18001a793  mov     [rsp+140h+var_C0], rax
0x18001a79b  lea     rax, [rbp+var_50]
0x18001a79f  mov     [rsp+140h+var_C8], rax
0x18001a7a4  lea     rax, [rbp+arg_18]
0x18001a7a8  mov     [rsp+140h+var_D0], rax
0x18001a7ad  lea     rax, [rbp+var_48]
0x18001a7b1  mov     [rsp+140h+var_D8], rax
0x18001a7b6  lea     rax, [rbp+var_80]
0x18001a7ba  mov     [rsp+140h+var_E0], rax
0x18001a7bf  lea     rax, [rbp+var_40]
0x18001a7c3  mov     [rsp+140h+var_E8], rax
0x18001a7c8  lea     rax, [rbp+var_7C]
0x18001a7cc  mov     [rsp+140h+var_F0], rax
0x18001a7d1  lea     rax, [rbp+var_38]
0x18001a7d5  mov     [rsp+140h+var_F8], rax
0x18001a7da  lea     rax, [rbp+var_78]
0x18001a7de  mov     [rsp+140h+var_100], rax
0x18001a7e3  lea     rax, [rbp+var_30]
0x18001a7e7  mov     [rsp+140h+var_108], rax
0x18001a7ec  lea     rax, [rbp+var_74]
0x18001a7f0  mov     [rbp+var_70], rcx
0x18001a7f4  mov     ecx, [rdi+44h]
0x18001a7f7  mov     [rsp+140h+var_110], rax
0x18001a7fc  lea     rax, [rbp+var_28]
0x18001a800  mov     [rbp+arg_0], ecx
0x18001a803  mov     ecx, [rdi+10h]
0x18001a806  mov     [rbp+arg_8], ecx
0x18001a809  mov     rcx, [rdi+78h]
0x18001a80d  mov     [rsp+140h+var_118], rax
0x18001a812  lea     rax, [rbp+var_20]
0x18001a816  mov     [rbp+var_68], rcx
0x18001a81a  mov     rcx, r9
0x18001a81d  mov     [rsp+140h+var_120], rax
0x18001a822  mov     [rbp+var_28], 1000000h
0x18001a82a  mov     [rbp+var_20], 0
0x18001a832  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a837  jmp     short loc_18001A89D
0x18001a839  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a83e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001a843  mov     rdi, rax
0x18001a846  mov     ecx, [rax]
0x18001a848  cmp     ecx, 5
0x18001a84b  jbe     short loc_18001A89D
0x18001a84d  call    cs:__imp_GetCurrentThreadId
0x18001a853  mov     r8, [rbx+110h]
0x18001a85a  lea     rdx, dword_18003FC7C
0x18001a861  mov     [rbp+arg_0], eax
0x18001a864  xor     r9d, r9d
0x18001a867  lea     rax, [rbp+arg_0]
0x18001a86b  mov     [rsp+140h+var_110], rax
0x18001a870  lea     rax, [rbp+arg_8]
0x18001a874  mov     ecx, [r8+48h]
0x18001a878  add     r8, 8
0x18001a87c  mov     [rsp+140h+var_118], rax
0x18001a881  lea     rax, [rbp+arg_10]
0x18001a885  mov     [rbp+arg_8], ecx
0x18001a888  mov     rcx, rdi
0x18001a88b  mov     [rsp+140h+var_120], rax
0x18001a890  mov     [rbp+arg_10], 0
0x18001a898  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a89d  mov     rcx, rbx
0x18001a8a0  add     rsp, 130h
0x18001a8a7  pop     rdi
0x18001a8a8  pop     rbx
0x18001a8a9  pop     rbp
0x18001a8aa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
