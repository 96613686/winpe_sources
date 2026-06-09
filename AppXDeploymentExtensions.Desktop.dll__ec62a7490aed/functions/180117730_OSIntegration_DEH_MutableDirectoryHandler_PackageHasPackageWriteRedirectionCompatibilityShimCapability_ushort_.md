# OSIntegration::DEH::MutableDirectoryHandler::PackageHasPackageWriteRedirectionCompatibilityShimCapability(ushort const *,bool &)

- ea: `0x180117730`
- end: `0x1801178d7`
- name: `?PackageHasPackageWriteRedirectionCompatibilityShimCapability@MutableDirectoryHandler@DEH@OSIntegration@@AEAAJPEBGAEA_N@Z`
- size: `423`
- prototype: `__int64 __fastcall(OSIntegration::DEH::MutableDirectoryHandler *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aa10c`

## callees

- `0x18001adb4`
- `0x180068f18`
- `0x1800aed10`
- `0x1800af918`
- `0x180100f3c`
- `0x180116d48`
- `0x180116d64`
- `0x180116d7c`
- `0x180116d88`
- `0x180116d98`
- `0x180116da4`
- `0x180117730`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180117892`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180117892`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18011784a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18011784a`
- `ntdll!RtlInitUnicodeString` at `0x180117810`
- `ntdll!RtlInitUnicodeString` at `0x180117810`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1801177c3`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1801177c3`

## string_xrefs

- `0x1801177e3`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x18011785e`: `onecore\admin\appmodel\osim\src\deh\appx\mutabledirectory\mutabledirectoryhandler.cpp`
- `0x1801177ff`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::MutableDirectoryHandler::PackageHasPackageWriteRedirectionCompatibilityShimCapability(
        OSIntegration::DEH::MutableDirectoryHandler *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  int ApplicationCapabilities; // ebx
  int v10; // eax
  unsigned int i; // ebx
  PSID *v12; // rax
  _BYTE v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v15; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid2[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[80]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a3 = 0;
  wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(v14);
  v6 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
         v14,
         v17,
         v5);
  v7 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::operator unsigned long *(v6);
  v8 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v14);
  ApplicationCapabilities = QueryApplicationCapabilities(a2, v8, v7, 0);
  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v17);
  if ( ApplicationCapabilities >= 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
    memset_0(pSid2, 0, 0x44u);
    memset_0(v19, 0, 0x44u);
    v10 = RtlDeriveCapabilitySidsFromName(&DestinationString, v19, pSid2);
    if ( v10 >= 0 )
    {
      for ( i = 0; i < v15; ++i )
      {
        v12 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](v14);
        if ( EqualSid(*v12, pSid2) )
        {
          *a3 = 1;
          break;
        }
      }
      ApplicationCapabilities = 0;
    }
    else
    {
      ApplicationCapabilities = wil::details::in1diag3::Return_NtStatus(
                                  retaddr,
                                  (void *)0x31C,
                                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabl"
                                                "edirectoryhandler.cpp",
                                  (const char *)(unsigned int)v10,
                                  0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\mutabledirectory\\mutabledirectoryhandler.cpp",
      (const char *)(unsigned int)ApplicationCapabilities,
      0);
  }
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v14);
  return (unsigned int)ApplicationCapabilities;
}

```

## disassembly

```asm
0x180117730  mov     [rsp-8+arg_0], rbx
0x180117735  push    rbp
0x180117736  push    rsi
0x180117737  push    rdi
0x180117738  lea     rbp, [rsp-30h]
0x18011773d  sub     rsp, 130h
0x180117744  mov     rax, cs:__security_cookie
0x18011774b  xor     rax, rsp
0x18011774e  mov     [rbp+40h+var_20], rax
0x180117752  lea     rcx, [rsp+140h+var_F0]
0x180117757  mov     byte ptr [r8], 0
0x18011775b  mov     rsi, r8
0x18011775e  mov     rdi, rdx
0x180117761  call    ??0?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(void)
0x180117766  lea     rdx, [rsp+140h+var_D0]
0x18011776b  lea     rcx, [rsp+140h+var_F0]
0x180117770  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x180117775  mov     rcx, rax
0x180117778  call    ??B?$size_address_ptr@K@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAKXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::operator ulong *(void)
0x18011777d  lea     rcx, [rsp+140h+var_F0]
0x180117782  mov     rbx, rax
0x180117785  call    ??I?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x18011778a  mov     [rsp+140h+var_100], 0
0x180117793  xor     r9d, r9d
0x180117796  mov     [rsp+140h+var_108], 0
0x18011779f  mov     r8, rbx
0x1801177a2  mov     [rsp+140h+var_110], 0
0x1801177ab  mov     rdx, rax
0x1801177ae  mov     [rsp+140h+var_118], 0
0x1801177b7  mov     rcx, rdi
0x1801177ba  mov     qword ptr [rsp+140h+var_120], 0; int
0x1801177c3  call    cs:__imp_QueryApplicationCapabilities
0x1801177ca  nop     dword ptr [rax+rax+00h]
0x1801177cf  lea     rcx, [rsp+140h+var_D0]
0x1801177d4  mov     ebx, eax
0x1801177d6  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1801177db  test    ebx, ebx
0x1801177dd  jns     short loc_1801177FC
0x1801177df  mov     rcx, [rbp+48h]; this
0x1801177e3  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801177ea  mov     r9d, ebx; char *
0x1801177ed  mov     edx, 311h; void *
0x1801177f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177f7  jmp     loc_1801178AB
0x1801177fc  xorps   xmm0, xmm0
0x1801177ff  lea     rdx, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x180117806  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x18011780b  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x180117810  call    cs:__imp_RtlInitUnicodeString
0x180117817  nop     dword ptr [rax+rax+00h]
0x18011781c  mov     ebx, 44h ; 'D'
0x180117821  lea     rcx, [rbp+40h+pSid2]; void *
0x180117825  mov     r8d, ebx; Size
0x180117828  xor     edx, edx; Val
0x18011782a  call    memset_0
0x18011782f  mov     r8d, ebx; Size
0x180117832  lea     rcx, [rbp+40h+var_70]; void *
0x180117836  xor     edx, edx; Val
0x180117838  call    memset_0
0x18011783d  lea     r8, [rbp+40h+pSid2]
0x180117841  lea     rdx, [rbp+40h+var_70]
0x180117845  lea     rcx, [rsp+140h+DestinationString]
0x18011784a  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180117851  nop     dword ptr [rax+rax+00h]
0x180117856  test    eax, eax
0x180117858  jns     short loc_180117876
0x18011785a  mov     rcx, [rbp+48h]; this
0x18011785e  lea     r8, aOnecoreAdminAp_115; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180117865  mov     r9d, eax; char *
0x180117868  mov     edx, 31Ch; void *
0x18011786d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180117872  mov     ebx, eax
0x180117874  jmp     short loc_1801178AB
0x180117876  xor     ebx, ebx
0x180117878  mov     edx, ebx
0x18011787a  cmp     rdx, [rsp+140h+var_E8]
0x18011787f  jnb     short loc_1801178A9
0x180117881  lea     rcx, [rsp+140h+var_F0]
0x180117886  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x18011788b  lea     rdx, [rbp+40h+pSid2]; pSid2
0x18011788f  mov     rcx, [rax]; pSid1
0x180117892  call    cs:__imp_EqualSid
0x180117899  nop     dword ptr [rax+rax+00h]
0x18011789e  test    eax, eax
0x1801178a0  jnz     short loc_1801178A6
0x1801178a2  inc     ebx
0x1801178a4  jmp     short loc_180117878
0x1801178a6  mov     byte ptr [rsi], 1
0x1801178a9  xor     ebx, ebx
0x1801178ab  lea     rcx, [rsp+140h+var_F0]
0x1801178b0  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x1801178b5  mov     eax, ebx
0x1801178b7  mov     rcx, [rbp+40h+var_20]
0x1801178bb  xor     rcx, rsp; StackCookie
0x1801178be  call    __security_check_cookie
0x1801178c3  mov     rbx, [rsp+140h+arg_0]
0x1801178cb  add     rsp, 130h
0x1801178d2  pop     rdi
0x1801178d3  pop     rsi
0x1801178d4  pop     rbp
0x1801178d5  retn
```
