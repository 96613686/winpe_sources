# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageDisplayName(Windows::Internal::StateRepository::IPackage *)

- ea: `0x180042d3c`
- end: `0x180042ee7`
- name: `?GetPackageDisplayName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@StateRepository@Internal@Windows@@@Z`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004430c`
- `0x180045954`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180004cfc`
- `0x180023c78`
- `0x180036598`
- `0x180042d3c`
- `0x180055ca0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180042e75`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180042e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042e5e`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageDisplayName(
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
      (void *)0x446,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)0x80004005LL,
      (int)string);
  v15[0] = 0;
  v5 = *(_QWORD *)(a1 + 384);
  v6 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v5 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  v7 = v6(v5, a3, v15);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x449,
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
      (void *)0x455,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0x1000u, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x45C,
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
0x180042d3c  push    rbp
0x180042d3e  push    rbx
0x180042d3f  push    rsi
0x180042d40  push    rdi
0x180042d41  push    r14
0x180042d43  lea     rbp, [rsp-1F50h]
0x180042d4b  mov     eax, 2050h
0x180042d50  call    _alloca_probe
0x180042d55  sub     rsp, rax
0x180042d58  mov     rax, cs:__security_cookie
0x180042d5f  xor     rax, rsp
0x180042d62  mov     [rbp+1F70h+var_30], rax
0x180042d69  mov     r14, r8
0x180042d6c  mov     rsi, rdx
0x180042d6f  mov     rdi, rcx
0x180042d72  mov     [rsp+2070h+var_2048], rdx
0x180042d77  mov     rcx, [rbp+1F78h]; this
0x180042d7e  test    r8, r8
0x180042d81  jnz     short loc_180042D9B
0x180042d83  mov     r9d, 80004005h; char *
0x180042d89  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042d90  mov     edx, 446h; void *
0x180042d95  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042d9b  mov     [rsp+2070h+var_2048], 0
0x180042da4  mov     rdi, [rdi+180h]
0x180042dab  mov     rax, [rdi]
0x180042dae  mov     rbx, [rax+30h]
0x180042db2  lea     rcx, [rsp+2070h+var_2048]
0x180042db7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042dbc  lea     r8, [rsp+2070h+var_2048]
0x180042dc1  mov     rdx, r14
0x180042dc4  mov     rcx, rdi
0x180042dc7  mov     rax, rbx
0x180042dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dcf  mov     rcx, [rbp+1F78h]; this
0x180042dd6  test    eax, eax
0x180042dd8  jns     short loc_180042DEF
0x180042dda  mov     r9d, eax; char *
0x180042ddd  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042de4  mov     edx, 449h; void *
0x180042de9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042def  mov     [rsp+2070h+string], 0
0x180042df8  mov     rdi, [rsp+2070h+var_2048]
0x180042dfd  mov     rax, [rdi]
0x180042e00  mov     rbx, [rax+30h]
0x180042e04  xor     ecx, ecx; string
0x180042e06  call    cs:__imp_WindowsDeleteString
0x180042e0c  mov     [rsp+2070h+string], 0; int
0x180042e15  lea     rdx, [rsp+2070h+string]
0x180042e1a  mov     rcx, rdi
0x180042e1d  mov     rax, rbx
0x180042e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e25  mov     rcx, [rbp+1F78h]; this
0x180042e2c  test    eax, eax
0x180042e2e  jns     short loc_180042E45
0x180042e30  mov     r9d, eax; char *
0x180042e33  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042e3a  mov     edx, 455h; void *
0x180042e3f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042e45  xor     edx, edx; Val
0x180042e47  mov     r8d, 2000h; Size
0x180042e4d  lea     rcx, [rsp+2070h+pszOutBuf]; void *
0x180042e52  call    memset_0
0x180042e57  xor     edx, edx; length
0x180042e59  mov     rcx, [rsp+2070h+string]; string
0x180042e5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180042e64  xor     r9d, r9d; ppvReserved
0x180042e67  mov     r8d, 1000h; cchOutBuf
0x180042e6d  lea     rdx, [rsp+2070h+pszOutBuf]; pszOutBuf
0x180042e72  mov     rcx, rax; pszSource
0x180042e75  call    cs:__imp_SHLoadIndirectString
0x180042e7b  mov     rcx, [rbp+1F78h]; this
0x180042e82  test    eax, eax
0x180042e84  jns     short loc_180042E9B
0x180042e86  mov     r9d, eax; char *
0x180042e89  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180042e90  mov     edx, 45Ch; void *
0x180042e95  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180042e9b  lea     rdx, [rsp+2070h+pszOutBuf]
0x180042ea0  mov     rcx, rsi
0x180042ea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042ea8  nop
0x180042ea9  mov     rcx, [rsp+2070h+string]; string
0x180042eae  call    cs:__imp_WindowsDeleteString
0x180042eb4  mov     [rsp+2070h+string], 0
0x180042ebd  lea     rcx, [rsp+2070h+var_2048]
0x180042ec2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042ec7  mov     rax, rsi
0x180042eca  mov     rcx, [rbp+1F70h+var_30]
0x180042ed1  xor     rcx, rsp; StackCookie
0x180042ed4  call    __security_check_cookie
0x180042ed9  add     rsp, 2050h
0x180042ee0  pop     r14
0x180042ee2  pop     rdi
0x180042ee3  pop     rsi
0x180042ee4  pop     rbx
0x180042ee5  pop     rbp
0x180042ee6  retn
```
