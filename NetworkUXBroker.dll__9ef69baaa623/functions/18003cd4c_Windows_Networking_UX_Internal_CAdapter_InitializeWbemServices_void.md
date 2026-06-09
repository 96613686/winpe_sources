# Windows::Networking::UX::Internal::CAdapter::InitializeWbemServices(void)

- ea: `0x18003cd4c`
- end: `0x18003cec4`
- name: `?InitializeWbemServices@CAdapter@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003d95c`

## callees

- `0x18000955c`
- `0x18000e768`
- `0x180021ed0`
- `0x180035dc0`
- `0x18003cd4c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ce6d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ce6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003cd83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003cd83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::CAdapter::InitializeWbemServices(
        Windows::Networking::UX::Internal::CAdapter *this)
{
  LPVOID *v2; // rdi
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64, _QWORD, _QWORD); // rbx
  IUnknown **v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  HRESULT v12; // eax
  unsigned int v13; // ebx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v2 = (LPVOID *)((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, v2);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    try
    {
      wil::make_bstr();
      v6 = *v2;
      v7 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 24LL);
      v8 = (IUnknown **)((char *)this + 88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v8);
      v9 = v7(v6, v17, 0, 0);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v12 = CoSetProxyBlanket(*v8, 0xAu, 0, 0, 3u, 3u, 0, 0);
        v13 = v12;
        if ( v12 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
            (const char *)(unsigned int)v12,
            ppva);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
          result = v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
          (const char *)(unsigned int)v9,
          0);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        result = v10;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xC5,
                             (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
                             v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapter.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18003cd4c  mov     [rsp+arg_8], rbx
0x18003cd51  mov     [rsp+arg_10], rsi
0x18003cd56  push    rdi
0x18003cd57  sub     rsp, 50h
0x18003cd5b  mov     rsi, rcx
0x18003cd5e  lea     rdi, [rcx+50h]
0x18003cd62  mov     rcx, rdi
0x18003cd65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cd6a  mov     [rsp+58h+ppv], rdi; int
0x18003cd6f  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18003cd76  xor     edx, edx; pUnkOuter
0x18003cd78  lea     r8d, [rdx+1]; dwClsContext
0x18003cd7c  lea     rcx, CLSID_WbemLocator; rclsid
0x18003cd83  call    cs:__imp_CoCreateInstance
0x18003cd89  mov     ebx, eax
0x18003cd8b  test    eax, eax
0x18003cd8d  jns     short loc_18003CDAF
0x18003cd8f  mov     rcx, [rsp+58h]; this
0x18003cd94  mov     r9d, eax; char *
0x18003cd97  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003cd9e  mov     edx, 0A4h; void *
0x18003cda3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cda8  mov     eax, ebx
0x18003cdaa  jmp     loc_18003CEB3
0x18003cdaf  lea     rdx, aRootStandardci; "root\\StandardCimv2"
0x18003cdb6  lea     rcx, [rsp+58h+arg_0]
0x18003cdbb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18003cdc0  nop
0x18003cdc1  mov     rdi, [rdi]
0x18003cdc4  mov     rax, [rdi]
0x18003cdc7  mov     rbx, [rax+18h]
0x18003cdcb  add     rsi, 58h ; 'X'
0x18003cdcf  mov     rcx, rsi
0x18003cdd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003cdd7  mov     [rsp+58h+var_18], rsi
0x18003cddc  mov     qword ptr [rsp+58h+dwCapabilities], 0
0x18003cde5  mov     [rsp+58h+pAuthInfo], 0
0x18003cdee  mov     [rsp+58h+dwImpLevel], 0
0x18003cdf6  mov     [rsp+58h+ppv], 0; int
0x18003cdff  xor     r9d, r9d
0x18003ce02  xor     r8d, r8d
0x18003ce05  mov     rdx, [rsp+58h+arg_0]
0x18003ce0a  mov     rcx, rdi
0x18003ce0d  mov     rax, rbx
0x18003ce10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce15  mov     ebx, eax
0x18003ce17  test    eax, eax
0x18003ce19  jns     short loc_18003CE43
0x18003ce1b  mov     rcx, [rsp+58h]; this
0x18003ce20  mov     r9d, eax; char *
0x18003ce23  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003ce2a  mov     edx, 0B4h; void *
0x18003ce2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ce34  nop
0x18003ce35  lea     rcx, [rsp+58h+arg_0]
0x18003ce3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ce3f  mov     eax, ebx
0x18003ce41  jmp     short loc_18003CEB3
0x18003ce43  mov     [rsp+58h+dwCapabilities], 0; dwCapabilities
0x18003ce4b  mov     [rsp+58h+pAuthInfo], 0; pAuthInfo
0x18003ce54  mov     eax, 3
0x18003ce59  mov     [rsp+58h+dwImpLevel], eax; dwImpLevel
0x18003ce5d  mov     dword ptr [rsp+58h+ppv], eax; int
0x18003ce61  xor     r9d, r9d; pServerPrincName
0x18003ce64  xor     r8d, r8d; dwAuthzSvc
0x18003ce67  lea     edx, [rax+7]; dwAuthnSvc
0x18003ce6a  mov     rcx, [rsi]; pProxy
0x18003ce6d  call    cs:__imp_CoSetProxyBlanket
0x18003ce73  mov     ebx, eax
0x18003ce75  test    eax, eax
0x18003ce77  jns     short loc_18003CEA1
0x18003ce79  mov     rcx, [rsp+58h]; this
0x18003ce7e  mov     r9d, eax; char *
0x18003ce81  lea     r8, aOnecoreuapNetU_3; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18003ce88  mov     edx, 0C1h; void *
0x18003ce8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ce92  nop
0x18003ce93  lea     rcx, [rsp+58h+arg_0]
0x18003ce98  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ce9d  mov     eax, ebx
0x18003ce9f  jmp     short loc_18003CEB3
0x18003cea1  lea     rcx, [rsp+58h+arg_0]
0x18003cea6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ceab  xor     eax, eax
0x18003cead  jmp     short loc_18003CEB3
0x18003ceaf  mov     eax, dword ptr [rsp+58h+arg_0]
0x18003ceb3  mov     rbx, [rsp+58h+arg_8]
0x18003ceb8  mov     rsi, [rsp+58h+arg_10]
0x18003cebd  add     rsp, 50h
0x18003cec1  pop     rdi
0x18003cec2  retn
```
