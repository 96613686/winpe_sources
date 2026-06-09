# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::StartPollingTask(void)

- ea: `0x180035810`
- end: `0x1800359df`
- name: `?StartPollingTask@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x18001c920`
- `0x18002335c`
- `0x180035810`
- `0x18003a52c`
- `0x1800a73f8`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180035827`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180035827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003586f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003586f`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180035883`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180035883`

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
0x180035810  push    rbp
0x180035812  push    rbx
0x180035813  push    rdi
0x180035814  mov     rbp, rsp
0x180035817  sub     rsp, 30h
0x18003581b  lea     rcx, [rbp+hMem]
0x18003581f  mov     [rbp+hMem], 0
0x180035827  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003582e  nop     dword ptr [rax+rax+00h]
0x180035833  mov     ebx, eax
0x180035835  test    eax, eax
0x180035837  jns     short loc_180035856
0x180035839  mov     rcx, [rbp+18h]; this
0x18003583d  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180035844  mov     r9d, eax; char *
0x180035847  mov     edx, 5B1h; void *
0x18003584c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035851  jmp     loc_1800359D4
0x180035856  lea     rdx, [rbp+hMem]
0x18003585a  mov     [rbp+string], 0
0x180035862  lea     rcx, [rbp+string]
0x180035866  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18003586b  mov     rcx, [rbp+hMem]; hMem
0x18003586f  call    cs:__imp_LocalFree
0x180035876  nop     dword ptr [rax+rax+00h]
0x18003587b  mov     [rbp+arg_18], 0
0x180035883  call    cs:__imp_GetDatabaseManagerInstance
0x18003588a  nop     dword ptr [rax+rax+00h]
0x18003588f  mov     rdi, rax
0x180035892  mov     rcx, [rax]
0x180035895  mov     rbx, [rcx+20h]
0x180035899  lea     rcx, [rbp+arg_18]
0x18003589d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800358a2  lea     r8, [rbp+arg_18]
0x1800358a6  mov     edx, 2061h
0x1800358ab  mov     rcx, rdi
0x1800358ae  mov     rax, rbx
0x1800358b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358b6  mov     ebx, eax
0x1800358b8  test    eax, eax
0x1800358ba  jns     short loc_1800358D9
0x1800358bc  mov     rcx, [rbp+18h]; this
0x1800358c0  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800358c7  mov     r9d, eax; char *
0x1800358ca  mov     edx, 5B7h; void *
0x1800358cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358d4  jmp     loc_1800359BB
0x1800358d9  mov     rdi, [rbp+arg_18]
0x1800358dd  lea     rcx, [rbp+arg_8]
0x1800358e1  mov     [rbp+arg_8], 0
0x1800358e9  mov     rax, [rdi]
0x1800358ec  mov     rbx, [rax+18h]
0x1800358f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800358f5  lea     rdx, [rbp+arg_8]
0x1800358f9  mov     rcx, rdi
0x1800358fc  mov     rax, rbx
0x1800358ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035904  mov     ebx, eax
0x180035906  test    eax, eax
0x180035908  jns     short loc_180035930
0x18003590a  mov     rcx, [rbp+18h]; this
0x18003590e  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180035915  mov     r9d, eax; char *
0x180035918  mov     edx, 5BAh; void *
0x18003591d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035922  lea     rcx, [rbp+arg_8]
0x180035926  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003592b  jmp     loc_1800359BB
0x180035930  mov     rbx, [rbp+arg_8]
0x180035934  test    rbx, rbx
0x180035937  jz      short loc_1800359AD
0x180035939  mov     [rbp+arg_10], 0
0x180035941  lea     rcx, [rbp+arg_10]
0x180035945  mov     rax, [rbx]
0x180035948  xor     edx, edx
0x18003594a  mov     rdi, [rax+20h]
0x18003594e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035953  lea     rdx, [rbp+arg_10]
0x180035957  mov     rcx, rbx
0x18003595a  mov     rax, rdi
0x18003595d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035962  mov     ebx, eax
0x180035964  test    eax, eax
0x180035966  jns     short loc_18003598B
0x180035968  mov     rcx, [rbp+18h]; this
0x18003596c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180035973  mov     r9d, eax; char *
0x180035976  mov     edx, 5BFh; void *
0x18003597b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035980  lea     rcx, [rbp+arg_10]
0x180035984  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035989  jmp     short loc_180035922
0x18003598b  mov     rcx, [rbp+string]; string
0x18003598f  xor     edx, edx; length
0x180035991  call    cs:__imp_WindowsGetStringRawBuffer
0x180035998  nop     dword ptr [rax+rax+00h]
0x18003599d  mov     rcx, [rbp+arg_10]; this
0x1800359a1  mov     rdx, rax; unsigned __int16 *
0x1800359a4  call    ?PerformBackgroundPoll@FirstSync@@YAJPEBG0K@Z; FirstSync::PerformBackgroundPoll(ushort const *,ushort const *,ulong)
0x1800359a9  mov     ebx, eax
0x1800359ab  jmp     short loc_180035980
0x1800359ad  lea     rcx, [rbp+arg_8]
0x1800359b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800359b6  mov     ebx, 1
0x1800359bb  lea     rcx, [rbp+arg_18]
0x1800359bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800359c4  mov     rcx, [rbp+string]; string
0x1800359c8  call    cs:__imp_WindowsDeleteString
0x1800359cf  nop     dword ptr [rax+rax+00h]
0x1800359d4  mov     eax, ebx
0x1800359d6  add     rsp, 30h
0x1800359da  pop     rdi
0x1800359db  pop     rbx
0x1800359dc  pop     rbp
0x1800359dd  retn
```
