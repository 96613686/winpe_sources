# AppReadiness::PackageInfo::GetPackageManager(_GUID const &,void * *)

- ea: `0x180017a08`
- end: `0x180017d92`
- name: `?GetPackageManager@PackageInfo@AppReadiness@@KAXAEBU_GUID@@PEAPEAX@Z`
- size: `906`
- prototype: `void __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180017998`
- `0x1800382e0`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a470`
- `0x180017a08`
- `0x180018aa8`
- `0x180018ac8`
- `0x1800203d8`
- `0x1800276e0`
- `0x180027a4c`
- `0x1800332e4`
- `0x180033600`
- `0x180033668`
- `0x180038350`
- `0x18003b920`
- `0x18003e210`
- `0x18003ecb4`
- `0x180075b4c`
- `0x180079010`

## import_xrefs

- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180017a4c`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180017ae1`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180017a4c`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180017ae1`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180017a7b`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180017b10`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180017a7b`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180017b10`

## string_xrefs

- `0x180017b59`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180017ca1`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180017d1e`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180017d5c`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180017b65`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180017cad`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180017d2a`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180017d68`: `AppReadiness::PackageInfo::GetPackageManager`
- `0x180017cb4`: `packageManagerInternal->CopyTo(riid, object)`
- `0x180017d6f`: `packageManager->CopyTo(riid, object)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AppReadiness::PackageInfo::GetPackageManager(const struct _GUID *a1, void **a2)
{
  std::_Ref_count_base *v4; // rbx
  _QWORD *v5; // rsi
  volatile signed __int32 *v6; // rdi
  int v7; // eax
  _QWORD *v8; // rsi
  int v9; // eax
  __int64 *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rax
  int v13; // eax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  int v17; // eax
  __int64 v18; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h]
  std::_Ref_count_base *v20; // [rsp+40h] [rbp-40h]
  HSTRING_HEADER pExceptionObject; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h]

  if ( !memcmp_0(a1, &GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef, 0x10u) )
  {
    _Lock_shared_ptr_spin_lock();
    v4 = qword_1800A4E40;
    if ( qword_1800A4E40 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_1800A4E40 + 2);
      v4 = qword_1800A4E40;
    }
    v8 = (_QWORD *)AppReadiness::PackageInfo::s_packageManagerInternal;
    v19 = AppReadiness::PackageInfo::s_packageManagerInternal;
    v20 = v4;
    v6 = (volatile signed __int32 *)v4;
    _Unlock_shared_ptr_spin_lock();
    if ( !v8 )
    {
      v18 = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pExceptionObject,
        L"Windows.Management.Deployment.Internal.PackageManagerInternal",
        0x3Eu,
        0x3Du);
      v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
             v22,
             &v18);
      if ( v9 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          v9,
          "Windows::Foundation::ActivateInstance( HStringReference(RuntimeClass_Windows_Management_Deployment_Internal_Pa"
          "ckageManagerInternal).Get(), &packageManagerInternalPtr)",
          "AppReadiness::PackageInfo::GetPackageManager",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
          500);
        throw (Windows::HResultException *)&pExceptionObject;
      }
      v10 = std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
              &pExceptionObject,
              (__int64)&v18);
      std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
        v11,
        v10);
      v12 = (_QWORD *)std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>((__int64)&pExceptionObject);
      v8 = (_QWORD *)*v12;
      v4 = (std::_Ref_count_base *)v12[1];
      *v12 = 0;
      v12[1] = 0;
      v19 = (__int64)v8;
      v20 = v4;
      if ( v6 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
      if ( *(_QWORD *)&pExceptionObject.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&pExceptionObject.Reserved.Reserved2[8]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      v6 = (volatile signed __int32 *)v4;
    }
    v13 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v8)(*v8, a1, a2);
    if ( v13 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v13,
        "packageManagerInternal->CopyTo(riid, object)",
        "AppReadiness::PackageInfo::GetPackageManager",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        506);
      throw (Windows::HResultException *)&pExceptionObject;
    }
  }
  else
  {
    _Lock_shared_ptr_spin_lock();
    v4 = qword_1800A4E30;
    if ( qword_1800A4E30 )
    {
      _InterlockedIncrement((volatile signed __int32 *)qword_1800A4E30 + 2);
      v4 = qword_1800A4E30;
    }
    v5 = (_QWORD *)AppReadiness::PackageInfo::s_packageManager;
    v19 = AppReadiness::PackageInfo::s_packageManager;
    v20 = v4;
    v6 = (volatile signed __int32 *)v4;
    _Unlock_shared_ptr_spin_lock();
    if ( !v5 )
    {
      v18 = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pExceptionObject,
        L"Windows.Management.Deployment.PackageManager",
        0x2Du,
        0x2Cu);
      v17 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(
              v22,
              &v18);
      if ( v17 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          v17,
          "Windows::Foundation::ActivateInstance( HStringReference(RuntimeClass_Windows_Management_Deployment_PackageMana"
          "ger).Get(), &packageManagerPtr)",
          "AppReadiness::PackageInfo::GetPackageManager",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
          516);
        throw (Windows::HResultException *)&pExceptionObject;
      }
      v14 = std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(
              &pExceptionObject,
              (char *)&v18);
      std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(v15, v14);
      v16 = std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(&pExceptionObject);
      v5 = (_QWORD *)*v16;
      v4 = (std::_Ref_count_base *)v16[1];
      *v16 = 0;
      v16[1] = 0;
      v19 = (__int64)v5;
      v20 = v4;
      if ( v6 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
      if ( *(_QWORD *)&pExceptionObject.Reserved.Reserved2[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&pExceptionObject.Reserved.Reserved2[8]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      v6 = (volatile signed __int32 *)v4;
    }
    v7 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v5)(*v5, a1, a2);
    if ( v7 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v7,
        "packageManager->CopyTo(riid, object)",
        "AppReadiness::PackageInfo::GetPackageManager",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        522);
      throw (Windows::HResultException *)&pExceptionObject;
    }
  }
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v6);
    }
  }
}

```

## disassembly

```asm
0x180017a08  mov     [rsp-28h+arg_10], rbx
0x180017a0d  push    rbp
0x180017a0e  push    rsi
0x180017a0f  push    rdi
0x180017a10  push    r14
0x180017a12  push    r15
0x180017a14  mov     rbp, rsp
0x180017a17  sub     rsp, 80h
0x180017a1e  mov     rax, cs:__security_cookie
0x180017a25  xor     rax, rsp
0x180017a28  mov     [rbp+var_10], rax
0x180017a2c  mov     r15, rdx
0x180017a2f  mov     r14, rcx
0x180017a32  mov     r8d, 10h; Size
0x180017a38  lea     rdx, _GUID_ee89017c_6b2d_4c86_9d83_821c4f38e2ef; Buf2
0x180017a3f  call    memcmp_0
0x180017a44  test    eax, eax
0x180017a46  jz      loc_180017AE1
0x180017a4c  call    cs:__imp__Lock_shared_ptr_spin_lock
0x180017a52  mov     rbx, cs:qword_1800A4E30
0x180017a59  test    rbx, rbx
0x180017a5c  jz      short loc_180017A69
0x180017a5e  lock inc dword ptr [rbx+8]
0x180017a62  mov     rbx, cs:qword_1800A4E30
0x180017a69  mov     rsi, cs:?s_packageManager@PackageInfo@AppReadiness@@1V?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@A; std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> AppReadiness::PackageInfo::s_packageManager
0x180017a70  mov     [rbp+var_48], rsi
0x180017a74  mov     [rbp+var_40], rbx
0x180017a78  mov     rdi, rbx
0x180017a7b  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x180017a81  nop
0x180017a82  test    rsi, rsi
0x180017a85  jz      loc_180017CD7
0x180017a8b  mov     rcx, [rsi]
0x180017a8e  mov     rax, [rcx]
0x180017a91  mov     r8, r15
0x180017a94  mov     rdx, r14
0x180017a97  mov     rax, [rax]
0x180017a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a9f  nop
0x180017aa0  test    eax, eax
0x180017aa2  js      loc_180017D54
0x180017aa8  test    rbx, rbx
0x180017aab  jz      short loc_180017ABE
0x180017aad  or      eax, 0FFFFFFFFh
0x180017ab0  lock xadd [rdi+8], eax
0x180017ab5  cmp     eax, 1
0x180017ab8  jz      loc_180017C15
0x180017abe  mov     rcx, [rbp+var_10]
0x180017ac2  xor     rcx, rsp; StackCookie
0x180017ac5  call    __security_check_cookie
0x180017aca  mov     rbx, [rsp+80h+arg_10]
0x180017ad2  add     rsp, 80h
0x180017ad9  pop     r15
0x180017adb  pop     r14
0x180017add  pop     rdi
0x180017ade  pop     rsi
0x180017adf  pop     rbp
0x180017ae0  retn
0x180017ae1  call    cs:__imp__Lock_shared_ptr_spin_lock
0x180017ae7  mov     rbx, cs:qword_1800A4E40
0x180017aee  test    rbx, rbx
0x180017af1  jz      short loc_180017AFE
0x180017af3  lock inc dword ptr [rbx+8]
0x180017af7  mov     rbx, cs:qword_1800A4E40
0x180017afe  mov     rsi, cs:?s_packageManagerInternal@PackageInfo@AppReadiness@@1V?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@A; std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> AppReadiness::PackageInfo::s_packageManagerInternal
0x180017b05  mov     [rbp+var_48], rsi
0x180017b09  mov     [rbp+var_40], rbx
0x180017b0d  mov     rdi, rbx
0x180017b10  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x180017b16  nop
0x180017b17  test    rsi, rsi
0x180017b1a  jnz     loc_180017BF3
0x180017b20  mov     [rbp+var_50], rsi
0x180017b24  mov     [rbp+var_20], rsi
0x180017b28  lea     r9d, [rsi+3Dh]; unsigned int
0x180017b2c  lea     r8d, [rsi+3Eh]; unsigned int
0x180017b30  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180017b37  lea     rcx, [rbp+pExceptionObject]; hstringHeader
0x180017b3b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017b40  lea     rdx, [rbp+var_50]
0x180017b44  mov     rcx, [rbp+var_20]
0x180017b48  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x180017b4d  test    eax, eax
0x180017b4f  jns     short loc_180017B8F
0x180017b51  mov     [rsp+80h+var_58], 1F4h; int
0x180017b59  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017b60  mov     [rsp+80h+var_60], rcx; char *
0x180017b65  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x180017b6c  lea     r8, aWindowsFoundat_1; "Windows::Foundation::ActivateInstance( "...
0x180017b73  mov     edx, eax; int
0x180017b75  lea     rcx, [rbp+pExceptionObject]; this
0x180017b79  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017b7e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180017b85  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017b89  call    _CxxThrowException_0
0x180017b8f  lea     rdx, [rbp+var_50]
0x180017b93  lea     rcx, [rbp+pExceptionObject]
0x180017b97  call    ??$make_shared@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@V123@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@$$QEAV?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Z; std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal> &&)
0x180017b9c  mov     rdx, rax
0x180017b9f  call    ??$atomic_store@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YAXPEAV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@V10@@Z; std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> *,std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x180017ba4  lea     rcx, [rbp+pExceptionObject]
0x180017ba8  call    ??$atomic_load@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@0@PEBV10@@Z; std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>> const *)
0x180017bad  mov     rsi, [rax]
0x180017bb0  mov     rbx, [rax+8]
0x180017bb4  mov     qword ptr [rax], 0
0x180017bbb  mov     qword ptr [rax+8], 0
0x180017bc3  mov     [rbp+var_48], rsi
0x180017bc7  mov     [rbp+var_40], rbx
0x180017bcb  test    rdi, rdi
0x180017bce  jz      short loc_180017BD8
0x180017bd0  mov     rcx, rdi; this
0x180017bd3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017bd8  mov     rcx, [rbp+var_30]; this
0x180017bdc  test    rcx, rcx
0x180017bdf  jz      short loc_180017BE7
0x180017be1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017be6  nop
0x180017be7  lea     rcx, [rbp+var_50]
0x180017beb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017bf0  mov     rdi, rbx
0x180017bf3  mov     rcx, [rsi]
0x180017bf6  mov     rax, [rcx]
0x180017bf9  mov     r8, r15
0x180017bfc  mov     rdx, r14
0x180017bff  mov     rax, [rax]
0x180017c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c07  nop
0x180017c08  test    eax, eax
0x180017c0a  js      loc_180017C99
0x180017c10  jmp     loc_180017AA8
0x180017c15  mov     rax, [rdi]
0x180017c18  mov     rcx, rdi
0x180017c1b  mov     rax, [rax]
0x180017c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c23  mov     rcx, rdi; this
0x180017c26  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180017c2b  jmp     loc_180017ABE
0x180017c30  lea     rdx, [rbp+var_50]
0x180017c34  lea     rcx, [rbp+pExceptionObject]
0x180017c38  call    ??$make_shared@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@V123@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@$$QEAV?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Z; std::make_shared<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>,Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2> &&)
0x180017c3d  mov     rdx, rax
0x180017c40  call    ??$atomic_store@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YAXPEAV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@V10@@Z; std::atomic_store<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> *,std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>)
0x180017c45  lea     rcx, [rbp+pExceptionObject]
0x180017c49  call    ??$atomic_load@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@std@@YA?AV?$shared_ptr@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@0@PEBV10@@Z; std::atomic_load<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(std::shared_ptr<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>> const *)
0x180017c4e  mov     rsi, [rax]
0x180017c51  mov     rbx, [rax+8]
0x180017c55  mov     qword ptr [rax], 0
0x180017c5c  mov     qword ptr [rax+8], 0
0x180017c64  mov     [rbp+var_48], rsi
0x180017c68  mov     [rbp+var_40], rbx
0x180017c6c  test    rdi, rdi
0x180017c6f  jz      short loc_180017C79
0x180017c71  mov     rcx, rdi; this
0x180017c74  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017c79  mov     rcx, [rbp+var_30]; this
0x180017c7d  test    rcx, rcx
0x180017c80  jz      short loc_180017C88
0x180017c82  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017c87  nop
0x180017c88  lea     rcx, [rbp+var_50]
0x180017c8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c91  mov     rdi, rbx
0x180017c94  jmp     loc_180017A8B
0x180017c99  mov     [rsp+80h+var_58], 1FAh; int
0x180017ca1  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017ca8  mov     [rsp+80h+var_60], rcx; char *
0x180017cad  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x180017cb4  lea     r8, aPackagemanager_6; "packageManagerInternal->CopyTo(riid, ob"...
0x180017cbb  mov     edx, eax; int
0x180017cbd  lea     rcx, [rbp+pExceptionObject]; this
0x180017cc1  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017cc6  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180017ccd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017cd1  call    _CxxThrowException_0
0x180017cd7  mov     [rbp+var_50], 0
0x180017cdf  mov     [rbp+var_20], 0
0x180017ce7  mov     r9d, 2Ch ; ','; unsigned int
0x180017ced  lea     r8d, [r9+1]; unsigned int
0x180017cf1  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180017cf8  lea     rcx, [rbp+pExceptionObject]; hstringHeader
0x180017cfc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017d01  lea     rdx, [rbp+var_50]
0x180017d05  mov     rcx, [rbp+var_20]
0x180017d09  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager2>>)
0x180017d0e  test    eax, eax
0x180017d10  jns     loc_180017C30
0x180017d16  mov     [rsp+80h+var_58], 204h; int
0x180017d1e  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017d25  mov     [rsp+80h+var_60], rcx; char *
0x180017d2a  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x180017d31  lea     r8, aWindowsFoundat_11; "Windows::Foundation::ActivateInstance( "...
0x180017d38  mov     edx, eax; int
0x180017d3a  lea     rcx, [rbp+pExceptionObject]; this
0x180017d3e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017d43  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180017d4a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d4e  call    _CxxThrowException_0
0x180017d54  mov     [rsp+80h+var_58], 20Ah; int
0x180017d5c  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017d63  mov     [rsp+80h+var_60], rcx; char *
0x180017d68  lea     r9, aAppreadinessPa_10; "AppReadiness::PackageInfo::GetPackageMa"...
0x180017d6f  lea     r8, aPackagemanager; "packageManager->CopyTo(riid, object)"
0x180017d76  mov     edx, eax; int
0x180017d78  lea     rcx, [rbp+pExceptionObject]; this
0x180017d7c  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017d81  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180017d88  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d8c  call    _CxxThrowException_0
```
