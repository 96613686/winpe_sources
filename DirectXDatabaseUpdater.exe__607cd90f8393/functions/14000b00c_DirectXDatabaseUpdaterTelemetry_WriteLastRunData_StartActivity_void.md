# DirectXDatabaseUpdaterTelemetry::WriteLastRunData::StartActivity(void)

- ea: `0x14000b00c`
- end: `0x14000b0c5`
- name: `?StartActivity@WriteLastRunData@DirectXDatabaseUpdaterTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::WriteLastRunData *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000f2a4`

## callees

- `0x14000187c`
- `0x1400022ec`
- `0x140006df4`
- `0x14000946c`
- `0x14000b00c`
- `0x14000ef38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b047`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::WriteLastRunData::StartActivity(
        DirectXDatabaseUpdaterTelemetry::WriteLastRunData *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = DirectXDatabaseUpdaterLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0x1000000;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_14001EA23,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x14000b00c  mov     [rsp+arg_10], rbx
0x14000b011  push    rdi
0x14000b012  sub     rsp, 30h
0x14000b016  mov     rbx, rcx
0x14000b019  call    ?zInternalStart@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000b01e  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000b023  mov     rdi, rax
0x14000b026  mov     edx, [rax]
0x14000b028  cmp     edx, 5
0x14000b02b  jbe     loc_14000B0B1
0x14000b031  mov     rdx, 400000000000h
0x14000b03b  mov     rcx, rax
0x14000b03e  call    _tlgKeywordOn
0x14000b043  test    al, al
0x14000b045  jz      short loc_14000B0B1
0x14000b047  call    cs:__imp_GetCurrentThreadId
0x14000b04d  mov     [rsp+38h+arg_0], eax
0x14000b051  mov     [rsp+38h+arg_8], 1000000h
0x14000b05a  mov     r8, [rbx+110h]
0x14000b061  cmp     byte ptr [r8+4], 0
0x14000b066  jz      short loc_14000B087
0x14000b068  lea     r9, [r8+18h]
0x14000b06c  cmp     dword ptr [r9], 0
0x14000b070  jnz     short loc_14000B08A
0x14000b072  cmp     dword ptr [r9+4], 0
0x14000b077  jnz     short loc_14000B08A
0x14000b079  cmp     dword ptr [r9+8], 0
0x14000b07e  jnz     short loc_14000B08A
0x14000b080  cmp     dword ptr [r9+0Ch], 0
0x14000b085  jnz     short loc_14000B08A
0x14000b087  xor     r9d, r9d
0x14000b08a  add     r8, 8
0x14000b08e  lea     rax, [rsp+38h+arg_0]
0x14000b093  mov     [rsp+38h+var_10], rax
0x14000b098  lea     rax, [rsp+38h+arg_8]
0x14000b09d  mov     [rsp+38h+var_18], rax
0x14000b0a2  lea     rdx, byte_14001EA23
0x14000b0a9  mov     rcx, rdi
0x14000b0ac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000b0b1  mov     rcx, rbx
0x14000b0b4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14000b0b9  nop
0x14000b0ba  mov     rbx, [rsp+38h+arg_10]
0x14000b0bf  add     rsp, 30h
0x14000b0c3  pop     rdi
0x14000b0c4  retn
```
