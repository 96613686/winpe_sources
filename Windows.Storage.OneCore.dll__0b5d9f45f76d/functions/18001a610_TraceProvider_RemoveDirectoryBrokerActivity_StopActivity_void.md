# TraceProvider::RemoveDirectoryBrokerActivity::StopActivity(void)

- ea: `0x18001a610`
- end: `0x18001a83c`
- name: `?StopActivity@RemoveDirectoryBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::RemoveDirectoryBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x18001a610`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a7dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a7dd`

## pseudocode

```c
void __fastcall TraceProvider::RemoveDirectoryBrokerActivity::StopActivity(
        TraceProvider::RemoveDirectoryBrokerActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = TraceProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v7,
        (__int64)&dword_18002A734,
        v9 + 8,
        (__int64)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&v29,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = TraceProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&dword_18002A88C,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this, v5, v6, v7);
}

```

## disassembly

```asm
0x18001a610  push    rbp
0x18001a612  push    rbx
0x18001a613  push    rdi
0x18001a614  lea     rbp, [rsp+10h]
0x18001a619  sub     rsp, 130h
0x18001a620  mov     rdi, [rcx+110h]
0x18001a627  mov     rbx, rcx
0x18001a62a  mov     eax, [rdi+48h]
0x18001a62d  test    eax, eax
0x18001a62f  jns     loc_18001A7C9
0x18001a635  add     rdi, 50h ; 'P'
0x18001a639  cmp     eax, [rdi+8]
0x18001a63c  jnz     loc_18001A7C9
0x18001a642  test    rdi, rdi
0x18001a645  jz      loc_18001A7C9
0x18001a64b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a650  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a655  mov     r9, rax
0x18001a658  mov     ecx, [rax]
0x18001a65a  cmp     ecx, 5
0x18001a65d  jbe     loc_18001A82A
0x18001a663  mov     rax, [rdi+70h]
0x18001a667  lea     rdx, dword_18002A734
0x18001a66e  mov     rcx, [rdi+30h]
0x18001a672  mov     [rbp+var_60], rax
0x18001a676  mov     eax, [rdi+68h]
0x18001a679  mov     r8, [rbx+110h]
0x18001a680  mov     dword ptr [rbp+arg_10], eax
0x18001a683  add     r8, 8
0x18001a687  mov     rax, [rdi+60h]
0x18001a68b  mov     [rbp+var_58], rax
0x18001a68f  mov     rax, [rdi+58h]
0x18001a693  mov     [rbp+var_50], rax
0x18001a697  mov     eax, [rdi+50h]
0x18001a69a  mov     [rbp+arg_18], eax
0x18001a69d  mov     rax, [rdi+48h]
0x18001a6a1  mov     [rbp+var_48], rax
0x18001a6a5  mov     eax, [rdi+20h]
0x18001a6a8  mov     [rbp+var_80], eax
0x18001a6ab  mov     rax, [rdi+18h]
0x18001a6af  mov     [rbp+var_40], rax
0x18001a6b3  mov     eax, [rdi]
0x18001a6b5  mov     [rbp+var_7C], eax
0x18001a6b8  mov     rax, [rdi+80h]
0x18001a6bf  mov     [rbp+var_38], rax
0x18001a6c3  mov     eax, [rdi+40h]
0x18001a6c6  mov     [rbp+var_78], eax
0x18001a6c9  mov     rax, [rdi+38h]
0x18001a6cd  mov     [rbp+var_30], rax
0x18001a6d1  mov     eax, [rdi+8]
0x18001a6d4  mov     [rbp+var_74], eax
0x18001a6d7  lea     rax, [rbp+var_70]
0x18001a6db  mov     [rsp+140h+var_90], rax
0x18001a6e3  lea     rax, [rbp+arg_0]
0x18001a6e7  mov     [rsp+140h+var_98], rax
0x18001a6ef  lea     rax, [rbp+arg_8]
0x18001a6f3  mov     [rsp+140h+var_A0], rax
0x18001a6fb  lea     rax, [rbp+var_68]
0x18001a6ff  mov     [rsp+140h+var_A8], rax
0x18001a707  lea     rax, [rbp+var_60]
0x18001a70b  mov     [rsp+140h+var_B0], rax
0x18001a713  lea     rax, [rbp+arg_10]
0x18001a717  mov     [rsp+140h+var_B8], rax
0x18001a71f  lea     rax, [rbp+var_58]
0x18001a723  mov     [rsp+140h+var_C0], rax
0x18001a72b  lea     rax, [rbp+var_50]
0x18001a72f  mov     [rsp+140h+var_C8], rax
0x18001a734  lea     rax, [rbp+arg_18]
0x18001a738  mov     [rsp+140h+var_D0], rax
0x18001a73d  lea     rax, [rbp+var_48]
0x18001a741  mov     [rsp+140h+var_D8], rax
0x18001a746  lea     rax, [rbp+var_80]
0x18001a74a  mov     [rsp+140h+var_E0], rax
0x18001a74f  lea     rax, [rbp+var_40]
0x18001a753  mov     [rsp+140h+var_E8], rax
0x18001a758  lea     rax, [rbp+var_7C]
0x18001a75c  mov     [rsp+140h+var_F0], rax
0x18001a761  lea     rax, [rbp+var_38]
0x18001a765  mov     [rsp+140h+var_F8], rax
0x18001a76a  lea     rax, [rbp+var_78]
0x18001a76e  mov     [rsp+140h+var_100], rax
0x18001a773  lea     rax, [rbp+var_30]
0x18001a777  mov     [rsp+140h+var_108], rax
0x18001a77c  lea     rax, [rbp+var_74]
0x18001a780  mov     [rbp+var_70], rcx
0x18001a784  mov     ecx, [rdi+44h]
0x18001a787  mov     [rsp+140h+var_110], rax
0x18001a78c  lea     rax, [rbp+var_28]
0x18001a790  mov     [rbp+arg_0], ecx
0x18001a793  mov     ecx, [rdi+10h]
0x18001a796  mov     [rbp+arg_8], ecx
0x18001a799  mov     rcx, [rdi+78h]
0x18001a79d  mov     [rsp+140h+var_118], rax
0x18001a7a2  lea     rax, [rbp+var_20]
0x18001a7a6  mov     [rbp+var_68], rcx
0x18001a7aa  mov     rcx, r9
0x18001a7ad  mov     [rsp+140h+var_120], rax
0x18001a7b2  mov     [rbp+var_28], 1000000h
0x18001a7ba  mov     [rbp+var_20], 0
0x18001a7c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a7c7  jmp     short loc_18001A82A
0x18001a7c9  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a7ce  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a7d3  mov     rdi, rax
0x18001a7d6  mov     ecx, [rax]
0x18001a7d8  cmp     ecx, 5
0x18001a7db  jbe     short loc_18001A82A
0x18001a7dd  call    cs:__imp_GetCurrentThreadId
0x18001a7e3  mov     r8, [rbx+110h]
0x18001a7ea  lea     rdx, dword_18002A88C
0x18001a7f1  mov     [rbp+arg_0], eax
0x18001a7f4  lea     rax, [rbp+arg_0]
0x18001a7f8  mov     [rsp+140h+var_110], rax
0x18001a7fd  lea     rax, [rbp+arg_8]
0x18001a801  mov     [rsp+140h+var_118], rax
0x18001a806  lea     rax, [rbp+arg_10]
0x18001a80a  mov     ecx, [r8+48h]
0x18001a80e  add     r8, 8
0x18001a812  mov     [rbp+arg_8], ecx
0x18001a815  mov     rcx, rdi
0x18001a818  mov     [rsp+140h+var_120], rax
0x18001a81d  mov     [rbp+arg_10], 0
0x18001a825  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a82a  mov     rcx, rbx
0x18001a82d  add     rsp, 130h
0x18001a834  pop     rdi
0x18001a835  pop     rbx
0x18001a836  pop     rbp
0x18001a837  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
