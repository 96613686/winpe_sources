# CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002ca18`
- end: `0x18002cb2a`
- name: `?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014da0`
- `0x18002cb30`

## callees

- `0x180010850`
- `0x1800125ac`
- `0x180012634`
- `0x180018400`
- `0x18001847c`
- `0x180018530`
- `0x18002ca18`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002ca48`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002ca48`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cad5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002cad5`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002ca95`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002ca95`

## string_xrefs

- `0x18002ca60`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002caad`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002caed`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1CC,
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
                  (void *)0x1CF,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1CE,
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
0x18002ca18  push    rbx
0x18002ca1a  sub     rsp, 0D0h
0x18002ca21  mov     rax, cs:__security_cookie
0x18002ca28  xor     rax, rsp
0x18002ca2b  mov     [rsp+0D8h+var_18], rax
0x18002ca33  mov     rbx, rdx
0x18002ca36  mov     [rsp+0D8h+packageFamilyNameLength], 41h ; 'A'
0x18002ca3e  lea     rdx, [rsp+0D8h+packageFamilyNameLength]; packageFamilyNameLength
0x18002ca43  lea     r8, [rsp+0D8h+packageFamilyName]; packageFamilyName
0x18002ca48  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002ca4f  nop     dword ptr [rax+rax+00h]
0x18002ca54  test    eax, eax
0x18002ca56  jz      short loc_18002CA79
0x18002ca58  mov     rcx, [rsp+0D8h]; this
0x18002ca60  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002ca67  mov     r9d, eax; char *
0x18002ca6a  mov     edx, 1CCh; void *
0x18002ca6f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ca74  jmp     loc_18002CB10
0x18002ca79  and     [rsp+0D8h+Sid], 0
0x18002ca7f  lea     rcx, [rsp+0D8h+Sid]
0x18002ca84  xor     edx, edx
0x18002ca86  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002ca8b  lea     rdx, [rsp+0D8h+Sid]
0x18002ca90  lea     rcx, [rsp+0D8h+packageFamilyName]
0x18002ca95  call    cs:__imp_PackageSidFromFamilyName
0x18002ca9c  nop     dword ptr [rax+rax+00h]
0x18002caa1  test    eax, eax
0x18002caa3  jns     short loc_18002CAC3
0x18002caa5  mov     rcx, [rsp+0D8h]; this
0x18002caad  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cab4  mov     r9d, eax; char *
0x18002cab7  mov     edx, 1CEh; void *
0x18002cabc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002cac1  jmp     short loc_18002CAFE
0x18002cac3  xor     edx, edx
0x18002cac5  mov     rcx, rbx
0x18002cac8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cacd  mov     rcx, [rsp+0D8h+Sid]; Sid
0x18002cad2  mov     rdx, rbx; StringSid
0x18002cad5  call    cs:__imp_ConvertSidToStringSidW
0x18002cadc  nop     dword ptr [rax+rax+00h]
0x18002cae1  test    eax, eax
0x18002cae3  jnz     short loc_18002CB02
0x18002cae5  mov     rcx, [rsp+0D8h]; this
0x18002caed  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002caf4  mov     edx, 1CFh; void *
0x18002caf9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cafe  mov     ebx, eax
0x18002cb00  jmp     short loc_18002CB04
0x18002cb02  xor     ebx, ebx
0x18002cb04  lea     rcx, [rsp+0D8h+Sid]
0x18002cb09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cb0e  mov     eax, ebx
0x18002cb10  mov     rcx, [rsp+0D8h+var_18]
0x18002cb18  xor     rcx, rsp; StackCookie
0x18002cb1b  call    __security_check_cookie
0x18002cb20  add     rsp, 0D0h
0x18002cb27  pop     rbx
0x18002cb28  retn
```
