# AppReadiness::Tasks::RegisterPackage::OnStarted(void)

- ea: `0x180021400`
- end: `0x1800214e0`
- name: `?OnStarted@RegisterPackage@Tasks@AppReadiness@@MEAAXXZ`
- size: `224`
- prototype: `void __fastcall(AppReadiness::Tasks::RegisterPackage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180021400`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002146d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002146d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021457`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021483`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021483`

## string_xrefs

- `0x180021450`: `Windows.Foundation.Uri`
- `0x180021495`: `onecoreuap\shell\appreadiness\src\tasks\registerpackage.cpp`
- `0x1800214a1`: `AppReadiness::Tasks::RegisterPackage::OnStarted`
- `0x1800214a8`: `Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_Foundation_Uri).Get(), m_uriFactory.ReleaseAndGetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::Tasks::RegisterPackage::OnStarted(AppReadiness::Tasks::RegisterPackage *this)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx
  HRESULT v3; // eax
  int ActivationFactory; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF

  v1 = (_QWORD *)((char *)this + 256);
  v2 = *((_QWORD *)this + 32);
  if ( v2 )
  {
    *v1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, v1);
  if ( ActivationFactory < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&hstringHeader,
      ActivationFactory,
      "Windows::Foundation::GetActivationFactory(HStringReference(RuntimeClass_Windows_Foundation_Uri).Get(), m_uriFactor"
      "y.ReleaseAndGetAddressOf())",
      "AppReadiness::Tasks::RegisterPackage::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
      67);
    throw (Windows::HResultException *)&hstringHeader;
  }
}

```

## disassembly

```asm
0x180021400  push    rbx
0x180021402  sub     rsp, 60h
0x180021406  mov     rax, cs:__security_cookie
0x18002140d  xor     rax, rsp
0x180021410  mov     [rsp+68h+var_10], rax
0x180021415  lea     rbx, [rcx+100h]
0x18002141c  mov     rcx, [rbx]
0x18002141f  test    rcx, rcx
0x180021422  jz      short loc_180021438
0x180021424  mov     qword ptr [rbx], 0
0x18002142b  mov     rax, [rcx]
0x18002142e  mov     rax, [rax+10h]
0x180021432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021437  nop
0x180021438  mov     [rsp+68h+string], 0
0x180021441  lea     r9, [rsp+68h+string]; string
0x180021446  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18002144b  mov     edx, 16h; length
0x180021450  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180021457  call    cs:__imp_WindowsCreateStringReference
0x18002145d  test    eax, eax
0x18002145f  jns     short loc_180021474
0x180021461  xor     r9d, r9d; lpArguments
0x180021464  xor     r8d, r8d; nNumberOfArguments
0x180021467  lea     edx, [r9+1]; dwExceptionFlags
0x18002146b  mov     ecx, eax; dwExceptionCode
0x18002146d  call    cs:__imp_RaiseException
0x180021473  int     3; Trap to Debugger
0x180021474  mov     r8, rbx
0x180021477  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18002147e  mov     rcx, [rsp+68h+string]
0x180021483  call    cs:__imp_RoGetActivationFactory
0x180021489  test    eax, eax
0x18002148b  jns     short loc_1800214CD
0x18002148d  mov     [rsp+68h+var_40], 43h ; 'C'; int
0x180021495  lea     rcx, aOnecoreuapShel_9; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18002149c  mov     [rsp+68h+var_48], rcx; char *
0x1800214a1  lea     r9, aAppreadinessTa_17; "AppReadiness::Tasks::RegisterPackage::O"...
0x1800214a8  lea     r8, aWindowsFoundat_3; "Windows::Foundation::GetActivationFacto"...
0x1800214af  mov     edx, eax; int
0x1800214b1  lea     rcx, [rsp+68h+hstringHeader]; this
0x1800214b6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800214bb  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800214c2  lea     rcx, [rsp+68h+hstringHeader]; pExceptionObject
0x1800214c7  call    _CxxThrowException_0
0x1800214cd  mov     rcx, [rsp+68h+var_10]
0x1800214d2  xor     rcx, rsp; StackCookie
0x1800214d5  call    __security_check_cookie
0x1800214da  add     rsp, 60h
0x1800214de  pop     rbx
0x1800214df  retn
```
