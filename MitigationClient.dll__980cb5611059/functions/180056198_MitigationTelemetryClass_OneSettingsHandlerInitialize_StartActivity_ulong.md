# MitigationTelemetryClass::OneSettingsHandlerInitialize::StartActivity(ulong)

- ea: `0x180056198`
- end: `0x18005626b`
- name: `?StartActivity@OneSettingsHandlerInitialize@MitigationTelemetryClass@@QEAAXK@Z`
- size: `211`
- prototype: `void __fastcall(MitigationTelemetryClass::OneSettingsHandlerInitialize *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800552a0`

## callees

- `0x1800019bc`
- `0x180001b7c`
- `0x1800176c4`
- `0x18001786c`
- `0x18001b9bc`
- `0x18002464c`
- `0x180056198`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800561e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800561e7`

## pseudocode

```c
void __fastcall MitigationTelemetryClass::OneSettingsHandlerInitialize::StartActivity(
        MitigationTelemetryClass::OneSettingsHandlerInitialize *this,
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
        (__int64)&dword_18007078C,
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
0x180056198  mov     [rsp+arg_0], rbx
0x18005619d  mov     [rsp+arg_8], edx
0x1800561a1  push    rdi
0x1800561a2  sub     rsp, 30h
0x1800561a6  mov     rbx, rcx
0x1800561a9  call    ?IsTelemetryEnabled@MitigationTelemetryUtils@@SA_NXZ; MitigationTelemetryUtils::IsTelemetryEnabled(void)
0x1800561ae  test    al, al
0x1800561b0  jz      loc_180056260
0x1800561b6  mov     rcx, rbx
0x1800561b9  call    ?zInternalStart@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800561be  call    ?Provider@MitigationTelemetryClass@@SAPEBU_tlgProvider_t@@XZ; MitigationTelemetryClass::Provider(void)
0x1800561c3  mov     rdi, rax
0x1800561c6  mov     edx, [rax]
0x1800561c8  cmp     edx, 5
0x1800561cb  jbe     loc_180056251
0x1800561d1  mov     rdx, 400000000000h
0x1800561db  mov     rcx, rax
0x1800561de  call    _tlgKeywordOn
0x1800561e3  test    al, al
0x1800561e5  jz      short loc_180056251
0x1800561e7  call    cs:__imp_GetCurrentThreadId
0x1800561ed  mov     r8, [rbx+110h]
0x1800561f4  mov     [rsp+38h+arg_8], eax
0x1800561f8  mov     [rsp+38h+arg_10], 1000000h
0x180056201  cmp     byte ptr [r8+4], 0
0x180056206  jz      short loc_180056227
0x180056208  lea     r9, [r8+18h]
0x18005620c  cmp     dword ptr [r9], 0
0x180056210  jnz     short loc_18005622A
0x180056212  cmp     dword ptr [r9+4], 0
0x180056217  jnz     short loc_18005622A
0x180056219  cmp     dword ptr [r9+8], 0
0x18005621e  jnz     short loc_18005622A
0x180056220  cmp     dword ptr [r9+0Ch], 0
0x180056225  jnz     short loc_18005622A
0x180056227  xor     r9d, r9d
0x18005622a  lea     rax, [rsp+38h+arg_8]
0x18005622f  add     r8, 8
0x180056233  mov     [rsp+38h+var_10], rax
0x180056238  lea     rdx, dword_18007078C
0x18005623f  lea     rax, [rsp+38h+arg_10]
0x180056244  mov     rcx, rdi
0x180056247  mov     [rsp+38h+var_18], rax
0x18005624c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180056251  mov     rcx, rbx
0x180056254  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180056259  mov     byte ptr [rbx+150h], 1
0x180056260  mov     rbx, [rsp+38h+arg_0]
0x180056265  add     rsp, 30h
0x180056269  pop     rdi
0x18005626a  retn
```
