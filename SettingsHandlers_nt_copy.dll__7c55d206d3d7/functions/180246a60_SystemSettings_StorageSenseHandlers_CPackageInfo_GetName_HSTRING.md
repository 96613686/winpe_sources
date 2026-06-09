# SystemSettings::StorageSenseHandlers::CPackageInfo::GetName(HSTRING__ * *)

- ea: `0x180246a60`
- end: `0x180246c03`
- name: `?GetName@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `419`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180011bb0`
- `0x18005016c`
- `0x18005019c`
- `0x180246a60`
- `0x180246fac`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180246b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180246b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180246bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180246bb3`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x180246b43`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x180246b43`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180246bc5`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180246bc5`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180246b8e`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180246b8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageInfo::GetName(
        SystemSettings::StorageSenseHandlers::CPackageInfo *this,
        HSTRING *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, SystemSettings::StorageSenseHandlers::CAppInfo **); // rbx
  HRESULT PackageFullName; // ebx
  SystemSettings::StorageSenseHandlers::CAppInfo *v7; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // [rsp+20h] [rbp-20h] BYREF
  PCNZWCH sourceString; // [rsp+28h] [rbp-18h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-10h]
  __int64 v13; // [rsp+38h] [rbp-8h]
  int v14; // [rsp+70h] [rbp+30h] BYREF
  SystemSettings::StorageSenseHandlers::CAppInfo *v15; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  v4 = *((_QWORD *)this + 4);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, SystemSettings::StorageSenseHandlers::CAppInfo **))(*(_QWORD *)v4 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  PackageFullName = v5(v4, 0, &v15);
  if ( PackageFullName >= 0 )
  {
    v14 = 0;
    if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4), &v14) >= 0
      && v14 == 1 )
    {
      PackageFullName = (*(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppInfo *, HSTRING *))(*(_QWORD *)v15 + 48LL))(
                          v15,
                          a2);
    }
    else
    {
      v7 = v15;
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(v7, &string);
      if ( PackageFullName >= 0 )
      {
        v10 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        PackageFullName = AppXGetPackageSid(StringRawBuffer, &v10);
        if ( PackageFullName >= 0 )
        {
          sourceString = 0;
          *(_QWORD *)length = 0;
          v13 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
          *(_QWORD *)length = -1;
          v13 = -1;
          PackageFullName = LookupAppContainerDisplayName(v10, &sourceString);
          if ( PackageFullName >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
            PackageFullName = WindowsCreateString(sourceString, length[0], a2);
          }
          AppXFreeMemory(v10);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
        }
      }
      WindowsDeleteString(string);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  return (unsigned int)PackageFullName;
}

```

## disassembly

```asm
0x180246a60  push    rbp
0x180246a62  push    rbx
0x180246a63  push    rsi
0x180246a64  push    rdi
0x180246a65  push    r14
0x180246a67  mov     rbp, rsp
0x180246a6a  sub     rsp, 40h
0x180246a6e  mov     rsi, rdx
0x180246a71  mov     r14, rcx
0x180246a74  mov     [rbp+arg_10], 0
0x180246a7c  mov     rdi, [rcx+20h]
0x180246a80  mov     rax, [rdi]
0x180246a83  mov     rbx, [rax+30h]
0x180246a87  lea     rcx, [rbp+arg_10]
0x180246a8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246a90  lea     r8, [rbp+arg_10]
0x180246a94  xor     edx, edx
0x180246a96  mov     rcx, rdi
0x180246a99  mov     rax, rbx
0x180246a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246aa1  mov     ebx, eax
0x180246aa3  test    eax, eax
0x180246aa5  js      loc_180246BEC
0x180246aab  mov     [rbp+arg_0], 0
0x180246ab2  mov     rcx, [r14+20h]
0x180246ab6  mov     rax, [rcx]
0x180246ab9  lea     rdx, [rbp+arg_0]
0x180246abd  mov     rax, [rax+38h]
0x180246ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246ac6  test    eax, eax
0x180246ac8  js      short loc_180246AEA
0x180246aca  cmp     [rbp+arg_0], 1
0x180246ace  jnz     short loc_180246AEA
0x180246ad0  mov     rcx, [rbp+arg_10]
0x180246ad4  mov     rax, [rcx]
0x180246ad7  mov     rdx, rsi
0x180246ada  mov     rax, [rax+30h]
0x180246ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246ae3  mov     ebx, eax
0x180246ae5  jmp     loc_180246BEC
0x180246aea  mov     rbx, [rbp+arg_10]
0x180246aee  mov     [rbp+string], 0
0x180246af6  xor     ecx, ecx; string
0x180246af8  call    cs:__imp_WindowsDeleteString
0x180246aff  nop     dword ptr [rax+rax+00h]
0x180246b04  mov     [rbp+string], 0
0x180246b0c  lea     rdx, [rbp+string]; HSTRING *
0x180246b10  mov     rcx, rbx; this
0x180246b13  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x180246b18  mov     ebx, eax
0x180246b1a  test    eax, eax
0x180246b1c  js      loc_180246BDB
0x180246b22  mov     [rbp+var_20], 0
0x180246b2a  xor     edx, edx; length
0x180246b2c  mov     rcx, [rbp+string]; string
0x180246b30  call    cs:__imp_WindowsGetStringRawBuffer
0x180246b37  nop     dword ptr [rax+rax+00h]
0x180246b3c  lea     rdx, [rbp+var_20]
0x180246b40  mov     rcx, rax
0x180246b43  call    cs:__imp_AppXGetPackageSid
0x180246b4a  nop     dword ptr [rax+rax+00h]
0x180246b4f  mov     ebx, eax
0x180246b51  test    eax, eax
0x180246b53  js      loc_180246BDB
0x180246b59  mov     [rbp+sourceString], 0
0x180246b61  mov     qword ptr [rbp+length], 0
0x180246b69  mov     [rbp+var_8], 0
0x180246b71  lea     rcx, [rbp+sourceString]
0x180246b75  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180246b7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180246b7e  mov     qword ptr [rbp+length], rax
0x180246b82  mov     [rbp+var_8], rax
0x180246b86  lea     rdx, [rbp+sourceString]
0x180246b8a  mov     rcx, [rbp+var_20]
0x180246b8e  call    cs:__imp_LookupAppContainerDisplayName
0x180246b95  nop     dword ptr [rax+rax+00h]
0x180246b9a  mov     ebx, eax
0x180246b9c  test    eax, eax
0x180246b9e  js      short loc_180246BC1
0x180246ba0  lea     rcx, [rbp+sourceString]
0x180246ba4  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180246ba9  mov     r8, rsi; string
0x180246bac  mov     edx, [rbp+length]; length
0x180246baf  mov     rcx, [rbp+sourceString]; sourceString
0x180246bb3  call    cs:__imp_WindowsCreateString
0x180246bba  nop     dword ptr [rax+rax+00h]
0x180246bbf  mov     ebx, eax
0x180246bc1  mov     rcx, [rbp+var_20]
0x180246bc5  call    cs:__imp_AppXFreeMemory
0x180246bcc  nop     dword ptr [rax+rax+00h]
0x180246bd1  lea     rcx, [rbp+sourceString]
0x180246bd5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180246bda  nop
0x180246bdb  mov     rcx, [rbp+string]; string
0x180246bdf  call    cs:__imp_WindowsDeleteString
0x180246be6  nop     dword ptr [rax+rax+00h]
0x180246beb  nop
0x180246bec  lea     rcx, [rbp+arg_10]
0x180246bf0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246bf5  mov     eax, ebx
0x180246bf7  add     rsp, 40h
0x180246bfb  pop     r14
0x180246bfd  pop     rdi
0x180246bfe  pop     rsi
0x180246bff  pop     rbx
0x180246c00  pop     rbp
0x180246c01  retn
```
