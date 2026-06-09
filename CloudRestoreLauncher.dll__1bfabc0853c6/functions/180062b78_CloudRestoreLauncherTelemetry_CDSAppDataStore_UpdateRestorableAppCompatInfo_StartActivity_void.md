# CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo::StartActivity(void)

- ea: `0x180062b78`
- end: `0x180062c07`
- name: `?StartActivity@CDSAppDataStore_UpdateRestorableAppCompatInfo@CloudRestoreLauncherTelemetry@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180064870`

## callees

- `0x180001628`
- `0x180017a5c`
- `0x1800195cc`
- `0x18001d124`
- `0x1800460d8`
- `0x180062b78`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180062b99`
- `KERNEL32!GetCurrentThreadId` at `0x180062b99`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo::StartActivity(
        CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = CloudRestoreLauncherTelemetry::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4) || _tlgGuidIsZero((const struct _GUID *)(v4 + 24)) )
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_180152F18,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180062b78  mov     [rsp+arg_10], rbx
0x180062b7d  push    rdi
0x180062b7e  sub     rsp, 30h
0x180062b82  mov     rbx, rcx
0x180062b85  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180062b8a  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180062b8f  mov     rdi, rax
0x180062b92  mov     edx, [rax]
0x180062b94  cmp     edx, 5
0x180062b97  jbe     short loc_180062BF3
0x180062b99  call    cs:__imp_GetCurrentThreadId
0x180062b9f  mov     [rsp+38h+arg_0], eax
0x180062ba3  mov     [rsp+38h+arg_8], 0
0x180062bac  mov     r8, [rbx+110h]
0x180062bb3  cmp     byte ptr [r8+4], 0
0x180062bb8  jz      short loc_180062BC7
0x180062bba  lea     rcx, [r8+18h]; struct _GUID *
0x180062bbe  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180062bc3  test    al, al
0x180062bc5  jz      short loc_180062BC9
0x180062bc7  xor     ecx, ecx
0x180062bc9  add     r8, 8
0x180062bcd  lea     rax, [rsp+38h+arg_0]
0x180062bd2  mov     [rsp+38h+var_10], rax
0x180062bd7  lea     rax, [rsp+38h+arg_8]
0x180062bdc  mov     [rsp+38h+var_18], rax
0x180062be1  mov     r9, rcx
0x180062be4  lea     rdx, unk_180152F18
0x180062beb  mov     rcx, rdi
0x180062bee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180062bf3  mov     rcx, rbx
0x180062bf6  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180062bfb  nop
0x180062bfc  mov     rbx, [rsp+38h+arg_10]
0x180062c01  add     rsp, 30h
0x180062c05  pop     rdi
0x180062c06  retn
```
