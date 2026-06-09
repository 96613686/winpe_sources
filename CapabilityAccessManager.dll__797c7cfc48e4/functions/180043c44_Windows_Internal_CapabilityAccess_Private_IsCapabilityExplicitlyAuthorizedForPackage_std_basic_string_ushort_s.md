# Windows::Internal::CapabilityAccess::Private::IsCapabilityExplicitlyAuthorizedForPackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180043c44`
- end: `0x180043eb4`
- name: `?IsCapabilityExplicitlyAuthorizedForPackage@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `624`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006874c`
- `0x1800833d0`

## callees

- `0x1800094c0`
- `0x18002392c`
- `0x180029408`
- `0x18003ae98`
- `0x180043c44`
- `0x180046438`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180043db3`
- `ntdll!RtlEqualSid` at `0x180043de3`
- `ntdll!RtlEqualSid` at `0x180043e10`
- `ntdll!RtlEqualSid` at `0x180043db3`
- `ntdll!RtlEqualSid` at `0x180043de3`
- `ntdll!RtlEqualSid` at `0x180043e10`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180043c94`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180043c94`
- `ntdll!RtlInitUnicodeString` at `0x180043c82`
- `ntdll!RtlInitUnicodeString` at `0x180043c82`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180043d58`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180043d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Windows::Internal::CapabilityAccess::Private::IsCapabilityExplicitlyAuthorizedForPackage(
        __int64 a1,
        __int64 a2)
{
  const WCHAR *v3; // rax
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v13; // [rsp+68h] [rbp-98h]
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp-88h]
  __int64 v16; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v17; // [rsp+88h] [rbp-78h]
  __int64 *v18; // [rsp+90h] [rbp-70h]
  unsigned int v19; // [rsp+98h] [rbp-68h] BYREF
  char v20; // [rsp+9Ch] [rbp-64h]
  __int64 *v21; // [rsp+A0h] [rbp-60h]
  int v22; // [rsp+A8h] [rbp-58h] BYREF
  char v23; // [rsp+ACh] [rbp-54h]
  __int64 *v24; // [rsp+B0h] [rbp-50h]
  unsigned int v25; // [rsp+B8h] [rbp-48h]
  char v26; // [rsp+BCh] [rbp-44h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE Sid2[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[48]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  DestinationString = 0;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  RtlInitUnicodeString(&DestinationString, v3);
  v4 = RtlDeriveCapabilitySidsFromName(&DestinationString, v29, Sid2);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x50F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v4,
      v11);
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  v13 = 0;
  v24 = &v12;
  v25 = 0;
  v26 = 1;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v12);
  v21 = &v14;
  v22 = 0;
  v23 = 1;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v14);
  v18 = &v16;
  v19 = 0;
  v20 = 1;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v16);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v6 = QueryApplicationCapabilitiesEx(v5, &v16, &v19, &v14);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x521,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v6,
      (int)&v22);
  if ( v20 )
    v18[1] = v19;
  if ( v23 )
    v21[1] = (unsigned int)v22;
  if ( v26 )
    v24[1] = v25;
  v7 = 0;
  if ( v17 )
  {
    while ( RtlEqualSid(*(PSID *)(v16 + 8LL * v7), Sid2) != 1 )
    {
      if ( ++v7 >= v17 )
        goto LABEL_12;
    }
  }
  else
  {
LABEL_12:
    v8 = 0;
    if ( v15 )
    {
      while ( RtlEqualSid(*(PSID *)(v14 + 8LL * v8), Sid2) != 1 )
      {
        if ( ++v8 >= v15 )
          goto LABEL_15;
      }
    }
    else
    {
LABEL_15:
      v9 = 0;
      if ( !v13 )
      {
LABEL_18:
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v12);
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v14);
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v16);
        return 0;
      }
      while ( RtlEqualSid(*(PSID *)(v12 + 8LL * v9), Sid2) != 1 )
      {
        if ( ++v9 >= v13 )
          goto LABEL_18;
      }
    }
  }
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v12);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v14);
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v16);
  return 1;
}

```

## disassembly

```asm
0x180043c44  mov     [rsp-8+arg_10], rbx
0x180043c49  mov     [rsp-8+arg_18], rdi
0x180043c4e  push    rbp
0x180043c4f  lea     rbp, [rsp-40h]
0x180043c54  sub     rsp, 140h
0x180043c5b  mov     rax, cs:__security_cookie
0x180043c62  xor     rax, rsp
0x180043c65  mov     [rbp+40h+var_10], rax
0x180043c69  mov     rbx, rcx
0x180043c6c  xorps   xmm0, xmm0
0x180043c6f  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x180043c73  mov     rcx, rdx
0x180043c76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043c7b  mov     rdx, rax; SourceString
0x180043c7e  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x180043c82  call    cs:__imp_RtlInitUnicodeString
0x180043c88  lea     r8, [rbp+40h+Sid2]
0x180043c8c  lea     rdx, [rbp+40h+var_40]
0x180043c90  lea     rcx, [rbp+40h+DestinationString]
0x180043c94  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180043c9a  mov     rcx, [rbp+48h]; this
0x180043c9e  xor     edi, edi
0x180043ca0  test    eax, eax
0x180043ca2  js      loc_180043E9F
0x180043ca8  mov     [rbp+40h+var_C0], rdi
0x180043cac  mov     [rbp+40h+var_B8], rdi
0x180043cb0  mov     [rsp+140h+var_D0], rdi
0x180043cb5  mov     [rsp+140h+var_C8], rdi
0x180043cba  mov     [rsp+140h+var_E0], rdi
0x180043cbf  mov     [rsp+140h+var_D8], rdi
0x180043cc4  lea     rax, [rsp+140h+var_E0]
0x180043cc9  mov     [rbp+40h+var_90], rax
0x180043ccd  mov     [rbp+40h+var_88], edi
0x180043cd0  mov     [rbp+40h+var_84], 1
0x180043cd4  lea     rcx, [rsp+140h+var_E0]
0x180043cd9  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043cde  lea     rax, [rsp+140h+var_D0]
0x180043ce3  mov     [rbp+40h+var_A0], rax
0x180043ce7  mov     [rbp+40h+var_98], edi
0x180043cea  mov     [rbp+40h+var_94], 1
0x180043cee  lea     rcx, [rsp+140h+var_D0]
0x180043cf3  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043cf8  lea     rax, [rbp+40h+var_C0]
0x180043cfc  mov     [rbp+40h+var_B0], rax
0x180043d00  mov     [rbp+40h+var_A8], edi
0x180043d03  mov     [rbp+40h+var_A4], 1
0x180043d07  lea     rcx, [rbp+40h+var_C0]
0x180043d0b  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043d10  mov     rcx, rbx
0x180043d13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d18  mov     [rsp+140h+var_F0], rdi
0x180043d1d  mov     [rsp+140h+var_F8], rdi
0x180043d22  mov     [rsp+140h+var_100], rdi
0x180043d27  mov     [rsp+140h+var_108], rdi
0x180043d2c  lea     rcx, [rbp+40h+var_88]
0x180043d30  mov     [rsp+140h+var_110], rcx
0x180043d35  lea     rcx, [rsp+140h+var_E0]
0x180043d3a  mov     [rsp+140h+var_118], rcx
0x180043d3f  lea     rcx, [rbp+40h+var_98]
0x180043d43  mov     qword ptr [rsp+140h+var_120], rcx; int
0x180043d48  lea     r9, [rsp+140h+var_D0]
0x180043d4d  lea     r8, [rbp+40h+var_A8]
0x180043d51  lea     rdx, [rbp+40h+var_C0]
0x180043d55  mov     rcx, rax
0x180043d58  call    cs:__imp_QueryApplicationCapabilitiesEx
0x180043d5e  mov     rcx, [rbp+48h]; this
0x180043d62  test    eax, eax
0x180043d64  js      loc_180043E8A
0x180043d6a  cmp     [rbp+40h+var_A4], dil
0x180043d6e  jz      short loc_180043D7B
0x180043d70  mov     ecx, [rbp+40h+var_A8]
0x180043d73  mov     rax, [rbp+40h+var_B0]
0x180043d77  mov     [rax+8], rcx
0x180043d7b  cmp     [rbp+40h+var_94], dil
0x180043d7f  jz      short loc_180043D8C
0x180043d81  mov     ecx, [rbp+40h+var_98]
0x180043d84  mov     rax, [rbp+40h+var_A0]
0x180043d88  mov     [rax+8], rcx
0x180043d8c  cmp     [rbp+40h+var_84], dil
0x180043d90  jz      short loc_180043D9D
0x180043d92  mov     ecx, [rbp+40h+var_88]
0x180043d95  mov     rax, [rbp+40h+var_90]
0x180043d99  mov     [rax+8], rcx
0x180043d9d  mov     ebx, edi
0x180043d9f  cmp     [rbp+40h+var_B8], rdi
0x180043da3  jbe     short loc_180043DCB
0x180043da5  mov     eax, ebx
0x180043da7  lea     rdx, [rbp+40h+Sid2]; Sid2
0x180043dab  mov     rcx, [rbp+40h+var_C0]
0x180043daf  mov     rcx, [rcx+rax*8]; Sid1
0x180043db3  call    cs:__imp_RtlEqualSid
0x180043db9  cmp     al, 1
0x180043dbb  jz      loc_180043E67
0x180043dc1  inc     ebx
0x180043dc3  mov     eax, ebx
0x180043dc5  cmp     rax, [rbp+40h+var_B8]
0x180043dc9  jb      short loc_180043DA5
0x180043dcb  mov     ebx, edi
0x180043dcd  cmp     [rsp+140h+var_C8], rdi
0x180043dd2  jbe     short loc_180043DF8
0x180043dd4  mov     eax, ebx
0x180043dd6  lea     rdx, [rbp+40h+Sid2]; Sid2
0x180043dda  mov     rcx, [rsp+140h+var_D0]
0x180043ddf  mov     rcx, [rcx+rax*8]; Sid1
0x180043de3  call    cs:__imp_RtlEqualSid
0x180043de9  cmp     al, 1
0x180043deb  jz      short loc_180043E67
0x180043ded  inc     ebx
0x180043def  mov     eax, ebx
0x180043df1  cmp     rax, [rsp+140h+var_C8]
0x180043df6  jb      short loc_180043DD4
0x180043df8  mov     ebx, edi
0x180043dfa  cmp     [rsp+140h+var_D8], rdi
0x180043dff  jbe     short loc_180043E25
0x180043e01  mov     eax, ebx
0x180043e03  lea     rdx, [rbp+40h+Sid2]; Sid2
0x180043e07  mov     rcx, [rsp+140h+var_E0]
0x180043e0c  mov     rcx, [rcx+rax*8]; Sid1
0x180043e10  call    cs:__imp_RtlEqualSid
0x180043e16  cmp     al, 1
0x180043e18  jz      short loc_180043E67
0x180043e1a  inc     ebx
0x180043e1c  mov     eax, ebx
0x180043e1e  cmp     rax, [rsp+140h+var_D8]
0x180043e23  jb      short loc_180043E01
0x180043e25  lea     rcx, [rsp+140h+var_E0]
0x180043e2a  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e2f  nop
0x180043e30  lea     rcx, [rsp+140h+var_D0]
0x180043e35  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e3a  nop
0x180043e3b  lea     rcx, [rbp+40h+var_C0]
0x180043e3f  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e44  xor     al, al
0x180043e46  mov     rcx, [rbp+40h+var_10]
0x180043e4a  xor     rcx, rsp; StackCookie
0x180043e4d  call    __security_check_cookie
0x180043e52  lea     r11, [rsp+140h+var_s0]
0x180043e5a  mov     rbx, [r11+20h]
0x180043e5e  mov     rdi, [r11+28h]
0x180043e62  mov     rsp, r11
0x180043e65  pop     rbp
0x180043e66  retn
0x180043e67  lea     rcx, [rsp+140h+var_E0]
0x180043e6c  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e71  nop
0x180043e72  lea     rcx, [rsp+140h+var_D0]
0x180043e77  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e7c  nop
0x180043e7d  lea     rcx, [rbp+40h+var_C0]
0x180043e81  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180043e86  mov     al, 1
0x180043e88  jmp     short loc_180043E46
0x180043e8a  mov     r9d, eax; char *
0x180043e8d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180043e94  mov     edx, 521h; void *
0x180043e99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043e9f  mov     r9d, eax; char *
0x180043ea2  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180043ea9  mov     edx, 50Fh; void *
0x180043eae  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
