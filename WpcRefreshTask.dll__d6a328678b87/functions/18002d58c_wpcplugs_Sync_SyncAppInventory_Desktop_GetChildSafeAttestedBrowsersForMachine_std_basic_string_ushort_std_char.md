# wpcplugs::Sync::SyncAppInventory::Desktop::GetChildSafeAttestedBrowsersForMachine(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18002d58c`
- end: `0x18002dbe3`
- name: `?GetChildSafeAttestedBrowsersForMachine@Desktop@SyncAppInventory@Sync@wpcplugs@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z`
- size: `1623`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x1800887b4`

## callees

- `0x1800060a0`
- `0x1800060fc`
- `0x180006108`
- `0x180007e28`
- `0x1800082bc`
- `0x180008d50`
- `0x180009a80`
- `0x18000bba8`
- `0x18000e840`
- `0x18001cfa0`
- `0x18002cc64`
- `0x18002d0b0`
- `0x18002d58c`
- `0x18002eb54`
- `0x18002eccc`
- `0x18002edc0`
- `0x1800717b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d686`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002d961`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002d961`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d6e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d6e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d5f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d5f5`

## string_xrefs

- `0x18002d61a`: `Error opening registry key:  {0}`
- `0x18002db6b`: `Key is empty to read attested apps from:  {0}`
- `0x18002d709`: `Error querying registry key info: {0}`
- `0x18002da42`: `Error reading registry value at index: {0}: {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall wpcplugs::Sync::SyncAppInventory::Desktop::GetChildSafeAttestedBrowsersForMachine(
        const WCHAR *lpSubKey,
        __int64 *a2)
{
  const WCHAR *v3; // rbx
  unsigned int v4; // esi
  Private::Format *v5; // rbx
  __int64 v6; // rax
  Private::Format *v7; // rax
  unsigned int v8; // esi
  Private::Format *v9; // rbx
  __int64 v10; // rax
  Private::Format *v11; // rax
  Private::Format *v12; // rbx
  __int64 v13; // rax
  Private::Format *v14; // rax
  Private::Format *v15; // rbx
  __int64 v16; // rax
  Private::Format *v17; // rax
  __int64 v18; // r14
  unsigned __int64 v19; // rsi
  size_t v20; // rcx
  _QWORD *v21; // rbx
  void *v22; // rax
  WCHAR *v23; // rsi
  unsigned __int64 v24; // rdx
  BYTE *v25; // r15
  DWORD v26; // r14d
  unsigned int v27; // r12d
  __int64 v28; // rbx
  unsigned __int64 v29; // r8
  char **v30; // rcx
  Private::Format *v31; // rbx
  _WORD *v32; // r9
  DWORD v33; // r8d
  Private::Format *v34; // rbx
  __int64 v35; // rax
  Private::Format *v36; // rax
  unsigned __int64 v37; // rdx
  Private::Format *v38; // rax
  Private::Format *v39; // rax
  WCHAR *v40; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  BYTE *v48; // [rsp+88h] [rbp-78h]
  WCHAR *v49; // [rsp+90h] [rbp-70h]
  __int128 v50; // [rsp+98h] [rbp-68h] BYREF
  __int128 v51; // [rsp+A8h] [rbp-58h]
  __int128 v52; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-38h]
  __int64 v54; // [rsp+D0h] [rbp-30h]
  char *v55[5]; // [rsp+D8h] [rbp-28h] BYREF
  char *v56[10]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[6]; // [rsp+152h] [rbp+52h] BYREF

  v3 = lpSubKey;
  if ( !*((_QWORD *)lpSubKey + 2) )
  {
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v52,
      L"Key is empty to read attested apps from:  {0}",
      0x2Du);
    v38 = (Private::Format *)StringAlgo::FormatString(v56, &v52);
    v39 = Private::Format::operator%<std::wstring>(v38, (__int64)v3);
    LODWORD(v40) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v39);
    std::wstring::~wstring(v56);
    return;
  }
  hKey = 0;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    v3 = *(const WCHAR **)lpSubKey;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v50 = 0;
    v51 = 0u;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v50, L"Error opening registry key:  {0}", 0x20u);
    v5 = (Private::Format *)StringAlgo::FormatString(v55, &v50);
    v6 = std::to_wstring(&v52, v4);
    v7 = Private::Format::operator%<std::wstring>(v5, v6);
    LODWORD(v40) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v7);
    std::wstring::~wstring((char **)&v52);
LABEL_6:
    std::wstring::~wstring(v55);
    goto LABEL_7;
  }
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v51 = 0u;
  v50 = 0;
  if ( v8 )
  {
    std::wstring::_Construct<1,unsigned short const *>((char **)&v50, L"Error querying registry key info: {0}", 0x25u);
    v9 = (Private::Format *)StringAlgo::FormatString(v55, &v50);
    v10 = std::to_wstring(&v52, v8);
    v11 = Private::Format::operator%<std::wstring>(v9, v10);
    LODWORD(v40) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v11);
    std::wstring::~wstring((char **)&v52);
    goto LABEL_6;
  }
  if ( !cValues )
  {
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v50,
      L"no browsers found which are attested as safe on this machine : {0}",
      0x42u);
    v12 = (Private::Format *)StringAlgo::FormatString(v55, &v50);
    v13 = std::to_wstring(&v52, cValues);
    v14 = Private::Format::operator%<std::wstring>(v12, v13);
    LODWORD(v40) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v14);
    std::wstring::~wstring((char **)&v52);
    goto LABEL_6;
  }
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&v50,
    L"no. of browsers found which are attested as safe on this machine : {0}",
    0x46u);
  v15 = (Private::Format *)StringAlgo::FormatString(v55, &v50);
  v16 = std::to_wstring(&v52, cValues);
  v17 = Private::Format::operator%<std::wstring>(v15, v16);
  LODWORD(v40) = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v17);
  std::wstring::~wstring((char **)&v52);
  std::wstring::~wstring(v55);
  v18 = (a2[1] - *a2) >> 6;
  v19 = v18 + cValues;
  if ( v19 > (a2[2] - *a2) >> 6 )
  {
    if ( v19 > 0x3FFFFFFFFFFFFFFLL )
      std::vector<Session>::_Xlength();
    v20 = v19 << 6;
    if ( v19 << 6 )
    {
      if ( v20 < 0x1000 )
      {
        v21 = operator new(v20);
      }
      else
      {
        if ( v20 + 39 < v20 )
          __scrt_throw_std_bad_array_new_length();
        v22 = operator new(v20 + 39);
        if ( !v22 )
          __fastfail(5u);
        v21 = (_QWORD *)(((unsigned __int64)v22 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v21 - 1) = v22;
      }
    }
    else
    {
      v21 = 0;
    }
    std::_Uninitialized_move<std::pair<std::wstring,std::wstring> *,std::allocator<std::pair<std::wstring,std::wstring>>>(
      *a2,
      a2[1],
      (__int64)v21);
    std::vector<std::pair<std::wstring,std::wstring>>::_Change_array(a2, v21, v18, v19);
  }
  v23 = (WCHAR *)operator new[](saturated_mul(cbMaxValueNameLen + 1, 2u));
  v49 = v23;
  v25 = (BYTE *)operator new[](cbMaxValueLen);
  v48 = v25;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v26 = 0;
  if ( cValues )
  {
    while ( 1 )
    {
      cchValueName = cbMaxValueNameLen + 1;
      cbData = cbMaxValueLen;
      v27 = RegEnumValueW(hKey, v26, v23, &cchValueName, 0, &Type, v25, &cbData);
      if ( v27 )
        break;
      if ( Type - 1 <= 1 )
      {
        v50 = 0;
        v51 = 0u;
        std::wstring::_Construct<1,unsigned short const *>((char **)&v50, v25, (unsigned __int64)cbData >> 1);
        v40 = v23;
        v28 = a2[1];
        if ( v28 == a2[2] )
        {
          std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<unsigned short *,std::wstring>(
            a2,
            a2[1],
            &v40,
            &v50);
        }
        else
        {
          *(_OWORD *)v28 = 0;
          *(_QWORD *)(v28 + 16) = 0;
          *(_QWORD *)(v28 + 24) = 0;
          v29 = -1;
          do
            ++v29;
          while ( v23[v29] );
          std::wstring::_Construct<1,unsigned short const *>((char **)v28, v23, v29);
          *(_OWORD *)(v28 + 32) = v50;
          *(_OWORD *)(v28 + 48) = v51;
          *(_QWORD *)&v51 = 0;
          *((_QWORD *)&v51 + 1) = 7;
          LOWORD(v50) = 0;
          a2[1] += 64;
        }
        v30 = (char **)&v50;
LABEL_40:
        std::wstring::~wstring(v30);
      }
      if ( ++v26 >= cValues )
        goto LABEL_42;
    }
    if ( v27 == 259 )
      goto LABEL_42;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v52,
      L"Error reading registry value at index: {0}: {1}",
      0x2Fu);
    v31 = (Private::Format *)StringAlgo::FormatString(v56, &v52);
    v32 = v57;
    v33 = v26;
    do
    {
      *--v32 = v33 % 0xA + 48;
      v33 /= 0xAu;
    }
    while ( v33 );
    v50 = 0;
    v51 = 0u;
    if ( v32 == (_WORD *)v57 )
    {
      *(_QWORD *)&v51 = 0;
      *((_QWORD *)&v51 + 1) = 7;
      LOWORD(v50) = 0;
    }
    else
    {
      std::wstring::_Construct<1,unsigned short const *>((char **)&v50, v32, (v57 - (_BYTE *)v32) >> 1);
    }
    v34 = Private::Format::operator%<std::wstring>(v31, (__int64)&v50);
    v35 = std::to_wstring(v55, v27);
    v36 = Private::Format::operator%<std::wstring>(v34, v35);
    LODWORD(v40) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v40, v36);
    std::wstring::~wstring(v55);
    std::wstring::~wstring((char **)&v50);
    v30 = v56;
    goto LABEL_40;
  }
LABEL_42:
  operator delete(v25, v24);
  operator delete(v23, v37);
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18002d58c  mov     [rsp-8+arg_10], rbx
0x18002d591  push    rbp
0x18002d592  push    rsi
0x18002d593  push    rdi
0x18002d594  push    r12
0x18002d596  push    r13
0x18002d598  push    r14
0x18002d59a  push    r15
0x18002d59c  lea     rbp, [rsp-60h]
0x18002d5a1  sub     rsp, 160h
0x18002d5a8  mov     rax, cs:__security_cookie
0x18002d5af  xor     rax, rsp
0x18002d5b2  mov     [rbp+90h+var_38], rax
0x18002d5b6  mov     rdi, rdx
0x18002d5b9  mov     rbx, rcx
0x18002d5bc  xor     r13d, r13d
0x18002d5bf  cmp     [rcx+10h], r13
0x18002d5c3  jz      loc_18002DB56
0x18002d5c9  mov     [rsp+190h+hKey], r13
0x18002d5ce  cmp     qword ptr [rcx+18h], 7
0x18002d5d3  jbe     short loc_18002D5D8
0x18002d5d5  mov     rbx, [rcx]
0x18002d5d8  lea     rax, [rsp+190h+hKey]
0x18002d5dd  mov     [rsp+190h+phkResult], rax; phkResult
0x18002d5e2  mov     r9d, 20019h; samDesired
0x18002d5e8  xor     r8d, r8d; ulOptions
0x18002d5eb  mov     rdx, rbx; lpSubKey
0x18002d5ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d5f5  call    cs:__imp_RegOpenKeyExW
0x18002d5fb  mov     esi, eax
0x18002d5fd  test    eax, eax
0x18002d5ff  jz      loc_18002D691
0x18002d605  xorps   xmm0, xmm0
0x18002d608  movups  [rbp+90h+var_F8], xmm0
0x18002d60c  mov     qword ptr [rbp+90h+var_E8], r13
0x18002d610  mov     qword ptr [rbp+90h+var_E8+8], r13
0x18002d614  mov     r8d, 20h ; ' '
0x18002d61a  lea     rdx, aErrorOpeningRe; "Error opening registry key:  {0}"
0x18002d621  lea     rcx, [rbp+90h+var_F8]
0x18002d625  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d62a  lea     rdx, [rbp+90h+var_F8]
0x18002d62e  lea     rcx, [rbp+90h+var_B8]
0x18002d632  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002d637  mov     rbx, rax
0x18002d63a  mov     edx, esi
0x18002d63c  lea     rcx, [rbp+90h+var_D8]
0x18002d640  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18002d645  nop
0x18002d646  mov     rdx, rax
0x18002d649  mov     rcx, rbx; this
0x18002d64c  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18002d651  mov     dword ptr [rsp+190h+var_130], r13d
0x18002d656  mov     rdx, rax
0x18002d659  lea     rcx, [rsp+190h+var_130]
0x18002d65e  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002d663  nop
0x18002d664  lea     rcx, [rbp+90h+var_D8]
0x18002d668  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d66d  nop
0x18002d66e  lea     rcx, [rbp+90h+var_B8]
0x18002d672  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d677  nop
0x18002d678  mov     rcx, [rsp+190h+hKey]; hKey
0x18002d67d  test    rcx, rcx
0x18002d680  jz      loc_18002DBB0
0x18002d686  call    cs:__imp_RegCloseKey
0x18002d68c  jmp     loc_18002DBB0
0x18002d691  mov     [rsp+190h+cbMaxValueNameLen], r13d
0x18002d696  mov     [rsp+190h+cbMaxValueLen], r13d
0x18002d69b  mov     [rsp+190h+cValues], r13d
0x18002d6a0  mov     [rsp+190h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002d6a5  mov     [rsp+190h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002d6aa  lea     rax, [rsp+190h+cbMaxValueLen]
0x18002d6af  mov     [rsp+190h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002d6b4  lea     rax, [rsp+190h+cbMaxValueNameLen]
0x18002d6b9  mov     [rsp+190h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002d6be  lea     rax, [rsp+190h+cValues]
0x18002d6c3  mov     [rsp+190h+lpcValues], rax; lpcValues
0x18002d6c8  mov     [rsp+190h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18002d6cd  mov     [rsp+190h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18002d6d2  mov     [rsp+190h+phkResult], r13; lpcSubKeys
0x18002d6d7  xor     r9d, r9d; lpReserved
0x18002d6da  xor     r8d, r8d; lpcchClass
0x18002d6dd  xor     edx, edx; lpClass
0x18002d6df  mov     rcx, [rsp+190h+hKey]; hKey
0x18002d6e4  call    cs:__imp_RegQueryInfoKeyW
0x18002d6ea  mov     esi, eax
0x18002d6ec  xorps   xmm0, xmm0
0x18002d6ef  mov     qword ptr [rbp+90h+var_E8], r13
0x18002d6f3  mov     qword ptr [rbp+90h+var_E8+8], r13
0x18002d6f7  lea     rcx, [rbp+90h+var_F8]
0x18002d6fb  movups  [rbp+90h+var_F8], xmm0
0x18002d6ff  test    eax, eax
0x18002d701  jz      short loc_18002D75E
0x18002d703  mov     r8d, 25h ; '%'
0x18002d709  lea     rdx, aErrorQueryingR; "Error querying registry key info: {0}"
0x18002d710  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d715  lea     rdx, [rbp+90h+var_F8]
0x18002d719  lea     rcx, [rbp+90h+var_B8]
0x18002d71d  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002d722  mov     rbx, rax
0x18002d725  mov     edx, esi
0x18002d727  lea     rcx, [rbp+90h+var_D8]
0x18002d72b  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@J@Z; std::to_wstring(long)
0x18002d730  nop
0x18002d731  mov     rdx, rax
0x18002d734  mov     rcx, rbx; this
0x18002d737  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18002d73c  mov     dword ptr [rsp+190h+var_130], r13d
0x18002d741  mov     rdx, rax
0x18002d744  lea     rcx, [rsp+190h+var_130]
0x18002d749  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002d74e  nop
0x18002d74f  lea     rcx, [rbp+90h+var_D8]
0x18002d753  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d758  nop
0x18002d759  jmp     loc_18002D66E
0x18002d75e  cmp     [rsp+190h+cValues], r13d
0x18002d763  jnz     short loc_18002D7C5
0x18002d765  mov     r8d, 42h ; 'B'
0x18002d76b  lea     rdx, aNoBrowsersFoun; "no browsers found which are attested as"...
0x18002d772  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d777  lea     rdx, [rbp+90h+var_F8]
0x18002d77b  lea     rcx, [rbp+90h+var_B8]
0x18002d77f  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002d784  mov     rbx, rax
0x18002d787  mov     edx, [rsp+190h+cValues]
0x18002d78b  lea     rcx, [rbp+90h+var_D8]
0x18002d78f  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002d794  nop
0x18002d795  mov     rdx, rax
0x18002d798  mov     rcx, rbx; this
0x18002d79b  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18002d7a0  mov     dword ptr [rsp+190h+var_130], 2
0x18002d7a8  mov     rdx, rax
0x18002d7ab  lea     rcx, [rsp+190h+var_130]
0x18002d7b0  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002d7b5  nop
0x18002d7b6  lea     rcx, [rbp+90h+var_D8]
0x18002d7ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d7bf  nop
0x18002d7c0  jmp     loc_18002D66E
0x18002d7c5  mov     r8d, 46h ; 'F'
0x18002d7cb  lea     rdx, aNoOfBrowsersFo; "no. of browsers found which are atteste"...
0x18002d7d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d7d7  lea     rdx, [rbp+90h+var_F8]
0x18002d7db  lea     rcx, [rbp+90h+var_B8]
0x18002d7df  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002d7e4  mov     rbx, rax
0x18002d7e7  mov     edx, [rsp+190h+cValues]
0x18002d7eb  lea     rcx, [rbp+90h+var_D8]
0x18002d7ef  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18002d7f4  nop
0x18002d7f5  mov     rdx, rax
0x18002d7f8  mov     rcx, rbx; this
0x18002d7fb  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18002d800  mov     dword ptr [rsp+190h+var_130], 2
0x18002d808  mov     rdx, rax
0x18002d80b  lea     rcx, [rsp+190h+var_130]
0x18002d810  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002d815  nop
0x18002d816  lea     rcx, [rbp+90h+var_D8]
0x18002d81a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d81f  nop
0x18002d820  lea     rcx, [rbp+90h+var_B8]
0x18002d824  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d829  mov     r14, [rdi+8]
0x18002d82d  sub     r14, [rdi]
0x18002d830  sar     r14, 6
0x18002d834  mov     esi, [rsp+190h+cValues]
0x18002d838  add     rsi, r14
0x18002d83b  mov     rax, [rdi+10h]
0x18002d83f  sub     rax, [rdi]
0x18002d842  sar     rax, 6
0x18002d846  cmp     rsi, rax
0x18002d849  jbe     loc_18002D8D1
0x18002d84f  mov     rax, 3FFFFFFFFFFFFFFh
0x18002d859  cmp     rsi, rax
0x18002d85c  ja      loc_18002DBDD
0x18002d862  mov     rcx, rsi
0x18002d865  shl     rcx, 6; Size
0x18002d869  test    rcx, rcx
0x18002d86c  jnz     short loc_18002D873
0x18002d86e  mov     rbx, r13
0x18002d871  jmp     short loc_18002D8B1
0x18002d873  cmp     rcx, 1000h
0x18002d87a  jb      short loc_18002D8A9
0x18002d87c  lea     rax, [rcx+27h]
0x18002d880  cmp     rax, rcx
0x18002d883  jbe     loc_18002DBD7
0x18002d889  mov     rcx, rax; Size
0x18002d88c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d891  test    rax, rax
0x18002d894  jnz     short loc_18002D89B
0x18002d896  lea     ecx, [rax+5]
0x18002d899  int     29h; Win8: RtlFailFast(ecx)
0x18002d89b  lea     rbx, [rax+27h]
0x18002d89f  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18002d8a3  mov     [rbx-8], rax
0x18002d8a7  jmp     short loc_18002D8B1
0x18002d8a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d8ae  mov     rbx, rax
0x18002d8b1  mov     r8, rbx
0x18002d8b4  mov     rdx, [rdi+8]
0x18002d8b8  mov     rcx, [rdi]
0x18002d8bb  call    ??$_Uninitialized_move@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@YAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@QEAU10@0PEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@0@@Z; std::_Uninitialized_move<std::pair<std::wstring,std::wstring> *,std::allocator<std::pair<std::wstring,std::wstring>>>(std::pair<std::wstring,std::wstring> * const,std::pair<std::wstring,std::wstring> * const,std::pair<std::wstring,std::wstring> *,std::allocator<std::pair<std::wstring,std::wstring>> &)
0x18002d8c0  mov     r9, rsi
0x18002d8c3  mov     r8, r14
0x18002d8c6  mov     rdx, rbx
0x18002d8c9  mov     rcx, rdi
0x18002d8cc  call    ?_Change_array@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXQEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@_K1@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Change_array(std::pair<std::wstring,std::wstring> * const,unsigned __int64,unsigned __int64)
0x18002d8d1  mov     ecx, [rsp+190h+cbMaxValueNameLen]
0x18002d8d5  inc     ecx
0x18002d8d7  mov     eax, 2
0x18002d8dc  mul     rcx
0x18002d8df  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d8e6  cmovb   rax, rcx
0x18002d8ea  mov     rcx, rax; unsigned __int64
0x18002d8ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d8f2  mov     rsi, rax
0x18002d8f5  mov     [rbp+90h+var_100], rax
0x18002d8f9  mov     ecx, [rsp+190h+cbMaxValueLen]; unsigned __int64
0x18002d8fd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d902  mov     r15, rax
0x18002d905  mov     [rbp+90h+var_108], rax
0x18002d909  mov     [rbp+90h+cchValueName], r13d
0x18002d90d  mov     [rsp+190h+cbData], r13d
0x18002d912  mov     [rbp+90h+Type], r13d
0x18002d916  mov     r14d, r13d
0x18002d919  cmp     [rsp+190h+cValues], r13d
0x18002d91e  jbe     loc_18002DB40
0x18002d924  mov     eax, [rsp+190h+cbMaxValueNameLen]
0x18002d928  inc     eax
0x18002d92a  mov     [rbp+90h+cchValueName], eax
0x18002d92d  mov     eax, [rsp+190h+cbMaxValueLen]
0x18002d931  mov     [rsp+190h+cbData], eax
0x18002d935  lea     rax, [rsp+190h+cbData]
0x18002d93a  mov     [rsp+190h+lpcValues], rax; lpcbData
0x18002d93f  mov     [rsp+190h+lpcbMaxClassLen], r15; lpData
0x18002d944  lea     rax, [rbp+90h+Type]
0x18002d948  mov     [rsp+190h+lpcbMaxSubKeyLen], rax; lpType
0x18002d94d  mov     [rsp+190h+phkResult], r13; lpReserved
0x18002d952  lea     r9, [rbp+90h+cchValueName]; lpcchValueName
0x18002d956  mov     r8, rsi; lpValueName
0x18002d959  mov     edx, r14d; dwIndex
0x18002d95c  mov     rcx, [rsp+190h+hKey]; hKey
0x18002d961  call    cs:__imp_RegEnumValueW
0x18002d967  mov     r12d, eax
0x18002d96a  test    eax, eax
0x18002d96c  jnz     loc_18002DA20
0x18002d972  mov     eax, [rbp+90h+Type]
0x18002d975  dec     eax
0x18002d977  cmp     eax, 1
0x18002d97a  ja      loc_18002DB32
0x18002d980  xorps   xmm0, xmm0
0x18002d983  movups  [rbp+90h+var_F8], xmm0
0x18002d987  mov     qword ptr [rbp+90h+var_E8], r13
0x18002d98b  mov     qword ptr [rbp+90h+var_E8+8], r13
0x18002d98f  mov     r8d, [rsp+190h+cbData]
0x18002d994  shr     r8, 1
0x18002d997  mov     rdx, r15
0x18002d99a  lea     rcx, [rbp+90h+var_F8]
0x18002d99e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d9a3  nop
0x18002d9a4  mov     [rsp+190h+var_130], rsi
0x18002d9a9  mov     rbx, [rdi+8]
0x18002d9ad  cmp     rbx, [rdi+10h]
0x18002d9b1  jz      short loc_18002DA02
0x18002d9b3  xorps   xmm0, xmm0
0x18002d9b6  movups  xmmword ptr [rbx], xmm0
0x18002d9b9  mov     [rbx+10h], r13
0x18002d9bd  mov     [rbx+18h], r13
0x18002d9c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d9c5  inc     r8
0x18002d9c8  cmp     [rsi+r8*2], r13w
0x18002d9cd  jnz     short loc_18002D9C5
0x18002d9cf  mov     rdx, rsi
0x18002d9d2  mov     rcx, rbx
0x18002d9d5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d9da  movups  xmm0, [rbp+90h+var_F8]
0x18002d9de  movups  xmmword ptr [rbx+20h], xmm0
0x18002d9e2  movups  xmm1, [rbp+90h+var_E8]
0x18002d9e6  movups  xmmword ptr [rbx+30h], xmm1
0x18002d9ea  mov     qword ptr [rbp+90h+var_E8], r13
0x18002d9ee  mov     qword ptr [rbp+90h+var_E8+8], 7
0x18002d9f6  mov     word ptr [rbp+90h+var_F8], r13w
0x18002d9fb  add     qword ptr [rdi+8], 40h ; '@'
0x18002da00  jmp     short loc_18002DA17
0x18002da02  lea     r9, [rbp+90h+var_F8]
0x18002da06  lea     r8, [rsp+190h+var_130]
0x18002da0b  mov     rdx, rbx
0x18002da0e  mov     rcx, rdi
0x18002da11  call    ??$_Emplace_reallocate@PEAGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@QEAU21@$$QEAPEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<ushort *,std::wstring>(std::pair<std::wstring,std::wstring> * const,ushort * &&,std::wstring &&)
0x18002da16  nop
0x18002da17  lea     rcx, [rbp+90h+var_F8]
0x18002da1b  jmp     loc_18002DB2D
0x18002da20  cmp     r12d, 103h
0x18002da27  jz      loc_18002DB40
0x18002da2d  xorps   xmm0, xmm0
0x18002da30  movups  [rbp+90h+var_D8], xmm0
  ... truncated ...
```
