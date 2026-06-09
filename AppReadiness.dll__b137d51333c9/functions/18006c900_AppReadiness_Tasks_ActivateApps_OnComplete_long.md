# AppReadiness::Tasks::ActivateApps::OnComplete(long)

- ea: `0x18006c900`
- end: `0x18006ca1c`
- name: `?OnComplete@ActivateApps@Tasks@AppReadiness@@MEAAXJ@Z`
- size: `284`
- prototype: `void __fastcall(AppReadiness::Tasks::ActivateApps *__hidden this, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a2c8`
- `0x18000a470`
- `0x1800148b0`
- `0x180019260`
- `0x180027f5c`
- `0x18006c900`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c9c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c9c7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006c9d5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006c9d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Tasks::ActivateApps::OnComplete(AppReadiness::Tasks::ActivateApps *this, int a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v9; // [rsp+28h] [rbp-20h]
  _BYTE v10[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+18h] BYREF

  v4 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *, _BYTE *))(*(_QWORD *)this + 80LL))(this, v10);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v4, &v8);
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
  v5 = (const WCHAR *)(*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 24LL))(this);
  v6 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
  AppReadiness::Storage::PackageList::WritePackageTaskResult(v6, (const WCHAR *)(v8 + 40), v5, a2);
  v12 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
  v7 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 31) = 0;
  std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(&v12, (__int64)this + 328);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v7);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 64LL))(v12);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
}

```

## disassembly

```asm
0x18006c900  mov     [rsp+arg_8], rbx
0x18006c905  mov     [rsp+arg_18], rsi
0x18006c90a  push    rdi
0x18006c90b  sub     rsp, 40h
0x18006c90f  mov     esi, edx
0x18006c911  mov     rdi, rcx
0x18006c914  mov     rax, [rcx]
0x18006c917  lea     rdx, [rsp+48h+var_18]
0x18006c91c  mov     rax, [rax+50h]
0x18006c920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c925  lea     rdx, [rsp+48h+var_28]
0x18006c92a  mov     rcx, rax
0x18006c92d  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x18006c932  nop
0x18006c933  mov     rcx, [rsp+48h+var_10]; this
0x18006c938  test    rcx, rcx
0x18006c93b  jz      short loc_18006C942
0x18006c93d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006c942  mov     rax, [rdi]
0x18006c945  mov     rcx, rdi
0x18006c948  mov     rax, [rax+18h]
0x18006c94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c951  mov     rbx, rax
0x18006c954  mov     rcx, [rdi]
0x18006c957  mov     rax, [rcx+70h]
0x18006c95b  mov     rcx, rdi
0x18006c95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c963  mov     rdx, [rsp+48h+var_28]
0x18006c968  add     rdx, 28h ; '('
0x18006c96c  mov     r9d, esi
0x18006c96f  mov     r8, rbx
0x18006c972  mov     rcx, rax
0x18006c975  call    ?WritePackageTaskResult@PackageList@Storage@AppReadiness@@SAXPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1J@Z; AppReadiness::Storage::PackageList::WritePackageTaskResult(AppReadiness::User *,std::wstring const &,std::wstring const &,long)
0x18006c97a  mov     [rsp+48h+arg_0], 0
0x18006c983  lea     rdx, [rdi+38h]
0x18006c987  lea     rcx, [rsp+48h+SRWLock]
0x18006c98c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18006c991  mov     rbx, [rdi+100h]
0x18006c998  mov     qword ptr [rdi+100h], 0
0x18006c9a3  xor     eax, eax
0x18006c9a5  mov     [rdi+0F8h], rax
0x18006c9ac  lea     rdx, [rdi+148h]
0x18006c9b3  lea     rcx, [rsp+48h+arg_0]
0x18006c9b8  call    ??$swap@V?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@$0A@@std@@YAXAEAV?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@0@Z; std::swap<Microsoft::WRL::ComPtr<IWindowsStoreUserApps>,0>(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &,Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &)
0x18006c9bd  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18006c9c2  test    rcx, rcx
0x18006c9c5  jz      short loc_18006C9CD
0x18006c9c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18006c9cd  test    rbx, rbx
0x18006c9d0  jz      short loc_18006C9DB
0x18006c9d2  mov     rcx, rbx
0x18006c9d5  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18006c9db  mov     rcx, [rsp+48h+arg_0]
0x18006c9e0  test    rcx, rcx
0x18006c9e3  jz      short loc_18006C9F2
0x18006c9e5  mov     rax, [rcx]
0x18006c9e8  mov     rax, [rax+40h]
0x18006c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9f1  nop
0x18006c9f2  lea     rcx, [rsp+48h+arg_0]
0x18006c9f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9fc  nop
0x18006c9fd  mov     rcx, [rsp+48h+var_20]; this
0x18006ca02  test    rcx, rcx
0x18006ca05  jz      short loc_18006CA0C
0x18006ca07  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006ca0c  mov     rbx, [rsp+48h+arg_8]
0x18006ca11  mov     rsi, [rsp+48h+arg_18]
0x18006ca16  add     rsp, 40h
0x18006ca1a  pop     rdi
0x18006ca1b  retn
```
