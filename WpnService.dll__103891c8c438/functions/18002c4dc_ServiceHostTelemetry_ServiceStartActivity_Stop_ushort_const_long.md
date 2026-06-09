# ServiceHostTelemetry::ServiceStartActivity::Stop(ushort const *,long)

- ea: `0x18002c4dc`
- end: `0x18002c756`
- name: `?Stop@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z`
- size: `634`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002c188`

## callees

- `0x1800023d8`
- `0x1800026d4`
- `0x18000f270`
- `0x180016b74`
- `0x1800172bc`
- `0x180018430`
- `0x18002c4dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6d7`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::Stop(
        ServiceHostTelemetry::ServiceStartActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  int v22; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v30; // [rsp+100h] [rbp-30h] BYREF
  __int64 v31; // [rsp+108h] [rbp-28h] BYREF
  __int64 v32; // [rsp+110h] [rbp-20h] BYREF
  __int64 v33; // [rsp+118h] [rbp-18h] BYREF
  DWORD v34; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = ServiceHostLogging::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8, v7) )
    {
      v26 = *((_QWORD *)v6 + 15);
      v27 = *((_QWORD *)v6 + 14);
      v10 = *((_QWORD *)this + 34);
      v34 = v6[26];
      v28 = *((_QWORD *)v6 + 12);
      v29 = *((_QWORD *)v6 + 11);
      v19 = v6[20];
      v30 = *((_QWORD *)v6 + 9);
      v20 = v6[8];
      v31 = *((_QWORD *)v6 + 3);
      v21 = *v6;
      v32 = *((_QWORD *)v6 + 16);
      v22 = v6[16];
      v33 = *((_QWORD *)v6 + 7);
      v18 = v6[2];
      v23 = 0x1000000;
      v24 = 0x1000000;
      v25 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&unk_18003D4A0,
        v10 + 8,
        v9,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v18,
        &v33,
        (__int64)&v22,
        &v32,
        (__int64)&v21,
        &v31,
        (__int64)&v20,
        &v30,
        (__int64)&v19,
        &v29,
        &v28,
        (__int64)&v34,
        &v27,
        &v26,
        &v25);
    }
  }
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = ServiceHostLogging::Provider();
    v14 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12, v13) )
    {
      v24 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v34 = CurrentThreadId;
      v18 = *(_DWORD *)(v16 + 72);
      v23 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)word_18003D43A,
        v16 + 8,
        v17,
        (__int64)&v23,
        (__int64)&v18,
        (__int64)&v34,
        &v24);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002c4dc  mov     [rsp-8+arg_8], rbx
0x18002c4e1  mov     [rsp-8+arg_10], rsi
0x18002c4e6  push    rbp
0x18002c4e7  push    rdi
0x18002c4e8  push    r14
0x18002c4ea  lea     rbp, [rsp+10h]
0x18002c4ef  sub     rsp, 120h
0x18002c4f6  mov     rdi, [rcx+110h]
0x18002c4fd  mov     esi, r8d
0x18002c500  mov     r14, rdx
0x18002c503  mov     rbx, rcx
0x18002c506  mov     eax, [rdi+48h]
0x18002c509  test    eax, eax
0x18002c50b  jns     loc_18002C6A6
0x18002c511  add     rdi, 50h ; 'P'
0x18002c515  cmp     eax, [rdi+8]
0x18002c518  jnz     loc_18002C6A6
0x18002c51e  test    rdi, rdi
0x18002c521  jz      loc_18002C6A6
0x18002c527  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002c52c  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c531  mov     r9, rax
0x18002c534  mov     ecx, [rax]
0x18002c536  cmp     ecx, 5
0x18002c539  jbe     loc_18002C737
0x18002c53f  mov     rdx, 400000000000h
0x18002c549  mov     rcx, rax
0x18002c54c  call    _tlgKeywordOn
0x18002c551  test    al, al
0x18002c553  jz      loc_18002C737
0x18002c559  mov     rax, [rdi+78h]
0x18002c55d  lea     rdx, unk_18003D4A0
0x18002c564  mov     [rbp+var_50], rax
0x18002c568  mov     rcx, r9
0x18002c56b  mov     rax, [rdi+70h]
0x18002c56f  mov     [rbp+var_48], rax
0x18002c573  mov     eax, [rdi+68h]
0x18002c576  mov     r8, [rbx+110h]
0x18002c57d  mov     [rbp+arg_18], eax
0x18002c580  add     r8, 8
0x18002c584  mov     rax, [rdi+60h]
0x18002c588  mov     [rbp+var_40], rax
0x18002c58c  mov     rax, [rdi+58h]
0x18002c590  mov     [rbp+var_38], rax
0x18002c594  mov     eax, [rdi+50h]
0x18002c597  mov     [rbp+var_7C], eax
0x18002c59a  mov     rax, [rdi+48h]
0x18002c59e  mov     [rbp+var_30], rax
0x18002c5a2  mov     eax, [rdi+20h]
0x18002c5a5  mov     [rbp+var_78], eax
0x18002c5a8  mov     rax, [rdi+18h]
0x18002c5ac  mov     [rbp+var_28], rax
0x18002c5b0  mov     eax, [rdi]
0x18002c5b2  mov     [rbp+var_74], eax
0x18002c5b5  mov     rax, [rdi+80h]
0x18002c5bc  mov     [rbp+var_20], rax
0x18002c5c0  mov     eax, [rdi+40h]
0x18002c5c3  mov     [rbp+var_70], eax
0x18002c5c6  mov     rax, [rdi+38h]
0x18002c5ca  mov     [rbp+var_18], rax
0x18002c5ce  mov     eax, [rdi+8]
0x18002c5d1  mov     [rbp+var_80], eax
0x18002c5d4  mov     eax, 1000000h
0x18002c5d9  mov     [rbp+var_68], rax
0x18002c5dd  mov     [rbp+var_60], rax
0x18002c5e1  lea     rax, [rbp+arg_0]
0x18002c5e5  mov     [rsp+130h+var_88], rax
0x18002c5ed  lea     rax, [rbp+var_58]
0x18002c5f1  mov     [rsp+130h+var_90], rax
0x18002c5f9  lea     rax, [rbp+var_50]
0x18002c5fd  mov     [rsp+130h+var_98], rax
0x18002c605  lea     rax, [rbp+var_48]
0x18002c609  mov     [rsp+130h+var_A0], rax
0x18002c611  lea     rax, [rbp+arg_18]
0x18002c615  mov     [rsp+130h+var_A8], rax
0x18002c61d  lea     rax, [rbp+var_40]
0x18002c621  mov     [rsp+130h+var_B0], rax
0x18002c629  lea     rax, [rbp+var_38]
0x18002c62d  mov     [rsp+130h+var_B8], rax
0x18002c632  lea     rax, [rbp+var_7C]
0x18002c636  mov     [rsp+130h+var_C0], rax
0x18002c63b  lea     rax, [rbp+var_30]
0x18002c63f  mov     [rsp+130h+var_C8], rax
0x18002c644  lea     rax, [rbp+var_78]
0x18002c648  mov     [rsp+130h+var_D0], rax
0x18002c64d  lea     rax, [rbp+var_28]
0x18002c651  mov     [rsp+130h+var_D8], rax
0x18002c656  lea     rax, [rbp+var_74]
0x18002c65a  mov     [rsp+130h+var_E0], rax
0x18002c65f  lea     rax, [rbp+var_20]
0x18002c663  mov     [rsp+130h+var_E8], rax
0x18002c668  lea     rax, [rbp+var_70]
0x18002c66c  mov     [rsp+130h+var_F0], rax
0x18002c671  lea     rax, [rbp+var_18]
0x18002c675  mov     [rsp+130h+var_F8], rax
0x18002c67a  lea     rax, [rbp+var_80]
0x18002c67e  mov     [rsp+130h+var_100], rax
0x18002c683  lea     rax, [rbp+var_68]
0x18002c687  mov     [rsp+130h+var_108], rax
0x18002c68c  lea     rax, [rbp+var_60]
0x18002c690  mov     [rsp+130h+var_110], rax
0x18002c695  mov     [rbp+arg_0], esi
0x18002c698  mov     [rbp+var_58], r14
0x18002c69c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002c6a1  jmp     loc_18002C737
0x18002c6a6  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002c6ab  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002c6b0  mov     rdi, rax
0x18002c6b3  mov     ecx, [rax]
0x18002c6b5  cmp     ecx, 5
0x18002c6b8  jbe     short loc_18002C737
0x18002c6ba  mov     rdx, 400000000000h
0x18002c6c4  mov     rcx, rax
0x18002c6c7  call    _tlgKeywordOn
0x18002c6cc  test    al, al
0x18002c6ce  jz      short loc_18002C737
0x18002c6d0  mov     [rbp+arg_0], esi
0x18002c6d3  mov     [rbp+var_60], r14
0x18002c6d7  call    cs:__imp_GetCurrentThreadId
0x18002c6dd  mov     r8, [rbx+110h]
0x18002c6e4  lea     rdx, word_18003D43A
0x18002c6eb  mov     [rbp+arg_18], eax
0x18002c6ee  mov     rcx, rdi
0x18002c6f1  mov     eax, [r8+48h]
0x18002c6f5  add     r8, 8
0x18002c6f9  mov     [rbp+var_80], eax
0x18002c6fc  mov     eax, 1000000h
0x18002c701  mov     [rbp+var_68], rax
0x18002c705  lea     rax, [rbp+arg_0]
0x18002c709  mov     [rsp+130h+var_F0], rax
0x18002c70e  lea     rax, [rbp+var_60]
0x18002c712  mov     [rsp+130h+var_F8], rax
0x18002c717  lea     rax, [rbp+arg_18]
0x18002c71b  mov     [rsp+130h+var_100], rax
0x18002c720  lea     rax, [rbp+var_80]
0x18002c724  mov     [rsp+130h+var_108], rax
0x18002c729  lea     rax, [rbp+var_68]
0x18002c72d  mov     [rsp+130h+var_110], rax
0x18002c732  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002c737  mov     rcx, rbx
0x18002c73a  lea     r11, [rsp+130h+var_10]
0x18002c742  mov     rbx, [r11+28h]
0x18002c746  mov     rsi, [r11+30h]
0x18002c74a  mov     rsp, r11
0x18002c74d  pop     r14
0x18002c74f  pop     rdi
0x18002c750  pop     rbp
0x18002c751  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
