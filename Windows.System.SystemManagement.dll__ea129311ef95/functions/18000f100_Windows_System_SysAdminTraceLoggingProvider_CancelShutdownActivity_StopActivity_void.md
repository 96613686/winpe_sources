# Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StopActivity(void)

- ea: `0x18000f100`
- end: `0x18000f32c`
- name: `?StopActivity@CancelShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800013ac`
- `0x180001730`
- `0x18000df18`
- `0x18000e62c`
- `0x18000f100`
- `0x18000fe68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f2cd`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *this)
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
        (__int64)byte_18003962D,
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
        (__int64)&word_1800395D6,
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
0x18000f100  push    rbp
0x18000f102  push    rbx
0x18000f103  push    rdi
0x18000f104  lea     rbp, [rsp+10h]
0x18000f109  sub     rsp, 130h
0x18000f110  mov     rdi, [rcx+110h]
0x18000f117  mov     rbx, rcx
0x18000f11a  mov     eax, [rdi+48h]
0x18000f11d  test    eax, eax
0x18000f11f  jns     loc_18000F2B9
0x18000f125  add     rdi, 50h ; 'P'
0x18000f129  cmp     eax, [rdi+8]
0x18000f12c  jnz     loc_18000F2B9
0x18000f132  test    rdi, rdi
0x18000f135  jz      loc_18000F2B9
0x18000f13b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f140  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f145  mov     r9, rax
0x18000f148  mov     ecx, [rax]
0x18000f14a  cmp     ecx, 5
0x18000f14d  jbe     loc_18000F31A
0x18000f153  mov     rax, [rdi+70h]
0x18000f157  lea     rdx, byte_18003962D
0x18000f15e  mov     rcx, [rdi+30h]
0x18000f162  mov     [rbp+var_60], rax
0x18000f166  mov     eax, [rdi+68h]
0x18000f169  mov     r8, [rbx+110h]
0x18000f170  mov     dword ptr [rbp+arg_10], eax
0x18000f173  add     r8, 8
0x18000f177  mov     rax, [rdi+60h]
0x18000f17b  mov     [rbp+var_58], rax
0x18000f17f  mov     rax, [rdi+58h]
0x18000f183  mov     [rbp+var_50], rax
0x18000f187  mov     eax, [rdi+50h]
0x18000f18a  mov     [rbp+arg_18], eax
0x18000f18d  mov     rax, [rdi+48h]
0x18000f191  mov     [rbp+var_48], rax
0x18000f195  mov     eax, [rdi+20h]
0x18000f198  mov     [rbp+var_80], eax
0x18000f19b  mov     rax, [rdi+18h]
0x18000f19f  mov     [rbp+var_40], rax
0x18000f1a3  mov     eax, [rdi]
0x18000f1a5  mov     [rbp+var_7C], eax
0x18000f1a8  mov     rax, [rdi+80h]
0x18000f1af  mov     [rbp+var_38], rax
0x18000f1b3  mov     eax, [rdi+40h]
0x18000f1b6  mov     [rbp+var_78], eax
0x18000f1b9  mov     rax, [rdi+38h]
0x18000f1bd  mov     [rbp+var_30], rax
0x18000f1c1  mov     eax, [rdi+8]
0x18000f1c4  mov     [rbp+var_74], eax
0x18000f1c7  lea     rax, [rbp+var_70]
0x18000f1cb  mov     [rsp+140h+var_90], rax
0x18000f1d3  lea     rax, [rbp+arg_0]
0x18000f1d7  mov     [rsp+140h+var_98], rax
0x18000f1df  lea     rax, [rbp+arg_8]
0x18000f1e3  mov     [rsp+140h+var_A0], rax
0x18000f1eb  lea     rax, [rbp+var_68]
0x18000f1ef  mov     [rsp+140h+var_A8], rax
0x18000f1f7  lea     rax, [rbp+var_60]
0x18000f1fb  mov     [rsp+140h+var_B0], rax
0x18000f203  lea     rax, [rbp+arg_10]
0x18000f207  mov     [rsp+140h+var_B8], rax
0x18000f20f  lea     rax, [rbp+var_58]
0x18000f213  mov     [rsp+140h+var_C0], rax
0x18000f21b  lea     rax, [rbp+var_50]
0x18000f21f  mov     [rsp+140h+var_C8], rax
0x18000f224  lea     rax, [rbp+arg_18]
0x18000f228  mov     [rsp+140h+var_D0], rax
0x18000f22d  lea     rax, [rbp+var_48]
0x18000f231  mov     [rsp+140h+var_D8], rax
0x18000f236  lea     rax, [rbp+var_80]
0x18000f23a  mov     [rsp+140h+var_E0], rax
0x18000f23f  lea     rax, [rbp+var_40]
0x18000f243  mov     [rsp+140h+var_E8], rax
0x18000f248  lea     rax, [rbp+var_7C]
0x18000f24c  mov     [rsp+140h+var_F0], rax
0x18000f251  lea     rax, [rbp+var_38]
0x18000f255  mov     [rsp+140h+var_F8], rax
0x18000f25a  lea     rax, [rbp+var_78]
0x18000f25e  mov     [rsp+140h+var_100], rax
0x18000f263  lea     rax, [rbp+var_30]
0x18000f267  mov     [rsp+140h+var_108], rax
0x18000f26c  lea     rax, [rbp+var_74]
0x18000f270  mov     [rbp+var_70], rcx
0x18000f274  mov     ecx, [rdi+44h]
0x18000f277  mov     [rsp+140h+var_110], rax
0x18000f27c  lea     rax, [rbp+var_28]
0x18000f280  mov     [rbp+arg_0], ecx
0x18000f283  mov     ecx, [rdi+10h]
0x18000f286  mov     [rbp+arg_8], ecx
0x18000f289  mov     rcx, [rdi+78h]
0x18000f28d  mov     [rsp+140h+var_118], rax
0x18000f292  lea     rax, [rbp+var_20]
0x18000f296  mov     [rbp+var_68], rcx
0x18000f29a  mov     rcx, r9
0x18000f29d  mov     [rsp+140h+var_120], rax
0x18000f2a2  mov     [rbp+var_28], 1000000h
0x18000f2aa  mov     [rbp+var_20], 0
0x18000f2b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f2b7  jmp     short loc_18000F31A
0x18000f2b9  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f2be  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000f2c3  mov     rdi, rax
0x18000f2c6  mov     ecx, [rax]
0x18000f2c8  cmp     ecx, 5
0x18000f2cb  jbe     short loc_18000F31A
0x18000f2cd  call    cs:__imp_GetCurrentThreadId
0x18000f2d3  mov     r8, [rbx+110h]
0x18000f2da  lea     rdx, word_1800395D6
0x18000f2e1  mov     [rbp+arg_0], eax
0x18000f2e4  lea     rax, [rbp+arg_0]
0x18000f2e8  mov     [rsp+140h+var_110], rax
0x18000f2ed  lea     rax, [rbp+arg_8]
0x18000f2f1  mov     [rsp+140h+var_118], rax
0x18000f2f6  lea     rax, [rbp+arg_10]
0x18000f2fa  mov     ecx, [r8+48h]
0x18000f2fe  add     r8, 8
0x18000f302  mov     [rbp+arg_8], ecx
0x18000f305  mov     rcx, rdi
0x18000f308  mov     [rsp+140h+var_120], rax
0x18000f30d  mov     [rbp+arg_10], 0
0x18000f315  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f31a  mov     rcx, rbx
0x18000f31d  add     rsp, 130h
0x18000f324  pop     rdi
0x18000f325  pop     rbx
0x18000f326  pop     rbp
0x18000f327  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
