# StorSvc::TreeWalker::RegistryHelper::WriteRegistry(std::list<StorSvc::TreeWalker::RegistryEntry,std::allocator<StorSvc::TreeWalker::RegistryEntry>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180049c18`
- end: `0x180049e71`
- name: `?WriteRegistry@RegistryHelper@TreeWalker@StorSvc@@CAJAEBV?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@_N@Z`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180049e78`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180019d34`
- `0x18001c130`
- `0x18001c208`
- `0x180039f6c`
- `0x18003d0a8`
- `0x180041930`
- `0x180049c18`
- `0x18004a3ec`
- `0x18004b7c0`
- `0x18004b84c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049cf3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049cf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049d7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049d7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049c95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049c95`
- `RPCRT4!RpcRevertToSelf` at `0x180049d08`
- `RPCRT4!RpcRevertToSelf` at `0x180049d08`
- `RPCRT4!RpcImpersonateClient` at `0x180049c54`
- `RPCRT4!RpcImpersonateClient` at `0x180049c54`

## string_xrefs

- `0x180049c6c`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x180049d1d`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x180049e22`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::WriteRegistry(__int64 **a1, __int64 a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  time_t *v7; // rcx
  unsigned int v8; // r14d
  __int64 *v9; // rdi
  __int64 *v10; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 result; // rax
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  int dwOptions; // [rsp+20h] [rbp-F8h]
  int dwOptionsa; // [rsp+20h] [rbp-F8h]
  __int64 *v23; // [rsp+50h] [rbp-C8h]
  unsigned int v24; // [rsp+58h] [rbp-C0h]
  HKEY hKey; // [rsp+60h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE v27[32]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v28[32]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v29[32]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  try
  {
    hKey = 0;
    v24 = 0;
    if ( RpcImpersonateClient(0) )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
        (const char *)0x80004005LL,
        dwOptions);
    hKey = 0;
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v5 = RegCreateKeyExW(HKEY_CURRENT_USER, v4, 0, 0, 0, 0x3000Fu, 0, &hKey, 0);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    RpcRevertToSelf();
    v7 = (time_t *)retaddr;
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
        (const char *)(unsigned int)v6,
        dwOptionsa);
    v8 = 0;
    v24 = 0;
    v9 = *a1;
    v10 = (__int64 *)*v9;
    v23 = v9;
    while ( v10 != v9 )
    {
      v16 = v8++;
      v24 = v8;
      v17 = std::to_wstring(v29, v16);
      v18 = std::operator+<unsigned short>(v28, a2, L"\\");
      std::operator+<unsigned short>(v27, v18, v17);
      std::wstring::_Tidy_deallocate(v28);
      std::wstring::_Tidy_deallocate(v29);
      v20 = StorSvc::TreeWalker::RegistryHelper::WriteRegistryEntry(
              v19,
              (__int64)v27,
              (__int64)(v10 + 2),
              *((_DWORD *)v10 + 12));
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
          (const char *)(unsigned int)v20,
          dwOptionsa);
      std::wstring::_Tidy_deallocate(v27);
      v10 = (__int64 *)*v10;
      v23 = v10;
    }
    *(_QWORD *)Data = time(v7);
    v11 = RegSetValueExW(hKey, L"timeStamp", 0, 0xBu, Data, 8u);
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
    result = v12;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xA1, v13, v14);
  }
  return result;
}

```

## disassembly

```asm
0x180049c18  push    rbx
0x180049c1a  push    rsi
0x180049c1b  push    rdi
0x180049c1c  push    r12
0x180049c1e  push    r14
0x180049c20  push    r15
0x180049c22  sub     rsp, 0E8h
0x180049c29  mov     rax, cs:__security_cookie
0x180049c30  xor     rax, rsp
0x180049c33  mov     [rsp+118h+var_48], rax
0x180049c3b  mov     r12, rdx
0x180049c3e  mov     rdi, rcx
0x180049c41  mov     [rsp+118h+hKey], 0
0x180049c4a  mov     [rsp+118h+var_C0], 0
0x180049c52  xor     ecx, ecx; BindingHandle
0x180049c54  call    cs:__imp_RpcImpersonateClient
0x180049c5a  test    eax, eax
0x180049c5c  jz      short loc_180049C7D
0x180049c5e  mov     rcx, [rsp+118h]; this
0x180049c66  mov     r9d, 80004005h; char *
0x180049c6c  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180049c73  mov     edx, 82h; void *
0x180049c78  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180049c7d  mov     rbx, [rsp+118h+hKey]
0x180049c82  test    rbx, rbx
0x180049c85  jz      short loc_180049CA6
0x180049c87  lea     rcx, [rsp+118h+var_C8]; this
0x180049c8c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180049c91  nop
0x180049c92  mov     rcx, rbx; hKey
0x180049c95  call    cs:__imp_RegCloseKey
0x180049c9b  nop
0x180049c9c  lea     rcx, [rsp+118h+var_C8]; this
0x180049ca1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180049ca6  mov     [rsp+118h+hKey], 0
0x180049caf  mov     rcx, r12
0x180049cb2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049cb7  mov     [rsp+118h+lpdwDisposition], 0; lpdwDisposition
0x180049cc0  lea     rcx, [rsp+118h+hKey]
0x180049cc5  mov     [rsp+118h+phkResult], rcx; phkResult
0x180049cca  mov     [rsp+118h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180049cd3  mov     [rsp+118h+samDesired], 3000Fh; samDesired
0x180049cdb  mov     [rsp+118h+dwOptions], 0; int
0x180049ce3  xor     r9d, r9d; lpClass
0x180049ce6  xor     r8d, r8d; Reserved
0x180049ce9  mov     rdx, rax; lpSubKey
0x180049cec  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180049cf3  call    cs:__imp_RegCreateKeyExW
0x180049cf9  mov     ebx, eax
0x180049cfb  test    eax, eax
0x180049cfd  jle     short loc_180049D08
0x180049cff  movzx   ebx, ax
0x180049d02  or      ebx, 80070000h
0x180049d08  call    cs:__imp_RpcRevertToSelf
0x180049d0e  mov     rcx, [rsp+118h]; this
0x180049d16  test    ebx, ebx
0x180049d18  jns     short loc_180049D2E
0x180049d1a  mov     r9d, ebx; char *
0x180049d1d  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180049d24  mov     edx, 94h; void *
0x180049d29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180049d2e  xor     r14d, r14d
0x180049d31  mov     [rsp+118h+var_C0], r14d
0x180049d36  mov     rdi, [rdi]
0x180049d39  mov     rbx, [rdi]
0x180049d3c  mov     [rsp+118h+var_C8], rbx
0x180049d41  mov     [rsp+118h+var_C8], rdi
0x180049d46  cmp     rbx, rdi
0x180049d49  jnz     short loc_180049DA2
0x180049d4b  call    time
0x180049d50  mov     qword ptr [rsp+118h+Data], rax
0x180049d55  mov     [rsp+118h+samDesired], 8; cbData
0x180049d5d  lea     rax, [rsp+118h+Data]
0x180049d62  mov     qword ptr [rsp+118h+dwOptions], rax; lpData
0x180049d67  mov     r9d, 0Bh; dwType
0x180049d6d  xor     r8d, r8d; Reserved
0x180049d70  lea     rdx, aTimestamp; "timeStamp"
0x180049d77  mov     rcx, [rsp+118h+hKey]; hKey
0x180049d7c  call    cs:__imp_RegSetValueExW
0x180049d82  mov     ebx, eax
0x180049d84  test    eax, eax
0x180049d86  jle     short loc_180049D91
0x180049d88  movzx   ebx, ax
0x180049d8b  or      ebx, 80070000h
0x180049d91  lea     rcx, [rsp+118h+hKey]
0x180049d96  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x180049d9b  mov     eax, ebx
0x180049d9d  jmp     loc_180049E4F
0x180049da2  mov     edx, r14d
0x180049da5  inc     r14d
0x180049da8  mov     [rsp+118h+var_C0], r14d
0x180049dad  lea     rcx, [rsp+118h+var_68]
0x180049db5  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180049dba  mov     rsi, rax
0x180049dbd  lea     r8, asc_180092790; "\\"
0x180049dc4  mov     rdx, r12
0x180049dc7  lea     rcx, [rsp+118h+var_88]
0x180049dcf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180049dd4  nop
0x180049dd5  mov     r8, rsi
0x180049dd8  mov     rdx, rax
0x180049ddb  lea     rcx, [rsp+118h+var_A8]
0x180049de0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180049de5  nop
0x180049de6  lea     rcx, [rsp+118h+var_88]
0x180049dee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049df3  nop
0x180049df4  lea     rcx, [rsp+118h+var_68]
0x180049dfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049e01  mov     r9d, [rbx+30h]
0x180049e05  lea     r8, [rbx+10h]
0x180049e09  lea     rdx, [rsp+118h+var_A8]
0x180049e0e  call    ?WriteRegistryEntry@RegistryHelper@TreeWalker@StorSvc@@CAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1H_N@Z; StorSvc::TreeWalker::RegistryHelper::WriteRegistryEntry(HKEY__ *,std::wstring const &,std::wstring const &,int,bool)
0x180049e13  mov     rcx, [rsp+118h]; this
0x180049e1b  test    eax, eax
0x180049e1d  jns     short loc_180049E34
0x180049e1f  mov     r9d, eax; char *
0x180049e22  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180049e29  mov     edx, 9Bh; void *
0x180049e2e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180049e34  lea     rcx, [rsp+118h+var_A8]
0x180049e39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049e3e  mov     rbx, [rbx]
0x180049e41  mov     [rsp+118h+var_C8], rbx
0x180049e46  jmp     loc_180049D46
0x180049e4b  mov     eax, dword ptr [rsp+118h+var_C8]
0x180049e4f  mov     rcx, [rsp+118h+var_48]
0x180049e57  xor     rcx, rsp; StackCookie
0x180049e5a  call    __security_check_cookie
0x180049e5f  add     rsp, 0E8h
0x180049e66  pop     r15
0x180049e68  pop     r14
0x180049e6a  pop     r12
0x180049e6c  pop     rdi
0x180049e6d  pop     rsi
0x180049e6e  pop     rbx
0x180049e6f  retn
```
