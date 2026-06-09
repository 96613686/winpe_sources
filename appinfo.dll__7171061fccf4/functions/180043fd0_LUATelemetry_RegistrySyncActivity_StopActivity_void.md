# LUATelemetry::RegistrySyncActivity::StopActivity(void)

- ea: `0x180043fd0`
- end: `0x1800441f4`
- name: `?StopActivity@RegistrySyncActivity@LUATelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000be18`
- `0x18000f168`
- `0x180010658`
- `0x180011fd0`
- `0x18001b23c`
- `0x18001b31c`
- `0x180043fd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044195`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::StopActivity(LUATelemetry::RegistrySyncActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+A0h] [rbp-19h] BYREF
  int v15; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v16; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v18; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v19; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v20; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v21; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v22; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v23; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v24; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v25[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v26; // [rsp+120h] [rbp+67h] BYREF
  int v27; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+130h] [rbp+77h] BYREF
  int v29; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LUATelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v7 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v8 = *((_QWORD *)this + 34);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v26 = v4[26];
      v18 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v28) = v4[8];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v29 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v16 = v7;
      v24 = 0x1000000;
      v25[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned __int8 *)&unk_1800578C0,
        (const GUID *)(v8 + 8),
        v6,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v15,
        &v23,
        (__int64)&v14,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        &v18,
        (__int64)&v26,
        &v17,
        &v16);
    }
  }
  else
  {
    wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LUATelemetry::Provider();
    v10 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v12 + 72);
      v28 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned __int8 *)&word_1800573EE,
        (const GUID *)(v12 + 8),
        v13,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180043fd0  push    rbp
0x180043fd2  push    rbx
0x180043fd3  push    rdi
0x180043fd4  lea     rbp, [rsp-47h]
0x180043fd9  sub     rsp, 100h
0x180043fe0  mov     rdi, [rcx+110h]
0x180043fe7  mov     rbx, rcx
0x180043fea  mov     eax, [rdi+48h]
0x180043fed  test    eax, eax
0x180043fef  jns     loc_18004416B
0x180043ff5  add     rdi, 50h ; 'P'
0x180043ff9  cmp     eax, [rdi+8]
0x180043ffc  jnz     loc_18004416B
0x180044002  test    rdi, rdi
0x180044005  jz      loc_18004416B
0x18004400b  call    ?zInternalStop@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180044010  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180044015  mov     r9, rax
0x180044018  mov     ecx, [rax]
0x18004401a  cmp     ecx, 5
0x18004401d  jbe     loc_1800441E2
0x180044023  mov     rdx, 400000000000h
0x18004402d  mov     rcx, rax
0x180044030  call    _tlgKeywordOn
0x180044035  test    al, al
0x180044037  jz      loc_1800441E2
0x18004403d  mov     rax, [rdi+70h]
0x180044041  lea     rdx, unk_1800578C0
0x180044048  mov     rcx, [rdi+78h]
0x18004404c  mov     r8, [rbx+110h]
0x180044053  mov     [rbp+57h+var_60], rax
0x180044057  add     r8, 8
0x18004405b  mov     eax, [rdi+68h]
0x18004405e  mov     [rbp+57h+arg_0], eax
0x180044061  mov     rax, [rdi+60h]
0x180044065  mov     [rbp+57h+var_58], rax
0x180044069  mov     rax, [rdi+58h]
0x18004406d  mov     [rbp+57h+var_50], rax
0x180044071  mov     eax, [rdi+50h]
0x180044074  mov     [rbp+57h+arg_8], eax
0x180044077  mov     rax, [rdi+48h]
0x18004407b  mov     [rbp+57h+var_48], rax
0x18004407f  mov     eax, [rdi+20h]
0x180044082  mov     dword ptr [rbp+57h+arg_10], eax
0x180044085  mov     rax, [rdi+18h]
0x180044089  mov     [rbp+57h+var_40], rax
0x18004408d  mov     eax, [rdi]
0x18004408f  mov     [rbp+57h+arg_18], eax
0x180044092  mov     rax, [rdi+80h]
0x180044099  mov     [rbp+57h+var_38], rax
0x18004409d  mov     eax, [rdi+40h]
0x1800440a0  mov     [rbp+57h+var_70], eax
0x1800440a3  mov     rax, [rdi+38h]
0x1800440a7  mov     [rbp+57h+var_30], rax
0x1800440ab  mov     eax, [rdi+8]
0x1800440ae  mov     [rbp+57h+var_6C], eax
0x1800440b1  lea     rax, [rbp+57h+var_68]
0x1800440b5  mov     [rsp+110h+var_78], rax
0x1800440bd  lea     rax, [rbp+57h+var_60]
0x1800440c1  mov     [rsp+110h+var_80], rax
0x1800440c9  lea     rax, [rbp+57h+arg_0]
0x1800440cd  mov     [rsp+110h+var_88], rax
0x1800440d5  lea     rax, [rbp+57h+var_58]
0x1800440d9  mov     [rsp+110h+var_90], rax
0x1800440e1  lea     rax, [rbp+57h+var_50]
0x1800440e5  mov     [rsp+110h+var_98], rax
0x1800440ea  lea     rax, [rbp+57h+arg_8]
0x1800440ee  mov     [rsp+110h+var_A0], rax
0x1800440f3  lea     rax, [rbp+57h+var_48]
0x1800440f7  mov     [rsp+110h+var_A8], rax
0x1800440fc  lea     rax, [rbp+57h+arg_10]
0x180044100  mov     [rsp+110h+var_B0], rax
0x180044105  lea     rax, [rbp+57h+var_40]
0x180044109  mov     [rsp+110h+var_B8], rax
0x18004410e  lea     rax, [rbp+57h+arg_18]
0x180044112  mov     [rsp+110h+var_C0], rax
0x180044117  lea     rax, [rbp+57h+var_38]
0x18004411b  mov     [rsp+110h+var_C8], rax
0x180044120  lea     rax, [rbp+57h+var_70]
0x180044124  mov     [rsp+110h+var_D0], rax
0x180044129  lea     rax, [rbp+57h+var_30]
0x18004412d  mov     [rsp+110h+var_D8], rax
0x180044132  lea     rax, [rbp+57h+var_6C]
0x180044136  mov     [rsp+110h+var_E0], rax
0x18004413b  lea     rax, [rbp+57h+var_28]
0x18004413f  mov     [rsp+110h+var_E8], rax
0x180044144  lea     rax, [rbp+57h+var_20]
0x180044148  mov     [rbp+57h+var_68], rcx
0x18004414c  mov     rcx, r9
0x18004414f  mov     [rsp+110h+var_F0], rax
0x180044154  mov     [rbp+57h+var_28], 1000000h
0x18004415c  mov     [rbp+57h+var_20], 3000000h
0x180044164  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180044169  jmp     short loc_1800441E2
0x18004416b  call    ?zInternalStop@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180044170  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180044175  mov     rdi, rax
0x180044178  mov     ecx, [rax]
0x18004417a  cmp     ecx, 5
0x18004417d  jbe     short loc_1800441E2
0x18004417f  mov     rdx, 400000000000h
0x180044189  mov     rcx, rax
0x18004418c  call    _tlgKeywordOn
0x180044191  test    al, al
0x180044193  jz      short loc_1800441E2
0x180044195  call    cs:__imp_GetCurrentThreadId
0x18004419b  mov     r8, [rbx+110h]
0x1800441a2  lea     rdx, word_1800573EE
0x1800441a9  mov     [rbp+57h+arg_0], eax
0x1800441ac  mov     rcx, rdi
0x1800441af  mov     eax, [r8+48h]
0x1800441b3  add     r8, 8
0x1800441b7  mov     [rbp+57h+arg_8], eax
0x1800441ba  lea     rax, [rbp+57h+arg_0]
0x1800441be  mov     [rsp+110h+var_E0], rax
0x1800441c3  lea     rax, [rbp+57h+arg_8]
0x1800441c7  mov     [rsp+110h+var_E8], rax
0x1800441cc  lea     rax, [rbp+57h+arg_10]
0x1800441d0  mov     [rsp+110h+var_F0], rax
0x1800441d5  mov     [rbp+57h+arg_10], 3000000h
0x1800441dd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800441e2  mov     rcx, rbx
0x1800441e5  add     rsp, 100h
0x1800441ec  pop     rdi
0x1800441ed  pop     rbx
0x1800441ee  pop     rbp
0x1800441ef  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
