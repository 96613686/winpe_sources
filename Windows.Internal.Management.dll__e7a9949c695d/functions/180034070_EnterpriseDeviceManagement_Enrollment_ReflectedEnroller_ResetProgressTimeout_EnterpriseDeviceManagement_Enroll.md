# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ResetProgressTimeout(EnterpriseDeviceManagement::Enrollment::MDMProgressMode)

- ea: `0x180034070`
- end: `0x180034273`
- name: `?ResetProgressTimeout@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJW4MDMProgressMode@23@@Z`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x18001e414`
- `0x180024cd0`
- `0x180034070`
- `0x18003b198`
- `0x18009e840`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x18003409a`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18003409a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003425b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003425b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003420e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003420e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800340d4`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800340f1`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800340f1`
- `dmenterprisediagnostics!StartAutoLog` at `0x180034234`
- `dmenterprisediagnostics!StartAutoLog` at `0x180034234`

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
0x180034070  mov     [rsp-8+arg_0], rbx
0x180034075  mov     [rsp-8+arg_8], rdi
0x18003407a  push    rbp
0x18003407b  mov     rbp, rsp
0x18003407e  sub     rsp, 40h
0x180034082  mov     [rbp+string], 0
0x18003408a  mov     [rbp+hMem], 0
0x180034092  test    edx, edx
0x180034094  jz      short loc_1800340DC
0x180034096  lea     rcx, [rbp+hMem]
0x18003409a  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800340a0  mov     ebx, eax
0x1800340a2  test    eax, eax
0x1800340a4  jns     short loc_1800340C3
0x1800340a6  mov     rcx, [rbp+8]; this
0x1800340aa  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800340b1  mov     r9d, eax; char *
0x1800340b4  mov     edx, 732h; void *
0x1800340b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800340be  jmp     loc_180034257
0x1800340c3  lea     rdx, [rbp+hMem]
0x1800340c7  lea     rcx, [rbp+string]
0x1800340cb  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800340d0  mov     rcx, [rbp+hMem]; hMem
0x1800340d4  call    cs:__imp_LocalFree
0x1800340da  jmp     short loc_1800340E9
0x1800340dc  lea     rdx, [rbp+hMem]
0x1800340e0  lea     rcx, [rbp+string]
0x1800340e4  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800340e9  mov     [rbp+arg_10], 0
0x1800340f1  call    cs:__imp_GetDatabaseManagerInstance
0x1800340f7  mov     rdi, rax
0x1800340fa  mov     rcx, [rax]
0x1800340fd  mov     rbx, [rcx+20h]
0x180034101  lea     rcx, [rbp+arg_10]
0x180034105  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003410a  lea     r8, [rbp+arg_10]
0x18003410e  mov     edx, 2061h
0x180034113  mov     rcx, rdi
0x180034116  mov     rax, rbx
0x180034119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003411e  mov     ebx, eax
0x180034120  test    eax, eax
0x180034122  jns     short loc_18003414A
0x180034124  mov     rcx, [rbp+8]; this
0x180034128  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003412f  mov     r9d, eax; char *
0x180034132  mov     edx, 73Ch; void *
0x180034137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003413c  lea     rcx, [rbp+arg_10]
0x180034140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034145  jmp     loc_180034257
0x18003414a  mov     rdi, [rbp+arg_10]
0x18003414e  lea     rcx, [rbp+arg_18]
0x180034152  mov     [rbp+arg_18], 0
0x18003415a  mov     rax, [rdi]
0x18003415d  mov     rbx, [rax+18h]
0x180034161  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034166  lea     rdx, [rbp+arg_18]
0x18003416a  mov     rcx, rdi
0x18003416d  mov     rax, rbx
0x180034170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034175  mov     ebx, eax
0x180034177  test    eax, eax
0x180034179  jns     short loc_18003419E
0x18003417b  mov     r9d, eax; char *
0x18003417e  mov     edx, 73Fh; void *
0x180034183  mov     rcx, [rbp+8]; this
0x180034187  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003418e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034193  lea     rcx, [rbp+arg_18]
0x180034197  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003419c  jmp     short loc_18003413C
0x18003419e  mov     rbx, [rbp+arg_18]
0x1800341a2  test    rbx, rbx
0x1800341a5  jnz     short loc_1800341B6
0x1800341a7  mov     ebx, 80070057h
0x1800341ac  mov     edx, 741h
0x1800341b1  mov     r9d, ebx
0x1800341b4  jmp     short loc_180034183
0x1800341b6  mov     [rbp+pszMore], 0
0x1800341be  lea     rcx, [rbp+pszMore]
0x1800341c2  mov     rax, [rbx]
0x1800341c5  xor     edx, edx
0x1800341c7  mov     rdi, [rax+20h]
0x1800341cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800341d0  lea     rdx, [rbp+pszMore]
0x1800341d4  mov     rcx, rbx
0x1800341d7  mov     rax, rdi
0x1800341da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341df  mov     ebx, eax
0x1800341e1  test    eax, eax
0x1800341e3  jns     short loc_180034208
0x1800341e5  mov     edx, 743h; void *
0x1800341ea  mov     rcx, [rbp+8]; this
0x1800341ee  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800341f5  mov     r9d, eax; char *
0x1800341f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341fd  lea     rcx, [rbp+pszMore]
0x180034201  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034206  jmp     short loc_180034193
0x180034208  mov     rcx, [rbp+string]; string
0x18003420c  xor     edx, edx; length
0x18003420e  call    cs:__imp_WindowsGetStringRawBuffer
0x180034214  mov     rcx, [rbp+pszMore]; pszMore
0x180034218  mov     rdx, rax; PCWSTR
0x18003421b  call    ?ResetTimeOut@FirstSync@@YAJPEBG0@Z; FirstSync::ResetTimeOut(ushort const *,ushort const *)
0x180034220  mov     ebx, eax
0x180034222  test    eax, eax
0x180034224  jns     short loc_18003422D
0x180034226  mov     edx, 744h
0x18003422b  jmp     short loc_1800341EA
0x18003422d  lea     rcx, aDeviceenrollme_0; "DeviceEnrollment"
0x180034234  call    cs:__imp_?StartAutoLog@@YAJPEBG@Z; StartAutoLog(ushort const *)
0x18003423a  lea     rcx, [rbp+pszMore]
0x18003423e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034243  lea     rcx, [rbp+arg_18]
0x180034247  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003424c  lea     rcx, [rbp+arg_10]
0x180034250  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034255  xor     ebx, ebx
0x180034257  mov     rcx, [rbp+string]; string
0x18003425b  call    cs:__imp_WindowsDeleteString
0x180034261  mov     rdi, [rsp+40h+arg_8]
0x180034266  mov     eax, ebx
0x180034268  mov     rbx, [rsp+40h+arg_0]
0x18003426d  add     rsp, 40h
0x180034271  pop     rbp
0x180034272  retn
```
