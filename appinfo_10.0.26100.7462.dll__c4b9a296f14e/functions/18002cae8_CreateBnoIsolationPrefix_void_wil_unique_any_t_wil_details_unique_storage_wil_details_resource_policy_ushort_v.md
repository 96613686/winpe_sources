# CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002cae8`
- end: `0x18002cbfa`
- name: `?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014da0`
- `0x18002cc00`

## callees

- `0x180010850`
- `0x1800125ac`
- `0x180012634`
- `0x180018400`
- `0x18001847c`
- `0x180018530`
- `0x18002cae8`
- `0x180044a20`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002cb18`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002cb18`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cba5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cba5`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002cb65`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002cb65`

## string_xrefs

- `0x18002cb30`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cb7d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cbbd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall CreateBnoIsolationPrefix(void *a1, LPWSTR *a2)
{
  unsigned int PackageFamilyNameFromToken; // eax
  int v5; // eax
  unsigned int LastError; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  PSID Sid; // [rsp+20h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+28h] [rbp-B0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+30h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  packageFamilyNameLength = 65;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(a1, &packageFamilyNameLength, packageFamilyName);
  if ( PackageFamilyNameFromToken )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1CD,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             (const char *)PackageFamilyNameFromToken,
             (unsigned int)Sid);
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  v5 = PackageSidFromFamilyName(packageFamilyName, &Sid);
  if ( v5 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a2,
      0);
    if ( ConvertSidToStringSidW(Sid, a2) )
    {
      v8 = 0;
      goto LABEL_9;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1D0,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1CF,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)(unsigned int)v5,
                  (int)Sid);
  }
  v8 = LastError;
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return v8;
}

```

## disassembly

```asm
0x18002cae8  push    rbx
0x18002caea  sub     rsp, 0D0h
0x18002caf1  mov     rax, cs:__security_cookie
0x18002caf8  xor     rax, rsp
0x18002cafb  mov     [rsp+0D8h+var_18], rax
0x18002cb03  mov     rbx, rdx
0x18002cb06  mov     [rsp+0D8h+packageFamilyNameLength], 41h ; 'A'
0x18002cb0e  lea     rdx, [rsp+0D8h+packageFamilyNameLength]; packageFamilyNameLength
0x18002cb13  lea     r8, [rsp+0D8h+packageFamilyName]; packageFamilyName
0x18002cb18  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002cb1f  nop     dword ptr [rax+rax+00h]
0x18002cb24  test    eax, eax
0x18002cb26  jz      short loc_18002CB49
0x18002cb28  mov     rcx, [rsp+0D8h]; this
0x18002cb30  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cb37  mov     r9d, eax; char *
0x18002cb3a  mov     edx, 1CDh; void *
0x18002cb3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cb44  jmp     loc_18002CBE0
0x18002cb49  and     [rsp+0D8h+Sid], 0
0x18002cb4f  lea     rcx, [rsp+0D8h+Sid]
0x18002cb54  xor     edx, edx
0x18002cb56  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002cb5b  lea     rdx, [rsp+0D8h+Sid]
0x18002cb60  lea     rcx, [rsp+0D8h+packageFamilyName]
0x18002cb65  call    cs:__imp_PackageSidFromFamilyName
0x18002cb6c  nop     dword ptr [rax+rax+00h]
0x18002cb71  test    eax, eax
0x18002cb73  jns     short loc_18002CB93
0x18002cb75  mov     rcx, [rsp+0D8h]; this
0x18002cb7d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cb84  mov     r9d, eax; char *
0x18002cb87  mov     edx, 1CFh; void *
0x18002cb8c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002cb91  jmp     short loc_18002CBCE
0x18002cb93  xor     edx, edx
0x18002cb95  mov     rcx, rbx
0x18002cb98  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cb9d  mov     rcx, [rsp+0D8h+Sid]; Sid
0x18002cba2  mov     rdx, rbx; StringSid
0x18002cba5  call    cs:__imp_ConvertSidToStringSidW
0x18002cbac  nop     dword ptr [rax+rax+00h]
0x18002cbb1  test    eax, eax
0x18002cbb3  jnz     short loc_18002CBD2
0x18002cbb5  mov     rcx, [rsp+0D8h]; this
0x18002cbbd  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cbc4  mov     edx, 1D0h; void *
0x18002cbc9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cbce  mov     ebx, eax
0x18002cbd0  jmp     short loc_18002CBD4
0x18002cbd2  xor     ebx, ebx
0x18002cbd4  lea     rcx, [rsp+0D8h+Sid]
0x18002cbd9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cbde  mov     eax, ebx
0x18002cbe0  mov     rcx, [rsp+0D8h+var_18]
0x18002cbe8  xor     rcx, rsp; StackCookie
0x18002cbeb  call    __security_check_cookie
0x18002cbf0  add     rsp, 0D0h
0x18002cbf7  pop     rbx
0x18002cbf8  retn
```
