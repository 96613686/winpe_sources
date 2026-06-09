# UserOOBETelemetry::EnableOneDriveBusinessPolicies::StartActivity(void)

- ea: `0x18001b76c`
- end: `0x18001b885`
- name: `?StartActivity@EnableOneDriveBusinessPolicies@UserOOBETelemetry@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(UserOOBETelemetry::EnableOneDriveBusinessPolicies *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180019c70`

## callees

- `0x1800019bc`
- `0x180001fe8`
- `0x18000a664`
- `0x180014714`
- `0x18001ac04`
- `0x18001b76c`
- `0x18001b88c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b7fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b7fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b7b5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b7b5`

## pseudocode

```c
void __fastcall UserOOBETelemetry::EnableOneDriveBusinessPolicies::StartActivity(
        UserOOBETelemetry::EnableOneDriveBusinessPolicies *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  int v6; // ebx
  __int64 v7; // r8
  int v8; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = UserOOBELogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = UserOOBELogging::Provider();
  v6 = (int)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = 0x1000000;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)&byte_180060D57,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (UserOOBETelemetry::EnableOneDriveBusinessPolicies *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x18001b76c  mov     [rsp+arg_10], rbx
0x18001b771  push    rdi
0x18001b772  sub     rsp, 30h
0x18001b776  mov     rdi, rcx
0x18001b779  lea     rdx, [rsp+38h+arg_0]
0x18001b77e  call    ?LockExclusive@?$ActivityBase@VUserOOBELogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b783  mov     rbx, [rdi+110h]
0x18001b78a  call    ?Provider@UserOOBELogging@@SAPEBU_tlgProvider_t@@XZ; UserOOBELogging::Provider(void)
0x18001b78f  mov     edx, [rax]
0x18001b791  cmp     edx, 5
0x18001b794  jbe     short loc_18001B7BD
0x18001b796  mov     rdx, 400000000000h
0x18001b7a0  mov     rcx, rax
0x18001b7a3  call    _tlgKeywordOn
0x18001b7a8  test    al, al
0x18001b7aa  jz      short loc_18001B7BD
0x18001b7ac  lea     rdx, [rbx+8]; ActivityId
0x18001b7b0  mov     ecx, 3; ControlCode
0x18001b7b5  call    cs:__imp_EventActivityIdControl
0x18001b7bb  jmp     short loc_18001B7C4
0x18001b7bd  xorps   xmm0, xmm0
0x18001b7c0  movups  xmmword ptr [rbx+8], xmm0
0x18001b7c4  mov     dword ptr [rbx], 1
0x18001b7ca  lea     rcx, [rsp+38h+arg_0]
0x18001b7cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b7d4  call    ?Provider@UserOOBELogging@@SAPEBU_tlgProvider_t@@XZ; UserOOBELogging::Provider(void)
0x18001b7d9  mov     rbx, rax
0x18001b7dc  mov     ecx, [rax]
0x18001b7de  cmp     ecx, 5
0x18001b7e1  jbe     loc_18001B867
0x18001b7e7  mov     rdx, 400000000000h
0x18001b7f1  mov     rcx, rax
0x18001b7f4  call    _tlgKeywordOn
0x18001b7f9  test    al, al
0x18001b7fb  jz      short loc_18001B867
0x18001b7fd  call    cs:__imp_GetCurrentThreadId
0x18001b803  mov     [rsp+38h+arg_0], eax
0x18001b807  mov     [rsp+38h+arg_8], 1000000h
0x18001b810  mov     r8, [rdi+110h]
0x18001b817  cmp     byte ptr [r8+4], 0
0x18001b81c  jz      short loc_18001B83D
0x18001b81e  lea     r9, [r8+18h]
0x18001b822  cmp     dword ptr [r9], 0
0x18001b826  jnz     short loc_18001B840
0x18001b828  cmp     dword ptr [r9+4], 0
0x18001b82d  jnz     short loc_18001B840
0x18001b82f  cmp     dword ptr [r9+8], 0
0x18001b834  jnz     short loc_18001B840
0x18001b836  cmp     dword ptr [r9+0Ch], 0
0x18001b83b  jnz     short loc_18001B840
0x18001b83d  xor     r9d, r9d
0x18001b840  add     r8, 8
0x18001b844  lea     rax, [rsp+38h+arg_0]
0x18001b849  mov     [rsp+38h+var_10], rax
0x18001b84e  lea     rax, [rsp+38h+arg_8]
0x18001b853  mov     [rsp+38h+var_18], rax
0x18001b858  lea     rdx, byte_180060D57
0x18001b85f  mov     rcx, rbx
0x18001b862  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001b867  lea     rcx, [rdi+120h]; this
0x18001b86e  cmp     dword ptr [rcx+18h], 0
0x18001b872  jnz     short loc_18001B87A
0x18001b874  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001b879  nop
0x18001b87a  mov     rbx, [rsp+38h+arg_10]
0x18001b87f  add     rsp, 30h
0x18001b883  pop     rdi
0x18001b884  retn
```
