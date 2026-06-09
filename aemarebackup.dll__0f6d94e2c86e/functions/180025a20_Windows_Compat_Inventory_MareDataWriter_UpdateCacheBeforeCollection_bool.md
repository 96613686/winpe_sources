# Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection(bool)

- ea: `0x180025a20`
- end: `0x180026206`
- name: `?UpdateCacheBeforeCollection@MareDataWriter@Inventory@Compat@Windows@@AEAAJ_N@Z`
- size: `2022`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::MareDataWriter *this, char)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x18000529c`
- `0x18000702c`
- `0x18000fb60`
- `0x18000fce8`
- `0x180011fcc`
- `0x18001209c`
- `0x180012510`
- `0x1800134b8`
- `0x180013ad4`
- `0x180013ec4`
- `0x180014ed4`
- `0x180015b48`
- `0x18001b554`
- `0x18001bb7c`
- `0x18001d4d0`
- `0x18001d840`
- `0x18001de34`
- `0x1800241fc`
- `0x180025a20`
- `0x18002756c`
- `0x1800276cc`
- `0x18002b0b8`
- `0x18002d900`
- `0x1800307fc`
- `0x180030ad4`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025b75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025b75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180025b6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180025b6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025b53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ca6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025c18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025c9c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025c18`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025c9c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025cdf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025cdf`

## string_xrefs

- `0x180025e6b`: `%ls has %d items in cache`
- `0x180025f6f`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x1800261a4`: `TelCacheProvider::GetNextItem failed [%#x]`
- `0x180025aa0`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection`
- `0x180025aca`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection`
- `0x180025b8d`: `Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection`
- `0x180025abd`: `GetUserData did not find any user SIDs [%#x]`
- `0x180025bd9`: `\AppData\Local\Backup\lastCompatBackupTime.txt`
- `0x180025cc8`: `%ls backup JSON doesn't exist`
- `0x180025d1a`: `%ls has been read by ADEPT`
- `0x180025d29`: `%ls has NOT been read by ADEPT`
- `0x180026160`: `TelCacheProvider::GetMetadata failed [%#x]`
- `0x1800260e1`: `TelCacheProvider::SetMetadata failed [%#x]`
- `0x180025dba`: `TelCacheProvider::GetItemCount failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection(
        Windows::Compat::Inventory::MareDataWriter *this,
        char a2)
{
  int UserData; // eax
  signed int LastError; // ebx
  HANDLE *v6; // rbx
  char v7; // cl
  __int64 v8; // rax
  _QWORD *v9; // r12
  _QWORD *i; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // r9
  __int64 v14; // rcx
  const WCHAR *v15; // rcx
  const wchar_t *v16; // rax
  const WCHAR *v17; // rcx
  wchar_t **v18; // rax
  const char *v19; // r9
  __int64 v20; // r8
  LPCWSTR *v21; // rax
  TelCacheProvider *v22; // r13
  int ItemCount; // eax
  const wchar_t *v24; // rax
  unsigned __int16 *v26; // r12
  wchar_t *j; // rbx
  __int64 v28; // r13
  __int64 k; // r15
  const wchar_t *v30; // rdx
  size_t v31; // r8
  const wchar_t *v32; // rcx
  __int64 v33; // r12
  __int64 m; // r15
  wchar_t *v35; // rbx
  wchar_t *v36; // r14
  const wchar_t *v37; // rdx
  const WCHAR *v38; // r8
  const wchar_t *v39; // rcx
  unsigned __int16 *v40; // rax
  unsigned __int16 *v41; // r14
  unsigned __int16 *v42; // rbx
  const unsigned __int16 *v43; // rdx
  int Metadata; // eax
  const struct std::nothrow_t *v45; // rdx
  const unsigned __int16 *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  const unsigned __int16 *v48; // rdx
  int v49; // eax
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 v53; // [rsp+20h] [rbp-E0h]
  __int64 v54; // [rsp+20h] [rbp-E0h]
  unsigned int v55; // [rsp+40h] [rbp-C0h] BYREF
  TelCacheProvider *v56; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v57; // [rsp+50h] [rbp-B0h]
  wchar_t *v58[2]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v59; // [rsp+68h] [rbp-98h]
  __int128 v60; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h]
  wchar_t **v62; // [rsp+88h] [rbp-78h]
  LPCWSTR v63[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v64; // [rsp+B0h] [rbp-50h]
  wchar_t *S2[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v67; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpFileName[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v69; // [rsp+F0h] [rbp-10h]
  __int128 v70; // [rsp+F8h] [rbp-8h] BYREF
  FILETIME FileTime2[2]; // [rsp+108h] [rbp+8h] BYREF
  int v72; // [rsp+118h] [rbp+18h]
  __int128 FileInformation; // [rsp+120h] [rbp+20h] BYREF
  FILETIME FileTime1[2]; // [rsp+130h] [rbp+30h] BYREF
  int v75; // [rsp+140h] [rbp+40h]
  char v76[8]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v77[72]; // [rsp+158h] [rbp+58h] BYREF
  wchar_t *S1; // [rsp+1A0h] [rbp+A0h]
  wchar_t *v79; // [rsp+1A8h] [rbp+A8h]

  *(_OWORD *)v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  Windows::Compat::Inventory::MareApplication::MareApplication((Windows::Compat::Inventory::MareApplication *)v76);
  UserData = Windows::Compat::Inventory::MareDataWriter::GetUserData((void **)&v60, (_QWORD *)this + 41);
  LastError = UserData;
  if ( UserData < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
      891,
      "GetUserData failed [%#x]",
      UserData);
    goto LABEL_118;
  }
  if ( UserData == 1 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
      896,
      "GetUserData did not find any user SIDs [%#x]",
      1);
    goto LABEL_118;
  }
  if ( a2 )
  {
    if ( *((_QWORD *)this + 29) )
    {
      v6 = (HANDLE *)((char *)this + 248);
      Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 248));
      if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 29) + 120LL))(*((_QWORD *)this + 29)) >= 0 )
      {
        *((_WORD *)this + 76) = 0;
        *((_WORD *)this + 120) = 0;
      }
      if ( *((_BYTE *)this + 284) )
      {
        v7 = 0;
        v8 = *((_QWORD *)this + 34);
        if ( *(_DWORD *)(v8 + 4) == 1 )
        {
          *((_BYTE *)this + 284) = 0;
          v7 = 1;
        }
        --*(_DWORD *)(v8 + 4);
        if ( !v7 )
          goto LABEL_17;
        goto LABEL_16;
      }
      if ( !WaitForSingleObject(*v6, 0xFFFFFFFF) )
      {
        --**((_DWORD **)this + 34);
        --*((_DWORD *)this + 70);
        ReleaseMutex(*v6);
LABEL_16:
        SetEvent(*((HANDLE *)this + 33));
      }
    }
LABEL_17:
    LastError = 0;
    goto LABEL_118;
  }
  v9 = (_QWORD *)*((_QWORD *)&v60 + 1);
  for ( i = (_QWORD *)v60; i != v9; i += 12 )
  {
    std::wstring::wstring(S2, i + 8);
    v13 = i + 4;
    v14 = i[6];
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v14) < 0x2E )
      std::_Xlen_string();
    if ( i[7] > 7u )
      v13 = (_QWORD *)*v13;
    std::wstring::wstring(lpFileName, v11, v12, v13, v14, L"\\AppData\\Local\\Backup\\lastCompatBackupTime.txt", 46);
    FileInformation = 0;
    *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
    v75 = 0;
    v15 = (const WCHAR *)lpFileName;
    if ( v69 > 7 )
      v15 = lpFileName[0];
    if ( GetFileAttributesExW(v15, GetFileExInfoStandard, &FileInformation) )
    {
      std::wstring::wstring(v63, i);
      v70 = 0;
      *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
      v72 = 0;
      v17 = (const WCHAR *)v63;
      if ( v64 > 7 )
        v17 = v63[0];
      if ( GetFileAttributesExW(v17, GetFileExInfoStandard, &v70) )
      {
        if ( CompareFileTime(
               (const FILETIME *)&FileTime1[0].dwHighDateTime,
               (const FILETIME *)&FileTime2[0].dwHighDateTime) < 0 )
        {
          v19 = "%ls has NOT been read by ADEPT";
          v20 = 959;
        }
        else
        {
          if ( v58[1] == v59 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v58, v58[1], S2);
          }
          else
          {
            std::wstring::wstring(v58[1], S2);
            v58[1] += 16;
          }
          v19 = "%ls has been read by ADEPT";
          v20 = 955;
        }
        v21 = v63;
        if ( v64 > 7 )
          v21 = (LPCWSTR *)v63[0];
        AslLogCallPrintf(3, "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection", v20, v19, v21);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError != 2 )
        {
          v24 = (const wchar_t *)v63;
          if ( v64 > 7 )
            v24 = v63[0];
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
            946,
            "GetFileAttributesExW(%ls) failed [%d]",
            v24,
            LastError);
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          std::wstring::~wstring(v63);
          goto LABEL_54;
        }
        v18 = S2;
        if ( v67 > 7 )
          v18 = (wchar_t **)S2[0];
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
          941,
          "%ls backup JSON doesn't exist",
          v18);
      }
      std::wstring::~wstring(v63);
    }
    else
    {
      LastError = GetLastError();
      v16 = (const wchar_t *)lpFileName;
      if ( (unsigned int)(LastError - 2) > 1 )
      {
        if ( v69 > 7 )
          v16 = lpFileName[0];
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
          927,
          "GetFileAttributesExW(%ls) failed [%d]",
          v16,
          LastError);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_54:
        std::wstring::~wstring(lpFileName);
        std::wstring::~wstring(S2);
        goto LABEL_118;
      }
      if ( v69 > 7 )
        v16 = lpFileName[0];
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
        922,
        "%ls not uploaded up to CDS %d",
        v16,
        LastError);
    }
    std::wstring::~wstring(lpFileName);
    std::wstring::~wstring(S2);
  }
  Windows::Compat::Inventory::MareApplication::SetCacheUpdateMode(0);
  v55 = 0;
  v22 = (Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144);
  v56 = (Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144);
  ItemCount = TelCacheProvider::GetItemCount((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144), &v55);
  LastError = ItemCount;
  if ( ItemCount >= 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
      975,
      "%ls has %d items in cache",
      L"MareBackupApps",
      v55);
    for ( LastError = TelCacheProvider::GetFirstItem(
                        (Windows::Compat::Inventory::MareDataWriter *)((char *)this + 144),
                        (struct IAmiInventoryItem *)v77);
          LastError != -2147024637;
          LastError = TelCacheProvider::GetNextItem(v22, (struct IAmiInventoryItem *)v77) )
    {
      if ( !v55-- )
        break;
      if ( LastError < 0 )
      {
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
          988,
          "TelCacheProvider::GetNextItem failed [%#x]",
          LastError);
      }
      else
      {
        v26 = (unsigned __int16 *)std::vector<std::wstring>::vector<std::wstring>(v63, v58);
        v57 = v26;
        for ( j = S1; j != v79; j += 20 )
        {
          v28 = *((_QWORD *)v26 + 1);
          for ( k = *(_QWORD *)v26; k != v28; k += 32 )
          {
            std::wstring::wstring(S2, k);
            v30 = (const wchar_t *)S2;
            if ( v67 > 7 )
              v30 = S2[0];
            v31 = *((_QWORD *)j + 2);
            if ( *((_QWORD *)j + 3) <= 7u )
              v32 = j;
            else
              v32 = *(const wchar_t **)j;
            if ( v31 == v66 && (!v31 || !wmemcmp(v32, v30, v31)) )
              *((_DWORD *)j + 8) = 2;
            std::wstring::~wstring(S2);
          }
        }
        std::vector<std::wstring>::_Tidy(v26);
        v22 = v56;
        TelCacheProvider::AddItem(v56, (struct IAmiInventoryItem *)v77);
      }
    }
    if ( (_WORD)LastError == 259 )
    {
      v33 = *((_QWORD *)&v60 + 1);
      for ( m = v60; m != v33; m += 96 )
      {
        std::wstring::wstring(v63, m + 64);
        v35 = v58[0];
        v36 = v58[1];
        while ( 1 )
        {
          if ( v35 == v36 )
          {
            LODWORD(v56) = 256;
            v40 = (unsigned __int16 *)operator new[](0x200u);
            v41 = v40;
            v42 = v40;
            v57 = v40;
            v43 = (const unsigned __int16 *)v63;
            if ( v64 > 7 )
              v43 = v63[0];
            Metadata = TelCacheProvider::GetMetadata(v22, v43, v40, (unsigned int *)&v56);
            if ( (unsigned __int16)Metadata == 234 )
            {
              v42 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v56, 2u));
              v57 = v42;
              operator delete(v41, v45);
              v46 = (const unsigned __int16 *)v63;
              if ( v64 > 7 )
                v46 = v63[0];
              TelCacheProvider::GetMetadata(v22, v46, v42, (unsigned int *)&v56);
              v41 = v42;
            }
            else
            {
              v47 = 0;
              if ( Metadata < 0 )
              {
                if ( (unsigned __int16)Metadata != 2 )
                  AslLogCallPrintf(
                    1,
                    "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
                    1049,
                    "TelCacheProvider::GetMetadata failed [%#x]",
                    Metadata);
              }
              else if ( *v41 )
              {
                v62 = S2;
                *(_OWORD *)S2 = 0;
                v66 = 0;
                v67 = 0;
                v50 = -1;
                do
                  ++v50;
                while ( v41[v50] );
                std::wstring::_Construct<1,unsigned short const *>(S2, v41);
                v51 = std::wstring::wstring(lpFileName, v63);
                Windows::Compat::Inventory::MareApplication::SetUninstallDataFromCacheBySid(v51, S2);
              }
            }
            if ( v41 )
              operator delete(v42, v47);
            goto LABEL_113;
          }
          v37 = (const wchar_t *)v63;
          if ( v64 > 7 )
            v37 = v63[0];
          v38 = (const WCHAR *)*((_QWORD *)v35 + 2);
          v39 = *((_QWORD *)v35 + 3) <= 7u ? v35 : *(const wchar_t **)v35;
          if ( v38 == v63[2] && (!v38 || !wmemcmp(v39, v37, (size_t)v38)) )
            break;
          v35 += 16;
        }
        v48 = (const unsigned __int16 *)v63;
        if ( v64 > 7 )
          v48 = v63[0];
        v49 = TelCacheProvider::SetMetadata(v22, v48, &dword_1800F6C3C);
        if ( v49 < 0 )
          AslLogCallPrintf(
            1,
            "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
            1027,
            "TelCacheProvider::SetMetadata failed [%#x]",
            v49);
LABEL_113:
        std::wstring::~wstring(v63);
      }
      LastError = 0;
    }
    else
    {
      LODWORD(v54) = LastError;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
        999,
        "TelCacheProvider::GetNextItem failed [%#x]",
        v54);
    }
  }
  else
  {
    LODWORD(v53) = ItemCount;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::UpdateCacheBeforeCollection",
      970,
      "TelCacheProvider::GetItemCount failed [%#x]",
      v53);
  }
LABEL_118:
  Windows::Compat::Inventory::MareApplication::~MareApplication((Windows::Compat::Inventory::MareApplication *)v76);
  std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::~vector<std::tuple<std::wstring,std::wstring,std::wstring>>(&v60);
  std::vector<std::wstring>::_Tidy(v58);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180025a20  push    rbp
0x180025a22  push    rbx
0x180025a23  push    rsi
0x180025a24  push    rdi
0x180025a25  push    r12
0x180025a27  push    r13
0x180025a29  push    r14
0x180025a2b  push    r15
0x180025a2d  lea     rbp, [rsp-178h]
0x180025a35  sub     rsp, 278h
0x180025a3c  mov     rax, cs:__security_cookie
0x180025a43  xor     rax, rsp
0x180025a46  mov     [rbp+1B0h+var_50], rax
0x180025a4d  mov     sil, dl
0x180025a50  mov     r14, rcx
0x180025a53  xor     r13d, r13d
0x180025a56  xorps   xmm0, xmm0
0x180025a59  movdqu  xmmword ptr [rsp+2B0h+var_258], xmm0
0x180025a5f  mov     [rsp+2B0h+var_248], r13
0x180025a64  movdqu  [rsp+2B0h+var_240], xmm0
0x180025a6a  mov     [rbp+1B0h+var_230], r13
0x180025a6e  lea     rcx, [rbp+1B0h+var_160]; this
0x180025a72  call    ??0MareApplication@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::MareApplication::MareApplication(void)
0x180025a77  nop
0x180025a78  lea     rdx, [r14+148h]
0x180025a7f  lea     rcx, [rsp+2B0h+var_240]
0x180025a84  call    ?GetUserData@MareDataWriter@Inventory@Compat@Windows@@SAJAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; Windows::Compat::Inventory::MareDataWriter::GetUserData(std::vector<std::tuple<std::wstring,std::wstring,std::wstring>> &,std::wstring *)
0x180025a89  mov     ebx, eax
0x180025a8b  test    eax, eax
0x180025a8d  jns     short loc_180025AB0
0x180025a8f  mov     dword ptr [rsp+2B0h+var_290], eax
0x180025a93  lea     r9, aGetuserdataFai; "GetUserData failed [%#x]"
0x180025a9a  mov     r8d, 37Bh
0x180025aa0  lea     rdx, aWindowsCompatI_35; "Windows::Compat::Inventory::MareDataWri"...
0x180025aa7  lea     ecx, [r13+1]
0x180025aab  jmp     loc_1800261B6
0x180025ab0  mov     edi, 1
0x180025ab5  cmp     eax, edi
0x180025ab7  jnz     short loc_180025AD6
0x180025ab9  mov     dword ptr [rsp+2B0h+var_290], edi
0x180025abd  lea     r9, aGetuserdataDid; "GetUserData did not find any user SIDs "...
0x180025ac4  mov     r8d, 380h
0x180025aca  lea     rdx, aWindowsCompatI_35; "Windows::Compat::Inventory::MareDataWri"...
0x180025ad1  jmp     loc_1800261B4
0x180025ad6  test    sil, sil
0x180025ad9  jz      loc_180025B83
0x180025adf  cmp     [r14+0E8h], r13
0x180025ae6  jz      loc_180025B7B
0x180025aec  lea     rbx, [r14+0F8h]
0x180025af3  mov     rcx, rbx; this
0x180025af6  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180025afb  mov     rcx, [r14+0E8h]
0x180025b02  mov     rax, [rcx]
0x180025b05  mov     rax, [rax+78h]
0x180025b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b0e  test    eax, eax
0x180025b10  js      short loc_180025B22
0x180025b12  mov     [r14+98h], r13w
0x180025b1a  mov     [r14+0F0h], r13w
0x180025b22  cmp     [rbx+24h], r13b
0x180025b26  jz      short loc_180025B49
0x180025b28  mov     cl, r13b
0x180025b2b  mov     rax, [rbx+18h]
0x180025b2f  cmp     [rax+4], edi
0x180025b32  jnz     short loc_180025B3B
0x180025b34  mov     [rbx+24h], r13b
0x180025b38  mov     cl, dil
0x180025b3b  or      r14d, 0FFFFFFFFh
0x180025b3f  add     [rax+4], r14d
0x180025b43  test    cl, cl
0x180025b45  jz      short loc_180025B7B
0x180025b47  jmp     short loc_180025B71
0x180025b49  or      r14d, 0FFFFFFFFh
0x180025b4d  mov     edx, r14d; dwMilliseconds
0x180025b50  mov     rcx, [rbx]; hHandle
0x180025b53  call    cs:__imp_WaitForSingleObject
0x180025b59  test    eax, eax
0x180025b5b  jnz     short loc_180025B7B
0x180025b5d  mov     rax, [rbx+18h]
0x180025b61  add     [rax], r14d
0x180025b64  add     [rbx+20h], r14d
0x180025b68  mov     rcx, [rbx]; hMutex
0x180025b6b  call    cs:__imp_ReleaseMutex
0x180025b71  mov     rcx, [rbx+10h]; hEvent
0x180025b75  call    cs:__imp_SetEvent
0x180025b7b  mov     ebx, r13d
0x180025b7e  jmp     loc_1800261BC
0x180025b83  mov     r15, qword ptr [rsp+2B0h+var_240]
0x180025b88  mov     r12, qword ptr [rsp+2B0h+var_240+8]
0x180025b8d  lea     rsi, aWindowsCompatI_35; "Windows::Compat::Inventory::MareDataWri"...
0x180025b94  jmp     loc_180025D78
0x180025b99  lea     rdx, [r15+40h]
0x180025b9d  lea     rcx, [rbp+1B0h+S2]
0x180025ba1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025ba6  nop
0x180025ba7  lea     r9, [r15+20h]
0x180025bab  mov     rcx, [r9+10h]
0x180025baf  mov     rax, 7FFFFFFFFFFFFFFEh
0x180025bb9  sub     rax, rcx
0x180025bbc  cmp     rax, 2Eh ; '.'
0x180025bc0  jb      loc_180026200
0x180025bc6  cmp     qword ptr [r9+18h], 7
0x180025bcb  jbe     short loc_180025BD0
0x180025bcd  mov     r9, [r9]
0x180025bd0  mov     [rsp+2B0h+var_280], 2Eh ; '.'
0x180025bd9  lea     rax, aAppdataLocalBa; "\\AppData\\Local\\Backup\\lastCompatBac"...
0x180025be0  mov     [rsp+2B0h+var_288], rax
0x180025be5  mov     [rsp+2B0h+var_290], rcx
0x180025bea  lea     rcx, [rbp+1B0h+lpFileName]
0x180025bee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180025bf3  nop
0x180025bf4  xorps   xmm0, xmm0
0x180025bf7  xor     eax, eax
0x180025bf9  movups  [rbp+1B0h+FileInformation], xmm0
0x180025bfd  movups  xmmword ptr [rbp+1B0h+FileTime1.dwLowDateTime], xmm0
0x180025c01  mov     [rbp+1B0h+var_170], eax
0x180025c04  lea     rcx, [rbp+1B0h+lpFileName]
0x180025c08  cmp     [rbp+1B0h+var_1C0], 7
0x180025c0d  cmova   rcx, [rbp+1B0h+lpFileName]; lpFileName
0x180025c12  lea     r8, [rbp+1B0h+FileInformation]; lpFileInformation
0x180025c16  xor     edx, edx; fInfoLevelId
0x180025c18  call    cs:__imp_GetFileAttributesExW
0x180025c1e  test    eax, eax
0x180025c20  jnz     short loc_180025C6B
0x180025c22  call    cs:__imp_GetLastError
0x180025c28  mov     ebx, eax
0x180025c2a  add     eax, 0FFFFFFFEh
0x180025c2d  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180025c31  mov     rdx, rsi
0x180025c34  cmp     eax, edi
0x180025c36  lea     rax, [rbp+1B0h+lpFileName]
0x180025c3a  ja      loc_180025DCC
0x180025c40  cmp     [rbp+1B0h+var_1C0], 7
0x180025c45  cmova   rax, [rbp+1B0h+lpFileName]
0x180025c4a  mov     [rsp+2B0h+var_290], rax
0x180025c4f  lea     r9, aLsNotUploadedU; "%ls not uploaded up to CDS %d"
0x180025c56  mov     r8d, 39Ah
0x180025c5c  mov     ecx, 3
0x180025c61  call    AslLogCallPrintf
0x180025c66  jmp     loc_180025D61
0x180025c6b  mov     rdx, r15
0x180025c6e  lea     rcx, [rbp+1B0h+var_218]
0x180025c72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025c77  nop
0x180025c78  xorps   xmm0, xmm0
0x180025c7b  xor     eax, eax
0x180025c7d  movups  [rbp+1B0h+var_1B8], xmm0
0x180025c81  movups  xmmword ptr [rbp+1B0h+FileTime2.dwLowDateTime], xmm0
0x180025c85  mov     [rbp+1B0h+var_198], eax
0x180025c88  lea     rcx, [rbp+1B0h+var_218]
0x180025c8c  cmp     [rbp+1B0h+var_200], 7
0x180025c91  cmova   rcx, [rbp+1B0h+var_218]; lpFileName
0x180025c96  lea     r8, [rbp+1B0h+var_1B8]; lpFileInformation
0x180025c9a  xor     edx, edx; fInfoLevelId
0x180025c9c  call    cs:__imp_GetFileAttributesExW
0x180025ca2  test    eax, eax
0x180025ca4  jnz     short loc_180025CD7
0x180025ca6  call    cs:__imp_GetLastError
0x180025cac  mov     ebx, eax
0x180025cae  mov     rdx, rsi
0x180025cb1  cmp     eax, 2
0x180025cb4  jnz     loc_180025E14
0x180025cba  lea     rax, [rbp+1B0h+S2]
0x180025cbe  cmp     [rbp+1B0h+var_1E0], 7
0x180025cc3  cmova   rax, [rbp+1B0h+S2]
0x180025cc8  lea     r9, aLsBackupJsonDo; "%ls backup JSON doesn't exist"
0x180025ccf  mov     r8d, 3ADh
0x180025cd5  jmp     short loc_180025D47
0x180025cd7  lea     rdx, [rbp+1B0h+FileTime2.dwHighDateTime]; lpFileTime2
0x180025cdb  lea     rcx, [rbp+1B0h+FileTime1.dwHighDateTime]; lpFileTime1
0x180025cdf  call    cs:__imp_CompareFileTime
0x180025ce5  test    eax, eax
0x180025ce7  js      short loc_180025D29
0x180025ce9  mov     rax, [rsp+2B0h+var_258+8]
0x180025cee  cmp     rax, [rsp+2B0h+var_248]
0x180025cf3  jz      short loc_180025D09
0x180025cf5  lea     rdx, [rbp+1B0h+S2]
0x180025cf9  mov     rcx, rax
0x180025cfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025d01  add     [rsp+2B0h+var_258+8], 20h ; ' '
0x180025d07  jmp     short loc_180025D1A
0x180025d09  lea     r8, [rbp+1B0h+S2]
0x180025d0d  mov     rdx, rax
0x180025d10  lea     rcx, [rsp+2B0h+var_258]
0x180025d15  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180025d1a  lea     r9, aLsHasBeenReadB; "%ls has been read by ADEPT"
0x180025d21  mov     r8d, 3BBh
0x180025d27  jmp     short loc_180025D36
0x180025d29  lea     r9, aLsHasNotBeenRe; "%ls has NOT been read by ADEPT"
0x180025d30  mov     r8d, 3BFh
0x180025d36  lea     rax, [rbp+1B0h+var_218]
0x180025d3a  cmp     [rbp+1B0h+var_200], 7
0x180025d3f  mov     rdx, rsi
0x180025d42  cmova   rax, [rbp+1B0h+var_218]
0x180025d47  mov     [rsp+2B0h+var_290], rax
0x180025d4c  mov     ecx, 3
0x180025d51  call    AslLogCallPrintf
0x180025d56  nop
0x180025d57  lea     rcx, [rbp+1B0h+var_218]
0x180025d5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025d60  nop
0x180025d61  lea     rcx, [rbp+1B0h+lpFileName]
0x180025d65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025d6a  nop
0x180025d6b  lea     rcx, [rbp+1B0h+S2]
0x180025d6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025d74  add     r15, 60h ; '`'
0x180025d78  cmp     r15, r12
0x180025d7b  jnz     loc_180025B99
0x180025d81  xor     ecx, ecx
0x180025d83  call    ?SetCacheUpdateMode@MareApplication@Inventory@Compat@Windows@@SAXW4CacheUpdateMode@1234@@Z; Windows::Compat::Inventory::MareApplication::SetCacheUpdateMode(Windows::Compat::Inventory::MareApplication::CacheUpdateMode)
0x180025d88  mov     [rsp+2B0h+var_270], r13d
0x180025d8d  lea     r13, [r14+90h]
0x180025d94  mov     [rsp+2B0h+var_268], r13
0x180025d99  lea     rdx, [rsp+2B0h+var_270]; unsigned int *
0x180025d9e  mov     rcx, r13; this
0x180025da1  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180025da6  mov     ebx, eax
0x180025da8  xor     r15d, r15d
0x180025dab  mov     rdx, rsi
0x180025dae  test    eax, eax
0x180025db0  jns     loc_180025E57
0x180025db6  mov     dword ptr [rsp+2B0h+var_290], eax
0x180025dba  lea     r9, aTelcacheprovid_5; "TelCacheProvider::GetItemCount failed ["...
0x180025dc1  mov     r8d, 3CAh
0x180025dc7  jmp     loc_1800261B4
0x180025dcc  cmp     [rbp+1B0h+var_1C0], 7
0x180025dd1  cmova   rax, [rbp+1B0h+lpFileName]
0x180025dd6  mov     [rsp+2B0h+var_290], rax
0x180025ddb  lea     r9, aGetfileattribu; "GetFileAttributesExW(%ls) failed [%d]"
0x180025de2  mov     r8d, 39Fh
0x180025de8  mov     ecx, edi
0x180025dea  call    AslLogCallPrintf
0x180025def  test    ebx, ebx
0x180025df1  jle     short loc_180025DFC
0x180025df3  movzx   ebx, bx
0x180025df6  or      ebx, 80070000h
0x180025dfc  lea     rcx, [rbp+1B0h+lpFileName]
0x180025e00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025e05  nop
0x180025e06  lea     rcx, [rbp+1B0h+S2]
0x180025e0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025e0f  jmp     loc_1800261BC
0x180025e14  lea     rax, [rbp+1B0h+var_218]
0x180025e18  cmp     [rbp+1B0h+var_200], 7
0x180025e1d  cmova   rax, [rbp+1B0h+var_218]
0x180025e22  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180025e26  mov     [rsp+2B0h+var_290], rax
0x180025e2b  lea     r9, aGetfileattribu; "GetFileAttributesExW(%ls) failed [%d]"
0x180025e32  mov     r8d, 3B2h
0x180025e38  mov     ecx, edi
0x180025e3a  call    AslLogCallPrintf
0x180025e3f  test    ebx, ebx
0x180025e41  jle     short loc_180025E4C
0x180025e43  movzx   ebx, bx
0x180025e46  or      ebx, 80070000h
0x180025e4c  lea     rcx, [rbp+1B0h+var_218]
0x180025e50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025e55  jmp     short loc_180025DFC
0x180025e57  mov     eax, [rsp+2B0h+var_270]
0x180025e5b  mov     dword ptr [rsp+2B0h+var_288], eax
0x180025e5f  lea     rax, aMarebackupapps; "MareBackupApps"
0x180025e66  mov     [rsp+2B0h+var_290], rax
0x180025e6b  lea     r9, aLsHasDItemsInC; "%ls has %d items in cache"
0x180025e72  mov     r8d, 3CFh
0x180025e78  mov     ecx, 3
0x180025e7d  call    AslLogCallPrintf
0x180025e82  lea     rdx, [rbp+1B0h+var_158]; struct IAmiInventoryItem *
0x180025e86  mov     rcx, r13; this
0x180025e89  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180025e8e  mov     ebx, eax
0x180025e90  cmp     eax, 80070103h
0x180025e95  jz      loc_180025F9F
0x180025e9b  or      r14d, 0FFFFFFFFh
0x180025e9f  mov     eax, [rsp+2B0h+var_270]
0x180025ea3  mov     ecx, eax
0x180025ea5  add     eax, r14d
0x180025ea8  mov     [rsp+2B0h+var_270], eax
0x180025eac  test    ecx, ecx
0x180025eae  jz      loc_180025F9F
0x180025eb4  test    ebx, ebx
0x180025eb6  js      loc_180025F6B
0x180025ebc  lea     rdx, [rsp+2B0h+var_258]
0x180025ec1  lea     rcx, [rbp+1B0h+var_218]
0x180025ec5  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180025eca  mov     r12, rax
0x180025ecd  mov     [rsp+2B0h+var_260], rax
0x180025ed2  mov     rbx, [rbp+1B0h+S1]
0x180025ed9  cmp     rbx, [rbp+1B0h+var_108]
0x180025ee0  jz      short loc_180025F4D
0x180025ee2  mov     r13, [r12+8]
0x180025ee7  mov     r15, [r12]
0x180025eeb  jmp     short loc_180025F42
0x180025eed  mov     rdx, r15
0x180025ef0  lea     rcx, [rbp+1B0h+S2]
0x180025ef4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180025ef9  lea     rdx, [rbp+1B0h+S2]
0x180025efd  cmp     [rbp+1B0h+var_1E0], 7
0x180025f02  cmova   rdx, [rbp+1B0h+S2]; S2
0x180025f07  mov     r8, [rbx+10h]; N
  ... truncated ...
```
