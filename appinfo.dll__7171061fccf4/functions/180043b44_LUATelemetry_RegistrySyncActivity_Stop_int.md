# LUATelemetry::RegistrySyncActivity::Stop(int)

- ea: `0x180043b44`
- end: `0x180043d94`
- name: `?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `592`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800432a0`

## callees

- `0x180003ca4`
- `0x180003f68`
- `0x18000f168`
- `0x180011fd0`
- `0x18001b23c`
- `0x18001b31c`
- `0x180043b44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043d24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043d24`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::Stop(LUATelemetry::RegistrySyncActivity *this, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  int v17; // [rsp+B8h] [rbp-78h] BYREF
  int v18; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-70h] BYREF
  const wchar_t *v20; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+D0h] [rbp-60h] BYREF
  const wchar_t *v22; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v24; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v25; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v27; // [rsp+100h] [rbp-30h] BYREF
  __int64 v28[3]; // [rsp+108h] [rbp-28h] BYREF
  int v29; // [rsp+130h] [rbp+0h] BYREF
  DWORD v30; // [rsp+140h] [rbp+10h] BYREF
  int v31; // [rsp+148h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LUATelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)this + 34);
      v20 = (const wchar_t *)*((_QWORD *)v6 + 15);
      v21 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v30 = v6[26];
      v22 = (const wchar_t *)*((_QWORD *)v6 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v31 = v6[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v15 = v6[8];
      v25 = (const wchar_t *)*((_QWORD *)v6 + 3);
      v16 = *v6;
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v17 = v6[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v18 = v6[2];
      v29 = a2;
      v28[0] = 0x1000000;
      v19 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)&word_180057786,
        v9 + 8,
        v8,
        (__int64)&v19,
        (__int64)v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20,
        (__int64)&v29);
    }
  }
  else
  {
    wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = LUATelemetry::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
    {
      v29 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v19 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (__int64)&dword_1800579EC,
        v13 + 8,
        v14,
        (__int64)&v19,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180043b44  mov     [rsp-8+arg_8], rbx
0x180043b49  push    rbp
0x180043b4a  push    rsi
0x180043b4b  push    rdi
0x180043b4c  lea     rbp, [rsp+20h]
0x180043b51  sub     rsp, 110h
0x180043b58  mov     rdi, [rcx+110h]
0x180043b5f  mov     esi, edx
0x180043b61  mov     rbx, rcx
0x180043b64  mov     eax, [rdi+48h]
0x180043b67  test    eax, eax
0x180043b69  jns     loc_180043CF7
0x180043b6f  add     rdi, 50h ; 'P'
0x180043b73  cmp     eax, [rdi+8]
0x180043b76  jnz     loc_180043CF7
0x180043b7c  test    rdi, rdi
0x180043b7f  jz      loc_180043CF7
0x180043b85  call    ?zInternalStop@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180043b8a  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180043b8f  mov     r9, rax
0x180043b92  mov     ecx, [rax]
0x180043b94  cmp     ecx, 5
0x180043b97  jbe     loc_180043D7A
0x180043b9d  mov     rdx, 400000000000h
0x180043ba7  mov     rcx, rax
0x180043baa  call    _tlgKeywordOn
0x180043baf  test    al, al
0x180043bb1  jz      loc_180043D7A
0x180043bb7  mov     rax, [rdi+78h]
0x180043bbb  lea     rdx, word_180057786
0x180043bc2  mov     r8, [rbx+110h]
0x180043bc9  mov     rcx, r9
0x180043bcc  mov     [rbp-10h+var_58], rax
0x180043bd0  add     r8, 8
0x180043bd4  mov     rax, [rdi+70h]
0x180043bd8  mov     [rbp-10h+var_50], rax
0x180043bdc  mov     eax, [rdi+68h]
0x180043bdf  mov     [rbp-10h+arg_10], eax
0x180043be2  mov     rax, [rdi+60h]
0x180043be6  mov     [rbp-10h+var_48], rax
0x180043bea  mov     rax, [rdi+58h]
0x180043bee  mov     [rbp-10h+var_40], rax
0x180043bf2  mov     eax, [rdi+50h]
0x180043bf5  mov     [rbp-10h+arg_18], eax
0x180043bf8  mov     rax, [rdi+48h]
0x180043bfc  mov     [rbp-10h+var_38], rax
0x180043c00  mov     eax, [rdi+20h]
0x180043c03  mov     [rbp-10h+var_70], eax
0x180043c06  mov     rax, [rdi+18h]
0x180043c0a  mov     [rbp-10h+var_30], rax
0x180043c0e  mov     eax, [rdi]
0x180043c10  mov     [rbp-10h+var_6C], eax
0x180043c13  mov     rax, [rdi+80h]
0x180043c1a  mov     [rbp-10h+var_28], rax
0x180043c1e  mov     eax, [rdi+40h]
0x180043c21  mov     [rbp-10h+var_68], eax
0x180043c24  mov     rax, [rdi+38h]
0x180043c28  mov     [rbp-10h+var_20], rax
0x180043c2c  mov     eax, [rdi+8]
0x180043c2f  mov     [rbp-10h+var_64], eax
0x180043c32  lea     rax, [rbp-10h+arg_0]
0x180043c36  mov     [rsp+120h+var_80], rax
0x180043c3e  lea     rax, [rbp-10h+var_58]
0x180043c42  mov     [rsp+120h+var_88], rax
0x180043c4a  lea     rax, [rbp-10h+var_50]
0x180043c4e  mov     [rsp+120h+var_90], rax
0x180043c56  lea     rax, [rbp-10h+arg_10]
0x180043c5a  mov     [rsp+120h+var_98], rax
0x180043c62  lea     rax, [rbp-10h+var_48]
0x180043c66  mov     [rsp+120h+var_A0], rax
0x180043c6e  lea     rax, [rbp-10h+var_40]
0x180043c72  mov     [rsp+120h+var_A8], rax
0x180043c77  lea     rax, [rbp-10h+arg_18]
0x180043c7b  mov     [rsp+120h+var_B0], rax
0x180043c80  lea     rax, [rbp-10h+var_38]
0x180043c84  mov     [rsp+120h+var_B8], rax
0x180043c89  lea     rax, [rbp-10h+var_70]
0x180043c8d  mov     [rsp+120h+var_C0], rax
0x180043c92  lea     rax, [rbp-10h+var_30]
0x180043c96  mov     [rsp+120h+var_C8], rax
0x180043c9b  lea     rax, [rbp-10h+var_6C]
0x180043c9f  mov     [rsp+120h+var_D0], rax
0x180043ca4  lea     rax, [rbp-10h+var_28]
0x180043ca8  mov     [rsp+120h+var_D8], rax
0x180043cad  lea     rax, [rbp-10h+var_68]
0x180043cb1  mov     [rsp+120h+var_E0], rax
0x180043cb6  lea     rax, [rbp-10h+var_20]
0x180043cba  mov     [rsp+120h+var_E8], rax
0x180043cbf  lea     rax, [rbp-10h+var_64]
0x180043cc3  mov     [rsp+120h+var_F0], rax
0x180043cc8  lea     rax, [rbp-10h+var_18]
0x180043ccc  mov     [rsp+120h+var_F8], rax
0x180043cd1  lea     rax, [rbp-10h+var_60]
0x180043cd5  mov     [rsp+120h+var_100], rax
0x180043cda  mov     [rbp-10h+arg_0], esi
0x180043cdd  mov     [rbp-10h+var_18], 1000000h
0x180043ce5  mov     [rbp-10h+var_60], 3000000h
0x180043ced  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180043cf2  jmp     loc_180043D7A
0x180043cf7  call    ?zInternalStop@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180043cfc  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180043d01  mov     rdi, rax
0x180043d04  mov     ecx, [rax]
0x180043d06  cmp     ecx, 5
0x180043d09  jbe     short loc_180043D7A
0x180043d0b  mov     rdx, 400000000000h
0x180043d15  mov     rcx, rax
0x180043d18  call    _tlgKeywordOn
0x180043d1d  test    al, al
0x180043d1f  jz      short loc_180043D7A
0x180043d21  mov     [rbp-10h+arg_0], esi
0x180043d24  call    cs:__imp_GetCurrentThreadId
0x180043d2a  mov     r8, [rbx+110h]
0x180043d31  lea     rdx, dword_1800579EC
0x180043d38  mov     [rbp-10h+arg_10], eax
0x180043d3b  mov     rcx, rdi
0x180043d3e  mov     eax, [r8+48h]
0x180043d42  add     r8, 8
0x180043d46  mov     [rbp-10h+arg_18], eax
0x180043d49  lea     rax, [rbp-10h+arg_0]
0x180043d4d  mov     [rsp+120h+var_E8], rax
0x180043d52  lea     rax, [rbp-10h+arg_10]
0x180043d56  mov     [rsp+120h+var_F0], rax
0x180043d5b  lea     rax, [rbp-10h+arg_18]
0x180043d5f  mov     [rsp+120h+var_F8], rax
0x180043d64  lea     rax, [rbp-10h+var_60]
0x180043d68  mov     [rsp+120h+var_100], rax
0x180043d6d  mov     [rbp-10h+var_60], 3000000h
0x180043d75  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180043d7a  mov     rcx, rbx
0x180043d7d  mov     rbx, [rsp+120h+arg_8]
0x180043d85  add     rsp, 110h
0x180043d8c  pop     rdi
0x180043d8d  pop     rsi
0x180043d8e  pop     rbp
0x180043d8f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
