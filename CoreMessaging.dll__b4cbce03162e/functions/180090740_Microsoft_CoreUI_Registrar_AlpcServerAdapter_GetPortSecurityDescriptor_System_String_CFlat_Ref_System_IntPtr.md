# Microsoft::CoreUI::Registrar::AlpcServerAdapter::GetPortSecurityDescriptor(System::String *,CFlat::Ref<System::IntPtr>)

- ea: `0x180090740`
- end: `0x18009088a`
- name: `?GetPortSecurityDescriptor@AlpcServerAdapter@Registrar@CoreUI@Microsoft@@SAXPEAVString@System@@U?$Ref@UIntPtr@System@@@CFlat@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(struct System::String *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a4634`

## callees

- `0x180007d80`
- `0x180027214`
- `0x18002e654`
- `0x180030c30`
- `0x18003950c`
- `0x180090740`
- `0x180090890`
- `0x1800b24c0`
- `0x1800b24e0`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18009078a`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18009078a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800907db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800907db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180090841`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180090841`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::Registrar::AlpcServerAdapter::GetPortSecurityDescriptor(
        struct System::String *a1,
        PSECURITY_DESCRIPTOR *a2)
{
  _QWORD *v3; // rax
  int v4; // edi
  int v5; // edi
  _QWORD *v6; // rax
  const WCHAR *v7; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  _BYTE v12[8]; // [rsp+48h] [rbp-8h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+70h] [rbp+20h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF

  v10 = 0;
  SecurityDescriptor = 0;
  v3 = (_QWORD *)Cn::ToUnicode::ToUnicode((Cn::ToUnicode *)&v11, a1);
  v4 = QueryTransientObjectSecurityDescriptor(8, (*v3 + 32LL) & -(__int64)(*v3 != 0), &SecurityDescriptor);
  CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(&v11);
  v5 = v4 | 0x10000000;
  if ( v5 < 0 )
    CFlat::Abandonment::FailWithHR(v5, 0, 0);
  StringSecurityDescriptorLen = 0;
  StringSecurityDescriptor = 0;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
          SecurityDescriptor,
          1u,
          4u,
          &StringSecurityDescriptor,
          &StringSecurityDescriptorLen)
    || !StringSecurityDescriptor
    || !StringSecurityDescriptorLen
    || ((v6 = (_QWORD *)System::String::Create$(v12),
         System::String::Concat(&v11, *v6, &off_1800DB630),
         CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(v12),
         v11)
      ? (v7 = (const WCHAR *)(v11 + 32))
      : (v7 = 0),
        !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &v10, 0) || !v10) )
  {
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
  }
  *a2 = v10;
  CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<enum Microsoft::CoreUI::Registrar::RegistrarClientId>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&StringSecurityDescriptor);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
}

```

## disassembly

```asm
0x180090740  mov     [rsp-8+arg_0], rbx
0x180090745  mov     [rsp-8+arg_8], rdi
0x18009074a  push    rbp
0x18009074b  mov     rbp, rsp
0x18009074e  sub     rsp, 50h
0x180090752  mov     rbx, rdx
0x180090755  mov     [rbp+var_18], 0
0x18009075d  mov     [rbp+SecurityDescriptor], 0
0x180090765  mov     rdx, rcx; struct System::String *
0x180090768  lea     rcx, [rbp+var_10]; this
0x18009076c  call    ??0ToUnicode@Cn@@QEAA@PEAVString@System@@@Z; Cn::ToUnicode::ToUnicode(System::String *)
0x180090771  mov     rcx, [rax]
0x180090774  lea     rax, [rcx+20h]
0x180090778  neg     rcx
0x18009077b  sbb     rdx, rdx
0x18009077e  and     rdx, rax
0x180090781  lea     r8, [rbp+SecurityDescriptor]
0x180090785  mov     ecx, 8
0x18009078a  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180090790  mov     edi, eax
0x180090792  lea     rcx, [rbp+var_10]; void *
0x180090796  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x18009079b  or      edi, 10000000h
0x1800907a1  jns     short loc_1800907B0
0x1800907a3  xor     r8d, r8d; int
0x1800907a6  xor     edx, edx; void *
0x1800907a8  mov     ecx, edi; int
0x1800907aa  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800907b0  mov     [rbp+arg_10], 0
0x1800907b7  mov     [rbp+StringSecurityDescriptor], 0
0x1800907bf  lea     rax, [rbp+arg_10]
0x1800907c3  mov     [rsp+50h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x1800907c8  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800907cc  mov     edi, 1
0x1800907d1  lea     r8d, [rdi+3]; SecurityInformation
0x1800907d5  mov     edx, edi; RequestedStringSDRevision
0x1800907d7  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800907db  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800907e1  test    eax, eax
0x1800907e3  jz      loc_180090884
0x1800907e9  mov     rdx, [rbp+StringSecurityDescriptor]
0x1800907ed  test    rdx, rdx
0x1800907f0  jz      loc_180090884
0x1800907f6  cmp     [rbp+arg_10], 0
0x1800907fa  jz      loc_180090884
0x180090800  lea     rcx, [rbp+var_8]
0x180090804  call    ?Create$@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEA_W@Z; System::String::Create$(wchar_t *)
0x180090809  nop
0x18009080a  lea     r8, off_1800DB630
0x180090811  mov     rdx, [rax]
0x180090814  lea     rcx, [rbp+var_10]
0x180090818  call    ?Concat@String@System@@SA?AV?$SmartPtr@VString@System@@@CFlat@@PEAV12@0@Z; System::String::Concat(System::String *,System::String *)
0x18009081d  nop
0x18009081e  lea     rcx, [rbp+var_8]; void *
0x180090822  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x180090827  mov     rax, [rbp+var_10]
0x18009082b  test    rax, rax
0x18009082e  jnz     short loc_180090834
0x180090830  xor     ecx, ecx
0x180090832  jmp     short loc_180090838
0x180090834  lea     rcx, [rax+20h]; StringSecurityDescriptor
0x180090838  xor     r9d, r9d; SecurityDescriptorSize
0x18009083b  lea     r8, [rbp+var_18]; SecurityDescriptor
0x18009083f  mov     edx, edi; StringSDRevision
0x180090841  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180090847  test    eax, eax
0x180090849  jz      short loc_180090884
0x18009084b  mov     rax, [rbp+var_18]
0x18009084f  test    rax, rax
0x180090852  jz      short loc_180090884
0x180090854  mov     [rbx], rax
0x180090857  lea     rcx, [rbp+var_10]; void *
0x18009085b  call    ??1?$SmartPtr@V?$EqualityComparer$1@W4RegistrarClientId@Registrar@CoreUI@Microsoft@@@Generic@Collections@System@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>::~SmartPtr<System::Collections::Generic::EqualityComparer$1<Microsoft::CoreUI::Registrar::RegistrarClientId>>(void)
0x180090860  nop
0x180090861  lea     rcx, [rbp+StringSecurityDescriptor]
0x180090865  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18009086a  nop
0x18009086b  lea     rcx, [rbp+SecurityDescriptor]
0x18009086f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180090874  mov     rbx, [rsp+50h+arg_0]
0x180090879  mov     rdi, [rsp+50h+arg_8]
0x18009087e  add     rsp, 50h
0x180090882  pop     rbp
0x180090883  retn
0x180090884  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
```
