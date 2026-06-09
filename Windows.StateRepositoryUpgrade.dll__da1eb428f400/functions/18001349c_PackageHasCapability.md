# PackageHasCapability

- ea: `0x18001349c`
- end: `0x180013646`
- name: `PackageHasCapability`
- size: `426`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001364c`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x18000a3c0`
- `0x180013120`
- `0x180013138`
- `0x180013220`
- `0x180013238`
- `0x1800132ac`
- `0x1800132bc`
- `0x1800132c8`
- `0x18001349c`
- `0x180013728`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800135c6`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800135c6`
- `ntdll!RtlInitUnicodeString` at `0x1800135b3`
- `ntdll!RtlInitUnicodeString` at `0x1800135b3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013607`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013607`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180013540`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180013540`

## pseudocode

```c
__int64 __fastcall PackageHasCapability(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  int ApplicationCapabilities; // ebx
  int v9; // eax
  unsigned __int64 i; // rbx
  PSID *v11; // rax
  _BYTE v13[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v14; // [rsp+68h] [rbp-98h]
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSid2[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v18[80]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *a3 = 0;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v13);
  v5 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address<unsigned long>(
         v13,
         v16);
  v6 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::operator unsigned long *(v5);
  v7 = wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v13);
  ApplicationCapabilities = QueryApplicationCapabilitiesEx(a1, v7, v6, 0);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v16);
  if ( ApplicationCapabilities == -2147024444 )
    goto LABEL_11;
  if ( ApplicationCapabilities >= 0 )
  {
    memset_0(v18, 0, 0x44u);
    memset_0(pSid2, 0, 0x44u);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"runFullTrust");
    v9 = RtlDeriveCapabilitySidsFromName(&DestinationString, v18, pSid2);
    if ( v9 < 0 )
    {
      ApplicationCapabilities = wil::details::in1diag3::Return_NtStatus(
                                  retaddr,
                                  (void *)0xB1,
                                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-statere"
                                                "pository.hasrunfulltrustcapability.cpp",
                                  (const char *)(unsigned int)v9,
                                  0);
      goto LABEL_12;
    }
    for ( i = 0; i < v14; ++i )
    {
      v11 = (PSID *)wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](
                      v13,
                      i);
      if ( EqualSid(*v11, pSid2) )
      {
        *a3 = 1;
        break;
      }
    }
LABEL_11:
    ApplicationCapabilities = 0;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.hasrunfulltrustcapability.cpp",
    (const char *)(unsigned int)ApplicationCapabilities,
    0);
LABEL_12:
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(v13);
  return (unsigned int)ApplicationCapabilities;
}

```

## disassembly

```asm
0x18001349c  mov     [rsp-8+arg_8], rbx
0x1800134a1  push    rbp
0x1800134a2  push    rsi
0x1800134a3  push    rdi
0x1800134a4  lea     rbp, [rsp-40h]
0x1800134a9  sub     rsp, 140h
0x1800134b0  mov     rax, cs:__security_cookie
0x1800134b7  xor     rax, rsp
0x1800134ba  mov     [rbp+50h+var_20], rax
0x1800134be  mov     rdi, rcx
0x1800134c1  mov     byte ptr [r8], 0
0x1800134c5  lea     rcx, [rsp+150h+var_F0]
0x1800134ca  mov     rsi, r8
0x1800134cd  call    ??0?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x1800134d2  lea     rdx, [rbp+50h+var_D0]
0x1800134d6  lea     rcx, [rsp+150h+var_F0]
0x1800134db  call    ??$size_address@K@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address<ulong>(void)
0x1800134e0  mov     rcx, rax
0x1800134e3  call    ??B?$size_address_ptr@K@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAKXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::operator ulong *(void)
0x1800134e8  lea     rcx, [rsp+150h+var_F0]
0x1800134ed  mov     rbx, rax
0x1800134f0  call    ??I?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x1800134f5  mov     [rsp+150h+var_100], 0
0x1800134fe  xor     r9d, r9d
0x180013501  mov     [rsp+150h+var_108], 0
0x18001350a  mov     r8, rbx
0x18001350d  mov     [rsp+150h+var_110], 0
0x180013516  mov     rdx, rax
0x180013519  mov     [rsp+150h+var_118], 0
0x180013522  mov     rcx, rdi
0x180013525  mov     [rsp+150h+var_120], 0
0x18001352e  mov     [rsp+150h+var_128], 0
0x180013537  mov     qword ptr [rsp+150h+var_130], 0; int
0x180013540  call    cs:__imp_QueryApplicationCapabilitiesEx
0x180013546  lea     rcx, [rbp+50h+var_D0]
0x18001354a  mov     ebx, eax
0x18001354c  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x180013551  cmp     ebx, 800701C4h
0x180013557  jz      loc_180013619
0x18001355d  test    ebx, ebx
0x18001355f  jns     short loc_18001357E
0x180013561  mov     rcx, [rbp+58h]; this
0x180013565  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\staterepositor"...
0x18001356c  mov     r9d, ebx; char *
0x18001356f  mov     edx, 0A9h; void *
0x180013574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013579  jmp     loc_18001361B
0x18001357e  mov     ebx, 44h ; 'D'
0x180013583  lea     rcx, [rbp+50h+var_70]; void *
0x180013587  mov     r8d, ebx; Size
0x18001358a  xor     edx, edx; Val
0x18001358c  call    memset_0
0x180013591  mov     r8d, ebx; Size
0x180013594  lea     rcx, [rbp+50h+pSid2]; void *
0x180013598  xor     edx, edx; Val
0x18001359a  call    memset_0
0x18001359f  xorps   xmm0, xmm0
0x1800135a2  lea     rdx, ?RestrictedCapabilityRunFullTrust@Value@Packaging@Appx@@3QBGB; "runFullTrust"
0x1800135a9  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1800135ae  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1800135b3  call    cs:__imp_RtlInitUnicodeString
0x1800135b9  lea     r8, [rbp+50h+pSid2]
0x1800135bd  lea     rdx, [rbp+50h+var_70]
0x1800135c1  lea     rcx, [rsp+150h+DestinationString]
0x1800135c6  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800135cc  test    eax, eax
0x1800135ce  jns     short loc_1800135EA
0x1800135d0  mov     rcx, [rbp+58h]; this
0x1800135d4  lea     r8, aOnecoreBaseApp_31; "onecore\\base\\appmodel\\staterepositor"...
0x1800135db  mov     r9d, eax; char *
0x1800135de  lea     edx, [rbx+6Dh]; void *
0x1800135e1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800135e6  mov     ebx, eax
0x1800135e8  jmp     short loc_18001361B
0x1800135ea  xor     ebx, ebx
0x1800135ec  cmp     rbx, [rsp+150h+var_E8]
0x1800135f1  jnb     short loc_180013619
0x1800135f3  mov     rdx, rbx
0x1800135f6  lea     rcx, [rsp+150h+var_F0]
0x1800135fb  call    ??A?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAX_K@Z; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x180013600  lea     rdx, [rbp+50h+pSid2]; pSid2
0x180013604  mov     rcx, [rax]; pSid1
0x180013607  call    cs:__imp_EqualSid
0x18001360d  test    eax, eax
0x18001360f  jnz     short loc_180013616
0x180013611  inc     rbx
0x180013614  jmp     short loc_1800135EC
0x180013616  mov     byte ptr [rsi], 1
0x180013619  xor     ebx, ebx
0x18001361b  lea     rcx, [rsp+150h+var_F0]
0x180013620  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x180013625  mov     eax, ebx
0x180013627  mov     rcx, [rbp+50h+var_20]
0x18001362b  xor     rcx, rsp; StackCookie
0x18001362e  call    __security_check_cookie
0x180013633  mov     rbx, [rsp+150h+arg_8]
0x18001363b  add     rsp, 140h
0x180013642  pop     rdi
0x180013643  pop     rsi
0x180013644  pop     rbp
0x180013645  retn
```
