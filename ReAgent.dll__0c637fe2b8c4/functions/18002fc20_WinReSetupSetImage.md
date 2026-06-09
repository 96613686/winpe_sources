# WinReSetupSetImage

- ea: `0x18002fc20`
- end: `0x18003075e`
- name: `WinReSetupSetImage`
- size: `2878`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180001f94`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000f044`
- `0x18001c2f4`
- `0x18001c324`
- `0x18001c448`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f47c`
- `0x1800259d0`
- `0x180028cc4`
- `0x18002da38`
- `0x18002fc20`
- `0x180030f18`
- `0x18003158c`
- `0x180031e10`
- `0x18004df64`
- `0x18004f8d0`
- `0x180051dc8`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180030004`
- `msvcrt!_wcsicmp` at `0x180030029`
- `msvcrt!_wcsicmp` at `0x18003004e`
- `msvcrt!_wcsicmp` at `0x180030073`
- `msvcrt!_wcsicmp` at `0x180030118`
- `msvcrt!_wcsicmp` at `0x18003016d`
- `msvcrt!_wcsicmp` at `0x1800301af`
- `msvcrt!_wcsicmp` at `0x180030581`
- `msvcrt!_wcsicmp` at `0x180030004`
- `msvcrt!_wcsicmp` at `0x180030029`
- `msvcrt!_wcsicmp` at `0x18003004e`
- `msvcrt!_wcsicmp` at `0x180030073`
- `msvcrt!_wcsicmp` at `0x180030118`
- `msvcrt!_wcsicmp` at `0x18003016d`
- `msvcrt!_wcsicmp` at `0x1800301af`
- `msvcrt!_wcsicmp` at `0x180030581`
- `msvcrt!_wcsnicmp` at `0x1800300be`
- `msvcrt!_wcsnicmp` at `0x1800300be`
- `KERNEL32!RemoveDirectoryW` at `0x1800300a6`
- `KERNEL32!RemoveDirectoryW` at `0x1800300a6`
- `KERNEL32!ReadFile` at `0x180030567`
- `KERNEL32!ReadFile` at `0x180030567`
- `KERNEL32!CreateFileW` at `0x18003051a`
- `KERNEL32!CreateFileW` at `0x18003051a`
- `KERNEL32!CloseHandle` at `0x1800305b8`
- `KERNEL32!CloseHandle` at `0x1800305b8`
- `KERNEL32!FindFirstFileW` at `0x18002ff15`
- `KERNEL32!FindFirstFileW` at `0x18002ff15`
- `KERNEL32!FindNextFileW` at `0x180030247`
- `KERNEL32!FindNextFileW` at `0x180030247`
- `KERNEL32!FindClose` at `0x1800306fd`
- `KERNEL32!FindClose` at `0x1800306fd`
- `KERNEL32!DeleteFileW` at `0x180030216`
- `KERNEL32!DeleteFileW` at `0x180030216`

## string_xrefs

- `0x18002fe03`: `failed to get winre config`
- `0x1800303bc`: `failed to append path`
- `0x1800303b0`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002fd20`: `ImagePath: %s, ImageIndex: %d, backup directory: %s`
- `0x1800306d0`: `directory not specified`
- `0x1800300b7`: `install`
- `0x1800305a7`: `StringCchCopyW failed`
- `0x180030602`: `string copy failed`
- `0x180030653`: `string copy failed`
- `0x18003068b`: `failed to set winre config`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall WinReSetupSetImage(__int64 a1, unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r14
  DWORD v7; // edi
  unsigned int v8; // r15d
  __int64 FirstFileW; // r13
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // r8
  void *v12; // r12
  unsigned int WimImageInfo; // eax
  bool v14; // cc
  _QWORD *v15; // rax
  __int64 v16; // rdx
  const wchar_t *v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  __int64 v21; // rdx
  const WCHAR *v22; // r15
  _QWORD *v23; // rax
  __int64 v24; // rdx
  const WCHAR *v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // rax
  const wchar_t *v29; // rcx
  __int64 v30; // rdx
  const wchar_t *v31; // rax
  const wchar_t *v32; // rax
  const wchar_t *v33; // rax
  unsigned __int16 *v34; // rax
  const WCHAR *v35; // rax
  const wchar_t *v36; // rax
  const wchar_t *v37; // rax
  const wchar_t *v38; // rax
  char v39; // r14
  const WCHAR *v40; // rcx
  __int64 v41; // rdx
  int v42; // edi
  const unsigned __int16 *v43; // r8
  unsigned int v44; // eax
  _QWORD *v45; // rax
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // rax
  __int64 v48; // rcx
  const WCHAR *v49; // rax
  __int64 v50; // rdx
  HANDLE FileW; // rdi
  unsigned __int16 *v52; // rdi
  const wchar_t *v53; // r8
  void *Block; // [rsp+48h] [rbp-20A0h] BYREF
  unsigned __int16 *v57; // [rsp+50h] [rbp-2098h]
  __int64 v58; // [rsp+58h] [rbp-2090h]
  const unsigned __int16 *v59; // [rsp+60h] [rbp-2088h]
  __int64 v60; // [rsp+68h] [rbp-2080h]
  _QWORD v61[4]; // [rsp+70h] [rbp-2078h] BYREF
  _QWORD v62[4]; // [rsp+90h] [rbp-2058h] BYREF
  _QWORD v63[4]; // [rsp+B0h] [rbp-2038h] BYREF
  DWORD NumberOfBytesRead[2]; // [rsp+D0h] [rbp-2018h] BYREF
  __int128 v65; // [rsp+D8h] [rbp-2010h] BYREF
  __int128 v66; // [rsp+E8h] [rbp-2000h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-1FF0h]
  _QWORD v68[2]; // [rsp+108h] [rbp-1FE0h] BYREF
  __int64 v69; // [rsp+118h] [rbp-1FD0h]
  struct _GUID v70; // [rsp+128h] [rbp-1FC0h] BYREF
  _QWORD v71[5]; // [rsp+138h] [rbp-1FB0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp-1F88h] BYREF
  _QWORD v73[76]; // [rsp+3B0h] [rbp-1D38h] BYREF
  unsigned __int16 v74[302]; // [rsp+614h] [rbp-1AD4h] BYREF
  unsigned __int16 v75[306]; // [rsp+870h] [rbp-1878h] BYREF
  int v76; // [rsp+AD4h] [rbp-1614h]
  unsigned int v77; // [rsp+AD8h] [rbp-1610h]
  int v78; // [rsp+ADCh] [rbp-160Ch]
  int v79; // [rsp+AE0h] [rbp-1608h]
  unsigned __int16 v80[302]; // [rsp+AE4h] [rbp-1604h] BYREF
  _QWORD v81[79]; // [rsp+D40h] [rbp-13A8h] BYREF
  wchar_t String2[614]; // [rsp+FB8h] [rbp-1130h] BYREF
  unsigned __int16 v83[302]; // [rsp+1484h] [rbp-C64h] BYREF
  int v84; // [rsp+16E0h] [rbp-A08h]
  int v85; // [rsp+1948h] [rbp-7A0h]
  int v86; // [rsp+1950h] [rbp-798h]
  unsigned __int16 v88[306]; // [rsp+197Ch] [rbp-76Ch] BYREF
  unsigned __int16 Buffer; // [rsp+1BE0h] [rbp-508h] BYREF
  char v90[606]; // [rsp+1BE2h] [rbp-506h] BYREF
  unsigned __int16 v91[304]; // [rsp+1E40h] [rbp-2A8h] BYREF

  v60 = -2;
  v59 = a4;
  v5 = a2;
  v57 = a2;
  v7 = 0;
  NumberOfBytesRead[0] = 0;
  v8 = 0;
  v70 = GUID_NULL;
  Block = 0;
  memset_0(v81, 0, 0xEA0u);
  memset_0(v73, 0, 0x990u);
  FirstFileW = -1;
  v58 = -1;
  memset_0(v91, 0, 0x25Cu);
  v65 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupSetImage");
  v10 = a4;
  if ( !a4 )
    v10 = L"NULL";
  v11 = v5;
  if ( v5 )
    v11 = L"NULL";
  UnattendLogW(0, L"ImagePath: %s, ImageIndex: %d, backup directory: %s", v11, a3, v10);
  LogGuid(L"newOSBCDGuid: ", a1);
  if ( !v5 || !*v5 )
  {
    UnattendLogW(1, L"directory not specified");
    goto LABEL_96;
  }
  if ( !(unsigned int)winReGetPBRImageFullPath(v5, v91) )
  {
    UnattendLogW(1, L"PBR image not found.");
    goto LABEL_96;
  }
  if ( !(unsigned int)winreGetOSGuidOrDefault(a1, &v70) )
  {
    UnattendLogW(2, L"winreGetOSGuidOrDefault failed");
    goto LABEL_96;
  }
  if ( CBootCfg::GetOsInfoForBootEntry((CBootCfg *)CBootCfg::m_instance, &v70, (struct _SRT_OS_INFO **)&Block) )
  {
    UnattendLogW(2, L"GetOsInfoForBootEntry failed");
    v12 = Block;
    goto LABEL_94;
  }
  v81[0] = 3744;
  v12 = Block;
  if ( !(unsigned int)WinReGetConfigInternal((__int64)Block, 0, (__int64)v81) )
  {
    UnattendLogW(2, L"failed to get winre config");
    goto LABEL_94;
  }
  WimImageInfo = Utils::GetWimImageInfo(v91, a3, (struct _WIM_IMAGE_INFO *)&v65);
  if ( !WimImageInfo )
  {
    UnattendLogW(0, L"PBR image version: %d.%d", (unsigned int)v65, DWORD1(v65));
    v14 = (unsigned int)v65 <= 6;
    if ( (_DWORD)v65 == 6 )
    {
      if ( DWORD1(v65) > 3 )
        goto LABEL_21;
      v14 = (unsigned int)v65 <= 6;
    }
    if ( v14 )
    {
      v22 = &cchOriginalDestLength;
      goto LABEL_54;
    }
LABEL_21:
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    std::wstring::wstring(v71, v5);
    if ( !v71[2]
      || (v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71),
          v17 = L"*",
          *((_WORD *)v15 + v16 - 1) != 92) )
    {
      v17 = L"\\*";
    }
    v18 = std::char_traits<unsigned short>::length(v17);
    std::wstring::append(v71, v19, v18);
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
    FirstFileW = (__int64)FindFirstFileW(v20, &FindFileData);
    v58 = FirstFileW;
    if ( FirstFileW == -1 )
    {
      UnattendLogW(2, L"FindFirstFileW failed");
      v22 = &cchOriginalDestLength;
    }
    else
    {
      v22 = &cchOriginalDestLength;
      do
      {
        std::wstring::wstring(v68, v5);
        if ( !v69
          || (v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68),
              v25 = &cchOriginalDestLength,
              *((_WORD *)v23 + v24 - 1) != 92) )
        {
          v25 = L"\\";
        }
        v26 = std::char_traits<unsigned short>::length(v25);
        std::wstring::append(v68, v27, v26);
        v28 = std::char_traits<unsigned short>::length(FindFileData.cFileName);
        std::wstring::append(v68, (__int64)FindFileData.cFileName, v28);
        std::wstring::wstring(&v66, FindFileData.cFileName);
        v29 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v66);
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( _wcsicmp(v29, L".") )
          {
            v31 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v66);
            if ( _wcsicmp(v31, L"..") )
            {
              v32 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v66);
              if ( _wcsicmp(v32, L"drivers") )
              {
                v33 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v66);
                if ( _wcsicmp(v33, L"OEMInformation") )
                {
                  v34 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
                  winreDeleteAllFiles(v34);
                  v35 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
                  RemoveDirectoryW(v35);
                }
              }
            }
          }
        }
        else
        {
          if ( _wcsnicmp(v29, L"install", 7u) )
            goto LABEL_41;
          std::wstring::wstring(v63, &v66, v67 - 3);
          v7 |= 9u;
          NumberOfBytesRead[0] = v7;
          v36 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
          if ( !_wcsicmp(v36, L"wim") )
            goto LABEL_40;
          std::wstring::wstring(v62, &v66, v67 - 3);
          v7 |= 0x12u;
          NumberOfBytesRead[0] = v7;
          v37 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62);
          if ( _wcsicmp(v37, L"swm")
            && (std::wstring::wstring(v61, &v66, v67 - 3),
                v7 |= 0x24u,
                v38 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61),
                _wcsicmp(v38, L"esd")) )
          {
LABEL_41:
            v39 = 1;
          }
          else
          {
LABEL_40:
            v39 = 0;
          }
          if ( (v7 & 4) != 0 )
          {
            v7 &= ~4u;
            std::wstring::~wstring((__int64)v61, v30);
          }
          if ( (v7 & 2) != 0 )
          {
            v7 &= ~2u;
            std::wstring::~wstring((__int64)v62, v30);
          }
          if ( (v7 & 1) != 0 )
          {
            v7 &= ~1u;
            std::wstring::~wstring((__int64)v63, v30);
          }
          if ( v39 )
          {
            v40 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
            DeleteFileW(v40);
          }
          v5 = v57;
        }
        std::wstring::~wstring((__int64)&v66, v30);
        std::wstring::~wstring((__int64)v68, v41);
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    }
    std::wstring::~wstring((__int64)v71, v21);
LABEL_54:
    if ( !v88[0] )
    {
LABEL_72:
      if ( (unsigned int)v65 <= 6 && DWORD1(v65) < 4 && v59 )
      {
        std::wstring::wstring(v68, v59);
        v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
        if ( *((_WORD *)v45 + v69 - 1) != 92 )
          v22 = L"\\";
        v46 = std::char_traits<unsigned short>::length(v22);
        std::wstring::append(v68, (__int64)v22, v46);
        v47 = std::char_traits<unsigned short>::length(L"WinReLocation.txt");
        std::wstring::append(v68, v48, v47);
        v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
        FileW = CreateFileW(v49, 0x80000000, 0, 0, 3u, 0x80u, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          NumberOfBytesRead[0] = 0;
          memset_0(&Buffer, 0, 0x208u);
          if ( ReadFile(FileW, &Buffer, 0x208u, NumberOfBytesRead, 0)
            && _wcsicmp(&Buffer, String2)
            && StringCchCopyW(v80, 0x12Eu, &Buffer) < 0 )
          {
            UnattendLogW(2, L"StringCchCopyW failed");
          }
          CloseHandle(FileW);
        }
        std::wstring::~wstring((__int64)v68, v50);
      }
      v73[0] = 2448;
      v76 = v85;
      if ( StringCchCopyW(v75, 0x12Eu, v83) < 0
        || (v78 = v84, v79 = v86, v52 = v57, StringCchCopyW(v74, 0x12Eu, v57) < 0) )
      {
        UnattendLogW(2, L"string copy failed");
        v8 = 0;
      }
      else
      {
        v77 = a3;
        if ( (unsigned int)WinReSetConfig(v73, v12) )
        {
          winreCreatePBRMarkerFile(v52);
          v8 = 1;
        }
        else
        {
          UnattendLogW(2, L"failed to set winre config");
          v8 = 0;
        }
      }
      goto LABEL_92;
    }
    v66 = 0;
    Buffer = 0;
    memset_0(v90, 0, 0x25Au);
    *(_QWORD *)NumberOfBytesRead = 0;
    v42 = StringCchLengthW(v88, 0x7FFFFFFFu, (unsigned __int64 *)NumberOfBytesRead);
    if ( v42 >= 0 )
    {
      if ( !*(_QWORD *)NumberOfBytesRead || (v43 = L"%s\\%s", v88[*(_QWORD *)NumberOfBytesRead - 1] == 92) )
        v43 = L"%s%s";
      v42 = StringCchPrintfW(&Buffer, 0x12Eu, v43, v88, L"Winre.wim");
      if ( v42 >= 0 )
      {
LABEL_69:
        v44 = Utils::GetWimImageInfo(&Buffer, 1u, (struct _WIM_IMAGE_INFO *)&v66);
        if ( v44 )
        {
          UnattendLogW(1, L"Unable to get the WinRE WIM image info. Error: 0X%X", v44);
        }
        else
        {
          UnattendLogW(0, L"Downlevel WinRE image version: %d.%d", (unsigned int)v66, DWORD1(v66));
          if ( (_QWORD)v65 == (_QWORD)v66 )
            UnattendLogW(0, L"The WinRE image associated with the current PBR image is: %s.", v88);
        }
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
          (unsigned int)v42);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (unsigned int)v42);
    }
    if ( (_WORD)v42 )
    {
      UnattendLogW(2, L"WinReSetupSetImage %s (0x%x) in file %S line %d", L"failed to append path");
      v8 = 0;
LABEL_92:
      if ( FirstFileW != -1 )
        FindClose((HANDLE)FirstFileW);
      goto LABEL_94;
    }
    goto LABEL_69;
  }
  UnattendLogW(1, L"Unable to get the WIM image info. Error: 0X%X", WimImageInfo);
LABEL_94:
  if ( v12 )
    operator delete(v12);
LABEL_96:
  v53 = L"TRUE";
  if ( !v8 )
    v53 = L"FALSE";
  UnattendLogW(0, L"WinReSetupSetImage() returning %s", v53);
  UnattendFinalizeLog();
  return v8;
}

```

## disassembly

```asm
0x18002fc20  push    rbx
0x18002fc22  push    rsi
0x18002fc23  push    rdi
0x18002fc24  push    r12
0x18002fc26  push    r13
0x18002fc28  push    r14
0x18002fc2a  push    r15
0x18002fc2c  mov     eax, 20B0h
0x18002fc31  call    _alloca_probe
0x18002fc36  sub     rsp, rax
0x18002fc39  mov     [rsp+20E8h+var_2080], 0FFFFFFFFFFFFFFFEh
0x18002fc42  mov     rax, cs:__security_cookie
0x18002fc49  xor     rax, rsp
0x18002fc4c  mov     [rsp+20E8h+var_48], rax
0x18002fc54  mov     r12, r9
0x18002fc57  mov     [rsp+20E8h+var_2088], r9
0x18002fc5c  mov     [rsp+20E8h+var_20A4], r8d
0x18002fc61  mov     r14, rdx
0x18002fc64  mov     [rsp+20E8h+var_2098], rdx
0x18002fc69  mov     rsi, rcx
0x18002fc6c  xor     ebx, ebx
0x18002fc6e  mov     edi, ebx
0x18002fc70  mov     [rsp+20E8h+NumberOfBytesRead], ebx
0x18002fc77  mov     r15d, ebx
0x18002fc7a  mov     [rsp+20E8h+var_20A8], ebx
0x18002fc7e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fc85  movdqu  xmmword ptr [rsp+20E8h+var_1FC0.Data1], xmm0
0x18002fc8e  mov     [rsp+20E8h+Block], rbx
0x18002fc93  xor     edx, edx; Val
0x18002fc95  mov     r8d, 0EA0h; Size
0x18002fc9b  lea     rcx, [rsp+20E8h+var_13A8]; void *
0x18002fca3  call    memset_0
0x18002fca8  xor     edx, edx; Val
0x18002fcaa  mov     r8d, 990h; Size
0x18002fcb0  lea     rcx, [rsp+20E8h+var_1D38]; void *
0x18002fcb8  call    memset_0
0x18002fcbd  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002fcc1  mov     [rsp+20E8h+var_2090], r13
0x18002fcc6  xor     edx, edx; Val
0x18002fcc8  mov     r8d, 25Ch; Size
0x18002fcce  lea     rcx, [rsp+20E8h+var_2A8]; void *
0x18002fcd6  call    memset_0
0x18002fcdb  xorps   xmm0, xmm0
0x18002fcde  movups  [rsp+20E8h+var_2010], xmm0
0x18002fce6  xor     ecx, ecx
0x18002fce8  call    UnattendInitializeLogEx2
0x18002fced  lea     rdx, aEnterWinresetu_5; "Enter WinReSetupSetImage"
0x18002fcf4  xor     ecx, ecx
0x18002fcf6  call    UnattendLogW
0x18002fcfb  lea     rcx, aNull_0; "NULL"
0x18002fd02  mov     rax, r12
0x18002fd05  test    r12, r12
0x18002fd08  cmovz   rax, rcx
0x18002fd0c  mov     r8, r14
0x18002fd0f  test    r14, r14
0x18002fd12  cmovnz  r8, rcx
0x18002fd16  mov     qword ptr [rsp+20E8h+dwCreationDisposition], rax
0x18002fd1b  mov     r9d, [rsp+20E8h+var_20A4]
0x18002fd20  lea     rdx, aImagepathSImag; "ImagePath: %s, ImageIndex: %d, backup d"...
0x18002fd27  xor     ecx, ecx
0x18002fd29  call    UnattendLogW
0x18002fd2e  mov     rdx, rsi
0x18002fd31  lea     rcx, aNewosbcdguid_0; "newOSBCDGuid: "
0x18002fd38  call    LogGuid
0x18002fd3d  nop
0x18002fd3e  test    r14, r14
0x18002fd41  jz      loc_1800306D0
0x18002fd47  cmp     [r14], bx
0x18002fd4b  jz      loc_1800306D0
0x18002fd51  lea     rdx, [rsp+20E8h+var_2A8]
0x18002fd59  mov     rcx, r14
0x18002fd5c  call    winReGetPBRImageFullPath
0x18002fd61  test    eax, eax
0x18002fd63  jnz     short loc_18002FD7A
0x18002fd65  lea     rdx, aPbrImageNotFou; "PBR image not found."
0x18002fd6c  lea     ecx, [rbx+1]
0x18002fd6f  call    UnattendLogW
0x18002fd74  nop
0x18002fd75  jmp     loc_180030710
0x18002fd7a  lea     rdx, [rsp+20E8h+var_1FC0]
0x18002fd82  mov     rcx, rsi
0x18002fd85  call    winreGetOSGuidOrDefault
0x18002fd8a  test    eax, eax
0x18002fd8c  jnz     short loc_18002FDA3
0x18002fd8e  lea     rdx, aWinregetosguid_0; "winreGetOSGuidOrDefault failed"
0x18002fd95  lea     ecx, [rax+2]
0x18002fd98  call    UnattendLogW
0x18002fd9d  nop
0x18002fd9e  jmp     loc_180030710
0x18002fda3  lea     r8, [rsp+20E8h+Block]; struct _SRT_OS_INFO **
0x18002fda8  lea     rdx, [rsp+20E8h+var_1FC0]; struct _GUID *
0x18002fdb0  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x18002fdb7  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x18002fdbc  test    eax, eax
0x18002fdbe  jz      short loc_18002FDDC
0x18002fdc0  lea     rdx, aGetosinfoforbo; "GetOsInfoForBootEntry failed"
0x18002fdc7  mov     ecx, 2
0x18002fdcc  call    UnattendLogW
0x18002fdd1  nop
0x18002fdd2  mov     r12, [rsp+20E8h+Block]
0x18002fdd7  jmp     loc_180030703
0x18002fddc  mov     [rsp+20E8h+var_13A8], 0EA0h
0x18002fde8  lea     r8, [rsp+20E8h+var_13A8]
0x18002fdf0  xor     edx, edx
0x18002fdf2  mov     r12, [rsp+20E8h+Block]
0x18002fdf7  mov     rcx, r12
0x18002fdfa  call    WinReGetConfigInternal
0x18002fdff  test    eax, eax
0x18002fe01  jnz     short loc_18002FE18
0x18002fe03  lea     rdx, aFailedToGetWin_1; "failed to get winre config"
0x18002fe0a  lea     ecx, [rax+2]
0x18002fe0d  call    UnattendLogW
0x18002fe12  nop
0x18002fe13  jmp     loc_180030703
0x18002fe18  lea     r8, [rsp+20E8h+var_2010]; struct _WIM_IMAGE_INFO *
0x18002fe20  mov     edx, [rsp+20E8h+var_20A4]; unsigned int
0x18002fe24  lea     rcx, [rsp+20E8h+var_2A8]; unsigned __int16 *
0x18002fe2c  call    ?GetWimImageInfo@Utils@@SAKPEBGKPEAU_WIM_IMAGE_INFO@@@Z; Utils::GetWimImageInfo(ushort const *,ulong,_WIM_IMAGE_INFO *)
0x18002fe31  test    eax, eax
0x18002fe33  jz      short loc_18002FE4F
0x18002fe35  mov     r8d, eax
0x18002fe38  lea     rdx, aUnableToGetThe; "Unable to get the WIM image info. Error"...
0x18002fe3f  mov     ecx, 1
0x18002fe44  call    UnattendLogW
0x18002fe49  nop
0x18002fe4a  jmp     loc_180030703
0x18002fe4f  mov     r9d, dword ptr [rsp+20E8h+var_2010+4]
0x18002fe57  mov     r8d, dword ptr [rsp+20E8h+var_2010]
0x18002fe5f  lea     rdx, aPbrImageVersio; "PBR image version: %d.%d"
0x18002fe66  xor     ecx, ecx
0x18002fe68  call    UnattendLogW
0x18002fe6d  cmp     dword ptr [rsp+20E8h+var_2010], 6
0x18002fe75  jnz     short loc_18002FE89
0x18002fe77  cmp     dword ptr [rsp+20E8h+var_2010+4], 3
0x18002fe7f  ja      short loc_18002FE8F
0x18002fe81  cmp     dword ptr [rsp+20E8h+var_2010], 6
0x18002fe89  jbe     loc_18003026B
0x18002fe8f  xor     edx, edx; Val
0x18002fe91  mov     r8d, 250h; Size
0x18002fe97  lea     rcx, [rsp+20E8h+FindFileData]; void *
0x18002fe9f  call    memset_0
0x18002fea4  mov     rdx, r14
0x18002fea7  lea     rcx, [rsp+20E8h+var_1FB0]
0x18002feaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002feb4  nop
0x18002feb5  mov     rdx, [rsp+20E8h+var_1FA0]
0x18002febd  test    rdx, rdx
0x18002fec0  jz      short loc_18002FEDE
0x18002fec2  lea     rcx, [rsp+20E8h+var_1FB0]
0x18002feca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002fecf  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18002fed5  lea     rcx, asc_18007D468; "*"
0x18002fedc  jz      short loc_18002FEE5
0x18002fede  lea     rcx, asc_180083504; "\\*"
0x18002fee5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002feea  mov     r8, rax
0x18002feed  mov     rdx, rcx
0x18002fef0  lea     rcx, [rsp+20E8h+var_1FB0]
0x18002fef8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002fefd  lea     rcx, [rsp+20E8h+var_1FB0]
0x18002ff05  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ff0a  mov     rcx, rax; lpFileName
0x18002ff0d  lea     rdx, [rsp+20E8h+FindFileData]; lpFindFileData
0x18002ff15  call    cs:__imp_FindFirstFileW
0x18002ff1b  mov     r13, rax
0x18002ff1e  mov     [rsp+20E8h+var_2090], rax
0x18002ff23  mov     esi, 2
0x18002ff28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ff2c  jnz     short loc_18002FF48
0x18002ff2e  lea     rdx, aFindfirstfilew_0; "FindFirstFileW failed"
0x18002ff35  mov     ecx, esi
0x18002ff37  call    UnattendLogW
0x18002ff3c  lea     r15, cchOriginalDestLength
0x18002ff43  jmp     loc_180030255
0x18002ff48  lea     r15, cchOriginalDestLength
0x18002ff4f  mov     rdx, r14
0x18002ff52  lea     rcx, [rsp+20E8h+var_1FE0]
0x18002ff5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002ff5f  nop
0x18002ff60  mov     rdx, [rsp+20E8h+var_1FD0]
0x18002ff68  test    rdx, rdx
0x18002ff6b  jz      short loc_18002FF85
0x18002ff6d  lea     rcx, [rsp+20E8h+var_1FE0]
0x18002ff75  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ff7a  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18002ff80  mov     rcx, r15
0x18002ff83  jz      short loc_18002FF8C
0x18002ff85  lea     rcx, pszSrc; "\\"
0x18002ff8c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002ff91  mov     r8, rax
0x18002ff94  mov     rdx, rcx
0x18002ff97  lea     rcx, [rsp+20E8h+var_1FE0]
0x18002ff9f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002ffa4  lea     rcx, [rsp+20E8h+FindFileData.cFileName]
0x18002ffac  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002ffb1  mov     r8, rax
0x18002ffb4  lea     rdx, [rsp+20E8h+FindFileData.cFileName]
0x18002ffbc  lea     rcx, [rsp+20E8h+var_1FE0]
0x18002ffc4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002ffc9  lea     rdx, [rsp+20E8h+FindFileData.cFileName]
0x18002ffd1  lea     rcx, [rsp+20E8h+var_2000]
0x18002ffd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002ffde  nop
0x18002ffdf  lea     rcx, [rsp+20E8h+var_2000]
0x18002ffe7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ffec  mov     rcx, rax; String1
0x18002ffef  test    byte ptr [rsp+20E8h+FindFileData.dwFileAttributes], 10h
0x18002fff7  jz      loc_1800300B1
0x18002fffd  lea     rdx, asc_180070DA8; "."
0x180030004  call    cs:__imp__wcsicmp
0x18003000a  test    eax, eax
0x18003000c  jz      loc_180030221
0x180030012  lea     rcx, [rsp+20E8h+var_2000]
0x18003001a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003001f  mov     rcx, rax; String1
0x180030022  lea     rdx, asc_18007D4E4; ".."
0x180030029  call    cs:__imp__wcsicmp
0x18003002f  test    eax, eax
0x180030031  jz      loc_180030221
0x180030037  lea     rcx, [rsp+20E8h+var_2000]
0x18003003f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030044  mov     rcx, rax; String1
0x180030047  lea     rdx, aDrivers; "drivers"
0x18003004e  call    cs:__imp__wcsicmp
0x180030054  test    eax, eax
0x180030056  jz      loc_180030221
0x18003005c  lea     rcx, [rsp+20E8h+var_2000]
0x180030064  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030069  mov     rcx, rax; String1
0x18003006c  lea     rdx, aOeminformation; "OEMInformation"
0x180030073  call    cs:__imp__wcsicmp
0x180030079  test    eax, eax
0x18003007b  jz      loc_180030221
0x180030081  lea     rcx, [rsp+20E8h+var_1FE0]
0x180030089  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003008e  mov     rcx, rax
0x180030091  call    winreDeleteAllFiles
0x180030096  lea     rcx, [rsp+20E8h+var_1FE0]
0x18003009e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800300a3  mov     rcx, rax; lpPathName
0x1800300a6  call    cs:__imp_RemoveDirectoryW
0x1800300ac  jmp     loc_180030221
0x1800300b1  mov     r8d, 7; MaxCount
0x1800300b7  lea     rdx, aInstall; "install"
0x1800300be  call    cs:__imp__wcsnicmp
0x1800300c4  test    eax, eax
0x1800300c6  jnz     loc_1800301BE
0x1800300cc  mov     r8, [rsp+20E8h+var_1FF0]
0x1800300d4  add     r8, 0FFFFFFFFFFFFFFFDh
0x1800300d8  lea     r14d, [rax+3]
0x1800300dc  mov     r9d, r14d
0x1800300df  lea     rdx, [rsp+20E8h+var_2000]
0x1800300e7  lea     rcx, [rsp+20E8h+var_2038]
0x1800300ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800300f4  or      edi, 8
0x1800300f7  or      edi, 1
0x1800300fa  mov     [rsp+20E8h+NumberOfBytesRead], edi
0x180030101  lea     rcx, [rsp+20E8h+var_2038]
0x180030109  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003010e  mov     rcx, rax; String1
0x180030111  lea     rdx, aWim_0; "wim"
0x180030118  call    cs:__imp__wcsicmp
0x18003011e  test    eax, eax
0x180030120  jz      loc_1800301B9
0x180030126  mov     r8, [rsp+20E8h+var_1FF0]
0x18003012e  add     r8, 0FFFFFFFFFFFFFFFDh
0x180030132  mov     r9d, r14d
0x180030135  lea     rdx, [rsp+20E8h+var_2000]
0x18003013d  lea     rcx, [rsp+20E8h+var_2058]
0x180030145  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18003014a  or      edi, 10h
0x18003014d  or      edi, esi
0x18003014f  mov     [rsp+20E8h+NumberOfBytesRead], edi
0x180030156  lea     rcx, [rsp+20E8h+var_2058]
0x18003015e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030163  mov     rcx, rax; String1
0x180030166  lea     rdx, aSwm; "swm"
0x18003016d  call    cs:__imp__wcsicmp
0x180030173  test    eax, eax
0x180030175  jz      short loc_1800301B9
0x180030177  mov     r8, [rsp+20E8h+var_1FF0]
0x18003017f  add     r8, 0FFFFFFFFFFFFFFFDh
0x180030183  mov     r9d, r14d
0x180030186  lea     rdx, [rsp+20E8h+var_2000]
0x18003018e  lea     rcx, [rsp+20E8h+var_2078]
0x180030193  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x180030198  or      edi, 24h
0x18003019b  lea     rcx, [rsp+20E8h+var_2078]
0x1800301a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800301a5  mov     rcx, rax; String1
0x1800301a8  lea     rdx, aEsd; "esd"
0x1800301af  call    cs:__imp__wcsicmp
0x1800301b5  test    eax, eax
0x1800301b7  jnz     short loc_1800301BE
0x1800301b9  mov     r14b, bl
0x1800301bc  jmp     short loc_1800301C1
0x1800301be  mov     r14b, 1
0x1800301c1  test    dil, 4
0x1800301c5  jz      short loc_1800301D5
0x1800301c7  and     edi, 0FFFFFFFBh
  ... truncated ...
```
