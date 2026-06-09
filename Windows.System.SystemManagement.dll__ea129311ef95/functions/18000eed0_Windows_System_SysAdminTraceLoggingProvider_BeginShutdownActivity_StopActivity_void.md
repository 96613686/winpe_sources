# Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StopActivity(void)

- ea: `0x18000eed0`
- end: `0x18000f0f4`
- name: `?StopActivity@BeginShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010f8`
- `0x180001730`
- `0x180001ebc`
- `0x18000df18`
- `0x18000e62c`
- `0x18000eed0`
- `0x18000fe68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f095`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *this)
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
        (__int64)byte_180039821,
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
        (__int64)byte_1800397CB,
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
0x18000eed0  push    rbp
0x18000eed2  push    rbx
0x18000eed3  push    rdi
0x18000eed4  lea     rbp, [rsp-47h]
0x18000eed9  sub     rsp, 100h
0x18000eee0  mov     rdi, [rcx+110h]
0x18000eee7  mov     rbx, rcx
0x18000eeea  mov     eax, [rdi+48h]
0x18000eeed  test    eax, eax
0x18000eeef  jns     loc_18000F06B
0x18000eef5  add     rdi, 50h ; 'P'
0x18000eef9  cmp     eax, [rdi+8]
0x18000eefc  jnz     loc_18000F06B
0x18000ef02  test    rdi, rdi
0x18000ef05  jz      loc_18000F06B
0x18000ef0b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ef10  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000ef15  mov     r9, rax
0x18000ef18  mov     ecx, [rax]
0x18000ef1a  cmp     ecx, 5
0x18000ef1d  jbe     loc_18000F0E2
0x18000ef23  mov     rdx, 200000000000h
0x18000ef2d  mov     rcx, rax
0x18000ef30  call    _tlgKeywordOn
0x18000ef35  test    al, al
0x18000ef37  jz      loc_18000F0E2
0x18000ef3d  mov     rax, [rdi+70h]
0x18000ef41  lea     rdx, byte_180039821
0x18000ef48  mov     rcx, [rdi+78h]
0x18000ef4c  mov     r8, [rbx+110h]
0x18000ef53  mov     [rbp+57h+var_60], rax
0x18000ef57  add     r8, 8
0x18000ef5b  mov     eax, [rdi+68h]
0x18000ef5e  mov     [rbp+57h+arg_0], eax
0x18000ef61  mov     rax, [rdi+60h]
0x18000ef65  mov     [rbp+57h+var_58], rax
0x18000ef69  mov     rax, [rdi+58h]
0x18000ef6d  mov     [rbp+57h+var_50], rax
0x18000ef71  mov     eax, [rdi+50h]
0x18000ef74  mov     [rbp+57h+arg_8], eax
0x18000ef77  mov     rax, [rdi+48h]
0x18000ef7b  mov     [rbp+57h+var_48], rax
0x18000ef7f  mov     eax, [rdi+20h]
0x18000ef82  mov     dword ptr [rbp+57h+arg_10], eax
0x18000ef85  mov     rax, [rdi+18h]
0x18000ef89  mov     [rbp+57h+var_40], rax
0x18000ef8d  mov     eax, [rdi]
0x18000ef8f  mov     [rbp+57h+arg_18], eax
0x18000ef92  mov     rax, [rdi+80h]
0x18000ef99  mov     [rbp+57h+var_38], rax
0x18000ef9d  mov     eax, [rdi+40h]
0x18000efa0  mov     [rbp+57h+var_70], eax
0x18000efa3  mov     rax, [rdi+38h]
0x18000efa7  mov     [rbp+57h+var_30], rax
0x18000efab  mov     eax, [rdi+8]
0x18000efae  mov     [rbp+57h+var_6C], eax
0x18000efb1  lea     rax, [rbp+57h+var_68]
0x18000efb5  mov     [rsp+110h+var_78], rax
0x18000efbd  lea     rax, [rbp+57h+var_60]
0x18000efc1  mov     [rsp+110h+var_80], rax
0x18000efc9  lea     rax, [rbp+57h+arg_0]
0x18000efcd  mov     [rsp+110h+var_88], rax
0x18000efd5  lea     rax, [rbp+57h+var_58]
0x18000efd9  mov     [rsp+110h+var_90], rax
0x18000efe1  lea     rax, [rbp+57h+var_50]
0x18000efe5  mov     [rsp+110h+var_98], rax
0x18000efea  lea     rax, [rbp+57h+arg_8]
0x18000efee  mov     [rsp+110h+var_A0], rax
0x18000eff3  lea     rax, [rbp+57h+var_48]
0x18000eff7  mov     [rsp+110h+var_A8], rax
0x18000effc  lea     rax, [rbp+57h+arg_10]
0x18000f000  mov     [rsp+110h+var_B0], rax
0x18000f005  lea     rax, [rbp+57h+var_40]
0x18000f009  mov     [rsp+110h+var_B8], rax
0x18000f00e  lea     rax, [rbp+57h+arg_18]
0x18000f012  mov     [rsp+110h+var_C0], rax
0x18000f017  lea     rax, [rbp+57h+var_38]
0x18000f01b  mov     [rsp+110h+var_C8], rax
0x18000f020  lea     rax, [rbp+57h+var_70]
0x18000f024  mov     [rsp+110h+var_D0], rax
0x18000f029  lea     rax, [rbp+57h+var_30]
0x18000f02d  mov     [rsp+110h+var_D8], rax
0x18000f032  lea     rax, [rbp+57h+var_6C]
0x18000f036  mov     [rsp+110h+var_E0], rax
0x18000f03b  lea     rax, [rbp+57h+var_28]
0x18000f03f  mov     [rsp+110h+var_E8], rax
0x18000f044  lea     rax, [rbp+57h+var_20]
0x18000f048  mov     [rbp+57h+var_68], rcx
0x18000f04c  mov     rcx, r9
0x18000f04f  mov     [rsp+110h+var_F0], rax
0x18000f054  mov     [rbp+57h+var_28], 1000000h
0x18000f05c  mov     [rbp+57h+var_20], 0
0x18000f064  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000f069  jmp     short loc_18000F0E2
0x18000f06b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f070  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f075  mov     rdi, rax
0x18000f078  mov     ecx, [rax]
0x18000f07a  cmp     ecx, 5
0x18000f07d  jbe     short loc_18000F0E2
0x18000f07f  mov     rdx, 200000000000h
0x18000f089  mov     rcx, rax
0x18000f08c  call    _tlgKeywordOn
0x18000f091  test    al, al
0x18000f093  jz      short loc_18000F0E2
0x18000f095  call    cs:__imp_GetCurrentThreadId
0x18000f09b  mov     r8, [rbx+110h]
0x18000f0a2  lea     rdx, byte_1800397CB
0x18000f0a9  mov     [rbp+57h+arg_0], eax
0x18000f0ac  mov     rcx, rdi
0x18000f0af  mov     eax, [r8+48h]
0x18000f0b3  add     r8, 8
0x18000f0b7  mov     [rbp+57h+arg_8], eax
0x18000f0ba  lea     rax, [rbp+57h+arg_0]
0x18000f0be  mov     [rsp+110h+var_E0], rax
0x18000f0c3  lea     rax, [rbp+57h+arg_8]
0x18000f0c7  mov     [rsp+110h+var_E8], rax
0x18000f0cc  lea     rax, [rbp+57h+arg_10]
0x18000f0d0  mov     [rsp+110h+var_F0], rax
0x18000f0d5  mov     [rbp+57h+arg_10], 0
0x18000f0dd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f0e2  mov     rcx, rbx
0x18000f0e5  add     rsp, 100h
0x18000f0ec  pop     rdi
0x18000f0ed  pop     rbx
0x18000f0ee  pop     rbp
0x18000f0ef  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
