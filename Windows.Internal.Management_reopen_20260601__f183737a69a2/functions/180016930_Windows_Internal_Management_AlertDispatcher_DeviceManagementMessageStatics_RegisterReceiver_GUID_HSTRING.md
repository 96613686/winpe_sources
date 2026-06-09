# Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::RegisterReceiver(_GUID,HSTRING__ *)

- ea: `0x180016930`
- end: `0x180016d58`
- name: `?RegisterReceiver@DeviceManagementMessageStatics@AlertDispatcher@Management@Internal@Windows@@UEAAJU_GUID@@PEAUHSTRING__@@@Z`
- size: `1064`
- prototype: `int(Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics *__hidden this, struct _GUID *__struct_ptr, HSTRING)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180004eb0`
- `0x180007c39`
- `0x18000a5c4`
- `0x18000dc18`
- `0x180015eb4`
- `0x18001656c`
- `0x180016668`
- `0x180016698`
- `0x180016930`
- `0x180016d80`
- `0x180017024`
- `0x18004ac2c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016ca1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016ca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016b3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016c02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::RegisterReceiver(
        Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics *this,
        struct _GUID *a2,
        HSTRING a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  const WCHAR *v12; // rax
  int v13; // ebx
  LSTATUS v14; // ebx
  const BYTE *StringRawBuffer; // rax
  LSTATUS v16; // eax
  unsigned int v17; // ebx
  int phkResult; // [rsp+20h] [rbp-E8h]
  UINT32 length; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY v21[2]; // [rsp+60h] [rbp-A8h] BYREF
  HKEY v22[2]; // [rsp+70h] [rbp-98h] BYREF
  char v23; // [rsp+80h] [rbp-88h]
  HKEY *v24; // [rsp+90h] [rbp-78h] BYREF
  HKEY v25; // [rsp+98h] [rbp-70h] BYREF
  char v26; // [rsp+A0h] [rbp-68h]
  _BYTE v27[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v28[32]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( !a3 || !memcmp_0(a2, &GUID_NULL, 0x10u) )
    return 2147942487LL;
  v6 = Windows::Internal::Management::Enrollment::Enroller::AccessCheck(0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\alertmessage.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    return v7;
  }
  hKey = 0;
  v21[0] = 0;
  std::wstring::wstring(v27);
  *(struct _GUID *)v22 = *a2;
  v10 = Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::StripGUIDBraces(v9, v22, v27);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\alertmessage.cpp",
      (const char *)(unsigned int)v10,
      phkResult);
    std::wstring::~wstring(v27);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v11;
  }
  std::operator+<unsigned short>(v28, *((_QWORD *)this + 9), v27);
  v22[0] = (HKEY)&hKey;
  v22[1] = 0;
  v23 = 1;
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20006u, &v22[1]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v22);
  if ( v13 )
  {
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
LABEL_10:
    std::wstring::~wstring(v28);
    std::wstring::~wstring(v27);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v13;
  }
  v22[0] = 0;
  v24 = v22;
  v25 = 0;
  v26 = 1;
  v14 = RegOpenKeyExW(hKey, *((LPCWSTR *)this + 7), 0, 0x20019u, &v25);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v24);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
  if ( v14 )
  {
    v24 = v21;
    v25 = 0;
    v26 = 1;
    v13 = RegCreateKeyExW(hKey, *((LPCWSTR *)this + 7), 0, 0, 0, 0xF003Fu, 0, &v25, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v24);
    if ( v13 )
    {
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      goto LABEL_10;
    }
    length = 0;
    StringRawBuffer = (const BYTE *)WindowsGetStringRawBuffer(a3, &length);
    v16 = RegSetValueExW(v21[0], *((LPCWSTR *)this + 8), 0, 1u, StringRawBuffer, 2 * length);
    v17 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      std::wstring::~wstring(v28);
      std::wstring::~wstring(v27);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v17;
    }
    else
    {
      std::wstring::~wstring(v28);
      std::wstring::~wstring(v27);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
  }
  else
  {
    std::wstring::~wstring(v28);
    std::wstring::~wstring(v27);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942583LL;
  }
}

```

## disassembly

```asm
0x180016930  mov     [rsp+arg_18], rbx
0x180016935  push    rsi
0x180016936  push    rdi
0x180016937  push    r14
0x180016939  sub     rsp, 0F0h
0x180016940  mov     rax, cs:__security_cookie
0x180016947  xor     rax, rsp
0x18001694a  mov     [rsp+108h+var_20], rax
0x180016952  mov     r14, r8
0x180016955  mov     rsi, rdx
0x180016958  mov     rdi, rcx
0x18001695b  test    r8, r8
0x18001695e  jz      loc_180016D2E
0x180016964  mov     r8d, 10h; Size
0x18001696a  lea     rdx, GUID_NULL; Buf2
0x180016971  mov     rcx, rsi; Buf1
0x180016974  call    memcmp_0
0x180016979  test    eax, eax
0x18001697b  jz      loc_180016D2E
0x180016981  xor     ecx, ecx
0x180016983  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180016988  mov     ebx, eax
0x18001698a  test    eax, eax
0x18001698c  jns     short loc_1800169B1
0x18001698e  mov     rcx, [rsp+108h]; this
0x180016996  mov     r9d, eax; char *
0x180016999  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800169a0  mov     edx, 3Dh ; '='; void *
0x1800169a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800169aa  mov     eax, ebx
0x1800169ac  jmp     loc_180016D33
0x1800169b1  mov     [rsp+108h+hKey], 0
0x1800169ba  mov     [rsp+108h+var_A8], 0
0x1800169c3  lea     rcx, [rsp+108h+var_60]
0x1800169cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800169d0  nop
0x1800169d1  movups  xmm1, xmmword ptr [rsi]
0x1800169d4  movdqu  xmmword ptr [rsp+108h+var_98], xmm1
0x1800169da  lea     r8, [rsp+108h+var_60]
0x1800169e2  lea     rdx, [rsp+108h+var_98]
0x1800169e7  call    ?StripGUIDBraces@DeviceManagementMessageStatics@AlertDispatcher@Management@Internal@Windows@@AEAAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::StripGUIDBraces(_GUID,std::wstring &)
0x1800169ec  mov     ebx, eax
0x1800169ee  test    eax, eax
0x1800169f0  jns     short loc_180016A39
0x1800169f2  mov     rcx, [rsp+108h]; this
0x1800169fa  mov     r9d, eax; char *
0x1800169fd  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180016a04  mov     edx, 43h ; 'C'; void *
0x180016a09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a0e  nop
0x180016a0f  lea     rcx, [rsp+108h+var_60]
0x180016a17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016a1c  nop
0x180016a1d  lea     rcx, [rsp+108h+var_A8]
0x180016a22  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016a27  nop
0x180016a28  lea     rcx, [rsp+108h+hKey]
0x180016a2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016a32  mov     eax, ebx
0x180016a34  jmp     loc_180016D33
0x180016a39  lea     r8, [rsp+108h+var_60]
0x180016a41  mov     rdx, [rdi+48h]
0x180016a45  lea     rcx, [rsp+108h+var_40]
0x180016a4d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180016a52  lea     rax, [rsp+108h+hKey]
0x180016a57  mov     [rsp+108h+var_98], rax
0x180016a5c  mov     [rsp+108h+var_98+8], 0
0x180016a65  mov     [rsp+108h+var_88], 1
0x180016a6d  lea     rcx, [rsp+108h+var_40]
0x180016a75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016a7a  mov     rdx, rax; lpSubKey
0x180016a7d  lea     rax, [rsp+108h+var_98+8]
0x180016a82  mov     [rsp+108h+phkResult], rax; phkResult
0x180016a87  mov     r9d, 20006h; samDesired
0x180016a8d  xor     r8d, r8d; ulOptions
0x180016a90  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016a97  call    cs:__imp_RegOpenKeyExW
0x180016a9e  nop     dword ptr [rax+rax+00h]
0x180016aa3  mov     ebx, eax
0x180016aa5  lea     rcx, [rsp+108h+var_98]
0x180016aaa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180016aaf  test    ebx, ebx
0x180016ab1  jz      short loc_180016AF6
0x180016ab3  jle     short loc_180016ABE
0x180016ab5  movzx   ebx, bx
0x180016ab8  or      ebx, 80070000h
0x180016abe  lea     rcx, [rsp+108h+var_40]
0x180016ac6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016acb  nop
0x180016acc  lea     rcx, [rsp+108h+var_60]
0x180016ad4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016ad9  nop
0x180016ada  lea     rcx, [rsp+108h+var_A8]
0x180016adf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016ae4  nop
0x180016ae5  lea     rcx, [rsp+108h+hKey]
0x180016aea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016aef  mov     eax, ebx
0x180016af1  jmp     loc_180016D33
0x180016af6  mov     [rsp+108h+var_98], 0
0x180016aff  lea     rax, [rsp+108h+var_98]
0x180016b04  mov     [rsp+108h+var_78], rax
0x180016b0c  mov     [rsp+108h+var_70], 0
0x180016b18  mov     [rsp+108h+var_68], 1
0x180016b20  lea     rax, [rsp+108h+var_70]
0x180016b28  mov     [rsp+108h+phkResult], rax; phkResult
0x180016b2d  mov     r9d, 20019h; samDesired
0x180016b33  xor     r8d, r8d; ulOptions
0x180016b36  mov     rdx, [rdi+38h]; lpSubKey
0x180016b3a  mov     rcx, [rsp+108h+hKey]; hKey
0x180016b3f  call    cs:__imp_RegOpenKeyExW
0x180016b46  nop     dword ptr [rax+rax+00h]
0x180016b4b  mov     ebx, eax
0x180016b4d  lea     rcx, [rsp+108h+var_78]
0x180016b55  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180016b5a  lea     rcx, [rsp+108h+var_98]
0x180016b5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016b64  test    ebx, ebx
0x180016b66  jnz     short loc_180016BA3
0x180016b68  lea     rcx, [rsp+108h+var_40]
0x180016b70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016b75  nop
0x180016b76  lea     rcx, [rsp+108h+var_60]
0x180016b7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016b83  nop
0x180016b84  lea     rcx, [rsp+108h+var_A8]
0x180016b89  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016b8e  nop
0x180016b8f  lea     rcx, [rsp+108h+hKey]
0x180016b94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016b99  mov     eax, 800700B7h
0x180016b9e  jmp     loc_180016D33
0x180016ba3  lea     rax, [rsp+108h+var_A8]
0x180016ba8  mov     [rsp+108h+var_78], rax
0x180016bb0  mov     [rsp+108h+var_70], 0
0x180016bbc  mov     [rsp+108h+var_68], 1
0x180016bc4  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x180016bcd  lea     rax, [rsp+108h+var_70]
0x180016bd5  mov     [rsp+108h+var_D0], rax; phkResult
0x180016bda  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016be3  mov     [rsp+108h+samDesired], 0F003Fh; samDesired
0x180016beb  mov     dword ptr [rsp+108h+phkResult], 0; dwOptions
0x180016bf3  xor     r9d, r9d; lpClass
0x180016bf6  xor     r8d, r8d; Reserved
0x180016bf9  mov     rdx, [rdi+38h]; lpSubKey
0x180016bfd  mov     rcx, [rsp+108h+hKey]; hKey
0x180016c02  call    cs:__imp_RegCreateKeyExW
0x180016c09  nop     dword ptr [rax+rax+00h]
0x180016c0e  mov     ebx, eax
0x180016c10  lea     rcx, [rsp+108h+var_78]
0x180016c18  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180016c1d  test    ebx, ebx
0x180016c1f  jz      short loc_180016C64
0x180016c21  jle     short loc_180016C2C
0x180016c23  movzx   ebx, bx
0x180016c26  or      ebx, 80070000h
0x180016c2c  lea     rcx, [rsp+108h+var_40]
0x180016c34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016c39  nop
0x180016c3a  lea     rcx, [rsp+108h+var_60]
0x180016c42  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016c47  nop
0x180016c48  lea     rcx, [rsp+108h+var_A8]
0x180016c4d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016c52  nop
0x180016c53  lea     rcx, [rsp+108h+hKey]
0x180016c58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016c5d  mov     eax, ebx
0x180016c5f  jmp     loc_180016D33
0x180016c64  mov     [rsp+108h+length], 0
0x180016c6c  lea     rdx, [rsp+108h+length]; length
0x180016c71  mov     rcx, r14; string
0x180016c74  call    cs:__imp_WindowsGetStringRawBuffer
0x180016c7b  nop     dword ptr [rax+rax+00h]
0x180016c80  mov     edx, [rsp+108h+length]
0x180016c84  add     edx, edx
0x180016c86  mov     [rsp+108h+samDesired], edx; cbData
0x180016c8a  mov     [rsp+108h+phkResult], rax; lpData
0x180016c8f  mov     r9d, 1; dwType
0x180016c95  xor     r8d, r8d; Reserved
0x180016c98  mov     rdx, [rdi+40h]; lpValueName
0x180016c9c  mov     rcx, [rsp+108h+var_A8]; hKey
0x180016ca1  call    cs:__imp_RegSetValueExW
0x180016ca8  nop     dword ptr [rax+rax+00h]
0x180016cad  mov     ebx, eax
0x180016caf  test    eax, eax
0x180016cb1  jz      short loc_180016CF3
0x180016cb3  jle     short loc_180016CBE
0x180016cb5  movzx   ebx, ax
0x180016cb8  or      ebx, 80070000h
0x180016cbe  lea     rcx, [rsp+108h+var_40]
0x180016cc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016ccb  nop
0x180016ccc  lea     rcx, [rsp+108h+var_60]
0x180016cd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016cd9  nop
0x180016cda  lea     rcx, [rsp+108h+var_A8]
0x180016cdf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016ce4  nop
0x180016ce5  lea     rcx, [rsp+108h+hKey]
0x180016cea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016cef  mov     eax, ebx
0x180016cf1  jmp     short loc_180016D33
0x180016cf3  lea     rcx, [rsp+108h+var_40]
0x180016cfb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016d00  nop
0x180016d01  lea     rcx, [rsp+108h+var_60]
0x180016d09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016d0e  nop
0x180016d0f  lea     rcx, [rsp+108h+var_A8]
0x180016d14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016d19  nop
0x180016d1a  lea     rcx, [rsp+108h+hKey]
0x180016d1f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016d24  xor     eax, eax
0x180016d26  jmp     short loc_180016D33
0x180016d28  mov     eax, [rsp+108h+length]
0x180016d2c  jmp     short loc_180016D33
0x180016d2e  mov     eax, 80070057h
0x180016d33  mov     rcx, [rsp+108h+var_20]
0x180016d3b  xor     rcx, rsp; StackCookie
0x180016d3e  call    __security_check_cookie
0x180016d43  mov     rbx, [rsp+108h+arg_18]
0x180016d4b  add     rsp, 0F0h
0x180016d52  pop     r14
0x180016d54  pop     rdi
0x180016d55  pop     rsi
0x180016d56  retn
```
