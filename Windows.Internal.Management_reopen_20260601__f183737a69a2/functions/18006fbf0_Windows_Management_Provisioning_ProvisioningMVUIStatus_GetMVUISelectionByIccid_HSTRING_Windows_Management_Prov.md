# Windows::Management::Provisioning::ProvisioningMVUIStatus::GetMVUISelectionByIccid(HSTRING__ *,Windows::Management::Provisioning::IProvisioningMVUISelection * *)

- ea: `0x18006fbf0`
- end: `0x18006fdfa`
- name: `?GetMVUISelectionByIccid@ProvisioningMVUIStatus@Provisioning@Management@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIProvisioningMVUISelection@234@@Z`
- size: `522`
- prototype: `int(Windows::Management::Provisioning::ProvisioningMVUIStatus *__hidden this, HSTRING, struct Windows::Management::Provisioning::IProvisioningMVUISelection **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x18000dc98`
- `0x18000f088`
- `0x180017b1c`
- `0x18006f620`
- `0x18006fbf0`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fd13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006fd13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fc58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fc58`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Management::Provisioning::ProvisioningMVUIStatus::GetMVUISelectionByIccid(
        Windows::Management::Provisioning::ProvisioningMVUIStatus *this,
        HSTRING a2,
        struct Windows::Management::Provisioning::IProvisioningMVUISelection **a3)
{
  char *v5; // rsi
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rbx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, PCWSTR, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  struct Windows::Management::Provisioning::IProvisioningMVUISelection **v18; // rax
  struct Windows::Management::Provisioning::IProvisioningMVUISelection *v19; // rbx
  __int64 v20; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  __int64 v23; // [rsp+30h] [rbp-28h] BYREF
  LPVOID v24; // [rsp+38h] [rbp-20h] BYREF
  __int64 v25; // [rsp+40h] [rbp-18h] BYREF
  _BYTE v26[16]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  __int64 v28; // [rsp+A8h] [rbp+50h] BYREF

  v5 = (char *)this + 40;
  wil::EnterCriticalSection(v26, (char *)this + 48);
  if ( !*(_QWORD *)v5 )
  {
    v24 = 0;
    v23 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    v6 = CoCreateInstance(
           &GUID_fb647f50_2192_49e0_a68f_5775434058c7,
           0,
           1u,
           &GUID_7b967ffd_bc01_4a23_aedd_055f4002710f,
           &v24);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 121;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
        (const char *)(unsigned int)v6,
        ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      goto LABEL_20;
    }
    v9 = v24;
    v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v24 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v6 = v10(v9, &v23);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 122;
      goto LABEL_6;
    }
    v11 = v23;
    v23 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::operator=(v5, v11);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  }
  v28 = 0;
  v12 = *(_QWORD *)v5;
  v13 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64 *))(**(_QWORD **)v5 + 40LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v15 = v13(v12, StringRawBuffer, &v28);
  v7 = v15;
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
    v17 = 128;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\provisioningmvuistatus.cpp",
      (const char *)v16,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    goto LABEL_20;
  }
  if ( !v28 )
  {
    v7 = -2147467261;
    v16 = 2147500035LL;
    v17 = 129;
    goto LABEL_10;
  }
  v18 = (struct Windows::Management::Provisioning::IProvisioningMVUISelection **)Microsoft::WRL::Details::Make<Windows::Management::Provisioning::ProvisioningMVUISelection,Microsoft::WRL::ComPtr<IMVUISelection> &>(
                                                                                   &v25,
                                                                                   &v28);
  v19 = *v18;
  *v18 = 0;
  v20 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v19 )
    (*(void (__fastcall **)(struct Windows::Management::Provisioning::IProvisioningMVUISelection *))(*(_QWORD *)v19 + 8LL))(v19);
  *a3 = v19;
  if ( v19 )
    (*(void (__fastcall **)(struct Windows::Management::Provisioning::IProvisioningMVUISelection *))(*(_QWORD *)v19 + 16LL))(v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v7 = 0;
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v26);
  return v7;
}

```

## disassembly

```asm
0x18006fbf0  push    rbp
0x18006fbf2  push    rbx
0x18006fbf3  push    rsi
0x18006fbf4  push    rdi
0x18006fbf5  push    r14
0x18006fbf7  push    r15
0x18006fbf9  mov     rbp, rsp
0x18006fbfc  sub     rsp, 58h
0x18006fc00  mov     r14, r8
0x18006fc03  mov     r15, rdx
0x18006fc06  lea     rsi, [rcx+28h]
0x18006fc0a  lea     rdx, [rcx+30h]
0x18006fc0e  lea     rcx, [rbp+var_10]
0x18006fc12  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006fc17  nop
0x18006fc18  cmp     qword ptr [rsi], 0
0x18006fc1c  jnz     loc_18006FCF3
0x18006fc22  mov     [rbp+var_20], 0
0x18006fc2a  mov     [rbp+var_28], 0
0x18006fc32  lea     rcx, [rbp+var_20]
0x18006fc36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fc3b  lea     rax, [rbp+var_20]
0x18006fc3f  mov     qword ptr [rsp+58h+ppv], rax; int
0x18006fc44  lea     r9, _GUID_7b967ffd_bc01_4a23_aedd_055f4002710f; riid
0x18006fc4b  xor     edx, edx; pUnkOuter
0x18006fc4d  lea     r8d, [rdx+1]; dwClsContext
0x18006fc51  lea     rcx, _GUID_fb647f50_2192_49e0_a68f_5775434058c7; rclsid
0x18006fc58  call    cs:__imp_CoCreateInstance
0x18006fc5f  nop     dword ptr [rax+rax+00h]
0x18006fc64  mov     ebx, eax
0x18006fc66  test    eax, eax
0x18006fc68  jns     short loc_18006FC71
0x18006fc6a  mov     edx, 79h ; 'y'
0x18006fc6f  jmp     short loc_18006FC9F
0x18006fc71  mov     rdi, [rbp+var_20]
0x18006fc75  mov     rax, [rdi]
0x18006fc78  mov     rbx, [rax+48h]
0x18006fc7c  lea     rcx, [rbp+var_28]
0x18006fc80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fc85  lea     rdx, [rbp+var_28]
0x18006fc89  mov     rcx, rdi
0x18006fc8c  mov     rax, rbx
0x18006fc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc94  mov     ebx, eax
0x18006fc96  test    eax, eax
0x18006fc98  jns     short loc_18006FCCB
0x18006fc9a  mov     edx, 7Ah ; 'z'; void *
0x18006fc9f  mov     r9d, eax; char *
0x18006fca2  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006fca9  mov     rcx, [rbp+30h]; this
0x18006fcad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fcb2  nop
0x18006fcb3  lea     rcx, [rbp+var_28]
0x18006fcb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fcbc  nop
0x18006fcbd  lea     rcx, [rbp+var_20]
0x18006fcc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fcc6  jmp     loc_18006FDE1
0x18006fccb  mov     rdx, [rbp+var_28]
0x18006fccf  mov     [rbp+var_28], 0
0x18006fcd7  mov     rcx, rsi
0x18006fcda  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x18006fcdf  nop
0x18006fce0  lea     rcx, [rbp+var_28]
0x18006fce4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fce9  nop
0x18006fcea  lea     rcx, [rbp+var_20]
0x18006fcee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fcf3  mov     [rbp+arg_18], 0
0x18006fcfb  mov     rdi, [rsi]
0x18006fcfe  mov     rax, [rdi]
0x18006fd01  mov     rbx, [rax+28h]
0x18006fd05  lea     rcx, [rbp+arg_18]
0x18006fd09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fd0e  xor     edx, edx; length
0x18006fd10  mov     rcx, r15; string
0x18006fd13  call    cs:__imp_WindowsGetStringRawBuffer
0x18006fd1a  nop     dword ptr [rax+rax+00h]
0x18006fd1f  lea     r8, [rbp+arg_18]
0x18006fd23  mov     rdx, rax
0x18006fd26  mov     rcx, rdi
0x18006fd29  mov     rax, rbx
0x18006fd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd31  mov     ebx, eax
0x18006fd33  test    eax, eax
0x18006fd35  jns     short loc_18006FD5E
0x18006fd37  mov     r9d, eax; char *
0x18006fd3a  mov     edx, 80h; void *
0x18006fd3f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006fd46  mov     rcx, [rbp+30h]; this
0x18006fd4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fd4f  nop
0x18006fd50  lea     rcx, [rbp+arg_18]
0x18006fd54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fd59  jmp     loc_18006FDE1
0x18006fd5e  cmp     [rbp+arg_18], 0
0x18006fd63  jnz     short loc_18006FD74
0x18006fd65  mov     ebx, 80004003h
0x18006fd6a  mov     r9d, ebx
0x18006fd6d  mov     edx, 81h
0x18006fd72  jmp     short loc_18006FD3F
0x18006fd74  lea     rdx, [rbp+arg_18]
0x18006fd78  lea     rcx, [rbp+var_18]
0x18006fd7c  call    ??$Make@VProvisioningMVUISelection@Provisioning@Management@Windows@@AEAV?$ComPtr@UIMVUISelection@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VProvisioningMVUISelection@Provisioning@Management@Windows@@@12@AEAV?$ComPtr@UIMVUISelection@@@12@@Z; Microsoft::WRL::Details::Make<Windows::Management::Provisioning::ProvisioningMVUISelection,Microsoft::WRL::ComPtr<IMVUISelection> &>(Microsoft::WRL::ComPtr<IMVUISelection> &)
0x18006fd81  mov     rbx, [rax]
0x18006fd84  mov     qword ptr [rax], 0
0x18006fd8b  mov     rcx, [rbp+var_18]
0x18006fd8f  test    rcx, rcx
0x18006fd92  jz      short loc_18006FDA9
0x18006fd94  mov     [rbp+var_18], 0
0x18006fd9c  mov     rax, [rcx]
0x18006fd9f  mov     rax, [rax+10h]
0x18006fda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fda8  nop
0x18006fda9  test    rbx, rbx
0x18006fdac  jz      short loc_18006FDBE
0x18006fdae  mov     rax, [rbx]
0x18006fdb1  mov     rcx, rbx
0x18006fdb4  mov     rax, [rax+8]
0x18006fdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fdbd  nop
0x18006fdbe  mov     [r14], rbx
0x18006fdc1  test    rbx, rbx
0x18006fdc4  jz      short loc_18006FDD6
0x18006fdc6  mov     rax, [rbx]
0x18006fdc9  mov     rcx, rbx
0x18006fdcc  mov     rax, [rax+10h]
0x18006fdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fdd5  nop
0x18006fdd6  lea     rcx, [rbp+arg_18]
0x18006fdda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006fddf  xor     ebx, ebx
0x18006fde1  lea     rcx, [rbp+var_10]
0x18006fde5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18006fdea  mov     eax, ebx
0x18006fdec  add     rsp, 58h
0x18006fdf0  pop     r15
0x18006fdf2  pop     r14
0x18006fdf4  pop     rdi
0x18006fdf5  pop     rsi
0x18006fdf6  pop     rbx
0x18006fdf7  pop     rbp
0x18006fdf8  retn
```
