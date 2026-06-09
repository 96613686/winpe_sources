# Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Impl::BaseTaskExecutor,Windows::System::Threading::IWorkItemHandler,AppReadiness::Impl::BaseTask *>(Windows::System::Threading::IWorkItemHandler * *,AppReadiness::Impl::BaseTask * &&)

- ea: `0x180002654`
- end: `0x1800028a6`
- name: `??$MakeAndInitialize@VBaseTaskExecutor@Impl@AppReadiness@@UIWorkItemHandler@Threading@System@Windows@@PEAVBaseTask@23@@Details@WRL@Microsoft@@YAJPEAPEAUIWorkItemHandler@Threading@System@Windows@@$$QEAPEAVBaseTask@Impl@AppReadiness@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800024c4`

## callees

- `0x180002654`
- `0x1800028ac`
- `0x180002958`
- `0x180033ff8`
- `0x18003e210`
- `0x180040338`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002884`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002764`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002764`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002781`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002781`

## string_xrefs

- `0x18000275d`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Impl::BaseTaskExecutor,Windows::System::Threading::IWorkItemHandler,AppReadiness::Impl::BaseTask *>(
        _QWORD *a1,
        __int64 *a2)
{
  char *v4; // rax
  char *v5; // rsi
  _QWORD *v6; // rbx
  __int64 v7; // r14
  __int64 v8; // rcx
  HRESULT v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  *a1 = 0;
  v4 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v18[0] = v4;
  if ( !v4 )
  {
    LODWORD(v6) = -2147024882;
LABEL_21:
    Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(v18);
    return (unsigned int)v6;
  }
  v6 = v4 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 8));
  *((_DWORD *)v5 + 11) = 1;
  *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::System::Threading::IWorkItemHandler'};
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = &AppReadiness::Impl::BaseTaskExecutor::`vftable'{for `Windows::System::Threading::IWorkItemHandler'};
  *v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)v5 + 6) = 0;
  v18[1] = v5;
  v18[0] = 0;
  v7 = *a2;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v8 = *((_QWORD *)v5 + 6);
  *((_QWORD *)v5 + 6) = v7;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v17 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.System.Threading.ThreadPool", 0x23u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    RaiseException(v9, 1u, 0, 0);
LABEL_20:
    (*(void (__fastcall **)(char *))(v11 + 16))(v5);
    goto LABEL_21;
  }
  LODWORD(v6) = RoGetActivationFactory(string, &GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91, &v17);
  if ( (int)v6 >= 0 )
  {
    v16 = 0;
    v13 = v17;
    v6 = *(_QWORD **)(*(_QWORD *)v17 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 96LL))(v7);
    LODWORD(v6) = ((__int64 (__fastcall *)(__int64, char *, _QWORD, __int64 *))v6)(
                    v13,
                    v5,
                    (unsigned int)(v14 >= 4) - 1,
                    &v16);
    v15 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v10 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *(_QWORD *)v5;
  if ( (int)v6 < 0 )
    goto LABEL_20;
  LODWORD(v6) = (*(__int64 (__fastcall **)(char *, GUID *, _QWORD *))v11)(
                  v5,
                  &GUID_1d1a8b8b_fa66_414f_9cbd_b65fc99d17fa,
                  a1);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002654  mov     [rsp-28h+arg_10], rbx
0x180002659  push    rbp
0x18000265a  push    rsi
0x18000265b  push    rdi
0x18000265c  push    r14
0x18000265e  push    r15
0x180002660  mov     rbp, rsp
0x180002663  sub     rsp, 80h
0x18000266a  mov     rax, cs:__security_cookie
0x180002671  xor     rax, rsp
0x180002674  mov     [rbp+var_10], rax
0x180002678  mov     r14, rdx
0x18000267b  mov     r15, rcx
0x18000267e  mov     qword ptr [rcx], 0
0x180002685  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000268c  mov     ecx, 38h ; '8'; unsigned __int64
0x180002691  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002696  mov     rsi, rax
0x180002699  mov     [rbp+var_40], rax
0x18000269d  test    rax, rax
0x1800026a0  jz      loc_180002871
0x1800026a6  lea     rbx, [rax+8]
0x1800026aa  mov     rcx, rbx; this
0x1800026ad  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800026b2  mov     dword ptr [rsi+2Ch], 1
0x1800026b9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWorkItemHandler@Threading@System@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIWorkItemHandler@Threading@System@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::System::Threading::IWorkItemHandler'}
0x1800026c0  mov     [rsi], rax
0x1800026c3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWorkItemHandler@Threading@System@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800026ca  mov     [rbx], rax
0x1800026cd  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800026d4  test    rcx, rcx
0x1800026d7  jz      short loc_1800026E6
0x1800026d9  mov     rax, [rcx]
0x1800026dc  mov     rax, [rax+8]
0x1800026e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e5  nop
0x1800026e6  lea     rax, ??_7BaseTaskExecutor@Impl@AppReadiness@@6BIWorkItemHandler@Threading@System@Windows@@@; const AppReadiness::Impl::BaseTaskExecutor::`vftable'{for `Windows::System::Threading::IWorkItemHandler'}
0x1800026ed  mov     [rsi], rax
0x1800026f0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWorkItemHandler@Threading@System@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::Threading::IWorkItemHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800026f7  mov     [rbx], rax
0x1800026fa  mov     qword ptr [rsi+30h], 0
0x180002702  mov     [rbp+var_38], rsi
0x180002706  mov     [rbp+var_40], 0
0x18000270e  mov     r14, [r14]
0x180002711  test    r14, r14
0x180002714  jz      short loc_180002726
0x180002716  mov     rax, [r14]
0x180002719  mov     rcx, r14
0x18000271c  mov     rax, [rax+8]
0x180002720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002725  nop
0x180002726  mov     rcx, [rsi+30h]
0x18000272a  mov     [rsi+30h], r14
0x18000272e  test    rcx, rcx
0x180002731  jz      short loc_180002740
0x180002733  mov     rax, [rcx]
0x180002736  mov     rax, [rax+10h]
0x18000273a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273f  nop
0x180002740  mov     [rbp+var_48], 0
0x180002748  mov     [rbp+string], 0
0x180002750  lea     r9, [rbp+string]; string
0x180002754  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180002758  mov     edx, 23h ; '#'; length
0x18000275d  lea     rcx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x180002764  call    cs:__imp_WindowsCreateStringReference
0x18000276a  test    eax, eax
0x18000276c  js      loc_180002878
0x180002772  lea     r8, [rbp+var_48]
0x180002776  lea     rdx, _GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91
0x18000277d  mov     rcx, [rbp+string]
0x180002781  call    cs:__imp_RoGetActivationFactory
0x180002787  mov     ebx, eax
0x180002789  test    eax, eax
0x18000278b  jns     short loc_180002802
0x18000278d  mov     rcx, [rbp+var_48]
0x180002791  test    rcx, rcx
0x180002794  jz      short loc_1800027AB
0x180002796  mov     [rbp+var_48], 0
0x18000279e  mov     rax, [rcx]
0x1800027a1  mov     rax, [rax+10h]
0x1800027a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027aa  nop
0x1800027ab  mov     rax, [rsi]
0x1800027ae  test    ebx, ebx
0x1800027b0  js      loc_18000288B
0x1800027b6  mov     r8, r15
0x1800027b9  lea     rdx, _GUID_1d1a8b8b_fa66_414f_9cbd_b65fc99d17fa
0x1800027c0  mov     rcx, rsi
0x1800027c3  mov     rax, [rax]
0x1800027c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027cb  mov     ebx, eax
0x1800027cd  mov     rcx, [rsi]
0x1800027d0  mov     rax, [rcx+10h]
0x1800027d4  mov     rcx, rsi
0x1800027d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027dc  nop
0x1800027dd  mov     eax, ebx
0x1800027df  mov     rcx, [rbp+var_10]
0x1800027e3  xor     rcx, rsp; StackCookie
0x1800027e6  call    __security_check_cookie
0x1800027eb  mov     rbx, [rsp+80h+arg_10]
0x1800027f3  add     rsp, 80h
0x1800027fa  pop     r15
0x1800027fc  pop     r14
0x1800027fe  pop     rdi
0x1800027ff  pop     rsi
0x180002800  pop     rbp
0x180002801  retn
0x180002802  mov     [rbp+var_50], 0
0x18000280a  mov     rdi, [rbp+var_48]
0x18000280e  mov     rax, [rdi]
0x180002811  mov     rbx, [rax+38h]
0x180002815  lea     rcx, [rbp+var_50]
0x180002819  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000281e  mov     rax, [r14]
0x180002821  mov     rcx, r14
0x180002824  mov     rax, [rax+60h]
0x180002828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282d  xor     r8d, r8d
0x180002830  cmp     eax, 4
0x180002833  setnl   r8b
0x180002837  dec     r8d
0x18000283a  lea     r9, [rbp+var_50]
0x18000283e  mov     rdx, rsi
0x180002841  mov     rcx, rdi
0x180002844  mov     rax, rbx
0x180002847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284c  mov     ebx, eax
0x18000284e  mov     rcx, [rbp+var_50]
0x180002852  test    rcx, rcx
0x180002855  jz      short loc_18000286C
0x180002857  mov     [rbp+var_50], 0
0x18000285f  mov     rax, [rcx]
0x180002862  mov     rax, [rax+10h]
0x180002866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286b  nop
0x18000286c  jmp     loc_18000278D
0x180002871  mov     ebx, 8007000Eh
0x180002876  jmp     short loc_180002898
0x180002878  xor     r9d, r9d; lpArguments
0x18000287b  xor     r8d, r8d; nNumberOfArguments
0x18000287e  lea     edx, [r9+1]; dwExceptionFlags
0x180002882  mov     ecx, eax; dwExceptionCode
0x180002884  call    cs:__imp_RaiseException
0x18000288a  nop
0x18000288b  mov     rcx, rsi
0x18000288e  mov     rax, [rax+10h]
0x180002892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002897  nop
0x180002898  lea     rcx, [rbp+var_40]
0x18000289c  call    ??1?$MakeAllocator@VResolveStoreCategories@Tasks@AppReadiness@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(void)
0x1800028a1  jmp     loc_1800027DD
```
