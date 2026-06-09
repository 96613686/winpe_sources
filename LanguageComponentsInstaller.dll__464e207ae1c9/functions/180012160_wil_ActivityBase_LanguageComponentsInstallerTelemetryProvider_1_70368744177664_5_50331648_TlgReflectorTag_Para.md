# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180012160`
- end: `0x1800121d1`
- name: `??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180013288`
- `0x180013514`
- `0x1800140e0`
- `0x180014788`

## callees

- `0x180003a34`
- `0x180012160`
- `0x1800121d8`
- `0x180013494`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rcx
  char *v3; // rdi

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v2 = *(volatile signed __int32 **)(a1 + 280);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *(char **)(a1 + 280);
      if ( v3 )
      {
        wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x180012160  mov     [rsp+arg_0], rbx
0x180012165  push    rdi
0x180012166  sub     rsp, 20h
0x18001216a  mov     rbx, rcx
0x18001216d  add     rcx, 120h; this
0x180012174  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180012179  mov     rcx, [rbx+118h]
0x180012180  test    rcx, rcx
0x180012183  jz      short loc_1800121BE
0x180012185  or      eax, 0FFFFFFFFh
0x180012188  lock xadd [rcx], eax
0x18001218c  cmp     eax, 1
0x18001218f  jnz     short loc_1800121B3
0x180012191  mov     rdi, [rbx+118h]
0x180012198  test    rdi, rdi
0x18001219b  jz      short loc_1800121B3
0x18001219d  lea     rcx, [rdi+8]
0x1800121a1  call    ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800121a6  mov     edx, 110h
0x1800121ab  mov     rcx, rdi; Block
0x1800121ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800121b3  mov     qword ptr [rbx+118h], 0
0x1800121be  lea     rcx, [rbx+8]
0x1800121c2  mov     rbx, [rsp+28h+arg_0]
0x1800121c7  add     rsp, 20h
0x1800121cb  pop     rdi
0x1800121cc  jmp     ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
```
