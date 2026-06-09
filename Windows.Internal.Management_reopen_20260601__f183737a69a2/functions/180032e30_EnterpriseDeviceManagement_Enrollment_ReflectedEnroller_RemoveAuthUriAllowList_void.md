# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RemoveAuthUriAllowList(void)

- ea: `0x180032e30`
- end: `0x180032ecf`
- name: `?RemoveAuthUriAllowList@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180016698`
- `0x180017118`
- `0x18002a028`
- `0x180032e30`
- `0x180033500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032e91`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032e91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032e6e`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RemoveAuthUriAllowList(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this)
{
  unsigned int v1; // ebx
  const WCHAR *v2; // rax
  unsigned int v3; // eax
  __int64 v4; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath(1);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20006u, &hKey);
  if ( v3 )
  {
    v4 = 379;
LABEL_5:
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v4,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
           (const char *)v3,
           phkResult);
    goto LABEL_6;
  }
  v3 = RegDeleteValueW(hKey, L"authAllowList");
  if ( v3 )
  {
    v4 = 380;
    goto LABEL_5;
  }
LABEL_6:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x180032e30  push    rbx
0x180032e32  sub     rsp, 30h
0x180032e36  xor     ebx, ebx
0x180032e38  lea     rcx, [rsp+38h+hKey]
0x180032e3d  xor     edx, edx
0x180032e3f  mov     [rsp+38h+hKey], rbx
0x180032e44  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180032e49  lea     ecx, [rbx+1]
0x180032e4c  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180032e51  lea     rcx, [rsp+38h+hKey]
0x180032e56  mov     r9d, 20006h; samDesired
0x180032e5c  mov     qword ptr [rsp+38h+phkResult], rcx; unsigned int
0x180032e61  xor     r8d, r8d; ulOptions
0x180032e64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032e6b  mov     rdx, rax; lpSubKey
0x180032e6e  call    cs:__imp_RegOpenKeyExW
0x180032e75  nop     dword ptr [rax+rax+00h]
0x180032e7a  test    eax, eax
0x180032e7c  jz      short loc_180032E85
0x180032e7e  mov     edx, 17Bh
0x180032e83  jmp     short loc_180032EA6
0x180032e85  mov     rcx, [rsp+38h+hKey]; hKey
0x180032e8a  lea     rdx, ValueName; "authAllowList"
0x180032e91  call    cs:__imp_RegDeleteValueW
0x180032e98  nop     dword ptr [rax+rax+00h]
0x180032e9d  test    eax, eax
0x180032e9f  jz      short loc_180032EBC
0x180032ea1  mov     edx, 17Ch; void *
0x180032ea6  mov     rcx, [rsp+38h]; this
0x180032eab  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180032eb2  mov     r9d, eax; char *
0x180032eb5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032eba  mov     ebx, eax
0x180032ebc  lea     rcx, [rsp+38h+hKey]
0x180032ec1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180032ec6  mov     eax, ebx
0x180032ec8  add     rsp, 30h
0x180032ecc  pop     rbx
0x180032ecd  retn
```
