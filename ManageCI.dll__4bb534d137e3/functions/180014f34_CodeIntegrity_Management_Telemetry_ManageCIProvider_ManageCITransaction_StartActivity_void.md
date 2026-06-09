# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::StartActivity(void)

- ea: `0x180014f34`
- end: `0x18001504d`
- name: `?StartActivity@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012110`

## callees

- `0x1800019bc`
- `0x180001fe4`
- `0x18000a398`
- `0x18001481c`
- `0x180014ce4`
- `0x180014f34`
- `0x180015054`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fc5`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::StartActivity(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v10);
  v2 = *((_QWORD *)this + 34);
  v3 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v5 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  v7 = (__int64)v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v6) )
  {
    LODWORD(v10) = GetCurrentThreadId();
    v11 = 0x1000000;
    v8 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_180031AE9,
      v8 + 8,
      v9,
      (__int64)&v11,
      (__int64)&v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *)((char *)this + 288));
}

```

## disassembly

```asm
0x180014f34  mov     [rsp+arg_10], rbx
0x180014f39  push    rdi
0x180014f3a  sub     rsp, 30h
0x180014f3e  mov     rdi, rcx
0x180014f41  lea     rdx, [rsp+38h+arg_0]
0x180014f46  call    ?LockExclusive@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014f4b  mov     rbx, [rdi+110h]
0x180014f52  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180014f57  mov     edx, [rax]
0x180014f59  cmp     edx, 5
0x180014f5c  jbe     short loc_180014F85
0x180014f5e  mov     rdx, 400000000000h
0x180014f68  mov     rcx, rax
0x180014f6b  call    _tlgKeywordOn
0x180014f70  test    al, al
0x180014f72  jz      short loc_180014F85
0x180014f74  lea     rdx, [rbx+8]; ActivityId
0x180014f78  mov     ecx, 3; ControlCode
0x180014f7d  call    cs:__imp_EventActivityIdControl
0x180014f83  jmp     short loc_180014F8C
0x180014f85  xorps   xmm0, xmm0
0x180014f88  movups  xmmword ptr [rbx+8], xmm0
0x180014f8c  mov     dword ptr [rbx], 1
0x180014f92  lea     rcx, [rsp+38h+arg_0]
0x180014f97  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014f9c  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180014fa1  mov     rbx, rax
0x180014fa4  mov     ecx, [rax]
0x180014fa6  cmp     ecx, 5
0x180014fa9  jbe     loc_18001502F
0x180014faf  mov     rdx, 400000000000h
0x180014fb9  mov     rcx, rax
0x180014fbc  call    _tlgKeywordOn
0x180014fc1  test    al, al
0x180014fc3  jz      short loc_18001502F
0x180014fc5  call    cs:__imp_GetCurrentThreadId
0x180014fcb  mov     dword ptr [rsp+38h+arg_0], eax
0x180014fcf  mov     [rsp+38h+arg_8], 1000000h
0x180014fd8  mov     r8, [rdi+110h]
0x180014fdf  cmp     byte ptr [r8+4], 0
0x180014fe4  jz      short loc_180015005
0x180014fe6  lea     r9, [r8+18h]
0x180014fea  cmp     dword ptr [r9], 0
0x180014fee  jnz     short loc_180015008
0x180014ff0  cmp     dword ptr [r9+4], 0
0x180014ff5  jnz     short loc_180015008
0x180014ff7  cmp     dword ptr [r9+8], 0
0x180014ffc  jnz     short loc_180015008
0x180014ffe  cmp     dword ptr [r9+0Ch], 0
0x180015003  jnz     short loc_180015008
0x180015005  xor     r9d, r9d
0x180015008  add     r8, 8
0x18001500c  lea     rax, [rsp+38h+arg_0]
0x180015011  mov     [rsp+38h+var_10], rax
0x180015016  lea     rax, [rsp+38h+arg_8]
0x18001501b  mov     [rsp+38h+var_18], rax
0x180015020  lea     rdx, byte_180031AE9
0x180015027  mov     rcx, rbx
0x18001502a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001502f  lea     rcx, [rdi+120h]; this
0x180015036  cmp     dword ptr [rcx+18h], 0
0x18001503a  jnz     short loc_180015042
0x18001503c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180015041  nop
0x180015042  mov     rbx, [rsp+38h+arg_10]
0x180015047  add     rsp, 30h
0x18001504b  pop     rdi
0x18001504c  retn
```
