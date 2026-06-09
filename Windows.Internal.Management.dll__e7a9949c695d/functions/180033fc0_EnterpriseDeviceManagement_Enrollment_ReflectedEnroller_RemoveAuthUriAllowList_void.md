# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RemoveAuthUriAllowList(void)

- ea: `0x180033fc0`
- end: `0x180034052`
- name: `?RemoveAuthUriAllowList@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180015f70`
- `0x1800169b8`
- `0x18002b664`
- `0x180033fc0`
- `0x18003446c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003401b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003401b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033ffe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033ffe`

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
0x180033fc0  push    rbx
0x180033fc2  sub     rsp, 30h
0x180033fc6  xor     ebx, ebx
0x180033fc8  lea     rcx, [rsp+38h+hKey]
0x180033fcd  xor     edx, edx
0x180033fcf  mov     [rsp+38h+hKey], rbx
0x180033fd4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033fd9  lea     ecx, [rbx+1]
0x180033fdc  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180033fe1  lea     rcx, [rsp+38h+hKey]
0x180033fe6  mov     r9d, 20006h; samDesired
0x180033fec  mov     qword ptr [rsp+38h+phkResult], rcx; unsigned int
0x180033ff1  xor     r8d, r8d; ulOptions
0x180033ff4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033ffb  mov     rdx, rax; lpSubKey
0x180033ffe  call    cs:__imp_RegOpenKeyExW
0x180034004  test    eax, eax
0x180034006  jz      short loc_18003400F
0x180034008  mov     edx, 17Bh
0x18003400d  jmp     short loc_18003402A
0x18003400f  mov     rcx, [rsp+38h+hKey]; hKey
0x180034014  lea     rdx, ValueName; "authAllowList"
0x18003401b  call    cs:__imp_RegDeleteValueW
0x180034021  test    eax, eax
0x180034023  jz      short loc_180034040
0x180034025  mov     edx, 17Ch; void *
0x18003402a  mov     rcx, [rsp+38h]; this
0x18003402f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034036  mov     r9d, eax; char *
0x180034039  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003403e  mov     ebx, eax
0x180034040  lea     rcx, [rsp+38h+hKey]
0x180034045  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003404a  mov     eax, ebx
0x18003404c  add     rsp, 30h
0x180034050  pop     rbx
0x180034051  retn
```
