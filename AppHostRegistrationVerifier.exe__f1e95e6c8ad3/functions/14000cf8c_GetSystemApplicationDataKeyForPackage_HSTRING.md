# GetSystemApplicationDataKeyForPackage(HSTRING__ *)

- ea: `0x14000cf8c`
- end: `0x14000d12c`
- name: `?GetSystemApplicationDataKeyForPackage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z`
- size: `416`
- prototype: `PHKEY __fastcall(PHKEY phkResult, HSTRING string)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ced4`
- `0x14000d194`
- `0x14000eb7c`

## callees

- `0x14000305c`
- `0x140006fc0`
- `0x14000a13c`
- `0x14000a17c`
- `0x14000cf8c`
- `0x14000fbb0`
- `0x14000fc20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000cfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000cfb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000d0e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000d0e5`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x14000cff2`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x14000d04f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x14000cff2`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x14000d04f`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x14000cfc6`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x14000cfc6`

## string_xrefs

- `0x14000d082`: `\AppUriHandlers`

## pseudocode

```c
PHKEY __fastcall GetSystemApplicationDataKeyForPackage(PHKEY phkResult, HSTRING string)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned __int16 *v6; // rsi
  int v7; // eax
  unsigned int Key; // eax
  unsigned int v9; // r8d
  DWORD dwOptions; // [rsp+20h] [rbp-40h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-40h]
  __int64 v13; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v15; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v4 = OpenStateExplicit(-4, StringRawBuffer);
  v13 = v4;
  hKey = 0;
  v15 = 0;
  if ( (unsigned int)GetSystemAppDataKey(v4, 0, 0, &v15) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
  v5 = (unsigned int)(v15 + 15);
  v6 = (unsigned __int16 *)operator new[](saturated_mul(v5, 2u));
  if ( !(unsigned int)GetSystemAppDataKey(v4, &hKey, v6, &v15) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
  *phkResult = 0;
  v7 = StringCchCatW(v6, v5, L"\\AppUriHandlers");
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v7,
      dwOptions);
  Key = RegCreateKeyExW(hKey, v6, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2A7, v9, (const char *)Key, dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
  return phkResult;
}

```

## disassembly

```asm
0x14000cf8c  mov     [rsp-28h+arg_8], rbx
0x14000cf91  mov     [rsp-28h+arg_0], rcx
0x14000cf96  push    rbp
0x14000cf97  push    rsi
0x14000cf98  push    rdi
0x14000cf99  push    r14
0x14000cf9b  push    r15
0x14000cf9d  mov     rbp, rsp
0x14000cfa0  sub     rsp, 60h
0x14000cfa4  mov     rax, rdx
0x14000cfa7  mov     rdi, rcx
0x14000cfaa  mov     [rbp+var_10], 0
0x14000cfb1  xor     edx, edx; length
0x14000cfb3  mov     rcx, rax; string
0x14000cfb6  call    cs:__imp_WindowsGetStringRawBuffer
0x14000cfbc  mov     rdx, rax
0x14000cfbf  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x14000cfc6  call    cs:__imp_OpenStateExplicit
0x14000cfcc  mov     rbx, rax
0x14000cfcf  mov     [rbp+var_8], rax
0x14000cfd3  mov     [rbp+hKey], 0
0x14000cfdb  mov     [rbp+arg_10], 0
0x14000cfe2  mov     rsi, [rbp+28h]
0x14000cfe6  lea     r9, [rbp+arg_10]
0x14000cfea  xor     r8d, r8d
0x14000cfed  xor     edx, edx
0x14000cfef  mov     rcx, rax
0x14000cff2  call    cs:__imp_GetSystemAppDataKey
0x14000cff8  test    eax, eax
0x14000cffa  jz      short loc_14000D017
0x14000cffc  mov     r9d, 8000FFFFh; char *
0x14000d002  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000d009  mov     edx, 29Dh; void *
0x14000d00e  mov     rcx, rsi; this
0x14000d011  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000d017  mov     r14d, [rbp+arg_10]
0x14000d01b  add     r14d, 0Fh
0x14000d01f  mov     eax, 2
0x14000d024  mul     r14
0x14000d027  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d02e  cmovb   rax, rcx
0x14000d032  mov     rcx, rax; unsigned __int64
0x14000d035  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000d03a  mov     rsi, rax
0x14000d03d  mov     r15, [rbp+28h]
0x14000d041  lea     r9, [rbp+arg_10]
0x14000d045  mov     r8, rax
0x14000d048  lea     rdx, [rbp+hKey]
0x14000d04c  mov     rcx, rbx
0x14000d04f  call    cs:__imp_GetSystemAppDataKey
0x14000d055  test    eax, eax
0x14000d057  jnz     short loc_14000D074
0x14000d059  mov     r9d, 8000FFFFh; char *
0x14000d05f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000d066  mov     edx, 2A1h; void *
0x14000d06b  mov     rcx, r15; this
0x14000d06e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000d074  mov     qword ptr [rdi], 0
0x14000d07b  mov     [rbp+var_10], 1
0x14000d082  lea     r8, aAppurihandlers; "\\AppUriHandlers"
0x14000d089  mov     rdx, r14; unsigned __int64
0x14000d08c  mov     rcx, rsi; unsigned __int16 *
0x14000d08f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d094  mov     rcx, [rbp+28h]; this
0x14000d098  test    eax, eax
0x14000d09a  jns     short loc_14000D0B1
0x14000d09c  mov     r9d, eax; char *
0x14000d09f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000d0a6  mov     edx, 2A4h; void *
0x14000d0ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000d0b1  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x14000d0ba  mov     [rsp+60h+phkResult], rdi; phkResult
0x14000d0bf  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000d0c8  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x14000d0d0  mov     [rsp+60h+dwOptions], 0; unsigned int
0x14000d0d8  xor     r9d, r9d; lpClass
0x14000d0db  xor     r8d, r8d; Reserved
0x14000d0de  mov     rdx, rsi; lpSubKey
0x14000d0e1  mov     rcx, [rbp+hKey]; hKey
0x14000d0e5  call    cs:__imp_RegCreateKeyExW
0x14000d0eb  mov     rcx, [rbp+28h]; this
0x14000d0ef  test    eax, eax
0x14000d0f1  jz      short loc_14000D101
0x14000d0f3  mov     r9d, eax; char *
0x14000d0f6  mov     edx, 2A7h; void *
0x14000d0fb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000d101  lea     rcx, [rbp+hKey]
0x14000d105  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000d10a  nop
0x14000d10b  lea     rcx, [rbp+var_8]
0x14000d10f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000d114  mov     rax, rdi
0x14000d117  mov     rbx, [rsp+60h+arg_8]
0x14000d11f  add     rsp, 60h
0x14000d123  pop     r15
0x14000d125  pop     r14
0x14000d127  pop     rdi
0x14000d128  pop     rsi
0x14000d129  pop     rbp
0x14000d12a  retn
```
