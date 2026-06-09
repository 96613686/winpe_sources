# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18005d088`
- end: `0x18005d1cb`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `323`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d1d4`

## callees

- `0x180007270`
- `0x180054ec0`
- `0x1800583bc`
- `0x18005cfac`
- `0x18005d010`
- `0x18005d088`
- `0x18005d6e0`
- `0x18006e950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d0e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d0e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005d11b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005d11b`

## pseudocode

```c
__int64 __fastcall GetComponentCVForEnrollmentId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        HKEY a4)
{
  int v7; // ebx
  char *v8; // rcx
  char *v10; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-BCh] BYREF
  char **v14; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, L"OmaDmSession", 0, 0, (LPBYTE)Data, &cbData) )
  {
    v10 = 0;
    v14 = &v10;
    v15 = 0;
    v16 = 1;
    v7 = UnicodeToMB(Data, 0xFDE9u, &v15, &v13);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v14);
    if ( v7 >= 0 )
      StringCchCopyA(a3, 0x81u, v10);
    v8 = v10;
    v10 = 0;
    if ( v8 )
      MemoryFree(v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x18005d088  mov     [rsp-8+arg_0], rbx
0x18005d08d  push    rbp
0x18005d08e  push    rsi
0x18005d08f  push    rdi
0x18005d090  lea     rbp, [rsp-80h]
0x18005d095  sub     rsp, 180h
0x18005d09c  mov     rax, cs:__security_cookie
0x18005d0a3  xor     rax, rsp
0x18005d0a6  mov     [rbp+90h+var_20], rax
0x18005d0aa  mov     rbx, rdx
0x18005d0ad  mov     [rsp+190h+hKey], 0
0x18005d0b6  xor     edx, edx
0x18005d0b8  lea     rcx, [rsp+190h+hKey]
0x18005d0bd  mov     rdi, r9
0x18005d0c0  mov     rsi, r8
0x18005d0c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005d0c8  lea     rax, [rsp+190h+hKey]
0x18005d0cd  mov     r9d, 20019h; samDesired
0x18005d0d3  xor     r8d, r8d; ulOptions
0x18005d0d6  mov     [rsp+190h+phkResult], rax; phkResult
0x18005d0db  mov     rdx, rbx; lpSubKey
0x18005d0de  mov     rcx, rdi; hKey
0x18005d0e1  call    cs:__imp_RegOpenKeyExW
0x18005d0e8  nop     dword ptr [rax+rax+00h]
0x18005d0ed  mov     rcx, [rsp+190h+hKey]; hKey
0x18005d0f2  lea     rax, [rsp+190h+cbData]
0x18005d0f7  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18005d0fc  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x18005d103  lea     rax, [rsp+190h+Data]
0x18005d108  mov     [rsp+190h+cbData], 102h
0x18005d110  xor     r9d, r9d; lpType
0x18005d113  mov     [rsp+190h+phkResult], rax; lpData
0x18005d118  xor     r8d, r8d; lpReserved
0x18005d11b  call    cs:__imp_RegQueryValueExW
0x18005d122  nop     dword ptr [rax+rax+00h]
0x18005d127  test    eax, eax
0x18005d129  jnz     short loc_18005D19F
0x18005d12b  lea     rax, [rsp+190h+var_160]
0x18005d130  mov     [rsp+190h+var_160], 0
0x18005d139  lea     r9, [rsp+190h+var_14C]; unsigned int *
0x18005d13e  mov     [rsp+190h+var_148], rax
0x18005d143  lea     r8, [rsp+190h+var_140]; char **
0x18005d148  mov     [rsp+190h+var_140], 0
0x18005d151  mov     edx, 0FDE9h; CodePage
0x18005d156  mov     [rsp+190h+var_138], 1
0x18005d15b  lea     rcx, [rsp+190h+Data]; lpWideCharStr
0x18005d160  call    ?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18005d165  lea     rcx, [rsp+190h+var_148]
0x18005d16a  mov     ebx, eax
0x18005d16c  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18005d171  test    ebx, ebx
0x18005d173  js      short loc_18005D187
0x18005d175  mov     r8, [rsp+190h+var_160]; char *
0x18005d17a  mov     edx, 81h; unsigned __int64
0x18005d17f  mov     rcx, rsi; char *
0x18005d182  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d187  mov     rcx, [rsp+190h+var_160]; void *
0x18005d18c  mov     [rsp+190h+var_160], 0
0x18005d195  test    rcx, rcx
0x18005d198  jz      short loc_18005D19F
0x18005d19a  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18005d19f  lea     rcx, [rsp+190h+hKey]
0x18005d1a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005d1a9  xor     eax, eax
0x18005d1ab  mov     rcx, [rbp+90h+var_20]
0x18005d1af  xor     rcx, rsp; StackCookie
0x18005d1b2  call    __security_check_cookie
0x18005d1b7  mov     rbx, [rsp+190h+arg_0]
0x18005d1bf  add     rsp, 180h
0x18005d1c6  pop     rdi
0x18005d1c7  pop     rsi
0x18005d1c8  pop     rbp
0x18005d1c9  retn
```
