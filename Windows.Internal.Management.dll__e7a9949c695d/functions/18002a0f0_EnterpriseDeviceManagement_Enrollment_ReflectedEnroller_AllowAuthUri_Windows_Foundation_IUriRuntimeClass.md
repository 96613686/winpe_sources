# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::AllowAuthUri(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x18002a0f0`
- end: `0x18002a237`
- name: `?AllowAuthUri@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a2a4`
- `0x180015f70`
- `0x1800169b8`
- `0x180017244`
- `0x18002a0f0`
- `0x18002b664`
- `0x18003446c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002a14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002a14e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a1db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a1db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a205`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a205`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a1a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a1a6`

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
0x18002a0f0  mov     [rsp-8+arg_0], rbx
0x18002a0f5  push    rbp
0x18002a0f6  mov     rbp, rsp
0x18002a0f9  sub     rsp, 50h
0x18002a0fd  mov     rax, [rdx]
0x18002a100  mov     rcx, rdx
0x18002a103  lea     rdx, [rbp+string]
0x18002a107  mov     [rbp+string], 0
0x18002a10f  mov     rax, [rax+58h]
0x18002a113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a118  mov     ebx, eax
0x18002a11a  test    eax, eax
0x18002a11c  jns     short loc_18002A13B
0x18002a11e  mov     rcx, [rbp+8]; this
0x18002a122  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a129  mov     r9d, eax; char *
0x18002a12c  mov     edx, 16Eh; void *
0x18002a131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a136  jmp     loc_18002A221
0x18002a13b  mov     rcx, [rbp+string]; string
0x18002a13f  mov     [rbp+hKey], 0
0x18002a147  mov     [rbp+dwDisposition], 0
0x18002a14e  call    cs:__imp_WindowsGetStringLen
0x18002a154  xor     edx, edx
0x18002a156  lea     rcx, [rbp+hKey]
0x18002a15a  mov     ebx, eax
0x18002a15c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a161  mov     ecx, 1
0x18002a166  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18002a16b  lea     rcx, [rbp+dwDisposition]
0x18002a16f  xor     r9d, r9d; lpClass
0x18002a172  mov     [rsp+50h+lpdwDisposition], rcx; lpdwDisposition
0x18002a177  xor     r8d, r8d; Reserved
0x18002a17a  lea     rcx, [rbp+hKey]
0x18002a17e  mov     rdx, rax; lpSubKey
0x18002a181  mov     [rsp+50h+phkResult], rcx; phkResult
0x18002a186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a18d  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a196  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18002a19e  mov     [rsp+50h+dwOptions], 0; unsigned int
0x18002a1a6  call    cs:__imp_RegCreateKeyExW
0x18002a1ac  test    eax, eax
0x18002a1ae  jz      short loc_18002A1D5
0x18002a1b0  mov     edx, 172h; void *
0x18002a1b5  mov     rcx, [rbp+8]; this
0x18002a1b9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a1c0  mov     r9d, eax; char *
0x18002a1c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a1c8  lea     rcx, [rbp+hKey]
0x18002a1cc  mov     ebx, eax
0x18002a1ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a1d3  jmp     short loc_18002A221
0x18002a1d5  mov     rcx, [rbp+string]; string
0x18002a1d9  xor     edx, edx; length
0x18002a1db  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a1e1  mov     rcx, [rbp+hKey]; hKey
0x18002a1e5  lea     edx, ds:2[rbx*2]
0x18002a1ec  mov     [rsp+50h+samDesired], edx; cbData
0x18002a1f0  mov     r9d, 1; dwType
0x18002a1f6  lea     rdx, ValueName; "authAllowList"
0x18002a1fd  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18002a202  xor     r8d, r8d; Reserved
0x18002a205  call    cs:__imp_RegSetValueExW
0x18002a20b  test    eax, eax
0x18002a20d  jz      short loc_18002A216
0x18002a20f  mov     edx, 173h
0x18002a214  jmp     short loc_18002A1B5
0x18002a216  lea     rcx, [rbp+hKey]
0x18002a21a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a21f  xor     ebx, ebx
0x18002a221  lea     rcx, [rbp+string]; this
0x18002a225  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002a22a  mov     eax, ebx
0x18002a22c  mov     rbx, [rsp+50h+arg_0]
0x18002a231  add     rsp, 50h
0x18002a235  pop     rbp
0x18002a236  retn
```
