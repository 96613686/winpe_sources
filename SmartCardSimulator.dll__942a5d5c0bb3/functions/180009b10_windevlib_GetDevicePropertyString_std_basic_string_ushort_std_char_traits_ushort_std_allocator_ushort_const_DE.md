# windevlib::GetDevicePropertyString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_DEVPROPKEY const *)

- ea: `0x180009b10`
- end: `0x180009c3e`
- name: `?GetDevicePropertyString@windevlib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBU_DEVPROPKEY@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000835c`
- `0x180020248`
- `0x18002941c`

## callees

- `0x180008018`
- `0x1800089e8`
- `0x180008a6c`
- `0x180009b10`
- `0x180009c44`
- `0x18000a960`
- `0x18000b94c`
- `0x18000ba94`
- `0x18000bad4`
- `0x180058700`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180009b4c`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180009b4c`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180009b9e`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180009b9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall windevlib::GetDevicePropertyString(__int64 a1, const WCHAR *a2, __int64 a3)
{
  HDEVINFO DeviceInfoList; // rax
  BOOL v7; // eax
  __int64 DevicePropertyString; // rax
  __int64 v9; // rdx
  HDEVINFO DeviceInfoSet; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v12[2]; // [rsp+38h] [rbp-21h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+48h] [rbp-11h] BYREF
  _WORD v14[8]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  __int64 v16; // [rsp+80h] [rbp+27h]

  v12[0] = a1;
  DeviceInfoSet = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &DeviceInfoSet,
    DeviceInfoList);
  throw_error_setupapi_if(DeviceInfoSet == 0);
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const WCHAR **)a2;
  v7 = SetupDiOpenDeviceInfoW(DeviceInfoSet, a2, 0, 0, &DeviceInfoData);
  throw_error_setupapi_if(!v7);
  v16 = 7;
  v15 = 0;
  v14[0] = 0;
  DevicePropertyString = windevlib::GetDevicePropertyString(v12, &DeviceInfoSet, &DeviceInfoData, a3, v14);
  errorlib::scoped_error<setupapi_error::tag>::throwfailed(DevicePropertyString);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v12);
  std::wstring::wstring(a1, v14);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v14, v9, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&DeviceInfoSet);
  return a1;
}

```

## disassembly

```asm
0x180009b10  mov     [rsp-8+arg_18], rsi
0x180009b15  push    rbp
0x180009b16  push    rdi
0x180009b17  push    r14
0x180009b19  lea     rbp, [rsp-47h]
0x180009b1e  sub     rsp, 0A0h
0x180009b25  mov     rax, cs:__security_cookie
0x180009b2c  xor     rax, rsp
0x180009b2f  mov     [rbp+57h+var_20], rax
0x180009b33  mov     r14, r8
0x180009b36  mov     rdi, rdx
0x180009b39  mov     rsi, rcx
0x180009b3c  mov     [rbp+57h+var_78], rcx
0x180009b40  mov     [rbp+57h+DeviceInfoSet], 0
0x180009b48  xor     edx, edx; hwndParent
0x180009b4a  xor     ecx, ecx; ClassGuid
0x180009b4c  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180009b52  mov     rdx, rax
0x180009b55  lea     rcx, [rbp+57h+DeviceInfoSet]
0x180009b59  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180009b5e  xor     ecx, ecx
0x180009b60  cmp     [rbp+57h+DeviceInfoSet], rcx
0x180009b64  setz    cl; int
0x180009b67  call    ?throw_error_setupapi_if@@YAXH@Z; throw_error_setupapi_if(int)
0x180009b6c  xorps   xmm0, xmm0
0x180009b6f  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x180009b73  movups  xmmword ptr [rbp+57h+var_68.ClassGuid.Data4+4], xmm0
0x180009b77  mov     [rbp+57h+var_68.cbSize], 20h ; ' '
0x180009b7e  cmp     qword ptr [rdi+18h], 8
0x180009b83  jb      short loc_180009B88
0x180009b85  mov     rdi, [rdi]
0x180009b88  lea     rax, [rbp+57h+var_68]
0x180009b8c  mov     [rsp+0B0h+DeviceInfoData], rax; DeviceInfoData
0x180009b91  xor     r9d, r9d; OpenFlags
0x180009b94  xor     r8d, r8d; hwndParent
0x180009b97  mov     rdx, rdi; DeviceInstanceId
0x180009b9a  mov     rcx, [rbp+57h+DeviceInfoSet]; DeviceInfoSet
0x180009b9e  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180009ba4  xor     ecx, ecx
0x180009ba6  test    eax, eax
0x180009ba8  setz    cl; int
0x180009bab  call    ?throw_error_setupapi_if@@YAXH@Z; throw_error_setupapi_if(int)
0x180009bb0  mov     [rbp+57h+var_30], 7
0x180009bb8  mov     [rbp+57h+var_38], 0
0x180009bc0  xor     eax, eax
0x180009bc2  mov     [rbp+57h+var_48], ax
0x180009bc6  lea     rax, [rbp+57h+var_48]
0x180009bca  mov     [rsp+0B0h+DeviceInfoData], rax
0x180009bcf  mov     r9, r14
0x180009bd2  lea     r8, [rbp+57h+var_68]
0x180009bd6  lea     rdx, [rbp+57h+DeviceInfoSet]
0x180009bda  lea     rcx, [rbp+57h+var_78]
0x180009bde  call    ?GetDevicePropertyString@windevlib@@YA?AV?$scoped_error@Utag@setupapi_error@@@errorlib@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SP_DEVINFO_DATA@@PEBU_DEVPROPKEY@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windevlib::GetDevicePropertyString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,_SP_DEVINFO_DATA *,_DEVPROPKEY const *,std::wstring *)
0x180009be3  nop
0x180009be4  mov     rcx, rax
0x180009be7  call    ?throwfailed@?$scoped_error@Utag@setupapi_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<setupapi_error::tag>::throwfailed(void)
0x180009bec  nop
0x180009bed  lea     rcx, [rbp+57h+var_78]
0x180009bf1  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180009bf6  lea     rdx, [rbp+57h+var_48]
0x180009bfa  mov     rcx, rsi
0x180009bfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180009c02  nop
0x180009c03  xor     r8d, r8d
0x180009c06  mov     dl, 1
0x180009c08  lea     rcx, [rbp+57h+var_48]
0x180009c0c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009c11  nop
0x180009c12  lea     rcx, [rbp+57h+DeviceInfoSet]
0x180009c16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180009c1b  mov     rax, rsi
0x180009c1e  mov     rcx, [rbp+57h+var_20]
0x180009c22  xor     rcx, rsp; StackCookie
0x180009c25  call    __security_check_cookie
0x180009c2a  mov     rsi, [rsp+0B0h+arg_18]
0x180009c32  add     rsp, 0A0h
0x180009c39  pop     r14
0x180009c3b  pop     rdi
0x180009c3c  pop     rbp
0x180009c3d  retn
```
