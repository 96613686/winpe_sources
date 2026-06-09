# CMidiConfigurationManager::GetEnabledTransports(void)

- ea: `0x1400238a4`
- end: `0x140023d4c`
- name: `?GetEnabledTransports@CMidiConfigurationManager@@QEBA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ`
- size: `1192`
- prototype: `CLSID **__fastcall(__int64, CLSID **)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140023398`
- `0x140030b10`

## callees

- `0x140002490`
- `0x1400054c0`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000c598`
- `0x14001487c`
- `0x140021c00`
- `0x140022954`
- `0x1400229d8`
- `0x1400238a4`
- `0x1400261b4`
- `0x1400264ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140023b83`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140023b83`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140023a7d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140023a7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140023930`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140023930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023cd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023cfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023cd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140023cfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140023a25`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140023a25`

## string_xrefs

- `0x140023d39`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x140023b3d`: `CLSID`
- `0x140023922`: `Software\Microsoft\Windows MIDI Services\Transport Plugins`
- `0x140023aa6`: `Software\Microsoft\Windows MIDI Services\Transport Plugins`
- `0x140023c47`: `CMidiConfigurationManager::GetEnabledTransports`
- `0x140023b98`: `avcore\midi2\service\exe\midiconfigurationmanager.cpp`
- `0x140023c38`: `Duplicate transport GUID in registry`

## pseudocode

```c
CLSID **__fastcall CMidiConfigurationManager::GetEnabledTransports(__int64 a1, CLSID **a2)
{
  CLSID **v2; // rdi
  int v3; // eax
  DWORD v4; // eax
  DWORD i; // esi
  __int64 v6; // rdx
  __int128 *p_Src; // r8
  int v8; // eax
  const OLECHAR *v9; // rcx
  HRESULT v10; // eax
  CLSID *v11; // rdx
  CLSID *v12; // rax
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  int phkResult; // [rsp+20h] [rbp-528h]
  int phkResulta; // [rsp+20h] [rbp-528h]
  int v19; // [rsp+60h] [rbp-4E8h]
  DWORD cSubKeys; // [rsp+68h] [rbp-4E0h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-4DCh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-4D8h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+78h] [rbp-4D0h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-4CCh] BYREF
  DWORD cbMaxValueNameLen; // [rsp+80h] [rbp-4C8h] BYREF
  DWORD cValues; // [rsp+84h] [rbp-4C4h] BYREF
  DWORD cbMaxClassLen; // [rsp+88h] [rbp-4C0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+8Ch] [rbp-4BCh] BYREF
  DWORD cchClass; // [rsp+90h] [rbp-4B8h] BYREF
  HKEY hkey; // [rsp+98h] [rbp-4B0h] BYREF
  CLSID **v31; // [rsp+A0h] [rbp-4A8h]
  struct _FILETIME ftLastWriteTime; // [rsp+A8h] [rbp-4A0h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-498h] BYREF
  CLSID *p_pclsid; // [rsp+B8h] [rbp-490h] BYREF
  const wchar_t *v35; // [rsp+C0h] [rbp-488h] BYREF
  const char *v36; // [rsp+C8h] [rbp-480h] BYREF
  CLSID pclsid; // [rsp+D0h] [rbp-478h] BYREF
  __int128 Src; // [rsp+E0h] [rbp-468h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-458h]
  LPCOLESTR lpsz[4]; // [rsp+100h] [rbp-448h] BYREF
  WCHAR Class; // [rsp+120h] [rbp-428h] BYREF
  char v42[526]; // [rsp+122h] [rbp-426h] BYREF
  WCHAR Name[256]; // [rsp+330h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  v2 = a2;
  v31 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(a2, 0, &GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a);
  v19 = 3;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows MIDI Services\\Transport Plugins",
         0,
         0x20019u,
         &hKey);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v3,
      phkResult);
  cchName = 0;
  Class = 0;
  memset_0(v42, 0, 0x206u);
  cchClass = 260;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  RegQueryInfoKeyW(
    hKey,
    &Class,
    &cchClass,
    0,
    &cSubKeys,
    &cbMaxSubKeyLen,
    &cbMaxClassLen,
    &cValues,
    &cbMaxValueNameLen,
    &cbMaxValueLen,
    &cbSecurityDescriptor,
    &ftLastWriteTime);
  v4 = cSubKeys;
  if ( cSubKeys )
  {
    for ( i = 0; i < v4; ++i )
    {
      cchName = 255;
      if ( !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
      {
        Src = 0;
        v39 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          &Src,
          L"Software\\Microsoft\\Windows MIDI Services\\Transport Plugins",
          58);
        std::wstring::operator+=(&Src, L"\\");
        std::wstring::operator+=(&Src, Name);
        p_Src = &Src;
        if ( *((_QWORD *)&v39 + 1) > 7u )
          p_Src = (__int128 *)Src;
        wil::reg::open_unique_key(&hkey, v6, p_Src);
        try
        {
          v8 = wil::reg::get_value<unsigned long>(hkey);
        }
        catch ( ... )
        {
          v2 = v31;
          goto LABEL_12;
        }
        if ( v8 )
        {
LABEL_12:
          pclsid = 0;
          wil::reg::get_value<std::wstring>(lpsz, hkey, 0, L"CLSID");
          v19 |= 8u;
          v9 = (const OLECHAR *)lpsz;
          if ( lpsz[3] > (LPCOLESTR)7 )
            v9 = lpsz[0];
          v10 = CLSIDFromString(v9, &pclsid);
          if ( v10 >= 0 )
          {
            if ( !v10 )
            {
              v11 = v2[1];
              v12 = *v2;
              if ( *v2 == v11 )
              {
LABEL_21:
                if ( v11 == v2[2] )
                {
                  std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v2, v11, &pclsid);
                }
                else
                {
                  *v11 = pclsid;
                  ++v2[1];
                }
              }
              else
              {
                while ( *(_QWORD *)&v12->Data1 != *(_QWORD *)&pclsid.Data1
                     || *(_QWORD *)v12->Data4 != *(_QWORD *)pclsid.Data4 )
                {
                  if ( ++v12 == v11 )
                    goto LABEL_21;
                }
                v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
                if ( *v13 > 3u )
                {
                  v33 = a1;
                  p_pclsid = &pclsid;
                  v35 = L"Duplicate transport GUID in registry";
                  v36 = "CMidiConfigurationManager::GetEnabledTransports";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
                    (_DWORD)v13,
                    (unsigned int)&word_1400888EE,
                    v14,
                    v15,
                    (__int64)&v36,
                    (__int64)&v35,
                    (__int64)&p_pclsid,
                    (__int64)&v33);
                }
              }
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x7D,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiconfigurationmanager.cpp",
              (const char *)(unsigned int)v10,
              phkResulta);
          }
          std::wstring::~wstring(lpsz);
        }
        if ( hkey )
          RegCloseKey(hkey);
        std::wstring::~wstring(&Src);
      }
      v4 = cSubKeys;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1400238a4  mov     r11, rsp
0x1400238a7  mov     [r11+18h], rbx
0x1400238ab  mov     [r11+20h], rsi
0x1400238af  mov     [r11+8], rcx
0x1400238b3  push    rdi
0x1400238b4  sub     rsp, 540h
0x1400238bb  mov     rax, cs:__security_cookie
0x1400238c2  xor     rax, rsp
0x1400238c5  mov     [rsp+548h+var_18], rax
0x1400238cd  mov     rdi, rdx
0x1400238d0  mov     [r11-4A8h], rdx
0x1400238d7  xor     ebx, ebx
0x1400238d9  mov     [rsp+548h+var_4E8], ebx
0x1400238dd  mov     [rdx], rbx
0x1400238e0  mov     [rdx+8], rbx
0x1400238e4  mov     [rdx+10h], rbx
0x1400238e8  mov     [rsp+548h+var_4E8], 1
0x1400238f0  lea     r8, _GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a
0x1400238f7  xor     edx, edx
0x1400238f9  mov     rcx, rdi
0x1400238fc  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x140023901  nop
0x140023902  mov     [rsp+548h+var_4E8], 3
0x14002390a  mov     [rsp+548h+hKey], rbx
0x14002390f  lea     rax, [rsp+548h+hKey]
0x140023914  mov     [rsp+548h+phkResult], rax; int
0x140023919  mov     r9d, 20019h; samDesired
0x14002391f  xor     r8d, r8d; ulOptions
0x140023922  lea     rdx, SubKey; "Software\\Microsoft\\Windows MIDI Servi"...
0x140023929  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023930  call    cs:__imp_RegOpenKeyExW
0x140023936  test    eax, eax
0x140023938  jle     short loc_140023942
0x14002393a  movzx   eax, ax
0x14002393d  or      eax, 80070000h
0x140023942  mov     rcx, [rsp+548h]; this
0x14002394a  test    eax, eax
0x14002394c  js      loc_140023D36
0x140023952  mov     [rsp+548h+cchName], ebx
0x140023956  mov     [rsp+548h+Class], bx
0x14002395e  xor     edx, edx; Val
0x140023960  mov     r8d, 206h; Size
0x140023966  lea     rcx, [rsp+548h+var_426]; void *
0x14002396e  call    memset_0
0x140023973  mov     [rsp+548h+cchClass], 104h
0x14002397e  mov     [rsp+548h+cSubKeys], ebx
0x140023982  mov     [rsp+548h+cbMaxSubKeyLen], ebx
0x140023989  mov     [rsp+548h+cbMaxClassLen], ebx
0x140023990  mov     [rsp+548h+cValues], ebx
0x140023997  mov     [rsp+548h+cbMaxValueNameLen], ebx
0x14002399e  mov     [rsp+548h+cbMaxValueLen], ebx
0x1400239a2  mov     [rsp+548h+cbSecurityDescriptor], ebx
0x1400239a6  mov     qword ptr [rsp+548h+ftLastWriteTime.dwLowDateTime], rbx
0x1400239ae  lea     rax, [rsp+548h+ftLastWriteTime]
0x1400239b6  mov     [rsp+548h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400239bb  lea     rax, [rsp+548h+cbSecurityDescriptor]
0x1400239c0  mov     [rsp+548h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1400239c5  lea     rax, [rsp+548h+cbMaxValueLen]
0x1400239ca  mov     [rsp+548h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400239cf  lea     rax, [rsp+548h+cbMaxValueNameLen]
0x1400239d7  mov     [rsp+548h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1400239dc  lea     rax, [rsp+548h+cValues]
0x1400239e4  mov     [rsp+548h+lpcValues], rax; lpcValues
0x1400239e9  lea     rax, [rsp+548h+cbMaxClassLen]
0x1400239f1  mov     [rsp+548h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1400239f6  lea     rax, [rsp+548h+cbMaxSubKeyLen]
0x1400239fe  mov     [rsp+548h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140023a03  lea     rax, [rsp+548h+cSubKeys]
0x140023a08  mov     [rsp+548h+phkResult], rax; lpcSubKeys
0x140023a0d  xor     r9d, r9d; lpReserved
0x140023a10  lea     r8, [rsp+548h+cchClass]; lpcchClass
0x140023a18  lea     rdx, [rsp+548h+Class]; lpClass
0x140023a20  mov     rcx, [rsp+548h+hKey]; hKey
0x140023a25  call    cs:__imp_RegQueryInfoKeyW
0x140023a2b  mov     eax, [rsp+548h+cSubKeys]
0x140023a2f  test    eax, eax
0x140023a31  jz      loc_140023CF3
0x140023a37  mov     esi, ebx
0x140023a39  mov     [rsp+548h+var_4E4], esi
0x140023a3d  cmp     esi, eax
0x140023a3f  jnb     loc_140023CF3
0x140023a45  mov     [rsp+548h+cchName], 0FFh
0x140023a4d  lea     rax, [rsp+548h+ftLastWriteTime]
0x140023a55  mov     [rsp+548h+lpcValues], rax; lpftLastWriteTime
0x140023a5a  mov     [rsp+548h+lpcbMaxClassLen], rbx; lpcchClass
0x140023a5f  mov     [rsp+548h+lpcbMaxSubKeyLen], rbx; lpClass
0x140023a64  mov     [rsp+548h+phkResult], rbx; lpReserved
0x140023a69  lea     r9, [rsp+548h+cchName]; lpcchName
0x140023a6e  lea     r8, [rsp+548h+Name]; lpName
0x140023a76  mov     edx, esi; dwIndex
0x140023a78  mov     rcx, [rsp+548h+hKey]; hKey
0x140023a7d  call    cs:__imp_RegEnumKeyExW
0x140023a83  test    eax, eax
0x140023a85  jnz     loc_140023CE8
0x140023a8b  xorps   xmm0, xmm0
0x140023a8e  movups  [rsp+548h+Src], xmm0
0x140023a96  xorps   xmm1, xmm1
0x140023a99  movdqu  [rsp+548h+var_458], xmm1
0x140023aa2  lea     r8d, [rax+3Ah]
0x140023aa6  lea     rdx, SubKey; "Software\\Microsoft\\Windows MIDI Servi"...
0x140023aad  lea     rcx, [rsp+548h+Src]
0x140023ab5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140023aba  nop
0x140023abb  lea     rdx, asc_14007D0AC; "\\"
0x140023ac2  lea     rcx, [rsp+548h+Src]; Src
0x140023aca  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x140023acf  lea     rdx, [rsp+548h+Name]; void *
0x140023ad7  lea     rcx, [rsp+548h+Src]; Src
0x140023adf  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x140023ae4  lea     r8, [rsp+548h+Src]
0x140023aec  cmp     qword ptr [rsp+548h+var_458+8], 7
0x140023af5  cmova   r8, qword ptr [rsp+548h+Src]
0x140023afe  lea     rcx, [rsp+548h+hkey]
0x140023b06  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x140023b0b  nop
0x140023b0c  mov     rcx, [rsp+548h+hkey]
0x140023b14  call    ??$get_value@K@reg@wil@@YAKPEAUHKEY__@@PEBG@Z; wil::reg::get_value<ulong>(HKEY__ *,ushort const *)
0x140023b19  nop
0x140023b1a  test    eax, eax
0x140023b1c  jz      loc_140023CC7
0x140023b22  jmp     short loc_140023B32
0x140023b24  xor     ebx, ebx
0x140023b26  mov     esi, [rsp+548h+var_4E4]
0x140023b2a  mov     rdi, [rsp+548h+var_4A8]
0x140023b32  xorps   xmm0, xmm0
0x140023b35  movups  xmmword ptr [rsp+548h+pclsid.Data1], xmm0
0x140023b3d  lea     r9, aClsid_0; "CLSID"
0x140023b44  xor     r8d, r8d; lpSubKey
0x140023b47  mov     rdx, [rsp+548h+hkey]; hkey
0x140023b4f  lea     rcx, [rsp+548h+lpsz]; Src
0x140023b57  call    ??$get_value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1@Z; wil::reg::get_value<std::wstring>(HKEY__ *,ushort const *,ushort const *)
0x140023b5c  or      [rsp+548h+var_4E8], 8
0x140023b61  lea     rcx, [rsp+548h+lpsz]
0x140023b69  cmp     [rsp+548h+var_430], 7
0x140023b72  cmova   rcx, [rsp+548h+lpsz]; lpsz
0x140023b7b  lea     rdx, [rsp+548h+pclsid]; pclsid
0x140023b83  call    cs:__imp_CLSIDFromString
0x140023b89  mov     rcx, [rsp+548h]; this
0x140023b91  test    eax, eax
0x140023b93  jns     short loc_140023BAE
0x140023b95  mov     r9d, eax; char *
0x140023b98  lea     r8, aAvcoreMidi2Ser_7; "avcore\\midi2\\service\\exe\\midiconfig"...
0x140023b9f  mov     edx, 7Dh ; '}'; void *
0x140023ba4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140023ba9  jmp     loc_140023CA9
0x140023bae  jnz     loc_140023CA9
0x140023bb4  mov     rdx, [rdi+8]
0x140023bb8  mov     rax, [rdi]
0x140023bbb  cmp     rax, rdx
0x140023bbe  jz      short loc_140023BE4
0x140023bc0  mov     rcx, qword ptr [rsp+548h+pclsid.Data4]
0x140023bc8  mov     r8, qword ptr [rsp+548h+pclsid.Data1]
0x140023bd0  cmp     [rax], r8
0x140023bd3  jnz     short loc_140023BDB
0x140023bd5  cmp     [rax+8], rcx
0x140023bd9  jz      short loc_140023C04
0x140023bdb  add     rax, 10h
0x140023bdf  cmp     rax, rdx
0x140023be2  jnz     short loc_140023BD0
0x140023be4  cmp     rdx, [rdi+10h]
0x140023be8  jz      loc_140023C98
0x140023bee  movups  xmm0, xmmword ptr [rsp+548h+pclsid.Data1]
0x140023bf6  movdqu  xmmword ptr [rdx], xmm0
0x140023bfa  add     qword ptr [rdi+8], 10h
0x140023bff  jmp     loc_140023CA9
0x140023c04  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140023c09  mov     rcx, [rax+8]
0x140023c0d  mov     eax, [rcx]
0x140023c0f  cmp     eax, 3
0x140023c12  jbe     loc_140023CA9
0x140023c18  mov     rax, [rsp+548h+arg_0]
0x140023c20  mov     [rsp+548h+var_498], rax
0x140023c28  lea     rax, [rsp+548h+pclsid]
0x140023c30  mov     [rsp+548h+var_490], rax
0x140023c38  lea     rax, aDuplicateTrans; "Duplicate transport GUID in registry"
0x140023c3f  mov     [rsp+548h+var_488], rax
0x140023c47  lea     rax, aCmidiconfigura_5; "CMidiConfigurationManager::GetEnabledTr"...
0x140023c4e  mov     [rsp+548h+var_480], rax
0x140023c56  lea     rax, [rsp+548h+var_498]
0x140023c5e  mov     [rsp+548h+lpcValues], rax
0x140023c63  lea     rax, [rsp+548h+var_490]
0x140023c6b  mov     [rsp+548h+lpcbMaxClassLen], rax
0x140023c70  lea     rax, [rsp+548h+var_488]
0x140023c78  mov     [rsp+548h+lpcbMaxSubKeyLen], rax
0x140023c7d  lea     rax, [rsp+548h+var_480]
0x140023c85  mov     [rsp+548h+phkResult], rax
0x140023c8a  lea     rdx, word_1400888EE
0x140023c91  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x140023c96  jmp     short loc_140023CA9
0x140023c98  lea     r8, [rsp+548h+pclsid]
0x140023ca0  mov     rcx, rdi
0x140023ca3  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x140023ca8  nop
0x140023ca9  lea     rcx, [rsp+548h+lpsz]; void *
0x140023cb1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023cb6  nop
0x140023cb7  jmp     short loc_140023CC7
0x140023cb9  xor     ebx, ebx
0x140023cbb  mov     esi, [rsp+548h+var_4E4]
0x140023cbf  mov     rdi, [rsp+548h+var_4A8]
0x140023cc7  mov     rcx, [rsp+548h+hkey]; hKey
0x140023ccf  test    rcx, rcx
0x140023cd2  jz      short loc_140023CDB
0x140023cd4  call    cs:__imp_RegCloseKey
0x140023cda  nop
0x140023cdb  lea     rcx, [rsp+548h+Src]; void *
0x140023ce3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023ce8  inc     esi
0x140023cea  mov     eax, [rsp+548h+cSubKeys]
0x140023cee  jmp     loc_140023A39
0x140023cf3  mov     rcx, [rsp+548h+hKey]; hKey
0x140023cf8  test    rcx, rcx
0x140023cfb  jz      short loc_140023D04
0x140023cfd  call    cs:__imp_RegCloseKey
0x140023d03  nop
0x140023d04  jmp     short loc_140023D0E
0x140023d06  mov     rdi, [rsp+548h+var_4A8]
0x140023d0e  mov     rax, rdi
0x140023d11  mov     rcx, [rsp+548h+var_18]
0x140023d19  xor     rcx, rsp; StackCookie
0x140023d1c  call    __security_check_cookie
0x140023d21  lea     r11, [rsp+548h+var_8]
0x140023d29  mov     rbx, [r11+20h]
0x140023d2d  mov     rsi, [r11+28h]
0x140023d31  mov     rsp, r11
0x140023d34  pop     rdi
0x140023d35  retn
0x140023d36  mov     r9d, eax; char *
0x140023d39  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023d40  mov     edx, 1CBEh; void *
0x140023d45  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
