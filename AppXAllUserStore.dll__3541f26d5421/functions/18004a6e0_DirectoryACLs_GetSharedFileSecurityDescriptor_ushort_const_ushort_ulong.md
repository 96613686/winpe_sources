# DirectoryACLs::GetSharedFileSecurityDescriptor(ushort const *,ushort * *,ulong *)

- ea: `0x18004a6e0`
- end: `0x18004a7e6`
- name: `?GetSharedFileSecurityDescriptor@DirectoryACLs@@YAJPEBGPEAPEAGPEAK@Z`
- size: `262`
- prototype: `int(DirectoryACLs *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004954c`

## callees

- `0x18001a324`
- `0x18001a604`
- `0x180040880`
- `0x1800455bc`
- `0x18004a6e0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18004a784`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18004a784`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18004a730`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18004a730`

## string_xrefs

- `0x18004a73f`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x18004a793`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c
__int64 __fastcall DirectoryACLs::GetSharedFileSecurityDescriptor(
        WCHAR *this,
        unsigned __int16 *a2,
        ULONG *a3,
        unsigned int *a4)
{
  DWORD NamedSecurityInfoW; // eax
  unsigned int LastError; // ebx
  const char *v8; // r9
  unsigned int StringSecurityDescriptorLen; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp+20h] BYREF

  StringSecurityDescriptor = this;
  SecurityDescriptor = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(
                         L"P:\\WindowsApps\\AppxAllUserStore.dat",
                         SE_FILE_OBJECT,
                         4u,
                         0,
                         0,
                         0,
                         0,
                         &SecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x643,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                  (const char *)NamedSecurityInfoW,
                  StringSecurityDescriptorLen);
  }
  else
  {
    StringSecurityDescriptor = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSecurityDescriptor,
      0);
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 4u, &StringSecurityDescriptor, a3) )
    {
      *(_QWORD *)a2 = StringSecurityDescriptor;
      StringSecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x64B,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
                    v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18004a6e0  mov     r11, rsp
0x18004a6e3  mov     [r11+10h], rbx
0x18004a6e7  mov     [r11+8], rcx
0x18004a6eb  push    rdi
0x18004a6ec  sub     rsp, 40h
0x18004a6f0  xor     r9d, r9d; ppsidOwner
0x18004a6f3  mov     qword ptr [r11+20h], 0
0x18004a6fb  lea     rax, [r11+20h]
0x18004a6ff  mov     rdi, r8
0x18004a702  mov     [r11-10h], rax
0x18004a706  lea     rcx, pObjectName; "P:\\WindowsApps\\AppxAllUserStore.dat"
0x18004a70d  mov     qword ptr [r11-18h], 0
0x18004a715  mov     rbx, rdx
0x18004a718  mov     qword ptr [r11-20h], 0
0x18004a720  lea     edx, [r9+1]; ObjectType
0x18004a724  lea     r8d, [r9+4]; SecurityInfo
0x18004a728  mov     qword ptr [r11-28h], 0
0x18004a730  call    cs:__imp_GetNamedSecurityInfoW
0x18004a736  test    eax, eax
0x18004a738  jz      short loc_18004A757
0x18004a73a  mov     rcx, [rsp+48h]; this
0x18004a73f  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x18004a746  mov     r9d, eax; char *
0x18004a749  mov     edx, 643h; void *
0x18004a74e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004a753  mov     ebx, eax
0x18004a755  jmp     short loc_18004A7CF
0x18004a757  xor     edx, edx
0x18004a759  mov     [rsp+48h+StringSecurityDescriptor], 0
0x18004a762  lea     rcx, [rsp+48h+StringSecurityDescriptor]
0x18004a767  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004a76c  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18004a771  lea     r9, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004a776  mov     edx, 1; RequestedStringSDRevision
0x18004a77b  mov     qword ptr [rsp+48h+StringSecurityDescriptorLen], rdi; StringSecurityDescriptorLen
0x18004a780  lea     r8d, [rdx+3]; SecurityInformation
0x18004a784  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18004a78a  test    eax, eax
0x18004a78c  jnz     short loc_18004A7B2
0x18004a78e  mov     rcx, [rsp+48h]; this
0x18004a793  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x18004a79a  mov     edx, 64Bh; void *
0x18004a79f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004a7a4  lea     rcx, [rsp+48h+StringSecurityDescriptor]
0x18004a7a9  mov     ebx, eax
0x18004a7ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a7b0  jmp     short loc_18004A7CF
0x18004a7b2  mov     rax, [rsp+48h+StringSecurityDescriptor]
0x18004a7b7  lea     rcx, [rsp+48h+StringSecurityDescriptor]
0x18004a7bc  mov     [rbx], rax
0x18004a7bf  mov     [rsp+48h+StringSecurityDescriptor], 0
0x18004a7c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a7cd  xor     ebx, ebx
0x18004a7cf  lea     rcx, [rsp+48h+SecurityDescriptor]
0x18004a7d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004a7d9  mov     eax, ebx
0x18004a7db  mov     rbx, [rsp+48h+arg_8]
0x18004a7e0  add     rsp, 40h
0x18004a7e4  pop     rdi
0x18004a7e5  retn
```
