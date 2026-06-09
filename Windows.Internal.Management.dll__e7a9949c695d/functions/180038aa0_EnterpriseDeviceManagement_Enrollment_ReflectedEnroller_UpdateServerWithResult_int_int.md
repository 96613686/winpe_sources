# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::UpdateServerWithResult(int,int)

- ea: `0x180038aa0`
- end: `0x180038ccd`
- name: `?UpdateServerWithResult@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHH@Z`
- size: `557`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x18001e414`
- `0x180024cd0`
- `0x180030378`
- `0x180038aa0`
- `0x18003b198`
- `0x1800a3ef4`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180038ac7`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180038ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038c4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038aeb`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180038b38`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180038b38`
- `dmenterprisediagnostics!StopAutoLog` at `0x180038c7c`
- `dmenterprisediagnostics!StopAutoLog` at `0x180038c7c`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::UpdateServerWithResult(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        int a2,
        int a3)
{
  int ActiveUserSid; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // [rsp+20h] [rbp-28h] BYREF
  __int64 v20; // [rsp+28h] [rbp-20h] BYREF
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v24; // [rsp+88h] [rbp+40h] BYREF

  string = 0;
  hMem[0] = 0;
  if ( a3 )
  {
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, hMem);
  }
  else
  {
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)hMem);
    v5 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v6 = 1305;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v19);
      goto LABEL_24;
    }
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, hMem);
    LocalFree(hMem[0]);
  }
  if ( a2 )
  {
    ActiveUserSid = MarkEspComplete(string);
    v5 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      v6 = 1317;
      goto LABEL_9;
    }
  }
  v24 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v9 = v8(DatabaseManagerInstance, 8289, &v24);
  v5 = v9;
  if ( v9 >= 0 )
  {
    v10 = v24;
    v19 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    v12 = v11(v10, &v19);
    v5 = v12;
    if ( v12 >= 0 )
    {
      v13 = v19;
      if ( !v19 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
        v5 = 1;
        goto LABEL_24;
      }
      v20 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v20,
        0);
      v15 = v14(v13, &v20);
      v5 = v15;
      if ( v15 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v15 = FirstSync::MarkProvisioningComplete(v20, StringRawBuffer, a2 != 0, 0);
        v5 = v15;
        if ( v15 >= 0 )
        {
          StopAutoLog(L"DeviceEnrollment");
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
          v5 = 0;
          goto LABEL_24;
        }
        v16 = 1331;
      }
      else
      {
        v16 = 1329;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v15,
        v19);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v12,
        v19);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x529,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v9,
      v19);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
LABEL_24:
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x180038aa0  push    rbp
0x180038aa2  push    rbx
0x180038aa3  push    rsi
0x180038aa4  push    rdi
0x180038aa5  mov     rbp, rsp
0x180038aa8  sub     rsp, 48h
0x180038aac  mov     [rbp+string], 0
0x180038ab4  mov     esi, edx
0x180038ab6  mov     [rbp+hMem], 0
0x180038abe  test    r8d, r8d
0x180038ac1  jnz     short loc_180038AF3
0x180038ac3  lea     rcx, [rbp+hMem]
0x180038ac7  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180038acd  mov     ebx, eax
0x180038acf  test    eax, eax
0x180038ad1  jns     short loc_180038ADA
0x180038ad3  mov     edx, 519h
0x180038ad8  jmp     short loc_180038B18
0x180038ada  lea     rdx, [rbp+hMem]
0x180038ade  lea     rcx, [rbp+string]
0x180038ae2  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180038ae7  mov     rcx, [rbp+hMem]; hMem
0x180038aeb  call    cs:__imp_LocalFree
0x180038af1  jmp     short loc_180038B00
0x180038af3  lea     rdx, [rbp+hMem]
0x180038af7  lea     rcx, [rbp+string]
0x180038afb  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180038b00  test    esi, esi
0x180038b02  jz      short loc_180038B30
0x180038b04  mov     rcx, [rbp+string]
0x180038b08  call    MarkEspComplete
0x180038b0d  mov     ebx, eax
0x180038b0f  test    eax, eax
0x180038b11  jns     short loc_180038B30
0x180038b13  mov     edx, 525h; void *
0x180038b18  mov     rcx, [rbp+20h]; this
0x180038b1c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038b23  mov     r9d, eax; char *
0x180038b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b2b  jmp     loc_180038CB8
0x180038b30  mov     [rbp+arg_18], 0
0x180038b38  call    cs:__imp_GetDatabaseManagerInstance
0x180038b3e  mov     rdi, rax
0x180038b41  mov     rcx, [rax]
0x180038b44  mov     rbx, [rcx+20h]
0x180038b48  lea     rcx, [rbp+arg_18]
0x180038b4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038b51  lea     r8, [rbp+arg_18]
0x180038b55  mov     edx, 2061h
0x180038b5a  mov     rcx, rdi
0x180038b5d  mov     rax, rbx
0x180038b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b65  mov     ebx, eax
0x180038b67  test    eax, eax
0x180038b69  jns     short loc_180038B91
0x180038b6b  mov     rcx, [rbp+20h]; this
0x180038b6f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038b76  mov     r9d, eax; char *
0x180038b79  mov     edx, 529h; void *
0x180038b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b83  lea     rcx, [rbp+arg_18]
0x180038b87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038b8c  jmp     loc_180038CB8
0x180038b91  mov     rdi, [rbp+arg_18]
0x180038b95  lea     rcx, [rbp+var_28]
0x180038b99  mov     [rbp+var_28], 0
0x180038ba1  mov     rax, [rdi]
0x180038ba4  mov     rbx, [rax+18h]
0x180038ba8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038bad  lea     rdx, [rbp+var_28]
0x180038bb1  mov     rcx, rdi
0x180038bb4  mov     rax, rbx
0x180038bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bbc  mov     ebx, eax
0x180038bbe  test    eax, eax
0x180038bc0  jns     short loc_180038BE5
0x180038bc2  mov     rcx, [rbp+20h]; this
0x180038bc6  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038bcd  mov     r9d, eax; char *
0x180038bd0  mov     edx, 52Ch; void *
0x180038bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038bda  lea     rcx, [rbp+var_28]
0x180038bde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038be3  jmp     short loc_180038B83
0x180038be5  mov     rbx, [rbp+var_28]
0x180038be9  test    rbx, rbx
0x180038bec  jz      loc_180038CA1
0x180038bf2  mov     [rbp+var_20], 0
0x180038bfa  lea     rcx, [rbp+var_20]
0x180038bfe  mov     rax, [rbx]
0x180038c01  xor     edx, edx
0x180038c03  mov     rdi, [rax+20h]
0x180038c07  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180038c0c  lea     rdx, [rbp+var_20]
0x180038c10  mov     rcx, rbx
0x180038c13  mov     rax, rdi
0x180038c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c1b  mov     ebx, eax
0x180038c1d  test    eax, eax
0x180038c1f  jns     short loc_180038C44
0x180038c21  mov     edx, 531h; void *
0x180038c26  mov     rcx, [rbp+20h]; this
0x180038c2a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038c31  mov     r9d, eax; char *
0x180038c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c39  lea     rcx, [rbp+var_20]
0x180038c3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180038c42  jmp     short loc_180038BDA
0x180038c44  mov     rcx, [rbp+string]; string
0x180038c48  xor     edx, edx; length
0x180038c4a  call    cs:__imp_WindowsGetStringRawBuffer
0x180038c50  mov     rcx, [rbp+var_20]
0x180038c54  xor     r8d, r8d
0x180038c57  test    esi, esi
0x180038c59  mov     rdx, rax
0x180038c5c  setnz   r8b
0x180038c60  xor     r9d, r9d
0x180038c63  call    ?MarkProvisioningComplete@FirstSync@@YAJPEBG0W4ProvisioningStatus@1@H@Z; FirstSync::MarkProvisioningComplete(ushort const *,ushort const *,FirstSync::ProvisioningStatus,int)
0x180038c68  mov     ebx, eax
0x180038c6a  test    eax, eax
0x180038c6c  jns     short loc_180038C75
0x180038c6e  mov     edx, 533h
0x180038c73  jmp     short loc_180038C26
0x180038c75  lea     rcx, aDeviceenrollme_0; "DeviceEnrollment"
0x180038c7c  call    cs:__imp_?StopAutoLog@@YAJPEBG@Z; StopAutoLog(ushort const *)
0x180038c82  lea     rcx, [rbp+var_20]
0x180038c86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180038c8b  lea     rcx, [rbp+var_28]
0x180038c8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038c94  lea     rcx, [rbp+arg_18]
0x180038c98  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038c9d  xor     ebx, ebx
0x180038c9f  jmp     short loc_180038CB8
0x180038ca1  lea     rcx, [rbp+var_28]
0x180038ca5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038caa  lea     rcx, [rbp+arg_18]
0x180038cae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038cb3  mov     ebx, 1
0x180038cb8  mov     rcx, [rbp+string]; string
0x180038cbc  call    cs:__imp_WindowsDeleteString
0x180038cc2  mov     eax, ebx
0x180038cc4  add     rsp, 48h
0x180038cc8  pop     rdi
0x180038cc9  pop     rsi
0x180038cca  pop     rbx
0x180038ccb  pop     rbp
0x180038ccc  retn
```
