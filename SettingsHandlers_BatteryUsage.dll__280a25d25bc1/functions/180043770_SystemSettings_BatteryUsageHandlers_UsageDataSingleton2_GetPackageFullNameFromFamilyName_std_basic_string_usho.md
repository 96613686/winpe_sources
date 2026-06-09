# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180043770`
- end: `0x1800438ff`
- name: `?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z`
- size: `399`
- prototype: ``
- caller_count: `7`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ea14`
- `0x18004ce90`
- `0x18004ddc0`
- `0x18004e044`
- `0x18004e11c`
- `0x18004e210`
- `0x18004e2b0`

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
- `0x180043258`
- `0x180043770`
- `0x18004719c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004382c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004382c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800438b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004386c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004386c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
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
  v6 = (_QWORD *)(a1 + 400);
  std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    a1 + 400,
    &v18,
    a3);
  if ( v18 == *v6 )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v8, v9);
    PackageFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(
                              a1,
                              v10,
                              (__int64)&v18);
    if ( PackageFromFamilyName < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9C5,
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
        (void *)0x9C7,
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
0x180043770  mov     [rsp-28h+arg_18], rbx
0x180043775  push    rbp
0x180043776  push    rsi
0x180043777  push    rdi
0x180043778  push    r14
0x18004377a  push    r15
0x18004377c  mov     rbp, rsp
0x18004377f  sub     rsp, 80h
0x180043786  mov     rax, cs:__security_cookie
0x18004378d  xor     rax, rsp
0x180043790  mov     [rbp+var_10], rax
0x180043794  mov     rsi, r8
0x180043797  mov     r14, rdx
0x18004379a  mov     rbx, rcx
0x18004379d  mov     [rbp+var_60], rdx
0x1800437a1  mov     [rbp+var_38], r8
0x1800437a5  lea     r15, [rcx+190h]
0x1800437ac  lea     rdx, [rbp+var_60]
0x1800437b0  mov     rcx, r15
0x1800437b3  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800437b8  mov     rdx, [rbp+var_60]
0x1800437bc  cmp     rdx, [r15]
0x1800437bf  jz      short loc_1800437D2
0x1800437c1  add     rdx, 40h ; '@'
0x1800437c5  mov     rcx, r14
0x1800437c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800437cd  jmp     loc_1800438D1
0x1800437d2  mov     [rbp+var_60], 0
0x1800437da  lea     rcx, [rbp+var_60]
0x1800437de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800437e3  mov     rcx, rsi
0x1800437e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800437eb  lea     r8, [rbp+var_60]
0x1800437ef  mov     rdx, rax
0x1800437f2  mov     rcx, rbx
0x1800437f5  call    ?GetPackageFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x1800437fa  mov     rcx, [rbp+28h]; this
0x1800437fe  test    eax, eax
0x180043800  jns     short loc_180043817
0x180043802  mov     r9d, eax; char *
0x180043805  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004380c  mov     edx, 9C5h; void *
0x180043811  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180043817  mov     [rbp+string], 0
0x18004381f  mov     rdi, [rbp+var_60]
0x180043823  mov     rax, [rdi]
0x180043826  mov     rbx, [rax+70h]
0x18004382a  xor     ecx, ecx; string
0x18004382c  call    cs:__imp_WindowsDeleteString
0x180043832  mov     [rbp+string], 0
0x18004383a  lea     rdx, [rbp+string]
0x18004383e  mov     rcx, rdi
0x180043841  mov     rax, rbx
0x180043844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043849  mov     rcx, [rbp+28h]; this
0x18004384d  test    eax, eax
0x18004384f  jns     short loc_180043866
0x180043851  mov     r9d, eax; char *
0x180043854  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004385b  mov     edx, 9C7h; void *
0x180043860  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180043866  xor     edx, edx; length
0x180043868  mov     rcx, [rbp+string]; string
0x18004386c  call    cs:__imp_WindowsGetStringRawBuffer
0x180043872  mov     rdx, rax
0x180043875  lea     rcx, [rbp+var_30]
0x180043879  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004387e  nop
0x18004387f  mov     r8, rsi
0x180043882  lea     rdx, [rbp+var_48]
0x180043886  mov     rcx, r15
0x180043889  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18004388e  mov     rcx, [rax]
0x180043891  add     rcx, 40h ; '@'
0x180043895  lea     rdx, [rbp+var_30]
0x180043899  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004389e  lea     rdx, [rbp+var_30]
0x1800438a2  mov     rcx, r14
0x1800438a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800438aa  nop
0x1800438ab  lea     rcx, [rbp+var_30]
0x1800438af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800438b4  nop
0x1800438b5  mov     rcx, [rbp+string]; string
0x1800438b9  call    cs:__imp_WindowsDeleteString
0x1800438bf  mov     [rbp+string], 0
0x1800438c7  lea     rcx, [rbp+var_60]
0x1800438cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800438d0  nop
0x1800438d1  mov     rcx, rsi
0x1800438d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800438d9  mov     rax, r14
0x1800438dc  mov     rcx, [rbp+var_10]
0x1800438e0  xor     rcx, rsp; StackCookie
0x1800438e3  call    __security_check_cookie
0x1800438e8  mov     rbx, [rsp+80h+arg_18]
0x1800438f0  add     rsp, 80h
0x1800438f7  pop     r15
0x1800438f9  pop     r14
0x1800438fb  pop     rdi
0x1800438fc  pop     rsi
0x1800438fd  pop     rbp
0x1800438fe  retn
```
