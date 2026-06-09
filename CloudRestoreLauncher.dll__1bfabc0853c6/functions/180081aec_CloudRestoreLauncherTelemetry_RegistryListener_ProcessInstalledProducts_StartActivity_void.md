# CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts::StartActivity(void)

- ea: `0x180081aec`
- end: `0x180081b7b`
- name: `?StartActivity@RegistryListener_ProcessInstalledProducts@CloudRestoreLauncherTelemetry@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180081910`

## callees

- `0x180001628`
- `0x180017a5c`
- `0x1800195cc`
- `0x18001d124`
- `0x1800460d8`
- `0x180081aec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180081b0d`
- `KERNEL32!GetCurrentThreadId` at `0x180081b0d`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts::StartActivity(
        CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts *this)
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
      (unsigned int)&word_180156026,
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
0x180081aec  mov     [rsp+arg_10], rbx
0x180081af1  push    rdi
0x180081af2  sub     rsp, 30h
0x180081af6  mov     rbx, rcx
0x180081af9  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180081afe  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180081b03  mov     rdi, rax
0x180081b06  mov     edx, [rax]
0x180081b08  cmp     edx, 5
0x180081b0b  jbe     short loc_180081B67
0x180081b0d  call    cs:__imp_GetCurrentThreadId
0x180081b13  mov     [rsp+38h+arg_0], eax
0x180081b17  mov     [rsp+38h+arg_8], 0
0x180081b20  mov     r8, [rbx+110h]
0x180081b27  cmp     byte ptr [r8+4], 0
0x180081b2c  jz      short loc_180081B3B
0x180081b2e  lea     rcx, [r8+18h]; struct _GUID *
0x180081b32  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180081b37  test    al, al
0x180081b39  jz      short loc_180081B3D
0x180081b3b  xor     ecx, ecx
0x180081b3d  add     r8, 8
0x180081b41  lea     rax, [rsp+38h+arg_0]
0x180081b46  mov     [rsp+38h+var_10], rax
0x180081b4b  lea     rax, [rsp+38h+arg_8]
0x180081b50  mov     [rsp+38h+var_18], rax
0x180081b55  mov     r9, rcx
0x180081b58  lea     rdx, word_180156026
0x180081b5f  mov     rcx, rdi
0x180081b62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180081b67  mov     rcx, rbx
0x180081b6a  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180081b6f  nop
0x180081b70  mov     rbx, [rsp+38h+arg_10]
0x180081b75  add     rsp, 30h
0x180081b79  pop     rdi
0x180081b7a  retn
```
