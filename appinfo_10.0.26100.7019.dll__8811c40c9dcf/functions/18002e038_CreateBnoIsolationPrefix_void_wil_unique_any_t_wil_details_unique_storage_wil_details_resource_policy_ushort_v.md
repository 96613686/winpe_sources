# CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18002e038`
- end: `0x18002e14a`
- name: `?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014d40`
- `0x18002e150`

## callees

- `0x180010710`
- `0x18001246c`
- `0x1800124f4`
- `0x180018150`
- `0x1800181cc`
- `0x180018280`
- `0x18002e038`
- `0x180042950`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002e068`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002e068`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002e0f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002e0f5`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002e0b5`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18002e0b5`

## string_xrefs

- `0x18002e080`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e0cd`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e10d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1CE,
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
                  (void *)0x1D1,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x1D0,
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
0x18002e038  push    rbx
0x18002e03a  sub     rsp, 0D0h
0x18002e041  mov     rax, cs:__security_cookie
0x18002e048  xor     rax, rsp
0x18002e04b  mov     [rsp+0D8h+var_18], rax
0x18002e053  mov     rbx, rdx
0x18002e056  mov     [rsp+0D8h+packageFamilyNameLength], 41h ; 'A'
0x18002e05e  lea     rdx, [rsp+0D8h+packageFamilyNameLength]; packageFamilyNameLength
0x18002e063  lea     r8, [rsp+0D8h+packageFamilyName]; packageFamilyName
0x18002e068  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002e06f  nop     dword ptr [rax+rax+00h]
0x18002e074  test    eax, eax
0x18002e076  jz      short loc_18002E099
0x18002e078  mov     rcx, [rsp+0D8h]; this
0x18002e080  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e087  mov     r9d, eax; char *
0x18002e08a  mov     edx, 1CEh; void *
0x18002e08f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e094  jmp     loc_18002E130
0x18002e099  and     [rsp+0D8h+Sid], 0
0x18002e09f  lea     rcx, [rsp+0D8h+Sid]
0x18002e0a4  xor     edx, edx
0x18002e0a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002e0ab  lea     rdx, [rsp+0D8h+Sid]
0x18002e0b0  lea     rcx, [rsp+0D8h+packageFamilyName]
0x18002e0b5  call    cs:__imp_PackageSidFromFamilyName
0x18002e0bc  nop     dword ptr [rax+rax+00h]
0x18002e0c1  test    eax, eax
0x18002e0c3  jns     short loc_18002E0E3
0x18002e0c5  mov     rcx, [rsp+0D8h]; this
0x18002e0cd  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e0d4  mov     r9d, eax; char *
0x18002e0d7  mov     edx, 1D0h; void *
0x18002e0dc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e0e1  jmp     short loc_18002E11E
0x18002e0e3  xor     edx, edx
0x18002e0e5  mov     rcx, rbx
0x18002e0e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e0ed  mov     rcx, [rsp+0D8h+Sid]; Sid
0x18002e0f2  mov     rdx, rbx; StringSid
0x18002e0f5  call    cs:__imp_ConvertSidToStringSidW
0x18002e0fc  nop     dword ptr [rax+rax+00h]
0x18002e101  test    eax, eax
0x18002e103  jnz     short loc_18002E122
0x18002e105  mov     rcx, [rsp+0D8h]; this
0x18002e10d  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e114  mov     edx, 1D1h; void *
0x18002e119  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e11e  mov     ebx, eax
0x18002e120  jmp     short loc_18002E124
0x18002e122  xor     ebx, ebx
0x18002e124  lea     rcx, [rsp+0D8h+Sid]
0x18002e129  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e12e  mov     eax, ebx
0x18002e130  mov     rcx, [rsp+0D8h+var_18]
0x18002e138  xor     rcx, rsp; StackCookie
0x18002e13b  call    __security_check_cookie
0x18002e140  add     rsp, 0D0h
0x18002e147  pop     rbx
0x18002e148  retn
```
