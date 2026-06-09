# MitigationTelemetryClass::ReadOneSettigsJsonActivity::StartActivity(ulong)

- ea: `0x180056274`
- end: `0x180056347`
- name: `?StartActivity@ReadOneSettigsJsonActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `211`
- prototype: `void __fastcall(MitigationTelemetryClass::ReadOneSettigsJsonActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180055f18`

## callees

- `0x1800019bc`
- `0x180001b7c`
- `0x1800176c4`
- `0x18001786c`
- `0x18001b9bc`
- `0x18002464c`
- `0x180056274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800562c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800562c3`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::ReadOneSettigsJsonActivity::StartActivity(
        MitigationTelemetryClass::ReadOneSettigsJsonActivity *this,
        DWORD a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD v8; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v8 = a2;
  if ( MitigationTelemetryUtils::IsTelemetryEnabled() )
  {
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v3 = MitigationTelemetryClass::Provider();
    v4 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = *((_QWORD *)this + 34);
      v8 = CurrentThreadId;
      v9 = 0x1000000;
      if ( !*(_BYTE *)(v6 + 4)
        || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
        && !*(_DWORD *)(v6 + 28)
        && !*(_DWORD *)(v6 + 32)
        && !*(_DWORD *)(v6 + 36) )
      {
        v7 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v4,
        (__int64)&dword_1800709CC,
        v6 + 8,
        v7,
        (__int64)&v9,
        (__int64)&v8);
    }
    wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
    *((_BYTE *)this + 336) = 1;
  }
}

```

## disassembly

```asm
0x180056274  mov     [rsp+arg_0], rbx
0x180056279  mov     [rsp+arg_8], edx
0x18005627d  push    rdi
0x18005627e  sub     rsp, 30h
0x180056282  mov     rbx, rcx
0x180056285  call    ?IsTelemetryEnabled@MitigationTelemetryUtils@@SA_NXZ; MitigationTelemetryUtils::IsTelemetryEnabled(void)
0x18005628a  test    al, al
0x18005628c  jz      loc_18005633C
0x180056292  mov     rcx, rbx
0x180056295  call    ?zInternalStart@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18005629a  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x18005629f  mov     rdi, rax
0x1800562a2  mov     edx, [rax]
0x1800562a4  cmp     edx, 5
0x1800562a7  jbe     loc_18005632D
0x1800562ad  mov     rdx, 400000000000h
0x1800562b7  mov     rcx, rax
0x1800562ba  call    _tlgKeywordOn
0x1800562bf  test    al, al
0x1800562c1  jz      short loc_18005632D
0x1800562c3  call    cs:__imp_GetCurrentThreadId
0x1800562c9  mov     r8, [rbx+110h]
0x1800562d0  mov     [rsp+38h+arg_8], eax
0x1800562d4  mov     [rsp+38h+arg_10], 1000000h
0x1800562dd  cmp     byte ptr [r8+4], 0
0x1800562e2  jz      short loc_180056303
0x1800562e4  lea     r9, [r8+18h]
0x1800562e8  cmp     dword ptr [r9], 0
0x1800562ec  jnz     short loc_180056306
0x1800562ee  cmp     dword ptr [r9+4], 0
0x1800562f3  jnz     short loc_180056306
0x1800562f5  cmp     dword ptr [r9+8], 0
0x1800562fa  jnz     short loc_180056306
0x1800562fc  cmp     dword ptr [r9+0Ch], 0
0x180056301  jnz     short loc_180056306
0x180056303  xor     r9d, r9d
0x180056306  lea     rax, [rsp+38h+arg_8]
0x18005630b  add     r8, 8
0x18005630f  mov     [rsp+38h+var_10], rax
0x180056314  lea     rdx, dword_1800709CC
0x18005631b  lea     rax, [rsp+38h+arg_10]
0x180056320  mov     rcx, rdi
0x180056323  mov     [rsp+38h+var_18], rax
0x180056328  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18005632d  mov     rcx, rbx
0x180056330  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180056335  mov     byte ptr [rbx+150h], 1
0x18005633c  mov     rbx, [rsp+38h+arg_0]
0x180056341  add     rsp, 30h
0x180056345  pop     rdi
0x180056346  retn
```
