# AppReadiness::Tasks::UnregisterPackage::OnExecute(void)

- ea: `0x18002b850`
- end: `0x18002bcba`
- name: `?OnExecute@UnregisterPackage@Tasks@AppReadiness@@MEAAXXZ`
- size: `1130`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002a60`
- `0x18000c000`
- `0x18000e4a0`
- `0x18001835c`
- `0x180027a4c`
- `0x180029a38`
- `0x18002a970`
- `0x18002b63c`
- `0x18002b850`
- `0x18002bcc0`
- `0x18002bf58`
- `0x18002bfa8`
- `0x18002c40c`
- `0x18002c548`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bbab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bbab`

## string_xrefs

- `0x18002baa4`: `onecoreuap\shell\appreadiness\src\tasks\unregisterpackage.cpp`
- `0x18002bb0a`: `onecoreuap\shell\appreadiness\src\tasks\unregisterpackage.cpp`
- `0x18002bb6e`: `onecoreuap\shell\appreadiness\src\tasks\unregisterpackage.cpp`
- `0x18002bb81`: `deploymentOperation->put_Completed(this)`
- `0x18002bab0`: `AppReadiness::Tasks::UnregisterPackage::OnExecute`
- `0x18002bb16`: `AppReadiness::Tasks::UnregisterPackage::OnExecute`
- `0x18002bb7a`: `AppReadiness::Tasks::UnregisterPackage::OnExecute`
- `0x18002bab7`: `GetUser()->ExecuteUnderContext([&]() { auto packageManagerInternal = std::move(PackageInfo::GetPackageManager<IPackageManagerInternal>()); ThrowIfFailed(packageManagerInternal->RemovePackageWithExtendedOptionsAsync( to_winstring(m_packageFullName).Get(), (m_repair ? DeploymentOptionsInternal_RepairAppRegistrationOption : DeploymentOptionsInternal_None) | (m_keepApplicationData ? DeploymentOptionsInternal_PreserveApplicationData : DeploymentOptionsInternal_None), CheckFlags(TaskFlags::OnDemandSyn`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AppReadiness::Tasks::UnregisterPackage::OnExecute(RTL_SRWLOCK *this)
{
  __int64 *v2; // rax
  __int64 v3; // r14
  __int64 v4; // rcx
  RTL_SRWLOCK *v5; // rdx
  __int64 v6; // r8
  _OWORD *v7; // rax
  char v8; // di
  RTL_SRWLOCK *v9; // rdx
  RTL_SRWLOCK *v10; // rsi
  RTL_SRWLOCK *v11; // rdi
  __int64 v12; // rax
  int v13; // edi
  _QWORD *v14; // rdx
  RTL_SRWLOCK *v15; // rdx
  int v16; // edx
  RTL_SRWLOCK *v17; // rdx
  int v18; // edx
  __int64 v19; // rcx
  RTL_SRWLOCK *v20; // rdi
  __int64 v21; // rax
  _QWORD *v22; // r9
  __int64 v23; // [rsp+30h] [rbp-99h] BYREF
  __int64 v24; // [rsp+38h] [rbp-91h] BYREF
  __int64 v25; // [rsp+40h] [rbp-89h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-81h] BYREF
  _OWORD v27[2]; // [rsp+70h] [rbp-59h] BYREF
  _OWORD v28[2]; // [rsp+90h] [rbp-39h] BYREF
  _QWORD v29[7]; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD *v30; // [rsp+E8h] [rbp+1Fh]

  LODWORD(v23) = 0;
  v2 = (__int64 *)AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(&v25);
  v3 = 0;
  v24 = 0;
  if ( &v24 != v2 )
  {
    v3 = *v2;
    v24 = *v2;
    *v2 = 0;
  }
  v4 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( this[43].Ptr )
  {
    v9 = this + 41;
    memset(v27, 0, sizeof(v27));
    if ( this[44].Ptr > (PVOID)7 )
      v9 = (RTL_SRWLOCK *)v9->Ptr;
    std::wstring::_Construct<2,unsigned short const *>(v27, v9, this[43].Ptr);
    v7 = v27;
    v8 = 4;
  }
  else
  {
    v5 = this + 37;
    if ( this[40].Ptr > (PVOID)7 )
      v5 = (RTL_SRWLOCK *)v5->Ptr;
    memset(v28, 0, sizeof(v28));
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)&v5->Ptr + v6) );
    std::wstring::_Construct<1,unsigned short const *>(v28);
    LODWORD(v23) = 1;
    v7 = (_OWORD *)AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove(&this[-4], pExceptionObject, v28, &v24);
    v8 = 3;
  }
  v10 = this + 33;
  std::wstring::operator=(&this[33], v7);
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v27);
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
  }
  if ( (v8 & 1) != 0 )
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v28);
  if ( this[35].Ptr )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = this + 37;
      if ( this[40].Ptr > (PVOID)7 )
        v11 = (RTL_SRWLOCK *)v11->Ptr;
      if ( this[36].Ptr > (PVOID)7 )
        v10 = (RTL_SRWLOCK *)v10->Ptr;
      (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v10, (__int64)v11);
    }
    v23 = 0;
    v12 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
    v29[0] = off_18007C230;
    v29[1] = this - 4;
    v29[2] = &v23;
    v30 = v29;
    v13 = AppReadiness::User::ExecuteUnderContext(v12, (__int64)v29);
    if ( v30 )
    {
      v14 = v29;
      LOBYTE(v14) = v30 != v29;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v14);
    }
    if ( v13 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v13,
        "GetUser()->ExecuteUnderContext([&]() { auto packageManagerInternal = std::move(PackageInfo::GetPackageManager<IP"
        "ackageManagerInternal>()); ThrowIfFailed(packageManagerInternal->RemovePackageWithExtendedOptionsAsync( to_winst"
        "ring(m_packageFullName).Get(), (m_repair ? DeploymentOptionsInternal_RepairAppRegistrationOption : DeploymentOpt"
        "ionsInternal_None) | (m_keepApplicationData ? DeploymentOptionsInternal_PreserveApplicationData : DeploymentOpti"
        "onsInternal_None), CheckFlags(TaskFlags::OnDemandSyncTask) ? DeploymentOptionsInternal2_FailOnRedirectToDefaultA"
        "ccount : DeploymentOptionsInternal2_None, CheckFlags(TaskFlags::LogonBlocking) ? Windows::Management::Deployment"
        "::Internal::DeploymentOperationPriority_InteractiveHigh : Windows::Management::Deployment::Internal::DeploymentO"
        "perationPriority_Default, deploymentOperation.GetAddressOf())); })",
        "AppReadiness::Tasks::UnregisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\unregisterpackage.cpp",
        196);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v15 = this + 30;
    if ( this == (RTL_SRWLOCK *)32 )
      v15 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v23 + 48LL))(v23, v15);
    if ( v16 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v16,
        "deploymentOperation->put_Progress(this)",
        "AppReadiness::Tasks::UnregisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\unregisterpackage.cpp",
        198);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v17 = this + 29;
    if ( this == (RTL_SRWLOCK *)32 )
      v17 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v23 + 64LL))(v23, v17);
    if ( v18 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v18,
        "deploymentOperation->put_Completed(this)",
        "AppReadiness::Tasks::UnregisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\unregisterpackage.cpp",
        199);
      throw (Windows::HResultException *)pExceptionObject;
    }
    AcquireSRWLockExclusive(this + 7);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
      &this[32],
      &v23);
    if ( this != (RTL_SRWLOCK *)-56LL )
      ReleaseSRWLockExclusive(this + 7);
    if ( AppReadiness::Impl::BaseTask::IsCanceled((AppReadiness::Impl::BaseTask *)this) )
      (*((void (**)(void))this->Ptr + 26))();
    v19 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v20 = this + 37;
      if ( this[40].Ptr > (PVOID)7 )
        v20 = (RTL_SRWLOCK *)v20->Ptr;
      v21 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
      v22 = (_QWORD *)(v21 + 64);
      if ( *(_QWORD *)(v21 + 88) > 7u )
        v22 = (_QWORD *)*v22;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_3eeba0c2f58e361ad2cfab29b98a3de9_Traceguids,
        (_DWORD)v22,
        (__int64)v20);
    }
    AppReadiness::Impl::BaseTask::CompleteTask((AppReadiness::Impl::BaseTask *)this, 0);
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x18002b850  mov     [rsp-8+arg_8], rbx
0x18002b855  mov     [rsp-8+arg_10], rsi
0x18002b85a  push    rbp
0x18002b85b  push    rdi
0x18002b85c  push    r12
0x18002b85e  push    r14
0x18002b860  push    r15
0x18002b862  lea     rbp, [rsp-37h]
0x18002b867  sub     rsp, 100h
0x18002b86e  mov     rax, cs:__security_cookie
0x18002b875  xor     rax, rsp
0x18002b878  mov     [rbp+57h+var_30], rax
0x18002b87c  mov     rbx, rcx
0x18002b87f  xor     r12d, r12d
0x18002b882  mov     dword ptr [rsp+120h+var_F0], r12d
0x18002b887  lea     rcx, [rsp+120h+var_E0]
0x18002b88c  call    ??$GetPackageManager@UIPackageManager@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@XZ; AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(void)
0x18002b891  mov     r14d, r12d
0x18002b894  mov     [rsp+120h+var_E8], r12
0x18002b899  lea     rcx, [rsp+120h+var_E8]
0x18002b89e  cmp     rcx, rax
0x18002b8a1  jz      short loc_18002B8AE
0x18002b8a3  mov     r14, [rax]
0x18002b8a6  mov     [rsp+120h+var_E8], r14
0x18002b8ab  mov     [rax], r12
0x18002b8ae  mov     rcx, [rsp+120h+var_E0]
0x18002b8b3  test    rcx, rcx
0x18002b8b6  jz      short loc_18002B8CA
0x18002b8b8  mov     [rsp+120h+var_E0], r12
0x18002b8bd  mov     rax, [rcx]
0x18002b8c0  mov     rax, [rax+10h]
0x18002b8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c9  nop
0x18002b8ca  lea     r15, [rbx-20h]
0x18002b8ce  cmp     [r15+178h], r12
0x18002b8d5  jnz     short loc_18002B935
0x18002b8d7  lea     rdx, [rbx+128h]
0x18002b8de  cmp     qword ptr [rdx+18h], 7
0x18002b8e3  jbe     short loc_18002B8E8
0x18002b8e5  mov     rdx, [rdx]
0x18002b8e8  xorps   xmm0, xmm0
0x18002b8eb  movups  [rbp+57h+var_90], xmm0
0x18002b8ef  xorps   xmm1, xmm1
0x18002b8f2  movdqu  [rbp+57h+var_80], xmm1
0x18002b8f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b8fb  inc     r8
0x18002b8fe  cmp     [rdx+r8*2], r12w
0x18002b903  jnz     short loc_18002B8FB
0x18002b905  lea     rcx, [rbp+57h+var_90]
0x18002b909  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002b90e  nop
0x18002b90f  mov     dword ptr [rsp+120h+var_F0], 1
0x18002b917  lea     r9, [rsp+120h+var_E8]
0x18002b91c  lea     r8, [rbp+57h+var_90]
0x18002b920  lea     rdx, [rsp+120h+pExceptionObject]
0x18002b925  mov     rcx, r15
0x18002b928  call    ?FindPackageIdToRemove@UnregisterPackage@Tasks@AppReadiness@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@AEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Z; AppReadiness::Tasks::UnregisterPackage::FindPackageIdToRemove(std::wstring const &,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &)
0x18002b92d  nop
0x18002b92e  mov     edi, 3
0x18002b933  jmp     short loc_18002B96B
0x18002b935  lea     rdx, [rbx+148h]
0x18002b93c  xorps   xmm0, xmm0
0x18002b93f  movups  [rbp+57h+var_B0], xmm0
0x18002b943  xorps   xmm1, xmm1
0x18002b946  movdqu  [rbp+57h+var_A0], xmm1
0x18002b94b  mov     r8, [rdx+10h]
0x18002b94f  cmp     qword ptr [rdx+18h], 7
0x18002b954  jbe     short loc_18002B959
0x18002b956  mov     rdx, [rdx]
0x18002b959  lea     rcx, [rbp+57h+var_B0]
0x18002b95d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18002b962  lea     rax, [rbp+57h+var_B0]
0x18002b966  mov     edi, 4
0x18002b96b  lea     rsi, [rbx+108h]
0x18002b972  mov     rdx, rax
0x18002b975  mov     rcx, rsi
0x18002b978  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b97d  test    dil, 4
0x18002b981  jz      short loc_18002B990
0x18002b983  and     edi, 0FFFFFFFBh
0x18002b986  lea     rcx, [rbp+57h+var_B0]
0x18002b98a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002b98f  nop
0x18002b990  test    dil, 2
0x18002b994  jz      short loc_18002B9A4
0x18002b996  and     edi, 0FFFFFFFDh
0x18002b999  lea     rcx, [rsp+120h+pExceptionObject]
0x18002b99e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002b9a3  nop
0x18002b9a4  test    dil, 1
0x18002b9a8  jz      short loc_18002B9B3
0x18002b9aa  lea     rcx, [rbp+57h+var_90]
0x18002b9ae  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18002b9b3  cmp     [rbx+118h], r12
0x18002b9ba  jz      loc_18002BC0A
0x18002b9c0  lea     rax, WPP_GLOBAL_Control
0x18002b9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9ce  cmp     rcx, rax
0x18002b9d1  jz      short loc_18002BA37
0x18002b9d3  test    byte ptr [rcx+1Ch], 4
0x18002b9d7  jz      short loc_18002BA37
0x18002b9d9  lea     rdi, [rbx+128h]
0x18002b9e0  cmp     qword ptr [rdi+18h], 7
0x18002b9e5  jbe     short loc_18002B9EA
0x18002b9e7  mov     rdi, [rdi]
0x18002b9ea  cmp     qword ptr [rsi+18h], 7
0x18002b9ef  jbe     short loc_18002B9F4
0x18002b9f1  mov     rsi, [rsi]
0x18002b9f4  mov     rax, [rbx]
0x18002b9f7  mov     rcx, rbx
0x18002b9fa  mov     rax, [rax+70h]
0x18002b9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba03  lea     r9, [rax+40h]
0x18002ba07  cmp     qword ptr [r9+18h], 7
0x18002ba0c  jbe     short loc_18002BA11
0x18002ba0e  mov     r9, [r9]
0x18002ba11  mov     edx, 0Ch
0x18002ba16  mov     [rsp+120h+var_F8], rdi; __int64
0x18002ba1b  mov     [rsp+120h+var_100], rsi; __int64
0x18002ba20  lea     r8, WPP_3eeba0c2f58e361ad2cfab29b98a3de9_Traceguids
0x18002ba27  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba2e  mov     rcx, [rcx+10h]; LoggerHandle
0x18002ba32  call    WPP_SF_SSS
0x18002ba37  mov     [rsp+120h+var_F0], r12
0x18002ba3c  mov     rax, [rbx]
0x18002ba3f  mov     rcx, rbx
0x18002ba42  mov     rax, [rax+70h]
0x18002ba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba4b  lea     rcx, off_18007C230
0x18002ba52  mov     [rbp+57h+var_70], rcx
0x18002ba56  mov     [rbp+57h+var_68], r15
0x18002ba5a  lea     rcx, [rsp+120h+var_F0]
0x18002ba5f  mov     [rbp+57h+var_60], rcx
0x18002ba63  lea     rcx, [rbp+57h+var_70]
0x18002ba67  mov     [rbp+57h+var_38], rcx
0x18002ba6b  lea     rdx, [rbp+57h+var_70]
0x18002ba6f  mov     rcx, rax
0x18002ba72  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18002ba77  mov     edi, eax
0x18002ba79  mov     rcx, [rbp+57h+var_38]
0x18002ba7d  test    rcx, rcx
0x18002ba80  jz      short loc_18002BA98
0x18002ba82  mov     rax, [rcx]
0x18002ba85  lea     rdx, [rbp+57h+var_70]
0x18002ba89  cmp     rcx, rdx
0x18002ba8c  setnz   dl
0x18002ba8f  mov     rax, [rax+20h]
0x18002ba93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba98  test    edi, edi
0x18002ba9a  jns     short loc_18002BADC
0x18002ba9c  mov     dword ptr [rsp+120h+var_F8], 0C4h; int
0x18002baa4  lea     rax, aOnecoreuapShel_31; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002baab  mov     [rsp+120h+var_100], rax; char *
0x18002bab0  lea     r9, aAppreadinessTa_34; "AppReadiness::Tasks::UnregisterPackage:"...
0x18002bab7  lea     r8, aGetuserExecute; "GetUser()->ExecuteUnderContext([&]() { "...
0x18002babe  mov     edx, edi; int
0x18002bac0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18002bac5  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002baca  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002bad1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18002bad6  call    _CxxThrowException_0
0x18002badc  mov     rcx, [rsp+120h+var_F0]
0x18002bae1  mov     rax, [rcx]
0x18002bae4  test    r15, r15
0x18002bae7  lea     rdx, [rbx+0F0h]
0x18002baee  jnz     short loc_18002BAF3
0x18002baf0  mov     rdx, r12
0x18002baf3  mov     rax, [rax+30h]
0x18002baf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bafc  mov     edx, eax; int
0x18002bafe  test    eax, eax
0x18002bb00  jns     short loc_18002BB40
0x18002bb02  mov     dword ptr [rsp+120h+var_F8], 0C6h; int
0x18002bb0a  lea     rax, aOnecoreuapShel_31; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002bb11  mov     [rsp+120h+var_100], rax; char *
0x18002bb16  lea     r9, aAppreadinessTa_34; "AppReadiness::Tasks::UnregisterPackage:"...
0x18002bb1d  lea     r8, aDeploymentoper; "deploymentOperation->put_Progress(this)"
0x18002bb24  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18002bb29  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002bb2e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002bb35  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18002bb3a  call    _CxxThrowException_0
0x18002bb40  mov     rcx, [rsp+120h+var_F0]
0x18002bb45  mov     rax, [rcx]
0x18002bb48  test    r15, r15
0x18002bb4b  lea     rdx, [rbx+0E8h]
0x18002bb52  jnz     short loc_18002BB57
0x18002bb54  mov     rdx, r12
0x18002bb57  mov     rax, [rax+40h]
0x18002bb5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb60  mov     edx, eax; int
0x18002bb62  test    eax, eax
0x18002bb64  jns     short loc_18002BBA4
0x18002bb66  mov     dword ptr [rsp+120h+var_F8], 0C7h; int
0x18002bb6e  lea     rax, aOnecoreuapShel_31; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002bb75  mov     [rsp+120h+var_100], rax; char *
0x18002bb7a  lea     r9, aAppreadinessTa_34; "AppReadiness::Tasks::UnregisterPackage:"...
0x18002bb81  lea     r8, aDeploymentoper_0; "deploymentOperation->put_Completed(this"...
0x18002bb88  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18002bb8d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002bb92  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002bb99  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18002bb9e  call    _CxxThrowException_0
0x18002bba4  lea     rdi, [rbx+38h]
0x18002bba8  mov     rcx, rdi; SRWLock
0x18002bbab  call    cs:__imp_AcquireSRWLockExclusive
0x18002bbb1  lea     rcx, [rbx+100h]
0x18002bbb8  lea     rdx, [rsp+120h+var_F0]
0x18002bbbd  call    ??4?$ComPtr@U?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> const &)
0x18002bbc2  test    rdi, rdi
0x18002bbc5  jz      short loc_18002BBD0
0x18002bbc7  mov     rcx, rdi; SRWLock
0x18002bbca  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bbd0  mov     rcx, rbx; this
0x18002bbd3  call    ?IsCanceled@BaseTask@Impl@AppReadiness@@IEAA_NXZ; AppReadiness::Impl::BaseTask::IsCanceled(void)
0x18002bbd8  test    al, al
0x18002bbda  jz      short loc_18002BBEC
0x18002bbdc  mov     rax, [rbx]
0x18002bbdf  mov     rax, [rax+0D0h]
0x18002bbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbeb  nop
0x18002bbec  mov     rcx, [rsp+120h+var_F0]
0x18002bbf1  test    rcx, rcx
0x18002bbf4  jz      short loc_18002BC08
0x18002bbf6  mov     [rsp+120h+var_F0], r12
0x18002bbfb  mov     rax, [rcx]
0x18002bbfe  mov     rax, [rax+10h]
0x18002bc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc07  nop
0x18002bc08  jmp     short loc_18002BC7D
0x18002bc0a  lea     rax, WPP_GLOBAL_Control
0x18002bc11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc18  cmp     rcx, rax
0x18002bc1b  jz      short loc_18002BC72
0x18002bc1d  test    byte ptr [rcx+1Ch], 4
0x18002bc21  jz      short loc_18002BC72
0x18002bc23  lea     rdi, [rbx+128h]
0x18002bc2a  cmp     qword ptr [rdi+18h], 7
0x18002bc2f  jbe     short loc_18002BC34
0x18002bc31  mov     rdi, [rdi]
0x18002bc34  mov     rax, [rbx]
0x18002bc37  mov     rcx, rbx
0x18002bc3a  mov     rax, [rax+70h]
0x18002bc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc43  lea     r9, [rax+40h]
0x18002bc47  cmp     qword ptr [r9+18h], 7
0x18002bc4c  jbe     short loc_18002BC51
0x18002bc4e  mov     r9, [r9]
0x18002bc51  mov     edx, 0Dh
0x18002bc56  mov     [rsp+120h+var_100], rdi
0x18002bc5b  lea     r8, WPP_3eeba0c2f58e361ad2cfab29b98a3de9_Traceguids
0x18002bc62  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc69  mov     rcx, [rcx+10h]
0x18002bc6d  call    WPP_SF_SS
0x18002bc72  xor     edx, edx; int
0x18002bc74  mov     rcx, rbx; this
0x18002bc77  call    ?CompleteTask@BaseTask@Impl@AppReadiness@@IEAA_NJ@Z; AppReadiness::Impl::BaseTask::CompleteTask(long)
0x18002bc7c  nop
0x18002bc7d  test    r14, r14
0x18002bc80  jz      short loc_18002BC92
0x18002bc82  mov     rax, [r14]
0x18002bc85  mov     rcx, r14
0x18002bc88  mov     rax, [rax+10h]
0x18002bc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc91  nop
0x18002bc92  mov     rcx, [rbp+57h+var_30]
0x18002bc96  xor     rcx, rsp; StackCookie
0x18002bc99  call    __security_check_cookie
0x18002bc9e  lea     r11, [rsp+120h+var_20]
0x18002bca6  mov     rbx, [r11+38h]
0x18002bcaa  mov     rsi, [r11+40h]
0x18002bcae  mov     rsp, r11
0x18002bcb1  pop     r15
0x18002bcb3  pop     r14
0x18002bcb5  pop     r12
0x18002bcb7  pop     rdi
0x18002bcb8  pop     rbp
0x18002bcb9  retn
```
