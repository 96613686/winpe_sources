# Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)

- ea: `0x180014ec0`
- end: `0x180015055`
- name: `?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800149f0`

## callees

- `0x180014ec0`
- `0x18001505c`
- `0x18001953c`
- `0x180023278`
- `0x1800286d4`
- `0x18002c640`
- `0x18002ce30`
- `0x180035120`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fe7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014f3d`

## string_xrefs

- `0x180014f70`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180014f8c`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180015014`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(
        HSTRING string,
        void (__fastcall ****a2)(_QWORD, __int64))
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *v5; // rbx
  PCWSTR StringRawBuffer; // rax
  int v7; // eax
  unsigned int v8; // esi
  int phkResult; // [rsp+20h] [rbp-148h]
  int phkResulta; // [rsp+20h] [rbp-148h]
  _QWORD *v12; // [rsp+30h] [rbp-138h] BYREF
  HKEY v13; // [rsp+38h] [rbp-130h] BYREF
  char v14; // [rsp+40h] [rbp-128h]
  WCHAR SubKey[128]; // [rsp+50h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v4 = *a2;
  *a2 = 0;
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *)operator new(
                                                                                                    0x10u,
                                                                                                    (const struct std::nothrow_t *)std::nothrow);
  if ( v5 )
  {
    *(_QWORD *)v5 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable';
    *((_QWORD *)v5 + 1) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v7 = StringCchPrintfW(SubKey, 0x80u, L"SOFTWARE\\Classes\\OneCoreContracts\\%s", StringRawBuffer);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v13 = 0;
      v12 = (_QWORD *)((char *)v5 + 8);
      v14 = 1;
      RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v13);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v12);
      wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
        a2,
        v5);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v7,
        phkResult);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)v8,
        phkResulta);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(
        v5,
        1u);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      phkResult);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180014ec0  mov     [rsp+arg_10], rbx
0x180014ec5  mov     [rsp+arg_18], rsi
0x180014eca  push    rdi
0x180014ecb  sub     rsp, 160h
0x180014ed2  mov     rax, cs:__security_cookie
0x180014ed9  xor     rax, rsp
0x180014edc  mov     [rsp+168h+var_18], rax
0x180014ee4  mov     rsi, rcx
0x180014ee7  mov     rdi, rdx
0x180014eea  mov     rcx, [rdx]
0x180014eed  mov     qword ptr [rdx], 0
0x180014ef4  test    rcx, rcx
0x180014ef7  jz      short loc_180014F09
0x180014ef9  mov     rax, [rcx]
0x180014efc  mov     edx, 1
0x180014f01  mov     rax, [rax]
0x180014f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014f10  mov     ecx, 10h; unsigned __int64
0x180014f15  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014f1a  mov     rbx, rax
0x180014f1d  test    rax, rax
0x180014f20  jz      loc_18001500C
0x180014f26  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x180014f2d  xor     edx, edx; length
0x180014f2f  mov     [rbx], rax
0x180014f32  mov     rcx, rsi; string
0x180014f35  mov     qword ptr [rbx+8], 0
0x180014f3d  call    cs:__imp_WindowsGetStringRawBuffer
0x180014f44  nop     dword ptr [rax+rax+00h]
0x180014f49  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180014f50  mov     edx, 80h; unsigned __int64
0x180014f55  mov     r9, rax
0x180014f58  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x180014f5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014f62  mov     esi, eax
0x180014f64  test    eax, eax
0x180014f66  jns     short loc_180014FB1
0x180014f68  mov     rcx, [rsp+168h]; this
0x180014f70  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180014f77  mov     r9d, eax; char *
0x180014f7a  mov     edx, 129h; void *
0x180014f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f84  mov     rcx, [rsp+168h]; this
0x180014f8c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180014f93  mov     r9d, esi; char *
0x180014f96  mov     edx, 156h; void *
0x180014f9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fa0  mov     edx, 1; unsigned int
0x180014fa5  mov     rcx, rbx; this
0x180014fa8  call    ??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)
0x180014fad  mov     eax, esi
0x180014faf  jmp     short loc_18001502F
0x180014fb1  lea     rax, [rbx+8]
0x180014fb5  mov     [rsp+168h+var_130], 0
0x180014fbe  mov     [rsp+168h+var_138], rax
0x180014fc3  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x180014fc8  lea     rax, [rsp+168h+var_130]
0x180014fcd  mov     [rsp+168h+var_128], 1
0x180014fd2  mov     r9d, 20019h; samDesired
0x180014fd8  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x180014fdd  xor     r8d, r8d; ulOptions
0x180014fe0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014fe7  call    cs:__imp_RegOpenKeyExW
0x180014fee  nop     dword ptr [rax+rax+00h]
0x180014ff3  lea     rcx, [rsp+168h+var_138]
0x180014ff8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180014ffd  mov     rdx, rbx
0x180015000  mov     rcx, rdi
0x180015003  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180015008  xor     eax, eax
0x18001500a  jmp     short loc_18001502F
0x18001500c  mov     rcx, [rsp+168h]; this
0x180015014  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001501b  mov     ebx, 8007000Eh
0x180015020  mov     edx, 155h; void *
0x180015025  mov     r9d, ebx; char *
0x180015028  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001502d  mov     eax, ebx
0x18001502f  mov     rcx, [rsp+168h+var_18]
0x180015037  xor     rcx, rsp; StackCookie
0x18001503a  call    __security_check_cookie
0x18001503f  lea     r11, [rsp+168h+var_8]
0x180015047  mov     rbx, [r11+20h]
0x18001504b  mov     rsi, [r11+28h]
0x18001504f  mov     rsp, r11
0x180015052  pop     rdi
0x180015053  retn
```
