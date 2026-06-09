# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFamilyNameFromAppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity,HSTRING__ * *)

- ea: `0x1800430a4`
- end: `0x180043251`
- name: `?GetPackageFamilyNameFromAppIdentity@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJUAppIdentity@23@PEAPEAUHSTRING__@@@Z`
- size: `429`
- prototype: `int __high(struct SystemSettings::BatteryUsageHandlers::AppIdentity, HSTRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004aab0`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c78`
- `0x18002aab0`
- `0x18003e754`
- `0x1800430a4`
- `0x180045954`
- `0x18004719c`
- `0x1800512e0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800430fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180043207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800430fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180043207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800431bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800431bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431cd`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFamilyNameFromAppIdentity(
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
      v11 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::LookupFriendlyName(v10, v29, v9);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11, v12, v13);
      std::wstring::wstring((__int64)v30, v14);
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        &qword_180079B90,
        &v26,
        v30);
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v29);
      if ( v26 != qword_180079B90 )
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
0x1800430a4  mov     [rsp-8+arg_0], rbx
0x1800430a9  push    rbp
0x1800430aa  push    rsi
0x1800430ab  push    rdi
0x1800430ac  push    r14
0x1800430ae  push    r15
0x1800430b0  lea     rbp, [rsp-37h]
0x1800430b5  sub     rsp, 0B0h
0x1800430bc  mov     rax, cs:__security_cookie
0x1800430c3  xor     rax, rsp
0x1800430c6  mov     [rbp+57h+var_28], rax
0x1800430ca  mov     r14, r8
0x1800430cd  mov     rsi, rdx
0x1800430d0  mov     [rbp+57h+var_70], rdx
0x1800430d4  xor     r15d, r15d
0x1800430d7  mov     [rbp+57h+var_A8], r15
0x1800430db  cmp     dword ptr [rdx+20h], 1
0x1800430df  jnz     short loc_180043107
0x1800430e1  mov     rcx, rdx
0x1800430e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800430e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800430ed  inc     rdx; length
0x1800430f0  cmp     [rax+rdx*2], r15w
0x1800430f5  jnz     short loc_1800430ED
0x1800430f7  mov     rcx, rax; sourceString
0x1800430fa  call    cs:__imp_WindowsCreateString
0x180043100  mov     ebx, eax
0x180043102  jmp     loc_18004321A
0x180043107  mov     ebx, 80004005h
0x18004310c  cmp     [rdx+20h], r15d
0x180043110  jnz     loc_18004321A
0x180043116  mov     [rbp+57h+string], r15
0x18004311a  lea     rcx, [rbp+57h+var_98]; this
0x18004311e  call    ??0AppIdentity@BatteryUsageHandlers@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180043123  mov     r8, rax
0x180043126  lea     rdx, [rbp+57h+var_68]
0x18004312a  call    ?LookupFriendlyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppIdentity@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::LookupFriendlyName(SystemSettings::BatteryUsageHandlers::AppIdentity)
0x18004312f  nop
0x180043130  mov     rcx, rax
0x180043133  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043138  mov     rdx, rax
0x18004313b  lea     rcx, [rbp+57h+var_48]
0x18004313f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043144  lea     r8, [rbp+57h+var_48]
0x180043148  lea     rdx, [rbp+57h+var_A0]
0x18004314c  lea     rcx, qword_180079B90
0x180043153  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180043158  lea     rcx, [rbp+57h+var_48]
0x18004315c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043161  nop
0x180043162  lea     rcx, [rbp+57h+var_68]
0x180043166  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004316b  mov     rdx, [rbp+57h+var_A0]
0x18004316f  cmp     rdx, cs:qword_180079B90
0x180043176  jz      loc_18004320F
0x18004317c  add     rdx, 40h ; '@'
0x180043180  lea     rcx, [rbp+57h+var_A8]
0x180043184  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x180043189  mov     rdi, [rbp+57h+var_A8]
0x18004318d  mov     rax, [rdi]
0x180043190  mov     rbx, [rax+48h]
0x180043194  mov     rcx, [rbp+57h+string]; string
0x180043198  call    cs:__imp_WindowsDeleteString
0x18004319e  mov     [rbp+57h+string], r15
0x1800431a2  lea     rdx, [rbp+57h+string]
0x1800431a6  mov     rcx, rdi
0x1800431a9  mov     rax, rbx
0x1800431ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431b1  mov     ebx, eax
0x1800431b3  test    eax, eax
0x1800431b5  jns     short loc_1800431C7
0x1800431b7  mov     rcx, [rbp+57h+string]; string
0x1800431bb  call    cs:__imp_WindowsDeleteString
0x1800431c1  mov     [rbp+57h+string], r15
0x1800431c5  jmp     short loc_18004321A
0x1800431c7  xor     edx, edx; length
0x1800431c9  mov     rcx, [rbp+57h+string]; string
0x1800431cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800431d3  mov     rdx, rax
0x1800431d6  lea     rcx, [rbp+57h+var_68]
0x1800431da  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x1800431df  mov     rcx, rax
0x1800431e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800431e7  mov     rbx, rax
0x1800431ea  lea     rcx, [rbp+57h+var_68]
0x1800431ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800431f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800431f7  inc     rdx; length
0x1800431fa  cmp     [rbx+rdx*2], r15w
0x1800431ff  jnz     short loc_1800431F7
0x180043201  mov     r8, r14; string
0x180043204  mov     rcx, rbx; sourceString
0x180043207  call    cs:__imp_WindowsCreateString
0x18004320d  mov     ebx, eax
0x18004320f  mov     rcx, [rbp+57h+string]; string
0x180043213  call    cs:__imp_WindowsDeleteString
0x180043219  nop
0x18004321a  lea     rcx, [rbp+57h+var_A8]
0x18004321e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043223  nop
0x180043224  mov     rcx, rsi
0x180043227  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004322c  mov     eax, ebx
0x18004322e  mov     rcx, [rbp+57h+var_28]
0x180043232  xor     rcx, rsp; StackCookie
0x180043235  call    __security_check_cookie
0x18004323a  mov     rbx, [rsp+0D0h+arg_0]
0x180043242  add     rsp, 0B0h
0x180043249  pop     r15
0x18004324b  pop     r14
0x18004324d  pop     rdi
0x18004324e  pop     rsi
0x18004324f  pop     rbp
0x180043250  retn
```
