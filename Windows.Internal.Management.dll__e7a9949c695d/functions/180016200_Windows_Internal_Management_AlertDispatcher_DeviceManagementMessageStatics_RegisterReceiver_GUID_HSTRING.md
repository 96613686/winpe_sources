# Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::RegisterReceiver(_GUID,HSTRING__ *)

- ea: `0x180016200`
- end: `0x18001660a`
- name: `?RegisterReceiver@DeviceManagementMessageStatics@AlertDispatcher@Management@Internal@Windows@@UEAAJU_GUID@@PEAUHSTRING__@@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics *this, struct _GUID *, HSTRING)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180004d50`
- `0x180007ac9`
- `0x18000a2a4`
- `0x18000d724`
- `0x180015790`
- `0x180015e4c`
- `0x180015f40`
- `0x180015f70`
- `0x180016200`
- `0x180016630`
- `0x1800168d0`
- `0x18004aa4c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016532`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016559`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016559`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800164c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800164c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016409`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016409`

## pseudocode

```c
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
0x180016200  mov     [rsp+arg_18], rbx
0x180016205  push    rsi
0x180016206  push    rdi
0x180016207  push    r14
0x180016209  sub     rsp, 0F0h
0x180016210  mov     rax, cs:__security_cookie
0x180016217  xor     rax, rsp
0x18001621a  mov     [rsp+108h+var_20], rax
0x180016222  mov     r14, r8
0x180016225  mov     rsi, rdx
0x180016228  mov     rdi, rcx
0x18001622b  test    r8, r8
0x18001622e  jz      loc_1800165E0
0x180016234  mov     r8d, 10h; Size
0x18001623a  lea     rdx, GUID_NULL; Buf2
0x180016241  mov     rcx, rsi; Buf1
0x180016244  call    memcmp_0
0x180016249  test    eax, eax
0x18001624b  jz      loc_1800165E0
0x180016251  xor     ecx, ecx
0x180016253  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180016258  mov     ebx, eax
0x18001625a  test    eax, eax
0x18001625c  jns     short loc_180016281
0x18001625e  mov     rcx, [rsp+108h]; this
0x180016266  mov     r9d, eax; char *
0x180016269  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180016270  mov     edx, 3Dh ; '='; void *
0x180016275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001627a  mov     eax, ebx
0x18001627c  jmp     loc_1800165E5
0x180016281  mov     [rsp+108h+hKey], 0
0x18001628a  mov     [rsp+108h+var_A8], 0
0x180016293  lea     rcx, [rsp+108h+var_60]
0x18001629b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800162a0  nop
0x1800162a1  movups  xmm1, xmmword ptr [rsi]
0x1800162a4  movdqu  xmmword ptr [rsp+108h+var_98], xmm1
0x1800162aa  lea     r8, [rsp+108h+var_60]
0x1800162b2  lea     rdx, [rsp+108h+var_98]
0x1800162b7  call    ?StripGUIDBraces@DeviceManagementMessageStatics@AlertDispatcher@Management@Internal@Windows@@AEAAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::Management::AlertDispatcher::DeviceManagementMessageStatics::StripGUIDBraces(_GUID,std::wstring &)
0x1800162bc  mov     ebx, eax
0x1800162be  test    eax, eax
0x1800162c0  jns     short loc_180016309
0x1800162c2  mov     rcx, [rsp+108h]; this
0x1800162ca  mov     r9d, eax; char *
0x1800162cd  lea     r8, aOnecoreuapAdmi_37; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800162d4  mov     edx, 43h ; 'C'; void *
0x1800162d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162de  nop
0x1800162df  lea     rcx, [rsp+108h+var_60]
0x1800162e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800162ec  nop
0x1800162ed  lea     rcx, [rsp+108h+var_A8]
0x1800162f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800162f7  nop
0x1800162f8  lea     rcx, [rsp+108h+hKey]
0x1800162fd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016302  mov     eax, ebx
0x180016304  jmp     loc_1800165E5
0x180016309  lea     r8, [rsp+108h+var_60]
0x180016311  mov     rdx, [rdi+48h]
0x180016315  lea     rcx, [rsp+108h+var_40]
0x18001631d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180016322  lea     rax, [rsp+108h+hKey]
0x180016327  mov     [rsp+108h+var_98], rax
0x18001632c  mov     [rsp+108h+var_98+8], 0
0x180016335  mov     [rsp+108h+var_88], 1
0x18001633d  lea     rcx, [rsp+108h+var_40]
0x180016345  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001634a  mov     rdx, rax; lpSubKey
0x18001634d  lea     rax, [rsp+108h+var_98+8]
0x180016352  mov     [rsp+108h+phkResult], rax; phkResult
0x180016357  mov     r9d, 20006h; samDesired
0x18001635d  xor     r8d, r8d; ulOptions
0x180016360  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016367  call    cs:__imp_RegOpenKeyExW
0x18001636d  mov     ebx, eax
0x18001636f  lea     rcx, [rsp+108h+var_98]
0x180016374  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180016379  test    ebx, ebx
0x18001637b  jz      short loc_1800163C0
0x18001637d  jle     short loc_180016388
0x18001637f  movzx   ebx, bx
0x180016382  or      ebx, 80070000h
0x180016388  lea     rcx, [rsp+108h+var_40]
0x180016390  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016395  nop
0x180016396  lea     rcx, [rsp+108h+var_60]
0x18001639e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800163a3  nop
0x1800163a4  lea     rcx, [rsp+108h+var_A8]
0x1800163a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800163ae  nop
0x1800163af  lea     rcx, [rsp+108h+hKey]
0x1800163b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800163b9  mov     eax, ebx
0x1800163bb  jmp     loc_1800165E5
0x1800163c0  mov     [rsp+108h+var_98], 0
0x1800163c9  lea     rax, [rsp+108h+var_98]
0x1800163ce  mov     [rsp+108h+var_78], rax
0x1800163d6  mov     [rsp+108h+var_70], 0
0x1800163e2  mov     [rsp+108h+var_68], 1
0x1800163ea  lea     rax, [rsp+108h+var_70]
0x1800163f2  mov     [rsp+108h+phkResult], rax; phkResult
0x1800163f7  mov     r9d, 20019h; samDesired
0x1800163fd  xor     r8d, r8d; ulOptions
0x180016400  mov     rdx, [rdi+38h]; lpSubKey
0x180016404  mov     rcx, [rsp+108h+hKey]; hKey
0x180016409  call    cs:__imp_RegOpenKeyExW
0x18001640f  mov     ebx, eax
0x180016411  lea     rcx, [rsp+108h+var_78]
0x180016419  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001641e  lea     rcx, [rsp+108h+var_98]
0x180016423  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016428  test    ebx, ebx
0x18001642a  jnz     short loc_180016467
0x18001642c  lea     rcx, [rsp+108h+var_40]
0x180016434  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016439  nop
0x18001643a  lea     rcx, [rsp+108h+var_60]
0x180016442  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016447  nop
0x180016448  lea     rcx, [rsp+108h+var_A8]
0x18001644d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016452  nop
0x180016453  lea     rcx, [rsp+108h+hKey]
0x180016458  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001645d  mov     eax, 800700B7h
0x180016462  jmp     loc_1800165E5
0x180016467  lea     rax, [rsp+108h+var_A8]
0x18001646c  mov     [rsp+108h+var_78], rax
0x180016474  mov     [rsp+108h+var_70], 0
0x180016480  mov     [rsp+108h+var_68], 1
0x180016488  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x180016491  lea     rax, [rsp+108h+var_70]
0x180016499  mov     [rsp+108h+var_D0], rax; phkResult
0x18001649e  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800164a7  mov     [rsp+108h+samDesired], 0F003Fh; samDesired
0x1800164af  mov     dword ptr [rsp+108h+phkResult], 0; dwOptions
0x1800164b7  xor     r9d, r9d; lpClass
0x1800164ba  xor     r8d, r8d; Reserved
0x1800164bd  mov     rdx, [rdi+38h]; lpSubKey
0x1800164c1  mov     rcx, [rsp+108h+hKey]; hKey
0x1800164c6  call    cs:__imp_RegCreateKeyExW
0x1800164cc  mov     ebx, eax
0x1800164ce  lea     rcx, [rsp+108h+var_78]
0x1800164d6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800164db  test    ebx, ebx
0x1800164dd  jz      short loc_180016522
0x1800164df  jle     short loc_1800164EA
0x1800164e1  movzx   ebx, bx
0x1800164e4  or      ebx, 80070000h
0x1800164ea  lea     rcx, [rsp+108h+var_40]
0x1800164f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800164f7  nop
0x1800164f8  lea     rcx, [rsp+108h+var_60]
0x180016500  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016505  nop
0x180016506  lea     rcx, [rsp+108h+var_A8]
0x18001650b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016510  nop
0x180016511  lea     rcx, [rsp+108h+hKey]
0x180016516  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001651b  mov     eax, ebx
0x18001651d  jmp     loc_1800165E5
0x180016522  mov     [rsp+108h+length], 0
0x18001652a  lea     rdx, [rsp+108h+length]; length
0x18001652f  mov     rcx, r14; string
0x180016532  call    cs:__imp_WindowsGetStringRawBuffer
0x180016538  mov     edx, [rsp+108h+length]
0x18001653c  add     edx, edx
0x18001653e  mov     [rsp+108h+samDesired], edx; cbData
0x180016542  mov     [rsp+108h+phkResult], rax; lpData
0x180016547  mov     r9d, 1; dwType
0x18001654d  xor     r8d, r8d; Reserved
0x180016550  mov     rdx, [rdi+40h]; lpValueName
0x180016554  mov     rcx, [rsp+108h+var_A8]; hKey
0x180016559  call    cs:__imp_RegSetValueExW
0x18001655f  mov     ebx, eax
0x180016561  test    eax, eax
0x180016563  jz      short loc_1800165A5
0x180016565  jle     short loc_180016570
0x180016567  movzx   ebx, ax
0x18001656a  or      ebx, 80070000h
0x180016570  lea     rcx, [rsp+108h+var_40]
0x180016578  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001657d  nop
0x18001657e  lea     rcx, [rsp+108h+var_60]
0x180016586  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001658b  nop
0x18001658c  lea     rcx, [rsp+108h+var_A8]
0x180016591  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016596  nop
0x180016597  lea     rcx, [rsp+108h+hKey]
0x18001659c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800165a1  mov     eax, ebx
0x1800165a3  jmp     short loc_1800165E5
0x1800165a5  lea     rcx, [rsp+108h+var_40]
0x1800165ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800165b2  nop
0x1800165b3  lea     rcx, [rsp+108h+var_60]
0x1800165bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800165c0  nop
0x1800165c1  lea     rcx, [rsp+108h+var_A8]
0x1800165c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800165cb  nop
0x1800165cc  lea     rcx, [rsp+108h+hKey]
0x1800165d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800165d6  xor     eax, eax
0x1800165d8  jmp     short loc_1800165E5
0x1800165da  mov     eax, [rsp+108h+length]
0x1800165de  jmp     short loc_1800165E5
0x1800165e0  mov     eax, 80070057h
0x1800165e5  mov     rcx, [rsp+108h+var_20]
0x1800165ed  xor     rcx, rsp; StackCookie
0x1800165f0  call    __security_check_cookie
0x1800165f5  mov     rbx, [rsp+108h+arg_18]
0x1800165fd  add     rsp, 0F0h
0x180016604  pop     r14
0x180016606  pop     rdi
0x180016607  pop     rsi
0x180016608  retn
```
