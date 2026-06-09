# GetMachineSid(void * *)

- ea: `0x18000edb4`
- end: `0x18000ef6b`
- name: `?GetMachineSid@@YAJPEAPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016400`
- `0x180016718`

## callees

- `0x18000e530`
- `0x18000edb4`
- `0x18000ef74`
- `0x18000f034`
- `0x1800158b8`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000edfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000edfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef40`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ee57`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ef10`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ee57`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ef10`

## pseudocode

```c
__int64 __fastcall GetMachineSid(void **a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  void **unique; // rax
  __int64 v6; // rdx
  void *v7; // rdi
  HLOCAL v8; // rcx
  signed int v9; // eax
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-19h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-15h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-11h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-9h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-5h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+48h] [rbp-1h] BYREF
  void *v17; // [rsp+50h] [rbp+7h]
  WCHAR Buffer[16]; // [rsp+58h] [rbp+Fh] BYREF

  nSize = 16;
  ReferencedDomainName = 0;
  v17 = 0;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !LookupAccountNameLocalW(Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
  {
    v4 = GetLastError();
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 != -2147024774 )
      goto LABEL_17;
  }
  unique = (void **)wil::make_unique_hlocal<unsigned char [0]>(&hMem);
  v7 = *unique;
  *unique = 0;
  v17 = v7;
  v8 = hMem;
  hMem = 0;
  if ( v8 )
    LocalFree(v8);
  if ( !v7
    || (wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &hMem,
          v6,
          cchReferencedDomainName),
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &ReferencedDomainName,
          hMem),
        hMem = 0,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem),
        !ReferencedDomainName) )
  {
    v3 = -2147024882;
    goto LABEL_18;
  }
  if ( LookupAccountNameLocalW(Buffer, v7, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v3 = 0;
    *a1 = v7;
LABEL_17:
    v7 = 0;
    goto LABEL_18;
  }
  v9 = GetLastError();
  v3 = v9;
  if ( v9 > 0 )
    v3 = (unsigned __int16)v9 | 0x80070000;
LABEL_18:
  if ( v7 )
    LocalFree(v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&ReferencedDomainName);
  return v3;
}

```

## disassembly

```asm
0x18000edb4  push    rbp
0x18000edb6  push    rbx
0x18000edb7  push    rdi
0x18000edb8  push    r14
0x18000edba  lea     rbp, [rsp-3Fh]
0x18000edbf  sub     rsp, 88h
0x18000edc6  mov     rax, cs:__security_cookie
0x18000edcd  xor     rax, rsp
0x18000edd0  mov     [rbp+57h+var_28], rax
0x18000edd4  mov     r14, rcx
0x18000edd7  mov     [rbp+57h+nSize], 10h
0x18000edde  mov     [rbp+57h+ReferencedDomainName], 0
0x18000ede6  mov     [rbp+57h+var_50], 0
0x18000edee  lea     r8, [rbp+57h+nSize]; nSize
0x18000edf2  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000edf6  mov     ecx, 4; NameType
0x18000edfb  call    cs:__imp_GetComputerNameExW
0x18000ee01  test    eax, eax
0x18000ee03  jnz     short loc_18000EE23
0x18000ee05  call    cs:__imp_GetLastError
0x18000ee0b  mov     ebx, eax
0x18000ee0d  test    eax, eax
0x18000ee0f  jle     loc_18000EF36
0x18000ee15  movzx   ebx, ax
0x18000ee18  or      ebx, 80070000h
0x18000ee1e  jmp     loc_18000EF36
0x18000ee23  mov     [rbp+57h+cbSid], 0
0x18000ee2a  mov     [rbp+57h+var_70], 0
0x18000ee31  mov     [rbp+57h+var_60], 0
0x18000ee38  lea     rax, [rbp+57h+var_60]
0x18000ee3c  mov     [rsp+0A0h+peUse], rax; peUse
0x18000ee41  lea     rax, [rbp+57h+var_70]
0x18000ee45  mov     [rsp+0A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000ee4a  xor     r9d, r9d; ReferencedDomainName
0x18000ee4d  lea     r8, [rbp+57h+cbSid]; cbSid
0x18000ee51  xor     edx, edx; Sid
0x18000ee53  lea     rcx, [rbp+57h+Buffer]; lpAccountName
0x18000ee57  call    cs:__imp_LookupAccountNameLocalW
0x18000ee5d  test    eax, eax
0x18000ee5f  jnz     short loc_18000EE82
0x18000ee61  call    cs:__imp_GetLastError
0x18000ee67  mov     ebx, eax
0x18000ee69  test    eax, eax
0x18000ee6b  jle     short loc_18000EE76
0x18000ee6d  movzx   ebx, ax
0x18000ee70  or      ebx, 80070000h
0x18000ee76  cmp     ebx, 8007007Ah
0x18000ee7c  jnz     loc_18000EF36
0x18000ee82  mov     edx, [rbp+57h+cbSid]
0x18000ee85  lea     rcx, [rbp+57h+hMem]
0x18000ee89  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x18000ee8e  mov     rdi, [rax]
0x18000ee91  mov     qword ptr [rax], 0
0x18000ee98  mov     [rbp+57h+var_50], rdi
0x18000ee9c  mov     rcx, [rbp+57h+hMem]; hMem
0x18000eea0  mov     [rbp+57h+hMem], 0
0x18000eea8  test    rcx, rcx
0x18000eeab  jz      short loc_18000EEB3
0x18000eead  call    cs:__imp_LocalFree
0x18000eeb3  test    rdi, rdi
0x18000eeb6  jnz     short loc_18000EEBF
0x18000eeb8  mov     ebx, 8007000Eh
0x18000eebd  jmp     short loc_18000EF38
0x18000eebf  mov     r8d, [rbp+57h+var_70]
0x18000eec3  lea     rcx, [rbp+57h+hMem]
0x18000eec7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000eecc  mov     rdx, [rbp+57h+hMem]
0x18000eed0  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18000eed4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000eed9  mov     [rbp+57h+hMem], 0
0x18000eee1  lea     rcx, [rbp+57h+hMem]
0x18000eee5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000eeea  mov     r9, [rbp+57h+ReferencedDomainName]; ReferencedDomainName
0x18000eeee  test    r9, r9
0x18000eef1  jz      short loc_18000EEB8
0x18000eef3  lea     rax, [rbp+57h+var_60]
0x18000eef7  mov     [rsp+0A0h+peUse], rax; peUse
0x18000eefc  lea     rax, [rbp+57h+var_70]
0x18000ef00  mov     [rsp+0A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000ef05  lea     r8, [rbp+57h+cbSid]; cbSid
0x18000ef09  mov     rdx, rdi; Sid
0x18000ef0c  lea     rcx, [rbp+57h+Buffer]; lpAccountName
0x18000ef10  call    cs:__imp_LookupAccountNameLocalW
0x18000ef16  test    eax, eax
0x18000ef18  jnz     short loc_18000EF31
0x18000ef1a  call    cs:__imp_GetLastError
0x18000ef20  mov     ebx, eax
0x18000ef22  test    eax, eax
0x18000ef24  jle     short loc_18000EF38
0x18000ef26  movzx   ebx, ax
0x18000ef29  or      ebx, 80070000h
0x18000ef2f  jmp     short loc_18000EF38
0x18000ef31  xor     ebx, ebx
0x18000ef33  mov     [r14], rdi
0x18000ef36  xor     edi, edi
0x18000ef38  test    rdi, rdi
0x18000ef3b  jz      short loc_18000EF47
0x18000ef3d  mov     rcx, rdi; hMem
0x18000ef40  call    cs:__imp_LocalFree
0x18000ef46  nop
0x18000ef47  lea     rcx, [rbp+57h+ReferencedDomainName]
0x18000ef4b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000ef50  mov     eax, ebx
0x18000ef52  mov     rcx, [rbp+57h+var_28]
0x18000ef56  xor     rcx, rsp; StackCookie
0x18000ef59  call    __security_check_cookie
0x18000ef5e  add     rsp, 88h
0x18000ef65  pop     r14
0x18000ef67  pop     rdi
0x18000ef68  pop     rbx
0x18000ef69  pop     rbp
0x18000ef6a  retn
```
