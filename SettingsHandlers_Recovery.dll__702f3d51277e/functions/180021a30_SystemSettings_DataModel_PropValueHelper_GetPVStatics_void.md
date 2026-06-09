# SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)

- ea: `0x180021a30`
- end: `0x180021ac5`
- name: `?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ`
- size: `149`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013c78`
- `0x180017de0`
- `0x18001879c`
- `0x180018f40`
- `0x180019300`
- `0x1800195d0`
- `0x180019900`

## callees

- `0x180002350`
- `0x18001d6bc`
- `0x180021a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021aa2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021aa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021a76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021a76`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021a93`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021a93`

## pseudocode

```c
__int64 SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
{
  unsigned int ActivationFactory; // ebx
  HRESULT v1; // eax
  int v2; // edx
  unsigned int v3; // r8d
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  ActivationFactory = 0;
  EnterCriticalSection(&SystemSettings::DataModel::PropValueHelper::_staticsLock);
  if ( !SystemSettings::DataModel::PropValueHelper::_pPVStatics )
  {
    string = 0;
    v1 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
    if ( v1 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
      JUMPOUT(0x180021AC4LL);
    }
    ActivationFactory = RoGetActivationFactory(
                          string,
                          &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                          &SystemSettings::DataModel::PropValueHelper::_pPVStatics);
  }
  LeaveCriticalSection(&SystemSettings::DataModel::PropValueHelper::_staticsLock);
  return ActivationFactory;
}

```

## disassembly

```asm
0x180021a30  push    rbx
0x180021a32  sub     rsp, 50h
0x180021a36  mov     rax, cs:__security_cookie
0x180021a3d  xor     rax, rsp
0x180021a40  mov     [rsp+58h+var_18], rax
0x180021a45  lea     rcx, ?_staticsLock@PropValueHelper@DataModel@SystemSettings@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180021a4c  xor     ebx, ebx
0x180021a4e  call    cs:__imp_EnterCriticalSection
0x180021a54  cmp     cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA, rbx; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180021a5b  jnz     short loc_180021A9B
0x180021a5d  lea     r9, [rsp+58h+string]; string
0x180021a62  mov     [rsp+58h+string], rbx
0x180021a67  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180021a6c  lea     edx, [rbx+20h]; length
0x180021a6f  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180021a76  call    cs:__imp_WindowsCreateStringReference
0x180021a7c  test    eax, eax
0x180021a7e  js      short loc_180021ABD
0x180021a80  mov     rcx, [rsp+58h+string]
0x180021a85  lea     r8, ?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180021a8c  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180021a93  call    cs:__imp_RoGetActivationFactory
0x180021a99  mov     ebx, eax
0x180021a9b  lea     rcx, ?_staticsLock@PropValueHelper@DataModel@SystemSettings@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180021aa2  call    cs:__imp_LeaveCriticalSection
0x180021aa8  mov     eax, ebx
0x180021aaa  mov     rcx, [rsp+58h+var_18]
0x180021aaf  xor     rcx, rsp; StackCookie
0x180021ab2  call    __security_check_cookie
0x180021ab7  add     rsp, 50h
0x180021abb  pop     rbx
0x180021abc  retn
0x180021abd  mov     ecx, eax; this
0x180021abf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
