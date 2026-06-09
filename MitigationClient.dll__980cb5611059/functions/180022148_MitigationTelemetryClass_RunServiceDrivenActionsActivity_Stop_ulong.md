# MitigationTelemetryClass::RunServiceDrivenActionsActivity::Stop(ulong)

- ea: `0x180022148`
- end: `0x18002237b`
- name: `?Stop@RunServiceDrivenActionsActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `563`
- prototype: `void __fastcall(MitigationTelemetryClass::RunServiceDrivenActionsActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001fef0`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x180022148`
- `0x1800246bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002231a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002231a`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::RunServiceDrivenActionsActivity::Stop(
        MitigationTelemetryClass::RunServiceDrivenActionsActivity *this,
        DWORD a2)
{
  __int64 v3; // rdi
  int v4; // eax
  int *v5; // rdi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const WCHAR *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v19; // [rsp+A8h] [rbp-11h] BYREF
  const char *v20; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v21; // [rsp+B8h] [rbp-1h] BYREF
  const char *v22; // [rsp+C0h] [rbp+7h] BYREF
  const char *v23; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v24; // [rsp+D0h] [rbp+17h] BYREF
  const char *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v30 = a2;
  if ( *((_BYTE *)this + 336) )
  {
    v3 = *((_QWORD *)this + 34);
    v4 = *(_DWORD *)(v3 + 72);
    if ( v4 < 0 && (v5 = (int *)(v3 + 80), v4 == v5[2]) && v5 )
    {
      wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
      v6 = MitigationTelemetryClass::Provider();
      v9 = (__int64)v6;
      if ( *(_DWORD *)v6 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
        {
          v10 = (const WCHAR *)*((_QWORD *)v5 + 15);
          v11 = *((_QWORD *)this + 34);
          v20 = (const char *)*((_QWORD *)v5 + 14);
          v30 = v5[26];
          v21 = (const WCHAR *)*((_QWORD *)v5 + 12);
          v22 = (const char *)*((_QWORD *)v5 + 11);
          v29 = v5[20];
          v23 = (const char *)*((_QWORD *)v5 + 9);
          LODWORD(v31) = v5[8];
          v24 = (const WCHAR *)*((_QWORD *)v5 + 3);
          v32 = *v5;
          v25 = (const char *)*((_QWORD *)v5 + 16);
          v17 = v5[16];
          v26 = (const char *)*((_QWORD *)v5 + 7);
          v18 = v5[2];
          v27 = 0x1000000;
          v28[0] = 0x1000000;
          v19 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v9,
            (__int64)&unk_18006D768,
            v11 + 8,
            v9,
            (__int64)v28,
            (__int64)&v27,
            (__int64)&v18,
            &v26,
            (__int64)&v17,
            &v25,
            (__int64)&v32,
            &v24,
            (__int64)&v31,
            &v23,
            (__int64)&v29,
            &v22,
            &v21,
            (__int64)&v30,
            &v20,
            &v19);
        }
      }
    }
    else
    {
      wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
      v12 = MitigationTelemetryClass::Provider();
      v13 = (__int64)v12;
      if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        v30 = CurrentThreadId;
        v29 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (__int64)&unk_18006D708,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v29,
          (__int64)&v30);
      }
    }
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
      this,
      v7,
      v8,
      v9);
  }
}

```

## disassembly

```asm
0x180022148  mov     [rsp-8+arg_8], edx
0x18002214c  push    rbp
0x18002214d  push    rbx
0x18002214e  push    rdi
0x18002214f  lea     rbp, [rsp-47h]
0x180022154  sub     rsp, 100h
0x18002215b  cmp     byte ptr [rcx+150h], 0
0x180022162  mov     rbx, rcx
0x180022165  jz      loc_180022370
0x18002216b  mov     rdi, [rcx+110h]
0x180022172  mov     eax, [rdi+48h]
0x180022175  test    eax, eax
0x180022177  jns     loc_1800222F0
0x18002217d  add     rdi, 50h ; 'P'
0x180022181  cmp     eax, [rdi+8]
0x180022184  jnz     loc_1800222F0
0x18002218a  test    rdi, rdi
0x18002218d  jz      loc_1800222F0
0x180022193  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180022198  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x18002219d  mov     r9, rax
0x1800221a0  mov     ecx, [rax]
0x1800221a2  cmp     ecx, 5
0x1800221a5  jbe     loc_180022368
0x1800221ab  mov     rdx, 400000000000h
0x1800221b5  mov     rcx, rax
0x1800221b8  call    _tlgKeywordOn
0x1800221bd  test    al, al
0x1800221bf  jz      loc_180022368
0x1800221c5  mov     rax, [rdi+70h]
0x1800221c9  lea     rdx, unk_18006D768
0x1800221d0  mov     rcx, [rdi+78h]
0x1800221d4  mov     r8, [rbx+110h]
0x1800221db  mov     [rbp+57h+var_60], rax
0x1800221df  add     r8, 8
0x1800221e3  mov     eax, [rdi+68h]
0x1800221e6  mov     [rbp+57h+arg_8], eax
0x1800221e9  mov     rax, [rdi+60h]
0x1800221ed  mov     [rbp+57h+var_58], rax
0x1800221f1  mov     rax, [rdi+58h]
0x1800221f5  mov     [rbp+57h+var_50], rax
0x1800221f9  mov     eax, [rdi+50h]
0x1800221fc  mov     [rbp+57h+arg_0], eax
0x1800221ff  mov     rax, [rdi+48h]
0x180022203  mov     [rbp+57h+var_48], rax
0x180022207  mov     eax, [rdi+20h]
0x18002220a  mov     dword ptr [rbp+57h+arg_10], eax
0x18002220d  mov     rax, [rdi+18h]
0x180022211  mov     [rbp+57h+var_40], rax
0x180022215  mov     eax, [rdi]
0x180022217  mov     [rbp+57h+arg_18], eax
0x18002221a  mov     rax, [rdi+80h]
0x180022221  mov     [rbp+57h+var_38], rax
0x180022225  mov     eax, [rdi+40h]
0x180022228  mov     [rbp+57h+var_70], eax
0x18002222b  mov     rax, [rdi+38h]
0x18002222f  mov     [rbp+57h+var_30], rax
0x180022233  mov     eax, [rdi+8]
0x180022236  mov     [rbp+57h+var_6C], eax
0x180022239  mov     eax, 1000000h
0x18002223e  mov     [rbp+57h+var_28], rax
0x180022242  mov     [rbp+57h+var_20], rax
0x180022246  lea     rax, [rbp+57h+var_68]
0x18002224a  mov     [rsp+110h+var_78], rax
0x180022252  lea     rax, [rbp+57h+var_60]
0x180022256  mov     [rsp+110h+var_80], rax
0x18002225e  lea     rax, [rbp+57h+arg_8]
0x180022262  mov     [rsp+110h+var_88], rax
0x18002226a  lea     rax, [rbp+57h+var_58]
0x18002226e  mov     [rsp+110h+var_90], rax
0x180022276  lea     rax, [rbp+57h+var_50]
0x18002227a  mov     [rsp+110h+var_98], rax
0x18002227f  lea     rax, [rbp+57h+arg_0]
0x180022283  mov     [rsp+110h+var_A0], rax
0x180022288  lea     rax, [rbp+57h+var_48]
0x18002228c  mov     [rsp+110h+var_A8], rax
0x180022291  lea     rax, [rbp+57h+arg_10]
0x180022295  mov     [rsp+110h+var_B0], rax
0x18002229a  lea     rax, [rbp+57h+var_40]
0x18002229e  mov     [rsp+110h+var_B8], rax
0x1800222a3  lea     rax, [rbp+57h+arg_18]
0x1800222a7  mov     [rsp+110h+var_C0], rax
0x1800222ac  lea     rax, [rbp+57h+var_38]
0x1800222b0  mov     [rsp+110h+var_C8], rax
0x1800222b5  lea     rax, [rbp+57h+var_70]
0x1800222b9  mov     [rsp+110h+var_D0], rax
0x1800222be  lea     rax, [rbp+57h+var_30]
0x1800222c2  mov     [rsp+110h+var_D8], rax
0x1800222c7  lea     rax, [rbp+57h+var_6C]
0x1800222cb  mov     [rsp+110h+var_E0], rax
0x1800222d0  lea     rax, [rbp+57h+var_28]
0x1800222d4  mov     [rsp+110h+var_E8], rax
0x1800222d9  lea     rax, [rbp+57h+var_20]
0x1800222dd  mov     [rbp+57h+var_68], rcx
0x1800222e1  mov     rcx, r9
0x1800222e4  mov     [rsp+110h+var_F0], rax
0x1800222e9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800222ee  jmp     short loc_180022368
0x1800222f0  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800222f5  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800222fa  mov     rdi, rax
0x1800222fd  mov     ecx, [rax]
0x1800222ff  cmp     ecx, 5
0x180022302  jbe     short loc_180022368
0x180022304  mov     rdx, 400000000000h
0x18002230e  mov     rcx, rax
0x180022311  call    _tlgKeywordOn
0x180022316  test    al, al
0x180022318  jz      short loc_180022368
0x18002231a  call    cs:__imp_GetCurrentThreadId
0x180022320  mov     r8, [rbx+110h]
0x180022327  lea     rdx, unk_18006D708
0x18002232e  mov     [rbp+57h+arg_8], eax
0x180022331  mov     rcx, rdi
0x180022334  mov     eax, [r8+48h]
0x180022338  add     r8, 8
0x18002233c  mov     [rbp+57h+arg_0], eax
0x18002233f  mov     eax, 1000000h
0x180022344  mov     [rbp+57h+arg_10], rax
0x180022348  lea     rax, [rbp+57h+arg_8]
0x18002234c  mov     [rsp+110h+var_E0], rax
0x180022351  lea     rax, [rbp+57h+arg_0]
0x180022355  mov     [rsp+110h+var_E8], rax
0x18002235a  lea     rax, [rbp+57h+arg_10]
0x18002235e  mov     [rsp+110h+var_F0], rax
0x180022363  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022368  mov     rcx, rbx
0x18002236b  call    ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180022370  add     rsp, 100h
0x180022377  pop     rdi
0x180022378  pop     rbx
0x180022379  pop     rbp
0x18002237a  retn
```
