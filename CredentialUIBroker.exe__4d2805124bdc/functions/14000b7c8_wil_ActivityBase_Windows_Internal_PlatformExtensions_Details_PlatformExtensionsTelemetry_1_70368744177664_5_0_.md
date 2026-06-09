# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x14000b7c8`
- end: `0x14000b893`
- name: `?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `203`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140009734`

## callees

- `0x1400042c4`
- `0x140009158`
- `0x14000b7c8`
- `0x14000ed00`
- `0x140012f50`
- `0x1400178c8`
- `0x14001aea8`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
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
0x14000b7c8  mov     rax, rsp
0x14000b7cb  mov     [rax+10h], rbx
0x14000b7cf  mov     [rax+18h], rsi
0x14000b7d3  push    rdi
0x14000b7d4  sub     rsp, 0C0h
0x14000b7db  lea     rdi, [rcx+118h]
0x14000b7e2  mov     rbx, rcx
0x14000b7e5  cmp     qword ptr [rdi], 0
0x14000b7e9  jz      short loc_14000B823
0x14000b7eb  lea     rdx, [rax+8]
0x14000b7ef  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b7f4  mov     rax, [rdi]
0x14000b7f7  test    rax, rax
0x14000b7fa  jz      short loc_14000B806
0x14000b7fc  cmp     dword ptr [rax], 1
0x14000b7ff  jnz     short loc_14000B806
0x14000b801  mov     sil, 1
0x14000b804  jmp     short loc_14000B811
0x14000b806  xor     sil, sil
0x14000b809  mov     rcx, rdi
0x14000b80c  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14000b811  lea     rcx, [rsp+0C8h+arg_0]
0x14000b819  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b81e  test    sil, sil
0x14000b821  jz      short loc_14000B87E
0x14000b823  mov     rcx, [rbx+110h]
0x14000b82a  cmp     dword ptr [rcx], 1
0x14000b82d  jnz     short loc_14000B87E
0x14000b82f  cmp     dword ptr [rcx+58h], 0
0x14000b833  mov     eax, 8007023Eh
0x14000b838  mov     edx, [rcx+0F8h]
0x14000b83e  cmovl   eax, [rcx+58h]
0x14000b842  cmp     edx, 1
0x14000b845  jge     short loc_14000B864
0x14000b847  xor     edx, edx; Val
0x14000b849  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000b84e  mov     r8d, 98h; Size
0x14000b854  call    memset_0
0x14000b859  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b85e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000b864  cmp     dword ptr [rcx+48h], 0
0x14000b868  jl      short loc_14000B86D
0x14000b86a  mov     [rcx+48h], eax
0x14000b86d  lea     eax, [rdx-1]
0x14000b870  mov     [rcx+0F8h], eax
0x14000b876  mov     rcx, rbx
0x14000b879  call    ?ReportStopActivity@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14000b87e  lea     r11, [rsp+0C8h+var_8]
0x14000b886  mov     rbx, [r11+18h]
0x14000b88a  mov     rsi, [r11+20h]
0x14000b88e  mov     rsp, r11
0x14000b891  pop     rdi
0x14000b892  retn
```
