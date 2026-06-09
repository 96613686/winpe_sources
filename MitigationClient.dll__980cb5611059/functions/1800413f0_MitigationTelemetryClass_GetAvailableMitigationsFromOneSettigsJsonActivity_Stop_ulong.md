# MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::Stop(ulong)

- ea: `0x1800413f0`
- end: `0x180041623`
- name: `?Stop@GetAvailableMitigationsFromOneSettigsJsonActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `563`
- prototype: `void __fastcall(MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180040b48`

## callees

- `0x1800012b8`
- `0x1800019bc`
- `0x180001bec`
- `0x18001786c`
- `0x18001e13c`
- `0x1800246bc`
- `0x1800413f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800415c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800415c2`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::Stop(
        MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *this,
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
            (__int64)byte_18006F6C3,
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
          (__int64)byte_18006F651,
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
0x1800413f0  mov     [rsp-8+arg_8], edx
0x1800413f4  push    rbp
0x1800413f5  push    rbx
0x1800413f6  push    rdi
0x1800413f7  lea     rbp, [rsp-47h]
0x1800413fc  sub     rsp, 100h
0x180041403  cmp     byte ptr [rcx+150h], 0
0x18004140a  mov     rbx, rcx
0x18004140d  jz      loc_180041618
0x180041413  mov     rdi, [rcx+110h]
0x18004141a  mov     eax, [rdi+48h]
0x18004141d  test    eax, eax
0x18004141f  jns     loc_180041598
0x180041425  add     rdi, 50h ; 'P'
0x180041429  cmp     eax, [rdi+8]
0x18004142c  jnz     loc_180041598
0x180041432  test    rdi, rdi
0x180041435  jz      loc_180041598
0x18004143b  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041440  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180041445  mov     r9, rax
0x180041448  mov     ecx, [rax]
0x18004144a  cmp     ecx, 5
0x18004144d  jbe     loc_180041610
0x180041453  mov     rdx, 400000000000h
0x18004145d  mov     rcx, rax
0x180041460  call    _tlgKeywordOn
0x180041465  test    al, al
0x180041467  jz      loc_180041610
0x18004146d  mov     rax, [rdi+70h]
0x180041471  lea     rdx, byte_18006F6C3
0x180041478  mov     rcx, [rdi+78h]
0x18004147c  mov     r8, [rbx+110h]
0x180041483  mov     [rbp+57h+var_60], rax
0x180041487  add     r8, 8
0x18004148b  mov     eax, [rdi+68h]
0x18004148e  mov     [rbp+57h+arg_8], eax
0x180041491  mov     rax, [rdi+60h]
0x180041495  mov     [rbp+57h+var_58], rax
0x180041499  mov     rax, [rdi+58h]
0x18004149d  mov     [rbp+57h+var_50], rax
0x1800414a1  mov     eax, [rdi+50h]
0x1800414a4  mov     [rbp+57h+arg_0], eax
0x1800414a7  mov     rax, [rdi+48h]
0x1800414ab  mov     [rbp+57h+var_48], rax
0x1800414af  mov     eax, [rdi+20h]
0x1800414b2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800414b5  mov     rax, [rdi+18h]
0x1800414b9  mov     [rbp+57h+var_40], rax
0x1800414bd  mov     eax, [rdi]
0x1800414bf  mov     [rbp+57h+arg_18], eax
0x1800414c2  mov     rax, [rdi+80h]
0x1800414c9  mov     [rbp+57h+var_38], rax
0x1800414cd  mov     eax, [rdi+40h]
0x1800414d0  mov     [rbp+57h+var_70], eax
0x1800414d3  mov     rax, [rdi+38h]
0x1800414d7  mov     [rbp+57h+var_30], rax
0x1800414db  mov     eax, [rdi+8]
0x1800414de  mov     [rbp+57h+var_6C], eax
0x1800414e1  mov     eax, 1000000h
0x1800414e6  mov     [rbp+57h+var_28], rax
0x1800414ea  mov     [rbp+57h+var_20], rax
0x1800414ee  lea     rax, [rbp+57h+var_68]
0x1800414f2  mov     [rsp+110h+var_78], rax
0x1800414fa  lea     rax, [rbp+57h+var_60]
0x1800414fe  mov     [rsp+110h+var_80], rax
0x180041506  lea     rax, [rbp+57h+arg_8]
0x18004150a  mov     [rsp+110h+var_88], rax
0x180041512  lea     rax, [rbp+57h+var_58]
0x180041516  mov     [rsp+110h+var_90], rax
0x18004151e  lea     rax, [rbp+57h+var_50]
0x180041522  mov     [rsp+110h+var_98], rax
0x180041527  lea     rax, [rbp+57h+arg_0]
0x18004152b  mov     [rsp+110h+var_A0], rax
0x180041530  lea     rax, [rbp+57h+var_48]
0x180041534  mov     [rsp+110h+var_A8], rax
0x180041539  lea     rax, [rbp+57h+arg_10]
0x18004153d  mov     [rsp+110h+var_B0], rax
0x180041542  lea     rax, [rbp+57h+var_40]
0x180041546  mov     [rsp+110h+var_B8], rax
0x18004154b  lea     rax, [rbp+57h+arg_18]
0x18004154f  mov     [rsp+110h+var_C0], rax
0x180041554  lea     rax, [rbp+57h+var_38]
0x180041558  mov     [rsp+110h+var_C8], rax
0x18004155d  lea     rax, [rbp+57h+var_70]
0x180041561  mov     [rsp+110h+var_D0], rax
0x180041566  lea     rax, [rbp+57h+var_30]
0x18004156a  mov     [rsp+110h+var_D8], rax
0x18004156f  lea     rax, [rbp+57h+var_6C]
0x180041573  mov     [rsp+110h+var_E0], rax
0x180041578  lea     rax, [rbp+57h+var_28]
0x18004157c  mov     [rsp+110h+var_E8], rax
0x180041581  lea     rax, [rbp+57h+var_20]
0x180041585  mov     [rbp+57h+var_68], rcx
0x180041589  mov     rcx, r9
0x18004158c  mov     [rsp+110h+var_F0], rax
0x180041591  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180041596  jmp     short loc_180041610
0x180041598  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18004159d  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800415a2  mov     rdi, rax
0x1800415a5  mov     ecx, [rax]
0x1800415a7  cmp     ecx, 5
0x1800415aa  jbe     short loc_180041610
0x1800415ac  mov     rdx, 400000000000h
0x1800415b6  mov     rcx, rax
0x1800415b9  call    _tlgKeywordOn
0x1800415be  test    al, al
0x1800415c0  jz      short loc_180041610
0x1800415c2  call    cs:__imp_GetCurrentThreadId
0x1800415c8  mov     r8, [rbx+110h]
0x1800415cf  lea     rdx, byte_18006F651
0x1800415d6  mov     [rbp+57h+arg_8], eax
0x1800415d9  mov     rcx, rdi
0x1800415dc  mov     eax, [r8+48h]
0x1800415e0  add     r8, 8
0x1800415e4  mov     [rbp+57h+arg_0], eax
0x1800415e7  mov     eax, 1000000h
0x1800415ec  mov     [rbp+57h+arg_10], rax
0x1800415f0  lea     rax, [rbp+57h+arg_8]
0x1800415f4  mov     [rsp+110h+var_E0], rax
0x1800415f9  lea     rax, [rbp+57h+arg_0]
0x1800415fd  mov     [rsp+110h+var_E8], rax
0x180041602  lea     rax, [rbp+57h+arg_10]
0x180041606  mov     [rsp+110h+var_F0], rax
0x18004160b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041610  mov     rcx, rbx
0x180041613  call    ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180041618  add     rsp, 100h
0x18004161f  pop     rdi
0x180041620  pop     rbx
0x180041621  pop     rbp
0x180041622  retn
```
