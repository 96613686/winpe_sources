# SystemSettings::StorageSenseHandlers::UserFileRemovalRecommender::GetScanPaths(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180075410`
- end: `0x18007565a`
- name: `?GetScanPaths@UserFileRemovalRecommender@StorageSenseHandlers@SystemSettings@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `586`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180012374`
- `0x180016ef4`
- `0x180023928`
- `0x18005c60c`
- `0x180075410`
- `0x18007a96c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007548b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007548b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180075533`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180075533`

## string_xrefs

- `0x18007549f`: `CleanupRecommendations`
- `0x180075547`: `CleanupRecommendations`
- `0x1800754ba`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180075562`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::UserFileRemovalRecommender::GetScanPaths(
        __int64 a1,
        __int64 a2)
{
  HRESULT v4; // edi
  const KNOWNFOLDERID *v6; // rsi
  const KNOWNFOLDERID *v7; // r14
  HRESULT v8; // ebx
  LPVOID v9; // rdi
  unsigned int (__fastcall *v10)(LPVOID, PWSTR, __int64 *, _QWORD, _QWORD); // rbx
  LPVOID ppv; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-58h] BYREF
  __int64 v14; // [rsp+48h] [rbp-50h]
  __int64 v15; // [rsp+50h] [rbp-48h]
  _BYTE v16[32]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  ppszPath = 0;
  v14 = 0;
  v15 = 0;
  ppv = 0;
  v12 = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
  v4 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
  if ( v4 >= 0 )
  {
    v6 = *(const KNOWNFOLDERID **)(a1 + 240);
    v7 = *(const KNOWNFOLDERID **)(a1 + 248);
    while ( v6 != v7 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
      v14 = -1;
      v15 = -1;
      v8 = SHGetKnownFolderPath(v6, 0, 0, &ppszPath);
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
          (const char *)(unsigned int)v8,
          (int)"%hs",
          "CleanupRecommendations");
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v12);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
        return (unsigned int)v8;
      }
      v9 = ppv;
      v10 = *(unsigned int (__fastcall **)(LPVOID, PWSTR, __int64 *, _QWORD, _QWORD))(*(_QWORD *)ppv + 32LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v12);
      if ( v10(v9, ppszPath, &v12, 0, 0) == -2147023728 )
      {
        std::wstring::wstring(v16, ppszPath);
        std::vector<std::wstring>::push_back(a2, v16);
        std::wstring::_Tidy_deallocate(v16);
      }
      ++v6;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)v4,
      (int)"%hs",
      "CleanupRecommendations");
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180075410  mov     r11, rsp
0x180075413  mov     [r11+18h], rbx
0x180075417  mov     [r11+20h], rsi
0x18007541b  push    rdi
0x18007541c  push    r14
0x18007541e  push    r15
0x180075420  sub     rsp, 80h
0x180075427  mov     rax, cs:__security_cookie
0x18007542e  xor     rax, rsp
0x180075431  mov     [rsp+98h+var_20], rax
0x180075436  mov     r15, rdx
0x180075439  mov     rbx, rcx
0x18007543c  mov     qword ptr [r11-58h], 0
0x180075444  mov     qword ptr [r11-50h], 0
0x18007544c  mov     qword ptr [r11-48h], 0
0x180075454  mov     qword ptr [r11-68h], 0
0x18007545c  mov     qword ptr [r11-60h], 0
0x180075464  lea     rcx, [r11-68h]
0x180075468  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007546d  lea     rax, [rsp+98h+var_68]
0x180075472  mov     [rsp+98h+ppv], rax; ppv
0x180075477  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18007547e  xor     edx, edx; pUnkOuter
0x180075480  lea     r8d, [rdx+1]; dwClsContext
0x180075484  lea     rcx, CLSID_SyncRootManager; rclsid
0x18007548b  call    cs:__imp_CoCreateInstance
0x180075491  mov     edi, eax
0x180075493  test    eax, eax
0x180075495  jns     short loc_1800754F3
0x180075497  mov     rcx, [rsp+98h]; this
0x18007549f  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800754a6  mov     [rsp+98h+var_70], rax; char *
0x1800754ab  lea     rax, aHs; "%hs"
0x1800754b2  mov     [rsp+98h+ppv], rax; int
0x1800754b7  mov     r9d, edi; char *
0x1800754ba  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x1800754c1  mov     edx, 15Ch; void *
0x1800754c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800754cb  nop
0x1800754cc  lea     rcx, [rsp+98h+var_60]
0x1800754d1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800754d6  nop
0x1800754d7  lea     rcx, [rsp+98h+var_68]
0x1800754dc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800754e1  nop
0x1800754e2  lea     rcx, [rsp+98h+ppszPath]
0x1800754e7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800754ec  mov     eax, edi
0x1800754ee  jmp     loc_180075633
0x1800754f3  mov     rsi, [rbx+0F0h]
0x1800754fa  mov     r14, [rbx+0F8h]
0x180075501  cmp     rsi, r14
0x180075504  jz      loc_18007560A
0x18007550a  lea     rcx, [rsp+98h+ppszPath]
0x18007550f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075514  mov     [rsp+98h+var_50], 0FFFFFFFFFFFFFFFFh
0x18007551d  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFFh
0x180075526  lea     r9, [rsp+98h+ppszPath]; ppszPath
0x18007552b  xor     r8d, r8d; hToken
0x18007552e  xor     edx, edx; dwFlags
0x180075530  mov     rcx, rsi; rfid
0x180075533  call    cs:__imp_SHGetKnownFolderPath
0x180075539  mov     ebx, eax
0x18007553b  test    eax, eax
0x18007553d  jns     short loc_18007559B
0x18007553f  mov     rcx, [rsp+98h]; this
0x180075547  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x18007554e  mov     [rsp+98h+var_70], rax; char *
0x180075553  lea     rax, aHs; "%hs"
0x18007555a  mov     [rsp+98h+ppv], rax; int
0x18007555f  mov     r9d, ebx; char *
0x180075562  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180075569  mov     edx, 160h; void *
0x18007556e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075573  nop
0x180075574  lea     rcx, [rsp+98h+var_60]
0x180075579  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007557e  nop
0x18007557f  lea     rcx, [rsp+98h+var_68]
0x180075584  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075589  nop
0x18007558a  lea     rcx, [rsp+98h+ppszPath]
0x18007558f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075594  mov     eax, ebx
0x180075596  jmp     loc_180075633
0x18007559b  mov     rdi, [rsp+98h+var_68]
0x1800755a0  mov     rax, [rdi]
0x1800755a3  mov     rbx, [rax+20h]
0x1800755a7  lea     rcx, [rsp+98h+var_60]
0x1800755ac  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800755b1  mov     [rsp+98h+ppv], 0
0x1800755ba  xor     r9d, r9d
0x1800755bd  lea     r8, [rsp+98h+var_60]
0x1800755c2  mov     rdx, [rsp+98h+ppszPath]
0x1800755c7  mov     rcx, rdi
0x1800755ca  mov     rax, rbx
0x1800755cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800755d2  cmp     eax, 80070490h
0x1800755d7  jnz     short loc_180075601
0x1800755d9  mov     rdx, [rsp+98h+ppszPath]
0x1800755de  lea     rcx, [rsp+98h+var_40]
0x1800755e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800755e8  nop
0x1800755e9  lea     rdx, [rsp+98h+var_40]
0x1800755ee  mov     rcx, r15
0x1800755f1  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800755f6  nop
0x1800755f7  lea     rcx, [rsp+98h+var_40]
0x1800755fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075601  add     rsi, 10h
0x180075605  jmp     loc_180075501
0x18007560a  lea     rcx, [rsp+98h+var_60]
0x18007560f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075614  nop
0x180075615  lea     rcx, [rsp+98h+var_68]
0x18007561a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18007561f  nop
0x180075620  lea     rcx, [rsp+98h+ppszPath]
0x180075625  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007562a  nop
0x18007562b  xor     eax, eax
0x18007562d  jmp     short loc_180075633
0x18007562f  mov     eax, dword ptr [rsp+98h+var_68]
0x180075633  mov     rcx, [rsp+98h+var_20]
0x180075638  xor     rcx, rsp; StackCookie
0x18007563b  call    __security_check_cookie
0x180075640  lea     r11, [rsp+98h+var_18]
0x180075648  mov     rbx, [r11+30h]
0x18007564c  mov     rsi, [r11+38h]
0x180075650  mov     rsp, r11
0x180075653  pop     r15
0x180075655  pop     r14
0x180075657  pop     rdi
0x180075658  retn
```
