# Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StopActivity(void)

- ea: `0x18003dce0`
- end: `0x18003df0c`
- name: `?StopActivity@CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001314`
- `0x1800019ec`
- `0x18003bf74`
- `0x18003c9b8`
- `0x18003dce0`
- `0x180040bb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dead`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dead`

## pseudocode

```c
void __fastcall Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StopActivity(
        Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+150h] [rbp+10h] BYREF
  __int64 v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  __int64 v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v19 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v30) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      LODWORD(v31) = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v6;
      LODWORD(v28) = v4[17];
      LODWORD(v29) = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v26 = 0x1000000;
      v27[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v5,
        (int)&unk_180111840,
        v7 + 8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v17);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = CortanaSearchTelemetryLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(v28) = CurrentThreadId;
      LODWORD(v29) = *(_DWORD *)(v11 + 72);
      v30 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_1801117E1,
        v11 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18003dce0  push    rbp
0x18003dce2  push    rbx
0x18003dce3  push    rdi
0x18003dce4  lea     rbp, [rsp+10h]
0x18003dce9  sub     rsp, 130h
0x18003dcf0  mov     rdi, [rcx+110h]
0x18003dcf7  mov     rbx, rcx
0x18003dcfa  mov     eax, [rdi+48h]
0x18003dcfd  test    eax, eax
0x18003dcff  jns     loc_18003DE99
0x18003dd05  add     rdi, 50h ; 'P'
0x18003dd09  cmp     eax, [rdi+8]
0x18003dd0c  jnz     loc_18003DE99
0x18003dd12  test    rdi, rdi
0x18003dd15  jz      loc_18003DE99
0x18003dd1b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003dd20  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003dd25  mov     r9, rax
0x18003dd28  mov     ecx, [rax]
0x18003dd2a  cmp     ecx, 5
0x18003dd2d  jbe     loc_18003DEFA
0x18003dd33  mov     rax, [rdi+70h]
0x18003dd37  lea     rdx, unk_180111840; int
0x18003dd3e  mov     rcx, [rdi+30h]
0x18003dd42  mov     [rbp+var_60], rax
0x18003dd46  mov     eax, [rdi+68h]
0x18003dd49  mov     r8, [rbx+110h]
0x18003dd50  mov     dword ptr [rbp+arg_10], eax
0x18003dd53  add     r8, 8; int
0x18003dd57  mov     rax, [rdi+60h]
0x18003dd5b  mov     [rbp+var_58], rax
0x18003dd5f  mov     rax, [rdi+58h]
0x18003dd63  mov     [rbp+var_50], rax
0x18003dd67  mov     eax, [rdi+50h]
0x18003dd6a  mov     dword ptr [rbp+arg_18], eax
0x18003dd6d  mov     rax, [rdi+48h]
0x18003dd71  mov     [rbp+var_48], rax
0x18003dd75  mov     eax, [rdi+20h]
0x18003dd78  mov     dword ptr [rbp+var_80], eax
0x18003dd7b  mov     rax, [rdi+18h]
0x18003dd7f  mov     [rbp+var_40], rax
0x18003dd83  mov     eax, [rdi]
0x18003dd85  mov     dword ptr [rbp+var_80+4], eax
0x18003dd88  mov     rax, [rdi+80h]
0x18003dd8f  mov     [rbp+var_38], rax
0x18003dd93  mov     eax, [rdi+40h]
0x18003dd96  mov     dword ptr [rbp+var_78], eax
0x18003dd99  mov     rax, [rdi+38h]
0x18003dd9d  mov     [rbp+var_30], rax
0x18003dda1  mov     eax, [rdi+8]
0x18003dda4  mov     dword ptr [rbp+var_78+4], eax
0x18003dda7  lea     rax, [rbp+var_70]
0x18003ddab  mov     [rsp+140h+var_90], rax; __int64
0x18003ddb3  lea     rax, [rbp+arg_0]
0x18003ddb7  mov     [rsp+140h+var_98], rax; __int64
0x18003ddbf  lea     rax, [rbp+arg_8]
0x18003ddc3  mov     [rsp+140h+var_A0], rax; __int64
0x18003ddcb  lea     rax, [rbp+var_68]
0x18003ddcf  mov     [rsp+140h+var_A8], rax; __int64
0x18003ddd7  lea     rax, [rbp+var_60]
0x18003dddb  mov     [rsp+140h+var_B0], rax; __int64
0x18003dde3  lea     rax, [rbp+arg_10]
0x18003dde7  mov     [rsp+140h+var_B8], rax; __int64
0x18003ddef  lea     rax, [rbp+var_58]
0x18003ddf3  mov     [rsp+140h+var_C0], rax; __int64
0x18003ddfb  lea     rax, [rbp+var_50]
0x18003ddff  mov     [rsp+140h+var_C8], rax; __int64
0x18003de04  lea     rax, [rbp+arg_18]
0x18003de08  mov     [rsp+140h+var_D0], rax; __int64
0x18003de0d  lea     rax, [rbp+var_48]
0x18003de11  mov     [rsp+140h+var_D8], rax; __int64
0x18003de16  lea     rax, [rbp+var_80]
0x18003de1a  mov     [rsp+140h+var_E0], rax; __int64
0x18003de1f  lea     rax, [rbp+var_40]
0x18003de23  mov     [rsp+140h+var_E8], rax; __int64
0x18003de28  lea     rax, [rbp+var_80+4]
0x18003de2c  mov     [rsp+140h+var_F0], rax; __int64
0x18003de31  lea     rax, [rbp+var_38]
0x18003de35  mov     [rsp+140h+var_F8], rax; __int64
0x18003de3a  lea     rax, [rbp+var_78]
0x18003de3e  mov     [rsp+140h+var_100], rax; __int64
0x18003de43  lea     rax, [rbp+var_30]
0x18003de47  mov     [rsp+140h+var_108], rax; __int64
0x18003de4c  lea     rax, [rbp+var_78+4]
0x18003de50  mov     [rbp+var_70], rcx
0x18003de54  mov     ecx, [rdi+44h]
0x18003de57  mov     [rsp+140h+var_110], rax; __int64
0x18003de5c  lea     rax, [rbp+var_28]
0x18003de60  mov     dword ptr [rbp+arg_0], ecx
0x18003de63  mov     ecx, [rdi+10h]
0x18003de66  mov     dword ptr [rbp+arg_8], ecx
0x18003de69  mov     rcx, [rdi+78h]
0x18003de6d  mov     [rsp+140h+var_118], rax; __int64
0x18003de72  lea     rax, [rbp+var_20]
0x18003de76  mov     [rbp+var_68], rcx
0x18003de7a  mov     rcx, r9; int
0x18003de7d  mov     [rsp+140h+var_120], rax; __int64
0x18003de82  mov     [rbp+var_28], 1000000h
0x18003de8a  mov     [rbp+var_20], 2000000h
0x18003de92  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003de97  jmp     short loc_18003DEFA
0x18003de99  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003de9e  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003dea3  mov     rdi, rax
0x18003dea6  mov     ecx, [rax]
0x18003dea8  cmp     ecx, 5
0x18003deab  jbe     short loc_18003DEFA
0x18003dead  call    cs:__imp_GetCurrentThreadId
0x18003deb3  mov     r8, [rbx+110h]
0x18003deba  lea     rdx, byte_1801117E1
0x18003dec1  mov     dword ptr [rbp+arg_0], eax
0x18003dec4  lea     rax, [rbp+arg_0]
0x18003dec8  mov     [rsp+140h+var_110], rax
0x18003decd  lea     rax, [rbp+arg_8]
0x18003ded1  mov     [rsp+140h+var_118], rax
0x18003ded6  lea     rax, [rbp+arg_10]
0x18003deda  mov     ecx, [r8+48h]
0x18003dede  add     r8, 8
0x18003dee2  mov     dword ptr [rbp+arg_8], ecx
0x18003dee5  mov     rcx, rdi
0x18003dee8  mov     [rsp+140h+var_120], rax
0x18003deed  mov     [rbp+arg_10], 2000000h
0x18003def5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003defa  mov     rcx, rbx
0x18003defd  add     rsp, 130h
0x18003df04  pop     rdi
0x18003df05  pop     rbx
0x18003df06  pop     rbp
0x18003df07  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
