# SystemSettings::DataModel::CWebAuthHelper::_AddUriToSecurityZone(Windows::Foundation::IUriRuntimeClass *,tagURLZONE)

- ea: `0x1801b02a0`
- end: `0x1801b042a`
- name: `?_AddUriToSecurityZone@CWebAuthHelper@DataModel@SystemSettings@@IEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4tagURLZONE@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CWebAuthHelper *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, enum tagURLZONE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801afdec`

## callees

- `0x180011bb0`
- `0x18004dee4`
- `0x18005019c`
- `0x1801b02a0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b03af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b03af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b02e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b03f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b040b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b02e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b0311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b03f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b040b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b033c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b033c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b0351`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::DataModel::CWebAuthHelper::_AddUriToSecurityZone(
        SystemSettings::DataModel::CWebAuthHelper *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        enum tagURLZONE a3)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  HRESULT v6; // ebx
  __int64 (__fastcall *v7)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v9; // rax
  _QWORD v11[4]; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+70h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+28h] BYREF
  HSTRING v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  string = 0;
  v4 = 0;
  memset(v11, 0, 24);
  v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 136LL);
  WindowsDeleteString(0);
  v14 = 0;
  v6 = v5(a2, &v14);
  if ( v6 >= 0 )
  {
    v7 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 88LL);
    WindowsDeleteString(string);
    string = 0;
    v6 = v7(a2, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v9 = WindowsGetStringRawBuffer(v14, 0);
      v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             v11,
             L"%ws://%ws",
             v9,
             StringRawBuffer);
      v4 = v11[0];
    }
  }
  ppv = 0;
  if ( v6 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v6 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppv);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, 1, v4, 0);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v11);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801b02a0  mov     [rsp-18h+arg_10], rbx
0x1801b02a5  mov     [rsp-18h+string], rcx
0x1801b02aa  push    rbp
0x1801b02ab  push    rsi
0x1801b02ac  push    rdi
0x1801b02ad  mov     rbp, rsp
0x1801b02b0  sub     rsp, 50h
0x1801b02b4  mov     rdi, rdx
0x1801b02b7  mov     [rbp+arg_18], 0
0x1801b02bf  mov     [rbp+string], 0
0x1801b02c7  xor     esi, esi
0x1801b02c9  mov     [rbp+var_20], rsi
0x1801b02cd  mov     [rbp+var_18], rsi
0x1801b02d1  mov     [rbp+var_10], rsi
0x1801b02d5  mov     rax, [rdx]
0x1801b02d8  mov     rbx, [rax+88h]
0x1801b02df  xor     ecx, ecx; string
0x1801b02e1  call    cs:__imp_WindowsDeleteString
0x1801b02e8  nop     dword ptr [rax+rax+00h]
0x1801b02ed  mov     [rbp+arg_18], rsi
0x1801b02f1  lea     rdx, [rbp+arg_18]
0x1801b02f5  mov     rcx, rdi
0x1801b02f8  mov     rax, rbx
0x1801b02fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0300  mov     ebx, eax
0x1801b0302  test    eax, eax
0x1801b0304  js      short loc_1801B0379
0x1801b0306  mov     rax, [rdi]
0x1801b0309  mov     rbx, [rax+58h]
0x1801b030d  mov     rcx, [rbp+string]; string
0x1801b0311  call    cs:__imp_WindowsDeleteString
0x1801b0318  nop     dword ptr [rax+rax+00h]
0x1801b031d  mov     [rbp+string], rsi
0x1801b0321  lea     rdx, [rbp+string]
0x1801b0325  mov     rcx, rdi
0x1801b0328  mov     rax, rbx
0x1801b032b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0330  mov     ebx, eax
0x1801b0332  test    eax, eax
0x1801b0334  js      short loc_1801B0379
0x1801b0336  xor     edx, edx; length
0x1801b0338  mov     rcx, [rbp+string]; string
0x1801b033c  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b0343  nop     dword ptr [rax+rax+00h]
0x1801b0348  mov     rbx, rax
0x1801b034b  xor     edx, edx; length
0x1801b034d  mov     rcx, [rbp+arg_18]; string
0x1801b0351  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b0358  nop     dword ptr [rax+rax+00h]
0x1801b035d  mov     r9, rbx
0x1801b0360  mov     r8, rax
0x1801b0363  lea     rdx, aWsWs_1; "%ws://%ws"
0x1801b036a  lea     rcx, [rbp+var_20]
0x1801b036e  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1801b0373  mov     ebx, eax
0x1801b0375  mov     rsi, [rbp+var_20]
0x1801b0379  mov     [rbp+arg_8], 0
0x1801b0381  test    ebx, ebx
0x1801b0383  js      short loc_1801B03DB
0x1801b0385  lea     rcx, [rbp+arg_8]
0x1801b0389  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b038e  lea     rax, [rbp+arg_8]
0x1801b0392  mov     [rsp+50h+ppv], rax; ppv
0x1801b0397  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1801b039e  mov     edi, 1
0x1801b03a3  mov     r8d, edi; dwClsContext
0x1801b03a6  xor     edx, edx; pUnkOuter
0x1801b03a8  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1801b03af  call    cs:__imp_CoCreateInstance
0x1801b03b6  nop     dword ptr [rax+rax+00h]
0x1801b03bb  mov     ebx, eax
0x1801b03bd  test    eax, eax
0x1801b03bf  js      short loc_1801B03DB
0x1801b03c1  mov     rcx, [rbp+arg_8]
0x1801b03c5  mov     rax, [rcx]
0x1801b03c8  xor     r9d, r9d
0x1801b03cb  mov     r8, rsi
0x1801b03ce  mov     edx, edi
0x1801b03d0  mov     rax, [rax+48h]
0x1801b03d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b03d9  mov     ebx, eax
0x1801b03db  lea     rcx, [rbp+arg_8]
0x1801b03df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b03e4  nop
0x1801b03e5  lea     rcx, [rbp+var_20]
0x1801b03e9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b03ee  nop
0x1801b03ef  mov     rcx, [rbp+string]; string
0x1801b03f3  call    cs:__imp_WindowsDeleteString
0x1801b03fa  nop     dword ptr [rax+rax+00h]
0x1801b03ff  mov     [rbp+string], 0
0x1801b0407  mov     rcx, [rbp+arg_18]; string
0x1801b040b  call    cs:__imp_WindowsDeleteString
0x1801b0412  nop     dword ptr [rax+rax+00h]
0x1801b0417  mov     eax, ebx
0x1801b0419  mov     rbx, [rsp+50h+arg_10]
0x1801b0421  add     rsp, 50h
0x1801b0425  pop     rdi
0x1801b0426  pop     rsi
0x1801b0427  pop     rbp
0x1801b0428  retn
```
