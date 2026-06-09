# AppReadiness::User::OpenFirewallPolicyStore(void)

- ea: `0x180025910`
- end: `0x180025b80`
- name: `?OpenFirewallPolicyStore@User@AppReadiness@@IEAAXXZ`
- size: `624`
- prototype: `void __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002ebc`

## callees

- `0x180002958`
- `0x180016d80`
- `0x18001e6e4`
- `0x1800203d8`
- `0x180024d04`
- `0x180025910`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180049ba0`
- `0x18005aa44`
- `0x18005d590`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002597a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002597a`

## string_xrefs

- `0x18002595b`: `Windows.System.Threading.ThreadPool`
- `0x180025a90`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180025ace`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180025b0c`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180025b4a`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180025a9c`: `AppReadiness::User::OpenFirewallPolicyStore`
- `0x180025ada`: `AppReadiness::User::OpenFirewallPolicyStore`
- `0x180025b18`: `AppReadiness::User::OpenFirewallPolicyStore`
- `0x180025b56`: `AppReadiness::User::OpenFirewallPolicyStore`
- `0x180025b1f`: `threadpool->RunAsync(Microsoft::WRL::Callback<IWorkItemHandler>(wistd::move(asyncAction)).Get(), action.GetAddressOf())`
- `0x180025ae1`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPool).Get(), threadpool.GetAddressOf())`
- `0x180025b5d`: `wil::wait_for_completion_or_timeout_nothrow(action.Get(), c_FirewallTimeout, &timedOut)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AppReadiness::User::OpenFirewallPolicyStore(AppReadiness::User *this)
{
  int ActivationFactory; // eax
  __int64 v2; // rbx
  __int64 (__fastcall *v3)(__int64, AppReadiness::User *, _QWORD); // rsi
  AppReadiness::User **v4; // rax
  AppReadiness::User *v5; // rdi
  int v6; // ebx
  DWORD v7; // edx
  int v8; // r8d
  int v9; // eax
  char IsEnabled; // al
  AppReadiness *v11; // rcx
  char v12; // bl
  __int64 v13; // rcx
  __int64 v14; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-19h] BYREF
  AppReadiness::User *v18; // [rsp+48h] [rbp-11h] BYREF
  __int64 v19; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+58h] [rbp-1h] BYREF
  __int64 v21; // [rsp+70h] [rbp+17h]

  if ( !*((_QWORD *)this + 48) )
  {
    v18 = this;
    v16 = 0;
    v21 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &pExceptionObject,
      L"Windows.System.Threading.ThreadPool",
      0x24u,
      0x23u);
    ActivationFactory = RoGetActivationFactory(v21, &GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91, &v16);
    if ( ActivationFactory < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        ActivationFactory,
        "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_System_Threading_ThreadPool).Get"
        "(), threadpool.GetAddressOf())",
        "AppReadiness::User::OpenFirewallPolicyStore",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2678);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v17 = 0;
    v2 = v16;
    v3 = *(__int64 (__fastcall **)(__int64, AppReadiness::User *, _QWORD))(*(_QWORD *)v16 + 48LL);
    v4 = (AppReadiness::User **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::System::Threading::IWorkItemHandler::___Windows::Foundation::IAsyncAction____::DelegateInvokeHelper_Windows::System::Threading::IWorkItemHandler__lambda_61fc7db92e72dc93e43da743567fa07a___1_Windows::Foundation::IAsyncAction_____lambda_61fc7db92e72dc93e43da743567fa07a___(
                                  &v19,
                                  &v18);
    v5 = *v4;
    v18 = *v4;
    *v4 = 0;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release();
    }
    v6 = v3(v2, v5, &v17);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( v6 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v6,
        "threadpool->RunAsync(Microsoft::WRL::Callback<IWorkItemHandler>(wistd::move(asyncAction)).Get(), action.GetAddressOf())",
        "AppReadiness::User::OpenFirewallPolicyStore",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2681);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    v15[0] = 0;
    v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v17, v7, v8, v15);
    if ( v9 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        v9,
        "wil::wait_for_completion_or_timeout_nothrow(action.Get(), c_FirewallTimeout, &timedOut)",
        "AppReadiness::User::OpenFirewallPolicyStore",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2684);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARSFirewallLog>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ARSFirewallLog>::GetImpl'::`2'::impl);
    v12 = v15[0];
    if ( IsEnabled )
    {
      if ( !v15[0] )
      {
LABEL_12:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        v14 = v16;
        if ( v16 )
        {
          v16 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        return;
      }
      AppReadiness::LogFirewallServiceState(v11);
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
        McTemplateU0d_EventWriteTransfer(v13, User_FWOpenPolicyStore_Stop, 2147943860LL);
    }
    if ( v12 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        -2147023436,
        "!timedOut",
        "AppReadiness::User::OpenFirewallPolicyStore",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2695);
      throw (Windows::HResultException *)&pExceptionObject;
    }
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180025910  push    rbp
0x180025912  push    rbx
0x180025913  push    rsi
0x180025914  push    rdi
0x180025915  lea     rbp, [rsp-3Fh]
0x18002591a  sub     rsp, 98h
0x180025921  mov     rax, cs:__security_cookie
0x180025928  xor     rax, rsp
0x18002592b  mov     [rbp+57h+var_30], rax
0x18002592f  cmp     qword ptr [rcx+180h], 0
0x180025937  jnz     loc_180025A70
0x18002593d  mov     [rbp+57h+var_68], rcx
0x180025941  mov     [rbp+57h+var_78], 0
0x180025949  mov     [rbp+57h+var_40], 0
0x180025951  mov     r9d, 23h ; '#'; unsigned int
0x180025957  lea     r8d, [r9+1]; unsigned int
0x18002595b  lea     rdx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x180025962  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x180025966  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002596b  lea     r8, [rbp+57h+var_78]
0x18002596f  lea     rdx, _GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91
0x180025976  mov     rcx, [rbp+57h+var_40]
0x18002597a  call    cs:__imp_RoGetActivationFactory
0x180025980  test    eax, eax
0x180025982  js      loc_180025AC6
0x180025988  mov     [rbp+57h+var_70], 0
0x180025990  mov     rbx, [rbp+57h+var_78]
0x180025994  mov     rax, [rbx]
0x180025997  mov     rsi, [rax+30h]
0x18002599b  lea     rdx, [rbp+57h+var_68]
0x18002599f  lea     rcx, [rbp+57h+var_60]
0x1800259a3  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__System__Threading__IWorkItemHandler_____Windows__Foundation__IAsyncAction______DelegateInvokeHelper_Windows__System__Threading__IWorkItemHandler__lambda_61fc7db92e72dc93e43da743567fa07a___1_Windows__Foundation__IAsyncAction_____lambda_61fc7db92e72dc93e43da743567fa07a___
0x1800259a8  mov     rdi, [rax]
0x1800259ab  mov     [rbp+57h+var_68], rdi
0x1800259af  mov     qword ptr [rax], 0
0x1800259b6  mov     rcx, [rbp+57h+var_60]
0x1800259ba  test    rcx, rcx
0x1800259bd  jz      short loc_1800259CD
0x1800259bf  mov     [rbp+57h+var_60], 0
0x1800259c7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *>>::Release(void)
0x1800259cc  nop
0x1800259cd  lea     r8, [rbp+57h+var_70]
0x1800259d1  mov     rdx, rdi
0x1800259d4  mov     rcx, rbx
0x1800259d7  mov     rax, rsi
0x1800259da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259df  mov     ebx, eax
0x1800259e1  lea     rcx, [rbp+57h+var_68]
0x1800259e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800259ea  test    ebx, ebx
0x1800259ec  js      loc_180025B04
0x1800259f2  mov     [rbp+57h+var_80], 0
0x1800259f6  lea     r9, [rbp+57h+var_80]
0x1800259fa  mov     rcx, [rbp+57h+var_70]
0x1800259fe  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x180025a03  test    eax, eax
0x180025a05  js      loc_180025B42
0x180025a0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ARSFirewallLog@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ARSFirewallLog@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARSFirewallLog> `wil::Feature<__WilFeatureTraits_Feature_ARSFirewallLog>::GetImpl(void)'::`2'::impl
0x180025a12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ARSFirewallLog@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ARSFirewallLog>::__private_IsEnabled(void)
0x180025a17  mov     edi, 800705B4h
0x180025a1c  mov     bl, [rbp+57h+var_80]
0x180025a1f  test    al, al
0x180025a21  jz      short loc_180025A44
0x180025a23  test    bl, bl
0x180025a25  jz      short loc_180025A48
0x180025a27  call    ?LogFirewallServiceState@AppReadiness@@YAXXZ; AppReadiness::LogFirewallServiceState(void)
0x180025a2c  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 1
0x180025a33  jz      short loc_180025A44
0x180025a35  mov     r8d, edi
0x180025a38  lea     rdx, User_FWOpenPolicyStore_Stop
0x180025a3f  call    McTemplateU0d_EventWriteTransfer
0x180025a44  test    bl, bl
0x180025a46  jnz     short loc_180025A88
0x180025a48  lea     rcx, [rbp+57h+var_70]
0x180025a4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a51  nop
0x180025a52  mov     rcx, [rbp+57h+var_78]
0x180025a56  test    rcx, rcx
0x180025a59  jz      short loc_180025A70
0x180025a5b  mov     [rbp+57h+var_78], 0
0x180025a63  mov     rax, [rcx]
0x180025a66  mov     rax, [rax+10h]
0x180025a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a6f  nop
0x180025a70  mov     rcx, [rbp+57h+var_30]
0x180025a74  xor     rcx, rsp; StackCookie
0x180025a77  call    __security_check_cookie
0x180025a7c  add     rsp, 98h
0x180025a83  pop     rdi
0x180025a84  pop     rsi
0x180025a85  pop     rbx
0x180025a86  pop     rbp
0x180025a87  retn
0x180025a88  mov     [rsp+0B0h+var_88], 0A87h; int
0x180025a90  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180025a97  mov     [rsp+0B0h+var_90], rcx; char *
0x180025a9c  lea     r9, aAppreadinessUs_6; "AppReadiness::User::OpenFirewallPolicyS"...
0x180025aa3  lea     r8, aTimedout; "!timedOut"
0x180025aaa  mov     edx, edi; int
0x180025aac  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180025ab0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180025ab5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180025abc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025ac0  call    _CxxThrowException_0
0x180025ac6  mov     [rsp+0B0h+var_88], 0A76h; int
0x180025ace  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180025ad5  mov     [rsp+0B0h+var_90], rcx; char *
0x180025ada  lea     r9, aAppreadinessUs_6; "AppReadiness::User::OpenFirewallPolicyS"...
0x180025ae1  lea     r8, aWindowsFoundat_2; "Windows::Foundation::GetActivationFacto"...
0x180025ae8  mov     edx, eax; int
0x180025aea  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180025aee  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180025af3  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180025afa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025afe  call    _CxxThrowException_0
0x180025b04  mov     [rsp+0B0h+var_88], 0A79h; int
0x180025b0c  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180025b13  mov     [rsp+0B0h+var_90], rcx; char *
0x180025b18  lea     r9, aAppreadinessUs_6; "AppReadiness::User::OpenFirewallPolicyS"...
0x180025b1f  lea     r8, aThreadpoolRuna; "threadpool->RunAsync(Microsoft::WRL::Ca"...
0x180025b26  mov     edx, ebx; int
0x180025b28  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180025b2c  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180025b31  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180025b38  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025b3c  call    _CxxThrowException_0
0x180025b42  mov     [rsp+0B0h+var_88], 0A7Ch; int
0x180025b4a  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180025b51  mov     [rsp+0B0h+var_90], rcx; char *
0x180025b56  lea     r9, aAppreadinessUs_6; "AppReadiness::User::OpenFirewallPolicyS"...
0x180025b5d  lea     r8, aWilWaitForComp; "wil::wait_for_completion_or_timeout_not"...
0x180025b64  mov     edx, eax; int
0x180025b66  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180025b6a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180025b6f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180025b76  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180025b7a  call    _CxxThrowException_0
```
