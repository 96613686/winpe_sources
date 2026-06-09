# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x18000fa78`
- end: `0x18000fb44`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `204`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e180`

## callees

- `0x180003bc8`
- `0x180005568`
- `0x18000a668`
- `0x18000fa78`
- `0x1800123bc`
- `0x1800140c0`
- `0x18001884c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        struct tagComCallData *a1)
{
  void **p_pUserDefined; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  int v5; // eax
  int v6; // edx
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+D0h] [rbp+8h] BYREF

  p_pUserDefined = &a1[17].pUserDefined;
  if ( !a1[17].pUserDefined )
    goto LABEL_17;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v9);
  if ( *p_pUserDefined && *(_DWORD *)*p_pUserDefined == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(p_pUserDefined);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v3 )
  {
LABEL_17:
    v4 = *(_DWORD **)&a1[17].dwDispid;
    if ( *v4 == 1 )
    {
      v5 = -2147024322;
      if ( (int)v4[22] < 0 )
        v5 = v4[22];
      v6 = v4[62];
      if ( v6 < 1 )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      if ( (int)v4[18] >= 0 )
        v4[18] = v5;
      v4[62] = v6 - 1;
      Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(a1);
    }
  }
}

```

## disassembly

```asm
0x18000fa78  mov     rax, rsp
0x18000fa7b  mov     [rax+10h], rbx
0x18000fa7f  mov     [rax+18h], rsi
0x18000fa83  push    rdi
0x18000fa84  sub     rsp, 0C0h
0x18000fa8b  mov     rbx, rcx
0x18000fa8e  lea     rdi, [rcx+118h]
0x18000fa95  cmp     qword ptr [rdi], 0
0x18000fa99  jz      short loc_18000FAD3
0x18000fa9b  lea     rdx, [rax+8]
0x18000fa9f  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000faa4  mov     rax, [rdi]
0x18000faa7  test    rax, rax
0x18000faaa  jz      short loc_18000FAB6
0x18000faac  cmp     dword ptr [rax], 1
0x18000faaf  jnz     short loc_18000FAB6
0x18000fab1  mov     sil, 1
0x18000fab4  jmp     short loc_18000FAC1
0x18000fab6  xor     sil, sil
0x18000fab9  mov     rcx, rdi
0x18000fabc  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000fac1  lea     rcx, [rsp+0C8h+arg_0]
0x18000fac9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000face  test    sil, sil
0x18000fad1  jz      short loc_18000FB2F
0x18000fad3  mov     rcx, [rbx+110h]
0x18000fada  cmp     dword ptr [rcx], 1
0x18000fadd  jnz     short loc_18000FB2F
0x18000fadf  mov     eax, 8007023Eh
0x18000fae4  cmp     dword ptr [rcx+58h], 0
0x18000fae8  cmovl   eax, [rcx+58h]
0x18000faec  mov     edx, [rcx+0F8h]
0x18000faf2  cmp     edx, 1
0x18000faf5  jge     short loc_18000FB14
0x18000faf7  xor     edx, edx; Val
0x18000faf9  mov     r8d, 98h; Size
0x18000faff  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000fb04  call    memset_0
0x18000fb09  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000fb0e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000fb14  cmp     dword ptr [rcx+48h], 0
0x18000fb18  jl      short loc_18000FB1D
0x18000fb1a  mov     [rcx+48h], eax
0x18000fb1d  lea     eax, [rdx-1]
0x18000fb20  mov     [rcx+0F8h], eax
0x18000fb26  mov     rcx, rbx; struct tagComCallData *
0x18000fb29  call    ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x18000fb2e  nop
0x18000fb2f  lea     r11, [rsp+0C8h+var_8]
0x18000fb37  mov     rbx, [r11+18h]
0x18000fb3b  mov     rsi, [r11+20h]
0x18000fb3f  mov     rsp, r11
0x18000fb42  pop     rdi
0x18000fb43  retn
```
