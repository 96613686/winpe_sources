# MitigationTelemetryClass::RunServiceDrivenActionsActivity::StartActivity(ulong)

- ea: `0x180021550`
- end: `0x180021623`
- name: `?StartActivity@RunServiceDrivenActionsActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `211`
- prototype: `void __fastcall(MitigationTelemetryClass::RunServiceDrivenActionsActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001fef0`

## callees

- `0x1800019bc`
- `0x180001b7c`
- `0x1800176c4`
- `0x18001786c`
- `0x18001b9bc`
- `0x180021550`
- `0x18002464c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002159f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002159f`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::RunServiceDrivenActionsActivity::StartActivity(
        MitigationTelemetryClass::RunServiceDrivenActionsActivity *this,
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
        (__int64)&byte_18006D89F,
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
0x180021550  mov     [rsp+arg_0], rbx
0x180021555  mov     [rsp+arg_8], edx
0x180021559  push    rdi
0x18002155a  sub     rsp, 30h
0x18002155e  mov     rbx, rcx
0x180021561  call    ?IsTelemetryEnabled@MitigationTelemetryUtils@@SA_NXZ; MitigationTelemetryUtils::IsTelemetryEnabled(void)
0x180021566  test    al, al
0x180021568  jz      loc_180021618
0x18002156e  mov     rcx, rbx
0x180021571  call    ?zInternalStart@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180021576  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x18002157b  mov     rdi, rax
0x18002157e  mov     edx, [rax]
0x180021580  cmp     edx, 5
0x180021583  jbe     loc_180021609
0x180021589  mov     rdx, 400000000000h
0x180021593  mov     rcx, rax
0x180021596  call    _tlgKeywordOn
0x18002159b  test    al, al
0x18002159d  jz      short loc_180021609
0x18002159f  call    cs:__imp_GetCurrentThreadId
0x1800215a5  mov     r8, [rbx+110h]
0x1800215ac  mov     [rsp+38h+arg_8], eax
0x1800215b0  mov     [rsp+38h+arg_10], 1000000h
0x1800215b9  cmp     byte ptr [r8+4], 0
0x1800215be  jz      short loc_1800215DF
0x1800215c0  lea     r9, [r8+18h]
0x1800215c4  cmp     dword ptr [r9], 0
0x1800215c8  jnz     short loc_1800215E2
0x1800215ca  cmp     dword ptr [r9+4], 0
0x1800215cf  jnz     short loc_1800215E2
0x1800215d1  cmp     dword ptr [r9+8], 0
0x1800215d6  jnz     short loc_1800215E2
0x1800215d8  cmp     dword ptr [r9+0Ch], 0
0x1800215dd  jnz     short loc_1800215E2
0x1800215df  xor     r9d, r9d
0x1800215e2  lea     rax, [rsp+38h+arg_8]
0x1800215e7  add     r8, 8
0x1800215eb  mov     [rsp+38h+var_10], rax
0x1800215f0  lea     rdx, byte_18006D89F
0x1800215f7  lea     rax, [rsp+38h+arg_10]
0x1800215fc  mov     rcx, rdi
0x1800215ff  mov     [rsp+38h+var_18], rax
0x180021604  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180021609  mov     rcx, rbx
0x18002160c  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180021611  mov     byte ptr [rbx+150h], 1
0x180021618  mov     rbx, [rsp+38h+arg_0]
0x18002161d  add     rsp, 30h
0x180021621  pop     rdi
0x180021622  retn
```
