# LUATelemetry::GetPackageActivationTokenForAliasActivity::StartActivity(void)

- ea: `0x18000c510`
- end: `0x18000c68b`
- name: `?StartActivity@GetPackageActivationTokenForAliasActivity@LUATelemetry@@QEAAXXZ`
- size: `379`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForAliasActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180028aa4`

## callees

- `0x18000c510`
- `0x18001850c`
- `0x1800187ac`
- `0x180018b1c`
- `0x18001eb10`
- `0x180033b5c`
- `0x180042950`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c64d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c64d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c575`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForAliasActivity::StartActivity(
        LUATelemetry::GetPackageActivationTokenForAliasActivity *this)
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
    v13 = &unk_180051026;
    UserData.Reserved = 2;
    v14 = 85;
    v15 = 1;
    *(_QWORD *)v10 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v3 + 4), &EventDescriptor, v7, v8, 4u, &UserData);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000c510  mov     [rsp+arg_10], rbx
0x18000c515  push    rdi
0x18000c516  sub     rsp, 0A0h
0x18000c51d  mov     rax, cs:__security_cookie
0x18000c524  xor     rax, rsp
0x18000c527  mov     [rsp+0A8h+var_18], rax
0x18000c52f  mov     rbx, rcx
0x18000c532  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000c537  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000c53c  mov     rdi, rax
0x18000c53f  cmp     dword ptr [rax], 5
0x18000c542  jbe     loc_18000C661
0x18000c548  mov     [rsp+0A8h+arg_8], rsi
0x18000c550  mov     rsi, 200000000000h
0x18000c55a  test    [rax+10h], rsi
0x18000c55e  jz      loc_18000C659
0x18000c564  mov     rcx, [rax+18h]
0x18000c568  and     rcx, rsi
0x18000c56b  cmp     rcx, [rax+18h]
0x18000c56f  jnz     loc_18000C659
0x18000c575  call    cs:__imp_GetCurrentThreadId
0x18000c57c  nop     dword ptr [rax+rax+00h]
0x18000c581  xor     edx, edx
0x18000c583  mov     rcx, rbx
0x18000c586  mov     [rsp+0A8h+var_78], eax
0x18000c58a  mov     [rsp+0A8h+var_70], rdx
0x18000c58f  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x18000c594  mov     rcx, rbx
0x18000c597  mov     r9, rax
0x18000c59a  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000c59f  movzx   ecx, cs:word_18005101C
0x18000c5a6  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x18000c5ab  mov     r8, rax; ActivityId
0x18000c5ae  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], ecx
0x18000c5b2  mov     [rsp+0A8h+var_20], 4
0x18000c5be  lea     rax, [rsp+0A8h+var_78]
0x18000c5c3  mov     [rsp+0A8h+var_28], rax
0x18000c5cb  lea     rcx, _TraceLoggingMetadata
0x18000c5d2  mov     [rsp+0A8h+var_30], 8
0x18000c5db  lea     rax, [rsp+0A8h+var_70]
0x18000c5e0  mov     [rsp+0A8h+var_38], rax
0x18000c5e5  mov     rax, [rdi+8]
0x18000c5e9  mov     [rsp+0A8h+var_58.Ptr], rax
0x18000c5ee  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x18000c5f6  mov     [rsp+0A8h+EventDescriptor.Keyword], rsi
0x18000c5fb  movzx   eax, word ptr [rax]
0x18000c5fe  mov     [rsp+0A8h+var_58.Size], eax
0x18000c602  lea     rax, unk_180051026
0x18000c609  mov     [rsp+0A8h+var_48], rax
0x18000c60e  lea     rax, _TraceLoggingMetadataEnd
0x18000c615  sub     eax, ecx
0x18000c617  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x18000c61f  mov     [rsp+0A8h+var_40], 55h ; 'U'
0x18000c627  mov     [rsp+0A8h+var_3C], 1
0x18000c62f  mov     [rsp+0A8h+var_74], eax
0x18000c633  mov     eax, [rsp+0A8h+var_74]
0x18000c637  mov     rcx, [rdi+20h]; RegHandle
0x18000c63b  lea     rax, [rsp+0A8h+var_58]
0x18000c640  mov     [rsp+0A8h+UserData], rax; UserData
0x18000c645  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x18000c64d  call    cs:__imp_EventWriteTransfer
0x18000c654  nop     dword ptr [rax+rax+00h]
0x18000c659  mov     rsi, [rsp+0A8h+arg_8]
0x18000c661  mov     rcx, rbx
0x18000c664  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000c669  mov     rcx, [rsp+0A8h+var_18]
0x18000c671  xor     rcx, rsp; StackCookie
0x18000c674  call    __security_check_cookie
0x18000c679  mov     rbx, [rsp+0A8h+arg_10]
0x18000c681  add     rsp, 0A0h
0x18000c688  pop     rdi
0x18000c689  retn
```
