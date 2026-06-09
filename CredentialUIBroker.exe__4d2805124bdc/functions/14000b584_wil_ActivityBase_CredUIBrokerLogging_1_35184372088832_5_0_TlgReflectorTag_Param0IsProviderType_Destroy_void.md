# wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x14000b584`
- end: `0x14000b64f`
- name: `?Destroy@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `203`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140009254`
- `0x140009280`

## callees

- `0x1400042c4`
- `0x140009158`
- `0x14000b584`
- `0x14000ed00`
- `0x140012f50`
- `0x1400178c8`
- `0x14001ada0`

## pseudocode

```c
void __fastcall wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
    wil::details::shared_object<wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUIBrokerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
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
0x14000b584  mov     rax, rsp
0x14000b587  mov     [rax+10h], rbx
0x14000b58b  mov     [rax+18h], rsi
0x14000b58f  push    rdi
0x14000b590  sub     rsp, 0C0h
0x14000b597  lea     rdi, [rcx+118h]
0x14000b59e  mov     rbx, rcx
0x14000b5a1  cmp     qword ptr [rdi], 0
0x14000b5a5  jz      short loc_14000B5DF
0x14000b5a7  lea     rdx, [rax+8]
0x14000b5ab  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b5b0  mov     rax, [rdi]
0x14000b5b3  test    rax, rax
0x14000b5b6  jz      short loc_14000B5C2
0x14000b5b8  cmp     dword ptr [rax], 1
0x14000b5bb  jnz     short loc_14000B5C2
0x14000b5bd  mov     sil, 1
0x14000b5c0  jmp     short loc_14000B5CD
0x14000b5c2  xor     sil, sil
0x14000b5c5  mov     rcx, rdi
0x14000b5c8  call    ?reset@?$shared_object@V?$ActivityData@VCredUIBrokerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CredUIBrokerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14000b5cd  lea     rcx, [rsp+0C8h+arg_0]
0x14000b5d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b5da  test    sil, sil
0x14000b5dd  jz      short loc_14000B63A
0x14000b5df  mov     rcx, [rbx+110h]
0x14000b5e6  cmp     dword ptr [rcx], 1
0x14000b5e9  jnz     short loc_14000B63A
0x14000b5eb  cmp     dword ptr [rcx+58h], 0
0x14000b5ef  mov     eax, 8007023Eh
0x14000b5f4  mov     edx, [rcx+0F8h]
0x14000b5fa  cmovl   eax, [rcx+58h]
0x14000b5fe  cmp     edx, 1
0x14000b601  jge     short loc_14000B620
0x14000b603  xor     edx, edx; Val
0x14000b605  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000b60a  mov     r8d, 98h; Size
0x14000b610  call    memset_0
0x14000b615  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000b61a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000b620  cmp     dword ptr [rcx+48h], 0
0x14000b624  jl      short loc_14000B629
0x14000b626  mov     [rcx+48h], eax
0x14000b629  lea     eax, [rdx-1]
0x14000b62c  mov     [rcx+0F8h], eax
0x14000b632  mov     rcx, rbx
0x14000b635  call    ?ReportStopActivity@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14000b63a  lea     r11, [rsp+0C8h+var_8]
0x14000b642  mov     rbx, [r11+18h]
0x14000b646  mov     rsi, [r11+20h]
0x14000b64a  mov     rsp, r11
0x14000b64d  pop     rdi
0x14000b64e  retn
```
