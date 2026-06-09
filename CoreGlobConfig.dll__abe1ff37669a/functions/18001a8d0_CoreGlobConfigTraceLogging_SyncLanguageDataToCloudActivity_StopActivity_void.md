# CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::StopActivity(void)

- ea: `0x18001a8d0`
- end: `0x18001aaf4`
- name: `?StopActivity@SyncLanguageDataToCloudActivity@CoreGlobConfigTraceLogging@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180015bf0`
- `0x180016fcc`
- `0x18001a8d0`
- `0x18001f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa95`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity::StopActivity(
        CoreGlobConfigTraceLogging::SyncLanguageDataToCloudActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CoreGlobConfigTraceLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      v8 = (__int64 *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (__int64 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (__int64 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&dword_18002A41C,
        v9 + 8,
        v7,
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
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CoreGlobConfigTraceLogging::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002A553,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001a8d0  push    rbp
0x18001a8d2  push    rbx
0x18001a8d3  push    rdi
0x18001a8d4  lea     rbp, [rsp-47h]
0x18001a8d9  sub     rsp, 100h
0x18001a8e0  mov     rdi, [rcx+110h]
0x18001a8e7  mov     rbx, rcx
0x18001a8ea  mov     eax, [rdi+48h]
0x18001a8ed  test    eax, eax
0x18001a8ef  jns     loc_18001AA6B
0x18001a8f5  add     rdi, 50h ; 'P'
0x18001a8f9  cmp     eax, [rdi+8]
0x18001a8fc  jnz     loc_18001AA6B
0x18001a902  test    rdi, rdi
0x18001a905  jz      loc_18001AA6B
0x18001a90b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a910  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a915  mov     r9, rax
0x18001a918  mov     ecx, [rax]
0x18001a91a  cmp     ecx, 5
0x18001a91d  jbe     loc_18001AAE2
0x18001a923  mov     rdx, 200000000000h
0x18001a92d  mov     rcx, rax
0x18001a930  call    _tlgKeywordOn
0x18001a935  test    al, al
0x18001a937  jz      loc_18001AAE2
0x18001a93d  mov     rax, [rdi+70h]
0x18001a941  lea     rdx, dword_18002A41C
0x18001a948  mov     rcx, [rdi+78h]
0x18001a94c  mov     r8, [rbx+110h]
0x18001a953  mov     [rbp+57h+var_60], rax
0x18001a957  add     r8, 8
0x18001a95b  mov     eax, [rdi+68h]
0x18001a95e  mov     [rbp+57h+arg_0], eax
0x18001a961  mov     rax, [rdi+60h]
0x18001a965  mov     [rbp+57h+var_58], rax
0x18001a969  mov     rax, [rdi+58h]
0x18001a96d  mov     [rbp+57h+var_50], rax
0x18001a971  mov     eax, [rdi+50h]
0x18001a974  mov     [rbp+57h+arg_8], eax
0x18001a977  mov     rax, [rdi+48h]
0x18001a97b  mov     [rbp+57h+var_48], rax
0x18001a97f  mov     eax, [rdi+20h]
0x18001a982  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a985  mov     rax, [rdi+18h]
0x18001a989  mov     [rbp+57h+var_40], rax
0x18001a98d  mov     eax, [rdi]
0x18001a98f  mov     [rbp+57h+arg_18], eax
0x18001a992  mov     rax, [rdi+80h]
0x18001a999  mov     [rbp+57h+var_38], rax
0x18001a99d  mov     eax, [rdi+40h]
0x18001a9a0  mov     [rbp+57h+var_70], eax
0x18001a9a3  mov     rax, [rdi+38h]
0x18001a9a7  mov     [rbp+57h+var_30], rax
0x18001a9ab  mov     eax, [rdi+8]
0x18001a9ae  mov     [rbp+57h+var_6C], eax
0x18001a9b1  lea     rax, [rbp+57h+var_68]
0x18001a9b5  mov     [rsp+110h+var_78], rax
0x18001a9bd  lea     rax, [rbp+57h+var_60]
0x18001a9c1  mov     [rsp+110h+var_80], rax
0x18001a9c9  lea     rax, [rbp+57h+arg_0]
0x18001a9cd  mov     [rsp+110h+var_88], rax
0x18001a9d5  lea     rax, [rbp+57h+var_58]
0x18001a9d9  mov     [rsp+110h+var_90], rax
0x18001a9e1  lea     rax, [rbp+57h+var_50]
0x18001a9e5  mov     [rsp+110h+var_98], rax
0x18001a9ea  lea     rax, [rbp+57h+arg_8]
0x18001a9ee  mov     [rsp+110h+var_A0], rax
0x18001a9f3  lea     rax, [rbp+57h+var_48]
0x18001a9f7  mov     [rsp+110h+var_A8], rax
0x18001a9fc  lea     rax, [rbp+57h+arg_10]
0x18001aa00  mov     [rsp+110h+var_B0], rax
0x18001aa05  lea     rax, [rbp+57h+var_40]
0x18001aa09  mov     [rsp+110h+var_B8], rax
0x18001aa0e  lea     rax, [rbp+57h+arg_18]
0x18001aa12  mov     [rsp+110h+var_C0], rax
0x18001aa17  lea     rax, [rbp+57h+var_38]
0x18001aa1b  mov     [rsp+110h+var_C8], rax
0x18001aa20  lea     rax, [rbp+57h+var_70]
0x18001aa24  mov     [rsp+110h+var_D0], rax
0x18001aa29  lea     rax, [rbp+57h+var_30]
0x18001aa2d  mov     [rsp+110h+var_D8], rax
0x18001aa32  lea     rax, [rbp+57h+var_6C]
0x18001aa36  mov     [rsp+110h+var_E0], rax
0x18001aa3b  lea     rax, [rbp+57h+var_28]
0x18001aa3f  mov     [rsp+110h+var_E8], rax
0x18001aa44  lea     rax, [rbp+57h+var_20]
0x18001aa48  mov     [rbp+57h+var_68], rcx
0x18001aa4c  mov     rcx, r9
0x18001aa4f  mov     [rsp+110h+var_F0], rax
0x18001aa54  mov     [rbp+57h+var_28], 1000000h
0x18001aa5c  mov     [rbp+57h+var_20], 1000800h
0x18001aa64  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001aa69  jmp     short loc_18001AAE2
0x18001aa6b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aa70  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001aa75  mov     rdi, rax
0x18001aa78  mov     ecx, [rax]
0x18001aa7a  cmp     ecx, 5
0x18001aa7d  jbe     short loc_18001AAE2
0x18001aa7f  mov     rdx, 200000000000h
0x18001aa89  mov     rcx, rax
0x18001aa8c  call    _tlgKeywordOn
0x18001aa91  test    al, al
0x18001aa93  jz      short loc_18001AAE2
0x18001aa95  call    cs:__imp_GetCurrentThreadId
0x18001aa9b  mov     r8, [rbx+110h]
0x18001aaa2  lea     rdx, byte_18002A553
0x18001aaa9  mov     [rbp+57h+arg_0], eax
0x18001aaac  mov     rcx, rdi
0x18001aaaf  mov     eax, [r8+48h]
0x18001aab3  add     r8, 8
0x18001aab7  mov     [rbp+57h+arg_8], eax
0x18001aaba  lea     rax, [rbp+57h+arg_0]
0x18001aabe  mov     [rsp+110h+var_E0], rax
0x18001aac3  lea     rax, [rbp+57h+arg_8]
0x18001aac7  mov     [rsp+110h+var_E8], rax
0x18001aacc  lea     rax, [rbp+57h+arg_10]
0x18001aad0  mov     [rsp+110h+var_F0], rax
0x18001aad5  mov     [rbp+57h+arg_10], 1000800h
0x18001aadd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001aae2  mov     rcx, rbx
0x18001aae5  add     rsp, 100h
0x18001aaec  pop     rdi
0x18001aaed  pop     rbx
0x18001aaee  pop     rbp
0x18001aaef  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
