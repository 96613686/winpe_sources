# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)

- ea: `0x14000ef38`
- end: `0x14000efa2`
- name: `?zInternalStart@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `106`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14000ac0c`
- `0x14000ad00`
- `0x14000adcc`
- `0x14000ae8c`
- `0x14000af4c`
- `0x14000b00c`

## callees

- `0x1400022ec`
- `0x140005e18`
- `0x140008578`
- `0x140009460`
- `0x14000ef38`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ef7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ef7d`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(
        __int64 a1)
{
  __int64 v2; // rbx
  _DWORD *v3; // rax
  char v5; // [rsp+30h] [rbp+8h] BYREF

  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v5);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = (_DWORD *)wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider();
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x14000ef38  push    rbx
0x14000ef3a  sub     rsp, 20h
0x14000ef3e  lea     rdx, [rsp+28h+arg_0]
0x14000ef43  mov     rbx, rcx
0x14000ef46  call    ?LockExclusive@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000ef4b  mov     rbx, [rbx+110h]
0x14000ef52  call    ?Provider@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@SAPEBU_tlgProvider_t@@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::Provider(void)
0x14000ef57  mov     ecx, [rax]
0x14000ef59  cmp     ecx, 5
0x14000ef5c  jbe     short loc_14000EF85
0x14000ef5e  mov     rdx, 400000000000h
0x14000ef68  mov     rcx, rax
0x14000ef6b  call    _tlgKeywordOn
0x14000ef70  test    al, al
0x14000ef72  jz      short loc_14000EF85
0x14000ef74  lea     rdx, [rbx+8]; ActivityId
0x14000ef78  mov     ecx, 3; ControlCode
0x14000ef7d  call    cs:__imp_EventActivityIdControl
0x14000ef83  jmp     short loc_14000EF8C
0x14000ef85  xorps   xmm0, xmm0
0x14000ef88  movups  xmmword ptr [rbx+8], xmm0
0x14000ef8c  lea     rcx, [rsp+28h+arg_0]
0x14000ef91  mov     dword ptr [rbx], 1
0x14000ef97  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ef9c  add     rsp, 20h
0x14000efa0  pop     rbx
0x14000efa1  retn
```
