# AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(void)

- ea: `0x18001835c`
- end: `0x180018706`
- name: `??$GetPackageManager@UIPackageManager@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@XZ`
- size: `938`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18001823c`
- `0x18002b850`
- `0x180060de0`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a470`
- `0x18001835c`
- `0x180018aa8`
- `0x180018ac8`
- `0x1800203d8`
- `0x1800276e0`
- `0x180027a4c`
- `0x1800332e4`
- `0x1800335a8`
- `0x180033600`
- `0x180033668`
- `0x180038350`
- `0x18003b920`
- `0x18003e210`
- `0x18003ecb4`
- `0x180075b4c`
- `0x180079010`

## import_xrefs

- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x1800183ac`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x1800183ac`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x1800183db`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x1800183db`

## string_xrefs

- `0x180018424`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x18001864a`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180018688`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x1800186c6`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180018430`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180018656`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180018694`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x1800186d2`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x18001869b`: `packageManagerInternal->CopyTo(riid, object)`
- `0x1800186d9`: `packageManager->CopyTo(riid, object)`

## pseudocode

```c
__int64 *__fastcall AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager>(
        __int64 *a1)
{
  std::_Ref_count_base *v2; // rbx
  _QWORD *v3; // r14
  volatile signed __int32 *v4; // rdi
  int v5; // eax
  _QWORD *v6; // rdi
  std::_Ref_count_base *v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  std::_Ref_count_base *v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 *v20; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-21h]
  HSTRING_HEADER pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+70h] [rbp+7h]

  v20 = a1;
  v21 = 0;
  if ( !memcmp_0(&GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53, &GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef, 0x10u) )
  {
    std::atomic_load_explicit<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(&v22);
    v6 = (_QWORD *)v22;
    if ( v22 )
    {
      v7 = v23;
    }
    else
    {
      v20 = 0;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pExceptionObject,
        L"Windows.Management.Deployment.Internal.PackageManagerInternal",
        0x3Eu,
        0x3Du);
      v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
              v25,
              &v20);
      if ( v19 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          v19,
          "Windows::Foundation::ActivateInstance( HStringReference(RuntimeClass_Windows_Management_Deployment_Internal_Pa"
          "ckageManagerInternal).Get(), &packageManagerInternalPtr)",
          "AppReadiness::PackageInfo::GetPackageManager",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
          500);
        throw (Windows::HResultException *)&pExceptionObject;
      }
      v14 = (__int64 *)std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
                         &pExceptionObject,
                         &v20);
      std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
        v15,
        v14);
      v16 = (_QWORD *)std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>((__int64)&pExceptionObject);
      v6 = (_QWORD *)*v16;
      v7 = (std::_Ref_count_base *)v16[1];
      *v16 = 0;
      v16[1] = 0;
      v22 = (__int64)v6;
      v17 = v23;
      v23 = v7;
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      if ( *(_QWORD *)&pExceptionObject.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&pExceptionObject.Reserved.Reserved2[8]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    }
    v18 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v6)(
            *v6,
            &GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53,
            &v21);
    if ( v18 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v18,
        "packageManagerInternal->CopyTo(riid, object)",
        "AppReadiness::PackageInfo::GetPackageManager",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        506);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
  }
  else
  {
    _Lock_shared_ptr_spin_lock();
    v2 = qword_1800A4E30;
    if ( qword_1800A4E30 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_1800A4E30 + 2);
      v2 = qword_1800A4E30;
    }
    v3 = (_QWORD *)AppReadiness::PackageInfo::s_packageManager;
    v22 = AppReadiness::PackageInfo::s_packageManager;
    v23 = v2;
    v4 = (volatile signed __int32 *)v2;
    _Unlock_shared_ptr_spin_lock();
    if ( !v3 )
    {
      v20 = 0;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pExceptionObject,
        L"Windows.Management.Deployment.PackageManager",
        0x2Du,
        0x2Cu);
      v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(
             v25,
             &v20);
      if ( v5 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          v5,
          "Windows::Foundation::ActivateInstance( HStringReference(RuntimeClass_Windows_Management_Deployment_PackageMana"
          "ger).Get(), &packageManagerPtr)",
          "AppReadiness::PackageInfo::GetPackageManager",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
          516);
        throw (Windows::HResultException *)&pExceptionObject;
      }
      v8 = (_QWORD *)std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(
                       &pExceptionObject,
                       &v20);
      std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(v9, v8);
      v10 = std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(&pExceptionObject);
      v3 = (_QWORD *)*v10;
      v2 = (std::_Ref_count_base *)v10[1];
      *v10 = 0;
      v10[1] = 0;
      v22 = (__int64)v3;
      v23 = v2;
      if ( v4 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v4);
      if ( *(_QWORD *)&pExceptionObject.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&pExceptionObject.Reserved.Reserved2[8]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      v4 = (volatile signed __int32 *)v2;
    }
    v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v3)(
            *v3,
            &GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53,
            &v21);
    if ( v11 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v11,
        "packageManager->CopyTo(riid, object)",
        "AppReadiness::PackageInfo::GetPackageManager",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        522);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    if ( v2 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v4);
    }
  }
  *a1 = 0;
  if ( a1 == &v21 )
  {
    v12 = v21;
  }
  else
  {
    *a1 = v21;
    v12 = 0;
  }
  if ( v12 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18001835c  push    rbp
0x18001835e  push    rbx
0x18001835f  push    rsi
0x180018360  push    rdi
0x180018361  push    r14
0x180018363  push    r15
0x180018365  lea     rbp, [rsp-2Fh]
0x18001836a  sub     rsp, 98h
0x180018371  mov     rax, cs:__security_cookie
0x180018378  xor     rax, rsp
0x18001837b  mov     [rbp+57h+var_40], rax
0x18001837f  mov     rsi, rcx
0x180018382  mov     [rbp+57h+var_90], rcx
0x180018386  xor     r15d, r15d
0x180018389  mov     [rbp+57h+var_88], r15
0x18001838d  lea     r8d, [r15+10h]; Size
0x180018391  lea     rdx, _GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef; Buf2
0x180018398  lea     rcx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53; Buf1
0x18001839f  call    memcmp_0
0x1800183a4  test    eax, eax
0x1800183a6  jz      loc_18001845A
0x1800183ac  call    cs:__imp__Lock_shared_ptr_spin_lock
0x1800183b2  mov     rbx, cs:qword_1800A4E30
0x1800183b9  test    rbx, rbx
0x1800183bc  jz      short loc_1800183C9
0x1800183be  lock inc dword ptr [rbx+8]
0x1800183c2  mov     rbx, cs:qword_1800A4E30
0x1800183c9  mov     r14, cs:?s_packageManager@PackageInfo@AppReadiness@@1V?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@A; std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> AppReadiness::PackageInfo::s_packageManager
0x1800183d0  mov     [rbp+57h+var_80], r14
0x1800183d4  mov     [rbp+57h+var_78], rbx
0x1800183d8  mov     rdi, rbx
0x1800183db  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x1800183e1  nop
0x1800183e2  test    r14, r14
0x1800183e5  jnz     loc_1800184D6
0x1800183eb  mov     [rbp+57h+var_90], r15
0x1800183ef  mov     [rbp+57h+var_50], r15
0x1800183f3  lea     r9d, [r14+2Ch]; unsigned int
0x1800183f7  lea     r8d, [r14+2Dh]; unsigned int
0x1800183fb  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180018402  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x180018406  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001840b  lea     rdx, [rbp+57h+var_90]
0x18001840f  mov     rcx, [rbp+57h+var_50]
0x180018413  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>)
0x180018418  test    eax, eax
0x18001841a  jns     short loc_18001847A
0x18001841c  mov     [rsp+0C0h+var_98], 204h; int
0x180018424  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001842b  mov     [rsp+0C0h+var_A0], rcx; char *
0x180018430  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x180018437  lea     r8, aWindowsFoundat_11; "Windows::Foundation::ActivateInstance( "...
0x18001843e  mov     edx, eax; int
0x180018440  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180018444  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180018449  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180018450  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018454  call    _CxxThrowException_0
0x18001845a  lea     rcx, [rbp+57h+var_80]
0x18001845e  call    ??$atomic_load_explicit@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@PEBV10@W4memory_order@0@@Z; std::atomic_load_explicit<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> const *,std::memory_order)
0x180018463  nop
0x180018464  mov     rdi, [rbp+57h+var_80]
0x180018468  test    rdi, rdi
0x18001846b  jz      loc_18001860B
0x180018471  mov     rbx, [rbp+57h+var_78]
0x180018475  jmp     loc_1800185B8
0x18001847a  lea     rdx, [rbp+57h+var_90]
0x18001847e  lea     rcx, [rbp+57h+pExceptionObject]
0x180018482  call    ??$make_shared@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@V123@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@$$QEAV?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Z; std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2> &&)
0x180018487  mov     rdx, rax
0x18001848a  call    ??$atomic_store@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YAXPEAV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@V10@@Z; std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> *,std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>)
0x18001848f  lea     rcx, [rbp+57h+pExceptionObject]
0x180018493  call    ??$atomic_load@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@PEBV10@@Z; std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> const *)
0x180018498  mov     r14, [rax]
0x18001849b  mov     rbx, [rax+8]
0x18001849f  mov     [rax], r15
0x1800184a2  mov     [rax+8], r15
0x1800184a6  mov     [rbp+57h+var_80], r14
0x1800184aa  mov     [rbp+57h+var_78], rbx
0x1800184ae  test    rdi, rdi
0x1800184b1  jz      short loc_1800184BB
0x1800184b3  mov     rcx, rdi; this
0x1800184b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800184bb  mov     rcx, [rbp+57h+var_60]; this
0x1800184bf  test    rcx, rcx
0x1800184c2  jz      short loc_1800184CA
0x1800184c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800184c9  nop
0x1800184ca  lea     rcx, [rbp+57h+var_90]
0x1800184ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800184d3  mov     rdi, rbx
0x1800184d6  mov     rcx, [r14]
0x1800184d9  mov     rax, [rcx]
0x1800184dc  lea     r8, [rbp+57h+var_88]
0x1800184e0  lea     rdx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53
0x1800184e7  mov     rax, [rax]
0x1800184ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ef  nop
0x1800184f0  test    eax, eax
0x1800184f2  js      loc_1800186BE
0x1800184f8  test    rbx, rbx
0x1800184fb  jz      short loc_18001850E
0x1800184fd  or      eax, 0FFFFFFFFh
0x180018500  lock xadd [rdi+8], eax
0x180018505  cmp     eax, 1
0x180018508  jz      loc_1800185F0
0x18001850e  mov     [rsi], r15
0x180018511  lea     rax, [rbp+57h+var_88]
0x180018515  cmp     rsi, rax
0x180018518  jz      loc_1800186FC
0x18001851e  mov     rax, [rbp+57h+var_88]
0x180018522  mov     [rsi], rax
0x180018525  mov     rcx, r15
0x180018528  test    rcx, rcx
0x18001852b  jz      short loc_18001853E
0x18001852d  mov     [rbp+57h+var_88], r15
0x180018531  mov     rdx, [rcx]
0x180018534  mov     rax, [rdx+10h]
0x180018538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001853d  nop
0x18001853e  mov     rax, rsi
0x180018541  mov     rcx, [rbp+57h+var_40]
0x180018545  xor     rcx, rsp; StackCookie
0x180018548  call    __security_check_cookie
0x18001854d  add     rsp, 98h
0x180018554  pop     r15
0x180018556  pop     r14
0x180018558  pop     rdi
0x180018559  pop     rsi
0x18001855a  pop     rbx
0x18001855b  pop     rbp
0x18001855c  retn
0x18001855d  lea     rdx, [rbp+57h+var_90]
0x180018561  lea     rcx, [rbp+57h+pExceptionObject]
0x180018565  call    ??$make_shared@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@V123@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@$$QEAV?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Z; std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal> &&)
0x18001856a  mov     rdx, rax
0x18001856d  call    ??$atomic_store@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YAXPEAV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@V10@@Z; std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> *,std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x180018572  lea     rcx, [rbp+57h+pExceptionObject]
0x180018576  call    ??$atomic_load@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@PEBV10@@Z; std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> const *)
0x18001857b  mov     rdi, [rax]
0x18001857e  mov     rbx, [rax+8]
0x180018582  mov     [rax], r15
0x180018585  mov     [rax+8], r15
0x180018589  mov     [rbp+57h+var_80], rdi
0x18001858d  mov     rcx, [rbp+57h+var_78]; this
0x180018591  mov     [rbp+57h+var_78], rbx
0x180018595  test    rcx, rcx
0x180018598  jz      short loc_18001859F
0x18001859a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001859f  mov     rcx, [rbp+57h+var_60]; this
0x1800185a3  test    rcx, rcx
0x1800185a6  jz      short loc_1800185AE
0x1800185a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800185ad  nop
0x1800185ae  lea     rcx, [rbp+57h+var_90]
0x1800185b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800185b7  nop
0x1800185b8  mov     rcx, [rdi]
0x1800185bb  mov     rax, [rcx]
0x1800185be  lea     r8, [rbp+57h+var_88]
0x1800185c2  lea     rdx, _GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53
0x1800185c9  mov     rax, [rax]
0x1800185cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d1  nop
0x1800185d2  test    eax, eax
0x1800185d4  js      loc_180018680
0x1800185da  test    rbx, rbx
0x1800185dd  jz      loc_18001850E
0x1800185e3  mov     rcx, rbx; this
0x1800185e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800185eb  jmp     loc_18001850E
0x1800185f0  mov     rax, [rdi]
0x1800185f3  mov     rcx, rdi
0x1800185f6  mov     rax, [rax]
0x1800185f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fe  mov     rcx, rdi; this
0x180018601  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180018606  jmp     loc_18001850E
0x18001860b  mov     [rbp+57h+var_90], r15
0x18001860f  mov     [rbp+57h+var_50], r15
0x180018613  mov     r9d, 3Dh ; '='; unsigned int
0x180018619  lea     r8d, [r9+1]; unsigned int
0x18001861d  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180018624  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x180018628  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001862d  lea     rdx, [rbp+57h+var_90]
0x180018631  mov     rcx, [rbp+57h+var_50]
0x180018635  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x18001863a  test    eax, eax
0x18001863c  jns     loc_18001855D
0x180018642  mov     [rsp+0C0h+var_98], 1F4h; int
0x18001864a  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180018651  mov     [rsp+0C0h+var_A0], rcx; char *
0x180018656  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x18001865d  lea     r8, aWindowsFoundat_1; "Windows::Foundation::ActivateInstance( "...
0x180018664  mov     edx, eax; int
0x180018666  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001866a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18001866f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180018676  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001867a  call    _CxxThrowException_0
0x180018680  mov     [rsp+0C0h+var_98], 1FAh; int
0x180018688  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001868f  mov     [rsp+0C0h+var_A0], rcx; char *
0x180018694  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x18001869b  lea     r8, aPackagemanager_6; "packageManagerInternal->CopyTo(riid, ob"...
0x1800186a2  mov     edx, eax; int
0x1800186a4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800186a8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800186ad  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800186b4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800186b8  call    _CxxThrowException_0
0x1800186be  mov     [rsp+0C0h+var_98], 20Ah; int
0x1800186c6  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800186cd  mov     [rsp+0C0h+var_A0], rcx; char *
0x1800186d2  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x1800186d9  lea     r8, aPackagemanager; "packageManager->CopyTo(riid, object)"
0x1800186e0  mov     edx, eax; int
0x1800186e2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800186e6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800186eb  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800186f2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800186f6  call    _CxxThrowException_0
0x1800186fc  mov     rcx, [rbp+57h+var_88]
0x180018700  jmp     loc_180018528
```
