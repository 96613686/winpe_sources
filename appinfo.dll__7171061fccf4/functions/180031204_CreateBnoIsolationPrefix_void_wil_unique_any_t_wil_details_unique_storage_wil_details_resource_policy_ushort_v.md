# CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180031204`
- end: `0x180031306`
- name: `?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(void *, LPWSTR *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bb18`
- `0x18003130c`

## callees

- `0x180010430`
- `0x1800111ec`
- `0x180011414`
- `0x180018190`
- `0x180018dbc`
- `0x18001a0d4`
- `0x180031204`
- `0x180046e50`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180031234`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180031234`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800312b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800312b8`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18003127e`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x18003127e`

## string_xrefs

- `0x180031246`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180031290`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800312ca`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x2D8,
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
                  (void *)0x2DB,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x2DA,
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
0x180031204  push    rbx
0x180031206  sub     rsp, 0D0h
0x18003120d  mov     rax, cs:__security_cookie
0x180031214  xor     rax, rsp
0x180031217  mov     [rsp+0D8h+var_18], rax
0x18003121f  mov     rbx, rdx
0x180031222  mov     [rsp+0D8h+packageFamilyNameLength], 41h ; 'A'
0x18003122a  lea     rdx, [rsp+0D8h+packageFamilyNameLength]; packageFamilyNameLength
0x18003122f  lea     r8, [rsp+0D8h+packageFamilyName]; packageFamilyName
0x180031234  call    cs:__imp_GetPackageFamilyNameFromToken
0x18003123a  test    eax, eax
0x18003123c  jz      short loc_18003125F
0x18003123e  mov     rcx, [rsp+0D8h]; this
0x180031246  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003124d  mov     r9d, eax; char *
0x180031250  mov     edx, 2D8h; void *
0x180031255  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003125a  jmp     loc_1800312ED
0x18003125f  xor     edx, edx
0x180031261  mov     [rsp+0D8h+Sid], 0; int
0x18003126a  lea     rcx, [rsp+0D8h+Sid]
0x18003126f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031274  lea     rdx, [rsp+0D8h+Sid]
0x180031279  lea     rcx, [rsp+0D8h+packageFamilyName]
0x18003127e  call    cs:__imp_PackageSidFromFamilyName
0x180031284  test    eax, eax
0x180031286  jns     short loc_1800312A6
0x180031288  mov     rcx, [rsp+0D8h]; this
0x180031290  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180031297  mov     r9d, eax; char *
0x18003129a  mov     edx, 2DAh; void *
0x18003129f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800312a4  jmp     short loc_1800312DB
0x1800312a6  xor     edx, edx
0x1800312a8  mov     rcx, rbx
0x1800312ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800312b0  mov     rcx, [rsp+0D8h+Sid]; Sid
0x1800312b5  mov     rdx, rbx; StringSid
0x1800312b8  call    cs:__imp_ConvertSidToStringSidW
0x1800312be  test    eax, eax
0x1800312c0  jnz     short loc_1800312DF
0x1800312c2  mov     rcx, [rsp+0D8h]; this
0x1800312ca  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800312d1  mov     edx, 2DBh; void *
0x1800312d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800312db  mov     ebx, eax
0x1800312dd  jmp     short loc_1800312E1
0x1800312df  xor     ebx, ebx
0x1800312e1  lea     rcx, [rsp+0D8h+Sid]
0x1800312e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800312eb  mov     eax, ebx
0x1800312ed  mov     rcx, [rsp+0D8h+var_18]
0x1800312f5  xor     rcx, rsp; StackCookie
0x1800312f8  call    __security_check_cookie
0x1800312fd  add     rsp, 0D0h
0x180031304  pop     rbx
0x180031305  retn
```
