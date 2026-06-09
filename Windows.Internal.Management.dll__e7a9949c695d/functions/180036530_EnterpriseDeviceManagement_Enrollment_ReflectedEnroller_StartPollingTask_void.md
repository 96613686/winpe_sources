# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::StartPollingTask(void)

- ea: `0x180036530`
- end: `0x1800366e0`
- name: `?StartPollingTask@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x18001e414`
- `0x180024cd0`
- `0x180036530`
- `0x18003b198`
- `0x1800a40ac`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180036547`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180036547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800366d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800366d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003669f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003669f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036589`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036589`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180036597`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180036597`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::StartPollingTask(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this)
{
  int ActiveUserSid; // eax
  unsigned int v2; // ebx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, FirstSync **); // rdi
  int v11; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v13; // r8
  unsigned int v14; // r9d
  HLOCAL hMem; // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v19; // [rsp+58h] [rbp+28h] BYREF
  FirstSync *v20; // [rsp+60h] [rbp+30h] BYREF
  __int64 v21; // [rsp+68h] [rbp+38h] BYREF

  hMem = 0;
  ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
  v2 = ActiveUserSid;
  if ( ActiveUserSid >= 0 )
  {
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &hMem);
    LocalFree(hMem);
    v21 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    v5 = v4(DatabaseManagerInstance, 8289, &v21);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v6 = v21;
      v19 = 0;
      v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      v8 = v7(v6, &v19);
      v2 = v8;
      if ( v8 >= 0 )
      {
        v9 = v19;
        if ( !v19 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          v2 = 1;
          goto LABEL_14;
        }
        v20 = 0;
        v10 = *(__int64 (__fastcall **)(__int64, FirstSync **))(*(_QWORD *)v19 + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v20,
          0);
        v11 = v10(v9, &v20);
        v2 = v11;
        if ( v11 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v2 = FirstSync::PerformBackgroundPoll(v20, StringRawBuffer, v13, v14);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5BF,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
            (const char *)(unsigned int)v11,
            (int)hMem);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5BA,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)v8,
          (int)hMem);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v5,
        (int)hMem);
    }
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    WindowsDeleteString(string);
    return v2;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B1,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
    (const char *)(unsigned int)ActiveUserSid,
    (int)hMem);
  return v2;
}

```

## disassembly

```asm
0x180036530  push    rbp
0x180036532  push    rbx
0x180036533  push    rdi
0x180036534  mov     rbp, rsp
0x180036537  sub     rsp, 30h
0x18003653b  lea     rcx, [rbp+hMem]
0x18003653f  mov     [rbp+hMem], 0
0x180036547  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003654d  mov     ebx, eax
0x18003654f  test    eax, eax
0x180036551  jns     short loc_180036570
0x180036553  mov     rcx, [rbp+18h]; this
0x180036557  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003655e  mov     r9d, eax; char *
0x180036561  mov     edx, 5B1h; void *
0x180036566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003656b  jmp     loc_1800366D6
0x180036570  lea     rdx, [rbp+hMem]
0x180036574  mov     [rbp+string], 0
0x18003657c  lea     rcx, [rbp+string]
0x180036580  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180036585  mov     rcx, [rbp+hMem]; hMem
0x180036589  call    cs:__imp_LocalFree
0x18003658f  mov     [rbp+arg_18], 0
0x180036597  call    cs:__imp_GetDatabaseManagerInstance
0x18003659d  mov     rdi, rax
0x1800365a0  mov     rcx, [rax]
0x1800365a3  mov     rbx, [rcx+20h]
0x1800365a7  lea     rcx, [rbp+arg_18]
0x1800365ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800365b0  lea     r8, [rbp+arg_18]
0x1800365b4  mov     edx, 2061h
0x1800365b9  mov     rcx, rdi
0x1800365bc  mov     rax, rbx
0x1800365bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365c4  mov     ebx, eax
0x1800365c6  test    eax, eax
0x1800365c8  jns     short loc_1800365E7
0x1800365ca  mov     rcx, [rbp+18h]; this
0x1800365ce  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800365d5  mov     r9d, eax; char *
0x1800365d8  mov     edx, 5B7h; void *
0x1800365dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800365e2  jmp     loc_1800366C3
0x1800365e7  mov     rdi, [rbp+arg_18]
0x1800365eb  lea     rcx, [rbp+arg_8]
0x1800365ef  mov     [rbp+arg_8], 0
0x1800365f7  mov     rax, [rdi]
0x1800365fa  mov     rbx, [rax+18h]
0x1800365fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036603  lea     rdx, [rbp+arg_8]
0x180036607  mov     rcx, rdi
0x18003660a  mov     rax, rbx
0x18003660d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036612  mov     ebx, eax
0x180036614  test    eax, eax
0x180036616  jns     short loc_18003663E
0x180036618  mov     rcx, [rbp+18h]; this
0x18003661c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180036623  mov     r9d, eax; char *
0x180036626  mov     edx, 5BAh; void *
0x18003662b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036630  lea     rcx, [rbp+arg_8]
0x180036634  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036639  jmp     loc_1800366C3
0x18003663e  mov     rbx, [rbp+arg_8]
0x180036642  test    rbx, rbx
0x180036645  jz      short loc_1800366B5
0x180036647  mov     [rbp+arg_10], 0
0x18003664f  lea     rcx, [rbp+arg_10]
0x180036653  mov     rax, [rbx]
0x180036656  xor     edx, edx
0x180036658  mov     rdi, [rax+20h]
0x18003665c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180036661  lea     rdx, [rbp+arg_10]
0x180036665  mov     rcx, rbx
0x180036668  mov     rax, rdi
0x18003666b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036670  mov     ebx, eax
0x180036672  test    eax, eax
0x180036674  jns     short loc_180036699
0x180036676  mov     rcx, [rbp+18h]; this
0x18003667a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180036681  mov     r9d, eax; char *
0x180036684  mov     edx, 5BFh; void *
0x180036689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003668e  lea     rcx, [rbp+arg_10]
0x180036692  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036697  jmp     short loc_180036630
0x180036699  mov     rcx, [rbp+string]; string
0x18003669d  xor     edx, edx; length
0x18003669f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800366a5  mov     rcx, [rbp+arg_10]; this
0x1800366a9  mov     rdx, rax; unsigned __int16 *
0x1800366ac  call    ?PerformBackgroundPoll@FirstSync@@YAJPEBG0K@Z; FirstSync::PerformBackgroundPoll(ushort const *,ushort const *,ulong)
0x1800366b1  mov     ebx, eax
0x1800366b3  jmp     short loc_18003668E
0x1800366b5  lea     rcx, [rbp+arg_8]
0x1800366b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800366be  mov     ebx, 1
0x1800366c3  lea     rcx, [rbp+arg_18]
0x1800366c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800366cc  mov     rcx, [rbp+string]; string
0x1800366d0  call    cs:__imp_WindowsDeleteString
0x1800366d6  mov     eax, ebx
0x1800366d8  add     rsp, 30h
0x1800366dc  pop     rdi
0x1800366dd  pop     rbx
0x1800366de  pop     rbp
0x1800366df  retn
```
