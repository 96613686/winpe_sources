# SystemSettings::Accessibility::CBrailleLogicSingleton::AddDevice(SystemSettings::Accessibility::BrailleDeviceInfo const &)

- ea: `0x18003171c`
- end: `0x180031bfc`
- name: `?AddDevice@CBrailleLogicSingleton@Accessibility@SystemSettings@@QEAAJAEBUBrailleDeviceInfo@23@@Z`
- size: `1248`
- prototype: `__int64 __fastcall(SystemSettings::Accessibility::CBrailleLogicSingleton *__hidden this, const struct SystemSettings::Accessibility::BrailleDeviceInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003d550`

## callees

- `0x18000c840`
- `0x180012dcc`
- `0x18001362c`
- `0x180019a20`
- `0x1800234f8`
- `0x18002373c`
- `0x180024af8`
- `0x180024c04`
- `0x180027e48`
- `0x18002910c`
- `0x180029410`
- `0x18002a400`
- `0x18002aa84`
- `0x18002b9a8`
- `0x18002e218`
- `0x18003171c`
- `0x180041004`
- `0x180043520`
- `0x180043670`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003190b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCreateUSKeyW` at `0x18003190b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800318bf`
- `SHLWAPI!SHDeleteKeyW` at `0x1800319ba`
- `SHLWAPI!SHDeleteKeyW` at `0x180031a39`
- `SHLWAPI!SHDeleteKeyW` at `0x180031ab8`
- `SHLWAPI!SHDeleteKeyW` at `0x1800319ba`
- `SHLWAPI!SHDeleteKeyW` at `0x180031a39`
- `SHLWAPI!SHDeleteKeyW` at `0x180031ab8`

## string_xrefs

- `0x180031763`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031835`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031926`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031994`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031a13`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031a92`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x180031b72`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SystemSettings::Accessibility::CBrailleLogicSingleton::AddDevice(
        SystemSettings::Accessibility::CBrailleLogicSingleton *this,
        const struct SystemSettings::Accessibility::BrailleDeviceInfo *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  int updated; // eax
  unsigned int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  const WCHAR *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  const WCHAR *v35; // rax
  int v36; // eax
  unsigned int v37; // edi
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  const WCHAR *v41; // rax
  int v42; // eax
  __int64 v43; // rcx
  unsigned int v44; // edi
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  const WCHAR *v48; // rax
  __int64 v49; // rcx
  int v50; // eax
  unsigned int v51; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-A8h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-A8h]
  HUSKEY phNewUSKey; // [rsp+30h] [rbp-98h] BYREF
  __int64 *v55; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v56[32]; // [rsp+48h] [rbp-80h] BYREF
  _BYTE *v57; // [rsp+68h] [rbp-60h] BYREF
  char v58; // [rsp+70h] [rbp-58h]
  __int64 v59; // [rsp+88h] [rbp-40h] BYREF
  _BYTE v60[32]; // [rsp+90h] [rbp-38h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  phNewUSKey = 0;
  if ( *((_QWORD *)a2 + 2) )
  {
    v6 = (_QWORD *)qword_18039C7B0;
    v7 = qword_18039C7B8;
    while ( v6 != (_QWORD *)v7 )
    {
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 64, a2, a3, a4);
      v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6 + 8, v9, v8, v10);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v11, v6[10]) )
      {
        v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 32, a2, a3, a4);
        v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6 + 4, v13, v12, v14);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v15, v6[6]) )
        {
          v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 96, a2, a3, a4);
          v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6 + 12, v17, v16, v18);
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v19, v6[14]) )
          {
            updated = SystemSettings::Accessibility::CBrailleLogicSingleton::UpdateSelectedDevice(v20, v6);
            v22 = updated;
            if ( updated >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5A1,
                (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
                (const char *)(unsigned int)updated,
                dwFlags);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
              return v22;
            }
          }
        }
      }
      v6 += 16;
    }
    v23 = std::operator+<unsigned short>(&v57, qword_18039C4C0, L"\\");
    std::operator+<unsigned short>(v56, v23, a2);
    std::wstring::_Tidy_deallocate(&v57);
    phNewUSKey = 0;
    v27 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v56, v24, v25, v26);
    v28 = SHRegCreateUSKeyW(v27, 2u, 0, &phNewUSKey, 2u);
    if ( v28 )
    {
      v29 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x5AC,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
              (const char *)v28,
              dwFlagsa);
      std::wstring::_Tidy_deallocate(v56);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
      return v29;
    }
    else
    {
      v57 = v56;
      v58 = 1;
      v55 = (__int64 *)phNewUSKey;
      v30 = SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(
              &v55,
              L"Manufacturer",
              (char *)a2 + 32);
      v31 = v30;
      if ( v30 >= 0 )
      {
        v55 = (__int64 *)phNewUSKey;
        v36 = SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(
                &v55,
                L"ConnectionType",
                (char *)a2 + 64);
        v37 = v36;
        if ( v36 >= 0 )
        {
          v55 = (__int64 *)phNewUSKey;
          v42 = SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(
                  &v55,
                  L"SerialPort",
                  (char *)a2 + 96);
          v44 = v42;
          if ( v42 >= 0 )
          {
            v58 = 0;
            if ( qword_18039C7B8 == qword_18039C7C0 )
            {
              std::vector<SystemSettings::Accessibility::BrailleDeviceInfo>::_Emplace_reallocate<SystemSettings::Accessibility::BrailleDeviceInfo const &>(
                &qword_18039C7B0,
                (SystemSettings::Accessibility::BrailleDeviceInfo *)qword_18039C7B8,
                (__int64)a2);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<SystemSettings::Accessibility::BrailleDeviceInfo>>::construct<SystemSettings::Accessibility::BrailleDeviceInfo,SystemSettings::Accessibility::BrailleDeviceInfo const &>(
                v43,
                qword_18039C7B8,
                a2);
              qword_18039C7B8 += 128;
            }
            v59 = 6;
            std::wstring::wstring(v60, a2);
            v61 = 0;
            v55 = &v59;
            SystemSettings::DataModel::CSingletonHelper<SystemSettings::RadialControllerSettings::RadialControllerNotificationItem &>::_Notify<_lambda_eb60a5267e0a38d0fcece130b831a0e1_>(
              &SystemSettings::Accessibility::g_brailleLogicSingleton,
              &v55);
            v50 = SystemSettings::Accessibility::CBrailleLogicSingleton::UpdateSelectedDevice(v49, a2);
            v51 = v50;
            if ( v50 >= 0 )
            {
              std::wstring::_Tidy_deallocate(v60);
              std::wstring::_Tidy_deallocate(v56);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5BF,
                (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
                (const char *)(unsigned int)v50,
                dwFlagsa);
              std::wstring::_Tidy_deallocate(v60);
              std::wstring::_Tidy_deallocate(v56);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
              return v51;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5B6,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
              (const char *)(unsigned int)v42,
              dwFlagsa);
            v48 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v56, v45, v46, v47);
            SHDeleteKeyW(HKEY_CURRENT_USER, v48);
            std::wstring::_Tidy_deallocate(v56);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
            return v44;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5B5,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
            (const char *)(unsigned int)v36,
            dwFlagsa);
          v41 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v56, v38, v39, v40);
          SHDeleteKeyW(HKEY_CURRENT_USER, v41);
          std::wstring::_Tidy_deallocate(v56);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
          return v37;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B4,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
          (const char *)(unsigned int)v30,
          dwFlagsa);
        v35 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v56, v32, v33, v34);
        SHDeleteKeyW(HKEY_CURRENT_USER, v35);
        std::wstring::_Tidy_deallocate(v56);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
        return v31;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x598,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
      (const char *)0x8000FFFFLL,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phNewUSKey);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18003171c  mov     [rsp+arg_0], rbx
0x180031721  mov     [rsp+arg_10], rsi
0x180031726  push    rdi
0x180031727  sub     rsp, 0C0h
0x18003172e  mov     rax, cs:__security_cookie
0x180031735  xor     rax, rsp
0x180031738  mov     [rsp+0C8h+var_10], rax
0x180031740  mov     rbx, rdx
0x180031743  mov     [rsp+0C8h+phNewUSKey], 0
0x18003174c  cmp     qword ptr [rdx+10h], 0
0x180031751  jnz     short loc_180031786
0x180031753  mov     rcx, [rsp+0C8h]; this
0x18003175b  mov     ebx, 8000FFFFh
0x180031760  mov     r9d, ebx; char *
0x180031763  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003176a  mov     edx, 598h; void *
0x18003176f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031774  nop
0x180031775  lea     rcx, [rsp+0C8h+phNewUSKey]
0x18003177a  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003177f  mov     eax, ebx
0x180031781  jmp     loc_180031BD6
0x180031786  mov     rdi, cs:qword_18039C7B0
0x18003178d  mov     rsi, cs:qword_18039C7B8
0x180031794  cmp     rdi, rsi
0x180031797  jz      loc_180031872
0x18003179d  lea     rcx, [rbx+40h]
0x1800317a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800317a6  mov     r8, rax
0x1800317a9  lea     rcx, [rdi+40h]
0x1800317ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800317b2  mov     r9, [rbx+50h]
0x1800317b6  mov     rdx, [rdi+50h]
0x1800317ba  mov     rcx, rax
0x1800317bd  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800317c2  test    al, al
0x1800317c4  jz      loc_180031869
0x1800317ca  lea     rcx, [rbx+20h]
0x1800317ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800317d3  mov     r8, rax
0x1800317d6  lea     rcx, [rdi+20h]
0x1800317da  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800317df  mov     r9, [rbx+30h]
0x1800317e3  mov     rdx, [rdi+30h]
0x1800317e7  mov     rcx, rax
0x1800317ea  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800317ef  test    al, al
0x1800317f1  jz      short loc_180031869
0x1800317f3  lea     rcx, [rbx+60h]
0x1800317f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800317fc  mov     r8, rax
0x1800317ff  lea     rcx, [rdi+60h]
0x180031803  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031808  mov     r9, [rbx+70h]
0x18003180c  mov     rdx, [rdi+70h]
0x180031810  mov     rcx, rax
0x180031813  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180031818  test    al, al
0x18003181a  jz      short loc_180031869
0x18003181c  mov     rdx, rdi
0x18003181f  call    ?UpdateSelectedDevice@CBrailleLogicSingleton@Accessibility@SystemSettings@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Accessibility::CBrailleLogicSingleton::UpdateSelectedDevice(std::wstring const &)
0x180031824  mov     ebx, eax
0x180031826  test    eax, eax
0x180031828  jns     short loc_180031858
0x18003182a  mov     rcx, [rsp+0C8h]; this
0x180031832  mov     r9d, eax; char *
0x180031835  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003183c  mov     edx, 5A1h; void *
0x180031841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031846  nop
0x180031847  lea     rcx, [rsp+0C8h+phNewUSKey]
0x18003184c  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031851  mov     eax, ebx
0x180031853  jmp     loc_180031BD6
0x180031858  lea     rcx, [rsp+0C8h+phNewUSKey]
0x18003185d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031862  xor     eax, eax
0x180031864  jmp     loc_180031BD6
0x180031869  sub     rdi, 0FFFFFFFFFFFFFF80h
0x18003186d  jmp     loc_180031794
0x180031872  lea     r8, Control; "\\"
0x180031879  lea     rdx, qword_18039C4C0
0x180031880  lea     rcx, [rsp+0C8h+var_60]
0x180031885  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003188a  nop
0x18003188b  mov     r8, rbx
0x18003188e  mov     rdx, rax
0x180031891  lea     rcx, [rsp+0C8h+var_80]
0x180031896  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18003189b  nop
0x18003189c  lea     rcx, [rsp+0C8h+var_60]
0x1800318a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800318a6  mov     rax, [rsp+0C8h+phNewUSKey]
0x1800318ab  test    rax, rax
0x1800318ae  jz      short loc_1800318E4
0x1800318b0  mov     [rsp+0C8h+var_88], rax
0x1800318b5  lea     rcx, [rsp+0C8h+var_90]; this
0x1800318ba  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800318bf  mov     rax, cs:__imp_SHRegCloseUSKey
0x1800318c6  mov     [rsp+0C8h+var_60], rax
0x1800318cb  lea     rdx, [rsp+0C8h+var_88]
0x1800318d0  lea     rcx, [rsp+0C8h+var_60]
0x1800318d5  call    ??$invoke@P6AJPEAX@ZAEAPEAX@wistd@@YAJ$$QEAP6AJPEAX@ZAEAPEAX@Z; wistd::invoke<long (*)(void *),void * &>(long (*&&)(void *),void * &)
0x1800318da  lea     rcx, [rsp+0C8h+var_90]; this
0x1800318df  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800318e4  mov     [rsp+0C8h+phNewUSKey], 0
0x1800318ed  lea     rcx, [rsp+0C8h+var_80]
0x1800318f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800318f7  mov     rcx, rax; pwzPath
0x1800318fa  mov     edx, 2; samDesired
0x1800318ff  mov     [rsp+0C8h+dwFlags], edx; int
0x180031903  lea     r9, [rsp+0C8h+phNewUSKey]; phNewUSKey
0x180031908  xor     r8d, r8d; hRelativeUSKey
0x18003190b  call    cs:__imp_SHRegCreateUSKeyW
0x180031912  nop     dword ptr [rax+rax+00h]
0x180031917  test    eax, eax
0x180031919  jz      short loc_180031955
0x18003191b  mov     rcx, [rsp+0C8h]; this
0x180031923  mov     r9d, eax; char *
0x180031926  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003192d  mov     edx, 5ACh; void *
0x180031932  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031937  mov     ebx, eax
0x180031939  lea     rcx, [rsp+0C8h+var_80]
0x18003193e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031943  nop
0x180031944  lea     rcx, [rsp+0C8h+phNewUSKey]
0x180031949  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003194e  mov     eax, ebx
0x180031950  jmp     loc_180031BD6
0x180031955  lea     rax, [rsp+0C8h+var_80]
0x18003195a  mov     [rsp+0C8h+var_60], rax
0x18003195f  mov     [rsp+0C8h+var_58], 1
0x180031964  mov     rax, [rsp+0C8h+phNewUSKey]
0x180031969  mov     [rsp+0C8h+var_90], rax
0x18003196e  lea     r8, [rbx+20h]
0x180031972  lea     rdx, aManufacturer; "Manufacturer"
0x180031979  lea     rcx, [rsp+0C8h+var_90]
0x18003197e  call    ?WriteStringKey@CBrailleLogicSingleton@Accessibility@SystemSettings@@CAJAEBQEAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(void * const &,ushort const *,std::wstring const &)
0x180031983  mov     edi, eax
0x180031985  test    eax, eax
0x180031987  jns     short loc_1800319E3
0x180031989  mov     rcx, [rsp+0C8h]; this
0x180031991  mov     r9d, eax; char *
0x180031994  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003199b  mov     edx, 5B4h; void *
0x1800319a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319a5  nop
0x1800319a6  lea     rcx, [rsp+0C8h+var_80]
0x1800319ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800319b0  mov     rdx, rax; pszSubKey
0x1800319b3  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800319ba  call    cs:__imp_SHDeleteKeyW
0x1800319c1  nop     dword ptr [rax+rax+00h]
0x1800319c6  nop
0x1800319c7  lea     rcx, [rsp+0C8h+var_80]
0x1800319cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800319d1  nop
0x1800319d2  lea     rcx, [rsp+0C8h+phNewUSKey]
0x1800319d7  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800319dc  mov     eax, edi
0x1800319de  jmp     loc_180031BD6
0x1800319e3  mov     rax, [rsp+0C8h+phNewUSKey]
0x1800319e8  mov     [rsp+0C8h+var_90], rax
0x1800319ed  lea     r8, [rbx+40h]
0x1800319f1  lea     rdx, aConnectiontype; "ConnectionType"
0x1800319f8  lea     rcx, [rsp+0C8h+var_90]
0x1800319fd  call    ?WriteStringKey@CBrailleLogicSingleton@Accessibility@SystemSettings@@CAJAEBQEAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(void * const &,ushort const *,std::wstring const &)
0x180031a02  mov     edi, eax
0x180031a04  test    eax, eax
0x180031a06  jns     short loc_180031A62
0x180031a08  mov     rcx, [rsp+0C8h]; this
0x180031a10  mov     r9d, eax; char *
0x180031a13  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180031a1a  mov     edx, 5B5h; void *
0x180031a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a24  nop
0x180031a25  lea     rcx, [rsp+0C8h+var_80]
0x180031a2a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031a2f  mov     rdx, rax; pszSubKey
0x180031a32  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180031a39  call    cs:__imp_SHDeleteKeyW
0x180031a40  nop     dword ptr [rax+rax+00h]
0x180031a45  nop
0x180031a46  lea     rcx, [rsp+0C8h+var_80]
0x180031a4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031a50  nop
0x180031a51  lea     rcx, [rsp+0C8h+phNewUSKey]
0x180031a56  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031a5b  mov     eax, edi
0x180031a5d  jmp     loc_180031BD6
0x180031a62  mov     rax, [rsp+0C8h+phNewUSKey]
0x180031a67  mov     [rsp+0C8h+var_90], rax
0x180031a6c  lea     r8, [rbx+60h]
0x180031a70  lea     rdx, aSerialport; "SerialPort"
0x180031a77  lea     rcx, [rsp+0C8h+var_90]
0x180031a7c  call    ?WriteStringKey@CBrailleLogicSingleton@Accessibility@SystemSettings@@CAJAEBQEAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Accessibility::CBrailleLogicSingleton::WriteStringKey(void * const &,ushort const *,std::wstring const &)
0x180031a81  mov     edi, eax
0x180031a83  test    eax, eax
0x180031a85  jns     short loc_180031AE1
0x180031a87  mov     rcx, [rsp+0C8h]; this
0x180031a8f  mov     r9d, eax; char *
0x180031a92  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180031a99  mov     edx, 5B6h; void *
0x180031a9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031aa3  nop
0x180031aa4  lea     rcx, [rsp+0C8h+var_80]
0x180031aa9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180031aae  mov     rdx, rax; pszSubKey
0x180031ab1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180031ab8  call    cs:__imp_SHDeleteKeyW
0x180031abf  nop     dword ptr [rax+rax+00h]
0x180031ac4  nop
0x180031ac5  lea     rcx, [rsp+0C8h+var_80]
0x180031aca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031acf  nop
0x180031ad0  lea     rcx, [rsp+0C8h+phNewUSKey]
0x180031ad5  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031ada  mov     eax, edi
0x180031adc  jmp     loc_180031BD6
0x180031ae1  mov     [rsp+0C8h+var_58], 0
0x180031ae6  mov     rdx, cs:qword_18039C7B8
0x180031aed  mov     r8, rbx
0x180031af0  cmp     rdx, cs:qword_18039C7C0
0x180031af7  jz      short loc_180031B08
0x180031af9  call    ??$construct@UBrailleDeviceInfo@Accessibility@SystemSettings@@AEBU123@@?$_Default_allocator_traits@V?$allocator@UBrailleDeviceInfo@Accessibility@SystemSettings@@@std@@@std@@SAXAEAV?$allocator@UBrailleDeviceInfo@Accessibility@SystemSettings@@@1@QEAUBrailleDeviceInfo@Accessibility@SystemSettings@@AEBU345@@Z; std::_Default_allocator_traits<std::allocator<SystemSettings::Accessibility::BrailleDeviceInfo>>::construct<SystemSettings::Accessibility::BrailleDeviceInfo,SystemSettings::Accessibility::BrailleDeviceInfo const &>(std::allocator<SystemSettings::Accessibility::BrailleDeviceInfo> &,SystemSettings::Accessibility::BrailleDeviceInfo * const,SystemSettings::Accessibility::BrailleDeviceInfo const &)
0x180031afe  sub     cs:qword_18039C7B8, 0FFFFFFFFFFFFFF80h
0x180031b06  jmp     short loc_180031B14
0x180031b08  lea     rcx, qword_18039C7B0
0x180031b0f  call    ??$_Emplace_reallocate@AEBUBrailleDeviceInfo@Accessibility@SystemSettings@@@?$vector@UBrailleDeviceInfo@Accessibility@SystemSettings@@V?$allocator@UBrailleDeviceInfo@Accessibility@SystemSettings@@@std@@@std@@AEAAPEAUBrailleDeviceInfo@Accessibility@SystemSettings@@QEAU234@AEBU234@@Z; std::vector<SystemSettings::Accessibility::BrailleDeviceInfo>::_Emplace_reallocate<SystemSettings::Accessibility::BrailleDeviceInfo const &>(SystemSettings::Accessibility::BrailleDeviceInfo * const,SystemSettings::Accessibility::BrailleDeviceInfo const &)
0x180031b14  mov     [rsp+0C8h+var_40], 6
0x180031b20  mov     rdx, rbx
0x180031b23  lea     rcx, [rsp+0C8h+var_38]
0x180031b2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180031b30  nop
0x180031b31  xor     eax, eax
0x180031b33  mov     [rsp+0C8h+var_18], rax
0x180031b3b  lea     rax, [rsp+0C8h+var_40]
0x180031b43  mov     [rsp+0C8h+var_90], rax
0x180031b48  lea     rdx, [rsp+0C8h+var_90]
0x180031b4d  lea     rcx, ?g_brailleLogicSingleton@Accessibility@SystemSettings@@3VCBrailleLogicSingleton@12@A; SystemSettings::Accessibility::CBrailleLogicSingleton SystemSettings::Accessibility::g_brailleLogicSingleton
0x180031b54  call    ??$_Notify@V_lambda_eb60a5267e0a38d0fcece130b831a0e1_@@@?$CSingletonHelper@AEAURadialControllerNotificationItem@RadialControllerSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_eb60a5267e0a38d0fcece130b831a0e1_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::RadialControllerSettings::RadialControllerNotificationItem &>::_Notify<_lambda_eb60a5267e0a38d0fcece130b831a0e1_>(_lambda_eb60a5267e0a38d0fcece130b831a0e1_ const &)
0x180031b59  mov     rdx, rbx
0x180031b5c  call    ?UpdateSelectedDevice@CBrailleLogicSingleton@Accessibility@SystemSettings@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Accessibility::CBrailleLogicSingleton::UpdateSelectedDevice(std::wstring const &)
0x180031b61  mov     ebx, eax
0x180031b63  test    eax, eax
0x180031b65  jns     short loc_180031BAB
0x180031b67  mov     rcx, [rsp+0C8h]; this
0x180031b6f  mov     r9d, eax; char *
0x180031b72  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x180031b79  mov     edx, 5BFh; void *
0x180031b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031b83  nop
0x180031b84  lea     rcx, [rsp+0C8h+var_38]
0x180031b8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031b91  nop
0x180031b92  lea     rcx, [rsp+0C8h+var_80]
0x180031b97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031b9c  nop
0x180031b9d  lea     rcx, [rsp+0C8h+phNewUSKey]
0x180031ba2  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031ba7  mov     eax, ebx
0x180031ba9  jmp     short loc_180031BD6
0x180031bab  lea     rcx, [rsp+0C8h+var_38]
0x180031bb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031bb8  nop
0x180031bb9  lea     rcx, [rsp+0C8h+var_80]
0x180031bbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031bc3  nop
0x180031bc4  lea     rcx, [rsp+0C8h+phNewUSKey]
0x180031bc9  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?SHRegCloseUSKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&SHRegCloseUSKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031bce  xor     eax, eax
0x180031bd0  jmp     short loc_180031BD6
0x180031bd2  mov     eax, dword ptr [rsp+0C8h+phNewUSKey]
0x180031bd6  mov     rcx, [rsp+0C8h+var_10]
0x180031bde  xor     rcx, rsp; StackCookie
0x180031be1  call    __security_check_cookie
0x180031be6  lea     r11, [rsp+0C8h+var_8]
0x180031bee  mov     rbx, [r11+10h]
0x180031bf2  mov     rsi, [r11+20h]
0x180031bf6  mov     rsp, r11
0x180031bf9  pop     rdi
0x180031bfa  retn
```
