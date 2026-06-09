# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x18000fb4c`
- end: `0x18000fc18`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `204`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e154`

## callees

- `0x180003bc8`
- `0x180005568`
- `0x18000a668`
- `0x18000fb4c`
- `0x1800123bc`
- `0x1800140c0`
- `0x1800188a4`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(p_pUserDefined);
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
0x18000fb4c  mov     rax, rsp
0x18000fb4f  mov     [rax+10h], rbx
0x18000fb53  mov     [rax+18h], rsi
0x18000fb57  push    rdi
0x18000fb58  sub     rsp, 0C0h
0x18000fb5f  mov     rbx, rcx
0x18000fb62  lea     rdi, [rcx+118h]
0x18000fb69  cmp     qword ptr [rdi], 0
0x18000fb6d  jz      short loc_18000FBA7
0x18000fb6f  lea     rdx, [rax+8]
0x18000fb73  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fb78  mov     rax, [rdi]
0x18000fb7b  test    rax, rax
0x18000fb7e  jz      short loc_18000FB8A
0x18000fb80  cmp     dword ptr [rax], 1
0x18000fb83  jnz     short loc_18000FB8A
0x18000fb85  mov     sil, 1
0x18000fb88  jmp     short loc_18000FB95
0x18000fb8a  xor     sil, sil
0x18000fb8d  mov     rcx, rdi
0x18000fb90  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000fb95  lea     rcx, [rsp+0C8h+arg_0]
0x18000fb9d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000fba2  test    sil, sil
0x18000fba5  jz      short loc_18000FC03
0x18000fba7  mov     rcx, [rbx+110h]
0x18000fbae  cmp     dword ptr [rcx], 1
0x18000fbb1  jnz     short loc_18000FC03
0x18000fbb3  mov     eax, 8007023Eh
0x18000fbb8  cmp     dword ptr [rcx+58h], 0
0x18000fbbc  cmovl   eax, [rcx+58h]
0x18000fbc0  mov     edx, [rcx+0F8h]
0x18000fbc6  cmp     edx, 1
0x18000fbc9  jge     short loc_18000FBE8
0x18000fbcb  xor     edx, edx; Val
0x18000fbcd  mov     r8d, 98h; Size
0x18000fbd3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000fbd8  call    memset_0
0x18000fbdd  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000fbe2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000fbe8  cmp     dword ptr [rcx+48h], 0
0x18000fbec  jl      short loc_18000FBF1
0x18000fbee  mov     [rcx+48h], eax
0x18000fbf1  lea     eax, [rdx-1]
0x18000fbf4  mov     [rcx+0F8h], eax
0x18000fbfa  mov     rcx, rbx; struct tagComCallData *
0x18000fbfd  call    ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x18000fc02  nop
0x18000fc03  lea     r11, [rsp+0C8h+var_8]
0x18000fc0b  mov     rbx, [r11+18h]
0x18000fc0f  mov     rsi, [r11+20h]
0x18000fc13  mov     rsp, r11
0x18000fc16  pop     rdi
0x18000fc17  retn
```
