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
        _QWORD *a2)
{
  const WCHAR *v3; // rbx
  unsigned int v4; // esi
  Private::Format *v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // esi
  Private::Format *v8; // rbx
  __int64 v9; // rax
  Private::Format *v10; // rbx
  __int64 v11; // rax
  Private::Format *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r14
  unsigned __int64 v15; // rsi
  size_t v16; // rcx
  _QWORD *v17; // rbx
  void *v18; // rax
  WCHAR *v19; // rsi
  unsigned __int64 v20; // rdx
  BYTE *v21; // r15
  DWORD v22; // r14d
  unsigned int v23; // r12d
  __int64 v24; // rbx
  __int64 v25; // r8
  __int128 *v26; // rcx
  Private::Format *v27; // rbx
  _BYTE *v28; // r9
  DWORD v29; // r8d
  Private::Format *v30; // rbx
  __int64 v31; // rax
  unsigned __int64 v32; // rdx
  Private::Format *v33; // rax
  __int64 v34; // rax
  WCHAR *v35; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  BYTE *v43; // [rsp+88h] [rbp-78h]
  WCHAR *v44; // [rsp+90h] [rbp-70h]
  __int128 v45; // [rsp+98h] [rbp-68h] BYREF
  __int128 v46; // [rsp+A8h] [rbp-58h]
  __int128 v47; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  _BYTE v50[40]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v51[82]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v52[6]; // [rsp+152h] [rbp+52h] BYREF

  v3 = lpSubKey;
  if ( !*((_QWORD *)lpSubKey + 2) )
  {
    v47 = 0;
    v48 = 0;
    v49 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"Key is empty to read attested apps from:  {0}", 45);
    v33 = (Private::Format *)StringAlgo::FormatString(v51, &v47);
    v34 = Private::Format::operator%<std::wstring>(v33);
    LODWORD(v35) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v34);
    std::wstring::~wstring(v51);
    return;
  }
  hKey = 0;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    v3 = *(const WCHAR **)lpSubKey;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v45 = 0;
    v46 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v45, L"Error opening registry key:  {0}", 32);
    v5 = (Private::Format *)StringAlgo::FormatString(v50, &v45);
    std::to_wstring(&v47, v4);
    v6 = Private::Format::operator%<std::wstring>(v5);
    LODWORD(v35) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v6);
    std::wstring::~wstring(&v47);
LABEL_6:
    std::wstring::~wstring(v50);
    goto LABEL_7;
  }
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v46 = 0u;
  v45 = 0;
  if ( v7 )
  {
    std::wstring::_Construct<1,unsigned short const *>(&v45, L"Error querying registry key info: {0}", 37);
    v8 = (Private::Format *)StringAlgo::FormatString(v50, &v45);
    std::to_wstring(&v47, v7);
    v9 = Private::Format::operator%<std::wstring>(v8);
    LODWORD(v35) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v9);
    std::wstring::~wstring(&v47);
    goto LABEL_6;
  }
  if ( !cValues )
  {
    std::wstring::_Construct<1,unsigned short const *>(
      &v45,
      L"no browsers found which are attested as safe on this machine : {0}",
      66);
    v10 = (Private::Format *)StringAlgo::FormatString(v50, &v45);
    std::to_wstring(&v47, cValues);
    v11 = Private::Format::operator%<std::wstring>(v10);
    LODWORD(v35) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v11);
    std::wstring::~wstring(&v47);
    goto LABEL_6;
  }
  std::wstring::_Construct<1,unsigned short const *>(
    &v45,
    L"no. of browsers found which are attested as safe on this machine : {0}",
    70);
  v12 = (Private::Format *)StringAlgo::FormatString(v50, &v45);
  std::to_wstring(&v47, cValues);
  v13 = Private::Format::operator%<std::wstring>(v12);
  LODWORD(v35) = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v13);
  std::wstring::~wstring(&v47);
  std::wstring::~wstring(v50);
  v14 = (__int64)(a2[1] - *a2) >> 6;
  v15 = v14 + cValues;
  if ( v15 > (__int64)(a2[2] - *a2) >> 6 )
  {
    if ( v15 > 0x3FFFFFFFFFFFFFFLL )
      std::vector<Session>::_Xlength();
    v16 = v15 << 6;
    if ( v15 << 6 )
    {
      if ( v16 < 0x1000 )
      {
        v17 = operator new(v16);
      }
      else
      {
        if ( v16 + 39 < v16 )
          __scrt_throw_std_bad_array_new_length();
        v18 = operator new(v16 + 39);
        if ( !v18 )
          __fastfail(5u);
        v17 = (_QWORD *)(((unsigned __int64)v18 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v17 - 1) = v18;
      }
    }
    else
    {
      v17 = 0;
    }
    std::_Uninitialized_move<std::pair<std::wstring,std::wstring> *,std::allocator<std::pair<std::wstring,std::wstring>>>(
      *a2,
      a2[1],
      v17);
    std::vector<std::pair<std::wstring,std::wstring>>::_Change_array(a2, v17, v14, v15);
  }
  v19 = (WCHAR *)operator new[](saturated_mul(cbMaxValueNameLen + 1, 2u));
  v44 = v19;
  v21 = (BYTE *)operator new[](cbMaxValueLen);
  v43 = v21;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  v22 = 0;
  if ( cValues )
  {
    while ( 1 )
    {
      cchValueName = cbMaxValueNameLen + 1;
      cbData = cbMaxValueLen;
      v23 = RegEnumValueW(hKey, v22, v19, &cchValueName, 0, &Type, v21, &cbData);
      if ( v23 )
        break;
      if ( Type - 1 <= 1 )
      {
        v45 = 0;
        v46 = 0u;
        std::wstring::_Construct<1,unsigned short const *>(&v45, v21, (unsigned __int64)cbData >> 1);
        v35 = v19;
        v24 = a2[1];
        if ( v24 == a2[2] )
        {
          std::vector<std::pair<std::wstring,std::wstring>>::_Emplace_reallocate<unsigned short *,std::wstring>(
            a2,
            a2[1],
            &v35,
            &v45);
        }
        else
        {
          *(_OWORD *)v24 = 0;
          *(_QWORD *)(v24 + 16) = 0;
          *(_QWORD *)(v24 + 24) = 0;
          v25 = -1;
          do
            ++v25;
          while ( v19[v25] );
          std::wstring::_Construct<1,unsigned short const *>(v24, v19, v25);
          *(_OWORD *)(v24 + 32) = v45;
          *(_OWORD *)(v24 + 48) = v46;
          *(_QWORD *)&v46 = 0;
          *((_QWORD *)&v46 + 1) = 7;
          LOWORD(v45) = 0;
          a2[1] += 64LL;
        }
        v26 = &v45;
LABEL_40:
        std::wstring::~wstring(v26);
      }
      if ( ++v22 >= cValues )
        goto LABEL_42;
    }
    if ( v23 == 259 )
      goto LABEL_42;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"Error reading registry value at index: {0}: {1}", 47);
    v27 = (Private::Format *)StringAlgo::FormatString(v51, &v47);
    v28 = v52;
    v29 = v22;
    do
    {
      v28 -= 2;
      *(_WORD *)v28 = v29 % 0xA + 48;
      v29 /= 0xAu;
    }
    while ( v29 );
    v45 = 0;
    v46 = 0u;
    if ( v28 == v52 )
    {
      *(_QWORD *)&v46 = 0;
      *((_QWORD *)&v46 + 1) = 7;
      LOWORD(v45) = 0;
    }
    else
    {
      std::wstring::_Construct<1,unsigned short const *>(&v45, v28, (v52 - v28) >> 1);
    }
    v30 = (Private::Format *)Private::Format::operator%<std::wstring>(v27);
    std::to_wstring(v50, v23);
    v31 = Private::Format::operator%<std::wstring>(v30);
    LODWORD(v35) = 0;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v35, v31);
    std::wstring::~wstring(v50);
    std::wstring::~wstring(&v45);
    v26 = (__int128 *)v51;
    goto LABEL_40;
  }
LABEL_42:
  operator delete(v21, v20);
  operator delete(v19, v32);
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
