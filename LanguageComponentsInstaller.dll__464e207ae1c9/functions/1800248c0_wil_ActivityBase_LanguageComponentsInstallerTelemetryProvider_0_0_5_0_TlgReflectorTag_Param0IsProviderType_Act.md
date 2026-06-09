# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x1800248c0`
- end: `0x180024931`
- name: `??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800249b8`
- `0x1800249e4`
- `0x180025d20`
- `0x180026020`

## callees

- `0x180003a34`
- `0x180013494`
- `0x1800248c0`
- `0x180024938`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
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
        wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x1800248c0  mov     [rsp+arg_0], rbx
0x1800248c5  push    rdi
0x1800248c6  sub     rsp, 20h
0x1800248ca  mov     rbx, rcx
0x1800248cd  add     rcx, 120h; this
0x1800248d4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800248d9  mov     rcx, [rbx+118h]
0x1800248e0  test    rcx, rcx
0x1800248e3  jz      short loc_18002491E
0x1800248e5  or      eax, 0FFFFFFFFh
0x1800248e8  lock xadd [rcx], eax
0x1800248ec  cmp     eax, 1
0x1800248ef  jnz     short loc_180024913
0x1800248f1  mov     rdi, [rbx+118h]
0x1800248f8  test    rdi, rdi
0x1800248fb  jz      short loc_180024913
0x1800248fd  lea     rcx, [rdi+8]
0x180024901  call    ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024906  mov     edx, 110h
0x18002490b  mov     rcx, rdi; Block
0x18002490e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024913  mov     qword ptr [rbx+118h], 0
0x18002491e  lea     rcx, [rbx+8]
0x180024922  mov     rbx, [rsp+28h+arg_0]
0x180024927  add     rsp, 20h
0x18002492b  pop     rdi
0x18002492c  jmp     ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
```
