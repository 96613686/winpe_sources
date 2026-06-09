# CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StopActivity(void)

- ea: `0x18001a470`
- end: `0x18001a694`
- name: `?StopActivity@SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180015bf0`
- `0x180016fcc`
- `0x18001a470`
- `0x18001f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a635`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StopActivity(
        CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *this)
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
        (__int64)&word_18002A746,
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
        (__int64)&unk_18002A880,
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
0x18001a470  push    rbp
0x18001a472  push    rbx
0x18001a473  push    rdi
0x18001a474  lea     rbp, [rsp-47h]
0x18001a479  sub     rsp, 100h
0x18001a480  mov     rdi, [rcx+110h]
0x18001a487  mov     rbx, rcx
0x18001a48a  mov     eax, [rdi+48h]
0x18001a48d  test    eax, eax
0x18001a48f  jns     loc_18001A60B
0x18001a495  add     rdi, 50h ; 'P'
0x18001a499  cmp     eax, [rdi+8]
0x18001a49c  jnz     loc_18001A60B
0x18001a4a2  test    rdi, rdi
0x18001a4a5  jz      loc_18001A60B
0x18001a4ab  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a4b0  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a4b5  mov     r9, rax
0x18001a4b8  mov     ecx, [rax]
0x18001a4ba  cmp     ecx, 5
0x18001a4bd  jbe     loc_18001A682
0x18001a4c3  mov     rdx, 200000000000h
0x18001a4cd  mov     rcx, rax
0x18001a4d0  call    _tlgKeywordOn
0x18001a4d5  test    al, al
0x18001a4d7  jz      loc_18001A682
0x18001a4dd  mov     rax, [rdi+70h]
0x18001a4e1  lea     rdx, word_18002A746
0x18001a4e8  mov     rcx, [rdi+78h]
0x18001a4ec  mov     r8, [rbx+110h]
0x18001a4f3  mov     [rbp+57h+var_60], rax
0x18001a4f7  add     r8, 8
0x18001a4fb  mov     eax, [rdi+68h]
0x18001a4fe  mov     [rbp+57h+arg_0], eax
0x18001a501  mov     rax, [rdi+60h]
0x18001a505  mov     [rbp+57h+var_58], rax
0x18001a509  mov     rax, [rdi+58h]
0x18001a50d  mov     [rbp+57h+var_50], rax
0x18001a511  mov     eax, [rdi+50h]
0x18001a514  mov     [rbp+57h+arg_8], eax
0x18001a517  mov     rax, [rdi+48h]
0x18001a51b  mov     [rbp+57h+var_48], rax
0x18001a51f  mov     eax, [rdi+20h]
0x18001a522  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a525  mov     rax, [rdi+18h]
0x18001a529  mov     [rbp+57h+var_40], rax
0x18001a52d  mov     eax, [rdi]
0x18001a52f  mov     [rbp+57h+arg_18], eax
0x18001a532  mov     rax, [rdi+80h]
0x18001a539  mov     [rbp+57h+var_38], rax
0x18001a53d  mov     eax, [rdi+40h]
0x18001a540  mov     [rbp+57h+var_70], eax
0x18001a543  mov     rax, [rdi+38h]
0x18001a547  mov     [rbp+57h+var_30], rax
0x18001a54b  mov     eax, [rdi+8]
0x18001a54e  mov     [rbp+57h+var_6C], eax
0x18001a551  lea     rax, [rbp+57h+var_68]
0x18001a555  mov     [rsp+110h+var_78], rax
0x18001a55d  lea     rax, [rbp+57h+var_60]
0x18001a561  mov     [rsp+110h+var_80], rax
0x18001a569  lea     rax, [rbp+57h+arg_0]
0x18001a56d  mov     [rsp+110h+var_88], rax
0x18001a575  lea     rax, [rbp+57h+var_58]
0x18001a579  mov     [rsp+110h+var_90], rax
0x18001a581  lea     rax, [rbp+57h+var_50]
0x18001a585  mov     [rsp+110h+var_98], rax
0x18001a58a  lea     rax, [rbp+57h+arg_8]
0x18001a58e  mov     [rsp+110h+var_A0], rax
0x18001a593  lea     rax, [rbp+57h+var_48]
0x18001a597  mov     [rsp+110h+var_A8], rax
0x18001a59c  lea     rax, [rbp+57h+arg_10]
0x18001a5a0  mov     [rsp+110h+var_B0], rax
0x18001a5a5  lea     rax, [rbp+57h+var_40]
0x18001a5a9  mov     [rsp+110h+var_B8], rax
0x18001a5ae  lea     rax, [rbp+57h+arg_18]
0x18001a5b2  mov     [rsp+110h+var_C0], rax
0x18001a5b7  lea     rax, [rbp+57h+var_38]
0x18001a5bb  mov     [rsp+110h+var_C8], rax
0x18001a5c0  lea     rax, [rbp+57h+var_70]
0x18001a5c4  mov     [rsp+110h+var_D0], rax
0x18001a5c9  lea     rax, [rbp+57h+var_30]
0x18001a5cd  mov     [rsp+110h+var_D8], rax
0x18001a5d2  lea     rax, [rbp+57h+var_6C]
0x18001a5d6  mov     [rsp+110h+var_E0], rax
0x18001a5db  lea     rax, [rbp+57h+var_28]
0x18001a5df  mov     [rsp+110h+var_E8], rax
0x18001a5e4  lea     rax, [rbp+57h+var_20]
0x18001a5e8  mov     [rbp+57h+var_68], rcx
0x18001a5ec  mov     rcx, r9
0x18001a5ef  mov     [rsp+110h+var_F0], rax
0x18001a5f4  mov     [rbp+57h+var_28], 1000000h
0x18001a5fc  mov     [rbp+57h+var_20], 1000800h
0x18001a604  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a609  jmp     short loc_18001A682
0x18001a60b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a610  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001a615  mov     rdi, rax
0x18001a618  mov     ecx, [rax]
0x18001a61a  cmp     ecx, 5
0x18001a61d  jbe     short loc_18001A682
0x18001a61f  mov     rdx, 200000000000h
0x18001a629  mov     rcx, rax
0x18001a62c  call    _tlgKeywordOn
0x18001a631  test    al, al
0x18001a633  jz      short loc_18001A682
0x18001a635  call    cs:__imp_GetCurrentThreadId
0x18001a63b  mov     r8, [rbx+110h]
0x18001a642  lea     rdx, unk_18002A880
0x18001a649  mov     [rbp+57h+arg_0], eax
0x18001a64c  mov     rcx, rdi
0x18001a64f  mov     eax, [r8+48h]
0x18001a653  add     r8, 8
0x18001a657  mov     [rbp+57h+arg_8], eax
0x18001a65a  lea     rax, [rbp+57h+arg_0]
0x18001a65e  mov     [rsp+110h+var_E0], rax
0x18001a663  lea     rax, [rbp+57h+arg_8]
0x18001a667  mov     [rsp+110h+var_E8], rax
0x18001a66c  lea     rax, [rbp+57h+arg_10]
0x18001a670  mov     [rsp+110h+var_F0], rax
0x18001a675  mov     [rbp+57h+arg_10], 1000800h
0x18001a67d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a682  mov     rcx, rbx
0x18001a685  add     rsp, 100h
0x18001a68c  pop     rdi
0x18001a68d  pop     rbx
0x18001a68e  pop     rbp
0x18001a68f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
