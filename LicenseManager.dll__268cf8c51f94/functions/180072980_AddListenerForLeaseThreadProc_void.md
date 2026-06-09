# AddListenerForLeaseThreadProc(void *)

- ea: `0x180072980`
- end: `0x180072c4b`
- name: `?AddListenerForLeaseThreadProc@@YAKPEAX@Z`
- size: `715`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x18000ca28`
- `0x180017230`
- `0x18001dad0`
- `0x18002aae8`
- `0x1800593bc`
- `0x1800629dc`
- `0x180062a40`
- `0x18006cd80`
- `0x18006ef78`
- `0x180072980`
- `0x180072c54`
- `0x180075e60`
- `0x18008c96c`
- `0x18008dc00`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072aa8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180072aa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072ad1`

## string_xrefs

- `0x1800729f2`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180072a3f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180072a89`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180072b05`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AddListenerForLeaseThreadProc(_QWORD *Parameter)
{
  int v2; // eax
  __int64 v3; // rax
  int v4; // eax
  _WORD *v5; // rax
  int v6; // eax
  int v7; // eax
  __int64 *v8; // rsi
  __int64 (__fastcall *v9)(__int64 *, LPVOID *); // r14
  void *v10; // rbx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rbx
  const char *v14; // r9
  LPVOID pv; // [rsp+20h] [rbp-98h] BYREF
  int v17; // [rsp+28h] [rbp-90h] BYREF
  __int64 *v18; // [rsp+30h] [rbp-88h] BYREF
  __int64 v19; // [rsp+38h] [rbp-80h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD *v21; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v22[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v23; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v21 = Parameter;
  v18 = 0;
  v2 = Microsoft::WRL::ComPtr<ILicenseInstance>::As<ILicenseInstanceInternal>(Parameter, &v18);
  try
  {
    if ( v2 >= 0 )
    {
      pv = 0;
      v3 = *v18;
      pv = 0;
      v4 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v3 + 24))(v18, &pv);
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4AF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v4,
          (int)pv);
      v5 = pv;
      if ( !pv || !*(_WORD *)pv )
      {
        v17 = 0;
        v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*Parameter + 96LL))(*Parameter, &v17);
        if ( v6 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B4,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v6,
            (int)pv);
        if ( v17 >= 1 )
        {
          MakeCom<LicenseInstanceCallback,>(v20);
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*Parameter + 112LL))(*Parameter, v20[0]);
          if ( v7 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4BE,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              (const char *)(unsigned int)v7,
              (int)pv);
          WaitForSingleObject(*(HANDLE *)(v20[0] + 24LL), 0xEA60u);
          v8 = v18;
          v9 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v18 + 24);
          v10 = pv;
          if ( pv )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
            CoTaskMemFree(v10);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
          }
          pv = 0;
          v11 = v9(v8, &pv);
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4C0,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              (const char *)(unsigned int)v11,
              (int)pv);
          v12 = v20[0];
          if ( v20[0] )
          {
            v20[0] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
        v5 = pv;
      }
      v13 = PushNotificationListener;
      v19 = PushNotificationListener;
      if ( PushNotificationListener )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)PushNotificationListener + 8LL))(PushNotificationListener);
        v5 = pv;
      }
      if ( v5 && *v5 && v13 )
      {
        SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)v20);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
        v22[0] = 0;
        v22[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v22[0]) = 0;
        v23 = 0;
        std::wstring::assign(v22, pv);
        Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v23, Parameter + 2);
        (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v13 + 40LL))(v13, v22);
        ActiveLease::~ActiveLease((ActiveLease *)v22);
        SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)v20);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    std::unique_ptr<PackageLicense>::~unique_ptr<PackageLicense>(&v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4D7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180072980  push    rbx
0x180072982  push    rsi
0x180072983  push    rdi
0x180072984  push    r14
0x180072986  push    r15
0x180072988  sub     rsp, 90h
0x18007298f  mov     rax, cs:__security_cookie
0x180072996  xor     rax, rsp
0x180072999  mov     [rsp+0B8h+var_38], rax
0x1800729a1  mov     rdi, rcx
0x1800729a4  xor     r15d, r15d
0x1800729a7  mov     [rsp+0B8h+var_68], rcx
0x1800729ac  mov     [rsp+0B8h+var_88], r15
0x1800729b1  lea     rdx, [rsp+0B8h+var_88]
0x1800729b6  call    ??$As@UILicenseInstanceInternal@@@?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILicenseInstanceInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::As<ILicenseInstanceInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILicenseInstanceInternal>>)
0x1800729bb  test    eax, eax
0x1800729bd  js      loc_180072C12
0x1800729c3  mov     [rsp+0B8h+pv], r15
0x1800729c8  mov     rcx, [rsp+0B8h+var_88]
0x1800729cd  mov     rax, [rcx]
0x1800729d0  mov     [rsp+0B8h+pv], r15; int
0x1800729d5  lea     rdx, [rsp+0B8h+pv]
0x1800729da  mov     rax, [rax+18h]
0x1800729de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729e3  mov     rcx, [rsp+0B8h]; this
0x1800729eb  test    eax, eax
0x1800729ed  jns     short loc_180072A03
0x1800729ef  mov     r9d, eax; char *
0x1800729f2  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800729f9  mov     edx, 4AFh; void *
0x1800729fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072a03  mov     rax, [rsp+0B8h+pv]
0x180072a08  test    rax, rax
0x180072a0b  jz      short loc_180072A17
0x180072a0d  cmp     [rax], r15w
0x180072a11  jnz     loc_180072B38
0x180072a17  mov     [rsp+0B8h+var_90], r15d
0x180072a1c  mov     rcx, [rdi]
0x180072a1f  mov     rax, [rcx]
0x180072a22  lea     rdx, [rsp+0B8h+var_90]
0x180072a27  mov     rax, [rax+60h]
0x180072a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a30  mov     rcx, [rsp+0B8h]; this
0x180072a38  test    eax, eax
0x180072a3a  jns     short loc_180072A50
0x180072a3c  mov     r9d, eax; char *
0x180072a3f  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180072a46  mov     edx, 4B4h; void *
0x180072a4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072a50  cmp     [rsp+0B8h+var_90], 1
0x180072a55  jl      loc_180072B33
0x180072a5b  lea     rcx, [rsp+0B8h+var_78]
0x180072a60  call    ??$MakeCom@VLicenseInstanceCallback@@$$V@@YA?AV?$ComPtr@VLicenseInstanceCallback@@@WRL@Microsoft@@XZ; MakeCom<LicenseInstanceCallback,>(void)
0x180072a65  nop
0x180072a66  mov     rcx, [rdi]
0x180072a69  mov     rax, [rcx]
0x180072a6c  mov     rdx, [rsp+0B8h+var_78]
0x180072a71  mov     rax, [rax+70h]
0x180072a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a7a  mov     rcx, [rsp+0B8h]; this
0x180072a82  test    eax, eax
0x180072a84  jns     short loc_180072A9A
0x180072a86  mov     r9d, eax; char *
0x180072a89  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180072a90  mov     edx, 4BEh; void *
0x180072a95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072a9a  mov     edx, 0EA60h; dwMilliseconds
0x180072a9f  mov     rcx, [rsp+0B8h+var_78]
0x180072aa4  mov     rcx, [rcx+18h]; hHandle
0x180072aa8  call    cs:__imp_WaitForSingleObject
0x180072aae  mov     rsi, [rsp+0B8h+var_88]
0x180072ab3  mov     rax, [rsi]
0x180072ab6  mov     r14, [rax+18h]
0x180072aba  mov     rbx, [rsp+0B8h+pv]
0x180072abf  test    rbx, rbx
0x180072ac2  jz      short loc_180072AE1
0x180072ac4  lea     rcx, [rsp+0B8h+var_80]; this
0x180072ac9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180072ace  mov     rcx, rbx; pv
0x180072ad1  call    cs:__imp_CoTaskMemFree
0x180072ad7  lea     rcx, [rsp+0B8h+var_80]; this
0x180072adc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180072ae1  mov     [rsp+0B8h+pv], r15; int
0x180072ae6  lea     rdx, [rsp+0B8h+pv]
0x180072aeb  mov     rcx, rsi
0x180072aee  mov     rax, r14
0x180072af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072af6  mov     rcx, [rsp+0B8h]; this
0x180072afe  test    eax, eax
0x180072b00  jns     short loc_180072B17
0x180072b02  mov     r9d, eax; char *
0x180072b05  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180072b0c  mov     edx, 4C0h; void *
0x180072b11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072b17  mov     rcx, [rsp+0B8h+var_78]
0x180072b1c  test    rcx, rcx
0x180072b1f  jz      short loc_180072B33
0x180072b21  mov     [rsp+0B8h+var_78], r15
0x180072b26  mov     rax, [rcx]
0x180072b29  mov     rax, [rax+10h]
0x180072b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b32  nop
0x180072b33  mov     rax, [rsp+0B8h+pv]
0x180072b38  mov     rbx, cs:?PushNotificationListener@@3V?$ComPtr@UIWnsListener@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IWnsListener> PushNotificationListener
0x180072b3f  mov     [rsp+0B8h+var_80], rbx
0x180072b44  test    rbx, rbx
0x180072b47  jz      short loc_180072B5D
0x180072b49  mov     rax, [rbx]
0x180072b4c  mov     rcx, rbx
0x180072b4f  mov     rax, [rax+8]
0x180072b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b58  mov     rax, [rsp+0B8h+pv]
0x180072b5d  test    rax, rax
0x180072b60  jz      loc_180072BFC
0x180072b66  cmp     [rax], r15w
0x180072b6a  jz      loc_180072BFC
0x180072b70  test    rbx, rbx
0x180072b73  jz      loc_180072BFC
0x180072b79  lea     rcx, [rsp+0B8h+var_78]; this
0x180072b7e  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x180072b83  nop
0x180072b84  mov     rax, [rbx]
0x180072b87  mov     rcx, rbx
0x180072b8a  mov     rax, [rax+18h]
0x180072b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b93  xorps   xmm0, xmm0
0x180072b96  movups  [rsp+0B8h+var_60], xmm0
0x180072b9b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180072ba3  movdqu  [rsp+0B8h+var_50], xmm1
0x180072ba9  mov     word ptr [rsp+0B8h+var_60], r15w
0x180072baf  mov     [rsp+0B8h+var_40], r15
0x180072bb4  mov     rdx, [rsp+0B8h+pv]
0x180072bb9  lea     rcx, [rsp+0B8h+var_60]
0x180072bbe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180072bc3  lea     rdx, [rdi+10h]
0x180072bc7  lea     rcx, [rsp+0B8h+var_40]
0x180072bcc  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180072bd1  mov     rax, [rbx]
0x180072bd4  lea     rdx, [rsp+0B8h+var_60]
0x180072bd9  mov     rcx, rbx
0x180072bdc  mov     rax, [rax+28h]
0x180072be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072be5  nop
0x180072be6  lea     rcx, [rsp+0B8h+var_60]; this
0x180072beb  call    ??1ActiveLease@@QEAA@XZ; ActiveLease::~ActiveLease(void)
0x180072bf0  nop
0x180072bf1  lea     rcx, [rsp+0B8h+var_78]; this
0x180072bf6  call    ??1SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180072bfb  nop
0x180072bfc  lea     rcx, [rsp+0B8h+var_80]
0x180072c01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072c06  nop
0x180072c07  lea     rcx, [rsp+0B8h+pv]
0x180072c0c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180072c11  nop
0x180072c12  lea     rcx, [rsp+0B8h+var_88]
0x180072c17  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072c1c  nop
0x180072c1d  lea     rcx, [rsp+0B8h+var_68]
0x180072c22  call    ??1?$unique_ptr@UPackageLicense@@U?$default_delete@UPackageLicense@@@std@@@std@@QEAA@XZ; std::unique_ptr<PackageLicense>::~unique_ptr<PackageLicense>(void)
0x180072c27  nop
0x180072c28  jmp     short $+2
0x180072c2a  xor     eax, eax
0x180072c2c  mov     rcx, [rsp+0B8h+var_38]
0x180072c34  xor     rcx, rsp; StackCookie
0x180072c37  call    __security_check_cookie
0x180072c3c  add     rsp, 90h
0x180072c43  pop     r15
0x180072c45  pop     r14
0x180072c47  pop     rdi
0x180072c48  pop     rsi
0x180072c49  pop     rbx
0x180072c4a  retn
```
