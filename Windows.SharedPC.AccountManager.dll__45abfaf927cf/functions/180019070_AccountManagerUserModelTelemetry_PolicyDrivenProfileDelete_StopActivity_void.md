# AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StopActivity(void)

- ea: `0x180019070`
- end: `0x180019297`
- name: `?StopActivity@PolicyDrivenProfileDelete@AccountManagerUserModelTelemetry@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000ed9c`
- `0x18001790c`
- `0x180019070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019235`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019235`

## pseudocode

```c
void __fastcall AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StopActivity(
        AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = AccountManagerUserModelTelemetry::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v9;
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)word_18002D852,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = AccountManagerUserModelTelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002D469,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180019070  push    rbp
0x180019072  push    rbx
0x180019073  push    rdi
0x180019074  lea     rbp, [rsp-47h]
0x180019079  sub     rsp, 100h
0x180019080  mov     rdi, [rcx+110h]
0x180019087  mov     rbx, rcx
0x18001908a  mov     eax, [rdi+48h]
0x18001908d  test    eax, eax
0x18001908f  jns     loc_18001920B
0x180019095  add     rdi, 50h ; 'P'
0x180019099  cmp     eax, [rdi+8]
0x18001909c  jnz     loc_18001920B
0x1800190a2  test    rdi, rdi
0x1800190a5  jz      loc_18001920B
0x1800190ab  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800190b0  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x1800190b5  mov     r9, rax
0x1800190b8  mov     ecx, [rax]
0x1800190ba  cmp     ecx, 5
0x1800190bd  jbe     loc_180019285
0x1800190c3  mov     rdx, 200000000000h
0x1800190cd  mov     rcx, rax
0x1800190d0  call    _tlgKeywordOn
0x1800190d5  test    al, al
0x1800190d7  jz      loc_180019285
0x1800190dd  mov     rax, [rdi+70h]
0x1800190e1  lea     rdx, word_18002D852
0x1800190e8  mov     rcx, [rdi+78h]
0x1800190ec  mov     r8, [rbx+110h]
0x1800190f3  mov     [rbp+57h+var_60], rax
0x1800190f7  add     r8, 8
0x1800190fb  mov     eax, [rdi+68h]
0x1800190fe  mov     [rbp+57h+arg_0], eax
0x180019101  mov     rax, [rdi+60h]
0x180019105  mov     [rbp+57h+var_58], rax
0x180019109  mov     rax, [rdi+58h]
0x18001910d  mov     [rbp+57h+var_50], rax
0x180019111  mov     eax, [rdi+50h]
0x180019114  mov     [rbp+57h+arg_8], eax
0x180019117  mov     rax, [rdi+48h]
0x18001911b  mov     [rbp+57h+var_48], rax
0x18001911f  mov     eax, [rdi+20h]
0x180019122  mov     dword ptr [rbp+57h+arg_10], eax
0x180019125  mov     rax, [rdi+18h]
0x180019129  mov     [rbp+57h+var_40], rax
0x18001912d  mov     eax, [rdi]
0x18001912f  mov     [rbp+57h+arg_18], eax
0x180019132  mov     rax, [rdi+80h]
0x180019139  mov     [rbp+57h+var_38], rax
0x18001913d  mov     eax, [rdi+40h]
0x180019140  mov     [rbp+57h+var_70], eax
0x180019143  mov     rax, [rdi+38h]
0x180019147  mov     [rbp+57h+var_30], rax
0x18001914b  mov     eax, [rdi+8]
0x18001914e  mov     [rbp+57h+var_6C], eax
0x180019151  lea     rax, [rbp+57h+var_68]
0x180019155  mov     [rsp+110h+var_78], rax
0x18001915d  lea     rax, [rbp+57h+var_60]
0x180019161  mov     [rsp+110h+var_80], rax
0x180019169  lea     rax, [rbp+57h+arg_0]
0x18001916d  mov     [rsp+110h+var_88], rax
0x180019175  lea     rax, [rbp+57h+var_58]
0x180019179  mov     [rsp+110h+var_90], rax
0x180019181  lea     rax, [rbp+57h+var_50]
0x180019185  mov     [rsp+110h+var_98], rax
0x18001918a  lea     rax, [rbp+57h+arg_8]
0x18001918e  mov     [rsp+110h+var_A0], rax
0x180019193  lea     rax, [rbp+57h+var_48]
0x180019197  mov     [rsp+110h+var_A8], rax
0x18001919c  lea     rax, [rbp+57h+arg_10]
0x1800191a0  mov     [rsp+110h+var_B0], rax
0x1800191a5  lea     rax, [rbp+57h+var_40]
0x1800191a9  mov     [rsp+110h+var_B8], rax
0x1800191ae  lea     rax, [rbp+57h+arg_18]
0x1800191b2  mov     [rsp+110h+var_C0], rax
0x1800191b7  lea     rax, [rbp+57h+var_38]
0x1800191bb  mov     [rsp+110h+var_C8], rax
0x1800191c0  lea     rax, [rbp+57h+var_70]
0x1800191c4  mov     [rsp+110h+var_D0], rax
0x1800191c9  lea     rax, [rbp+57h+var_30]
0x1800191cd  mov     [rsp+110h+var_D8], rax
0x1800191d2  lea     rax, [rbp+57h+var_6C]
0x1800191d6  mov     [rsp+110h+var_E0], rax
0x1800191db  lea     rax, [rbp+57h+var_28]
0x1800191df  mov     [rsp+110h+var_E8], rax
0x1800191e4  lea     rax, [rbp+57h+var_20]
0x1800191e8  mov     [rbp+57h+var_68], rcx
0x1800191ec  mov     rcx, r9
0x1800191ef  mov     [rsp+110h+var_F0], rax
0x1800191f4  mov     [rbp+57h+var_28], 1000000h
0x1800191fc  mov     [rbp+57h+var_20], 0
0x180019204  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019209  jmp     short loc_180019285
0x18001920b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019210  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x180019215  mov     rdi, rax
0x180019218  mov     ecx, [rax]
0x18001921a  cmp     ecx, 5
0x18001921d  jbe     short loc_180019285
0x18001921f  mov     rdx, 200000000000h
0x180019229  mov     rcx, rax
0x18001922c  call    _tlgKeywordOn
0x180019231  test    al, al
0x180019233  jz      short loc_180019285
0x180019235  call    cs:__imp_GetCurrentThreadId
0x18001923b  mov     r8, [rbx+110h]
0x180019242  lea     rdx, byte_18002D469
0x180019249  mov     [rbp+57h+arg_0], eax
0x18001924c  xor     r9d, r9d
0x18001924f  mov     rcx, rdi
0x180019252  mov     eax, [r8+48h]
0x180019256  add     r8, 8
0x18001925a  mov     [rbp+57h+arg_8], eax
0x18001925d  lea     rax, [rbp+57h+arg_0]
0x180019261  mov     [rsp+110h+var_E0], rax
0x180019266  lea     rax, [rbp+57h+arg_8]
0x18001926a  mov     [rsp+110h+var_E8], rax
0x18001926f  lea     rax, [rbp+57h+arg_10]
0x180019273  mov     [rsp+110h+var_F0], rax
0x180019278  mov     [rbp+57h+arg_10], 0
0x180019280  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019285  mov     rcx, rbx
0x180019288  add     rsp, 100h
0x18001928f  pop     rdi
0x180019290  pop     rbx
0x180019291  pop     rbp
0x180019292  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
