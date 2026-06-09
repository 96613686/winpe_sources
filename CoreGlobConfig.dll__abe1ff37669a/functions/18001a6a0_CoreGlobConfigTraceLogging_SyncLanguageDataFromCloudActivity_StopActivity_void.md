# CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StopActivity(void)

- ea: `0x18001a6a0`
- end: `0x18001a8c4`
- name: `?StopActivity@SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180015bf0`
- `0x180016fcc`
- `0x18001a6a0`
- `0x18001f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a865`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StopActivity(
        CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *this)
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
        (__int64)&dword_18002A0D4,
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
        (__int64)byte_18002A20D,
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
0x18001a6a0  push    rbp
0x18001a6a2  push    rbx
0x18001a6a3  push    rdi
0x18001a6a4  lea     rbp, [rsp-47h]
0x18001a6a9  sub     rsp, 100h
0x18001a6b0  mov     rdi, [rcx+110h]
0x18001a6b7  mov     rbx, rcx
0x18001a6ba  mov     eax, [rdi+48h]
0x18001a6bd  test    eax, eax
0x18001a6bf  jns     loc_18001A83B
0x18001a6c5  add     rdi, 50h ; 'P'
0x18001a6c9  cmp     eax, [rdi+8]
0x18001a6cc  jnz     loc_18001A83B
0x18001a6d2  test    rdi, rdi
0x18001a6d5  jz      loc_18001A83B
0x18001a6db  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a6e0  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a6e5  mov     r9, rax
0x18001a6e8  mov     ecx, [rax]
0x18001a6ea  cmp     ecx, 5
0x18001a6ed  jbe     loc_18001A8B2
0x18001a6f3  mov     rdx, 200000000000h
0x18001a6fd  mov     rcx, rax
0x18001a700  call    _tlgKeywordOn
0x18001a705  test    al, al
0x18001a707  jz      loc_18001A8B2
0x18001a70d  mov     rax, [rdi+70h]
0x18001a711  lea     rdx, dword_18002A0D4
0x18001a718  mov     rcx, [rdi+78h]
0x18001a71c  mov     r8, [rbx+110h]
0x18001a723  mov     [rbp+57h+var_60], rax
0x18001a727  add     r8, 8
0x18001a72b  mov     eax, [rdi+68h]
0x18001a72e  mov     [rbp+57h+arg_0], eax
0x18001a731  mov     rax, [rdi+60h]
0x18001a735  mov     [rbp+57h+var_58], rax
0x18001a739  mov     rax, [rdi+58h]
0x18001a73d  mov     [rbp+57h+var_50], rax
0x18001a741  mov     eax, [rdi+50h]
0x18001a744  mov     [rbp+57h+arg_8], eax
0x18001a747  mov     rax, [rdi+48h]
0x18001a74b  mov     [rbp+57h+var_48], rax
0x18001a74f  mov     eax, [rdi+20h]
0x18001a752  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a755  mov     rax, [rdi+18h]
0x18001a759  mov     [rbp+57h+var_40], rax
0x18001a75d  mov     eax, [rdi]
0x18001a75f  mov     [rbp+57h+arg_18], eax
0x18001a762  mov     rax, [rdi+80h]
0x18001a769  mov     [rbp+57h+var_38], rax
0x18001a76d  mov     eax, [rdi+40h]
0x18001a770  mov     [rbp+57h+var_70], eax
0x18001a773  mov     rax, [rdi+38h]
0x18001a777  mov     [rbp+57h+var_30], rax
0x18001a77b  mov     eax, [rdi+8]
0x18001a77e  mov     [rbp+57h+var_6C], eax
0x18001a781  lea     rax, [rbp+57h+var_68]
0x18001a785  mov     [rsp+110h+var_78], rax
0x18001a78d  lea     rax, [rbp+57h+var_60]
0x18001a791  mov     [rsp+110h+var_80], rax
0x18001a799  lea     rax, [rbp+57h+arg_0]
0x18001a79d  mov     [rsp+110h+var_88], rax
0x18001a7a5  lea     rax, [rbp+57h+var_58]
0x18001a7a9  mov     [rsp+110h+var_90], rax
0x18001a7b1  lea     rax, [rbp+57h+var_50]
0x18001a7b5  mov     [rsp+110h+var_98], rax
0x18001a7ba  lea     rax, [rbp+57h+arg_8]
0x18001a7be  mov     [rsp+110h+var_A0], rax
0x18001a7c3  lea     rax, [rbp+57h+var_48]
0x18001a7c7  mov     [rsp+110h+var_A8], rax
0x18001a7cc  lea     rax, [rbp+57h+arg_10]
0x18001a7d0  mov     [rsp+110h+var_B0], rax
0x18001a7d5  lea     rax, [rbp+57h+var_40]
0x18001a7d9  mov     [rsp+110h+var_B8], rax
0x18001a7de  lea     rax, [rbp+57h+arg_18]
0x18001a7e2  mov     [rsp+110h+var_C0], rax
0x18001a7e7  lea     rax, [rbp+57h+var_38]
0x18001a7eb  mov     [rsp+110h+var_C8], rax
0x18001a7f0  lea     rax, [rbp+57h+var_70]
0x18001a7f4  mov     [rsp+110h+var_D0], rax
0x18001a7f9  lea     rax, [rbp+57h+var_30]
0x18001a7fd  mov     [rsp+110h+var_D8], rax
0x18001a802  lea     rax, [rbp+57h+var_6C]
0x18001a806  mov     [rsp+110h+var_E0], rax
0x18001a80b  lea     rax, [rbp+57h+var_28]
0x18001a80f  mov     [rsp+110h+var_E8], rax
0x18001a814  lea     rax, [rbp+57h+var_20]
0x18001a818  mov     [rbp+57h+var_68], rcx
0x18001a81c  mov     rcx, r9
0x18001a81f  mov     [rsp+110h+var_F0], rax
0x18001a824  mov     [rbp+57h+var_28], 1000000h
0x18001a82c  mov     [rbp+57h+var_20], 1000800h
0x18001a834  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a839  jmp     short loc_18001A8B2
0x18001a83b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a840  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a845  mov     rdi, rax
0x18001a848  mov     ecx, [rax]
0x18001a84a  cmp     ecx, 5
0x18001a84d  jbe     short loc_18001A8B2
0x18001a84f  mov     rdx, 200000000000h
0x18001a859  mov     rcx, rax
0x18001a85c  call    _tlgKeywordOn
0x18001a861  test    al, al
0x18001a863  jz      short loc_18001A8B2
0x18001a865  call    cs:__imp_GetCurrentThreadId
0x18001a86b  mov     r8, [rbx+110h]
0x18001a872  lea     rdx, byte_18002A20D
0x18001a879  mov     [rbp+57h+arg_0], eax
0x18001a87c  mov     rcx, rdi
0x18001a87f  mov     eax, [r8+48h]
0x18001a883  add     r8, 8
0x18001a887  mov     [rbp+57h+arg_8], eax
0x18001a88a  lea     rax, [rbp+57h+arg_0]
0x18001a88e  mov     [rsp+110h+var_E0], rax
0x18001a893  lea     rax, [rbp+57h+arg_8]
0x18001a897  mov     [rsp+110h+var_E8], rax
0x18001a89c  lea     rax, [rbp+57h+arg_10]
0x18001a8a0  mov     [rsp+110h+var_F0], rax
0x18001a8a5  mov     [rbp+57h+arg_10], 1000800h
0x18001a8ad  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a8b2  mov     rcx, rbx
0x18001a8b5  add     rsp, 100h
0x18001a8bc  pop     rdi
0x18001a8bd  pop     rbx
0x18001a8be  pop     rbp
0x18001a8bf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
