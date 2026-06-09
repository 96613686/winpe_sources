# Windows::Registry::SetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<uint,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x18003c6b0`
- end: `0x18003c8d6`
- name: `?SetValue@Registry@Windows@@QEAAXQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11AEBV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180023280`

## callees

- `0x180009380`
- `0x180033b00`
- `0x180035184`
- `0x18003c020`
- `0x18003c6b0`
- `0x18003df70`
- `0x180056500`
- `0x180058abc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c745`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c7ae`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c84c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c745`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c7ae`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003c84c`

## string_xrefs

- `0x18003c7cf`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c86f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c8b5`: `Registry type unsupported`

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
0x18003c6b0  mov     [rsp-8+arg_0], rbx
0x18003c6b5  mov     [rsp-8+arg_8], rdi
0x18003c6ba  push    rbp
0x18003c6bb  lea     rbp, [rsp-47h]
0x18003c6c0  sub     rsp, 0A0h
0x18003c6c7  mov     rax, cs:__security_cookie
0x18003c6ce  xor     rax, rsp
0x18003c6d1  mov     [rbp+47h+var_10], rax
0x18003c6d5  mov     rdi, [rbp+47h+arg_20]
0x18003c6d9  mov     rbx, [rbp+47h+arg_28]
0x18003c6dd  movaps  xmm0, xmmword ptr [r9]
0x18003c6e1  movdqa  [rbp+47h+Data], xmm0
0x18003c6e6  movaps  xmm1, xmmword ptr [r8]
0x18003c6ea  movdqa  xmmword ptr [rbp+47h+pExceptionObject], xmm1
0x18003c6ef  lea     r9, [rbp+47h+Data]
0x18003c6f3  lea     r8, [rbp+47h+pExceptionObject]
0x18003c6f7  lea     rdx, [rbp+47h+lpSubKey]
0x18003c6fb  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003c700  nop
0x18003c701  mov     al, [rbx+20h]
0x18003c704  test    al, al
0x18003c706  jnz     short loc_18003C768
0x18003c708  mov     eax, [rbx]
0x18003c70a  mov     dword ptr [rbp+47h+Data], eax
0x18003c70d  mov     rbx, [rdi]
0x18003c710  lea     rdi, [rbp+47h+lpSubKey]
0x18003c714  cmp     [rbp+47h+var_48], 7
0x18003c719  cmova   rdi, [rbp+47h+lpSubKey]
0x18003c71e  lea     rdx, [rbp+47h+lpSubKey]
0x18003c722  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003c727  mov     r9d, 4; dwType
0x18003c72d  mov     [rsp+0A0h+cbData], r9d; cbData
0x18003c732  lea     rax, [rbp+47h+Data]
0x18003c736  mov     [rsp+0A0h+lpData], rax; lpData
0x18003c73b  mov     r8, rbx; lpValueName
0x18003c73e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c745  call    cs:__imp_RegSetKeyValueW
0x18003c74b  mov     [rsp+0A0h+var_70], rbx
0x18003c750  mov     qword ptr [rsp+0A0h+cbData], rdi
0x18003c755  lea     rdx, aWsWs_0; "%ws[%ws]"
0x18003c75c  mov     [rsp+0A0h+lpData], rdx
0x18003c761  mov     edx, 15Dh
0x18003c766  jmp     short loc_18003C7CF
0x18003c768  cmp     al, 1
0x18003c76a  jnz     short loc_18003C7E7
0x18003c76c  mov     rax, [rbx]
0x18003c76f  mov     qword ptr [rbp+47h+Data], rax
0x18003c773  mov     rbx, [rdi]
0x18003c776  lea     rdi, [rbp+47h+lpSubKey]
0x18003c77a  cmp     [rbp+47h+var_48], 7
0x18003c77f  cmova   rdi, [rbp+47h+lpSubKey]
0x18003c784  lea     rdx, [rbp+47h+lpSubKey]
0x18003c788  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003c78d  mov     [rsp+0A0h+cbData], 8; cbData
0x18003c795  lea     rax, [rbp+47h+Data]
0x18003c799  mov     [rsp+0A0h+lpData], rax; lpData
0x18003c79e  mov     r9d, 0Bh; dwType
0x18003c7a4  mov     r8, rbx; lpValueName
0x18003c7a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c7ae  call    cs:__imp_RegSetKeyValueW
0x18003c7b4  mov     [rsp+0A0h+var_70], rbx
0x18003c7b9  mov     qword ptr [rsp+0A0h+cbData], rdi; char *
0x18003c7be  lea     rdx, aWsWs_0; "%ws[%ws]"
0x18003c7c5  mov     [rsp+0A0h+lpData], rdx; unsigned int
0x18003c7ca  mov     edx, 168h; void *
0x18003c7cf  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c7d6  mov     r9d, eax; char *
0x18003c7d9  mov     rcx, [rbp+4Fh]; this
0x18003c7dd  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003c7e2  jmp     loc_18003C88B
0x18003c7e7  cmp     al, 2
0x18003c7e9  jnz     loc_18003C8B5
0x18003c7ef  mov     rdx, rbx
0x18003c7f2  lea     rcx, [rbp+47h+pExceptionObject]
0x18003c7f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c7fb  nop
0x18003c7fc  mov     rbx, [rdi]
0x18003c7ff  lea     rdi, [rbp+47h+lpSubKey]
0x18003c803  cmp     [rbp+47h+var_48], 7
0x18003c808  cmova   rdi, [rbp+47h+lpSubKey]
0x18003c80d  lea     rcx, [rbp+47h+pExceptionObject]
0x18003c811  cmp     [rbp+47h+var_18], 7
0x18003c816  cmova   rcx, [rbp+47h+pExceptionObject]
0x18003c81b  lea     rdx, [rbp+47h+lpSubKey]
0x18003c81f  cmp     [rbp+47h+var_48], 7
0x18003c824  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003c829  mov     eax, [rbp+47h+var_20]
0x18003c82c  lea     eax, ds:2[rax*2]
0x18003c833  mov     [rsp+0A0h+cbData], eax; cbData
0x18003c837  mov     [rsp+0A0h+lpData], rcx; lpData
0x18003c83c  mov     r9d, 1; dwType
0x18003c842  mov     r8, rbx; lpValueName
0x18003c845  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c84c  call    cs:__imp_RegSetKeyValueW
0x18003c852  mov     rcx, [rbp+4Fh]; this
0x18003c856  mov     [rsp+0A0h+var_70], rbx
0x18003c85b  mov     qword ptr [rsp+0A0h+cbData], rdi; char *
0x18003c860  lea     rdx, aWsWs_0; "%ws[%ws]"
0x18003c867  mov     [rsp+0A0h+lpData], rdx; unsigned int
0x18003c86c  mov     r9d, eax; char *
0x18003c86f  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c876  mov     edx, 174h; void *
0x18003c87b  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003c880  nop
0x18003c881  lea     rcx, [rbp+47h+pExceptionObject]; void *
0x18003c885  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c88a  nop
0x18003c88b  lea     rcx, [rbp+47h+lpSubKey]; void *
0x18003c88f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c894  mov     rcx, [rbp+47h+var_10]
0x18003c898  xor     rcx, rsp; StackCookie
0x18003c89b  call    __security_check_cookie
0x18003c8a0  lea     r11, [rsp+0A0h+var_s0]
0x18003c8a8  mov     rbx, [r11+10h]
0x18003c8ac  mov     rdi, [r11+18h]
0x18003c8b0  mov     rsp, r11
0x18003c8b3  pop     rbp
0x18003c8b4  retn
0x18003c8b5  lea     rdx, aRegistryTypeUn; "Registry type unsupported"
0x18003c8bc  lea     rcx, [rbp+47h+pExceptionObject]; this
0x18003c8c0  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18003c8c5  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18003c8cc  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x18003c8d0  call    _CxxThrowException
```
