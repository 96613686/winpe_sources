# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::AllowAuthUri(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x180028990`
- end: `0x180028af0`
- name: `?AllowAuthUri@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x180017a40`
- `0x180028990`
- `0x18002a028`
- `0x180033500`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800289ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800289ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028a87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028a87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028ab7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028ab7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a4c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a4c`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::AllowAuthUri(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        struct Windows::Foundation::IUriRuntimeClass *a2)
{
  __int64 v2; // rax
  int v3; // eax
  unsigned int v4; // ebx
  UINT32 StringLen; // ebx
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rdx
  const BYTE *StringRawBuffer; // rax
  int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD dwDisposition; // [rsp+68h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+28h] BYREF

  v2 = *(_QWORD *)a2;
  string = 0;
  v3 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(v2 + 88))(a2, &string);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    StringLen = WindowsGetStringLen(string);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = (const WCHAR *)DMGetKnownRegPath(1);
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( v7 )
    {
      v8 = 370;
    }
    else
    {
      StringRawBuffer = (const BYTE *)WindowsGetStringRawBuffer(string, 0);
      v7 = RegSetValueExW(hKey, L"authAllowList", 0, 1u, StringRawBuffer, 2 * StringLen + 2);
      if ( !v7 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v4 = 0;
        goto LABEL_9;
      }
      v8 = 371;
    }
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
           (const char *)v7,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
  }
LABEL_9:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v4;
}

```

## disassembly

```asm
0x180028990  mov     [rsp-8+arg_0], rbx
0x180028995  push    rbp
0x180028996  mov     rbp, rsp
0x180028999  sub     rsp, 50h
0x18002899d  mov     rax, [rdx]
0x1800289a0  mov     rcx, rdx
0x1800289a3  lea     rdx, [rbp+string]
0x1800289a7  mov     [rbp+string], 0
0x1800289af  mov     rax, [rax+58h]
0x1800289b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289b8  mov     ebx, eax
0x1800289ba  test    eax, eax
0x1800289bc  jns     short loc_1800289DB
0x1800289be  mov     rcx, [rbp+8]; this
0x1800289c2  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800289c9  mov     r9d, eax; char *
0x1800289cc  mov     edx, 16Eh; void *
0x1800289d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289d6  jmp     loc_180028AD9
0x1800289db  mov     rcx, [rbp+string]; string
0x1800289df  mov     [rbp+hKey], 0
0x1800289e7  mov     [rbp+dwDisposition], 0
0x1800289ee  call    cs:__imp_WindowsGetStringLen
0x1800289f5  nop     dword ptr [rax+rax+00h]
0x1800289fa  xor     edx, edx
0x1800289fc  lea     rcx, [rbp+hKey]
0x180028a00  mov     ebx, eax
0x180028a02  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028a07  mov     ecx, 1
0x180028a0c  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180028a11  lea     rcx, [rbp+dwDisposition]
0x180028a15  xor     r9d, r9d; lpClass
0x180028a18  mov     [rsp+50h+lpdwDisposition], rcx; lpdwDisposition
0x180028a1d  xor     r8d, r8d; Reserved
0x180028a20  lea     rcx, [rbp+hKey]
0x180028a24  mov     rdx, rax; lpSubKey
0x180028a27  mov     [rsp+50h+phkResult], rcx; phkResult
0x180028a2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028a33  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180028a3c  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180028a44  mov     [rsp+50h+dwOptions], 0; unsigned int
0x180028a4c  call    cs:__imp_RegCreateKeyExW
0x180028a53  nop     dword ptr [rax+rax+00h]
0x180028a58  test    eax, eax
0x180028a5a  jz      short loc_180028A81
0x180028a5c  mov     edx, 172h; void *
0x180028a61  mov     rcx, [rbp+8]; this
0x180028a65  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180028a6c  mov     r9d, eax; char *
0x180028a6f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028a74  lea     rcx, [rbp+hKey]
0x180028a78  mov     ebx, eax
0x180028a7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028a7f  jmp     short loc_180028AD9
0x180028a81  mov     rcx, [rbp+string]; string
0x180028a85  xor     edx, edx; length
0x180028a87  call    cs:__imp_WindowsGetStringRawBuffer
0x180028a8e  nop     dword ptr [rax+rax+00h]
0x180028a93  mov     rcx, [rbp+hKey]; hKey
0x180028a97  lea     edx, ds:2[rbx*2]
0x180028a9e  mov     [rsp+50h+samDesired], edx; cbData
0x180028aa2  mov     r9d, 1; dwType
0x180028aa8  lea     rdx, ValueName; "authAllowList"
0x180028aaf  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180028ab4  xor     r8d, r8d; Reserved
0x180028ab7  call    cs:__imp_RegSetValueExW
0x180028abe  nop     dword ptr [rax+rax+00h]
0x180028ac3  test    eax, eax
0x180028ac5  jz      short loc_180028ACE
0x180028ac7  mov     edx, 173h
0x180028acc  jmp     short loc_180028A61
0x180028ace  lea     rcx, [rbp+hKey]
0x180028ad2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028ad7  xor     ebx, ebx
0x180028ad9  lea     rcx, [rbp+string]; this
0x180028add  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180028ae2  mov     eax, ebx
0x180028ae4  mov     rbx, [rsp+50h+arg_0]
0x180028ae9  add     rsp, 50h
0x180028aed  pop     rbp
0x180028aee  retn
```
