# AppxAllUserStore::Internal::LogFileInformation(AppxAllUserStore::BasicLogFile *,ushort const *)

- ea: `0x1800432ac`
- end: `0x18004347d`
- name: `?LogFileInformation@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBG@Z`
- size: `465`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180043b10`

## callees

- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x180036498`
- `0x180040880`
- `0x1800432ac`
- `0x1800455bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800432de`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004335b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800432de`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004335b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18004330f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18004330f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800433c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800433c0`

## string_xrefs

- `0x180043369`: `GetFileSecurity %ls failed.`
- `0x1800433ce`: `ConvertSecurityDescriptorToStringSecurityDescriptor %ls failed.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::LogFileInformation(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        const unsigned __int16 *a3)
{
  unsigned int LastErrorMsg; // ebx
  PSECURITY_DESCRIPTOR v6; // rbx
  int v7; // eax
  int v8; // eax
  int lpnLengthNeeded; // [rsp+20h] [rbp-20h]
  LPWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR v12; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD nLengthNeeded; // [rsp+70h] [rbp+30h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+78h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  if ( GetFileSecurityW((LPCWSTR)a2, 7u, 0, 0, &nLengthNeeded) )
  {
    LastErrorMsg = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)0x8000FFFFLL,
      lpnLengthNeeded);
  }
  else
  {
    v12 = LocalAlloc(0, nLengthNeeded);
    v6 = v12;
    if ( v12 )
    {
      if ( GetFileSecurityW((LPCWSTR)a2, 7u, v12, nLengthNeeded, &nLengthNeeded) )
      {
        StringSecurityDescriptorLen = 0;
        StringSecurityDescriptor = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSecurityDescriptor,
          0);
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               v6,
               1u,
               7u,
               &StringSecurityDescriptor,
               &StringSecurityDescriptorLen) )
        {
          if ( this )
          {
            v7 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"LogFileInformation %ls.", a2);
            if ( v7 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x15D,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v7);
            v8 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"SD %ls", StringSecurityDescriptor);
            if ( v8 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x15E,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v8);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
          LastErrorMsg = 0;
        }
        else
        {
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0x15B,
                           (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                           "ConvertSecurityDescriptorToStringSecurityDescriptor %ls failed.",
                           (const char *)a2);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
        }
      }
      else
      {
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x155,
                         (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                         "GetFileSecurity %ls failed.",
                         (const char *)a2);
      }
    }
    else
    {
      LastErrorMsg = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)0x8007000ELL,
        lpnLengthNeeded);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  }
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1800432ac  mov     [rsp-18h+arg_0], rbx
0x1800432b1  push    rbp
0x1800432b2  push    rsi
0x1800432b3  push    rdi
0x1800432b4  mov     rbp, rsp
0x1800432b7  sub     rsp, 40h
0x1800432bb  mov     rdi, rdx
0x1800432be  mov     [rbp+nLengthNeeded], 0
0x1800432c5  xor     r9d, r9d; nLength
0x1800432c8  lea     rax, [rbp+nLengthNeeded]
0x1800432cc  mov     rsi, rcx
0x1800432cf  mov     qword ptr [rsp+40h+lpnLengthNeeded], rax; int
0x1800432d4  xor     r8d, r8d; pSecurityDescriptor
0x1800432d7  mov     rcx, rdi; lpFileName
0x1800432da  lea     edx, [r9+7]; RequestedInformation
0x1800432de  call    cs:__imp_GetFileSecurityW
0x1800432e4  test    eax, eax
0x1800432e6  jz      short loc_18004330A
0x1800432e8  mov     rcx, [rbp+18h]; this
0x1800432ec  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800432f3  mov     ebx, 8000FFFFh
0x1800432f8  mov     edx, 14Eh; void *
0x1800432fd  mov     r9d, ebx; char *
0x180043300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043305  jmp     loc_18004346E
0x18004330a  mov     edx, [rbp+nLengthNeeded]; uBytes
0x18004330d  xor     ecx, ecx; uFlags
0x18004330f  call    cs:__imp_LocalAlloc
0x180043315  mov     [rbp+var_8], rax
0x180043319  mov     rbx, rax
0x18004331c  test    rax, rax
0x18004331f  jnz     short loc_180043343
0x180043321  mov     rcx, [rbp+18h]; this
0x180043325  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004332c  mov     ebx, 8007000Eh
0x180043331  mov     edx, 151h; void *
0x180043336  mov     r9d, ebx; char *
0x180043339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004333e  jmp     loc_180043465
0x180043343  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180043347  lea     rax, [rbp+nLengthNeeded]
0x18004334b  mov     r8, rbx; pSecurityDescriptor
0x18004334e  mov     qword ptr [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180043353  mov     edx, 7; RequestedInformation
0x180043358  mov     rcx, rdi; lpFileName
0x18004335b  call    cs:__imp_GetFileSecurityW
0x180043361  test    eax, eax
0x180043363  jnz     short loc_18004338D
0x180043365  mov     rcx, [rbp+18h]; this
0x180043369  lea     r9, aGetfilesecurit; "GetFileSecurity %ls failed."
0x180043370  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180043377  mov     qword ptr [rsp+40h+lpnLengthNeeded], rdi; char *
0x18004337c  mov     edx, 155h; void *
0x180043381  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180043386  mov     ebx, eax
0x180043388  jmp     loc_180043465
0x18004338d  xor     edx, edx
0x18004338f  mov     [rbp+StringSecurityDescriptorLen], 0
0x180043396  lea     rcx, [rbp+StringSecurityDescriptor]
0x18004339a  mov     [rbp+StringSecurityDescriptor], 0
0x1800433a2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800433a7  mov     edx, 1; RequestedStringSDRevision
0x1800433ac  lea     rax, [rbp+StringSecurityDescriptorLen]
0x1800433b0  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800433b4  mov     qword ptr [rsp+40h+lpnLengthNeeded], rax; int
0x1800433b9  mov     rcx, rbx; SecurityDescriptor
0x1800433bc  lea     r8d, [rdx+6]; SecurityInformation
0x1800433c0  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800433c6  test    eax, eax
0x1800433c8  jnz     short loc_1800433F8
0x1800433ca  mov     rcx, [rbp+18h]; this
0x1800433ce  lea     r9, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x1800433d5  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800433dc  mov     qword ptr [rsp+40h+lpnLengthNeeded], rdi; char *
0x1800433e1  mov     edx, 15Bh; void *
0x1800433e6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800433eb  lea     rcx, [rbp+StringSecurityDescriptor]
0x1800433ef  mov     ebx, eax
0x1800433f1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800433f6  jmp     short loc_180043465
0x1800433f8  test    rsi, rsi
0x1800433fb  jz      short loc_18004345A
0x1800433fd  mov     r8, rdi
0x180043400  lea     rdx, aLogfileinforma; "LogFileInformation %ls."
0x180043407  mov     rcx, rsi; this
0x18004340a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004340f  test    eax, eax
0x180043411  jns     short loc_18004342B
0x180043413  mov     rcx, [rbp+18h]; this
0x180043417  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004341e  mov     r9d, eax; char *
0x180043421  mov     edx, 15Dh; void *
0x180043426  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004342b  mov     r8, [rbp+StringSecurityDescriptor]
0x18004342f  lea     rdx, aSdLs; "SD %ls"
0x180043436  mov     rcx, rsi; this
0x180043439  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004343e  test    eax, eax
0x180043440  jns     short loc_18004345A
0x180043442  mov     rcx, [rbp+18h]; this
0x180043446  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x18004344d  mov     r9d, eax; char *
0x180043450  mov     edx, 15Eh; void *
0x180043455  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004345a  lea     rcx, [rbp+StringSecurityDescriptor]
0x18004345e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043463  xor     ebx, ebx
0x180043465  lea     rcx, [rbp+var_8]
0x180043469  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004346e  mov     eax, ebx
0x180043470  mov     rbx, [rsp+40h+arg_0]
0x180043475  add     rsp, 40h
0x180043479  pop     rdi
0x18004347a  pop     rsi
0x18004347b  pop     rbp
0x18004347c  retn
```
