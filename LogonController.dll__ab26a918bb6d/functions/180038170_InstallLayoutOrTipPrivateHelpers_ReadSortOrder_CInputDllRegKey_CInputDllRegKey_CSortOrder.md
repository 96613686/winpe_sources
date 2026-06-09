# InstallLayoutOrTipPrivateHelpers::ReadSortOrder(CInputDllRegKey &,CInputDllRegKey &,CSortOrder &)

- ea: `0x180038170`
- end: `0x180038a84`
- name: `?ReadSortOrder@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputDllRegKey@@0AEAVCSortOrder@@@Z`
- size: `2324`
- prototype: `void __fastcall(struct CInputDllRegKey *, struct CInputDllRegKey *, struct CSortOrder *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005500`
- `0x180096a78`

## callees

- `0x180004b70`
- `0x1800332d0`
- `0x180038170`
- `0x180039bf8`
- `0x18003bb00`
- `0x18006c000`
- `0x18006caa0`
- `0x18006cad0`
- `0x18006cb30`
- `0x18006f4c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180038652`
- `KERNEL32!LeaveCriticalSection` at `0x180038652`
- `KERNEL32!EnterCriticalSection` at `0x18003860a`
- `KERNEL32!EnterCriticalSection` at `0x18003860a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800381e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038470`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038701`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800381e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038470`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800389f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800389f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003848d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003871e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800387c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800387e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003848d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003871e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800387c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800387e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038840`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003889c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003893b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038840`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003889c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003893b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800388b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800388d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003896b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800388b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800388d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003896b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800384c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180038768`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800384c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180038768`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038419`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180038419`

## string_xrefs

- `0x180038a05`: `CLSID`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::ReadSortOrder(
        struct CInputDllRegKey *a1,
        struct CInputDllRegKey *a2,
        struct CSortOrder *a3)
{
  HKEY v3; // rbx
  HKEY v4; // rsi
  LSTATUS v7; // eax
  HKEY v8; // r13
  int v9; // r8d
  int v10; // eax
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int16 *v14; // r10
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int16 *v20; // r10
  unsigned __int8 v21; // dl
  __int64 v22; // rcx
  DWORD v23; // edi
  LSTATUS v24; // eax
  __int64 v25; // rdx
  HKEY v26; // rdi
  LSTATUS v27; // eax
  HKEY v28; // rbx
  DWORD v29; // edi
  LSTATUS v30; // eax
  __int64 v31; // rdx
  __int16 v32; // ax
  __int64 **v33; // rdx
  __int16 v34; // si
  _DWORD *v35; // rbx
  _QWORD *v36; // rax
  DWORD v37; // r15d
  __int16 v38; // r12
  HKEY v39; // rsi
  LSTATUS v40; // eax
  HKEY v41; // r14
  CSortOrder *v42; // rdi
  unsigned __int16 *v43; // rax
  int v44; // ecx
  int v45; // edx
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v47; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v49; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  HKEY v53; // [rsp+88h] [rbp-78h]
  CSortOrder *v54; // [rsp+90h] [rbp-70h]
  __int16 v55; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v56[2]; // [rsp+A2h] [rbp-5Eh] BYREF
  BYTE v57[8]; // [rsp+A4h] [rbp-5Ch] BYREF
  int v58; // [rsp+ACh] [rbp-54h]
  BYTE v59[78]; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned __int16 v60[303]; // [rsp+102h] [rbp+2h] BYREF
  BYTE Data[8]; // [rsp+360h] [rbp+260h] BYREF
  HKEY v62; // [rsp+368h] [rbp+268h]
  __int16 v63; // [rsp+370h] [rbp+270h]
  __int16 v64; // [rsp+380h] [rbp+280h] BYREF
  _QWORD v65[9]; // [rsp+382h] [rbp+282h] BYREF
  int v66; // [rsp+3CAh] [rbp+2CAh]
  __int16 v67; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v68[9]; // [rsp+3D2h] [rbp+2D2h] BYREF
  int v69; // [rsp+41Ah] [rbp+31Ah]
  WCHAR ValueName[256]; // [rsp+420h] [rbp+320h] BYREF
  WCHAR SubKey[256]; // [rsp+620h] [rbp+520h] BYREF

  v3 = (HKEY)*((_QWORD *)a1 + 1);
  v4 = 0;
  v54 = a3;
  phkResult = 0;
  hKey = 0;
  if ( v3 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
    v3 = hKey;
  v7 = RegOpenKeyExW(v3, &sourceString, 0, 0x20019u, &phkResult);
  if ( !v7
    || (v53 = 0, v8 = 0, v7 == 5)
    && (dwDisposition = 0, !RegCreateKeyExW(v3, &sourceString, 0, 0, 4u, 0x20019u, 0, &phkResult, &dwDisposition)) )
  {
    v8 = phkResult;
    v53 = phkResult;
  }
  if ( hKey )
    RegCloseKey(hKey);
  memset(v65, 0, sizeof(v65));
  v9 = 1;
  v64 = 123;
  v10 = 1;
  v11 = 0;
  v66 = 0;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  do
  {
    if ( v10 >= 36 )
      break;
    v12 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v11);
    v13 = v10++;
    v14 = &v64 + v13;
    if ( (_BYTE)v12 == 45 )
    {
      *v14 = 45;
    }
    else
    {
      *v14 = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_TFCAT_TIP_KEYBOARD.Data1 + v12) >> 4];
      v15 = *((_BYTE *)&_ImageBase + v12 + 710352) & 0xF;
      v16 = v10++;
      *(&v64 + v16) = word_1800B0E90[v15];
    }
    ++v11;
  }
  while ( v11 < 0x14 );
  v67 = 123;
  v17 = 0;
  *(&v64 + v10) = 125;
  *((_WORD *)v65 + v10) = 0;
  do
  {
    if ( v9 >= 36 )
      break;
    v18 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v17);
    v19 = v9++;
    v20 = &v67 + v19;
    if ( (_BYTE)v18 == 45 )
    {
      *v20 = 45;
    }
    else
    {
      v21 = *((_BYTE *)&GUID_NULL.Data1 + v18);
      v22 = v9++;
      *v20 = word_1800B0E90[(unsigned __int64)v21 >> 4];
      *(&v67 + v22) = word_1800B0E90[v21 & 0xF];
    }
    ++v17;
  }
  while ( v17 < 0x14 );
  *(&v67 + v9) = 125;
  *((_WORD *)v68 + v9) = 0;
  memset_0(ValueName, 0, sizeof(ValueName));
  v23 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      cchValueName[0] = 256;
      v24 = RegEnumValueW(v8, v23, ValueName, cchValueName, 0, 0, 0, 0);
      v25 = 255;
      if ( v24 )
        v25 = 0;
      ValueName[v25] = 0;
      if ( v24 )
        break;
      cchValueName[0] = 0;
      ++v23;
      if ( swscanf(ValueName, L"%08d", cchValueName) == 1 )
      {
        LODWORD(v47) = 18;
        cchName = 0;
        if ( RegQueryValueExW(v8, ValueName, 0, &cchName, Data, (LPDWORD)&v47) )
        {
          *(_WORD *)Data = 0;
        }
        else
        {
          v63 = 0;
          v32 = o_wcstoul_0((const wchar_t *)Data, 0, 16);
          v33 = *(__int64 ***)a3;
          v34 = v32;
          while ( v33 )
          {
            if ( *(_WORD *)v33[2] == v32 )
              goto LABEL_45;
            v33 = (__int64 **)*v33;
          }
          v35 = operator new(0x2C0u);
          memset_0((char *)v35 + 2, 0, 0x2BEu);
          *(_WORD *)v35 = v34;
          v35[175] = *((_DWORD *)a3 + 4) + 1;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a3 + 24));
          v36 = operator new(0x18u);
          *v36 = 0;
          v36[1] = 0;
          v36[2] = v35;
          if ( *(_QWORD *)a3 || *((_QWORD *)a3 + 1) )
          {
            *(_QWORD *)(*(_QWORD *)a3 + 8LL) = v36;
            *v36 = *(_QWORD *)a3;
            v36[1] = 0;
          }
          else
          {
            *((_QWORD *)a3 + 1) = 0;
          }
          *(_QWORD *)a3 = v36;
          ++*((_DWORD *)a3 + 4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a3 + 24));
LABEL_45:
          v4 = 0;
        }
      }
    }
  }
  v26 = (HKEY)*((_QWORD *)a2 + 1);
  v49 = 0;
  v47 = 0;
  if ( v26 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &v47) )
    v26 = v47;
  v27 = RegOpenKeyExW(v26, &sourceString, 0, 0x20019u, &v49);
  if ( !v27
    || (v28 = 0, v27 == 5) && (cchName = 0, !RegCreateKeyExW(v26, &sourceString, 0, 0, 4u, 0x20019u, 0, &v49, &cchName)) )
  {
    v28 = v49;
  }
  if ( v47 )
    RegCloseKey(v47);
  v29 = 0;
  if ( v28 )
  {
    while ( 1 )
    {
      cchName = 256;
      v30 = RegEnumKeyExW(v28, v29, ValueName, &cchName, (LPDWORD)v4, (LPWSTR)v4, (LPDWORD)v4, (PFILETIME)v4);
      v31 = 510;
      if ( v30 )
        v31 = (__int64)v4;
      *(WCHAR *)((char *)ValueName + v31) = (unsigned __int16)v4;
      if ( v30 )
        break;
      LODWORD(v49) = ++v29;
      memset_0(SubKey, 0, sizeof(SubKey));
      StringCchPrintfW(SubKey, 0x100u, L"%s\\%s", ValueName, &v64);
      v37 = 0;
      v38 = o_wcstoul_0(ValueName, 0, 16);
      v47 = 0;
      v39 = v28;
      *(_QWORD *)cchValueName = 0;
      if ( v28 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, (PHKEY)cchValueName) )
        v39 = *(HKEY *)cchValueName;
      v40 = RegOpenKeyExW(v39, SubKey, 0, 0x20019u, &v47);
      if ( !v40
        || (v41 = 0, v40 == 5) && (cchName = 0, !RegCreateKeyExW(v39, SubKey, 0, 0, 4u, 0x20019u, 0, &v47, &cchName)) )
      {
        v41 = v47;
      }
      if ( *(_QWORD *)cchValueName )
        RegCloseKey(*(HKEY *)cchValueName);
      v4 = 0;
      if ( v41 )
      {
        v42 = v54;
        while ( 1 )
        {
          cchName = 256;
          if ( RegEnumKeyExW(v41, v37, ValueName, &cchName, (LPDWORD)v4, (LPWSTR)v4, (LPDWORD)v4, (PFILETIME)v4) )
            break;
          ValueName[255] = (unsigned __int16)v4;
          *(_QWORD *)Data = &CInputDllRegKey::`vftable';
          v62 = v4;
          ++v37;
          cchName = 0;
          if ( swscanf(ValueName, L"%08d", &cchName) == 1 )
          {
            if ( (unsigned int)CInputDllRegKey::Open((CInputDllRegKey *)Data, v41, ValueName, 0x20019u) )
            {
              v4 = v62;
            }
            else
            {
              memset_0(v56, 0, 0x2BAu);
              v4 = v62;
              v55 = v38;
              cchValueName[0] = 0;
              LODWORD(v47) = 4;
              RegQueryValueExW(v62, L"KeyboardLayout", 0, cchValueName, v57, (LPDWORD)&v47);
              CInputDllRegKey::QueryValueCch((CInputDllRegKey *)Data, v59, L"CLSID", 39);
              CInputDllRegKey::QueryValueCch((CInputDllRegKey *)Data, (BYTE *)v60, L"Profile", 39);
              v43 = (unsigned __int16 *)v59;
              do
              {
                v44 = v43[398];
                v45 = *v43 - v44;
                if ( v45 )
                  break;
                ++v43;
              }
              while ( v44 );
              v58 = (v45 != 0) + 1;
              CSortOrder::AddAssemblyItem(v42, (struct InputContainer *)&v55);
            }
          }
          *(_QWORD *)Data = &CInputDllRegKey::`vftable';
          if ( v4 )
          {
            RegCloseKey(v4);
            v4 = 0;
            v62 = 0;
          }
        }
        ValueName[0] = (unsigned __int16)v4;
        RegCloseKey(v41);
        v29 = (unsigned int)v49;
        v8 = v53;
      }
    }
    RegCloseKey(v28);
  }
  if ( v8 )
    RegCloseKey(v8);
}

```

## disassembly

```asm
0x180038170  mov     [rsp-8+arg_18], rbx
0x180038175  push    rbp
0x180038176  push    rsi
0x180038177  push    rdi
0x180038178  push    r12
0x18003817a  push    r13
0x18003817c  push    r14
0x18003817e  push    r15
0x180038180  lea     rbp, [rsp-730h]
0x180038188  sub     rsp, 830h
0x18003818f  mov     rax, cs:__security_cookie
0x180038196  xor     rax, rsp
0x180038199  mov     [rbp+760h+var_40], rax
0x1800381a0  mov     rbx, [rcx+8]
0x1800381a4  xor     esi, esi
0x1800381a6  mov     [rbp+760h+var_7D0], r8
0x1800381aa  mov     r15, r8
0x1800381ad  mov     [rsp+860h+var_7F0], rsi
0x1800381b2  mov     r14, rdx
0x1800381b5  mov     [rbp+760h+hKey], rsi
0x1800381b9  cmp     rbx, 0FFFFFFFF80000001h
0x1800381c0  jz      loc_1800388AF
0x1800381c6  lea     rax, [rsp+860h+var_7F0]
0x1800381cb  mov     r9d, 20019h; samDesired
0x1800381d1  xor     r8d, r8d; ulOptions
0x1800381d4  mov     [rsp+860h+phkResult], rax; phkResult
0x1800381d9  lea     rdx, sourceString; lpSubKey
0x1800381e0  mov     rcx, rbx; hKey
0x1800381e3  call    cs:__imp_RegOpenKeyExW
0x1800381e9  test    eax, eax
0x1800381eb  jnz     loc_1800387F3
0x1800381f1  mov     r13, [rsp+860h+var_7F0]
0x1800381f6  mov     [rbp+760h+var_7D8], r13
0x1800381fa  mov     rcx, [rbp+760h+hKey]; hKey
0x1800381fe  test    rcx, rcx
0x180038201  jz      short loc_180038209
0x180038203  call    cs:__imp_RegCloseKey
0x180038209  mov     ebx, 7Bh ; '{'
0x18003820e  mov     [rbp+760h+var_4DE], rsi
0x180038215  mov     r8d, 1
0x18003821b  mov     [rbp+760h+var_4E0], bx
0x180038222  mov     eax, r8d
0x180038225  mov     [rbp+760h+var_4D6], rsi
0x18003822c  mov     [rbp+760h+var_4CE], rsi
0x180038233  lea     r11, __ImageBase
0x18003823a  mov     [rbp+760h+var_4C6], rsi
0x180038241  mov     r9d, esi
0x180038244  mov     [rbp+760h+var_4BE], rsi
0x18003824b  mov     r12d, 2Dh ; '-'
0x180038251  mov     [rbp+760h+var_4B6], rsi
0x180038258  mov     [rbp+760h+var_4AE], rsi
0x18003825f  mov     [rbp+760h+var_4A6], rsi
0x180038266  mov     [rbp+760h+var_49E], rsi
0x18003826d  mov     [rbp+760h+var_496], esi
0x180038273  mov     [rbp+760h+var_48E], rsi
0x18003827a  mov     [rbp+760h+var_486], rsi
0x180038281  mov     [rbp+760h+var_47E], rsi
0x180038288  mov     [rbp+760h+var_476], rsi
0x18003828f  mov     [rbp+760h+var_46E], rsi
0x180038296  mov     [rbp+760h+var_466], rsi
0x18003829d  mov     [rbp+760h+var_45E], rsi
0x1800382a4  mov     [rbp+760h+var_456], rsi
0x1800382ab  mov     [rbp+760h+var_44E], rsi
0x1800382b2  mov     [rbp+760h+var_446], esi
0x1800382b8  cmp     eax, 24h ; '$'
0x1800382bb  jge     short loc_18003832A
0x1800382bd  movsxd  rcx, r9d
0x1800382c0  lea     r10, [rbp+760h+var_4E0]
0x1800382c7  movzx   edx, byte ptr [rcx+r11+0B0EC0h]
0x1800382d0  movsxd  rcx, eax
0x1800382d3  inc     eax
0x1800382d5  lea     r10, [r10+rcx*2]
0x1800382d9  cmp     dl, r12b
0x1800382dc  jz      loc_180038527
0x1800382e2  movzx   ecx, byte ptr [rdx+r11+0AD6D0h]
0x1800382eb  lea     rdx, [rdx+0AD6D0h]
0x1800382f2  shr     rcx, 4
0x1800382f6  movzx   ecx, ds:rva word_1800B0E90[r11+rcx*2]
0x1800382ff  mov     [r10], cx
0x180038303  movzx   ecx, byte ptr [rdx+r11]
0x180038308  and     ecx, 0Fh
0x18003830b  movsxd  rdx, eax
0x18003830e  inc     eax
0x180038310  movzx   ecx, ds:rva word_1800B0E90[r11+rcx*2]
0x180038319  mov     [rbp+rdx*2+760h+var_4E0], cx
0x180038321  inc     r9d
0x180038324  cmp     r9d, 14h
0x180038328  jb      short loc_1800382B8
0x18003832a  movsxd  rcx, eax
0x18003832d  mov     edi, 7Dh ; '}'
0x180038332  mov     [rbp+760h+var_490], bx
0x180038339  mov     r9d, esi
0x18003833c  mov     [rbp+rcx*2+760h+var_4E0], di
0x180038344  movsxd  rcx, eax
0x180038347  mov     word ptr [rbp+rcx*2+760h+var_4DE], si
0x18003834f  nop
0x180038350  cmp     r8d, 24h ; '$'
0x180038354  jge     short loc_1800383BB
0x180038356  movsxd  rax, r9d
0x180038359  lea     r10, [rbp+760h+var_490]
0x180038360  movzx   ecx, byte ptr [rax+r11+0B0EC0h]
0x180038369  movsxd  rax, r8d
0x18003836c  inc     r8d
0x18003836f  lea     r10, [r10+rax*2]
0x180038373  cmp     cl, r12b
0x180038376  jz      loc_180038530
0x18003837c  movzx   edx, byte ptr [rcx+r11+0AD440h]
0x180038385  mov     eax, edx
0x180038387  movsxd  rcx, r8d
0x18003838a  shr     rax, 4
0x18003838e  and     edx, 0Fh
0x180038391  inc     r8d
0x180038394  movzx   eax, ds:rva word_1800B0E90[r11+rax*2]
0x18003839d  mov     [r10], ax
0x1800383a1  movzx   eax, ds:rva word_1800B0E90[r11+rdx*2]
0x1800383aa  mov     [rbp+rcx*2+760h+var_490], ax
0x1800383b2  inc     r9d
0x1800383b5  cmp     r9d, 14h
0x1800383b9  jb      short loc_180038350
0x1800383bb  movsxd  rcx, r8d
0x1800383be  xor     edx, edx; Val
0x1800383c0  movsxd  rax, r8d
0x1800383c3  mov     r8d, 200h; Size
0x1800383c9  mov     [rbp+rax*2+760h+var_490], di
0x1800383d1  mov     word ptr [rbp+rcx*2+760h+var_48E], si
0x1800383d9  lea     rcx, [rbp+760h+ValueName]; void *
0x1800383e0  call    memset_0
0x1800383e5  mov     edi, esi
0x1800383e7  test    r13, r13
0x1800383ea  jz      short loc_180038438
0x1800383ec  mov     [rsp+860h+lpcbData], rsi; lpcbData
0x1800383f1  lea     r9, [rsp+860h+cchValueName]; lpcchValueName
0x1800383f6  mov     [rsp+860h+lpData], rsi; lpData
0x1800383fb  lea     r8, [rbp+760h+ValueName]; lpValueName
0x180038402  mov     [rsp+860h+lpType], rsi; lpType
0x180038407  mov     edx, edi; dwIndex
0x180038409  mov     rcx, r13; hKey
0x18003840c  mov     [rsp+860h+phkResult], rsi; lpReserved
0x180038411  mov     [rsp+860h+cchValueName], 100h
0x180038419  call    cs:__imp_RegEnumValueW
0x18003841f  test    eax, eax
0x180038421  mov     edx, 1FEh
0x180038426  cmovnz  rdx, rsi
0x18003842a  mov     [rbp+rdx+760h+ValueName], si
0x180038432  jz      loc_180038539
0x180038438  mov     rdi, [r14+8]
0x18003843c  mov     [rsp+860h+var_7F8], rsi
0x180038441  mov     [rsp+860h+var_808], rsi
0x180038446  cmp     rdi, 0FFFFFFFF80000001h
0x18003844d  jz      loc_1800388CF
0x180038453  lea     rax, [rsp+860h+var_7F8]
0x180038458  mov     r9d, 20019h; samDesired
0x18003845e  xor     r8d, r8d; ulOptions
0x180038461  mov     [rsp+860h+phkResult], rax; phkResult
0x180038466  lea     rdx, sourceString; lpSubKey
0x18003846d  mov     rcx, rdi; hKey
0x180038470  call    cs:__imp_RegOpenKeyExW
0x180038476  test    eax, eax
0x180038478  jnz     loc_180038853
0x18003847e  mov     rbx, [rsp+860h+var_7F8]
0x180038483  mov     rcx, [rsp+860h+var_808]; hKey
0x180038488  test    rcx, rcx
0x18003848b  jz      short loc_180038493
0x18003848d  call    cs:__imp_RegCloseKey
0x180038493  mov     edi, esi
0x180038495  test    rbx, rbx
0x180038498  jz      short loc_1800384EF
0x18003849a  mov     [rsp+860h+lpcbData], rsi; lpftLastWriteTime
0x18003849f  lea     r9, [rsp+860h+cchName]; lpcchName
0x1800384a4  mov     [rsp+860h+lpData], rsi; lpcchClass
0x1800384a9  lea     r8, [rbp+760h+ValueName]; lpName
0x1800384b0  mov     [rsp+860h+lpType], rsi; lpClass
0x1800384b5  mov     edx, edi; dwIndex
0x1800384b7  mov     rcx, rbx; hKey
0x1800384ba  mov     [rsp+860h+phkResult], rsi; lpReserved
0x1800384bf  mov     [rsp+860h+cchName], 100h
0x1800384c7  call    cs:__imp_RegEnumKeyExW
0x1800384cd  test    eax, eax
0x1800384cf  mov     edx, 1FEh
0x1800384d4  cmovnz  rdx, rsi
0x1800384d8  mov     [rbp+rdx+760h+ValueName], si
0x1800384e0  jz      loc_18003866B
0x1800384e6  mov     rcx, rbx; hKey
0x1800384e9  call    cs:__imp_RegCloseKey
0x1800384ef  test    r13, r13
0x1800384f2  jz      short loc_1800384FD
0x1800384f4  mov     rcx, r13; hKey
0x1800384f7  call    cs:__imp_RegCloseKey
0x1800384fd  mov     rcx, [rbp+760h+var_40]
0x180038504  xor     rcx, rsp; StackCookie
0x180038507  call    __security_check_cookie
0x18003850c  mov     rbx, [rsp+860h+arg_18]
0x180038514  add     rsp, 830h
0x18003851b  pop     r15
0x18003851d  pop     r14
0x18003851f  pop     r13
0x180038521  pop     r12
0x180038523  pop     rdi
0x180038524  pop     rsi
0x180038525  pop     rbp
0x180038526  retn
0x180038527  mov     [r10], r12w
0x18003852b  jmp     loc_180038321
0x180038530  mov     [r10], r12w
0x180038534  jmp     loc_1800383B2
0x180038539  lea     r8, [rsp+860h+cchValueName]
0x18003853e  mov     [rsp+860h+cchValueName], esi
0x180038542  lea     rdx, a08d; "%08d"
0x180038549  inc     edi
0x18003854b  lea     rcx, [rbp+760h+ValueName]; Buffer
0x180038552  call    swscanf
0x180038557  cmp     eax, 1
0x18003855a  jnz     loc_1800383EC
0x180038560  lea     rax, [rsp+860h+var_808]
0x180038565  mov     dword ptr [rsp+860h+var_808], 12h
0x18003856d  mov     [rsp+860h+lpType], rax; lpcbData
0x180038572  lea     r9, [rsp+860h+cchName]; lpType
0x180038577  lea     rax, [rbp+760h+Data]
0x18003857e  mov     [rsp+860h+cchName], esi
0x180038582  xor     r8d, r8d; lpReserved
0x180038585  mov     [rsp+860h+phkResult], rax; lpData
0x18003858a  lea     rdx, [rbp+760h+ValueName]; lpValueName
0x180038591  mov     rcx, r13; hKey
0x180038594  call    cs:__imp_RegQueryValueExW
0x18003859a  test    eax, eax
0x18003859c  jnz     loc_18003865F
0x1800385a2  xor     edx, edx; EndPtr
0x1800385a4  mov     [rbp+760h+var_4F0], si
0x1800385ab  mov     r8d, 10h; Radix
0x1800385b1  lea     rcx, [rbp+760h+Data]; String
0x1800385b8  call    _o_wcstoul_0
0x1800385bd  mov     rdx, [r15]
0x1800385c0  mov     esi, eax
0x1800385c2  test    rdx, rdx
0x1800385c5  jz      short loc_1800385D9
0x1800385c7  mov     rcx, [rdx+10h]
0x1800385cb  cmp     [rcx], si
0x1800385ce  jz      loc_180038658
0x1800385d4  mov     rdx, [rdx]
0x1800385d7  jmp     short loc_1800385C2
0x1800385d9  mov     ecx, 2C0h; Size
0x1800385de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800385e3  xor     edx, edx; Val
0x1800385e5  mov     r8d, 2BEh; Size
0x1800385eb  mov     rbx, rax
0x1800385ee  lea     rcx, [rax+2]; void *
0x1800385f2  call    memset_0
0x1800385f7  mov     [rbx], si
0x1800385fa  mov     ecx, [r15+10h]
0x1800385fe  inc     ecx
0x180038600  mov     [rbx+2BCh], ecx
0x180038606  lea     rcx, [r15+18h]; lpCriticalSection
0x18003860a  call    cs:__imp_EnterCriticalSection
0x180038610  mov     ecx, 18h; Size
0x180038615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003861a  xor     edx, edx
0x18003861c  mov     rcx, rax
0x18003861f  mov     [rax], rdx
0x180038622  mov     [rax+8], rdx
0x180038626  mov     [rax+10h], rbx
0x18003862a  mov     rax, [r15]
0x18003862d  test    rax, rax
0x180038630  jnz     loc_18003894E
0x180038636  cmp     [r15+8], rdx
0x18003863a  jnz     loc_18003894E
0x180038640  mov     [r15+8], rcx
0x180038644  mov     rax, r15
0x180038647  mov     [rax], rcx
0x18003864a  lea     rcx, [r15+18h]; lpCriticalSection
0x18003864e  inc     dword ptr [r15+10h]
0x180038652  call    cs:__imp_LeaveCriticalSection
0x180038658  xor     esi, esi
0x18003865a  jmp     loc_1800383EC
0x18003865f  mov     word ptr [rbp+760h+Data], si
0x180038666  jmp     loc_1800383EC
0x18003866b  inc     edi
0x18003866d  lea     rcx, [rbp+760h+SubKey]; void *
0x180038674  xor     edx, edx; Val
0x180038676  mov     dword ptr [rsp+860h+var_7F8], edi
0x18003867a  mov     r8d, 200h; Size
0x180038680  call    memset_0
0x180038685  lea     rax, [rbp+760h+var_4E0]
0x18003868c  mov     edx, 100h; unsigned __int64
0x180038691  lea     r9, [rbp+760h+ValueName]
0x180038698  mov     [rsp+860h+phkResult], rax
0x18003869d  lea     r8, aSS_0; "%s\\%s"
0x1800386a4  lea     rcx, [rbp+760h+SubKey]; unsigned __int16 *
0x1800386ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800386b0  xor     edx, edx; EndPtr
0x1800386b2  lea     rcx, [rbp+760h+ValueName]; String
0x1800386b9  mov     r8d, 10h; Radix
0x1800386bf  call    _o_wcstoul_0
0x1800386c4  xor     r15d, r15d
0x1800386c7  mov     r12d, eax
0x1800386ca  mov     [rsp+860h+var_808], r15
0x1800386cf  mov     rsi, rbx
0x1800386d2  mov     qword ptr [rsp+860h+cchValueName], r15
0x1800386d7  cmp     rbx, 0FFFFFFFF80000001h
0x1800386de  jz      loc_180038961
0x1800386e4  lea     rax, [rsp+860h+var_808]
  ... truncated ...
```
