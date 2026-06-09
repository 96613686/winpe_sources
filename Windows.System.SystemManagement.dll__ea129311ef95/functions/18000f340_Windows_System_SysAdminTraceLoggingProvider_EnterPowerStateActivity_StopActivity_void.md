# Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateActivity::StopActivity(void)

- ea: `0x18000f340`
- end: `0x18000f564`
- name: `?StopActivity@EnterPowerStateActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010f8`
- `0x180001730`
- `0x180001ebc`
- `0x18000df18`
- `0x18000e62c`
- `0x18000f340`
- `0x18000fe68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f505`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::EnterPowerStateActivity *this)
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
        (__int64)byte_180039459,
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
        (__int64)byte_180039401,
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
0x18000f340  push    rbp
0x18000f342  push    rbx
0x18000f343  push    rdi
0x18000f344  lea     rbp, [rsp-47h]
0x18000f349  sub     rsp, 100h
0x18000f350  mov     rdi, [rcx+110h]
0x18000f357  mov     rbx, rcx
0x18000f35a  mov     eax, [rdi+48h]
0x18000f35d  test    eax, eax
0x18000f35f  jns     loc_18000F4DB
0x18000f365  add     rdi, 50h ; 'P'
0x18000f369  cmp     eax, [rdi+8]
0x18000f36c  jnz     loc_18000F4DB
0x18000f372  test    rdi, rdi
0x18000f375  jz      loc_18000F4DB
0x18000f37b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f380  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f385  mov     r9, rax
0x18000f388  mov     ecx, [rax]
0x18000f38a  cmp     ecx, 5
0x18000f38d  jbe     loc_18000F552
0x18000f393  mov     rdx, 200000000000h
0x18000f39d  mov     rcx, rax
0x18000f3a0  call    _tlgKeywordOn
0x18000f3a5  test    al, al
0x18000f3a7  jz      loc_18000F552
0x18000f3ad  mov     rax, [rdi+70h]
0x18000f3b1  lea     rdx, byte_180039459
0x18000f3b8  mov     rcx, [rdi+78h]
0x18000f3bc  mov     r8, [rbx+110h]
0x18000f3c3  mov     [rbp+57h+var_60], rax
0x18000f3c7  add     r8, 8
0x18000f3cb  mov     eax, [rdi+68h]
0x18000f3ce  mov     [rbp+57h+arg_0], eax
0x18000f3d1  mov     rax, [rdi+60h]
0x18000f3d5  mov     [rbp+57h+var_58], rax
0x18000f3d9  mov     rax, [rdi+58h]
0x18000f3dd  mov     [rbp+57h+var_50], rax
0x18000f3e1  mov     eax, [rdi+50h]
0x18000f3e4  mov     [rbp+57h+arg_8], eax
0x18000f3e7  mov     rax, [rdi+48h]
0x18000f3eb  mov     [rbp+57h+var_48], rax
0x18000f3ef  mov     eax, [rdi+20h]
0x18000f3f2  mov     dword ptr [rbp+57h+arg_10], eax
0x18000f3f5  mov     rax, [rdi+18h]
0x18000f3f9  mov     [rbp+57h+var_40], rax
0x18000f3fd  mov     eax, [rdi]
0x18000f3ff  mov     [rbp+57h+arg_18], eax
0x18000f402  mov     rax, [rdi+80h]
0x18000f409  mov     [rbp+57h+var_38], rax
0x18000f40d  mov     eax, [rdi+40h]
0x18000f410  mov     [rbp+57h+var_70], eax
0x18000f413  mov     rax, [rdi+38h]
0x18000f417  mov     [rbp+57h+var_30], rax
0x18000f41b  mov     eax, [rdi+8]
0x18000f41e  mov     [rbp+57h+var_6C], eax
0x18000f421  lea     rax, [rbp+57h+var_68]
0x18000f425  mov     [rsp+110h+var_78], rax
0x18000f42d  lea     rax, [rbp+57h+var_60]
0x18000f431  mov     [rsp+110h+var_80], rax
0x18000f439  lea     rax, [rbp+57h+arg_0]
0x18000f43d  mov     [rsp+110h+var_88], rax
0x18000f445  lea     rax, [rbp+57h+var_58]
0x18000f449  mov     [rsp+110h+var_90], rax
0x18000f451  lea     rax, [rbp+57h+var_50]
0x18000f455  mov     [rsp+110h+var_98], rax
0x18000f45a  lea     rax, [rbp+57h+arg_8]
0x18000f45e  mov     [rsp+110h+var_A0], rax
0x18000f463  lea     rax, [rbp+57h+var_48]
0x18000f467  mov     [rsp+110h+var_A8], rax
0x18000f46c  lea     rax, [rbp+57h+arg_10]
0x18000f470  mov     [rsp+110h+var_B0], rax
0x18000f475  lea     rax, [rbp+57h+var_40]
0x18000f479  mov     [rsp+110h+var_B8], rax
0x18000f47e  lea     rax, [rbp+57h+arg_18]
0x18000f482  mov     [rsp+110h+var_C0], rax
0x18000f487  lea     rax, [rbp+57h+var_38]
0x18000f48b  mov     [rsp+110h+var_C8], rax
0x18000f490  lea     rax, [rbp+57h+var_70]
0x18000f494  mov     [rsp+110h+var_D0], rax
0x18000f499  lea     rax, [rbp+57h+var_30]
0x18000f49d  mov     [rsp+110h+var_D8], rax
0x18000f4a2  lea     rax, [rbp+57h+var_6C]
0x18000f4a6  mov     [rsp+110h+var_E0], rax
0x18000f4ab  lea     rax, [rbp+57h+var_28]
0x18000f4af  mov     [rsp+110h+var_E8], rax
0x18000f4b4  lea     rax, [rbp+57h+var_20]
0x18000f4b8  mov     [rbp+57h+var_68], rcx
0x18000f4bc  mov     rcx, r9
0x18000f4bf  mov     [rsp+110h+var_F0], rax
0x18000f4c4  mov     [rbp+57h+var_28], 1000000h
0x18000f4cc  mov     [rbp+57h+var_20], 0
0x18000f4d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f4d9  jmp     short loc_18000F552
0x18000f4db  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f4e0  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f4e5  mov     rdi, rax
0x18000f4e8  mov     ecx, [rax]
0x18000f4ea  cmp     ecx, 5
0x18000f4ed  jbe     short loc_18000F552
0x18000f4ef  mov     rdx, 200000000000h
0x18000f4f9  mov     rcx, rax
0x18000f4fc  call    _tlgKeywordOn
0x18000f501  test    al, al
0x18000f503  jz      short loc_18000F552
0x18000f505  call    cs:__imp_GetCurrentThreadId
0x18000f50b  mov     r8, [rbx+110h]
0x18000f512  lea     rdx, byte_180039401
0x18000f519  mov     [rbp+57h+arg_0], eax
0x18000f51c  mov     rcx, rdi
0x18000f51f  mov     eax, [r8+48h]
0x18000f523  add     r8, 8
0x18000f527  mov     [rbp+57h+arg_8], eax
0x18000f52a  lea     rax, [rbp+57h+arg_0]
0x18000f52e  mov     [rsp+110h+var_E0], rax
0x18000f533  lea     rax, [rbp+57h+arg_8]
0x18000f537  mov     [rsp+110h+var_E8], rax
0x18000f53c  lea     rax, [rbp+57h+arg_10]
0x18000f540  mov     [rsp+110h+var_F0], rax
0x18000f545  mov     [rbp+57h+arg_10], 0
0x18000f54d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f552  mov     rcx, rbx
0x18000f555  add     rsp, 100h
0x18000f55c  pop     rdi
0x18000f55d  pop     rbx
0x18000f55e  pop     rbp
0x18000f55f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
