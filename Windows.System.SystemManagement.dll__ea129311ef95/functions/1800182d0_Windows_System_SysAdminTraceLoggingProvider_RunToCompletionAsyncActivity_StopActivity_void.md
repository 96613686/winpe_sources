# Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StopActivity(void)

- ea: `0x1800182d0`
- end: `0x1800184fc`
- name: `?StopActivity@RunToCompletionAsyncActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800013ac`
- `0x180001730`
- `0x18000df18`
- `0x18000e62c`
- `0x18000fe68`
- `0x1800182d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001849d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001849d`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *this)
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
    wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::System::SysAdminTraceLoggingProvider::Provider();
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
        (__int64)&unk_18003A058,
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
    wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = Windows::System::SysAdminTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)byte_180039FFB,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x1800182d0  push    rbp
0x1800182d2  push    rbx
0x1800182d3  push    rdi
0x1800182d4  lea     rbp, [rsp+10h]
0x1800182d9  sub     rsp, 130h
0x1800182e0  mov     rdi, [rcx+110h]
0x1800182e7  mov     rbx, rcx
0x1800182ea  mov     eax, [rdi+48h]
0x1800182ed  test    eax, eax
0x1800182ef  jns     loc_180018489
0x1800182f5  add     rdi, 50h ; 'P'
0x1800182f9  cmp     eax, [rdi+8]
0x1800182fc  jnz     loc_180018489
0x180018302  test    rdi, rdi
0x180018305  jz      loc_180018489
0x18001830b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018310  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180018315  mov     r9, rax
0x180018318  mov     ecx, [rax]
0x18001831a  cmp     ecx, 5
0x18001831d  jbe     loc_1800184EA
0x180018323  mov     rax, [rdi+70h]
0x180018327  lea     rdx, unk_18003A058
0x18001832e  mov     rcx, [rdi+30h]
0x180018332  mov     [rbp+var_60], rax
0x180018336  mov     eax, [rdi+68h]
0x180018339  mov     r8, [rbx+110h]
0x180018340  mov     dword ptr [rbp+arg_10], eax
0x180018343  add     r8, 8
0x180018347  mov     rax, [rdi+60h]
0x18001834b  mov     [rbp+var_58], rax
0x18001834f  mov     rax, [rdi+58h]
0x180018353  mov     [rbp+var_50], rax
0x180018357  mov     eax, [rdi+50h]
0x18001835a  mov     [rbp+arg_18], eax
0x18001835d  mov     rax, [rdi+48h]
0x180018361  mov     [rbp+var_48], rax
0x180018365  mov     eax, [rdi+20h]
0x180018368  mov     [rbp+var_80], eax
0x18001836b  mov     rax, [rdi+18h]
0x18001836f  mov     [rbp+var_40], rax
0x180018373  mov     eax, [rdi]
0x180018375  mov     [rbp+var_7C], eax
0x180018378  mov     rax, [rdi+80h]
0x18001837f  mov     [rbp+var_38], rax
0x180018383  mov     eax, [rdi+40h]
0x180018386  mov     [rbp+var_78], eax
0x180018389  mov     rax, [rdi+38h]
0x18001838d  mov     [rbp+var_30], rax
0x180018391  mov     eax, [rdi+8]
0x180018394  mov     [rbp+var_74], eax
0x180018397  lea     rax, [rbp+var_70]
0x18001839b  mov     [rsp+140h+var_90], rax
0x1800183a3  lea     rax, [rbp+arg_0]
0x1800183a7  mov     [rsp+140h+var_98], rax
0x1800183af  lea     rax, [rbp+arg_8]
0x1800183b3  mov     [rsp+140h+var_A0], rax
0x1800183bb  lea     rax, [rbp+var_68]
0x1800183bf  mov     [rsp+140h+var_A8], rax
0x1800183c7  lea     rax, [rbp+var_60]
0x1800183cb  mov     [rsp+140h+var_B0], rax
0x1800183d3  lea     rax, [rbp+arg_10]
0x1800183d7  mov     [rsp+140h+var_B8], rax
0x1800183df  lea     rax, [rbp+var_58]
0x1800183e3  mov     [rsp+140h+var_C0], rax
0x1800183eb  lea     rax, [rbp+var_50]
0x1800183ef  mov     [rsp+140h+var_C8], rax
0x1800183f4  lea     rax, [rbp+arg_18]
0x1800183f8  mov     [rsp+140h+var_D0], rax
0x1800183fd  lea     rax, [rbp+var_48]
0x180018401  mov     [rsp+140h+var_D8], rax
0x180018406  lea     rax, [rbp+var_80]
0x18001840a  mov     [rsp+140h+var_E0], rax
0x18001840f  lea     rax, [rbp+var_40]
0x180018413  mov     [rsp+140h+var_E8], rax
0x180018418  lea     rax, [rbp+var_7C]
0x18001841c  mov     [rsp+140h+var_F0], rax
0x180018421  lea     rax, [rbp+var_38]
0x180018425  mov     [rsp+140h+var_F8], rax
0x18001842a  lea     rax, [rbp+var_78]
0x18001842e  mov     [rsp+140h+var_100], rax
0x180018433  lea     rax, [rbp+var_30]
0x180018437  mov     [rsp+140h+var_108], rax
0x18001843c  lea     rax, [rbp+var_74]
0x180018440  mov     [rbp+var_70], rcx
0x180018444  mov     ecx, [rdi+44h]
0x180018447  mov     [rsp+140h+var_110], rax
0x18001844c  lea     rax, [rbp+var_28]
0x180018450  mov     [rbp+arg_0], ecx
0x180018453  mov     ecx, [rdi+10h]
0x180018456  mov     [rbp+arg_8], ecx
0x180018459  mov     rcx, [rdi+78h]
0x18001845d  mov     [rsp+140h+var_118], rax
0x180018462  lea     rax, [rbp+var_20]
0x180018466  mov     [rbp+var_68], rcx
0x18001846a  mov     rcx, r9
0x18001846d  mov     [rsp+140h+var_120], rax
0x180018472  mov     [rbp+var_28], 1000000h
0x18001847a  mov     [rbp+var_20], 0
0x180018482  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018487  jmp     short loc_1800184EA
0x180018489  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001848e  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180018493  mov     rdi, rax
0x180018496  mov     ecx, [rax]
0x180018498  cmp     ecx, 5
0x18001849b  jbe     short loc_1800184EA
0x18001849d  call    cs:__imp_GetCurrentThreadId
0x1800184a3  mov     r8, [rbx+110h]
0x1800184aa  lea     rdx, byte_180039FFB
0x1800184b1  mov     [rbp+arg_0], eax
0x1800184b4  lea     rax, [rbp+arg_0]
0x1800184b8  mov     [rsp+140h+var_110], rax
0x1800184bd  lea     rax, [rbp+arg_8]
0x1800184c1  mov     [rsp+140h+var_118], rax
0x1800184c6  lea     rax, [rbp+arg_10]
0x1800184ca  mov     ecx, [r8+48h]
0x1800184ce  add     r8, 8
0x1800184d2  mov     [rbp+arg_8], ecx
0x1800184d5  mov     rcx, rdi
0x1800184d8  mov     [rsp+140h+var_120], rax
0x1800184dd  mov     [rbp+arg_10], 0
0x1800184e5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800184ea  mov     rcx, rbx
0x1800184ed  add     rsp, 130h
0x1800184f4  pop     rdi
0x1800184f5  pop     rbx
0x1800184f6  pop     rbp
0x1800184f7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
