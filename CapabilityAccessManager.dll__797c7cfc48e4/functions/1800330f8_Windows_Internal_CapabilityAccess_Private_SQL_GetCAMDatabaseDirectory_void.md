# Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseDirectory(void)

- ea: `0x1800330f8`
- end: `0x18003335a`
- name: `?GetCAMDatabaseDirectory@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `610`
- prototype: `HKEY __fastcall(HKEY)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033360`
- `0x180033404`
- `0x180033574`
- `0x18004ea1c`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002392c`
- `0x180029408`
- `0x1800299c4`
- `0x18002f280`
- `0x1800330f8`
- `0x180037034`
- `0x18003ae98`
- `0x18003ce34`
- `0x18003cf4c`
- `0x180058c8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033187`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033187`
- `ntdll!RtlGetPersistedStateLocation` at `0x180033229`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003327e`
- `ntdll!RtlGetPersistedStateLocation` at `0x180033229`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003327e`

## string_xrefs

- `0x180033179`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180033318`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180033330`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180033348`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180033222`: `CapabilityAccessManagerDatabaseRoot`
- `0x180033277`: `CapabilityAccessManagerDatabaseRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY __fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseDirectory(HKEY a1)
{
  unsigned int Key; // eax
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // r9d
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // r9d
  int PersistedStateLocation; // eax
  int dwOptions; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-39h]
  int dwOptionsb; // [rsp+20h] [rbp-39h]
  unsigned int v14; // [rsp+50h] [rbp-9h] BYREF
  HKEY phkResult[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v16; // [rsp+68h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+78h] [rbp+1Fh]
  _BYTE v18[32]; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  phkResult[0] = a1;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy((Windows::Internal::CapabilityAccess::Private::SQL *)a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      dwOptions);
  phkResult[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
          0,
          0,
          0,
          0x20119u,
          0,
          phkResult,
          0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)Key,
      dwOptionsa);
  Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
    v18,
    phkResult[0],
    &stru_1800D7150,
    L"DatabaseRoot",
    0);
  v16 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16) = 0;
  v14 = 256;
  std::wstring::resize(&v16, 128);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v16);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
  if ( (int)RtlGetPersistedStateLocation(L"CapabilityAccessManagerDatabaseRoot", 0, v3, 1, v4, v5, &v14) < 0 )
  {
    std::wstring::resize(&v16, (unsigned __int64)v14 >> 1);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v16);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"CapabilityAccessManagerDatabaseRoot",
                               0,
                               v6,
                               1,
                               v7,
                               v8,
                               &v14);
    if ( PersistedStateLocation < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)PersistedStateLocation,
        dwOptionsb);
  }
  std::wstring::resize(&v16, ((unsigned __int64)v14 >> 1) - 1);
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *(_OWORD *)a1 = v16;
  *((__m128i *)a1 + 1) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16) = 0;
  std::wstring::_Tidy_deallocate(&v16);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
  return a1;
}

```

## disassembly

```asm
0x1800330f8  mov     [rsp-8+arg_8], rbx
0x1800330fd  mov     [rsp-8+arg_10], rdi
0x180033102  push    rbp
0x180033103  lea     rbp, [rsp-57h]
0x180033108  sub     rsp, 0B0h
0x18003310f  mov     rax, cs:__security_cookie
0x180033116  xor     rax, rsp
0x180033119  mov     [rbp+57h+var_8], rax
0x18003311d  mov     rbx, rcx
0x180033120  mov     [rbp+57h+var_58], rcx
0x180033124  mov     rdi, [rbp+5Fh]
0x180033128  call    ?IsDatabaseEnabledByEditionPolicy@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(void)
0x18003312d  test    al, al
0x18003312f  jz      loc_18003332A
0x180033135  mov     [rbp+57h+var_58], 0
0x18003313d  xor     edx, edx
0x18003313f  lea     rcx, [rbp+57h+var_58]
0x180033143  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033148  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180033151  lea     rax, [rbp+57h+var_58]
0x180033155  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18003315a  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180033163  mov     [rsp+0B0h+samDesired], 20119h; samDesired
0x18003316b  mov     [rsp+0B0h+dwOptions], 0; unsigned int
0x180033173  xor     r9d, r9d; lpClass
0x180033176  xor     r8d, r8d; Reserved
0x180033179  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033180  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033187  call    cs:__imp_RegCreateKeyExW
0x18003318d  mov     rcx, [rbp+5Fh]; this
0x180033191  test    eax, eax
0x180033193  jnz     loc_180033345
0x180033199  mov     qword ptr [rsp+0B0h+dwOptions], 0
0x1800331a2  lea     r9, aDatabaseroot; "DatabaseRoot"
0x1800331a9  lea     r8, stru_1800D7150
0x1800331b0  mov     rdx, [rbp+57h+var_58]
0x1800331b4  lea     rcx, [rbp+57h+var_28]
0x1800331b8  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800331bd  nop
0x1800331be  xorps   xmm0, xmm0
0x1800331c1  movups  [rbp+57h+var_48], xmm0
0x1800331c5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800331cd  movdqu  [rbp+57h+var_38], xmm1
0x1800331d2  xor     eax, eax
0x1800331d4  mov     word ptr [rbp+57h+var_48], ax
0x1800331d8  mov     [rbp+57h+var_60], 100h
0x1800331df  mov     edx, 80h
0x1800331e4  lea     rcx, [rbp+57h+var_48]
0x1800331e8  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800331ed  mov     r9d, [rbp+57h+var_60]
0x1800331f1  lea     rcx, [rbp+57h+var_48]
0x1800331f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800331fa  mov     rdx, rax
0x1800331fd  lea     rcx, [rbp+57h+var_28]
0x180033201  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033206  mov     r8, rax
0x180033209  lea     rax, [rbp+57h+var_60]
0x18003320d  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x180033212  mov     [rsp+0B0h+samDesired], r9d
0x180033217  mov     qword ptr [rsp+0B0h+dwOptions], rdx
0x18003321c  xor     edx, edx
0x18003321e  lea     r9d, [rdx+1]
0x180033222  lea     rcx, aCapabilityacce_2; "CapabilityAccessManagerDatabaseRoot"
0x180033229  call    cs:__imp_RtlGetPersistedStateLocation
0x18003322f  test    eax, eax
0x180033231  jns     short loc_180033290
0x180033233  mov     edx, [rbp+57h+var_60]
0x180033236  shr     rdx, 1
0x180033239  lea     rcx, [rbp+57h+var_48]
0x18003323d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180033242  mov     r9d, [rbp+57h+var_60]
0x180033246  lea     rcx, [rbp+57h+var_48]
0x18003324a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003324f  mov     rdx, rax
0x180033252  lea     rcx, [rbp+57h+var_28]
0x180033256  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003325b  mov     r8, rax
0x18003325e  lea     rax, [rbp+57h+var_60]
0x180033262  mov     [rsp+0B0h+lpSecurityAttributes], rax
0x180033267  mov     [rsp+0B0h+samDesired], r9d
0x18003326c  mov     qword ptr [rsp+0B0h+dwOptions], rdx; int
0x180033271  xor     edx, edx
0x180033273  lea     r9d, [rdx+1]
0x180033277  lea     rcx, aCapabilityacce_2; "CapabilityAccessManagerDatabaseRoot"
0x18003327e  call    cs:__imp_RtlGetPersistedStateLocation
0x180033284  mov     rcx, [rbp+5Fh]; this
0x180033288  test    eax, eax
0x18003328a  js      loc_180033315
0x180033290  mov     edx, [rbp+57h+var_60]
0x180033293  shr     rdx, 1
0x180033296  dec     rdx
0x180033299  lea     rcx, [rbp+57h+var_48]
0x18003329d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800332a2  mov     qword ptr [rbx+10h], 0
0x1800332aa  mov     qword ptr [rbx+18h], 0
0x1800332b2  movups  xmm0, [rbp+57h+var_48]
0x1800332b6  movups  xmmword ptr [rbx], xmm0
0x1800332b9  movups  xmm1, [rbp+57h+var_38]
0x1800332bd  movups  xmmword ptr [rbx+10h], xmm1
0x1800332c1  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800332c9  movdqu  [rbp+57h+var_38], xmm0
0x1800332ce  xor     ecx, ecx
0x1800332d0  mov     word ptr [rbp+57h+var_48], cx
0x1800332d4  lea     rcx, [rbp+57h+var_48]
0x1800332d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800332dd  nop
0x1800332de  lea     rcx, [rbp+57h+var_28]
0x1800332e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800332e7  nop
0x1800332e8  lea     rcx, [rbp+57h+var_58]
0x1800332ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800332f1  mov     rax, rbx
0x1800332f4  mov     rcx, [rbp+57h+var_8]
0x1800332f8  xor     rcx, rsp; StackCookie
0x1800332fb  call    __security_check_cookie
0x180033300  lea     r11, [rsp+0B0h+var_s0]
0x180033308  mov     rbx, [r11+18h]
0x18003330c  mov     rdi, [r11+20h]
0x180033310  mov     rsp, r11
0x180033313  pop     rbp
0x180033314  retn
0x180033315  mov     r9d, eax; char *
0x180033318  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003331f  mov     edx, 1E1h; void *
0x180033324  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003332a  mov     r9d, 80004001h; char *
0x180033330  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180033337  mov     edx, 1C7h; void *
0x18003333c  mov     rcx, rdi; this
0x18003333f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033345  mov     r9d, eax; char *
0x180033348  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003334f  mov     edx, 1CDh; void *
0x180033354  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
