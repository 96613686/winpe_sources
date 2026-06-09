# Windows::Management::Provisioning::ProvisioningMVUIStatus::GetMVUISelectionByIccid(HSTRING__ *,Windows::Management::Provisioning::IProvisioningMVUISelection * *)

- ea: `0x18006e780`
- end: `0x18006e97d`
- name: `?GetMVUISelectionByIccid@ProvisioningMVUIStatus@Provisioning@Management@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIProvisioningMVUISelection@234@@Z`
- size: `509`
- prototype: `int(Windows::Management::Provisioning::ProvisioningMVUIStatus *__hidden this, HSTRING, struct Windows::Management::Provisioning::IProvisioningMVUISelection **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x18000d79c`
- `0x18000eaf4`
- `0x180017318`
- `0x18006e1d0`
- `0x18006e780`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e89d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e89d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e7e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e7e8`

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
  __int64 *v18; // rax
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
  v18 = Microsoft::WRL::Details::Make<Windows::Management::Provisioning::ProvisioningMVUISelection,Microsoft::WRL::ComPtr<IMVUISelection> &>(
          &v25,
          (__int64)&v28);
  v19 = (struct Windows::Management::Provisioning::IProvisioningMVUISelection *)*v18;
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
0x18006e780  push    rbp
0x18006e782  push    rbx
0x18006e783  push    rsi
0x18006e784  push    rdi
0x18006e785  push    r14
0x18006e787  push    r15
0x18006e789  mov     rbp, rsp
0x18006e78c  sub     rsp, 58h
0x18006e790  mov     r14, r8
0x18006e793  mov     r15, rdx
0x18006e796  lea     rsi, [rcx+28h]
0x18006e79a  lea     rdx, [rcx+30h]
0x18006e79e  lea     rcx, [rbp+var_10]
0x18006e7a2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006e7a7  nop
0x18006e7a8  cmp     qword ptr [rsi], 0
0x18006e7ac  jnz     loc_18006E87D
0x18006e7b2  mov     [rbp+var_20], 0
0x18006e7ba  mov     [rbp+var_28], 0
0x18006e7c2  lea     rcx, [rbp+var_20]
0x18006e7c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e7cb  lea     rax, [rbp+var_20]
0x18006e7cf  mov     qword ptr [rsp+58h+ppv], rax; int
0x18006e7d4  lea     r9, _GUID_7b967ffd_bc01_4a23_aedd_055f4002710f; riid
0x18006e7db  xor     edx, edx; pUnkOuter
0x18006e7dd  lea     r8d, [rdx+1]; dwClsContext
0x18006e7e1  lea     rcx, _GUID_fb647f50_2192_49e0_a68f_5775434058c7; rclsid
0x18006e7e8  call    cs:__imp_CoCreateInstance
0x18006e7ee  mov     ebx, eax
0x18006e7f0  test    eax, eax
0x18006e7f2  jns     short loc_18006E7FB
0x18006e7f4  mov     edx, 79h ; 'y'
0x18006e7f9  jmp     short loc_18006E829
0x18006e7fb  mov     rdi, [rbp+var_20]
0x18006e7ff  mov     rax, [rdi]
0x18006e802  mov     rbx, [rax+48h]
0x18006e806  lea     rcx, [rbp+var_28]
0x18006e80a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e80f  lea     rdx, [rbp+var_28]
0x18006e813  mov     rcx, rdi
0x18006e816  mov     rax, rbx
0x18006e819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e81e  mov     ebx, eax
0x18006e820  test    eax, eax
0x18006e822  jns     short loc_18006E855
0x18006e824  mov     edx, 7Ah ; 'z'; void *
0x18006e829  mov     r9d, eax; char *
0x18006e82c  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e833  mov     rcx, [rbp+30h]; this
0x18006e837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e83c  nop
0x18006e83d  lea     rcx, [rbp+var_28]
0x18006e841  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e846  nop
0x18006e847  lea     rcx, [rbp+var_20]
0x18006e84b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e850  jmp     loc_18006E965
0x18006e855  mov     rdx, [rbp+var_28]
0x18006e859  mov     [rbp+var_28], 0
0x18006e861  mov     rcx, rsi
0x18006e864  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x18006e869  nop
0x18006e86a  lea     rcx, [rbp+var_28]
0x18006e86e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e873  nop
0x18006e874  lea     rcx, [rbp+var_20]
0x18006e878  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e87d  mov     [rbp+arg_18], 0
0x18006e885  mov     rdi, [rsi]
0x18006e888  mov     rax, [rdi]
0x18006e88b  mov     rbx, [rax+28h]
0x18006e88f  lea     rcx, [rbp+arg_18]
0x18006e893  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e898  xor     edx, edx; length
0x18006e89a  mov     rcx, r15; string
0x18006e89d  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e8a3  lea     r8, [rbp+arg_18]
0x18006e8a7  mov     rdx, rax
0x18006e8aa  mov     rcx, rdi
0x18006e8ad  mov     rax, rbx
0x18006e8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8b5  mov     ebx, eax
0x18006e8b7  test    eax, eax
0x18006e8b9  jns     short loc_18006E8E2
0x18006e8bb  mov     r9d, eax; char *
0x18006e8be  mov     edx, 80h; void *
0x18006e8c3  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18006e8ca  mov     rcx, [rbp+30h]; this
0x18006e8ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e8d3  nop
0x18006e8d4  lea     rcx, [rbp+arg_18]
0x18006e8d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e8dd  jmp     loc_18006E965
0x18006e8e2  cmp     [rbp+arg_18], 0
0x18006e8e7  jnz     short loc_18006E8F8
0x18006e8e9  mov     ebx, 80004003h
0x18006e8ee  mov     r9d, ebx
0x18006e8f1  mov     edx, 81h
0x18006e8f6  jmp     short loc_18006E8C3
0x18006e8f8  lea     rdx, [rbp+arg_18]
0x18006e8fc  lea     rcx, [rbp+var_18]
0x18006e900  call    ??$Make@VProvisioningMVUISelection@Provisioning@Management@Windows@@AEAV?$ComPtr@UIMVUISelection@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VProvisioningMVUISelection@Provisioning@Management@Windows@@@12@AEAV?$ComPtr@UIMVUISelection@@@12@@Z; Microsoft::WRL::Details::Make<Windows::Management::Provisioning::ProvisioningMVUISelection,Microsoft::WRL::ComPtr<IMVUISelection> &>(Microsoft::WRL::ComPtr<IMVUISelection> &)
0x18006e905  mov     rbx, [rax]
0x18006e908  mov     qword ptr [rax], 0
0x18006e90f  mov     rcx, [rbp+var_18]
0x18006e913  test    rcx, rcx
0x18006e916  jz      short loc_18006E92D
0x18006e918  mov     [rbp+var_18], 0
0x18006e920  mov     rax, [rcx]
0x18006e923  mov     rax, [rax+10h]
0x18006e927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e92c  nop
0x18006e92d  test    rbx, rbx
0x18006e930  jz      short loc_18006E942
0x18006e932  mov     rax, [rbx]
0x18006e935  mov     rcx, rbx
0x18006e938  mov     rax, [rax+8]
0x18006e93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e941  nop
0x18006e942  mov     [r14], rbx
0x18006e945  test    rbx, rbx
0x18006e948  jz      short loc_18006E95A
0x18006e94a  mov     rax, [rbx]
0x18006e94d  mov     rcx, rbx
0x18006e950  mov     rax, [rax+10h]
0x18006e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e959  nop
0x18006e95a  lea     rcx, [rbp+arg_18]
0x18006e95e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e963  xor     ebx, ebx
0x18006e965  lea     rcx, [rbp+var_10]
0x18006e969  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18006e96e  mov     eax, ebx
0x18006e970  add     rsp, 58h
0x18006e974  pop     r15
0x18006e976  pop     r14
0x18006e978  pop     rdi
0x18006e979  pop     rsi
0x18006e97a  pop     rbx
0x18006e97b  pop     rbp
0x18006e97c  retn
```
