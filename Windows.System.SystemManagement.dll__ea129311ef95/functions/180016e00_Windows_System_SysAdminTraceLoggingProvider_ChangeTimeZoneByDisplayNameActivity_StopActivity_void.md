# Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StopActivity(void)

- ea: `0x180016e00`
- end: `0x180017024`
- name: `?StopActivity@ChangeTimeZoneByDisplayNameActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010f8`
- `0x180001730`
- `0x180001ebc`
- `0x18000df18`
- `0x18000e62c`
- `0x18000fe68`
- `0x180016e00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fc5`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *this)
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
        (__int64)&word_180039C66,
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
        (__int64)word_180039C02,
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
0x180016e00  push    rbp
0x180016e02  push    rbx
0x180016e03  push    rdi
0x180016e04  lea     rbp, [rsp-47h]
0x180016e09  sub     rsp, 100h
0x180016e10  mov     rdi, [rcx+110h]
0x180016e17  mov     rbx, rcx
0x180016e1a  mov     eax, [rdi+48h]
0x180016e1d  test    eax, eax
0x180016e1f  jns     loc_180016F9B
0x180016e25  add     rdi, 50h ; 'P'
0x180016e29  cmp     eax, [rdi+8]
0x180016e2c  jnz     loc_180016F9B
0x180016e32  test    rdi, rdi
0x180016e35  jz      loc_180016F9B
0x180016e3b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016e40  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180016e45  mov     r9, rax
0x180016e48  mov     ecx, [rax]
0x180016e4a  cmp     ecx, 5
0x180016e4d  jbe     loc_180017012
0x180016e53  mov     rdx, 200000000000h
0x180016e5d  mov     rcx, rax
0x180016e60  call    _tlgKeywordOn
0x180016e65  test    al, al
0x180016e67  jz      loc_180017012
0x180016e6d  mov     rax, [rdi+70h]
0x180016e71  lea     rdx, word_180039C66
0x180016e78  mov     rcx, [rdi+78h]
0x180016e7c  mov     r8, [rbx+110h]
0x180016e83  mov     [rbp+57h+var_60], rax
0x180016e87  add     r8, 8
0x180016e8b  mov     eax, [rdi+68h]
0x180016e8e  mov     [rbp+57h+arg_0], eax
0x180016e91  mov     rax, [rdi+60h]
0x180016e95  mov     [rbp+57h+var_58], rax
0x180016e99  mov     rax, [rdi+58h]
0x180016e9d  mov     [rbp+57h+var_50], rax
0x180016ea1  mov     eax, [rdi+50h]
0x180016ea4  mov     [rbp+57h+arg_8], eax
0x180016ea7  mov     rax, [rdi+48h]
0x180016eab  mov     [rbp+57h+var_48], rax
0x180016eaf  mov     eax, [rdi+20h]
0x180016eb2  mov     dword ptr [rbp+57h+arg_10], eax
0x180016eb5  mov     rax, [rdi+18h]
0x180016eb9  mov     [rbp+57h+var_40], rax
0x180016ebd  mov     eax, [rdi]
0x180016ebf  mov     [rbp+57h+arg_18], eax
0x180016ec2  mov     rax, [rdi+80h]
0x180016ec9  mov     [rbp+57h+var_38], rax
0x180016ecd  mov     eax, [rdi+40h]
0x180016ed0  mov     [rbp+57h+var_70], eax
0x180016ed3  mov     rax, [rdi+38h]
0x180016ed7  mov     [rbp+57h+var_30], rax
0x180016edb  mov     eax, [rdi+8]
0x180016ede  mov     [rbp+57h+var_6C], eax
0x180016ee1  lea     rax, [rbp+57h+var_68]
0x180016ee5  mov     [rsp+110h+var_78], rax
0x180016eed  lea     rax, [rbp+57h+var_60]
0x180016ef1  mov     [rsp+110h+var_80], rax
0x180016ef9  lea     rax, [rbp+57h+arg_0]
0x180016efd  mov     [rsp+110h+var_88], rax
0x180016f05  lea     rax, [rbp+57h+var_58]
0x180016f09  mov     [rsp+110h+var_90], rax
0x180016f11  lea     rax, [rbp+57h+var_50]
0x180016f15  mov     [rsp+110h+var_98], rax
0x180016f1a  lea     rax, [rbp+57h+arg_8]
0x180016f1e  mov     [rsp+110h+var_A0], rax
0x180016f23  lea     rax, [rbp+57h+var_48]
0x180016f27  mov     [rsp+110h+var_A8], rax
0x180016f2c  lea     rax, [rbp+57h+arg_10]
0x180016f30  mov     [rsp+110h+var_B0], rax
0x180016f35  lea     rax, [rbp+57h+var_40]
0x180016f39  mov     [rsp+110h+var_B8], rax
0x180016f3e  lea     rax, [rbp+57h+arg_18]
0x180016f42  mov     [rsp+110h+var_C0], rax
0x180016f47  lea     rax, [rbp+57h+var_38]
0x180016f4b  mov     [rsp+110h+var_C8], rax
0x180016f50  lea     rax, [rbp+57h+var_70]
0x180016f54  mov     [rsp+110h+var_D0], rax
0x180016f59  lea     rax, [rbp+57h+var_30]
0x180016f5d  mov     [rsp+110h+var_D8], rax
0x180016f62  lea     rax, [rbp+57h+var_6C]
0x180016f66  mov     [rsp+110h+var_E0], rax
0x180016f6b  lea     rax, [rbp+57h+var_28]
0x180016f6f  mov     [rsp+110h+var_E8], rax
0x180016f74  lea     rax, [rbp+57h+var_20]
0x180016f78  mov     [rbp+57h+var_68], rcx
0x180016f7c  mov     rcx, r9
0x180016f7f  mov     [rsp+110h+var_F0], rax
0x180016f84  mov     [rbp+57h+var_28], 1000000h
0x180016f8c  mov     [rbp+57h+var_20], 0
0x180016f94  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180016f99  jmp     short loc_180017012
0x180016f9b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180016fa0  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180016fa5  mov     rdi, rax
0x180016fa8  mov     ecx, [rax]
0x180016faa  cmp     ecx, 5
0x180016fad  jbe     short loc_180017012
0x180016faf  mov     rdx, 200000000000h
0x180016fb9  mov     rcx, rax
0x180016fbc  call    _tlgKeywordOn
0x180016fc1  test    al, al
0x180016fc3  jz      short loc_180017012
0x180016fc5  call    cs:__imp_GetCurrentThreadId
0x180016fcb  mov     r8, [rbx+110h]
0x180016fd2  lea     rdx, word_180039C02
0x180016fd9  mov     [rbp+57h+arg_0], eax
0x180016fdc  mov     rcx, rdi
0x180016fdf  mov     eax, [r8+48h]
0x180016fe3  add     r8, 8
0x180016fe7  mov     [rbp+57h+arg_8], eax
0x180016fea  lea     rax, [rbp+57h+arg_0]
0x180016fee  mov     [rsp+110h+var_E0], rax
0x180016ff3  lea     rax, [rbp+57h+arg_8]
0x180016ff7  mov     [rsp+110h+var_E8], rax
0x180016ffc  lea     rax, [rbp+57h+arg_10]
0x180017000  mov     [rsp+110h+var_F0], rax
0x180017005  mov     [rbp+57h+arg_10], 0
0x18001700d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017012  mov     rcx, rbx
0x180017015  add     rsp, 100h
0x18001701c  pop     rdi
0x18001701d  pop     rbx
0x18001701e  pop     rbp
0x18001701f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
