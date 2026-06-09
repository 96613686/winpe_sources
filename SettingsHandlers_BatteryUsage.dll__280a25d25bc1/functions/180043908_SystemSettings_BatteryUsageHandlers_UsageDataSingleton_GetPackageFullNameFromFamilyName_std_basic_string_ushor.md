# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180043908`
- end: `0x180043a97`
- name: `?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z`
- size: `399`
- prototype: ``
- caller_count: `7`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ed98`
- `0x18004aab0`
- `0x18004b580`
- `0x18004b824`
- `0x18004b8fc`
- `0x18004b9f0`
- `0x18004bcb0`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18001503c`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180023c78`
- `0x180036598`
- `0x18003d550`
- `0x18003e7a4`
- `0x1800434e4`
- `0x180043908`
- `0x18004719c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800439c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800439c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043a04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043a04`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r15
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int PackageFromFamilyName; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v16; // rax
  __int64 v18; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string[2]; // [rsp+28h] [rbp-58h] BYREF
  char v20[16]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h]
  _BYTE v22[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v18 = a2;
  v21 = a3;
  v6 = (_QWORD *)(a1 + 408);
  std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    a1 + 408,
    &v18,
    a3);
  if ( v18 == *v6 )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v8, v9);
    PackageFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(
                              a1,
                              v10,
                              (__int64)&v18);
    if ( PackageFromFamilyName < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x407,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)PackageFromFamilyName,
        v18);
    string[0] = 0;
    v12 = v18;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 112LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v14 = v13(v12, string);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x409,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v14,
        v18);
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    std::wstring::wstring((__int64)v22, (__int64)StringRawBuffer);
    v16 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(v6, v20, a3);
    std::wstring::operator=(*v16 + 64LL, v22);
    std::wstring::wstring(a2, v22);
    std::wstring::_Tidy_deallocate(v22);
    WindowsDeleteString(string[0]);
    string[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  }
  else
  {
    std::wstring::wstring(a2, v18 + 64, v7);
  }
  std::wstring::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x180043908  mov     [rsp-28h+arg_18], rbx
0x18004390d  push    rbp
0x18004390e  push    rsi
0x18004390f  push    rdi
0x180043910  push    r14
0x180043912  push    r15
0x180043914  mov     rbp, rsp
0x180043917  sub     rsp, 80h
0x18004391e  mov     rax, cs:__security_cookie
0x180043925  xor     rax, rsp
0x180043928  mov     [rbp+var_10], rax
0x18004392c  mov     rsi, r8
0x18004392f  mov     r14, rdx
0x180043932  mov     rbx, rcx
0x180043935  mov     [rbp+var_60], rdx
0x180043939  mov     [rbp+var_38], r8
0x18004393d  lea     r15, [rcx+198h]
0x180043944  lea     rdx, [rbp+var_60]
0x180043948  mov     rcx, r15
0x18004394b  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180043950  mov     rdx, [rbp+var_60]
0x180043954  cmp     rdx, [r15]
0x180043957  jz      short loc_18004396A
0x180043959  add     rdx, 40h ; '@'
0x18004395d  mov     rcx, r14
0x180043960  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180043965  jmp     loc_180043A69
0x18004396a  mov     [rbp+var_60], 0
0x180043972  lea     rcx, [rbp+var_60]
0x180043976  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004397b  mov     rcx, rsi
0x18004397e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043983  lea     r8, [rbp+var_60]
0x180043987  mov     rdx, rax
0x18004398a  mov     rcx, rbx
0x18004398d  call    ?GetPackageFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x180043992  mov     rcx, [rbp+28h]; this
0x180043996  test    eax, eax
0x180043998  jns     short loc_1800439AF
0x18004399a  mov     r9d, eax; char *
0x18004399d  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800439a4  mov     edx, 407h; void *
0x1800439a9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800439af  mov     [rbp+string], 0
0x1800439b7  mov     rdi, [rbp+var_60]
0x1800439bb  mov     rax, [rdi]
0x1800439be  mov     rbx, [rax+70h]
0x1800439c2  xor     ecx, ecx; string
0x1800439c4  call    cs:__imp_WindowsDeleteString
0x1800439ca  mov     [rbp+string], 0
0x1800439d2  lea     rdx, [rbp+string]
0x1800439d6  mov     rcx, rdi
0x1800439d9  mov     rax, rbx
0x1800439dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439e1  mov     rcx, [rbp+28h]; this
0x1800439e5  test    eax, eax
0x1800439e7  jns     short loc_1800439FE
0x1800439e9  mov     r9d, eax; char *
0x1800439ec  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800439f3  mov     edx, 409h; void *
0x1800439f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800439fe  xor     edx, edx; length
0x180043a00  mov     rcx, [rbp+string]; string
0x180043a04  call    cs:__imp_WindowsGetStringRawBuffer
0x180043a0a  mov     rdx, rax
0x180043a0d  lea     rcx, [rbp+var_30]
0x180043a11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043a16  nop
0x180043a17  mov     r8, rsi
0x180043a1a  lea     rdx, [rbp+var_48]
0x180043a1e  mov     rcx, r15
0x180043a21  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180043a26  mov     rcx, [rax]
0x180043a29  add     rcx, 40h ; '@'
0x180043a2d  lea     rdx, [rbp+var_30]
0x180043a31  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180043a36  lea     rdx, [rbp+var_30]
0x180043a3a  mov     rcx, r14
0x180043a3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180043a42  nop
0x180043a43  lea     rcx, [rbp+var_30]
0x180043a47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043a4c  nop
0x180043a4d  mov     rcx, [rbp+string]; string
0x180043a51  call    cs:__imp_WindowsDeleteString
0x180043a57  mov     [rbp+string], 0
0x180043a5f  lea     rcx, [rbp+var_60]
0x180043a63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043a68  nop
0x180043a69  mov     rcx, rsi
0x180043a6c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043a71  mov     rax, r14
0x180043a74  mov     rcx, [rbp+var_10]
0x180043a78  xor     rcx, rsp; StackCookie
0x180043a7b  call    __security_check_cookie
0x180043a80  mov     rbx, [rsp+80h+arg_18]
0x180043a88  add     rsp, 80h
0x180043a8f  pop     r15
0x180043a91  pop     r14
0x180043a93  pop     rdi
0x180043a94  pop     rsi
0x180043a95  pop     rbp
0x180043a96  retn
```
