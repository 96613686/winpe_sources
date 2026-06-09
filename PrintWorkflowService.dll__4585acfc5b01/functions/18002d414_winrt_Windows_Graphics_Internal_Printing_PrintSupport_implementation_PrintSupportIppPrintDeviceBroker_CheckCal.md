# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportIppPrintDeviceBroker::CheckCallerAccess(void)

- ea: `0x18002d414`
- end: `0x18002d587`
- name: `?CheckCallerAccess@PrintSupportIppPrintDeviceBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ`
- size: `371`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportIppPrintDeviceBroker *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d830`

## callees

- `0x180008610`
- `0x1800127a4`
- `0x1800129dc`
- `0x1800253ec`
- `0x1800275e0`
- `0x180027fd8`
- `0x18002d414`
- `0x180055968`
- `0x180055a34`
- `0x180055d08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002d4ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002d4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d46f`
- `Print.PrintSupport.Source!GetAppUserModelId` at `0x18002d4d5`
- `Print.PrintSupport.Source!GetAppUserModelId` at `0x18002d4d5`

## string_xrefs

- `0x18002d536`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportippprintdevicebroker.cpp`
- `0x18002d54b`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportippprintdevicebroker.cpp`
- `0x18002d560`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportippprintdevicebroker.cpp`
- `0x18002d575`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportippprintdevicebroker.cpp`
- `0x18002d52a`: `Caller does not have access to the printer.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportIppPrintDeviceBroker::CheckCallerAccess(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportIppPrintDeviceBroker *this)
{
  char v2; // di
  int CallingProcessHandle; // ebx
  bool *v4; // r8
  char *v5; // rcx
  unsigned __int16 **v6; // rdx
  int CallingProcessAppId; // eax
  const unsigned __int16 *v8; // rax
  int AppUserModelId; // eax
  unsigned int v10; // eax
  int v11; // [rsp+20h] [rbp-10h]
  const char *v12; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *v14; // [rsp+58h] [rbp+28h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+30h] BYREF

  v2 = 0;
  LOBYTE(v14) = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, 0, &hObject);
  if ( CallingProcessHandle >= 0 )
  {
    CallingProcessHandle = CallerIdentity::IsProcessAppContainer((CallerIdentity *)hObject, &v14, v4);
    v2 = (char)v14;
  }
  v5 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( CallingProcessHandle < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportippprintdevicebroker.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      v11);
  if ( v2 )
  {
    hObject = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hObject,
      0);
    CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&hObject, v6);
    if ( CallingProcessAppId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportippprintdevicebroker.cpp",
        (const char *)(unsigned int)CallingProcessAppId,
        v11);
    v14 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v14,
      0);
    v8 = winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportIppPrintDeviceBroker *)((char *)this + 24));
    AppUserModelId = GetAppUserModelId(v8, &v14);
    if ( AppUserModelId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportippprintdevicebroker.cpp",
        (const char *)(unsigned int)AppUserModelId,
        v11);
    if ( (unsigned int)_o__wcsicmp(hObject, v14) )
    {
      v10 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportippprintdevicebroker.cpp",
        (const char *)v10,
        (int)"Caller does not have access to the printer.",
        v12);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hObject);
  }
}

```

## disassembly

```asm
0x18002d414  mov     [rsp-18h+arg_0], rbx
0x18002d419  push    rbp
0x18002d41a  push    rsi
0x18002d41b  push    rdi
0x18002d41c  mov     rbp, rsp
0x18002d41f  sub     rsp, 30h
0x18002d423  mov     rsi, rcx
0x18002d426  xor     dil, dil
0x18002d429  mov     byte ptr [rbp+arg_8], dil
0x18002d42d  mov     [rbp+hObject], 0
0x18002d435  lea     r8, [rbp+hObject]
0x18002d439  xor     edx, edx
0x18002d43b  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18002d440  mov     ebx, eax
0x18002d442  test    eax, eax
0x18002d444  js      short loc_18002D459
0x18002d446  lea     rdx, [rbp+arg_8]; void *
0x18002d44a  mov     rcx, [rbp+hObject]; this
0x18002d44e  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18002d453  mov     ebx, eax
0x18002d455  mov     dil, byte ptr [rbp+arg_8]
0x18002d459  mov     rcx, [rbp+hObject]; hObject
0x18002d45d  mov     [rbp+hObject], 0
0x18002d465  lea     rax, [rcx-1]
0x18002d469  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d46d  ja      short loc_18002D475
0x18002d46f  call    cs:__imp_CloseHandle
0x18002d475  mov     rcx, [rbp+18h]; this
0x18002d479  test    ebx, ebx
0x18002d47b  js      loc_18002D548
0x18002d481  test    dil, dil
0x18002d484  jz      loc_18002D50C
0x18002d48a  mov     [rbp+hObject], 0
0x18002d492  xor     edx, edx
0x18002d494  lea     rcx, [rbp+hObject]
0x18002d498  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002d49d  lea     rcx, [rbp+hObject]; this
0x18002d4a1  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18002d4a6  mov     rcx, [rbp+18h]; this
0x18002d4aa  test    eax, eax
0x18002d4ac  js      loc_18002D55D
0x18002d4b2  mov     [rbp+arg_8], 0
0x18002d4ba  xor     edx, edx
0x18002d4bc  lea     rcx, [rbp+arg_8]
0x18002d4c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002d4c5  lea     rcx, [rsi+18h]; this
0x18002d4c9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002d4ce  lea     rdx, [rbp+arg_8]
0x18002d4d2  mov     rcx, rax
0x18002d4d5  call    cs:__imp_GetAppUserModelId
0x18002d4db  mov     rcx, [rbp+18h]; this
0x18002d4df  test    eax, eax
0x18002d4e1  js      loc_18002D572
0x18002d4e7  mov     rdx, [rbp+arg_8]
0x18002d4eb  mov     rcx, [rbp+hObject]
0x18002d4ef  call    cs:__imp__o__wcsicmp
0x18002d4f5  test    eax, eax
0x18002d4f7  jnz     short loc_18002D519
0x18002d4f9  lea     rcx, [rbp+arg_8]
0x18002d4fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d502  nop
0x18002d503  lea     rcx, [rbp+hObject]
0x18002d507  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d50c  mov     rbx, [rsp+30h+arg_0]
0x18002d511  add     rsp, 30h
0x18002d515  pop     rdi
0x18002d516  pop     rsi
0x18002d517  pop     rbp
0x18002d518  retn
0x18002d519  mov     ecx, 80070005h
0x18002d51e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d523  mov     r9d, eax; char *
0x18002d526  mov     rcx, [rbp+18h]; this
0x18002d52a  lea     rax, aCallerDoesNotH; "Caller does not have access to the prin"...
0x18002d531  mov     qword ptr [rsp+30h+var_10], rax; int
0x18002d536  lea     r8, aOnecoreuapPrin_23; "onecoreuap\\printscan\\print\\workflow"...
0x18002d53d  mov     edx, 2Ch ; ','; void *
0x18002d542  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d548  mov     r9d, ebx; char *
0x18002d54b  lea     r8, aOnecoreuapPrin_23; "onecoreuap\\printscan\\print\\workflow"...
0x18002d552  mov     edx, 22h ; '"'; void *
0x18002d557  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d55d  mov     r9d, eax; char *
0x18002d560  lea     r8, aOnecoreuapPrin_23; "onecoreuap\\printscan\\print\\workflow"...
0x18002d567  mov     edx, 26h ; '&'; void *
0x18002d56c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d572  mov     r9d, eax; char *
0x18002d575  lea     r8, aOnecoreuapPrin_23; "onecoreuap\\printscan\\print\\workflow"...
0x18002d57c  mov     edx, 28h ; '('; void *
0x18002d581  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
