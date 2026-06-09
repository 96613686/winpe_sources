# MitigationTelemetryClass::ReadOneSettigsJsonActivity::Stop(ulong)

- ea: `0x18005658c`
- end: `0x1800567bf`
- name: `?Stop@ReadOneSettigsJsonActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `563`
- prototype: `void __fastcall(MitigationTelemetryClass::ReadOneSettigsJsonActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180055f18`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x1800246bc`
- `0x18005658c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005675e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005675e`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::ReadOneSettigsJsonActivity::Stop(
        MitigationTelemetryClass::ReadOneSettigsJsonActivity *this,
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
            (__int64)&word_180070A1E,
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
          (__int64)byte_180070971,
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
0x18005658c  mov     [rsp-8+arg_8], edx
0x180056590  push    rbp
0x180056591  push    rbx
0x180056592  push    rdi
0x180056593  lea     rbp, [rsp-47h]
0x180056598  sub     rsp, 100h
0x18005659f  cmp     byte ptr [rcx+150h], 0
0x1800565a6  mov     rbx, rcx
0x1800565a9  jz      loc_1800567B4
0x1800565af  mov     rdi, [rcx+110h]
0x1800565b6  mov     eax, [rdi+48h]
0x1800565b9  test    eax, eax
0x1800565bb  jns     loc_180056734
0x1800565c1  add     rdi, 50h ; 'P'
0x1800565c5  cmp     eax, [rdi+8]
0x1800565c8  jnz     loc_180056734
0x1800565ce  test    rdi, rdi
0x1800565d1  jz      loc_180056734
0x1800565d7  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800565dc  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800565e1  mov     r9, rax
0x1800565e4  mov     ecx, [rax]
0x1800565e6  cmp     ecx, 5
0x1800565e9  jbe     loc_1800567AC
0x1800565ef  mov     rdx, 400000000000h
0x1800565f9  mov     rcx, rax
0x1800565fc  call    _tlgKeywordOn
0x180056601  test    al, al
0x180056603  jz      loc_1800567AC
0x180056609  mov     rax, [rdi+70h]
0x18005660d  lea     rdx, word_180070A1E
0x180056614  mov     rcx, [rdi+78h]
0x180056618  mov     r8, [rbx+110h]
0x18005661f  mov     [rbp+57h+var_60], rax
0x180056623  add     r8, 8
0x180056627  mov     eax, [rdi+68h]
0x18005662a  mov     [rbp+57h+arg_8], eax
0x18005662d  mov     rax, [rdi+60h]
0x180056631  mov     [rbp+57h+var_58], rax
0x180056635  mov     rax, [rdi+58h]
0x180056639  mov     [rbp+57h+var_50], rax
0x18005663d  mov     eax, [rdi+50h]
0x180056640  mov     [rbp+57h+arg_0], eax
0x180056643  mov     rax, [rdi+48h]
0x180056647  mov     [rbp+57h+var_48], rax
0x18005664b  mov     eax, [rdi+20h]
0x18005664e  mov     dword ptr [rbp+57h+arg_10], eax
0x180056651  mov     rax, [rdi+18h]
0x180056655  mov     [rbp+57h+var_40], rax
0x180056659  mov     eax, [rdi]
0x18005665b  mov     [rbp+57h+arg_18], eax
0x18005665e  mov     rax, [rdi+80h]
0x180056665  mov     [rbp+57h+var_38], rax
0x180056669  mov     eax, [rdi+40h]
0x18005666c  mov     [rbp+57h+var_70], eax
0x18005666f  mov     rax, [rdi+38h]
0x180056673  mov     [rbp+57h+var_30], rax
0x180056677  mov     eax, [rdi+8]
0x18005667a  mov     [rbp+57h+var_6C], eax
0x18005667d  mov     eax, 1000000h
0x180056682  mov     [rbp+57h+var_28], rax
0x180056686  mov     [rbp+57h+var_20], rax
0x18005668a  lea     rax, [rbp+57h+var_68]
0x18005668e  mov     [rsp+110h+var_78], rax
0x180056696  lea     rax, [rbp+57h+var_60]
0x18005669a  mov     [rsp+110h+var_80], rax
0x1800566a2  lea     rax, [rbp+57h+arg_8]
0x1800566a6  mov     [rsp+110h+var_88], rax
0x1800566ae  lea     rax, [rbp+57h+var_58]
0x1800566b2  mov     [rsp+110h+var_90], rax
0x1800566ba  lea     rax, [rbp+57h+var_50]
0x1800566be  mov     [rsp+110h+var_98], rax
0x1800566c3  lea     rax, [rbp+57h+arg_0]
0x1800566c7  mov     [rsp+110h+var_A0], rax
0x1800566cc  lea     rax, [rbp+57h+var_48]
0x1800566d0  mov     [rsp+110h+var_A8], rax
0x1800566d5  lea     rax, [rbp+57h+arg_10]
0x1800566d9  mov     [rsp+110h+var_B0], rax
0x1800566de  lea     rax, [rbp+57h+var_40]
0x1800566e2  mov     [rsp+110h+var_B8], rax
0x1800566e7  lea     rax, [rbp+57h+arg_18]
0x1800566eb  mov     [rsp+110h+var_C0], rax
0x1800566f0  lea     rax, [rbp+57h+var_38]
0x1800566f4  mov     [rsp+110h+var_C8], rax
0x1800566f9  lea     rax, [rbp+57h+var_70]
0x1800566fd  mov     [rsp+110h+var_D0], rax
0x180056702  lea     rax, [rbp+57h+var_30]
0x180056706  mov     [rsp+110h+var_D8], rax
0x18005670b  lea     rax, [rbp+57h+var_6C]
0x18005670f  mov     [rsp+110h+var_E0], rax
0x180056714  lea     rax, [rbp+57h+var_28]
0x180056718  mov     [rsp+110h+var_E8], rax
0x18005671d  lea     rax, [rbp+57h+var_20]
0x180056721  mov     [rbp+57h+var_68], rcx
0x180056725  mov     rcx, r9
0x180056728  mov     [rsp+110h+var_F0], rax
0x18005672d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180056732  jmp     short loc_1800567AC
0x180056734  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180056739  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x18005673e  mov     rdi, rax
0x180056741  mov     ecx, [rax]
0x180056743  cmp     ecx, 5
0x180056746  jbe     short loc_1800567AC
0x180056748  mov     rdx, 400000000000h
0x180056752  mov     rcx, rax
0x180056755  call    _tlgKeywordOn
0x18005675a  test    al, al
0x18005675c  jz      short loc_1800567AC
0x18005675e  call    cs:__imp_GetCurrentThreadId
0x180056764  mov     r8, [rbx+110h]
0x18005676b  lea     rdx, byte_180070971
0x180056772  mov     [rbp+57h+arg_8], eax
0x180056775  mov     rcx, rdi
0x180056778  mov     eax, [r8+48h]
0x18005677c  add     r8, 8
0x180056780  mov     [rbp+57h+arg_0], eax
0x180056783  mov     eax, 1000000h
0x180056788  mov     [rbp+57h+arg_10], rax
0x18005678c  lea     rax, [rbp+57h+arg_8]
0x180056790  mov     [rsp+110h+var_E0], rax
0x180056795  lea     rax, [rbp+57h+arg_0]
0x180056799  mov     [rsp+110h+var_E8], rax
0x18005679e  lea     rax, [rbp+57h+arg_10]
0x1800567a2  mov     [rsp+110h+var_F0], rax
0x1800567a7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800567ac  mov     rcx, rbx
0x1800567af  call    ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800567b4  add     rsp, 100h
0x1800567bb  pop     rdi
0x1800567bc  pop     rbx
0x1800567bd  pop     rbp
0x1800567be  retn
```
