# CFolderTypeDescription::_LoadFolderTypeInfo(ushort const *,int)

- ea: `0x1801fdb5c`
- end: `0x1801fe050`
- name: `?_LoadFolderTypeInfo@CFolderTypeDescription@@AEAAJPEBGH@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CFolderTypeDescription *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801fdae0`
- `0x1801fdb5c`

## callees

- `0x180065950`
- `0x180094c70`
- `0x1800a3080`
- `0x1801fdb5c`
- `0x1801fe124`
- `0x180221740`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdf99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdfd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdf99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801fdfd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fdbc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fde1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fde64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fdbc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fde1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801fde64`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801fdef3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801fdf86`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801fdef3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801fdf86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fdc85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fddb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fdfea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fe012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fdc85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fddb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fdfea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fe012`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801fdc65`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801fdc65`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdc43`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdcab`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdce0`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdc43`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdcab`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1801fdce0`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdcc4`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdcf9`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd12`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd2b`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd44`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdcc4`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdcf9`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd12`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd2b`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801fdd44`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fde38`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fe038`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fde38`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1801fe038`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdd60`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdd84`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdda8`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdd60`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdd84`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801fdda8`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x1801fdc1d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x1801fdfc9`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x1801fdc1d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x1801fdfc9`

## pseudocode

```c
__int64 __fastcall CFolderTypeDescription::_LoadFolderTypeInfo(
        CFolderTypeDescription *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // edi
  void *v8; // rcx
  IPropertyBag *v9; // rcx
  int TopViews; // eax
  IPropertyBag *v11; // rcx
  DWORD v12; // edi
  DWORD i; // edx
  unsigned int v14; // eax
  unsigned __int64 v15; // rcx
  _QWORD *v16; // rsi
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // kr00_8
  int v19; // eax
  DWORD v20; // edi
  __int64 v21; // r11
  IPropertyBag *propBag; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR v25; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR v26; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY v28; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cbData[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR value[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Data[40]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SubKey; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v35[526]; // [rsp+132h] [rbp+32h] BYREF
  WCHAR ValueName[264]; // [rsp+340h] [rbp+240h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes",
         0,
         0x20019u,
         &hKey) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    propBag = 0;
    v6 = SHCreatePropertyBagOnRegKey(hKey, a2, 0, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &propBag);
    if ( v6 >= 0 )
    {
      if ( PSPropertyBag_ReadStr(propBag, L"Parent", value, 39) >= 0 )
      {
        if ( !a3 )
        {
          *((GUID *)this + 3) = GUID_NULL;
          GUIDFromStringW(value);
        }
        CFolderTypeDescription::_LoadFolderTypeInfo(this, value, 1);
        v8 = (void *)*((_QWORD *)this + 9);
        *((_DWORD *)this + 16) = 0;
        CoTaskMemFree(v8);
        *((_QWORD *)this + 9) = 0;
      }
      v9 = propBag;
      *((_WORD *)this + 48) = 0;
      PSPropertyBag_ReadStr(v9, L"CanonicalName", (LPWSTR)this + 48, 260);
      PSPropertyBag_ReadDWORD(propBag, L"PerceivedType", (DWORD *)this + 154);
      PSPropertyBag_ReadStr(propBag, L"Theme", (LPWSTR)this + 310, 260);
      PSPropertyBag_ReadDWORD(propBag, L"LayoutType", (DWORD *)this + 285);
      PSPropertyBag_ReadDWORD(propBag, L"TopViewPersistence", (DWORD *)this + 292);
      PSPropertyBag_ReadDWORD(propBag, L"ViewSettingsPersistence", (DWORD *)this + 293);
      PSPropertyBag_ReadDWORD(propBag, L"Mode", (DWORD *)this + 294);
      v25 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"HelpTopic", &v25) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 143));
        *((_QWORD *)this + 143) = v25;
      }
      v26 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"Class", &v26) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 144));
        *((_QWORD *)this + 144) = v26;
      }
      v27 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"MostRelevant", &v27) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 145));
        *((_QWORD *)this + 145) = v27;
      }
      SubKey = 0;
      memset_0(v35, 0, 0x206u);
      StringCchPrintfW(
        &SubKey,
        0x104u,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes\\%s\\Modifiers",
        a2);
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20019u, &phkResult) )
      {
        *((_DWORD *)this + 16) = 0;
        v12 = 0;
        Type = 0;
        for ( i = 0; ; i = v12 )
        {
          cchValueName = 260;
          if ( RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, &Type, 0, 0) )
            break;
          ++*((_DWORD *)this + 16);
          ++v12;
        }
        v14 = *((_DWORD *)this + 16);
        if ( v14
          && ((v15 = v14,
               *(_QWORD *)cbData = 0,
               v16 = (_QWORD *)((char *)this + 72),
               v18 = v14,
               v17 = 536LL * v14,
               *((_QWORD *)this + 9) = 0,
               !is_mul_ok(v18, 0x218u))
            ? (v19 = -2147024362)
            : (v19 = CTCoAllocPolicy::Alloc((void *)v15, 1u, v17, (void **)this + 9)),
              v19 >= 0) )
        {
          v20 = 0;
          cchValueName = 260;
          for ( cbData[0] = 78; v20 < *((_DWORD *)this + 16); cbData[0] = 78 )
          {
            if ( RegEnumValueW(phkResult, v20, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, cbData) )
              break;
            StringCchCopyW((unsigned __int16 *)(536LL * v20 + *v16 + 16LL), 0x104u, ValueName);
            SHCLSIDFromString(Data, (CLSID *)(v21 + *v16));
            ++v20;
            cchValueName = 260;
          }
        }
        else
        {
          *((_DWORD *)this + 16) = 0;
        }
        RegCloseKey(phkResult);
      }
      PSPropertyBag_ReadGUID(propBag, L"DefaultView", (GUID *)this + 5);
      v28 = 0;
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes",
              0,
              0x20019u,
              &v28) )
      {
        *(_QWORD *)cbData = 0;
        if ( (int)SHCreatePropertyBagOnRegKey(hKey, a2, 0, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, cbData) >= 0 )
        {
          PSPropertyBag_ReadGUID(*(IPropertyBag **)cbData, L"DefaultView", (GUID *)this + 5);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)cbData + 16LL))(*(_QWORD *)cbData);
        }
        RegCloseKey(v28);
      }
      TopViews = CFolderTypeDescription::_LoadTopViews(this, a2, a3);
      v11 = propBag;
      v6 = TopViews;
      *((_BYTE *)this + 1192) = TopViews >= 0;
      ((void (__fastcall *)(IPropertyBag *))v11->lpVtbl->Release)(v11);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801fdb5c  mov     [rsp-8+arg_10], rbx
0x1801fdb61  mov     [rsp-8+arg_18], rsi
0x1801fdb66  push    rbp
0x1801fdb67  push    rdi
0x1801fdb68  push    r12
0x1801fdb6a  push    r14
0x1801fdb6c  push    r15
0x1801fdb6e  lea     rbp, [rsp-460h]
0x1801fdb76  sub     rsp, 560h
0x1801fdb7d  mov     rax, cs:__security_cookie
0x1801fdb84  xor     rax, rsp
0x1801fdb87  mov     [rbp+480h+var_30], rax
0x1801fdb8e  mov     r15d, r8d
0x1801fdb91  lea     rax, [rsp+580h+hKey]
0x1801fdb96  mov     r14, rdx
0x1801fdb99  mov     [rsp+580h+phkResult], rax; phkResult
0x1801fdb9e  mov     rbx, rcx
0x1801fdba1  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801fdba8  xor     r12d, r12d
0x1801fdbab  xor     r8d, r8d; ulOptions
0x1801fdbae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801fdbb5  mov     [rsp+580h+hKey], r12
0x1801fdbba  mov     r9d, 20019h; samDesired
0x1801fdbc0  call    cs:__imp_RegOpenKeyExW
0x1801fdbc6  test    eax, eax
0x1801fdbc8  jz      short loc_1801FDBFC
0x1801fdbca  mov     edi, 80004005h
0x1801fdbcf  mov     eax, edi
0x1801fdbd1  mov     rcx, [rbp+480h+var_30]
0x1801fdbd8  xor     rcx, rsp; StackCookie
0x1801fdbdb  call    __security_check_cookie
0x1801fdbe0  lea     r11, [rsp+580h+var_20]
0x1801fdbe8  mov     rbx, [r11+40h]
0x1801fdbec  mov     rsi, [r11+48h]
0x1801fdbf0  mov     rsp, r11
0x1801fdbf3  pop     r15
0x1801fdbf5  pop     r14
0x1801fdbf7  pop     r12
0x1801fdbf9  pop     rdi
0x1801fdbfa  pop     rbp
0x1801fdbfb  retn
0x1801fdbfc  mov     rcx, [rsp+580h+hKey]
0x1801fdc01  lea     rax, [rsp+580h+propBag]
0x1801fdc06  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1801fdc0d  mov     [rsp+580h+phkResult], rax
0x1801fdc12  xor     r8d, r8d
0x1801fdc15  mov     [rsp+580h+propBag], r12
0x1801fdc1a  mov     rdx, r14
0x1801fdc1d  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x1801fdc23  mov     edi, eax
0x1801fdc25  test    eax, eax
0x1801fdc27  js      loc_1801FDE9E
0x1801fdc2d  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdc32  lea     r8, [rbp+480h+value]; value
0x1801fdc36  mov     r9d, 27h ; '''; characterCount
0x1801fdc3c  lea     rdx, aParent_0; "Parent"
0x1801fdc43  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fdc49  test    eax, eax
0x1801fdc4b  js      short loc_1801FDC8F
0x1801fdc4d  test    r15d, r15d
0x1801fdc50  jnz     short loc_1801FDC6B
0x1801fdc52  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801fdc59  lea     rdx, [rbx+30h]
0x1801fdc5d  lea     rcx, [rbp+480h+value]
0x1801fdc61  movdqu  xmmword ptr [rdx], xmm0
0x1801fdc65  call    cs:__imp_GUIDFromStringW
0x1801fdc6b  mov     r8d, 1; int
0x1801fdc71  lea     rdx, [rbp+480h+value]; unsigned __int16 *
0x1801fdc75  mov     rcx, rbx; this
0x1801fdc78  call    ?_LoadFolderTypeInfo@CFolderTypeDescription@@AEAAJPEBGH@Z; CFolderTypeDescription::_LoadFolderTypeInfo(ushort const *,int)
0x1801fdc7d  mov     rcx, [rbx+48h]; pv
0x1801fdc81  mov     [rbx+40h], r12d
0x1801fdc85  call    cs:__imp_CoTaskMemFree
0x1801fdc8b  mov     [rbx+48h], r12
0x1801fdc8f  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdc94  lea     r8, [rbx+60h]; value
0x1801fdc98  mov     esi, 104h
0x1801fdc9d  mov     [r8], r12w
0x1801fdca1  mov     r9d, esi; characterCount
0x1801fdca4  lea     rdx, aCanonicalname; "CanonicalName"
0x1801fdcab  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fdcb1  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdcb6  lea     r8, [rbx+268h]; value
0x1801fdcbd  lea     rdx, aPerceivedtype; "PerceivedType"
0x1801fdcc4  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fdcca  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdccf  lea     r8, [rbx+26Ch]; value
0x1801fdcd6  mov     r9d, esi; characterCount
0x1801fdcd9  lea     rdx, aTheme; "Theme"
0x1801fdce0  call    cs:__imp_PSPropertyBag_ReadStr
0x1801fdce6  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdceb  lea     r8, [rbx+474h]; value
0x1801fdcf2  lea     rdx, aLayouttype; "LayoutType"
0x1801fdcf9  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fdcff  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd04  lea     r8, [rbx+490h]; value
0x1801fdd0b  lea     rdx, aTopviewpersist; "TopViewPersistence"
0x1801fdd12  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fdd18  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd1d  lea     r8, [rbx+494h]; value
0x1801fdd24  lea     rdx, aViewsettingspe; "ViewSettingsPersistence"
0x1801fdd2b  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fdd31  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd36  lea     r8, [rbx+498h]; value
0x1801fdd3d  lea     rdx, aMode_0; "Mode"
0x1801fdd44  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801fdd4a  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd4f  lea     r8, [rsp+580h+var_528]; value
0x1801fdd54  lea     rdx, aHelptopic; "HelpTopic"
0x1801fdd5b  mov     [rsp+580h+var_528], r12
0x1801fdd60  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fdd66  test    eax, eax
0x1801fdd68  jns     loc_1801FE00B
0x1801fdd6e  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd73  lea     r8, [rsp+580h+var_520]; value
0x1801fdd78  lea     rdx, aClass; "Class"
0x1801fdd7f  mov     [rsp+580h+var_520], r12
0x1801fdd84  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fdd8a  test    eax, eax
0x1801fdd8c  jns     loc_1801FDFE3
0x1801fdd92  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fdd97  lea     r8, [rsp+580h+var_518]; value
0x1801fdd9c  lea     rdx, aMostrelevant; "MostRelevant"
0x1801fdda3  mov     [rsp+580h+var_518], r12
0x1801fdda8  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801fddae  test    eax, eax
0x1801fddb0  js      short loc_1801FDDCB
0x1801fddb2  mov     rcx, [rbx+488h]; pv
0x1801fddb9  call    cs:__imp_CoTaskMemFree
0x1801fddbf  mov     rax, [rsp+580h+var_518]
0x1801fddc4  mov     [rbx+488h], rax
0x1801fddcb  xor     edx, edx; Val
0x1801fddcd  mov     [rbp+480h+SubKey], r12w
0x1801fddd2  mov     r8d, 206h; Size
0x1801fddd8  lea     rcx, [rbp+480h+var_44E]; void *
0x1801fdddc  call    memset_0
0x1801fdde1  mov     r9, r14
0x1801fdde4  lea     r8, aSoftwareMicros_94; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801fddeb  mov     rdx, rsi; unsigned __int64
0x1801fddee  lea     rcx, [rbp+480h+SubKey]; unsigned __int16 *
0x1801fddf2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801fddf7  lea     rax, [rsp+580h+var_538]
0x1801fddfc  mov     [rsp+580h+var_538], r12
0x1801fde01  mov     r9d, 20019h; samDesired
0x1801fde07  mov     [rsp+580h+phkResult], rax; phkResult
0x1801fde0c  xor     r8d, r8d; ulOptions
0x1801fde0f  lea     rdx, [rbp+480h+SubKey]; lpSubKey
0x1801fde13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801fde1a  call    cs:__imp_RegOpenKeyExW
0x1801fde20  test    eax, eax
0x1801fde22  jz      loc_1801FDEAE
0x1801fde28  mov     rcx, [rsp+580h+propBag]; propBag
0x1801fde2d  lea     r8, [rbx+50h]; value
0x1801fde31  lea     rdx, aDefaultview; "DefaultView"
0x1801fde38  call    cs:__imp_PSPropertyBag_ReadGUID
0x1801fde3e  lea     rax, [rsp+580h+var_510]
0x1801fde43  mov     [rsp+580h+var_510], r12
0x1801fde48  mov     r9d, 20019h; samDesired
0x1801fde4e  mov     [rsp+580h+phkResult], rax; phkResult
0x1801fde53  xor     r8d, r8d; ulOptions
0x1801fde56  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801fde5d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801fde64  call    cs:__imp_RegOpenKeyExW
0x1801fde6a  test    eax, eax
0x1801fde6c  jz      loc_1801FDFAA
0x1801fde72  mov     r8d, r15d; int
0x1801fde75  mov     rdx, r14; unsigned __int16 *
0x1801fde78  mov     rcx, rbx; this
0x1801fde7b  call    ?_LoadTopViews@CFolderTypeDescription@@AEAAJPEBGH@Z; CFolderTypeDescription::_LoadTopViews(ushort const *,int)
0x1801fde80  mov     rcx, [rsp+580h+propBag]
0x1801fde85  mov     edi, eax
0x1801fde87  shr     eax, 1Fh
0x1801fde8a  xor     al, 1
0x1801fde8c  mov     [rbx+4A8h], al
0x1801fde92  mov     rax, [rcx]
0x1801fde95  mov     rax, [rax+10h]
0x1801fde99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fde9e  mov     rcx, [rsp+580h+hKey]; hKey
0x1801fdea3  call    cs:__imp_RegCloseKey
0x1801fdea9  jmp     loc_1801FDBCF
0x1801fdeae  mov     [rbx+40h], r12d
0x1801fdeb2  mov     edi, r12d
0x1801fdeb5  mov     [rsp+580h+Type], r12d
0x1801fdeba  xor     edx, edx
0x1801fdebc  jmp     short loc_1801FDEC5
0x1801fdebe  inc     dword ptr [rbx+40h]
0x1801fdec1  inc     edi
0x1801fdec3  mov     edx, edi; dwIndex
0x1801fdec5  mov     rcx, [rsp+580h+var_538]; hKey
0x1801fdeca  lea     rax, [rsp+580h+Type]
0x1801fdecf  mov     [rsp+580h+lpcbData], r12; lpcbData
0x1801fded4  lea     r9, [rsp+580h+cchValueName]; lpcchValueName
0x1801fded9  mov     [rsp+580h+lpData], r12; lpData
0x1801fdede  lea     r8, [rbp+480h+ValueName]; lpValueName
0x1801fdee5  mov     [rsp+580h+lpType], rax; lpType
0x1801fdeea  mov     [rsp+580h+phkResult], r12; lpReserved
0x1801fdeef  mov     [rsp+580h+cchValueName], esi
0x1801fdef3  call    cs:__imp_RegEnumValueW
0x1801fdef9  test    eax, eax
0x1801fdefb  jz      short loc_1801FDEBE
0x1801fdefd  mov     eax, [rbx+40h]
0x1801fdf00  test    eax, eax
0x1801fdf02  jz      loc_1801FDFA4
0x1801fdf08  mov     ecx, eax; void *
0x1801fdf0a  mov     qword ptr [rbp+480h+cbData], r12
0x1801fdf0e  mov     eax, 218h
0x1801fdf13  lea     rsi, [rbx+48h]
0x1801fdf17  mul     rcx
0x1801fdf1a  mov     [rsi], r12
0x1801fdf1d  test    rdx, rdx
0x1801fdf20  jnz     loc_1801FE001
0x1801fdf26  mov     r9, rsi; void **
0x1801fdf29  mov     r8, rax; unsigned __int64
0x1801fdf2c  mov     edx, 1; unsigned int
0x1801fdf31  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801fdf36  test    eax, eax
0x1801fdf38  js      short loc_1801FDFA4
0x1801fdf3a  mov     edi, r12d
0x1801fdf3d  mov     [rsp+580h+cchValueName], 104h
0x1801fdf45  mov     [rbp+480h+cbData], 4Eh ; 'N'
0x1801fdf4c  cmp     [rbx+40h], r12d
0x1801fdf50  jbe     short loc_1801FDF94
0x1801fdf52  mov     rcx, [rsp+580h+var_538]; hKey
0x1801fdf57  lea     rax, [rbp+480h+cbData]
0x1801fdf5b  mov     [rsp+580h+lpcbData], rax; lpcbData
0x1801fdf60  lea     r9, [rsp+580h+cchValueName]; lpcchValueName
0x1801fdf65  lea     rax, [rbp+480h+Data]
0x1801fdf69  mov     edx, edi; dwIndex
0x1801fdf6b  mov     [rsp+580h+lpData], rax; lpData
0x1801fdf70  lea     r8, [rbp+480h+ValueName]; lpValueName
0x1801fdf77  lea     rax, [rsp+580h+Type]
0x1801fdf7c  mov     [rsp+580h+lpType], rax; lpType
0x1801fdf81  mov     [rsp+580h+phkResult], r12; lpReserved
0x1801fdf86  call    cs:__imp_RegEnumValueW
0x1801fdf8c  test    eax, eax
0x1801fdf8e  jz      loc_18065013A
0x1801fdf94  mov     rcx, [rsp+580h+var_538]; hKey
0x1801fdf99  call    cs:__imp_RegCloseKey
0x1801fdf9f  jmp     loc_1801FDE28
0x1801fdfa4  mov     [rbx+40h], r12d
0x1801fdfa8  jmp     short loc_1801FDF94
0x1801fdfaa  mov     rcx, [rsp+580h+hKey]
0x1801fdfaf  lea     rax, [rbp+480h+cbData]
0x1801fdfb3  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1801fdfba  mov     [rsp+580h+phkResult], rax
0x1801fdfbf  xor     r8d, r8d
0x1801fdfc2  mov     qword ptr [rbp+480h+cbData], r12
0x1801fdfc6  mov     rdx, r14
0x1801fdfc9  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x1801fdfcf  test    eax, eax
0x1801fdfd1  jns     short loc_1801FE029
0x1801fdfd3  mov     rcx, [rsp+580h+var_510]; hKey
0x1801fdfd8  call    cs:__imp_RegCloseKey
0x1801fdfde  jmp     loc_1801FDE72
0x1801fdfe3  mov     rcx, [rbx+480h]; pv
0x1801fdfea  call    cs:__imp_CoTaskMemFree
0x1801fdff0  mov     rax, [rsp+580h+var_520]
0x1801fdff5  mov     [rbx+480h], rax
0x1801fdffc  jmp     loc_1801FDD92
0x1801fe001  mov     eax, 80070216h
0x1801fe006  jmp     loc_1801FDF36
0x1801fe00b  mov     rcx, [rbx+478h]; pv
0x1801fe012  call    cs:__imp_CoTaskMemFree
0x1801fe018  mov     rax, [rsp+580h+var_528]
0x1801fe01d  mov     [rbx+478h], rax
0x1801fe024  jmp     loc_1801FDD6E
0x1801fe029  mov     rcx, qword ptr [rbp+480h+cbData]; propBag
0x1801fe02d  lea     r8, [rbx+50h]; value
0x1801fe031  lea     rdx, aDefaultview; "DefaultView"
0x1801fe038  call    cs:__imp_PSPropertyBag_ReadGUID
0x1801fe03e  mov     rcx, qword ptr [rbp+480h+cbData]
0x1801fe042  mov     rax, [rcx]
0x1801fe045  mov     rax, [rax+10h]
0x1801fe049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fe04e  jmp     short loc_1801FDFD3
0x18065013a  mov     rcx, [rsi]
0x18065013d  lea     r8, [rbp+480h+ValueName]; unsigned __int16 *
0x180650144  mov     eax, edi
0x180650146  add     rcx, 10h
0x18065014a  imul    r11, rax, 218h
0x180650151  mov     edx, 104h; unsigned __int64
0x180650156  add     rcx, r11; unsigned __int16 *
0x180650159  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18065015e  mov     rdx, [rsi]
0x180650161  lea     rcx, [rbp+480h+Data]; psz
0x180650165  add     rdx, r11; pclsid
0x180650168  call    SHCLSIDFromString
0x18065016d  inc     edi
0x18065016f  mov     [rsp+580h+cchValueName], 104h
0x180650177  mov     [rbp+480h+cbData], 4Eh ; 'N'
0x18065017e  cmp     edi, [rbx+40h]
0x180650181  jb      loc_1801FDF52
0x180650187  jmp     loc_1801FDF94
```
