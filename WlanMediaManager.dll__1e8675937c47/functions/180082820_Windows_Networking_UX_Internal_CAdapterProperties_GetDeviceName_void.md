# Windows::Networking::UX::Internal::CAdapterProperties::GetDeviceName(void)

- ea: `0x180082820`
- end: `0x180082972`
- name: `?GetDeviceName@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800849f8`

## callees

- `0x180003ed0`
- `0x1800097b4`
- `0x180011a20`
- `0x18001b838`
- `0x18001c044`
- `0x18001caf8`
- `0x18005f690`
- `0x18008129c`
- `0x180082820`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18008284e`
- `RPCRT4!UuidToStringW` at `0x18008284e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800828dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800828dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800828fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800828fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetDeviceName(
        Windows::Networking::UX::Internal::CAdapterProperties *this)
{
  RPC_STATUS v2; // ebx
  int v3; // ebx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  const WCHAR *v11; // rax
  HRESULT String; // eax
  unsigned int v13; // ebx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v15[16]; // [rsp+28h] [rbp-30h] BYREF
  UINT32 length; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  StringUuid = 0;
  v2 = UuidToStringW((const UUID *)this + 2, &StringUuid);
  if ( v2 )
  {
    v3 = v2 | 0x10000000;
    if ( v3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
        (const char *)(unsigned int)v3,
        (int)StringUuid);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
    return (unsigned int)v3;
  }
  else
  {
    std::wstring::wstring(v15);
    v5 = std::_WChar_traits<unsigned short>::length(StringUuid);
    std::wstring::_Append<unsigned short>(v15, v6, v5);
    v7 = std::_WChar_traits<unsigned short>::length(L"}");
    std::wstring::_Append<unsigned short>(v15, v8, v7);
    WindowsDeleteString(*((HSTRING *)this + 12));
    *((_QWORD *)this + 12) = 0;
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15, v9, v10);
    String = WindowsCreateString(v11, length, (HSTRING *)this + 12);
    v13 = String;
    if ( String >= 0 )
    {
      std::wstring::_Tidy_deallocate(v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B7,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
        (const char *)(unsigned int)String,
        (int)StringUuid);
      std::wstring::_Tidy_deallocate(v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
      return v13;
    }
  }
}

```

## disassembly

```asm
0x180082820  mov     [rsp+arg_8], rbx
0x180082825  push    rdi
0x180082826  sub     rsp, 50h
0x18008282a  mov     rax, cs:__security_cookie
0x180082831  xor     rax, rsp
0x180082834  mov     [rsp+58h+var_10], rax
0x180082839  mov     rdi, rcx
0x18008283c  mov     [rsp+58h+StringUuid], 0; int
0x180082845  add     rcx, 20h ; ' '; Uuid
0x180082849  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x18008284e  call    cs:__imp_UuidToStringW
0x180082854  mov     ebx, eax
0x180082856  test    eax, eax
0x180082858  jz      short loc_18008288D
0x18008285a  or      ebx, 10000000h
0x180082860  jge     short loc_18008287C
0x180082862  mov     rcx, [rsp+58h]; this
0x180082867  mov     r9d, ebx; char *
0x18008286a  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082871  mov     edx, 3B1h; void *
0x180082876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008287b  nop
0x18008287c  lea     rcx, [rsp+58h+StringUuid]
0x180082881  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180082886  mov     eax, ebx
0x180082888  jmp     loc_180082959
0x18008288d  lea     rdx, aDevice; "\\Device\\{"
0x180082894  lea     rcx, [rsp+58h+var_30]
0x180082899  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008289e  nop
0x18008289f  mov     rcx, [rsp+58h+StringUuid]
0x1800828a4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800828a9  mov     r8, rax
0x1800828ac  mov     rdx, rcx
0x1800828af  lea     rcx, [rsp+58h+var_30]
0x1800828b4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800828b9  lea     rcx, asc_1800A16BC; "}"
0x1800828c0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800828c5  mov     r8, rax
0x1800828c8  mov     rdx, rcx
0x1800828cb  lea     rcx, [rsp+58h+var_30]
0x1800828d0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800828d5  lea     rbx, [rdi+60h]
0x1800828d9  mov     rcx, [rbx]; string
0x1800828dc  call    cs:__imp_WindowsDeleteString
0x1800828e2  mov     qword ptr [rbx], 0
0x1800828e9  lea     rcx, [rsp+58h+var_30]
0x1800828ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800828f3  mov     rcx, rax; sourceString
0x1800828f6  mov     r8, rbx; string
0x1800828f9  mov     edx, [rsp+58h+length]; length
0x1800828fd  call    cs:__imp_WindowsCreateString
0x180082903  mov     ebx, eax
0x180082905  test    eax, eax
0x180082907  jns     short loc_18008293C
0x180082909  mov     rcx, [rsp+58h]; this
0x18008290e  mov     r9d, eax; char *
0x180082911  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082918  mov     edx, 3B7h; void *
0x18008291d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082922  nop
0x180082923  lea     rcx, [rsp+58h+var_30]
0x180082928  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008292d  nop
0x18008292e  lea     rcx, [rsp+58h+StringUuid]
0x180082933  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180082938  mov     eax, ebx
0x18008293a  jmp     short loc_180082959
0x18008293c  lea     rcx, [rsp+58h+var_30]
0x180082941  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082946  nop
0x180082947  lea     rcx, [rsp+58h+StringUuid]
0x18008294c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180082951  xor     eax, eax
0x180082953  jmp     short loc_180082959
0x180082955  mov     eax, dword ptr [rsp+58h+StringUuid]
0x180082959  mov     rcx, [rsp+58h+var_10]
0x18008295e  xor     rcx, rsp; StackCookie
0x180082961  call    __security_check_cookie
0x180082966  mov     rbx, [rsp+58h+arg_8]
0x18008296b  add     rsp, 50h
0x18008296f  pop     rdi
0x180082970  retn
```
