# PolicyManager::HasPinComplexity

- ea: `0x1800529b8`
- end: `0x180052b71`
- name: `PolicyManager::HasPinComplexity`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052c20`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x180012300`
- `0x180018194`
- `0x180019c94`
- `0x18001b974`
- `0x18002c640`
- `0x1800529b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052b09`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052b09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a65`

## string_xrefs

- `0x180052a16`: `PINComplexity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyManager::HasPinComplexity(__int64 a1, bool *a2)
{
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  signed int v6; // ebx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  DWORD cValues; // [rsp+60h] [rbp+7h] BYREF
  LSTATUS v10; // [rsp+64h] [rbp+Bh] BYREF
  void **v11; // [rsp+68h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+17h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+78h] [rbp+1Fh] BYREF

  if ( !a2 )
    return 87;
  *a2 = 0;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Policies\\Microsoft\\PassportForWork");
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, L"PINComplexity");
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v11);
  v4 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 != 2 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v10 = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)&dword_1800AD4F4,
          0,
          0,
          (__int64)&v10);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = HResultToSecurityStatus(v6);
      goto LABEL_18;
    }
    *a2 = 0;
  }
  else
  {
    cValues = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    v7 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_18;
    }
    *a2 = cValues != 0;
  }
  v7 = 0;
LABEL_18:
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v11);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x1800529b8  mov     [rsp-8+arg_0], rbx
0x1800529bd  mov     [rsp-8+arg_10], rsi
0x1800529c2  push    rbp
0x1800529c3  push    rdi
0x1800529c4  push    r14
0x1800529c6  lea     rbp, [rsp-47h]
0x1800529cb  sub     rsp, 0A0h
0x1800529d2  mov     rax, cs:__security_cookie
0x1800529d9  xor     rax, rsp
0x1800529dc  mov     [rbp+57h+var_18], rax
0x1800529e0  mov     rdi, rdx
0x1800529e3  xor     esi, esi
0x1800529e5  test    rdx, rdx
0x1800529e8  jnz     short loc_1800529F2
0x1800529ea  lea     eax, [rdx+57h]
0x1800529ed  jmp     loc_180052B4C
0x1800529f2  mov     [rdx], sil
0x1800529f5  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Passport"...
0x1800529fc  lea     rcx, [rbp+57h+lpSubKey]
0x180052a00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180052a05  nop
0x180052a06  lea     rdx, asc_18008F0A4; "\\"
0x180052a0d  lea     rcx, [rbp+57h+lpSubKey]
0x180052a11  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180052a16  lea     rdx, aPincomplexity; "PINComplexity"
0x180052a1d  lea     rcx, [rbp+57h+lpSubKey]
0x180052a21  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180052a26  lea     r14, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x180052a2d  mov     [rbp+57h+var_48], r14
0x180052a31  mov     [rbp+57h+hKey], rsi
0x180052a35  lea     rcx, [rbp+57h+var_48]
0x180052a39  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180052a3e  lea     rdx, [rbp+57h+lpSubKey]
0x180052a42  cmp     [rbp+57h+var_20], 7
0x180052a47  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180052a4c  lea     rax, [rbp+57h+hKey]
0x180052a50  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180052a55  mov     r9d, 20019h; samDesired
0x180052a5b  xor     r8d, r8d; ulOptions
0x180052a5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052a65  call    cs:__imp_RegOpenKeyExW
0x180052a6c  nop     dword ptr [rax+rax+00h]
0x180052a71  mov     ebx, eax
0x180052a73  test    eax, eax
0x180052a75  jz      short loc_180052ACE
0x180052a77  cmp     eax, 2
0x180052a7a  jnz     short loc_180052A86
0x180052a7c  mov     [rdi], sil
0x180052a7f  mov     ebx, esi
0x180052a81  jmp     loc_180052B33
0x180052a86  mov     eax, cs:dword_1800BE0B8
0x180052a8c  cmp     eax, 2
0x180052a8f  jbe     short loc_180052AB6
0x180052a91  mov     [rbp+57h+var_4C], ebx
0x180052a94  lea     rax, [rbp+57h+var_4C]
0x180052a98  mov     [rsp+0B0h+phkResult], rax
0x180052a9d  xor     r9d, r9d
0x180052aa0  xor     r8d, r8d
0x180052aa3  lea     rdx, dword_1800AD4F4
0x180052aaa  lea     rcx, dword_1800BE0B8
0x180052ab1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052ab6  test    ebx, ebx
0x180052ab8  jle     short loc_180052AC3
0x180052aba  movzx   ebx, bx
0x180052abd  or      ebx, 80070000h
0x180052ac3  mov     ecx, ebx; int
0x180052ac5  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180052aca  mov     ebx, eax
0x180052acc  jmp     short loc_180052B33
0x180052ace  mov     [rbp+57h+cValues], esi
0x180052ad1  mov     [rsp+0B0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180052ad6  mov     [rsp+0B0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180052adb  mov     [rsp+0B0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180052ae0  mov     [rsp+0B0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180052ae5  lea     rax, [rbp+57h+cValues]
0x180052ae9  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x180052aee  mov     [rsp+0B0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180052af3  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180052af8  mov     [rsp+0B0h+phkResult], rsi; lpcSubKeys
0x180052afd  xor     r9d, r9d; lpReserved
0x180052b00  xor     r8d, r8d; lpcchClass
0x180052b03  xor     edx, edx; lpClass
0x180052b05  mov     rcx, [rbp+57h+hKey]; hKey
0x180052b09  call    cs:__imp_RegQueryInfoKeyW
0x180052b10  nop     dword ptr [rax+rax+00h]
0x180052b15  mov     ebx, eax
0x180052b17  test    eax, eax
0x180052b19  jnz     short loc_180052B28
0x180052b1b  cmp     [rbp+57h+cValues], esi
0x180052b1e  setnz   al
0x180052b21  mov     [rdi], al
0x180052b23  jmp     loc_180052A7F
0x180052b28  jle     short loc_180052B33
0x180052b2a  movzx   ebx, ax
0x180052b2d  or      ebx, 80070000h
0x180052b33  mov     [rbp+57h+var_48], r14
0x180052b37  lea     rcx, [rbp+57h+var_48]
0x180052b3b  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180052b40  nop
0x180052b41  lea     rcx, [rbp+57h+lpSubKey]
0x180052b45  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180052b4a  mov     eax, ebx
0x180052b4c  mov     rcx, [rbp+57h+var_18]
0x180052b50  xor     rcx, rsp; StackCookie
0x180052b53  call    __security_check_cookie
0x180052b58  lea     r11, [rsp+0B0h+var_10]
0x180052b60  mov     rbx, [r11+20h]
0x180052b64  mov     rsi, [r11+30h]
0x180052b68  mov     rsp, r11
0x180052b6b  pop     r14
0x180052b6d  pop     rdi
0x180052b6e  pop     rbp
0x180052b6f  retn
```
