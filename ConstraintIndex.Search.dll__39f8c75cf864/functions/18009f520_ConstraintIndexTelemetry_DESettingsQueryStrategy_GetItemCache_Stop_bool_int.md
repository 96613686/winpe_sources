# ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::Stop(bool,int)

- ea: `0x18009f520`
- end: `0x18009f7c9`
- name: `?Stop@DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@QEAAX_NH@Z`
- size: `681`
- prototype: `void __fastcall(ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *__hidden this, bool, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009e800`

## callees

- `0x18000243c`
- `0x180002db4`
- `0x1800030f8`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x18009f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f74b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f74b`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::Stop(
        ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *this,
        unsigned __int8 a2,
        int a3)
{
  __int64 v3; // rdi
  int v5; // r14d
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // r8
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // edi
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  int v19; // r9d
  int v20; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v21; // [rsp+D4h] [rbp-7Ch] BYREF
  int v22; // [rsp+D8h] [rbp-78h] BYREF
  int v23; // [rsp+DCh] [rbp-74h] BYREF
  int v24; // [rsp+E0h] [rbp-70h] BYREF
  int v25; // [rsp+E4h] [rbp-6Ch] BYREF
  int v26; // [rsp+E8h] [rbp-68h] BYREF
  int v27; // [rsp+ECh] [rbp-64h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+100h] [rbp-50h] BYREF
  __int64 v31; // [rsp+108h] [rbp-48h] BYREF
  __int64 v32; // [rsp+110h] [rbp-40h] BYREF
  __int64 v33; // [rsp+118h] [rbp-38h] BYREF
  __int64 v34; // [rsp+120h] [rbp-30h] BYREF
  __int64 v35; // [rsp+128h] [rbp-28h] BYREF
  __int64 v36; // [rsp+130h] [rbp-20h] BYREF
  __int64 v37; // [rsp+138h] [rbp-18h] BYREF
  __int64 v38; // [rsp+140h] [rbp-10h] BYREF
  __int64 v39; // [rsp+170h] [rbp+20h] BYREF
  __int64 v40; // [rsp+188h] [rbp+38h] BYREF

  v3 = *((_QWORD *)this + 34);
  v5 = a2;
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 1, v10, v9) )
    {
      v29 = *((_QWORD *)v8 + 6);
      v22 = v8[17];
      v23 = v8[4];
      v30 = *((_QWORD *)v8 + 15);
      v31 = *((_QWORD *)v8 + 14);
      v24 = v8[26];
      v32 = *((_QWORD *)v8 + 12);
      v12 = *((_QWORD *)this + 34);
      v33 = *((_QWORD *)v8 + 11);
      v25 = v8[20];
      v34 = *((_QWORD *)v8 + 9);
      v26 = v8[8];
      v35 = *((_QWORD *)v8 + 3);
      v27 = *v8;
      v36 = *((_QWORD *)v8 + 16);
      v20 = v8[16];
      v37 = *((_QWORD *)v8 + 7);
      v21 = v8[2];
      LODWORD(v39) = a3;
      LODWORD(v40) = v5;
      v38 = 0x1000000;
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)&byte_18011383B,
        v12 + 8,
        (__int64)&v28,
        (__int64)&v38,
        (__int64)&v21,
        (__int64)&v37,
        (__int64)&v20,
        (__int64)&v36,
        (__int64)&v27,
        (__int64)&v35,
        (__int64)&v26,
        (__int64)&v34,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v40,
        (__int64)&v39);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = CortanaSearchTelemetryLogging::Provider();
    v16 = (int)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 1, v14, v15) )
    {
      LODWORD(v39) = a3;
      LODWORD(v40) = v5;
      CurrentThreadId = GetCurrentThreadId();
      v18 = *((_QWORD *)this + 34);
      v21 = CurrentThreadId;
      v20 = *(_DWORD *)(v18 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)&byte_1801137B7,
        v18 + 8,
        v19,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v21,
        (__int64)&v40,
        (__int64)&v39);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18009f520  mov     [rsp-18h+arg_8], rbx
0x18009f525  mov     [rsp-18h+arg_10], rsi
0x18009f52a  push    rbp
0x18009f52b  push    rdi
0x18009f52c  push    r14
0x18009f52e  mov     rbp, rsp
0x18009f531  sub     rsp, 150h
0x18009f538  mov     rdi, [rcx+110h]
0x18009f53f  mov     esi, r8d
0x18009f542  movzx   r14d, dl
0x18009f546  mov     rbx, rcx
0x18009f549  mov     eax, [rdi+48h]
0x18009f54c  test    eax, eax
0x18009f54e  jns     loc_18009F71F
0x18009f554  add     rdi, 50h ; 'P'
0x18009f558  cmp     eax, [rdi+8]
0x18009f55b  jnz     loc_18009F71F
0x18009f561  test    rdi, rdi
0x18009f564  jz      loc_18009F71F
0x18009f56a  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009f56f  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f574  mov     r9, rax
0x18009f577  mov     ecx, [rax]
0x18009f579  cmp     ecx, 5
0x18009f57c  jbe     loc_18009F7AA
0x18009f582  mov     edx, 1
0x18009f587  mov     rcx, rax
0x18009f58a  call    _tlgKeywordOn
0x18009f58f  test    al, al
0x18009f591  jz      loc_18009F7AA
0x18009f597  mov     rax, [rdi+30h]
0x18009f59b  mov     [rbp+var_58], rax
0x18009f59f  mov     eax, [rdi+44h]
0x18009f5a2  mov     dword ptr [rbp+var_78], eax
0x18009f5a5  mov     eax, [rdi+10h]
0x18009f5a8  mov     dword ptr [rbp+var_78+4], eax
0x18009f5ab  mov     rax, [rdi+78h]
0x18009f5af  mov     [rbp+var_50], rax
0x18009f5b3  mov     rax, [rdi+70h]
0x18009f5b7  mov     [rbp+var_48], rax
0x18009f5bb  mov     eax, [rdi+68h]
0x18009f5be  mov     dword ptr [rbp+var_70], eax
0x18009f5c1  mov     rax, [rdi+60h]
0x18009f5c5  mov     [rbp+var_40], rax
0x18009f5c9  mov     rax, [rdi+58h]
0x18009f5cd  mov     r8, [rbx+110h]
0x18009f5d4  mov     [rbp+var_38], rax
0x18009f5d8  add     r8, 8; int
0x18009f5dc  mov     eax, [rdi+50h]
0x18009f5df  mov     dword ptr [rbp+var_70+4], eax
0x18009f5e2  mov     rax, [rdi+48h]
0x18009f5e6  mov     [rbp+var_30], rax
0x18009f5ea  mov     eax, [rdi+20h]
0x18009f5ed  mov     [rbp+var_68], eax
0x18009f5f0  mov     rax, [rdi+18h]
0x18009f5f4  mov     [rbp+var_28], rax
0x18009f5f8  mov     eax, [rdi]
0x18009f5fa  mov     [rbp+var_64], eax
0x18009f5fd  mov     rax, [rdi+80h]
0x18009f604  mov     [rbp+var_20], rax
0x18009f608  mov     eax, [rdi+40h]
0x18009f60b  mov     dword ptr [rbp+var_80], eax
0x18009f60e  mov     rax, [rdi+38h]
0x18009f612  mov     [rbp+var_18], rax
0x18009f616  mov     eax, [rdi+8]
0x18009f619  mov     dword ptr [rbp+var_80+4], eax
0x18009f61c  lea     rax, [rbp+arg_0]
0x18009f620  mov     [rsp+150h+var_90], rax; __int64
0x18009f628  lea     rax, [rbp+arg_18]
0x18009f62c  mov     [rsp+150h+var_98], rax; __int64
0x18009f634  lea     rax, [rbp+var_58]
0x18009f638  mov     [rsp+150h+var_A0], rax; __int64
0x18009f640  lea     rax, [rbp+var_78]
0x18009f644  mov     [rsp+150h+var_A8], rax; __int64
0x18009f64c  lea     rax, [rbp+var_78+4]
0x18009f650  mov     [rsp+150h+var_B0], rax; __int64
0x18009f658  lea     rax, [rbp+var_50]
0x18009f65c  mov     [rsp+150h+var_B8], rax; __int64
0x18009f664  lea     rax, [rbp+var_48]
0x18009f668  mov     [rsp+150h+var_C0], rax; __int64
0x18009f670  lea     rax, [rbp+var_70]
0x18009f674  mov     [rsp+150h+var_C8], rax; __int64
0x18009f67c  lea     rax, [rbp+var_40]
0x18009f680  mov     [rsp+150h+var_D0], rax; __int64
0x18009f688  lea     rax, [rbp+var_38]
0x18009f68c  mov     [rsp+150h+var_D8], rax; __int64
0x18009f691  lea     rax, [rbp+var_70+4]
0x18009f695  mov     [rsp+150h+var_E0], rax; __int64
0x18009f69a  lea     rax, [rbp+var_30]
0x18009f69e  mov     [rsp+150h+var_E8], rax; __int64
0x18009f6a3  lea     rax, [rbp+var_68]
0x18009f6a7  mov     [rsp+150h+var_F0], rax; __int64
0x18009f6ac  lea     rax, [rbp+var_28]
0x18009f6b0  mov     [rsp+150h+var_F8], rax; __int64
0x18009f6b5  lea     rax, [rbp+var_64]
0x18009f6b9  mov     [rsp+150h+var_100], rax; __int64
0x18009f6be  lea     rax, [rbp+var_20]
0x18009f6c2  mov     [rsp+150h+var_108], rax; __int64
0x18009f6c7  lea     rax, [rbp+var_80]
0x18009f6cb  mov     [rsp+150h+var_110], rax; __int64
0x18009f6d0  lea     rax, [rbp+var_18]
0x18009f6d4  mov     [rsp+150h+var_118], rax; __int64
0x18009f6d9  lea     rax, [rbp+var_80+4]
0x18009f6dd  mov     [rsp+150h+var_120], rax; __int64
0x18009f6e2  lea     rax, [rbp+var_10]
0x18009f6e6  mov     [rsp+150h+var_128], rax; __int64
0x18009f6eb  lea     rax, [rbp+var_60]
0x18009f6ef  mov     dword ptr [rbp+arg_0], esi
0x18009f6f2  mov     dword ptr [rbp+arg_18], r14d
0x18009f6f6  mov     [rbp+var_10], 1000000h
0x18009f6fe  mov     [rbp+var_60], 0
0x18009f706  lea     rdx, byte_18011383B; int
0x18009f70d  mov     [rsp+150h+var_130], rax; __int64
0x18009f712  mov     rcx, r9; int
0x18009f715  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645644544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009f71a  jmp     loc_18009F7AA
0x18009f71f  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009f724  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f729  mov     rdi, rax
0x18009f72c  mov     ecx, [rax]
0x18009f72e  cmp     ecx, 5
0x18009f731  jbe     short loc_18009F7AA
0x18009f733  mov     edx, 1
0x18009f738  mov     rcx, rax
0x18009f73b  call    _tlgKeywordOn
0x18009f740  test    al, al
0x18009f742  jz      short loc_18009F7AA
0x18009f744  mov     dword ptr [rbp+arg_0], esi
0x18009f747  mov     dword ptr [rbp+arg_18], r14d
0x18009f74b  call    cs:__imp_GetCurrentThreadId
0x18009f751  mov     r8, [rbx+110h]
0x18009f758  lea     rdx, byte_1801137B7
0x18009f75f  mov     dword ptr [rbp+var_80+4], eax
0x18009f762  mov     rcx, rdi
0x18009f765  mov     eax, [r8+48h]
0x18009f769  add     r8, 8
0x18009f76d  mov     dword ptr [rbp+var_80], eax
0x18009f770  lea     rax, [rbp+arg_0]
0x18009f774  mov     [rsp+150h+var_110], rax
0x18009f779  lea     rax, [rbp+arg_18]
0x18009f77d  mov     [rsp+150h+var_118], rax
0x18009f782  lea     rax, [rbp+var_80+4]
0x18009f786  mov     [rsp+150h+var_120], rax
0x18009f78b  lea     rax, [rbp+var_80]
0x18009f78f  mov     [rsp+150h+var_128], rax
0x18009f794  lea     rax, [rbp+var_60]
0x18009f798  mov     [rsp+150h+var_130], rax
0x18009f79d  mov     [rbp+var_60], 0
0x18009f7a5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009f7aa  mov     rcx, rbx
0x18009f7ad  lea     r11, [rsp+150h+var_s0]
0x18009f7b5  mov     rbx, [r11+28h]
0x18009f7b9  mov     rsi, [r11+30h]
0x18009f7bd  mov     rsp, r11
0x18009f7c0  pop     r14
0x18009f7c2  pop     rdi
0x18009f7c3  pop     rbp
0x18009f7c4  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
