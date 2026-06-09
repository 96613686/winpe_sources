# _lambda_6a2b86f1dd55d0ddce5a2314f7d10145_::operator()

- ea: `0x14000f98c`
- end: `0x14000faea`
- name: `_lambda_6a2b86f1dd55d0ddce5a2314f7d10145_::operator()`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f30`
- `0x14000c214`
- `0x14000ed38`
- `0x14000f98c`
- `0x14001f3f8`
- `0x140029eb8`
- `0x14002a3e8`
- `0x14002c070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14000f9b1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14000f9b1`
- `KERNEL32!RegOpenKeyExW` at `0x14000fa5a`
- `KERNEL32!RegOpenKeyExW` at `0x14000fa5a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000fa9a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14000fa9a`

## string_xrefs

- `0x14000faac`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x14000fa0c`: `Recommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_6a2b86f1dd55d0ddce5a2314f7d10145_::operator()(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // eax
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  HKEY *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rdx
  const void *v10; // rax
  DWORD cbData; // edx
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v15[2]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v1 = _o__wtoi(*(_QWORD *)(**(_QWORD **)a1 + 8LL));
  v15[0] = 0;
  v15[1] = _mm_load_si128((const __m128i *)&_xmm);
  v2 = 0;
  LOWORD(v15[0]) = 0;
  if ( !v1 )
  {
    v5 = L"Anywhere";
    v6 = 8;
LABEL_10:
    std::wstring::_Assign<unsigned short>(v15, v5, v6);
    hKey = 0;
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer", 0, 2u, v7);
    if ( v8 )
    {
      v9 = 2010;
    }
    else
    {
      v10 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      v8 = RegSetKeyValueW(hKey, 0, L"AicEnabled", 1u, v10, cbData);
      if ( !v8 )
      {
LABEL_15:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_16;
      }
      v9 = 2014;
    }
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
           (const char *)v8,
           phkResult);
    goto LABEL_15;
  }
  v3 = v1 - 1;
  if ( !v3 )
  {
    v5 = L"Recommendations";
    v6 = 15;
    goto LABEL_10;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v5 = L"PreferStore";
    v6 = 11;
    goto LABEL_10;
  }
  if ( v4 == 1 )
  {
    v5 = L"StoreOnly";
    v6 = 9;
    goto LABEL_10;
  }
  v2 = -2147418113;
LABEL_16:
  std::wstring::_Tidy_deallocate(v15);
  return v2;
}

```

## disassembly

```asm
0x14000f98c  mov     [rsp-8+arg_8], rbx
0x14000f991  push    rbp
0x14000f992  mov     rbp, rsp
0x14000f995  sub     rsp, 60h
0x14000f999  mov     rax, cs:__security_cookie
0x14000f9a0  xor     rax, rsp
0x14000f9a3  mov     [rbp+var_8], rax
0x14000f9a7  mov     rax, [rcx]
0x14000f9aa  mov     rcx, [rax]
0x14000f9ad  mov     rcx, [rcx+8]
0x14000f9b1  call    cs:__imp__o__wtoi
0x14000f9b7  xorps   xmm0, xmm0
0x14000f9ba  movups  [rbp+var_28], xmm0
0x14000f9be  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000f9c6  movdqu  [rbp+var_18], xmm1
0x14000f9cb  xor     ebx, ebx
0x14000f9cd  mov     word ptr [rbp+var_28], bx
0x14000f9d1  test    eax, eax
0x14000f9d3  jz      short loc_14000FA1B
0x14000f9d5  sub     eax, 1
0x14000f9d8  jz      short loc_14000FA0C
0x14000f9da  sub     eax, 1
0x14000f9dd  jz      short loc_14000F9FD
0x14000f9df  cmp     eax, 1
0x14000f9e2  jz      short loc_14000F9EE
0x14000f9e4  mov     ebx, 8000FFFFh
0x14000f9e9  jmp     loc_14000FAC8
0x14000f9ee  lea     rdx, aStoreonly; "StoreOnly"
0x14000f9f5  mov     r8d, 9
0x14000f9fb  jmp     short loc_14000FA28
0x14000f9fd  lea     rdx, aPreferstore; "PreferStore"
0x14000fa04  mov     r8d, 0Bh
0x14000fa0a  jmp     short loc_14000FA28
0x14000fa0c  lea     rdx, aRecommendation; "Recommendations"
0x14000fa13  mov     r8d, 0Fh
0x14000fa19  jmp     short loc_14000FA28
0x14000fa1b  lea     rdx, aAnywhere; "Anywhere"
0x14000fa22  mov     r8d, 8
0x14000fa28  lea     rcx, [rbp+var_28]
0x14000fa2c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14000fa31  mov     [rbp+hKey], rbx
0x14000fa35  lea     rcx, [rbp+hKey]
0x14000fa39  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14000fa3e  mov     [rsp+60h+phkResult], rax; phkResult
0x14000fa43  mov     r9d, 2; samDesired
0x14000fa49  xor     r8d, r8d; ulOptions
0x14000fa4c  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000fa53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fa5a  call    cs:__imp_RegOpenKeyExW
0x14000fa60  test    eax, eax
0x14000fa62  jz      short loc_14000FA6B
0x14000fa64  mov     edx, 7DAh
0x14000fa69  jmp     short loc_14000FAA9
0x14000fa6b  mov     eax, dword ptr [rbp+var_18]
0x14000fa6e  lea     edx, ds:2[rax*2]
0x14000fa75  lea     rcx, [rbp+var_28]
0x14000fa79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14000fa7e  mov     [rsp+60h+cbData], edx; cbData
0x14000fa82  mov     [rsp+60h+phkResult], rax; unsigned int
0x14000fa87  mov     r9d, 1; dwType
0x14000fa8d  lea     r8, ValueName; "AicEnabled"
0x14000fa94  xor     edx, edx; lpSubKey
0x14000fa96  mov     rcx, [rbp+hKey]; hKey
0x14000fa9a  call    cs:__imp_RegSetKeyValueW
0x14000faa0  test    eax, eax
0x14000faa2  jz      short loc_14000FABE
0x14000faa4  mov     edx, 7DEh; void *
0x14000faa9  mov     r9d, eax; char *
0x14000faac  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x14000fab3  mov     rcx, [rbp+8]; this
0x14000fab7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000fabc  mov     ebx, eax
0x14000fabe  lea     rcx, [rbp+hKey]
0x14000fac2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000fac7  nop
0x14000fac8  lea     rcx, [rbp+var_28]
0x14000facc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000fad1  mov     eax, ebx
0x14000fad3  mov     rcx, [rbp+var_8]
0x14000fad7  xor     rcx, rsp; StackCookie
0x14000fada  call    __security_check_cookie
0x14000fadf  mov     rbx, [rsp+60h+arg_8]
0x14000fae4  add     rsp, 60h
0x14000fae8  pop     rbp
0x14000fae9  retn
```
