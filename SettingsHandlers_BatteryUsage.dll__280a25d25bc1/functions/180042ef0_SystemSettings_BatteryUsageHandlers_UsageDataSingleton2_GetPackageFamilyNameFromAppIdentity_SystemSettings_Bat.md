# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFamilyNameFromAppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity,HSTRING__ * *)

- ea: `0x180042ef0`
- end: `0x18004309d`
- name: `?GetPackageFamilyNameFromAppIdentity@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJUAppIdentity@23@PEAPEAUHSTRING__@@@Z`
- size: `429`
- prototype: `int __high(struct SystemSettings::BatteryUsageHandlers::AppIdentity, HSTRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ce90`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c78`
- `0x18002aab0`
- `0x18003e754`
- `0x180042ef0`
- `0x1800457f0`
- `0x18004719c`
- `0x1800512e0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180043053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180043053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004305f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004305f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043019`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043019`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFamilyNameFromAppIdentity(
        __int64 a1,
        const struct SystemSettings::BatteryUsageHandlers::AppIdentity *a2,
        HSTRING *a3)
{
  const WCHAR *v5; // rax
  HSTRING *v6; // r8
  __int64 v7; // rdx
  HRESULT v8; // ebx
  SystemSettings::BatteryUsageHandlers::AppIdentity *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 PackageFamilyNameFromPackageFullName; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  const WCHAR *v21; // rbx
  __int64 v22; // rdx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v25; // [rsp+28h] [rbp-51h] BYREF
  __int64 v26; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v27[40]; // [rsp+38h] [rbp-41h] BYREF
  const struct SystemSettings::BatteryUsageHandlers::AppIdentity *v28; // [rsp+60h] [rbp-19h]
  _BYTE v29[32]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp+Fh] BYREF

  v28 = a2;
  v25 = 0;
  if ( *((_DWORD *)a2 + 8) == 1 )
  {
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3);
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    v8 = WindowsCreateString(v5, v7, v6);
  }
  else
  {
    v8 = -2147467259;
    if ( !*((_DWORD *)a2 + 8) )
    {
      string = 0;
      v9 = SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(
             (SystemSettings::BatteryUsageHandlers::AppIdentity *)v27,
             a2,
             (__int64)a3);
      v11 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::LookupFriendlyName(v10, v29, v9);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11, v12, v13);
      std::wstring::wstring((__int64)v30, v14);
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        &qword_180079DC0,
        &v26,
        v30);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v29);
      if ( v26 != qword_180079DC0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(&v25, v26 + 64);
        v15 = v25;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 72LL);
        WindowsDeleteString(string);
        string = 0;
        v8 = v16(v15, &string);
        if ( v8 < 0 )
        {
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_13;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        PackageFamilyNameFromPackageFullName = SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(
                                                 v29,
                                                 StringRawBuffer);
        v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                               PackageFamilyNameFromPackageFullName,
                               v19,
                               v20);
        std::wstring::_Tidy_deallocate(v29);
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        v8 = WindowsCreateString(v21, v22, a3);
      }
      WindowsDeleteString(string);
    }
  }
LABEL_13:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  std::wstring::_Tidy_deallocate(a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180042ef0  mov     [rsp-8+arg_0], rbx
0x180042ef5  push    rbp
0x180042ef6  push    rsi
0x180042ef7  push    rdi
0x180042ef8  push    r14
0x180042efa  push    r15
0x180042efc  lea     rbp, [rsp-37h]
0x180042f01  sub     rsp, 0B0h
0x180042f08  mov     rax, cs:__security_cookie
0x180042f0f  xor     rax, rsp
0x180042f12  mov     [rbp+57h+var_28], rax
0x180042f16  mov     r14, r8
0x180042f19  mov     rsi, rdx
0x180042f1c  mov     [rbp+57h+var_70], rdx
0x180042f20  xor     r15d, r15d
0x180042f23  mov     [rbp+57h+var_A8], r15
0x180042f27  cmp     dword ptr [rdx+20h], 1
0x180042f2b  jnz     short loc_180042F53
0x180042f2d  mov     rcx, rdx
0x180042f30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042f35  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180042f39  inc     rdx; length
0x180042f3c  cmp     [rax+rdx*2], r15w
0x180042f41  jnz     short loc_180042F39
0x180042f43  mov     rcx, rax; sourceString
0x180042f46  call    cs:__imp_WindowsCreateString
0x180042f4c  mov     ebx, eax
0x180042f4e  jmp     loc_180043066
0x180042f53  mov     ebx, 80004005h
0x180042f58  cmp     [rdx+20h], r15d
0x180042f5c  jnz     loc_180043066
0x180042f62  mov     [rbp+57h+string], r15
0x180042f66  lea     rcx, [rbp+57h+var_98]; this
0x180042f6a  call    ??0AppIdentity@BatteryUsageHandlers@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180042f6f  mov     r8, rax
0x180042f72  lea     rdx, [rbp+57h+var_68]
0x180042f76  call    ?LookupFriendlyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppIdentity@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::LookupFriendlyName(SystemSettings::BatteryUsageHandlers::AppIdentity)
0x180042f7b  nop
0x180042f7c  mov     rcx, rax
0x180042f7f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042f84  mov     rdx, rax
0x180042f87  lea     rcx, [rbp+57h+var_48]
0x180042f8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042f90  lea     r8, [rbp+57h+var_48]
0x180042f94  lea     rdx, [rbp+57h+var_A0]
0x180042f98  lea     rcx, qword_180079DC0
0x180042f9f  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180042fa4  lea     rcx, [rbp+57h+var_48]
0x180042fa8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042fad  nop
0x180042fae  lea     rcx, [rbp+57h+var_68]
0x180042fb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042fb7  mov     rdx, [rbp+57h+var_A0]
0x180042fbb  cmp     rdx, cs:qword_180079DC0
0x180042fc2  jz      loc_18004305B
0x180042fc8  add     rdx, 40h ; '@'
0x180042fcc  lea     rcx, [rbp+57h+var_A8]
0x180042fd0  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x180042fd5  mov     rdi, [rbp+57h+var_A8]
0x180042fd9  mov     rax, [rdi]
0x180042fdc  mov     rbx, [rax+48h]
0x180042fe0  mov     rcx, [rbp+57h+string]; string
0x180042fe4  call    cs:__imp_WindowsDeleteString
0x180042fea  mov     [rbp+57h+string], r15
0x180042fee  lea     rdx, [rbp+57h+string]
0x180042ff2  mov     rcx, rdi
0x180042ff5  mov     rax, rbx
0x180042ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ffd  mov     ebx, eax
0x180042fff  test    eax, eax
0x180043001  jns     short loc_180043013
0x180043003  mov     rcx, [rbp+57h+string]; string
0x180043007  call    cs:__imp_WindowsDeleteString
0x18004300d  mov     [rbp+57h+string], r15
0x180043011  jmp     short loc_180043066
0x180043013  xor     edx, edx; length
0x180043015  mov     rcx, [rbp+57h+string]; string
0x180043019  call    cs:__imp_WindowsGetStringRawBuffer
0x18004301f  mov     rdx, rax
0x180043022  lea     rcx, [rbp+57h+var_68]
0x180043026  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x18004302b  mov     rcx, rax
0x18004302e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043033  mov     rbx, rax
0x180043036  lea     rcx, [rbp+57h+var_68]
0x18004303a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004303f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043043  inc     rdx; length
0x180043046  cmp     [rbx+rdx*2], r15w
0x18004304b  jnz     short loc_180043043
0x18004304d  mov     r8, r14; string
0x180043050  mov     rcx, rbx; sourceString
0x180043053  call    cs:__imp_WindowsCreateString
0x180043059  mov     ebx, eax
0x18004305b  mov     rcx, [rbp+57h+string]; string
0x18004305f  call    cs:__imp_WindowsDeleteString
0x180043065  nop
0x180043066  lea     rcx, [rbp+57h+var_A8]
0x18004306a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004306f  nop
0x180043070  mov     rcx, rsi
0x180043073  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043078  mov     eax, ebx
0x18004307a  mov     rcx, [rbp+57h+var_28]
0x18004307e  xor     rcx, rsp; StackCookie
0x180043081  call    __security_check_cookie
0x180043086  mov     rbx, [rsp+0D0h+arg_0]
0x18004308e  add     rsp, 0B0h
0x180043095  pop     r15
0x180043097  pop     r14
0x180043099  pop     rdi
0x18004309a  pop     rsi
0x18004309b  pop     rbp
0x18004309c  retn
```
