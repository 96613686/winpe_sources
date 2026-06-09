# _lambda_4e7b82f739ce8eeaa87e01b686e8b1eb_::operator()(void)

- ea: `0x180045b14`
- end: `0x180045dfd`
- name: `??R_lambda_4e7b82f739ce8eeaa87e01b686e8b1eb_@@QEBA@XZ`
- size: `745`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800476c0`

## callees

- `0x180002958`
- `0x18000a520`
- `0x18000d17c`
- `0x18000e4a0`
- `0x180011cac`
- `0x180012028`
- `0x180013b0c`
- `0x180014384`
- `0x18001bee0`
- `0x180027a4c`
- `0x180028814`
- `0x18002c824`
- `0x180035c18`
- `0x18003e210`
- `0x18003ecb4`
- `0x180045b14`

## string_xrefs

- `0x180045cca`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045d06`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045d47`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045d88`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045dc9`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045d5a`: `!IsCallerLowIL(userContextToken)`
- `0x180045cd6`: `AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()`
- `0x180045d12`: `AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()`
- `0x180045d53`: `AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()`
- `0x180045d94`: `AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()`
- `0x180045dd5`: `AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()`
- `0x180045d9b`: `localTask`
- `0x180045ddc`: `localTask.As(&taskToWrap)`
- `0x180045cdd`: `ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(task, taskToWrap.Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_4e7b82f739ce8eeaa87e01b686e8b1eb_::operator()(__int64 a1)
{
  AppReadiness::Api *v2; // rcx
  __int64 v3; // rcx
  _QWORD *v4; // r9
  AppReadiness::User *v5; // rbx
  struct ITask **v6; // rax
  int v7; // edx
  int v8; // edx
  __int64 v10; // [rsp+30h] [rbp-29h] BYREF
  AppReadiness::User *v11; // [rsp+38h] [rbp-21h] BYREF
  struct ITask *v12; // [rsp+40h] [rbp-19h] BYREF
  struct ITask *v13; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v15[40]; // [rsp+78h] [rbp+1Fh] BYREF

  if ( AppReadiness::Api::IsDisabledForAuditMode(*(AppReadiness::Api **)a1) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)v15,
      -2147024886,
      "!IsDisabledForAuditMode()",
      "AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      112);
    throw (Windows::HResultException *)v15;
  }
  if ( AppReadiness::Api::IsCallerLowIL(v2, **(_QWORD **)(a1 + 8)) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)v15,
      -2147024891,
      "!IsCallerLowIL(userContextToken)",
      "AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      113);
    throw (Windows::HResultException *)v15;
  }
  AppReadiness::Api::CreateUser(v3, &v11, **(_QWORD **)(a1 + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = (_QWORD *)((char *)v11 + 64);
    if ( *((_QWORD *)v11 + 11) > 7u )
      v4 = (_QWORD *)*v4;
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids,
      (_DWORD)v4,
      **(_QWORD **)(a1 + 16),
      **(_DWORD **)(a1 + 24));
  }
  v5 = v11;
  std::wstring::wstring(v15, **(_QWORD **)(a1 + 16));
  AppReadiness::User::FindTask((__int64)v5, &v10, (__int64)v15);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v15);
  if ( !v10 )
  {
    if ( (**(_BYTE **)(a1 + 24) & 4) == 0
      || (v6 = AppReadiness::User::CreateTask(v11, &v13, **(const WCHAR ***)(a1 + 16), 0),
          Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(&v10, v6),
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13),
          !v10) )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        -2147023728,
        "localTask",
        "AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        123);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v12 = 0;
  v7 = Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(&v10, &v12);
  if ( v7 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v7,
      "localTask.As(&taskToWrap)",
      "AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      125);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v13 = v12;
  v8 = Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(**(void ****)(a1 + 32));
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v8,
      "ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(tas"
      "k, taskToWrap.Get())",
      "AppReadiness::Api::GetTaskForUser::<lambda_4e7b82f739ce8eeaa87e01b686e8b1eb>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      126);
    throw (Windows::HResultException *)pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
}

```

## disassembly

```asm
0x180045b14  mov     [rsp-8+arg_8], rbx
0x180045b19  mov     [rsp-8+arg_10], rdi
0x180045b1e  push    rbp
0x180045b1f  lea     rbp, [rsp-57h]
0x180045b24  sub     rsp, 0B0h
0x180045b2b  mov     rax, cs:__security_cookie
0x180045b32  xor     rax, rsp
0x180045b35  mov     [rbp+57h+var_10], rax
0x180045b39  mov     rdi, rcx
0x180045b3c  mov     rcx, [rcx]; this
0x180045b3f  call    ?IsDisabledForAuditMode@Api@AppReadiness@@AEAA_NXZ; AppReadiness::Api::IsDisabledForAuditMode(void)
0x180045b44  test    al, al
0x180045b46  jnz     loc_180045CFE
0x180045b4c  mov     rdx, [rdi+8]
0x180045b50  mov     rdx, [rdx]; unsigned __int64
0x180045b53  call    ?IsCallerLowIL@Api@AppReadiness@@AEAA_N_K@Z; AppReadiness::Api::IsCallerLowIL(unsigned __int64)
0x180045b58  test    al, al
0x180045b5a  jnz     loc_180045D3F
0x180045b60  mov     r8, [rdi+8]
0x180045b64  mov     r8, [r8]
0x180045b67  lea     rdx, [rbp+57h+var_78]
0x180045b6b  call    ?CreateUser@Api@AppReadiness@@AEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@_K@Z; AppReadiness::Api::CreateUser(unsigned __int64)
0x180045b70  nop
0x180045b71  lea     rax, WPP_GLOBAL_Control
0x180045b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b7f  cmp     rcx, rax
0x180045b82  jz      short loc_180045BC9
0x180045b84  test    byte ptr [rcx+1Ch], 4
0x180045b88  jz      short loc_180045BC9
0x180045b8a  mov     rax, [rdi+18h]
0x180045b8e  mov     r8d, [rax]
0x180045b91  mov     rax, [rdi+10h]
0x180045b95  mov     r10, [rax]
0x180045b98  mov     r9, [rbp+57h+var_78]
0x180045b9c  add     r9, 40h ; '@'
0x180045ba0  cmp     qword ptr [r9+18h], 7
0x180045ba5  jbe     short loc_180045BAA
0x180045ba7  mov     r9, [r9]
0x180045baa  mov     edx, 0Ah
0x180045baf  mov     [rsp+0B0h+var_88], r8d
0x180045bb4  mov     [rsp+0B0h+var_90], r10
0x180045bb9  lea     r8, WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids
0x180045bc0  mov     rcx, [rcx+10h]
0x180045bc4  call    WPP_SF_SSd
0x180045bc9  mov     rbx, [rbp+57h+var_78]
0x180045bcd  mov     rdx, [rdi+10h]
0x180045bd1  mov     rdx, [rdx]
0x180045bd4  lea     rcx, [rbp+57h+var_38]
0x180045bd8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045bdd  nop
0x180045bde  lea     r8, [rbp+57h+var_38]
0x180045be2  lea     rdx, [rbp+57h+var_80]
0x180045be6  mov     rcx, rbx
0x180045be9  call    ?FindTask@User@AppReadiness@@QEBA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FindTaskFlags@2@@Z; AppReadiness::User::FindTask(std::wstring const &,AppReadiness::FindTaskFlags)
0x180045bee  nop
0x180045bef  lea     rcx, [rbp+57h+var_38]
0x180045bf3  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180045bf8  mov     rax, [rbp+57h+var_80]
0x180045bfc  test    rax, rax
0x180045bff  jnz     short loc_180045C47
0x180045c01  mov     rax, [rdi+18h]
0x180045c05  test    byte ptr [rax], 4
0x180045c08  jz      loc_180045D80
0x180045c0e  mov     r8, [rdi+10h]
0x180045c12  xor     r9d, r9d
0x180045c15  mov     r8, [r8]
0x180045c18  lea     rdx, [rbp+57h+var_68]
0x180045c1c  mov     rcx, [rbp+57h+var_78]; this
0x180045c20  call    ?CreateTask@User@AppReadiness@@QEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@PEBGPEAUIAppReadinessTaskCallback@@@Z; AppReadiness::User::CreateTask(ushort const *,IAppReadinessTaskCallback *)
0x180045c25  mov     rdx, rax
0x180045c28  lea     rcx, [rbp+57h+var_80]
0x180045c2c  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180045c31  lea     rcx, [rbp+57h+var_68]
0x180045c35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045c3a  mov     rax, [rbp+57h+var_80]
0x180045c3e  test    rax, rax
0x180045c41  jz      loc_180045D80
0x180045c47  mov     [rbp+57h+var_70], 0
0x180045c4f  lea     rdx, [rbp+57h+var_70]
0x180045c53  lea     rcx, [rbp+57h+var_80]
0x180045c57  call    ??$As@UIAppReadinessTask@@@?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppReadinessTask@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppReadinessTask>>)
0x180045c5c  mov     edx, eax; int
0x180045c5e  test    eax, eax
0x180045c60  js      loc_180045DC1
0x180045c66  mov     rax, [rbp+57h+var_70]
0x180045c6a  mov     [rbp+57h+var_68], rax
0x180045c6e  mov     rcx, [rdi+20h]
0x180045c72  lea     rdx, [rbp+57h+var_68]
0x180045c76  mov     rcx, [rcx]; void **
0x180045c79  call    ??$MakeAndInitializeDisconnectableObject@VExternalTaskWrapper@Impl@AppReadiness@@UIAppReadinessTask@@PEAU4@@ComDisconnectableObjectManager@Internal@Windows@@SAJPEAPEAUIAppReadinessTask@@$$QEAPEAU3@@Z; Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(IAppReadinessTask * *,IAppReadinessTask * &&)
0x180045c7e  mov     edx, eax; int
0x180045c80  test    eax, eax
0x180045c82  js      short loc_180045CC2
0x180045c84  lea     rcx, [rbp+57h+var_70]
0x180045c88  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045c8d  nop
0x180045c8e  lea     rcx, [rbp+57h+var_80]
0x180045c92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045c97  nop
0x180045c98  lea     rcx, [rbp+57h+var_78]
0x180045c9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045ca1  mov     rcx, [rbp+57h+var_10]
0x180045ca5  xor     rcx, rsp; StackCookie
0x180045ca8  call    __security_check_cookie
0x180045cad  lea     r11, [rsp+0B0h+var_s0]
0x180045cb5  mov     rbx, [r11+18h]
0x180045cb9  mov     rdi, [r11+20h]
0x180045cbd  mov     rsp, r11
0x180045cc0  pop     rbp
0x180045cc1  retn
0x180045cc2  mov     [rsp+0B0h+var_88], 7Eh ; '~'; int
0x180045cca  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045cd1  mov     [rsp+0B0h+var_90], rax; char *
0x180045cd6  lea     r9, aAppreadinessAp_8; "AppReadiness::Api::GetTaskForUser::<lam"...
0x180045cdd  lea     r8, aComdisconnecta_1; "ComDisconnectableObjectManager::MakeAnd"...
0x180045ce4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045ce8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045ced  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045cf4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045cf8  call    _CxxThrowException_0
0x180045cfe  mov     [rsp+0B0h+var_88], 70h ; 'p'; int
0x180045d06  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045d0d  mov     [rsp+0B0h+var_90], rax; char *
0x180045d12  lea     r9, aAppreadinessAp_8; "AppReadiness::Api::GetTaskForUser::<lam"...
0x180045d19  lea     r8, aIsdisabledfora; "!IsDisabledForAuditMode()"
0x180045d20  mov     edx, 8007000Ah; int
0x180045d25  lea     rcx, [rbp+57h+var_38]; this
0x180045d29  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045d2e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045d35  lea     rcx, [rbp+57h+var_38]; pExceptionObject
0x180045d39  call    _CxxThrowException_0
0x180045d3f  mov     [rsp+0B0h+var_88], 71h ; 'q'; int
0x180045d47  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045d4e  mov     [rsp+0B0h+var_90], rax; char *
0x180045d53  lea     r9, aAppreadinessAp_8; "AppReadiness::Api::GetTaskForUser::<lam"...
0x180045d5a  lea     r8, aIscallerlowilU; "!IsCallerLowIL(userContextToken)"
0x180045d61  mov     edx, 80070005h; int
0x180045d66  lea     rcx, [rbp+57h+var_38]; this
0x180045d6a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045d6f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045d76  lea     rcx, [rbp+57h+var_38]; pExceptionObject
0x180045d7a  call    _CxxThrowException_0
0x180045d80  mov     [rsp+0B0h+var_88], 7Bh ; '{'; int
0x180045d88  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045d8f  mov     [rsp+0B0h+var_90], rax; char *
0x180045d94  lea     r9, aAppreadinessAp_8; "AppReadiness::Api::GetTaskForUser::<lam"...
0x180045d9b  lea     r8, aLocaltask; "localTask"
0x180045da2  mov     edx, 80070490h; int
0x180045da7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045dab  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045db0  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045db7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045dbb  call    _CxxThrowException_0
0x180045dc1  mov     [rsp+0B0h+var_88], 7Dh ; '}'; int
0x180045dc9  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045dd0  mov     [rsp+0B0h+var_90], rax; char *
0x180045dd5  lea     r9, aAppreadinessAp_8; "AppReadiness::Api::GetTaskForUser::<lam"...
0x180045ddc  lea     r8, aLocaltaskAsTas; "localTask.As(&taskToWrap)"
0x180045de3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045de7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045dec  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045df3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045df7  call    _CxxThrowException_0
```
