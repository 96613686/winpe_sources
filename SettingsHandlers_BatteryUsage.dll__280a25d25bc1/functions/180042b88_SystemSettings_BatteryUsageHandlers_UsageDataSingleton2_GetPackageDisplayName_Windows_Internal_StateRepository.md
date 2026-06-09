# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageDisplayName(Windows::Internal::StateRepository::IPackage *)

- ea: `0x180042b88`
- end: `0x180042d33`
- name: `?GetPackageDisplayName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@StateRepository@Internal@Windows@@@Z`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043f80`
- `0x1800457f0`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180004cfc`
- `0x180023c78`
- `0x180036598`
- `0x180042b88`
- `0x180055ca0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180042cc1`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180042cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageDisplayName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, _QWORD *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const WCHAR *StringRawBuffer; // rax
  HRESULT v12; // eax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v15[3]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszOutBuf[4096]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2078h] [rbp+1F78h]

  v15[0] = a2;
  if ( !a3 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA04,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)0x80004005LL,
      (int)string);
  v15[0] = 0;
  v5 = *(_QWORD *)(a1 + 376);
  v6 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v5 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  v7 = v6(v5, a3, v15);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA07,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
  string = 0;
  v8 = v15[0];
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15[0] + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(v8, &string);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA13,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x1000u, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA1A,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
  std::wstring::wstring(a2, (__int64)pszOutBuf);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  return a2;
}

```

## disassembly

```asm
0x180042b88  push    rbp
0x180042b8a  push    rbx
0x180042b8b  push    rsi
0x180042b8c  push    rdi
0x180042b8d  push    r14
0x180042b8f  lea     rbp, [rsp-1F50h]
0x180042b97  mov     eax, 2050h
0x180042b9c  call    _alloca_probe
0x180042ba1  sub     rsp, rax
0x180042ba4  mov     rax, cs:__security_cookie
0x180042bab  xor     rax, rsp
0x180042bae  mov     [rbp+1F70h+var_30], rax
0x180042bb5  mov     r14, r8
0x180042bb8  mov     rsi, rdx
0x180042bbb  mov     rdi, rcx
0x180042bbe  mov     [rsp+2070h+var_2048], rdx
0x180042bc3  mov     rcx, [rbp+1F78h]; this
0x180042bca  test    r8, r8
0x180042bcd  jnz     short loc_180042BE7
0x180042bcf  mov     r9d, 80004005h; char *
0x180042bd5  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042bdc  mov     edx, 0A04h; void *
0x180042be1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042be7  mov     [rsp+2070h+var_2048], 0
0x180042bf0  mov     rdi, [rdi+178h]
0x180042bf7  mov     rax, [rdi]
0x180042bfa  mov     rbx, [rax+30h]
0x180042bfe  lea     rcx, [rsp+2070h+var_2048]
0x180042c03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042c08  lea     r8, [rsp+2070h+var_2048]
0x180042c0d  mov     rdx, r14
0x180042c10  mov     rcx, rdi
0x180042c13  mov     rax, rbx
0x180042c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c1b  mov     rcx, [rbp+1F78h]; this
0x180042c22  test    eax, eax
0x180042c24  jns     short loc_180042C3B
0x180042c26  mov     r9d, eax; char *
0x180042c29  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042c30  mov     edx, 0A07h; void *
0x180042c35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042c3b  mov     [rsp+2070h+string], 0
0x180042c44  mov     rdi, [rsp+2070h+var_2048]
0x180042c49  mov     rax, [rdi]
0x180042c4c  mov     rbx, [rax+30h]
0x180042c50  xor     ecx, ecx; string
0x180042c52  call    cs:__imp_WindowsDeleteString
0x180042c58  mov     [rsp+2070h+string], 0; int
0x180042c61  lea     rdx, [rsp+2070h+string]
0x180042c66  mov     rcx, rdi
0x180042c69  mov     rax, rbx
0x180042c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c71  mov     rcx, [rbp+1F78h]; this
0x180042c78  test    eax, eax
0x180042c7a  jns     short loc_180042C91
0x180042c7c  mov     r9d, eax; char *
0x180042c7f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042c86  mov     edx, 0A13h; void *
0x180042c8b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042c91  xor     edx, edx; Val
0x180042c93  mov     r8d, 2000h; Size
0x180042c99  lea     rcx, [rsp+2070h+pszOutBuf]; void *
0x180042c9e  call    memset_0
0x180042ca3  xor     edx, edx; length
0x180042ca5  mov     rcx, [rsp+2070h+string]; string
0x180042caa  call    cs:__imp_WindowsGetStringRawBuffer
0x180042cb0  xor     r9d, r9d; ppvReserved
0x180042cb3  mov     r8d, 1000h; cchOutBuf
0x180042cb9  lea     rdx, [rsp+2070h+pszOutBuf]; pszOutBuf
0x180042cbe  mov     rcx, rax; pszSource
0x180042cc1  call    cs:__imp_SHLoadIndirectString
0x180042cc7  mov     rcx, [rbp+1F78h]; this
0x180042cce  test    eax, eax
0x180042cd0  jns     short loc_180042CE7
0x180042cd2  mov     r9d, eax; char *
0x180042cd5  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042cdc  mov     edx, 0A1Ah; void *
0x180042ce1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042ce7  lea     rdx, [rsp+2070h+pszOutBuf]
0x180042cec  mov     rcx, rsi
0x180042cef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042cf4  nop
0x180042cf5  mov     rcx, [rsp+2070h+string]; string
0x180042cfa  call    cs:__imp_WindowsDeleteString
0x180042d00  mov     [rsp+2070h+string], 0
0x180042d09  lea     rcx, [rsp+2070h+var_2048]
0x180042d0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042d13  mov     rax, rsi
0x180042d16  mov     rcx, [rbp+1F70h+var_30]
0x180042d1d  xor     rcx, rsp; StackCookie
0x180042d20  call    __security_check_cookie
0x180042d25  add     rsp, 2050h
0x180042d2c  pop     r14
0x180042d2e  pop     rdi
0x180042d2f  pop     rsi
0x180042d30  pop     rbx
0x180042d31  pop     rbp
0x180042d32  retn
```
