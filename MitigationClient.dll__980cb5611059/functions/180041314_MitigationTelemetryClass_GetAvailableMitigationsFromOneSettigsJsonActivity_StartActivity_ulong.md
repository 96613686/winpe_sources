# MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::StartActivity(ulong)

- ea: `0x180041314`
- end: `0x1800413e7`
- name: `?StartActivity@GetAvailableMitigationsFromOneSettigsJsonActivity@MitigationTelemetryClass@@QEAAXK@Z`
- size: `211`
- prototype: `void __fastcall(MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180040b48`

## callees

- `0x1800019bc`
- `0x180001b7c`
- `0x1800176c4`
- `0x18001786c`
- `0x18001b9bc`
- `0x18002464c`
- `0x180041314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041363`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity::StartActivity(
        MitigationTelemetryClass::GetAvailableMitigationsFromOneSettigsJsonActivity *this,
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
        (__int64)&dword_18006F80C,
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
0x180041314  mov     [rsp+arg_0], rbx
0x180041319  mov     [rsp+arg_8], edx
0x18004131d  push    rdi
0x18004131e  sub     rsp, 30h
0x180041322  mov     rbx, rcx
0x180041325  call    ?IsTelemetryEnabled@MitigationTelemetryUtils@@SA_NXZ; MitigationTelemetryUtils::IsTelemetryEnabled(void)
0x18004132a  test    al, al
0x18004132c  jz      loc_1800413DC
0x180041332  mov     rcx, rbx
0x180041335  call    ?zInternalStart@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18004133a  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x18004133f  mov     rdi, rax
0x180041342  mov     edx, [rax]
0x180041344  cmp     edx, 5
0x180041347  jbe     loc_1800413CD
0x18004134d  mov     rdx, 400000000000h
0x180041357  mov     rcx, rax
0x18004135a  call    _tlgKeywordOn
0x18004135f  test    al, al
0x180041361  jz      short loc_1800413CD
0x180041363  call    cs:__imp_GetCurrentThreadId
0x180041369  mov     r8, [rbx+110h]
0x180041370  mov     [rsp+38h+arg_8], eax
0x180041374  mov     [rsp+38h+arg_10], 1000000h
0x18004137d  cmp     byte ptr [r8+4], 0
0x180041382  jz      short loc_1800413A3
0x180041384  lea     r9, [r8+18h]
0x180041388  cmp     dword ptr [r9], 0
0x18004138c  jnz     short loc_1800413A6
0x18004138e  cmp     dword ptr [r9+4], 0
0x180041393  jnz     short loc_1800413A6
0x180041395  cmp     dword ptr [r9+8], 0
0x18004139a  jnz     short loc_1800413A6
0x18004139c  cmp     dword ptr [r9+0Ch], 0
0x1800413a1  jnz     short loc_1800413A6
0x1800413a3  xor     r9d, r9d
0x1800413a6  lea     rax, [rsp+38h+arg_8]
0x1800413ab  add     r8, 8
0x1800413af  mov     [rsp+38h+var_10], rax
0x1800413b4  lea     rdx, dword_18006F80C
0x1800413bb  lea     rax, [rsp+38h+arg_10]
0x1800413c0  mov     rcx, rdi
0x1800413c3  mov     [rsp+38h+var_18], rax
0x1800413c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800413cd  mov     rcx, rbx
0x1800413d0  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800413d5  mov     byte ptr [rbx+150h], 1
0x1800413dc  mov     rbx, [rsp+38h+arg_0]
0x1800413e1  add     rsp, 30h
0x1800413e5  pop     rdi
0x1800413e6  retn
```
