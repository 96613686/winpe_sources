# LUATelemetry::FinishPackageActivationActivity::StartActivity(void)

- ea: `0x18000d3b0`
- end: `0x18000d52b`
- name: `?StartActivity@FinishPackageActivationActivity@LUATelemetry@@QEAAXXZ`
- size: `379`
- prototype: `void __fastcall(LUATelemetry::FinishPackageActivationActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180027d78`

## callees

- `0x18000d3b0`
- `0x1800187bc`
- `0x180018a5c`
- `0x180018dcc`
- `0x18001ef50`
- `0x180033c0c`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d415`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d415`

## pseudocode

```c
void __fastcall LUATelemetry::FinishPackageActivationActivity::StartActivity(
        LUATelemetry::FinishPackageActivationActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  const GUID *v7; // rax
  LPCGUID v8; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v10[12]; // [rsp+34h] [rbp-74h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  void *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+6Ch] [rbp-3Ch]
  _BYTE *v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+80h] [rbp-28h]
  __int64 v19; // [rsp+88h] [rbp-20h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = v2;
  if ( *(_DWORD *)v2 > 5u
    && (*((_QWORD *)v2 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v2 + 3) & 0x200000000000LL) == *((_QWORD *)v2 + 3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    *(_QWORD *)&v10[4] = 0;
    v4 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v7 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                         this,
                         v5,
                         v6,
                         v4);
    *(_DWORD *)&EventDescriptor.Level = 261;
    v19 = 4;
    p_CurrentThreadId = &CurrentThreadId;
    v17 = 8;
    v16 = &v10[4];
    UserData.Ptr = *((_QWORD *)v3 + 1);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x200000000000LL;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v13 = &unk_180052AAE;
    UserData.Reserved = 2;
    v14 = 75;
    v15 = 1;
    *(_QWORD *)v10 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v3 + 4), &EventDescriptor, v7, v8, 4u, &UserData);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000d3b0  mov     [rsp+arg_10], rbx
0x18000d3b5  push    rdi
0x18000d3b6  sub     rsp, 0A0h
0x18000d3bd  mov     rax, cs:__security_cookie
0x18000d3c4  xor     rax, rsp
0x18000d3c7  mov     [rsp+0A8h+var_18], rax
0x18000d3cf  mov     rbx, rcx
0x18000d3d2  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000d3d7  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000d3dc  mov     rdi, rax
0x18000d3df  cmp     dword ptr [rax], 5
0x18000d3e2  jbe     loc_18000D501
0x18000d3e8  mov     [rsp+0A8h+arg_8], rsi
0x18000d3f0  mov     rsi, 200000000000h
0x18000d3fa  test    [rax+10h], rsi
0x18000d3fe  jz      loc_18000D4F9
0x18000d404  mov     rcx, [rax+18h]
0x18000d408  and     rcx, rsi
0x18000d40b  cmp     rcx, [rax+18h]
0x18000d40f  jnz     loc_18000D4F9
0x18000d415  call    cs:__imp_GetCurrentThreadId
0x18000d41c  nop     dword ptr [rax+rax+00h]
0x18000d421  xor     edx, edx
0x18000d423  mov     rcx, rbx
0x18000d426  mov     [rsp+0A8h+var_78], eax
0x18000d42a  mov     [rsp+0A8h+var_70], rdx
0x18000d42f  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x18000d434  mov     rcx, rbx
0x18000d437  mov     r9, rax
0x18000d43a  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000d43f  movzx   ecx, cs:word_180052AA4
0x18000d446  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18000d44b  mov     r8, rax; ActivityId
0x18000d44e  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], ecx
0x18000d452  mov     [rsp+0A8h+var_20], 4
0x18000d45e  lea     rax, [rsp+0A8h+var_78]
0x18000d463  mov     [rsp+0A8h+var_28], rax
0x18000d46b  lea     rcx, _TraceLoggingMetadata
0x18000d472  mov     [rsp+0A8h+var_30], 8
0x18000d47b  lea     rax, [rsp+0A8h+var_70]
0x18000d480  mov     [rsp+0A8h+var_38], rax
0x18000d485  mov     rax, [rdi+8]
0x18000d489  mov     [rsp+0A8h+var_58.Ptr], rax
0x18000d48e  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x18000d496  mov     [rsp+0A8h+EventDescriptor.Keyword], rsi
0x18000d49b  movzx   eax, word ptr [rax]
0x18000d49e  mov     [rsp+0A8h+var_58.Size], eax
0x18000d4a2  lea     rax, unk_180052AAE
0x18000d4a9  mov     [rsp+0A8h+var_48], rax
0x18000d4ae  lea     rax, _TraceLoggingMetadataEnd
0x18000d4b5  sub     eax, ecx
0x18000d4b7  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x18000d4bf  mov     [rsp+0A8h+var_40], 4Bh ; 'K'
0x18000d4c7  mov     [rsp+0A8h+var_3C], 1
0x18000d4cf  mov     [rsp+0A8h+var_74], eax
0x18000d4d3  mov     eax, [rsp+0A8h+var_74]
0x18000d4d7  mov     rcx, [rdi+20h]; RegHandle
0x18000d4db  lea     rax, [rsp+0A8h+var_58]
0x18000d4e0  mov     [rsp+0A8h+UserData], rax; UserData
0x18000d4e5  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x18000d4ed  call    cs:__imp_EventWriteTransfer
0x18000d4f4  nop     dword ptr [rax+rax+00h]
0x18000d4f9  mov     rsi, [rsp+0A8h+arg_8]
0x18000d501  mov     rcx, rbx
0x18000d504  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000d509  mov     rcx, [rsp+0A8h+var_18]
0x18000d511  xor     rcx, rsp; StackCookie
0x18000d514  call    __security_check_cookie
0x18000d519  mov     rbx, [rsp+0A8h+arg_10]
0x18000d521  add     rsp, 0A0h
0x18000d528  pop     rdi
0x18000d529  retn
```
