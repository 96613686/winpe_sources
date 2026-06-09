# Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180021808`
- end: `0x1800218f7`
- name: `?CheckTokenCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002177c`

## callees

- `0x18001b444`
- `0x180021530`
- `0x180021808`
- `0x18002294c`
- `0x180023690`
- `0x1800238e0`

## import_xrefs

- `ntdll!RtlCapabilityCheck` at `0x1800218bd`
- `ntdll!RtlCapabilityCheck` at `0x1800218bd`
- `ntdll!RtlInitUnicodeString` at `0x1800218ac`
- `ntdll!RtlInitUnicodeString` at `0x1800218ac`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180021861`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180021861`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  const char *v5; // r9
  bool v6; // bl
  const WCHAR *v8; // rax
  int v9; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  int v12; // [rsp+48h] [rbp+18h] BYREF
  PSID Sid; // [rsp+50h] [rbp+20h] BYREF

  if ( *(_QWORD *)(a2 + 16) > 1u
    && *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3, a4) == 83
    && *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3, a4) + 2) == 45 )
  {
    v12 = 0;
    Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(&Sid);
    if ( !(unsigned int)CheckTokenCapability(*a1, Sid, &v12) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v5);
    v6 = v12 != 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    return v6;
  }
  else
  {
    LOBYTE(v12) = 0;
    DestinationString = 0;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3, a4);
    RtlInitUnicodeString(&DestinationString, v8);
    v9 = RtlCapabilityCheck(*a1, &DestinationString, &v12);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v9,
        *(int *)&DestinationString.Length);
    return (_BYTE)v12 != 0;
  }
}

```

## disassembly

```asm
0x180021808  mov     [rsp-8+arg_0], rbx
0x18002180d  mov     [rsp-8+arg_18], rdi
0x180021812  push    rbp
0x180021813  mov     rbp, rsp
0x180021816  sub     rsp, 30h
0x18002181a  mov     rbx, rcx
0x18002181d  cmp     qword ptr [rdx+10h], 1
0x180021822  jbe     short loc_180021892
0x180021824  mov     rcx, rdx
0x180021827  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002182c  cmp     word ptr [rax], 53h ; 'S'
0x180021830  jnz     short loc_180021892
0x180021832  mov     rcx, rdx
0x180021835  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002183a  cmp     word ptr [rax+2], 2Dh ; '-'
0x18002183f  jnz     short loc_180021892
0x180021841  mov     [rbp+arg_8], 0
0x180021848  lea     rcx, [rbp+Sid]; Sid
0x18002184c  call    ?GetSidFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(std::wstring const &)
0x180021851  nop
0x180021852  mov     rdi, [rbp+8]
0x180021856  lea     r8, [rbp+arg_8]
0x18002185a  mov     rdx, [rbp+Sid]
0x18002185e  mov     rcx, [rbx]
0x180021861  call    cs:__imp_CheckTokenCapability
0x180021867  test    eax, eax
0x180021869  jnz     short loc_18002187E
0x18002186b  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180021872  lea     edx, [rax+3Fh]; void *
0x180021875  mov     rcx, rdi; this
0x180021878  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002187e  cmp     [rbp+arg_8], 0
0x180021882  setnz   bl
0x180021885  lea     rcx, [rbp+Sid]
0x180021889  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002188e  mov     al, bl
0x180021890  jmp     short loc_1800218E7
0x180021892  mov     byte ptr [rbp+arg_8], 0
0x180021896  xorps   xmm0, xmm0
0x180021899  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002189d  mov     rcx, rdx
0x1800218a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800218a5  mov     rdx, rax; SourceString
0x1800218a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800218ac  call    cs:__imp_RtlInitUnicodeString
0x1800218b2  lea     r8, [rbp+arg_8]
0x1800218b6  lea     rdx, [rbp+DestinationString]
0x1800218ba  mov     rcx, [rbx]
0x1800218bd  call    cs:__imp_RtlCapabilityCheck
0x1800218c3  test    eax, eax
0x1800218c5  jns     short loc_1800218E0
0x1800218c7  mov     rcx, [rbp+8]; this
0x1800218cb  mov     r9d, eax; char *
0x1800218ce  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800218d5  mov     edx, 48h ; 'H'; void *
0x1800218da  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800218e0  cmp     byte ptr [rbp+arg_8], 0
0x1800218e4  setnz   al
0x1800218e7  mov     rbx, [rsp+30h+arg_0]
0x1800218ec  mov     rdi, [rsp+30h+arg_18]
0x1800218f1  add     rsp, 30h
0x1800218f5  pop     rbp
0x1800218f6  retn
```
