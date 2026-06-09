# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::UpdateServerWithResult(int,int)

- ea: `0x180037d50`
- end: `0x180037fa2`
- name: `?UpdateServerWithResult@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHH@Z`
- size: `594`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x18001c920`
- `0x18002335c`
- `0x18002eff0`
- `0x180037d50`
- `0x18003a52c`
- `0x1800a7230`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180037d77`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180037d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037f0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037f0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037da1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037da1`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180037df4`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180037df4`
- `dmenterprisediagnostics!StopAutoLog` at `0x180037f44`
- `dmenterprisediagnostics!StopAutoLog` at `0x180037f44`

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
0x180037d50  push    rbp
0x180037d52  push    rbx
0x180037d53  push    rsi
0x180037d54  push    rdi
0x180037d55  mov     rbp, rsp
0x180037d58  sub     rsp, 48h
0x180037d5c  mov     [rbp+string], 0
0x180037d64  mov     esi, edx
0x180037d66  mov     [rbp+hMem], 0
0x180037d6e  test    r8d, r8d
0x180037d71  jnz     short loc_180037DAF
0x180037d73  lea     rcx, [rbp+hMem]
0x180037d77  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180037d7e  nop     dword ptr [rax+rax+00h]
0x180037d83  mov     ebx, eax
0x180037d85  test    eax, eax
0x180037d87  jns     short loc_180037D90
0x180037d89  mov     edx, 519h
0x180037d8e  jmp     short loc_180037DD4
0x180037d90  lea     rdx, [rbp+hMem]
0x180037d94  lea     rcx, [rbp+string]
0x180037d98  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180037d9d  mov     rcx, [rbp+hMem]; hMem
0x180037da1  call    cs:__imp_LocalFree
0x180037da8  nop     dword ptr [rax+rax+00h]
0x180037dad  jmp     short loc_180037DBC
0x180037daf  lea     rdx, [rbp+hMem]
0x180037db3  lea     rcx, [rbp+string]
0x180037db7  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180037dbc  test    esi, esi
0x180037dbe  jz      short loc_180037DEC
0x180037dc0  mov     rcx, [rbp+string]
0x180037dc4  call    MarkEspComplete
0x180037dc9  mov     ebx, eax
0x180037dcb  test    eax, eax
0x180037dcd  jns     short loc_180037DEC
0x180037dcf  mov     edx, 525h; void *
0x180037dd4  mov     rcx, [rbp+20h]; this
0x180037dd8  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180037ddf  mov     r9d, eax; char *
0x180037de2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037de7  jmp     loc_180037F86
0x180037dec  mov     [rbp+arg_18], 0
0x180037df4  call    cs:__imp_GetDatabaseManagerInstance
0x180037dfb  nop     dword ptr [rax+rax+00h]
0x180037e00  mov     rdi, rax
0x180037e03  mov     rcx, [rax]
0x180037e06  mov     rbx, [rcx+20h]
0x180037e0a  lea     rcx, [rbp+arg_18]
0x180037e0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037e13  lea     r8, [rbp+arg_18]
0x180037e17  mov     edx, 2061h
0x180037e1c  mov     rcx, rdi
0x180037e1f  mov     rax, rbx
0x180037e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e27  mov     ebx, eax
0x180037e29  test    eax, eax
0x180037e2b  jns     short loc_180037E53
0x180037e2d  mov     rcx, [rbp+20h]; this
0x180037e31  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180037e38  mov     r9d, eax; char *
0x180037e3b  mov     edx, 529h; void *
0x180037e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e45  lea     rcx, [rbp+arg_18]
0x180037e49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037e4e  jmp     loc_180037F86
0x180037e53  mov     rdi, [rbp+arg_18]
0x180037e57  lea     rcx, [rbp+var_28]
0x180037e5b  mov     [rbp+var_28], 0
0x180037e63  mov     rax, [rdi]
0x180037e66  mov     rbx, [rax+18h]
0x180037e6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037e6f  lea     rdx, [rbp+var_28]
0x180037e73  mov     rcx, rdi
0x180037e76  mov     rax, rbx
0x180037e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e7e  mov     ebx, eax
0x180037e80  test    eax, eax
0x180037e82  jns     short loc_180037EA7
0x180037e84  mov     rcx, [rbp+20h]; this
0x180037e88  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180037e8f  mov     r9d, eax; char *
0x180037e92  mov     edx, 52Ch; void *
0x180037e97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e9c  lea     rcx, [rbp+var_28]
0x180037ea0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037ea5  jmp     short loc_180037E45
0x180037ea7  mov     rbx, [rbp+var_28]
0x180037eab  test    rbx, rbx
0x180037eae  jz      loc_180037F6F
0x180037eb4  mov     [rbp+var_20], 0
0x180037ebc  lea     rcx, [rbp+var_20]
0x180037ec0  mov     rax, [rbx]
0x180037ec3  xor     edx, edx
0x180037ec5  mov     rdi, [rax+20h]
0x180037ec9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037ece  lea     rdx, [rbp+var_20]
0x180037ed2  mov     rcx, rbx
0x180037ed5  mov     rax, rdi
0x180037ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037edd  mov     ebx, eax
0x180037edf  test    eax, eax
0x180037ee1  jns     short loc_180037F06
0x180037ee3  mov     edx, 531h; void *
0x180037ee8  mov     rcx, [rbp+20h]; this
0x180037eec  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180037ef3  mov     r9d, eax; char *
0x180037ef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037efb  lea     rcx, [rbp+var_20]
0x180037eff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037f04  jmp     short loc_180037E9C
0x180037f06  mov     rcx, [rbp+string]; string
0x180037f0a  xor     edx, edx; length
0x180037f0c  call    cs:__imp_WindowsGetStringRawBuffer
0x180037f13  nop     dword ptr [rax+rax+00h]
0x180037f18  mov     rcx, [rbp+var_20]
0x180037f1c  xor     r8d, r8d
0x180037f1f  test    esi, esi
0x180037f21  mov     rdx, rax
0x180037f24  setnz   r8b
0x180037f28  xor     r9d, r9d
0x180037f2b  call    ?MarkProvisioningComplete@FirstSync@@YAJPEBG0W4ProvisioningStatus@1@H@Z; FirstSync::MarkProvisioningComplete(ushort const *,ushort const *,FirstSync::ProvisioningStatus,int)
0x180037f30  mov     ebx, eax
0x180037f32  test    eax, eax
0x180037f34  jns     short loc_180037F3D
0x180037f36  mov     edx, 533h
0x180037f3b  jmp     short loc_180037EE8
0x180037f3d  lea     rcx, aDeviceenrollme_0; "DeviceEnrollment"
0x180037f44  call    cs:__imp_?StopAutoLog@@YAJPEBG@Z; StopAutoLog(ushort const *)
0x180037f4b  nop     dword ptr [rax+rax+00h]
0x180037f50  lea     rcx, [rbp+var_20]
0x180037f54  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037f59  lea     rcx, [rbp+var_28]
0x180037f5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f62  lea     rcx, [rbp+arg_18]
0x180037f66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f6b  xor     ebx, ebx
0x180037f6d  jmp     short loc_180037F86
0x180037f6f  lea     rcx, [rbp+var_28]
0x180037f73  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f78  lea     rcx, [rbp+arg_18]
0x180037f7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180037f81  mov     ebx, 1
0x180037f86  mov     rcx, [rbp+string]; string
0x180037f8a  call    cs:__imp_WindowsDeleteString
0x180037f91  nop     dword ptr [rax+rax+00h]
0x180037f96  mov     eax, ebx
0x180037f98  add     rsp, 48h
0x180037f9c  pop     rdi
0x180037f9d  pop     rsi
0x180037f9e  pop     rbx
0x180037f9f  pop     rbp
0x180037fa0  retn
```
