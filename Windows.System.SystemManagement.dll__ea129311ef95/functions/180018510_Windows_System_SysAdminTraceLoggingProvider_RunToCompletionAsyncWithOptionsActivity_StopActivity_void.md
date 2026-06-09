# Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StopActivity(void)

- ea: `0x180018510`
- end: `0x180018734`
- name: `?StopActivity@RunToCompletionAsyncWithOptionsActivity@SysAdminTraceLoggingProvider@System@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800010f8`
- `0x180001730`
- `0x180001ebc`
- `0x18000df18`
- `0x18000e62c`
- `0x18000fe68`
- `0x180018510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186d5`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StopActivity(
        Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *this)
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
        (__int64)&unk_180039E68,
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
        (__int64)&unk_180039E00,
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
0x180018510  push    rbp
0x180018512  push    rbx
0x180018513  push    rdi
0x180018514  lea     rbp, [rsp-47h]
0x180018519  sub     rsp, 100h
0x180018520  mov     rdi, [rcx+110h]
0x180018527  mov     rbx, rcx
0x18001852a  mov     eax, [rdi+48h]
0x18001852d  test    eax, eax
0x18001852f  jns     loc_1800186AB
0x180018535  add     rdi, 50h ; 'P'
0x180018539  cmp     eax, [rdi+8]
0x18001853c  jnz     loc_1800186AB
0x180018542  test    rdi, rdi
0x180018545  jz      loc_1800186AB
0x18001854b  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018550  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180018555  mov     r9, rax
0x180018558  mov     ecx, [rax]
0x18001855a  cmp     ecx, 5
0x18001855d  jbe     loc_180018722
0x180018563  mov     rdx, 200000000000h
0x18001856d  mov     rcx, rax
0x180018570  call    _tlgKeywordOn
0x180018575  test    al, al
0x180018577  jz      loc_180018722
0x18001857d  mov     rax, [rdi+70h]
0x180018581  lea     rdx, unk_180039E68
0x180018588  mov     rcx, [rdi+78h]
0x18001858c  mov     r8, [rbx+110h]
0x180018593  mov     [rbp+57h+var_60], rax
0x180018597  add     r8, 8
0x18001859b  mov     eax, [rdi+68h]
0x18001859e  mov     [rbp+57h+arg_0], eax
0x1800185a1  mov     rax, [rdi+60h]
0x1800185a5  mov     [rbp+57h+var_58], rax
0x1800185a9  mov     rax, [rdi+58h]
0x1800185ad  mov     [rbp+57h+var_50], rax
0x1800185b1  mov     eax, [rdi+50h]
0x1800185b4  mov     [rbp+57h+arg_8], eax
0x1800185b7  mov     rax, [rdi+48h]
0x1800185bb  mov     [rbp+57h+var_48], rax
0x1800185bf  mov     eax, [rdi+20h]
0x1800185c2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800185c5  mov     rax, [rdi+18h]
0x1800185c9  mov     [rbp+57h+var_40], rax
0x1800185cd  mov     eax, [rdi]
0x1800185cf  mov     [rbp+57h+arg_18], eax
0x1800185d2  mov     rax, [rdi+80h]
0x1800185d9  mov     [rbp+57h+var_38], rax
0x1800185dd  mov     eax, [rdi+40h]
0x1800185e0  mov     [rbp+57h+var_70], eax
0x1800185e3  mov     rax, [rdi+38h]
0x1800185e7  mov     [rbp+57h+var_30], rax
0x1800185eb  mov     eax, [rdi+8]
0x1800185ee  mov     [rbp+57h+var_6C], eax
0x1800185f1  lea     rax, [rbp+57h+var_68]
0x1800185f5  mov     [rsp+110h+var_78], rax
0x1800185fd  lea     rax, [rbp+57h+var_60]
0x180018601  mov     [rsp+110h+var_80], rax
0x180018609  lea     rax, [rbp+57h+arg_0]
0x18001860d  mov     [rsp+110h+var_88], rax
0x180018615  lea     rax, [rbp+57h+var_58]
0x180018619  mov     [rsp+110h+var_90], rax
0x180018621  lea     rax, [rbp+57h+var_50]
0x180018625  mov     [rsp+110h+var_98], rax
0x18001862a  lea     rax, [rbp+57h+arg_8]
0x18001862e  mov     [rsp+110h+var_A0], rax
0x180018633  lea     rax, [rbp+57h+var_48]
0x180018637  mov     [rsp+110h+var_A8], rax
0x18001863c  lea     rax, [rbp+57h+arg_10]
0x180018640  mov     [rsp+110h+var_B0], rax
0x180018645  lea     rax, [rbp+57h+var_40]
0x180018649  mov     [rsp+110h+var_B8], rax
0x18001864e  lea     rax, [rbp+57h+arg_18]
0x180018652  mov     [rsp+110h+var_C0], rax
0x180018657  lea     rax, [rbp+57h+var_38]
0x18001865b  mov     [rsp+110h+var_C8], rax
0x180018660  lea     rax, [rbp+57h+var_70]
0x180018664  mov     [rsp+110h+var_D0], rax
0x180018669  lea     rax, [rbp+57h+var_30]
0x18001866d  mov     [rsp+110h+var_D8], rax
0x180018672  lea     rax, [rbp+57h+var_6C]
0x180018676  mov     [rsp+110h+var_E0], rax
0x18001867b  lea     rax, [rbp+57h+var_28]
0x18001867f  mov     [rsp+110h+var_E8], rax
0x180018684  lea     rax, [rbp+57h+var_20]
0x180018688  mov     [rbp+57h+var_68], rcx
0x18001868c  mov     rcx, r9
0x18001868f  mov     [rsp+110h+var_F0], rax
0x180018694  mov     [rbp+57h+var_28], 1000000h
0x18001869c  mov     [rbp+57h+var_20], 0
0x1800186a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800186a9  jmp     short loc_180018722
0x1800186ab  call    ?zInternalStop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800186b0  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x1800186b5  mov     rdi, rax
0x1800186b8  mov     ecx, [rax]
0x1800186ba  cmp     ecx, 5
0x1800186bd  jbe     short loc_180018722
0x1800186bf  mov     rdx, 200000000000h
0x1800186c9  mov     rcx, rax
0x1800186cc  call    _tlgKeywordOn
0x1800186d1  test    al, al
0x1800186d3  jz      short loc_180018722
0x1800186d5  call    cs:__imp_GetCurrentThreadId
0x1800186db  mov     r8, [rbx+110h]
0x1800186e2  lea     rdx, unk_180039E00
0x1800186e9  mov     [rbp+57h+arg_0], eax
0x1800186ec  mov     rcx, rdi
0x1800186ef  mov     eax, [r8+48h]
0x1800186f3  add     r8, 8
0x1800186f7  mov     [rbp+57h+arg_8], eax
0x1800186fa  lea     rax, [rbp+57h+arg_0]
0x1800186fe  mov     [rsp+110h+var_E0], rax
0x180018703  lea     rax, [rbp+57h+arg_8]
0x180018707  mov     [rsp+110h+var_E8], rax
0x18001870c  lea     rax, [rbp+57h+arg_10]
0x180018710  mov     [rsp+110h+var_F0], rax
0x180018715  mov     [rbp+57h+arg_10], 0
0x18001871d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018722  mov     rcx, rbx
0x180018725  add     rsp, 100h
0x18001872c  pop     rdi
0x18001872d  pop     rbx
0x18001872e  pop     rbp
0x18001872f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
