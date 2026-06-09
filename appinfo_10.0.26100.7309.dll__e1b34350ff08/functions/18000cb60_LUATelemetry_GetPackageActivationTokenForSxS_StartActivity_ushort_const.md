# LUATelemetry::GetPackageActivationTokenForSxS::StartActivity(ushort const *)

- ea: `0x18000cb60`
- end: `0x18000ccfa`
- name: `?StartActivity@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBG@Z`
- size: `410`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForSxS *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180032810`

## callees

- `0x18000cb60`
- `0x1800187bc`
- `0x180018a5c`
- `0x180018dcc`
- `0x18001ef50`
- `0x180033c0c`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ccbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ccbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cbcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cbcb`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForSxS::StartActivity(
        LUATelemetry::GetPackageActivationTokenForSxS *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // edx
  const GUID *v10; // r8
  const GUID *v11; // r9
  __int64 v12; // rcx
  int v14; // ecx
  _DWORD v15[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  void *v19; // [rsp+60h] [rbp-9h]
  int v20; // [rsp+68h] [rbp-1h]
  int v21; // [rsp+6Ch] [rbp+3h]
  __int64 *v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  _DWORD *v24; // [rsp+80h] [rbp+17h]
  __int64 v25; // [rsp+88h] [rbp+1Fh]
  const unsigned __int16 *v26; // [rsp+90h] [rbp+27h]
  int v27; // [rsp+98h] [rbp+2Fh]
  int v28; // [rsp+9Ch] [rbp+33h]

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = LUATelemetry::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u
    && (*((_QWORD *)v4 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v4 + 3) & 0x200000000000LL) == *((_QWORD *)v4 + 3) )
  {
    v15[0] = GetCurrentThreadId();
    v16 = 0;
    v6 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v10 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                          this,
                          v7,
                          v8,
                          v6);
    if ( a2 )
    {
      v12 = -1;
      while ( a2[++v12] != (unsigned __int16)v9 )
        ;
      v14 = 2 * v12 + 2;
    }
    else
    {
      a2 = &String2;
      v14 = 2;
    }
    v27 = v14;
    v24 = v15;
    v28 = v9;
    v22 = &v16;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = *((_QWORD *)v5 + 1);
    v26 = a2;
    v25 = 4;
    v23 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x200000000000LL;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v19 = &unk_18005188C;
    UserData.Reserved = 2;
    v20 = 91;
    v21 = 1;
    v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v5 + 4), &EventDescriptor, v10, v11, 5u, &UserData);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000cb60  mov     [rsp-8+arg_10], rbx
0x18000cb65  push    rbp
0x18000cb66  push    rsi
0x18000cb67  push    rdi
0x18000cb68  lea     rbp, [rsp-47h]
0x18000cb6d  sub     rsp, 0B0h
0x18000cb74  mov     rax, cs:__security_cookie
0x18000cb7b  xor     rax, rsp
0x18000cb7e  mov     [rbp+57h+var_20], rax
0x18000cb82  mov     rbx, rdx
0x18000cb85  mov     rdi, rcx
0x18000cb88  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000cb8d  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000cb92  mov     rsi, rax
0x18000cb95  cmp     dword ptr [rax], 5
0x18000cb98  jbe     loc_18000CCD2
0x18000cb9e  mov     [rsp+0C0h+arg_8], r14
0x18000cba6  mov     r14, 200000000000h
0x18000cbb0  test    [rax+10h], r14
0x18000cbb4  jz      loc_18000CCCA
0x18000cbba  mov     rcx, [rax+18h]
0x18000cbbe  and     rcx, r14
0x18000cbc1  cmp     rcx, [rax+18h]
0x18000cbc5  jnz     loc_18000CCCA
0x18000cbcb  call    cs:__imp_GetCurrentThreadId
0x18000cbd2  nop     dword ptr [rax+rax+00h]
0x18000cbd7  xor     edx, edx
0x18000cbd9  mov     rcx, rdi
0x18000cbdc  mov     [rbp+57h+var_90], eax
0x18000cbdf  mov     [rbp+57h+var_88], rdx
0x18000cbe3  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x18000cbe8  mov     rcx, rdi
0x18000cbeb  mov     r9, rax
0x18000cbee  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000cbf3  mov     r8, rax; ActivityId
0x18000cbf6  test    rbx, rbx
0x18000cbf9  jz      short loc_18000CC16
0x18000cbfb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cc02  cmp     [rbx+rcx*2+2], dx
0x18000cc07  lea     rcx, [rcx+1]
0x18000cc0b  jnz     short loc_18000CC02
0x18000cc0d  lea     ecx, ds:2[rcx*2]
0x18000cc14  jmp     short loc_18000CC22
0x18000cc16  lea     rbx, String2
0x18000cc1d  mov     ecx, 2
0x18000cc22  mov     [rbp+57h+var_28], ecx
0x18000cc25  lea     rax, [rbp+57h+var_90]
0x18000cc29  mov     [rbp+57h+var_40], rax
0x18000cc2d  lea     rcx, _TraceLoggingMetadata
0x18000cc34  mov     [rbp+57h+var_24], edx
0x18000cc37  lea     rax, [rbp+57h+var_88]
0x18000cc3b  mov     [rbp+57h+var_50], rax
0x18000cc3f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000cc43  movzx   eax, cs:word_180051882
0x18000cc4a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000cc4d  mov     rax, [rsi+8]
0x18000cc51  mov     [rbp+57h+var_70.Ptr], rax
0x18000cc55  mov     [rbp+57h+var_30], rbx
0x18000cc59  mov     [rbp+57h+var_38], 4
0x18000cc61  mov     [rbp+57h+var_48], 8
0x18000cc69  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000cc70  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x18000cc74  movzx   eax, word ptr [rax]
0x18000cc77  mov     [rbp+57h+var_70.Size], eax
0x18000cc7a  lea     rax, unk_18005188C
0x18000cc81  mov     [rbp+57h+var_60], rax
0x18000cc85  lea     rax, _TraceLoggingMetadataEnd
0x18000cc8c  sub     eax, ecx
0x18000cc8e  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x18000cc95  mov     [rbp+57h+var_58], 5Bh ; '['
0x18000cc9c  mov     [rbp+57h+var_54], 1
0x18000cca3  mov     [rbp+57h+var_8C], eax
0x18000cca6  mov     eax, [rbp+57h+var_8C]
0x18000cca9  mov     rcx, [rsi+20h]; RegHandle
0x18000ccad  lea     rax, [rbp+57h+var_70]
0x18000ccb1  mov     [rsp+0C0h+UserData], rax; UserData
0x18000ccb6  mov     [rsp+0C0h+UserDataCount], 5; UserDataCount
0x18000ccbe  call    cs:__imp_EventWriteTransfer
0x18000ccc5  nop     dword ptr [rax+rax+00h]
0x18000ccca  mov     r14, [rsp+0C0h+arg_8]
0x18000ccd2  mov     rcx, rdi
0x18000ccd5  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000ccda  mov     rcx, [rbp+57h+var_20]
0x18000ccde  xor     rcx, rsp; StackCookie
0x18000cce1  call    __security_check_cookie
0x18000cce6  mov     rbx, [rsp+0C0h+arg_10]
0x18000ccee  add     rsp, 0B0h
0x18000ccf5  pop     rdi
0x18000ccf6  pop     rsi
0x18000ccf7  pop     rbp
0x18000ccf8  retn
```
