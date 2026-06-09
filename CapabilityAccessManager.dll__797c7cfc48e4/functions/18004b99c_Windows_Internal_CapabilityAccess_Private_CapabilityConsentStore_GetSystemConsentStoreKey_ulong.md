# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetSystemConsentStoreKey(ulong)

- ea: `0x18004b99c`
- end: `0x18004bbbb`
- name: `?GetSystemConsentStoreKey@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `543`
- prototype: `PHKEY __fastcall(PHKEY phkResult, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b144`
- `0x18004e9ec`
- `0x180050478`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001c5fc`
- `0x1800257a4`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18003ae98`
- `0x18003ce34`
- `0x18003cf4c`
- `0x180046610`
- `0x1800473fc`
- `0x18004b99c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bb60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bb60`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004ba22`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004ba22`

## string_xrefs

- `0x18004ba12`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x18004ba1b`: `CapabilityAccessManager`

## pseudocode

```c
PHKEY __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetSystemConsentStoreKey(
        PHKEY phkResult,
        int a2)
{
  unsigned int v4; // eax
  __int64 v5; // rax
  int v6; // edx
  int PersistedStateLocation; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r10
  const WCHAR *v14; // rax
  unsigned int Key; // eax
  int dwOptions; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-39h]
  unsigned int i; // [rsp+50h] [rbp-9h] BYREF
  int v20; // [rsp+54h] [rbp-5h]
  PHKEY v21; // [rsp+58h] [rbp-1h]
  _BYTE Src[16]; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp+17h]
  unsigned __int64 v24; // [rsp+78h] [rbp+1Fh]
  _BYTE v25[32]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v21 = phkResult;
  v20 = 0;
  std::wstring::wstring(v25);
  v4 = 256;
  for ( i = 256; ; v4 = i )
  {
    std::wstring::resize(v25, (unsigned __int64)v4 >> 1);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"CapabilityAccessManager",
                               0,
                               L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
                               0,
                               v5,
                               v6,
                               &i);
    if ( PersistedStateLocation != -2147483643 )
      break;
  }
  if ( PersistedStateLocation < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)(unsigned int)PersistedStateLocation,
      dwOptions);
  std::wstring::resize(v25, ((unsigned __int64)i >> 1) - 1);
  std::wstring::wstring(Src, v25);
  if ( v23 >= v24 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v23;
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_WORD *)(v8 + 2 * v9) = 92;
    *(_WORD *)(v8 + 2 * v9 + 2) = 0;
  }
  v10 = std::_WChar_traits<unsigned short>::length(L"ConsentStore");
  std::wstring::_Append<unsigned short>(Src, v11, v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    WPP_SF_S(*(_QWORD *)(v13 + 16), 10, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, v12);
  }
  *phkResult = 0;
  v20 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0, 0, a2 | 0x100, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)Key,
      dwOptionsa);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v25);
  return phkResult;
}

```

## disassembly

```asm
0x18004b99c  mov     [rsp-8+arg_10], rbx
0x18004b9a1  mov     [rsp-8+arg_18], rdi
0x18004b9a6  push    rbp
0x18004b9a7  lea     rbp, [rsp-57h]
0x18004b9ac  sub     rsp, 0B0h
0x18004b9b3  mov     rax, cs:__security_cookie
0x18004b9ba  xor     rax, rsp
0x18004b9bd  mov     [rbp+57h+var_10], rax
0x18004b9c1  mov     edi, edx
0x18004b9c3  mov     rbx, rcx
0x18004b9c6  mov     [rbp+57h+var_58], rcx
0x18004b9ca  mov     [rbp+57h+var_5C], 0
0x18004b9d1  lea     rcx, [rbp+57h+var_30]
0x18004b9d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004b9da  nop
0x18004b9db  mov     eax, 100h
0x18004b9e0  mov     [rbp+57h+var_60], eax
0x18004b9e3  mov     edx, eax
0x18004b9e5  shr     rdx, 1
0x18004b9e8  lea     rcx, [rbp+57h+var_30]
0x18004b9ec  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004b9f1  mov     edx, [rbp+57h+var_60]
0x18004b9f4  lea     rcx, [rbp+57h+var_30]
0x18004b9f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b9fd  lea     rcx, [rbp+57h+var_60]
0x18004ba01  mov     [rsp+0B0h+lpSecurityAttributes], rcx
0x18004ba06  mov     [rsp+0B0h+samDesired], edx
0x18004ba0a  mov     qword ptr [rsp+0B0h+dwOptions], rax; int
0x18004ba0f  xor     r9d, r9d
0x18004ba12  lea     r8, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004ba19  xor     edx, edx
0x18004ba1b  lea     rcx, aCapabilityacce_6; "CapabilityAccessManager"
0x18004ba22  call    cs:__imp_RtlGetPersistedStateLocation
0x18004ba28  cmp     eax, 80000005h
0x18004ba2d  jnz     short loc_18004BA34
0x18004ba2f  mov     eax, [rbp+57h+var_60]
0x18004ba32  jmp     short loc_18004B9E3
0x18004ba34  mov     rcx, [rbp+5Fh]; this
0x18004ba38  test    eax, eax
0x18004ba3a  jns     short loc_18004BA51
0x18004ba3c  mov     r9d, eax; char *
0x18004ba3f  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004ba46  mov     edx, 9Fh; void *
0x18004ba4b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004ba51  mov     edx, [rbp+57h+var_60]
0x18004ba54  shr     rdx, 1
0x18004ba57  dec     rdx
0x18004ba5a  lea     rcx, [rbp+57h+var_30]
0x18004ba5e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004ba63  lea     rdx, [rbp+57h+var_30]
0x18004ba67  lea     rcx, [rbp+57h+Src]
0x18004ba6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ba70  nop
0x18004ba71  mov     r8, [rbp+57h+var_40]
0x18004ba75  lea     rcx, [rbp+57h+Src]; Src
0x18004ba79  cmp     r8, [rbp+57h+var_38]
0x18004ba7d  jnb     short loc_18004BAA0
0x18004ba7f  lea     rax, [r8+1]
0x18004ba83  mov     [rbp+57h+var_40], rax
0x18004ba87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ba8c  mov     rdx, rax
0x18004ba8f  mov     word ptr [rax+r8*2], 5Ch ; '\'
0x18004ba96  xor     eax, eax
0x18004ba98  mov     [rdx+r8*2+2], ax
0x18004ba9e  jmp     short loc_18004BAAB
0x18004baa0  mov     r9d, 5Ch ; '\'
0x18004baa6  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004baab  lea     rcx, aConsentstore; "ConsentStore"
0x18004bab2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004bab7  mov     r8, rax
0x18004baba  mov     rdx, rcx
0x18004babd  lea     rcx, [rbp+57h+Src]
0x18004bac1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004bac6  lea     rax, WPP_GLOBAL_Control
0x18004bacd  mov     r10, cs:WPP_GLOBAL_Control
0x18004bad4  cmp     r10, rax
0x18004bad7  jz      short loc_18004BB08
0x18004bad9  test    byte ptr [r10+1Ch], 1
0x18004bade  jz      short loc_18004BB08
0x18004bae0  cmp     byte ptr [r10+19h], 4
0x18004bae5  jb      short loc_18004BB08
0x18004bae7  lea     rcx, [rbp+57h+Src]
0x18004baeb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004baf0  mov     r9, rax
0x18004baf3  mov     edx, 0Ah
0x18004baf8  lea     r8, WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids
0x18004baff  mov     rcx, [r10+10h]
0x18004bb03  call    WPP_SF_S
0x18004bb08  mov     qword ptr [rbx], 0
0x18004bb0f  mov     [rbp+57h+var_5C], 1
0x18004bb16  xor     edx, edx
0x18004bb18  mov     rcx, rbx
0x18004bb1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004bb20  bts     edi, 8
0x18004bb24  lea     rcx, [rbp+57h+Src]
0x18004bb28  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004bb2d  mov     rdx, rax; lpSubKey
0x18004bb30  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18004bb39  mov     [rsp+0B0h+phkResult], rbx; phkResult
0x18004bb3e  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004bb47  mov     [rsp+0B0h+samDesired], edi; samDesired
0x18004bb4b  mov     [rsp+0B0h+dwOptions], 0; unsigned int
0x18004bb53  xor     r9d, r9d; lpClass
0x18004bb56  xor     r8d, r8d; Reserved
0x18004bb59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004bb60  call    cs:__imp_RegCreateKeyExW
0x18004bb66  mov     rcx, [rbp+5Fh]; this
0x18004bb6a  test    eax, eax
0x18004bb6c  jz      short loc_18004BB83
0x18004bb6e  mov     r9d, eax; char *
0x18004bb71  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004bb78  mov     edx, 0B3h; void *
0x18004bb7d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004bb83  lea     rcx, [rbp+57h+Src]
0x18004bb87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bb8c  nop
0x18004bb8d  lea     rcx, [rbp+57h+var_30]
0x18004bb91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004bb96  mov     rax, rbx
0x18004bb99  mov     rcx, [rbp+57h+var_10]
0x18004bb9d  xor     rcx, rsp; StackCookie
0x18004bba0  call    __security_check_cookie
0x18004bba5  lea     r11, [rsp+0B0h+var_s0]
0x18004bbad  mov     rbx, [r11+20h]
0x18004bbb1  mov     rdi, [r11+28h]
0x18004bbb5  mov     rsp, r11
0x18004bbb8  pop     rbp
0x18004bbb9  retn
```
