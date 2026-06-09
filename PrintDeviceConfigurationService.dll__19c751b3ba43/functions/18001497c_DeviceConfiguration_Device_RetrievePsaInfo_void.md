# DeviceConfiguration::Device::RetrievePsaInfo(void)

- ea: `0x18001497c`
- end: `0x180014a67`
- name: `?RetrievePsaInfo@Device@DeviceConfiguration@@QEAAJXZ`
- size: `235`
- prototype: `__int64 __fastcall(DeviceConfiguration::Device *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800160c0`

## callees

- `0x1800020c0`
- `0x18000aeac`
- `0x18000c19c`
- `0x18000e628`
- `0x18000eb80`
- `0x1800115a0`
- `0x18001440c`
- `0x18001497c`

## import_xrefs

- `Print.PrintSupport.Source!GetAppUserModelId` at `0x1800149d3`
- `Print.PrintSupport.Source!GetAppUserModelId` at `0x1800149d3`

## string_xrefs

- `0x1800149a3`: `Attempting to retrieve PSA AUMID for device %ws`
- `0x1800149aa`: `DeviceConfiguration::Device::RetrievePsaInfo`
- `0x180014a23`: `DeviceConfiguration::Device::RetrievePsaInfo`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::RetrievePsaInfo(DeviceConfiguration::Device *this)
{
  DeviceConfiguration::Device *v1; // rbx
  DeviceConfiguration::Device *v2; // r8
  _QWORD *v3; // rcx
  __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+28h] [rbp-30h] BYREF

  v1 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = this;
  else
    v2 = *(DeviceConfiguration::Device **)this;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::Device::RetrievePsaInfo",
    L"Attempting to retrieve PSA AUMID for device %ws",
    v2);
  v6 = 0;
  v3 = (_QWORD *)((char *)v1 + 32);
  if ( *((_QWORD *)v1 + 7) > 7u )
    v3 = (_QWORD *)*v3;
  if ( (int)GetAppUserModelId(v3, &v6) >= 0 )
  {
    v4 = std::wstring::wstring(v7, v6);
    std::wstring::operator=((char *)v1 + 192, v4);
    std::wstring::_Tidy_deallocate(v7);
  }
  if ( *((_QWORD *)v1 + 26) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
    return 0;
  }
  else
  {
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(DeviceConfiguration::Device **)v1;
    DeviceConfigurationTelemetry::WriteDbgTraceWarning(
      "DeviceConfiguration::Device::RetrievePsaInfo",
      L"Failed to retrieve PSA AUMID for device %ws from device properties or via GetAppUserModelId",
      v1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x18001497c  push    rbx
0x18001497e  sub     rsp, 50h
0x180014982  mov     rax, cs:__security_cookie
0x180014989  xor     rax, rsp
0x18001498c  mov     [rsp+58h+var_10], rax
0x180014991  mov     rbx, rcx
0x180014994  cmp     qword ptr [rcx+18h], 7
0x180014999  jbe     short loc_1800149A0
0x18001499b  mov     r8, [rcx]
0x18001499e  jmp     short loc_1800149A3
0x1800149a0  mov     r8, rbx
0x1800149a3  lea     rdx, aAttemptingToRe_0; "Attempting to retrieve PSA AUMID for de"...
0x1800149aa  lea     rcx, aDeviceconfigur_21; "DeviceConfiguration::Device::RetrievePs"...
0x1800149b1  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800149b6  nop
0x1800149b7  mov     [rsp+58h+var_38], 0
0x1800149c0  lea     rcx, [rbx+20h]
0x1800149c4  cmp     qword ptr [rcx+18h], 7
0x1800149c9  jbe     short loc_1800149CE
0x1800149cb  mov     rcx, [rcx]
0x1800149ce  lea     rdx, [rsp+58h+var_38]
0x1800149d3  call    cs:__imp_GetAppUserModelId
0x1800149d9  test    eax, eax
0x1800149db  js      short loc_180014A05
0x1800149dd  mov     rdx, [rsp+58h+var_38]
0x1800149e2  lea     rcx, [rsp+58h+var_30]
0x1800149e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800149ec  lea     rcx, [rbx+0C0h]
0x1800149f3  mov     rdx, rax
0x1800149f6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800149fb  lea     rcx, [rsp+58h+var_30]
0x180014a00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014a05  cmp     qword ptr [rbx+0D0h], 0
0x180014a0d  jnz     short loc_180014A41
0x180014a0f  cmp     qword ptr [rbx+18h], 7
0x180014a14  jbe     short loc_180014A19
0x180014a16  mov     rbx, [rbx]
0x180014a19  mov     r8, rbx
0x180014a1c  lea     rdx, aFailedToRetrie_1; "Failed to retrieve PSA AUMID for device"...
0x180014a23  lea     rcx, aDeviceconfigur_21; "DeviceConfiguration::Device::RetrievePs"...
0x180014a2a  call    ?WriteDbgTraceWarning@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014a2f  nop
0x180014a30  lea     rcx, [rsp+58h+var_38]
0x180014a35  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014a3a  mov     eax, 80070490h
0x180014a3f  jmp     short loc_180014A53
0x180014a41  lea     rcx, [rsp+58h+var_38]
0x180014a46  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014a4b  xor     eax, eax
0x180014a4d  jmp     short loc_180014A53
0x180014a4f  mov     eax, dword ptr [rsp+58h+var_38]
0x180014a53  mov     rcx, [rsp+58h+var_10]
0x180014a58  xor     rcx, rsp; StackCookie
0x180014a5b  call    __security_check_cookie
0x180014a60  add     rsp, 50h
0x180014a64  pop     rbx
0x180014a65  retn
```
