# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x14000b6f4`
- end: `0x14000b7bf`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `203`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140009760`

## callees

- `0x1400042c4`
- `0x140009158`
- `0x14000b6f4`
- `0x14000ed00`
- `0x140012f50`
- `0x1400178c8`
- `0x14001ae50`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        __int64 a1)
{
  _QWORD *v1; // rdi
  char v3; // si
  _DWORD *v4; // rcx
  int v5; // eax
  int v6; // edx
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[160]; // [rsp+20h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+D0h] [rbp+8h] BYREF

  v1 = (_QWORD *)(a1 + 280);
  if ( !*(_QWORD *)(a1 + 280) )
    goto LABEL_17;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v9);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v3 )
  {
LABEL_17:
    v4 = *(_DWORD **)(a1 + 272);
    if ( *v4 == 1 )
    {
      v5 = -2147024322;
      v6 = v4[62];
      if ( (int)v4[22] < 0 )
        v5 = v4[22];
      if ( v6 < 1 )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      if ( (int)v4[18] >= 0 )
        v4[18] = v5;
      v4[62] = v6 - 1;
      wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
}

```

## disassembly

```asm
0x14000b6f4  mov     rax, rsp
0x14000b6f7  mov     [rax+10h], rbx
0x14000b6fb  mov     [rax+18h], rsi
0x14000b6ff  push    rdi
0x14000b700  sub     rsp, 0C0h
0x14000b707  lea     rdi, [rcx+118h]
0x14000b70e  mov     rbx, rcx
0x14000b711  cmp     qword ptr [rdi], 0
0x14000b715  jz      short loc_14000B74F
0x14000b717  lea     rdx, [rax+8]
0x14000b71b  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b720  mov     rax, [rdi]
0x14000b723  test    rax, rax
0x14000b726  jz      short loc_14000B732
0x14000b728  cmp     dword ptr [rax], 1
0x14000b72b  jnz     short loc_14000B732
0x14000b72d  mov     sil, 1
0x14000b730  jmp     short loc_14000B73D
0x14000b732  xor     sil, sil
0x14000b735  mov     rcx, rdi
0x14000b738  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14000b73d  lea     rcx, [rsp+0C8h+arg_0]
0x14000b745  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b74a  test    sil, sil
0x14000b74d  jz      short loc_14000B7AA
0x14000b74f  mov     rcx, [rbx+110h]
0x14000b756  cmp     dword ptr [rcx], 1
0x14000b759  jnz     short loc_14000B7AA
0x14000b75b  cmp     dword ptr [rcx+58h], 0
0x14000b75f  mov     eax, 8007023Eh
0x14000b764  mov     edx, [rcx+0F8h]
0x14000b76a  cmovl   eax, [rcx+58h]
0x14000b76e  cmp     edx, 1
0x14000b771  jge     short loc_14000B790
0x14000b773  xor     edx, edx; Val
0x14000b775  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000b77a  mov     r8d, 98h; Size
0x14000b780  call    memset_0
0x14000b785  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b78a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000b790  cmp     dword ptr [rcx+48h], 0
0x14000b794  jl      short loc_14000B799
0x14000b796  mov     [rcx+48h], eax
0x14000b799  lea     eax, [rdx-1]
0x14000b79c  mov     [rcx+0F8h], eax
0x14000b7a2  mov     rcx, rbx
0x14000b7a5  call    ?ReportStopActivity@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14000b7aa  lea     r11, [rsp+0C8h+var_8]
0x14000b7b2  mov     rbx, [r11+18h]
0x14000b7b6  mov     rsi, [r11+20h]
0x14000b7ba  mov     rsp, r11
0x14000b7bd  pop     rdi
0x14000b7be  retn
```
