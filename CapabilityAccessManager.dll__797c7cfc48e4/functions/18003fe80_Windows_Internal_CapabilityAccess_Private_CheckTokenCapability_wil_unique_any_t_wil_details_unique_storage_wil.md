# Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003fe80`
- end: `0x18003ff6f`
- name: `?CheckTokenCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `239`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fdf4`
- `0x180044874`
- `0x18006874c`
- `0x18006ae88`

## callees

- `0x180029408`
- `0x18002f260`
- `0x180039e9c`
- `0x18003ae98`
- `0x18003fe80`
- `0x180042fe8`

## import_xrefs

- `ntdll!RtlCapabilityCheck` at `0x18003ff35`
- `ntdll!RtlCapabilityCheck` at `0x18003ff35`
- `ntdll!RtlInitUnicodeString` at `0x18003ff24`
- `ntdll!RtlInitUnicodeString` at `0x18003ff24`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18003fed9`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18003fed9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(_QWORD *a1, __int64 a2)
{
  const char *v3; // r9
  bool v4; // bl
  const WCHAR *v6; // rax
  int v7; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  int v10; // [rsp+48h] [rbp+18h] BYREF
  PSID Sid; // [rsp+50h] [rbp+20h] BYREF

  if ( *(_QWORD *)(a2 + 16) > 1u
    && *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) == 83
    && *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) + 2) == 45 )
  {
    v10 = 0;
    Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(&Sid);
    if ( !(unsigned int)CheckTokenCapability(*a1, Sid, &v10) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v3);
    v4 = v10 != 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    return v4;
  }
  else
  {
    LOBYTE(v10) = 0;
    DestinationString = 0;
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    RtlInitUnicodeString(&DestinationString, v6);
    v7 = RtlCapabilityCheck(*a1, &DestinationString, &v10);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v7,
        *(int *)&DestinationString.Length);
    return (_BYTE)v10 != 0;
  }
}

```

## disassembly

```asm
0x18003fe80  mov     [rsp-8+arg_0], rbx
0x18003fe85  mov     [rsp-8+arg_18], rdi
0x18003fe8a  push    rbp
0x18003fe8b  mov     rbp, rsp
0x18003fe8e  sub     rsp, 30h
0x18003fe92  mov     rbx, rcx
0x18003fe95  cmp     qword ptr [rdx+10h], 1
0x18003fe9a  jbe     short loc_18003FF0A
0x18003fe9c  mov     rcx, rdx
0x18003fe9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fea4  cmp     word ptr [rax], 53h ; 'S'
0x18003fea8  jnz     short loc_18003FF0A
0x18003feaa  mov     rcx, rdx
0x18003fead  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003feb2  cmp     word ptr [rax+2], 2Dh ; '-'
0x18003feb7  jnz     short loc_18003FF0A
0x18003feb9  mov     [rbp+arg_8], 0
0x18003fec0  lea     rcx, [rbp+Sid]; Sid
0x18003fec4  call    ?GetSidFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(std::wstring const &)
0x18003fec9  nop
0x18003feca  mov     rdi, [rbp+8]
0x18003fece  lea     r8, [rbp+arg_8]
0x18003fed2  mov     rdx, [rbp+Sid]
0x18003fed6  mov     rcx, [rbx]
0x18003fed9  call    cs:__imp_CheckTokenCapability
0x18003fedf  test    eax, eax
0x18003fee1  jnz     short loc_18003FEF6
0x18003fee3  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003feea  lea     edx, [rax+3Fh]; void *
0x18003feed  mov     rcx, rdi; this
0x18003fef0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003fef6  cmp     [rbp+arg_8], 0
0x18003fefa  setnz   bl
0x18003fefd  lea     rcx, [rbp+Sid]
0x18003ff01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ff06  mov     al, bl
0x18003ff08  jmp     short loc_18003FF5F
0x18003ff0a  mov     byte ptr [rbp+arg_8], 0
0x18003ff0e  xorps   xmm0, xmm0
0x18003ff11  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003ff15  mov     rcx, rdx
0x18003ff18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ff1d  mov     rdx, rax; SourceString
0x18003ff20  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003ff24  call    cs:__imp_RtlInitUnicodeString
0x18003ff2a  lea     r8, [rbp+arg_8]
0x18003ff2e  lea     rdx, [rbp+DestinationString]
0x18003ff32  mov     rcx, [rbx]
0x18003ff35  call    cs:__imp_RtlCapabilityCheck
0x18003ff3b  test    eax, eax
0x18003ff3d  jns     short loc_18003FF58
0x18003ff3f  mov     rcx, [rbp+8]; this
0x18003ff43  mov     r9d, eax; char *
0x18003ff46  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003ff4d  mov     edx, 48h ; 'H'; void *
0x18003ff52  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003ff58  cmp     byte ptr [rbp+arg_8], 0
0x18003ff5c  setnz   al
0x18003ff5f  mov     rbx, [rsp+30h+arg_0]
0x18003ff64  mov     rdi, [rsp+30h+arg_18]
0x18003ff69  add     rsp, 30h
0x18003ff6d  pop     rbp
0x18003ff6e  retn
```
