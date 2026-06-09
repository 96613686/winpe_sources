# MitigationTelemetryClass::ReadOneSettigsJsonActivity::StopActivity(void)

- ea: `0x180056a00`
- end: `0x180056c22`
- name: `?StopActivity@ReadOneSettigsJsonActivity@MitigationTelemetryClass@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(MitigationTelemetryClass::ReadOneSettigsJsonActivity *__hidden this)`
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
- `0x180056a00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056bc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056bc2`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::ReadOneSettigsJsonActivity::StopActivity(
        MitigationTelemetryClass::ReadOneSettigsJsonActivity *this)
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
        (__int64)byte_180070BAB,
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
        (__int64)&unk_180070B50,
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
0x180056a00  push    rbp
0x180056a02  push    rbx
0x180056a03  push    rdi
0x180056a04  lea     rbp, [rsp-47h]
0x180056a09  sub     rsp, 100h
0x180056a10  mov     rdi, [rcx+110h]
0x180056a17  mov     rbx, rcx
0x180056a1a  mov     eax, [rdi+48h]
0x180056a1d  test    eax, eax
0x180056a1f  jns     loc_180056B98
0x180056a25  add     rdi, 50h ; 'P'
0x180056a29  cmp     eax, [rdi+8]
0x180056a2c  jnz     loc_180056B98
0x180056a32  test    rdi, rdi
0x180056a35  jz      loc_180056B98
0x180056a3b  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180056a40  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180056a45  mov     r9, rax
0x180056a48  mov     ecx, [rax]
0x180056a4a  cmp     ecx, 5
0x180056a4d  jbe     loc_180056C10
0x180056a53  mov     rdx, 400000000000h
0x180056a5d  mov     rcx, rax
0x180056a60  call    _tlgKeywordOn
0x180056a65  test    al, al
0x180056a67  jz      loc_180056C10
0x180056a6d  mov     rax, [rdi+70h]
0x180056a71  lea     rdx, byte_180070BAB
0x180056a78  mov     rcx, [rdi+78h]
0x180056a7c  mov     r8, [rbx+110h]
0x180056a83  mov     [rbp+57h+var_60], rax
0x180056a87  add     r8, 8
0x180056a8b  mov     eax, [rdi+68h]
0x180056a8e  mov     [rbp+57h+arg_0], eax
0x180056a91  mov     rax, [rdi+60h]
0x180056a95  mov     [rbp+57h+var_58], rax
0x180056a99  mov     rax, [rdi+58h]
0x180056a9d  mov     [rbp+57h+var_50], rax
0x180056aa1  mov     eax, [rdi+50h]
0x180056aa4  mov     [rbp+57h+arg_8], eax
0x180056aa7  mov     rax, [rdi+48h]
0x180056aab  mov     [rbp+57h+var_48], rax
0x180056aaf  mov     eax, [rdi+20h]
0x180056ab2  mov     dword ptr [rbp+57h+arg_10], eax
0x180056ab5  mov     rax, [rdi+18h]
0x180056ab9  mov     [rbp+57h+var_40], rax
0x180056abd  mov     eax, [rdi]
0x180056abf  mov     [rbp+57h+arg_18], eax
0x180056ac2  mov     rax, [rdi+80h]
0x180056ac9  mov     [rbp+57h+var_38], rax
0x180056acd  mov     eax, [rdi+40h]
0x180056ad0  mov     [rbp+57h+var_70], eax
0x180056ad3  mov     rax, [rdi+38h]
0x180056ad7  mov     [rbp+57h+var_30], rax
0x180056adb  mov     eax, [rdi+8]
0x180056ade  mov     [rbp+57h+var_6C], eax
0x180056ae1  mov     eax, 1000000h
0x180056ae6  mov     [rbp+57h+var_28], rax
0x180056aea  mov     [rbp+57h+var_20], rax
0x180056aee  lea     rax, [rbp+57h+var_68]
0x180056af2  mov     [rsp+110h+var_78], rax
0x180056afa  lea     rax, [rbp+57h+var_60]
0x180056afe  mov     [rsp+110h+var_80], rax
0x180056b06  lea     rax, [rbp+57h+arg_0]
0x180056b0a  mov     [rsp+110h+var_88], rax
0x180056b12  lea     rax, [rbp+57h+var_58]
0x180056b16  mov     [rsp+110h+var_90], rax
0x180056b1e  lea     rax, [rbp+57h+var_50]
0x180056b22  mov     [rsp+110h+var_98], rax
0x180056b27  lea     rax, [rbp+57h+arg_8]
0x180056b2b  mov     [rsp+110h+var_A0], rax
0x180056b30  lea     rax, [rbp+57h+var_48]
0x180056b34  mov     [rsp+110h+var_A8], rax
0x180056b39  lea     rax, [rbp+57h+arg_10]
0x180056b3d  mov     [rsp+110h+var_B0], rax
0x180056b42  lea     rax, [rbp+57h+var_40]
0x180056b46  mov     [rsp+110h+var_B8], rax
0x180056b4b  lea     rax, [rbp+57h+arg_18]
0x180056b4f  mov     [rsp+110h+var_C0], rax
0x180056b54  lea     rax, [rbp+57h+var_38]
0x180056b58  mov     [rsp+110h+var_C8], rax
0x180056b5d  lea     rax, [rbp+57h+var_70]
0x180056b61  mov     [rsp+110h+var_D0], rax
0x180056b66  lea     rax, [rbp+57h+var_30]
0x180056b6a  mov     [rsp+110h+var_D8], rax
0x180056b6f  lea     rax, [rbp+57h+var_6C]
0x180056b73  mov     [rsp+110h+var_E0], rax
0x180056b78  lea     rax, [rbp+57h+var_28]
0x180056b7c  mov     [rsp+110h+var_E8], rax
0x180056b81  lea     rax, [rbp+57h+var_20]
0x180056b85  mov     [rbp+57h+var_68], rcx
0x180056b89  mov     rcx, r9
0x180056b8c  mov     [rsp+110h+var_F0], rax
0x180056b91  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180056b96  jmp     short loc_180056C10
0x180056b98  call    ?zInternalStop@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180056b9d  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x180056ba2  mov     rdi, rax
0x180056ba5  mov     ecx, [rax]
0x180056ba7  cmp     ecx, 5
0x180056baa  jbe     short loc_180056C10
0x180056bac  mov     rdx, 400000000000h
0x180056bb6  mov     rcx, rax
0x180056bb9  call    _tlgKeywordOn
0x180056bbe  test    al, al
0x180056bc0  jz      short loc_180056C10
0x180056bc2  call    cs:__imp_GetCurrentThreadId
0x180056bc8  mov     r8, [rbx+110h]
0x180056bcf  lea     rdx, unk_180070B50
0x180056bd6  mov     [rbp+57h+arg_0], eax
0x180056bd9  mov     rcx, rdi
0x180056bdc  mov     eax, [r8+48h]
0x180056be0  add     r8, 8
0x180056be4  mov     [rbp+57h+arg_8], eax
0x180056be7  mov     eax, 1000000h
0x180056bec  mov     [rbp+57h+arg_10], rax
0x180056bf0  lea     rax, [rbp+57h+arg_0]
0x180056bf4  mov     [rsp+110h+var_E0], rax
0x180056bf9  lea     rax, [rbp+57h+arg_8]
0x180056bfd  mov     [rsp+110h+var_E8], rax
0x180056c02  lea     rax, [rbp+57h+arg_10]
0x180056c06  mov     [rsp+110h+var_F0], rax
0x180056c0b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056c10  mov     rcx, rbx
0x180056c13  add     rsp, 100h
0x180056c1a  pop     rdi
0x180056c1b  pop     rbx
0x180056c1c  pop     rbp
0x180056c1d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
