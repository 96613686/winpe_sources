# Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x1800842c4`
- end: `0x1800844ea`
- name: `?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18006e4e0`
- `0x18009b400`
- `0x1800bf7e4`

## callees

- `0x180011320`
- `0x180011680`
- `0x180039d4c`
- `0x180083c20`
- `0x1800842c4`
- `0x1800855a0`
- `0x1800dd930`
- `0x1800dff58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180084359`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800843c2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180084460`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180084359`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800843c2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180084460`

## string_xrefs

- `0x1800843e3`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180084483`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1800844c9`: `Registry type unsupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Registry::SetValue(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        __int128 *a4,
        const WCHAR **a5,
        __int64 a6)
{
  char v6; // al
  const WCHAR *v7; // rbx
  LPCWSTR *v8; // rdi
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  const WCHAR *v11; // rbx
  LPCWSTR *v12; // rdi
  const WCHAR *v13; // rdx
  unsigned int v14; // eax
  const WCHAR *v15; // rbx
  LPCWSTR *v16; // rdi
  LPCVOID *lpData; // rcx
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-1h]
  __int128 Data; // [rsp+60h] [rbp+7h] BYREF
  LPCVOID pExceptionObject[2]; // [rsp+70h] [rbp+17h] BYREF
  int v24; // [rsp+80h] [rbp+27h]
  unsigned __int64 v25; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+4Fh]

  Data = *a4;
  *(_OWORD *)pExceptionObject = *a3;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, pExceptionObject, &Data);
  v6 = *(_BYTE *)(a6 + 32);
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      *(_QWORD *)&Data = *(_QWORD *)a6;
      v11 = *a5;
      v12 = lpSubKey;
      if ( v21 > 7 )
        v12 = (LPCWSTR *)lpSubKey[0];
      v13 = (const WCHAR *)lpSubKey;
      if ( v21 > 7 )
        v13 = lpSubKey[0];
      v14 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v13, v11, 0xBu, &Data, 8u);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x168,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v14,
        (unsigned int)"%ws[%ws]",
        (const char *)v12,
        v11);
    }
    else
    {
      if ( v6 != 2 )
      {
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Registry type unsupported");
        throw (std::logic_error *)pExceptionObject;
      }
      std::wstring::wstring(pExceptionObject, a6);
      v15 = *a5;
      v16 = lpSubKey;
      if ( v21 > 7 )
        v16 = (LPCWSTR *)lpSubKey[0];
      lpData = pExceptionObject;
      if ( v25 > 7 )
        lpData = (LPCVOID *)pExceptionObject[0];
      v18 = (const WCHAR *)lpSubKey;
      if ( v21 > 7 )
        v18 = lpSubKey[0];
      v19 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v18, v15, 1u, lpData, 2 * v24 + 2);
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x174,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v19,
        (unsigned int)"%ws[%ws]",
        (const char *)v16,
        v15);
      std::wstring::~wstring(pExceptionObject);
    }
  }
  else
  {
    LODWORD(Data) = *(_DWORD *)a6;
    v7 = *a5;
    v8 = lpSubKey;
    if ( v21 > 7 )
      v8 = (LPCWSTR *)lpSubKey[0];
    v9 = (const WCHAR *)lpSubKey;
    if ( v21 > 7 )
      v9 = lpSubKey[0];
    v10 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v9, v7, 4u, &Data, 4u);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x15D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v10,
      (unsigned int)"%ws[%ws]",
      (const char *)v8,
      v7);
  }
  std::wstring::~wstring(lpSubKey);
}

```

## disassembly

```asm
0x1800842c4  mov     [rsp-8+arg_0], rbx
0x1800842c9  mov     [rsp-8+arg_8], rdi
0x1800842ce  push    rbp
0x1800842cf  lea     rbp, [rsp-47h]
0x1800842d4  sub     rsp, 0A0h
0x1800842db  mov     rax, cs:__security_cookie
0x1800842e2  xor     rax, rsp
0x1800842e5  mov     [rbp+47h+var_10], rax
0x1800842e9  mov     rdi, [rbp+47h+arg_20]
0x1800842ed  mov     rbx, [rbp+47h+arg_28]
0x1800842f1  movaps  xmm0, xmmword ptr [r9]
0x1800842f5  movdqa  [rbp+47h+Data], xmm0
0x1800842fa  movaps  xmm1, xmmword ptr [r8]
0x1800842fe  movdqa  xmmword ptr [rbp+47h+pExceptionObject], xmm1
0x180084303  lea     r9, [rbp+47h+Data]
0x180084307  lea     r8, [rbp+47h+pExceptionObject]
0x18008430b  lea     rdx, [rbp+47h+lpSubKey]
0x18008430f  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180084314  nop
0x180084315  mov     al, [rbx+20h]
0x180084318  test    al, al
0x18008431a  jnz     short loc_18008437C
0x18008431c  mov     eax, [rbx]
0x18008431e  mov     dword ptr [rbp+47h+Data], eax
0x180084321  mov     rbx, [rdi]
0x180084324  lea     rdi, [rbp+47h+lpSubKey]
0x180084328  cmp     [rbp+47h+var_48], 7
0x18008432d  cmova   rdi, [rbp+47h+lpSubKey]
0x180084332  lea     rdx, [rbp+47h+lpSubKey]
0x180084336  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18008433b  mov     r9d, 4; dwType
0x180084341  mov     [rsp+0A0h+cbData], r9d; cbData
0x180084346  lea     rax, [rbp+47h+Data]
0x18008434a  mov     [rsp+0A0h+lpData], rax; lpData
0x18008434f  mov     r8, rbx; lpValueName
0x180084352  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084359  call    cs:__imp_RegSetKeyValueW
0x18008435f  mov     [rsp+0A0h+var_70], rbx
0x180084364  mov     qword ptr [rsp+0A0h+cbData], rdi
0x180084369  lea     rdx, aWsWs; "%ws[%ws]"
0x180084370  mov     [rsp+0A0h+lpData], rdx
0x180084375  mov     edx, 15Dh
0x18008437a  jmp     short loc_1800843E3
0x18008437c  cmp     al, 1
0x18008437e  jnz     short loc_1800843FB
0x180084380  mov     rax, [rbx]
0x180084383  mov     qword ptr [rbp+47h+Data], rax
0x180084387  mov     rbx, [rdi]
0x18008438a  lea     rdi, [rbp+47h+lpSubKey]
0x18008438e  cmp     [rbp+47h+var_48], 7
0x180084393  cmova   rdi, [rbp+47h+lpSubKey]
0x180084398  lea     rdx, [rbp+47h+lpSubKey]
0x18008439c  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800843a1  mov     [rsp+0A0h+cbData], 8; cbData
0x1800843a9  lea     rax, [rbp+47h+Data]
0x1800843ad  mov     [rsp+0A0h+lpData], rax; lpData
0x1800843b2  mov     r9d, 0Bh; dwType
0x1800843b8  mov     r8, rbx; lpValueName
0x1800843bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800843c2  call    cs:__imp_RegSetKeyValueW
0x1800843c8  mov     [rsp+0A0h+var_70], rbx
0x1800843cd  mov     qword ptr [rsp+0A0h+cbData], rdi; char *
0x1800843d2  lea     rdx, aWsWs; "%ws[%ws]"
0x1800843d9  mov     [rsp+0A0h+lpData], rdx; unsigned int
0x1800843de  mov     edx, 168h; void *
0x1800843e3  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800843ea  mov     r9d, eax; char *
0x1800843ed  mov     rcx, [rbp+4Fh]; this
0x1800843f1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800843f6  jmp     loc_18008449F
0x1800843fb  cmp     al, 2
0x1800843fd  jnz     loc_1800844C9
0x180084403  mov     rdx, rbx
0x180084406  lea     rcx, [rbp+47h+pExceptionObject]
0x18008440a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008440f  nop
0x180084410  mov     rbx, [rdi]
0x180084413  lea     rdi, [rbp+47h+lpSubKey]
0x180084417  cmp     [rbp+47h+var_48], 7
0x18008441c  cmova   rdi, [rbp+47h+lpSubKey]
0x180084421  lea     rcx, [rbp+47h+pExceptionObject]
0x180084425  cmp     [rbp+47h+var_18], 7
0x18008442a  cmova   rcx, [rbp+47h+pExceptionObject]
0x18008442f  lea     rdx, [rbp+47h+lpSubKey]
0x180084433  cmp     [rbp+47h+var_48], 7
0x180084438  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18008443d  mov     eax, [rbp+47h+var_20]
0x180084440  lea     eax, ds:2[rax*2]
0x180084447  mov     [rsp+0A0h+cbData], eax; cbData
0x18008444b  mov     [rsp+0A0h+lpData], rcx; lpData
0x180084450  mov     r9d, 1; dwType
0x180084456  mov     r8, rbx; lpValueName
0x180084459  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084460  call    cs:__imp_RegSetKeyValueW
0x180084466  mov     rcx, [rbp+4Fh]; this
0x18008446a  mov     [rsp+0A0h+var_70], rbx
0x18008446f  mov     qword ptr [rsp+0A0h+cbData], rdi; char *
0x180084474  lea     rdx, aWsWs; "%ws[%ws]"
0x18008447b  mov     [rsp+0A0h+lpData], rdx; unsigned int
0x180084480  mov     r9d, eax; char *
0x180084483  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008448a  mov     edx, 174h; void *
0x18008448f  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180084494  nop
0x180084495  lea     rcx, [rbp+47h+pExceptionObject]; void *
0x180084499  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008449e  nop
0x18008449f  lea     rcx, [rbp+47h+lpSubKey]; void *
0x1800844a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800844a8  mov     rcx, [rbp+47h+var_10]
0x1800844ac  xor     rcx, rsp; StackCookie
0x1800844af  call    __security_check_cookie
0x1800844b4  lea     r11, [rsp+0A0h+var_s0]
0x1800844bc  mov     rbx, [r11+10h]
0x1800844c0  mov     rdi, [r11+18h]
0x1800844c4  mov     rsp, r11
0x1800844c7  pop     rbp
0x1800844c8  retn
0x1800844c9  lea     rdx, aRegistryTypeUn; "Registry type unsupported"
0x1800844d0  lea     rcx, [rbp+47h+pExceptionObject]; this
0x1800844d4  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x1800844d9  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1800844e0  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1800844e4  call    _CxxThrowException
```
