# Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateWithTimeSpanActivity::StopActivity(void)

- ea: `0x18000f570`
- end: `0x18000f794`
- name: `?StopActivity@EnterPowerStateWithTimeSpanActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateWithTimeSpanActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010f8`
- `0x180001730`
- `0x180001ebc`
- `0x18000df18`
- `0x18000e62c`
- `0x18000f570`
- `0x18000fe68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f735`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f735`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateWithTimeSpanActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateWithTimeSpanActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Windows::System::SysAdminTraceLoggingProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&byte_180039277,
        v10 + 8,
        v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = Windows::System::SysAdminTraceLoggingProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_180039213,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18000f570  push    rbp
0x18000f572  push    rbx
0x18000f573  push    rdi
0x18000f574  lea     rbp, [rsp-47h]
0x18000f579  sub     rsp, 100h
0x18000f580  mov     rdi, [rcx+110h]
0x18000f587  mov     rbx, rcx
0x18000f58a  mov     eax, [rdi+48h]
0x18000f58d  test    eax, eax
0x18000f58f  jns     loc_18000F70B
0x18000f595  add     rdi, 50h ; 'P'
0x18000f599  cmp     eax, [rdi+8]
0x18000f59c  jnz     loc_18000F70B
0x18000f5a2  test    rdi, rdi
0x18000f5a5  jz      loc_18000F70B
0x18000f5ab  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f5b0  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f5b5  mov     r9, rax
0x18000f5b8  mov     ecx, [rax]
0x18000f5ba  cmp     ecx, 5
0x18000f5bd  jbe     loc_18000F782
0x18000f5c3  mov     rdx, 200000000000h
0x18000f5cd  mov     rcx, rax
0x18000f5d0  call    _tlgKeywordOn
0x18000f5d5  test    al, al
0x18000f5d7  jz      loc_18000F782
0x18000f5dd  mov     rax, [rdi+70h]
0x18000f5e1  lea     rdx, byte_180039277
0x18000f5e8  mov     rcx, [rdi+78h]
0x18000f5ec  mov     r8, [rbx+110h]
0x18000f5f3  mov     [rbp+57h+var_60], rax
0x18000f5f7  add     r8, 8
0x18000f5fb  mov     eax, [rdi+68h]
0x18000f5fe  mov     [rbp+57h+arg_0], eax
0x18000f601  mov     rax, [rdi+60h]
0x18000f605  mov     [rbp+57h+var_58], rax
0x18000f609  mov     rax, [rdi+58h]
0x18000f60d  mov     [rbp+57h+var_50], rax
0x18000f611  mov     eax, [rdi+50h]
0x18000f614  mov     [rbp+57h+arg_8], eax
0x18000f617  mov     rax, [rdi+48h]
0x18000f61b  mov     [rbp+57h+var_48], rax
0x18000f61f  mov     eax, [rdi+20h]
0x18000f622  mov     dword ptr [rbp+57h+arg_10], eax
0x18000f625  mov     rax, [rdi+18h]
0x18000f629  mov     [rbp+57h+var_40], rax
0x18000f62d  mov     eax, [rdi]
0x18000f62f  mov     [rbp+57h+arg_18], eax
0x18000f632  mov     rax, [rdi+80h]
0x18000f639  mov     [rbp+57h+var_38], rax
0x18000f63d  mov     eax, [rdi+40h]
0x18000f640  mov     [rbp+57h+var_70], eax
0x18000f643  mov     rax, [rdi+38h]
0x18000f647  mov     [rbp+57h+var_30], rax
0x18000f64b  mov     eax, [rdi+8]
0x18000f64e  mov     [rbp+57h+var_6C], eax
0x18000f651  lea     rax, [rbp+57h+var_68]
0x18000f655  mov     [rsp+110h+var_78], rax
0x18000f65d  lea     rax, [rbp+57h+var_60]
0x18000f661  mov     [rsp+110h+var_80], rax
0x18000f669  lea     rax, [rbp+57h+arg_0]
0x18000f66d  mov     [rsp+110h+var_88], rax
0x18000f675  lea     rax, [rbp+57h+var_58]
0x18000f679  mov     [rsp+110h+var_90], rax
0x18000f681  lea     rax, [rbp+57h+var_50]
0x18000f685  mov     [rsp+110h+var_98], rax
0x18000f68a  lea     rax, [rbp+57h+arg_8]
0x18000f68e  mov     [rsp+110h+var_A0], rax
0x18000f693  lea     rax, [rbp+57h+var_48]
0x18000f697  mov     [rsp+110h+var_A8], rax
0x18000f69c  lea     rax, [rbp+57h+arg_10]
0x18000f6a0  mov     [rsp+110h+var_B0], rax
0x18000f6a5  lea     rax, [rbp+57h+var_40]
0x18000f6a9  mov     [rsp+110h+var_B8], rax
0x18000f6ae  lea     rax, [rbp+57h+arg_18]
0x18000f6b2  mov     [rsp+110h+var_C0], rax
0x18000f6b7  lea     rax, [rbp+57h+var_38]
0x18000f6bb  mov     [rsp+110h+var_C8], rax
0x18000f6c0  lea     rax, [rbp+57h+var_70]
0x18000f6c4  mov     [rsp+110h+var_D0], rax
0x18000f6c9  lea     rax, [rbp+57h+var_30]
0x18000f6cd  mov     [rsp+110h+var_D8], rax
0x18000f6d2  lea     rax, [rbp+57h+var_6C]
0x18000f6d6  mov     [rsp+110h+var_E0], rax
0x18000f6db  lea     rax, [rbp+57h+var_28]
0x18000f6df  mov     [rsp+110h+var_E8], rax
0x18000f6e4  lea     rax, [rbp+57h+var_20]
0x18000f6e8  mov     [rbp+57h+var_68], rcx
0x18000f6ec  mov     rcx, r9
0x18000f6ef  mov     [rsp+110h+var_F0], rax
0x18000f6f4  mov     [rbp+57h+var_28], 1000000h
0x18000f6fc  mov     [rbp+57h+var_20], 0
0x18000f704  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f709  jmp     short loc_18000F782
0x18000f70b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f710  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f715  mov     rdi, rax
0x18000f718  mov     ecx, [rax]
0x18000f71a  cmp     ecx, 5
0x18000f71d  jbe     short loc_18000F782
0x18000f71f  mov     rdx, 200000000000h
0x18000f729  mov     rcx, rax
0x18000f72c  call    _tlgKeywordOn
0x18000f731  test    al, al
0x18000f733  jz      short loc_18000F782
0x18000f735  call    cs:__imp_GetCurrentThreadId
0x18000f73b  mov     r8, [rbx+110h]
0x18000f742  lea     rdx, byte_180039213
0x18000f749  mov     [rbp+57h+arg_0], eax
0x18000f74c  mov     rcx, rdi
0x18000f74f  mov     eax, [r8+48h]
0x18000f753  add     r8, 8
0x18000f757  mov     [rbp+57h+arg_8], eax
0x18000f75a  lea     rax, [rbp+57h+arg_0]
0x18000f75e  mov     [rsp+110h+var_E0], rax
0x18000f763  lea     rax, [rbp+57h+arg_8]
0x18000f767  mov     [rsp+110h+var_E8], rax
0x18000f76c  lea     rax, [rbp+57h+arg_10]
0x18000f770  mov     [rsp+110h+var_F0], rax
0x18000f775  mov     [rbp+57h+arg_10], 0
0x18000f77d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f782  mov     rcx, rbx
0x18000f785  add     rsp, 100h
0x18000f78c  pop     rdi
0x18000f78d  pop     rbx
0x18000f78e  pop     rbp
0x18000f78f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
