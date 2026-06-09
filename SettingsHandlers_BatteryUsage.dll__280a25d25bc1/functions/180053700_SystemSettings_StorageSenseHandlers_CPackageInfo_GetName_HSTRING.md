# SystemSettings::StorageSenseHandlers::CPackageInfo::GetName(HSTRING__ * *)

- ea: `0x180053700`
- end: `0x180053874`
- name: `?GetName@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `372`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004cfc`
- `0x180021504`
- `0x180021534`
- `0x180053700`
- `0x18005387c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053837`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800537ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800537ca`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x1800537d7`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageSid` at `0x1800537d7`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180053843`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x180053843`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180053818`
- `USERENV!__imp_LookupAppContainerDisplayName` at `0x180053818`

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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)PackageFullName;
}

```

## disassembly

```asm
0x180053700  push    rbp
0x180053702  push    rbx
0x180053703  push    rsi
0x180053704  push    rdi
0x180053705  push    r14
0x180053707  mov     rbp, rsp
0x18005370a  sub     rsp, 40h
0x18005370e  mov     rsi, rdx
0x180053711  mov     r14, rcx
0x180053714  mov     [rbp+arg_10], 0
0x18005371c  mov     rdi, [rcx+20h]
0x180053720  mov     rax, [rdi]
0x180053723  mov     rbx, [rax+30h]
0x180053727  lea     rcx, [rbp+arg_10]
0x18005372b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053730  lea     r8, [rbp+arg_10]
0x180053734  xor     edx, edx
0x180053736  mov     rcx, rdi
0x180053739  mov     rax, rbx
0x18005373c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053741  mov     ebx, eax
0x180053743  test    eax, eax
0x180053745  js      loc_18005385E
0x18005374b  mov     [rbp+arg_0], 0
0x180053752  mov     rcx, [r14+20h]
0x180053756  mov     rax, [rcx]
0x180053759  lea     rdx, [rbp+arg_0]
0x18005375d  mov     rax, [rax+38h]
0x180053761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053766  test    eax, eax
0x180053768  js      short loc_18005378A
0x18005376a  cmp     [rbp+arg_0], 1
0x18005376e  jnz     short loc_18005378A
0x180053770  mov     rcx, [rbp+arg_10]
0x180053774  mov     rax, [rcx]
0x180053777  mov     rdx, rsi
0x18005377a  mov     rax, [rax+30h]
0x18005377e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053783  mov     ebx, eax
0x180053785  jmp     loc_18005385E
0x18005378a  mov     rbx, [rbp+arg_10]
0x18005378e  mov     [rbp+string], 0
0x180053796  xor     ecx, ecx; string
0x180053798  call    cs:__imp_WindowsDeleteString
0x18005379e  mov     [rbp+string], 0
0x1800537a6  lea     rdx, [rbp+string]; HSTRING *
0x1800537aa  mov     rcx, rbx; this
0x1800537ad  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x1800537b2  mov     ebx, eax
0x1800537b4  test    eax, eax
0x1800537b6  js      loc_180053853
0x1800537bc  mov     [rbp+var_20], 0
0x1800537c4  xor     edx, edx; length
0x1800537c6  mov     rcx, [rbp+string]; string
0x1800537ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800537d0  lea     rdx, [rbp+var_20]
0x1800537d4  mov     rcx, rax
0x1800537d7  call    cs:__imp_AppXGetPackageSid
0x1800537dd  mov     ebx, eax
0x1800537df  test    eax, eax
0x1800537e1  js      short loc_180053853
0x1800537e3  mov     [rbp+sourceString], 0
0x1800537eb  mov     qword ptr [rbp+length], 0
0x1800537f3  mov     [rbp+var_8], 0
0x1800537fb  lea     rcx, [rbp+sourceString]
0x1800537ff  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053804  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053808  mov     qword ptr [rbp+length], rax
0x18005380c  mov     [rbp+var_8], rax
0x180053810  lea     rdx, [rbp+sourceString]
0x180053814  mov     rcx, [rbp+var_20]
0x180053818  call    cs:__imp_LookupAppContainerDisplayName
0x18005381e  mov     ebx, eax
0x180053820  test    eax, eax
0x180053822  js      short loc_18005383F
0x180053824  lea     rcx, [rbp+sourceString]
0x180053828  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18005382d  mov     r8, rsi; string
0x180053830  mov     edx, [rbp+length]; length
0x180053833  mov     rcx, [rbp+sourceString]; sourceString
0x180053837  call    cs:__imp_WindowsCreateString
0x18005383d  mov     ebx, eax
0x18005383f  mov     rcx, [rbp+var_20]
0x180053843  call    cs:__imp_AppXFreeMemory
0x180053849  lea     rcx, [rbp+sourceString]
0x18005384d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053852  nop
0x180053853  mov     rcx, [rbp+string]; string
0x180053857  call    cs:__imp_WindowsDeleteString
0x18005385d  nop
0x18005385e  lea     rcx, [rbp+arg_10]
0x180053862  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053867  mov     eax, ebx
0x180053869  add     rsp, 40h
0x18005386d  pop     r14
0x18005386f  pop     rdi
0x180053870  pop     rsi
0x180053871  pop     rbx
0x180053872  pop     rbp
0x180053873  retn
```
