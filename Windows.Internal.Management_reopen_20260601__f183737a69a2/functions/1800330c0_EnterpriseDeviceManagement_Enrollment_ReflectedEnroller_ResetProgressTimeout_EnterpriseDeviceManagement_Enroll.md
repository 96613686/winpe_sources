# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ResetProgressTimeout(EnterpriseDeviceManagement::Enrollment::MDMProgressMode)

- ea: `0x1800330c0`
- end: `0x1800332e8`
- name: `?ResetProgressTimeout@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJW4MDMProgressMode@23@@Z`
- size: `552`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x18001c920`
- `0x18002335c`
- `0x1800330c0`
- `0x18003a52c`
- `0x1800a1838`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1800330ea`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800330ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800332c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800332c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003312a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003312a`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003314d`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003314d`
- `dmenterprisediagnostics!StartAutoLog` at `0x18003329c`
- `dmenterprisediagnostics!StartAutoLog` at `0x18003329c`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ResetProgressTimeout(__int64 a1, int a2)
{
  int ActiveUserSid; // eax
  unsigned int v3; // ebx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, PCWSTR *); // rdi
  int v14; // eax
  __int64 v15; // rdx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v17; // r8
  PCWSTR pszMore; // [rsp+20h] [rbp-20h] BYREF
  HSTRING string; // [rsp+28h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v23; // [rsp+60h] [rbp+20h] BYREF
  __int64 v24; // [rsp+68h] [rbp+28h] BYREF

  string = 0;
  hMem[0] = 0;
  if ( !a2 )
  {
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, hMem);
LABEL_6:
    v23 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v6 = v5(DatabaseManagerInstance, 8289, &v23);
    v3 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v6,
        (int)pszMore);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      goto LABEL_21;
    }
    v7 = v23;
    v24 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    v9 = v8(v7, &v24);
    v3 = v9;
    if ( v9 >= 0 )
    {
      v12 = v24;
      if ( v24 )
      {
        pszMore = 0;
        v13 = *(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v24 + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pszMore,
          0);
        v14 = v13(v12, &pszMore);
        v3 = v14;
        if ( v14 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v14 = FirstSync::ResetTimeOut(pszMore, StringRawBuffer, v17);
          v3 = v14;
          if ( v14 >= 0 )
          {
            StartAutoLog(L"DeviceEnrollment");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
            v3 = 0;
            goto LABEL_21;
          }
          v15 = 1860;
        }
        else
        {
          v15 = 1859;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)v14,
          (int)pszMore);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
        goto LABEL_12;
      }
      v3 = -2147024809;
      v11 = 1857;
      v10 = 2147942487LL;
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 1855;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)v10,
      (int)pszMore);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    goto LABEL_8;
  }
  ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)hMem);
  v3 = ActiveUserSid;
  if ( ActiveUserSid >= 0 )
  {
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, hMem);
    LocalFree(hMem[0]);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x732,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
    (const char *)(unsigned int)ActiveUserSid,
    (int)pszMore);
LABEL_21:
  WindowsDeleteString(string);
  return v3;
}

```

## disassembly

```asm
0x1800330c0  mov     [rsp-8+arg_0], rbx
0x1800330c5  mov     [rsp-8+arg_8], rdi
0x1800330ca  push    rbp
0x1800330cb  mov     rbp, rsp
0x1800330ce  sub     rsp, 40h
0x1800330d2  mov     [rbp+string], 0
0x1800330da  mov     [rbp+hMem], 0
0x1800330e2  test    edx, edx
0x1800330e4  jz      short loc_180033138
0x1800330e6  lea     rcx, [rbp+hMem]
0x1800330ea  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800330f1  nop     dword ptr [rax+rax+00h]
0x1800330f6  mov     ebx, eax
0x1800330f8  test    eax, eax
0x1800330fa  jns     short loc_180033119
0x1800330fc  mov     rcx, [rbp+8]; this
0x180033100  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033107  mov     r9d, eax; char *
0x18003310a  mov     edx, 732h; void *
0x18003310f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033114  jmp     loc_1800332C5
0x180033119  lea     rdx, [rbp+hMem]
0x18003311d  lea     rcx, [rbp+string]
0x180033121  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180033126  mov     rcx, [rbp+hMem]; hMem
0x18003312a  call    cs:__imp_LocalFree
0x180033131  nop     dword ptr [rax+rax+00h]
0x180033136  jmp     short loc_180033145
0x180033138  lea     rdx, [rbp+hMem]
0x18003313c  lea     rcx, [rbp+string]
0x180033140  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180033145  mov     [rbp+arg_10], 0
0x18003314d  call    cs:__imp_GetDatabaseManagerInstance
0x180033154  nop     dword ptr [rax+rax+00h]
0x180033159  mov     rdi, rax
0x18003315c  mov     rcx, [rax]
0x18003315f  mov     rbx, [rcx+20h]
0x180033163  lea     rcx, [rbp+arg_10]
0x180033167  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003316c  lea     r8, [rbp+arg_10]
0x180033170  mov     edx, 2061h
0x180033175  mov     rcx, rdi
0x180033178  mov     rax, rbx
0x18003317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033180  mov     ebx, eax
0x180033182  test    eax, eax
0x180033184  jns     short loc_1800331AC
0x180033186  mov     rcx, [rbp+8]; this
0x18003318a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033191  mov     r9d, eax; char *
0x180033194  mov     edx, 73Ch; void *
0x180033199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003319e  lea     rcx, [rbp+arg_10]
0x1800331a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800331a7  jmp     loc_1800332C5
0x1800331ac  mov     rdi, [rbp+arg_10]
0x1800331b0  lea     rcx, [rbp+arg_18]
0x1800331b4  mov     [rbp+arg_18], 0
0x1800331bc  mov     rax, [rdi]
0x1800331bf  mov     rbx, [rax+18h]
0x1800331c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800331c8  lea     rdx, [rbp+arg_18]
0x1800331cc  mov     rcx, rdi
0x1800331cf  mov     rax, rbx
0x1800331d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331d7  mov     ebx, eax
0x1800331d9  test    eax, eax
0x1800331db  jns     short loc_180033200
0x1800331dd  mov     r9d, eax; char *
0x1800331e0  mov     edx, 73Fh; void *
0x1800331e5  mov     rcx, [rbp+8]; this
0x1800331e9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800331f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800331f5  lea     rcx, [rbp+arg_18]
0x1800331f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800331fe  jmp     short loc_18003319E
0x180033200  mov     rbx, [rbp+arg_18]
0x180033204  test    rbx, rbx
0x180033207  jnz     short loc_180033218
0x180033209  mov     ebx, 80070057h
0x18003320e  mov     edx, 741h
0x180033213  mov     r9d, ebx
0x180033216  jmp     short loc_1800331E5
0x180033218  mov     [rbp+pszMore], 0
0x180033220  lea     rcx, [rbp+pszMore]
0x180033224  mov     rax, [rbx]
0x180033227  xor     edx, edx
0x180033229  mov     rdi, [rax+20h]
0x18003322d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180033232  lea     rdx, [rbp+pszMore]
0x180033236  mov     rcx, rbx
0x180033239  mov     rax, rdi
0x18003323c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033241  mov     ebx, eax
0x180033243  test    eax, eax
0x180033245  jns     short loc_18003326A
0x180033247  mov     edx, 743h; void *
0x18003324c  mov     rcx, [rbp+8]; this
0x180033250  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033257  mov     r9d, eax; char *
0x18003325a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003325f  lea     rcx, [rbp+pszMore]
0x180033263  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180033268  jmp     short loc_1800331F5
0x18003326a  mov     rcx, [rbp+string]; string
0x18003326e  xor     edx, edx; length
0x180033270  call    cs:__imp_WindowsGetStringRawBuffer
0x180033277  nop     dword ptr [rax+rax+00h]
0x18003327c  mov     rcx, [rbp+pszMore]; pszMore
0x180033280  mov     rdx, rax; PCWSTR
0x180033283  call    ?ResetTimeOut@FirstSync@@YAJPEBG0@Z; FirstSync::ResetTimeOut(ushort const *,ushort const *)
0x180033288  mov     ebx, eax
0x18003328a  test    eax, eax
0x18003328c  jns     short loc_180033295
0x18003328e  mov     edx, 744h
0x180033293  jmp     short loc_18003324C
0x180033295  lea     rcx, aDeviceenrollme_0; "DeviceEnrollment"
0x18003329c  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x1800332a3  nop     dword ptr [rax+rax+00h]
0x1800332a8  lea     rcx, [rbp+pszMore]
0x1800332ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800332b1  lea     rcx, [rbp+arg_18]
0x1800332b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800332ba  lea     rcx, [rbp+arg_10]
0x1800332be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800332c3  xor     ebx, ebx
0x1800332c5  mov     rcx, [rbp+string]; string
0x1800332c9  call    cs:__imp_WindowsDeleteString
0x1800332d0  nop     dword ptr [rax+rax+00h]
0x1800332d5  mov     rdi, [rsp+40h+arg_8]
0x1800332da  mov     eax, ebx
0x1800332dc  mov     rbx, [rsp+40h+arg_0]
0x1800332e1  add     rsp, 40h
0x1800332e5  pop     rbp
0x1800332e6  retn
```
