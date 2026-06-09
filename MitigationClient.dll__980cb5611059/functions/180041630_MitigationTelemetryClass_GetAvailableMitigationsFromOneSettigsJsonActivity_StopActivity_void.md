# MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::StopActivity(void)

- ea: `0x180041630`
- end: `0x180041852`
- name: `?StopActivity@GetAvailableMitigationsFromOneSettigsJsonActivity@MitigationTelemetryClass@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x1800246bc`
- `0x180041630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800417f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800417f2`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::StopActivity(
        MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *this)
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
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const char *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const char *v21; // [rsp+C0h] [rbp+7h] BYREF
  const char *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const char *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v25; // [rsp+E0h] [rbp+27h] BYREF
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
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = MitigationTelemetryClass::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const char *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const char *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const char *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const char *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const char *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v18 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&byte_18006F8E7,
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
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = MitigationTelemetryClass::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18006F875,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180041630  push    rbp
0x180041632  push    rbx
0x180041633  push    rdi
0x180041634  lea     rbp, [rsp-47h]
0x180041639  sub     rsp, 100h
0x180041640  mov     rdi, [rcx+110h]
0x180041647  mov     rbx, rcx
0x18004164a  mov     eax, [rdi+48h]
0x18004164d  test    eax, eax
0x18004164f  jns     loc_1800417C8
0x180041655  add     rdi, 50h ; 'P'
0x180041659  cmp     eax, [rdi+8]
0x18004165c  jnz     loc_1800417C8
0x180041662  test    rdi, rdi
0x180041665  jz      loc_1800417C8
0x18004166b  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041670  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180041675  mov     r9, rax
0x180041678  mov     ecx, [rax]
0x18004167a  cmp     ecx, 5
0x18004167d  jbe     loc_180041840
0x180041683  mov     rdx, 400000000000h
0x18004168d  mov     rcx, rax
0x180041690  call    _tlgKeywordOn
0x180041695  test    al, al
0x180041697  jz      loc_180041840
0x18004169d  mov     rax, [rdi+70h]
0x1800416a1  lea     rdx, byte_18006F8E7
0x1800416a8  mov     rcx, [rdi+78h]
0x1800416ac  mov     r8, [rbx+110h]
0x1800416b3  mov     [rbp+57h+var_60], rax
0x1800416b7  add     r8, 8
0x1800416bb  mov     eax, [rdi+68h]
0x1800416be  mov     [rbp+57h+arg_0], eax
0x1800416c1  mov     rax, [rdi+60h]
0x1800416c5  mov     [rbp+57h+var_58], rax
0x1800416c9  mov     rax, [rdi+58h]
0x1800416cd  mov     [rbp+57h+var_50], rax
0x1800416d1  mov     eax, [rdi+50h]
0x1800416d4  mov     [rbp+57h+arg_8], eax
0x1800416d7  mov     rax, [rdi+48h]
0x1800416db  mov     [rbp+57h+var_48], rax
0x1800416df  mov     eax, [rdi+20h]
0x1800416e2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800416e5  mov     rax, [rdi+18h]
0x1800416e9  mov     [rbp+57h+var_40], rax
0x1800416ed  mov     eax, [rdi]
0x1800416ef  mov     [rbp+57h+arg_18], eax
0x1800416f2  mov     rax, [rdi+80h]
0x1800416f9  mov     [rbp+57h+var_38], rax
0x1800416fd  mov     eax, [rdi+40h]
0x180041700  mov     [rbp+57h+var_70], eax
0x180041703  mov     rax, [rdi+38h]
0x180041707  mov     [rbp+57h+var_30], rax
0x18004170b  mov     eax, [rdi+8]
0x18004170e  mov     [rbp+57h+var_6C], eax
0x180041711  mov     eax, 1000000h
0x180041716  mov     [rbp+57h+var_28], rax
0x18004171a  mov     [rbp+57h+var_20], rax
0x18004171e  lea     rax, [rbp+57h+var_68]
0x180041722  mov     [rsp+110h+var_78], rax
0x18004172a  lea     rax, [rbp+57h+var_60]
0x18004172e  mov     [rsp+110h+var_80], rax
0x180041736  lea     rax, [rbp+57h+arg_0]
0x18004173a  mov     [rsp+110h+var_88], rax
0x180041742  lea     rax, [rbp+57h+var_58]
0x180041746  mov     [rsp+110h+var_90], rax
0x18004174e  lea     rax, [rbp+57h+var_50]
0x180041752  mov     [rsp+110h+var_98], rax
0x180041757  lea     rax, [rbp+57h+arg_8]
0x18004175b  mov     [rsp+110h+var_A0], rax
0x180041760  lea     rax, [rbp+57h+var_48]
0x180041764  mov     [rsp+110h+var_A8], rax
0x180041769  lea     rax, [rbp+57h+arg_10]
0x18004176d  mov     [rsp+110h+var_B0], rax
0x180041772  lea     rax, [rbp+57h+var_40]
0x180041776  mov     [rsp+110h+var_B8], rax
0x18004177b  lea     rax, [rbp+57h+arg_18]
0x18004177f  mov     [rsp+110h+var_C0], rax
0x180041784  lea     rax, [rbp+57h+var_38]
0x180041788  mov     [rsp+110h+var_C8], rax
0x18004178d  lea     rax, [rbp+57h+var_70]
0x180041791  mov     [rsp+110h+var_D0], rax
0x180041796  lea     rax, [rbp+57h+var_30]
0x18004179a  mov     [rsp+110h+var_D8], rax
0x18004179f  lea     rax, [rbp+57h+var_6C]
0x1800417a3  mov     [rsp+110h+var_E0], rax
0x1800417a8  lea     rax, [rbp+57h+var_28]
0x1800417ac  mov     [rsp+110h+var_E8], rax
0x1800417b1  lea     rax, [rbp+57h+var_20]
0x1800417b5  mov     [rbp+57h+var_68], rcx
0x1800417b9  mov     rcx, r9
0x1800417bc  mov     [rsp+110h+var_F0], rax
0x1800417c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800417c6  jmp     short loc_180041840
0x1800417c8  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800417cd  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800417d2  mov     rdi, rax
0x1800417d5  mov     ecx, [rax]
0x1800417d7  cmp     ecx, 5
0x1800417da  jbe     short loc_180041840
0x1800417dc  mov     rdx, 400000000000h
0x1800417e6  mov     rcx, rax
0x1800417e9  call    _tlgKeywordOn
0x1800417ee  test    al, al
0x1800417f0  jz      short loc_180041840
0x1800417f2  call    cs:__imp_GetCurrentThreadId
0x1800417f8  mov     r8, [rbx+110h]
0x1800417ff  lea     rdx, byte_18006F875
0x180041806  mov     [rbp+57h+arg_0], eax
0x180041809  mov     rcx, rdi
0x18004180c  mov     eax, [r8+48h]
0x180041810  add     r8, 8
0x180041814  mov     [rbp+57h+arg_8], eax
0x180041817  mov     eax, 1000000h
0x18004181c  mov     [rbp+57h+arg_10], rax
0x180041820  lea     rax, [rbp+57h+arg_0]
0x180041824  mov     [rsp+110h+var_E0], rax
0x180041829  lea     rax, [rbp+57h+arg_8]
0x18004182d  mov     [rsp+110h+var_E8], rax
0x180041832  lea     rax, [rbp+57h+arg_10]
0x180041836  mov     [rsp+110h+var_F0], rax
0x18004183b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041840  mov     rcx, rbx
0x180041843  add     rsp, 100h
0x18004184a  pop     rdi
0x18004184b  pop     rbx
0x18004184c  pop     rbp
0x18004184d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
