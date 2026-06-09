# WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StartActivity(ushort const *,_FILETIME const &)

- ea: `0x18001428c`
- end: `0x18001437a`
- name: `?StartActivity@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAXPEBGAEBU_FILETIME@@@Z`
- size: `238`
- prototype: `void __fastcall(WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *__hidden this, const unsigned __int16 *, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800121b0`

## callees

- `0x18000ee64`
- `0x18001428c`
- `0x180019e40`
- `0x18001c4e4`
- `0x18001f670`
- `0x1800202bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800142e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800142e5`

## pseudocode

```c
void __fastcall WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StartActivity(
        WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *this,
        char *a2,
        const struct _FILETIME *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  const GUID *v10; // r9
  char *v11; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v12[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v13; // [rsp+70h] [rbp+8h] BYREF
  __int64 v14; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WiFiCloudStoreTelemetry::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
  {
    v14 = (__int64)*a3;
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v12[0] = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = (const GUID *)(v9 + 24), !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v7,
      (unsigned __int8 *)word_180046A9A,
      (const GUID *)(v9 + 8),
      v10,
      (__int64)v12,
      (__int64)&v13,
      &v11,
      (__int64)&v14);
  }
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001428c  mov     [rsp+arg_8], rbx
0x180014291  push    rbp
0x180014292  push    rsi
0x180014293  push    rdi
0x180014294  sub     rsp, 50h
0x180014298  mov     rsi, r8
0x18001429b  mov     rbp, rdx
0x18001429e  mov     rbx, rcx
0x1800142a1  call    ?zInternalStart@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800142a6  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x1800142ab  mov     rdi, rax
0x1800142ae  mov     r9d, [rax]
0x1800142b1  cmp     r9d, 5
0x1800142b5  jbe     loc_180014366
0x1800142bb  mov     rdx, 400000000000h
0x1800142c5  mov     rcx, rax
0x1800142c8  call    _tlgKeywordOn
0x1800142cd  test    al, al
0x1800142cf  jz      loc_180014366
0x1800142d5  mov     rcx, [rsi]
0x1800142d8  mov     [rsp+68h+arg_18], rcx
0x1800142e0  mov     [rsp+68h+var_28], rbp
0x1800142e5  call    cs:__imp_GetCurrentThreadId
0x1800142eb  mov     r8, [rbx+110h]
0x1800142f2  mov     [rsp+68h+arg_0], eax
0x1800142f6  mov     [rsp+68h+var_20], 0
0x1800142ff  cmp     byte ptr [r8+4], 0
0x180014304  jz      short loc_180014325
0x180014306  lea     r9, [r8+18h]
0x18001430a  cmp     dword ptr [r9], 0
0x18001430e  jnz     short loc_180014328
0x180014310  cmp     dword ptr [r9+4], 0
0x180014315  jnz     short loc_180014328
0x180014317  cmp     dword ptr [r9+8], 0
0x18001431c  jnz     short loc_180014328
0x18001431e  cmp     dword ptr [r9+0Ch], 0
0x180014323  jnz     short loc_180014328
0x180014325  xor     r9d, r9d
0x180014328  lea     rax, [rsp+68h+arg_18]
0x180014330  add     r8, 8
0x180014334  mov     [rsp+68h+var_30], rax
0x180014339  lea     rdx, word_180046A9A
0x180014340  lea     rax, [rsp+68h+var_28]
0x180014345  mov     rcx, rdi
0x180014348  mov     [rsp+68h+var_38], rax
0x18001434d  lea     rax, [rsp+68h+arg_0]
0x180014352  mov     [rsp+68h+var_40], rax
0x180014357  lea     rax, [rsp+68h+var_20]
0x18001435c  mov     [rsp+68h+var_48], rax
0x180014361  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180014366  mov     rcx, rbx
0x180014369  mov     rbx, [rsp+68h+arg_8]
0x18001436e  add     rsp, 50h
0x180014372  pop     rdi
0x180014373  pop     rsi
0x180014374  pop     rbp
0x180014375  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
