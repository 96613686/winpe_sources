# WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(ushort const *,ushort const *,_FILETIME const &)

- ea: `0x180013f18`
- end: `0x180014026`
- name: `?StartActivity@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXPEBG0AEBU_FILETIME@@@Z`
- size: `270`
- prototype: `void __fastcall(WiFiCloudStoreTelemetry::WlanTriggeredSync *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _FILETIME *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800121b0`
- `0x180012fb4`

## callees

- `0x18000ee64`
- `0x180013f18`
- `0x180019e40`
- `0x18001a0d8`
- `0x18001f670`
- `0x1800202bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f7c`

## pseudocode

```c
void __fastcall WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(
        WiFiCloudStoreTelemetry::WlanTriggeredSync *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _FILETIME *a4)
{
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // [rsp+58h] [rbp-30h] BYREF
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-20h] BYREF
  DWORD v15; // [rsp+90h] [rbp+8h] BYREF

  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v7 = WiFiCloudStoreTelemetry::Provider();
  v8 = (__int64)v7;
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
  {
    v12 = a3;
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v8,
      (__int64)byte_180046AF9,
      v10 + 8,
      v11,
      (__int64)&v14,
      (__int64)&v15,
      &v13,
      &v12);
  }
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180013f18  mov     [rsp+arg_8], rbx
0x180013f1d  mov     [rsp+arg_10], rbp
0x180013f22  push    rsi
0x180013f23  push    rdi
0x180013f24  push    r14
0x180013f26  sub     rsp, 70h
0x180013f2a  mov     rsi, r9
0x180013f2d  mov     rbp, r8
0x180013f30  mov     r14, rdx
0x180013f33  mov     rbx, rcx
0x180013f36  call    ?zInternalStart@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180013f3b  call    ?Provider@WiFiCloudStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; WiFiCloudStoreTelemetry::Provider(void)
0x180013f40  mov     rdi, rax
0x180013f43  mov     r10d, [rax]
0x180013f46  cmp     r10d, 5
0x180013f4a  jbe     loc_18001400A
0x180013f50  mov     rdx, 400000000000h
0x180013f5a  mov     rcx, rax
0x180013f5d  call    _tlgKeywordOn
0x180013f62  test    al, al
0x180013f64  jz      loc_18001400A
0x180013f6a  mov     rcx, [rsi]
0x180013f6d  mov     [rsp+88h+var_38], rcx
0x180013f72  mov     [rsp+88h+var_30], rbp
0x180013f77  mov     [rsp+88h+var_28], r14
0x180013f7c  call    cs:__imp_GetCurrentThreadId
0x180013f82  mov     r8, [rbx+110h]
0x180013f89  mov     [rsp+88h+arg_0], eax
0x180013f90  mov     [rsp+88h+var_20], 0
0x180013f99  cmp     byte ptr [r8+4], 0
0x180013f9e  jz      short loc_180013FBF
0x180013fa0  lea     r9, [r8+18h]
0x180013fa4  cmp     dword ptr [r9], 0
0x180013fa8  jnz     short loc_180013FC2
0x180013faa  cmp     dword ptr [r9+4], 0
0x180013faf  jnz     short loc_180013FC2
0x180013fb1  cmp     dword ptr [r9+8], 0
0x180013fb6  jnz     short loc_180013FC2
0x180013fb8  cmp     dword ptr [r9+0Ch], 0
0x180013fbd  jnz     short loc_180013FC2
0x180013fbf  xor     r9d, r9d
0x180013fc2  lea     rax, [rsp+88h+var_38]
0x180013fc7  add     r8, 8
0x180013fcb  mov     [rsp+88h+var_48], rax
0x180013fd0  lea     rdx, byte_180046AF9
0x180013fd7  lea     rax, [rsp+88h+var_30]
0x180013fdc  mov     rcx, rdi
0x180013fdf  mov     [rsp+88h+var_50], rax
0x180013fe4  lea     rax, [rsp+88h+var_28]
0x180013fe9  mov     [rsp+88h+var_58], rax
0x180013fee  lea     rax, [rsp+88h+arg_0]
0x180013ff6  mov     [rsp+88h+var_60], rax
0x180013ffb  lea     rax, [rsp+88h+var_20]
0x180014000  mov     [rsp+88h+var_68], rax
0x180014005  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@53@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18001400a  mov     rcx, rbx
0x18001400d  lea     r11, [rsp+88h+var_18]
0x180014012  mov     rbx, [r11+28h]
0x180014016  mov     rbp, [r11+30h]
0x18001401a  mov     rsp, r11
0x18001401d  pop     r14
0x18001401f  pop     rdi
0x180014020  pop     rsi
0x180014021  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
