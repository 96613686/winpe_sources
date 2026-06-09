# CDataCollection::GetFilesVersion(wchar_t const *)

- ea: `0x18008cbac`
- end: `0x18008cef8`
- name: `?GetFilesVersion@CDataCollection@@QEAAJPEB_W@Z`
- size: `844`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x180005e34`
- `0x18000716c`
- `0x180007e10`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000dad0`
- `0x180014720`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001fe24`
- `0x18002b7a4`
- `0x180050db0`
- `0x18008c4c0`
- `0x18008c7f8`
- `0x18008cbac`
- `0x180097450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce73`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cd55`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cd8e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cd55`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cd8e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008ce9a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008ce9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDataCollection::GetFilesVersion(CReport **this, const wchar_t *a2)
{
  int TempFile; // edi
  LPCWSTR *i; // rbx
  _WORD *v6; // rcx
  char *v7; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v17; // [rsp+58h] [rbp-A8h]
  _WORD *v18; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v19; // [rsp+78h] [rbp-88h]
  _QWORD v20[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v20);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v18);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  hFile = 0;
  Buffer = -257;
  NumberOfBytesWritten = 0;
  FileName[0] = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    TempFile = -2147024809;
    goto LABEL_37;
  }
  if ( (int)CDataCollection::ExpandMultipleFileList(this, a2, v20) >= 0 )
  {
    for ( i = (LPCWSTR *)v20[0]; i != (LPCWSTR *)v20[1]; i += 4 )
    {
      if ( UtilFileExists(*i) )
      {
        v6 = v18;
        v19 = v18;
        *v18 = 0;
        CDataCollection::GetFileVersionInformation(v6, *i, &v18);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpBuffer, v18, v19 - v18);
      }
    }
  }
  if ( lpBuffer == v17 )
    goto LABEL_36;
  TempFile = UtilGetTempFile(
               (__int64)&hFile,
               0,
               (const size_t *)L".version.txt",
               FileName,
               (__int64)lpOverlapped,
               0,
               1u,
               0);
  v7 = (char *)hFile;
  if ( TempFile >= 0 )
  {
    if ( WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
    {
      if ( WriteFile(v7, lpBuffer, 2 * ((v17 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == 2 * ((v17 - (_BYTE *)lpBuffer) >> 1) )
      {
        TempFile = CReport::AddFile(*this, WerFileTypeOther, 3u, FileName, L"FileVer.txt", 0);
        if ( TempFile < 0 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
              (unsigned int)FileName,
              TempFile);
          goto LABEL_33;
        }
LABEL_36:
        TempFile = 0;
        goto LABEL_37;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 63;
LABEL_31:
        WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 62;
        goto LABEL_31;
      }
    }
    LastError = GetLastError();
    TempFile = ERROR_HR_FROM_WIN32(LastError);
    if ( TempFile >= 0 )
      goto LABEL_37;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)TempFile);
LABEL_33:
  if ( v7 != (char *)-1LL && v7 + 1 != (char *)1 && FileName[0] )
    DeleteFileW(FileName);
LABEL_37:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpBuffer);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v18);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(v20);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x18008cbac  mov     [rsp-8+arg_10], rbx
0x18008cbb1  mov     [rsp-8+arg_18], rsi
0x18008cbb6  push    rbp
0x18008cbb7  push    rdi
0x18008cbb8  push    r14
0x18008cbba  lea     rbp, [rsp-1D0h]
0x18008cbc2  sub     rsp, 2D0h
0x18008cbc9  mov     rax, cs:__security_cookie
0x18008cbd0  xor     rax, rsp
0x18008cbd3  mov     [rbp+1E0h+var_20], rax
0x18008cbda  mov     rbx, rdx
0x18008cbdd  mov     rsi, rcx
0x18008cbe0  lea     rcx, [rbp+1E0h+var_250]
0x18008cbe4  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18008cbe9  nop
0x18008cbea  lea     rcx, [rsp+2E0h+var_270]; void *
0x18008cbef  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008cbf4  nop
0x18008cbf5  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x18008cbfa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008cbff  nop
0x18008cc00  xor     r14d, r14d
0x18008cc03  mov     [rsp+2E0h+hFile], r14
0x18008cc08  mov     eax, 0FEFFh
0x18008cc0d  mov     [rsp+2E0h+Buffer], ax
0x18008cc12  mov     [rsp+2E0h+NumberOfBytesWritten], r14d
0x18008cc17  mov     [rbp+1E0h+FileName], r14w
0x18008cc1c  test    rbx, rbx
0x18008cc1f  jnz     short loc_18008CC57
0x18008cc21  lea     rax, WPP_GLOBAL_Control
0x18008cc28  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cc2f  cmp     rcx, rax
0x18008cc32  jz      short loc_18008CC4D
0x18008cc34  test    byte ptr [rcx+1Ch], 1
0x18008cc38  jz      short loc_18008CC4D
0x18008cc3a  lea     edx, [rbx+3Ch]
0x18008cc3d  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008cc44  mov     rcx, [rcx+10h]
0x18008cc48  call    WPP_SF_
0x18008cc4d  mov     edi, 80070057h
0x18008cc52  jmp     loc_18008CEA5
0x18008cc57  lea     r8, [rbp+1E0h+var_250]
0x18008cc5b  mov     rdx, rbx
0x18008cc5e  mov     rcx, rsi
0x18008cc61  call    ?ExpandMultipleFileList@CDataCollection@@AEAAJPEB_WAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; CDataCollection::ExpandMultipleFileList(wchar_t const *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x18008cc66  test    eax, eax
0x18008cc68  js      short loc_18008CCBB
0x18008cc6a  mov     rbx, [rbp+1E0h+var_250]
0x18008cc6e  cmp     rbx, [rbp+1E0h+var_248]
0x18008cc72  jz      short loc_18008CCBB
0x18008cc74  mov     rcx, [rbx]; lpSrc
0x18008cc77  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x18008cc7c  test    al, al
0x18008cc7e  jz      short loc_18008CCB5
0x18008cc80  mov     rcx, [rsp+2E0h+var_270]
0x18008cc85  mov     [rsp+2E0h+var_268], rcx
0x18008cc8a  mov     [rcx], r14w
0x18008cc8e  lea     r8, [rsp+2E0h+var_270]
0x18008cc93  mov     rdx, [rbx]
0x18008cc96  call    ?GetFileVersionInformation@CDataCollection@@AEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CDataCollection::GetFileVersionInformation(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008cc9b  mov     r8, [rsp+2E0h+var_268]
0x18008cca0  mov     rdx, [rsp+2E0h+var_270]
0x18008cca5  sub     r8, rdx
0x18008cca8  sar     r8, 1
0x18008ccab  lea     rcx, [rsp+2E0h+lpBuffer]
0x18008ccb0  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18008ccb5  add     rbx, 20h ; ' '
0x18008ccb9  jmp     short loc_18008CC6E
0x18008ccbb  mov     rax, [rsp+2E0h+var_288]
0x18008ccc0  cmp     [rsp+2E0h+lpBuffer], rax
0x18008ccc5  jz      loc_18008CEA2
0x18008cccb  mov     [rsp+2E0h+var_2A8], r14d
0x18008ccd0  mov     [rsp+2E0h+var_2B0], 1
0x18008ccd8  mov     [rsp+2E0h+var_2B8], r14
0x18008ccdd  lea     r9, [rbp+1E0h+FileName]
0x18008cce1  lea     r8, aVersionTxt; ".version.txt"
0x18008cce8  xor     edx, edx
0x18008ccea  lea     rcx, [rsp+2E0h+hFile]
0x18008ccef  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18008ccf4  mov     edi, eax
0x18008ccf6  mov     rbx, [rsp+2E0h+hFile]
0x18008ccfb  test    eax, eax
0x18008ccfd  jns     short loc_18008CD3D
0x18008ccff  lea     rax, WPP_GLOBAL_Control
0x18008cd06  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd0d  cmp     rcx, rax
0x18008cd10  jz      loc_18008CE86
0x18008cd16  test    byte ptr [rcx+1Ch], 1
0x18008cd1a  jz      loc_18008CE86
0x18008cd20  mov     edx, 3Dh ; '='
0x18008cd25  mov     r9d, edi
0x18008cd28  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008cd2f  mov     rcx, [rcx+10h]
0x18008cd33  call    WPP_SF_d
0x18008cd38  jmp     loc_18008CE86
0x18008cd3d  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x18008cd42  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008cd47  mov     r8d, 2; nNumberOfBytesToWrite
0x18008cd4d  lea     rdx, [rsp+2E0h+Buffer]; lpBuffer
0x18008cd52  mov     rcx, rbx; hFile
0x18008cd55  call    cs:__imp_WriteFile
0x18008cd5b  test    eax, eax
0x18008cd5d  jz      loc_18008CE45
0x18008cd63  cmp     [rsp+2E0h+NumberOfBytesWritten], 2
0x18008cd68  jnz     loc_18008CE45
0x18008cd6e  mov     rdx, [rsp+2E0h+lpBuffer]; lpBuffer
0x18008cd73  mov     r8, [rsp+2E0h+var_288]
0x18008cd78  sub     r8, rdx
0x18008cd7b  sar     r8, 1
0x18008cd7e  add     r8d, r8d; nNumberOfBytesToWrite
0x18008cd81  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x18008cd86  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008cd8b  mov     rcx, rbx; hFile
0x18008cd8e  call    cs:__imp_WriteFile
0x18008cd94  test    eax, eax
0x18008cd96  jz      loc_18008CE25
0x18008cd9c  mov     rcx, [rsp+2E0h+var_288]
0x18008cda1  sub     rcx, [rsp+2E0h+lpBuffer]
0x18008cda6  sar     rcx, 1
0x18008cda9  add     rcx, rcx
0x18008cdac  mov     eax, [rsp+2E0h+NumberOfBytesWritten]
0x18008cdb0  cmp     rax, rcx
0x18008cdb3  jnz     short loc_18008CE25
0x18008cdb5  mov     [rsp+2E0h+var_2B8], r14; wchar_t *
0x18008cdba  lea     rax, aFileverTxt; "FileVer.txt"
0x18008cdc1  mov     [rsp+2E0h+lpOverlapped], rax; wchar_t *
0x18008cdc6  lea     r9, [rbp+1E0h+FileName]; wchar_t *
0x18008cdca  mov     edx, 5; enum _WER_FILE_TYPE
0x18008cdcf  lea     r8d, [rdx-2]; unsigned int
0x18008cdd3  mov     rcx, [rsi]; this
0x18008cdd6  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18008cddb  mov     edi, eax
0x18008cddd  test    eax, eax
0x18008cddf  jns     loc_18008CEA2
0x18008cde5  lea     rax, WPP_GLOBAL_Control
0x18008cdec  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cdf3  cmp     rcx, rax
0x18008cdf6  jz      loc_18008CE86
0x18008cdfc  test    byte ptr [rcx+1Ch], 1
0x18008ce00  jz      loc_18008CE86
0x18008ce06  mov     edx, 40h ; '@'
0x18008ce0b  mov     dword ptr [rsp+2E0h+lpOverlapped], edi
0x18008ce0f  lea     r9, [rbp+1E0h+FileName]
0x18008ce13  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008ce1a  mov     rcx, [rcx+10h]
0x18008ce1e  call    WPP_SF_SD
0x18008ce23  jmp     short loc_18008CE86
0x18008ce25  lea     rax, WPP_GLOBAL_Control
0x18008ce2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce33  cmp     rcx, rax
0x18008ce36  jz      short loc_18008CE73
0x18008ce38  test    byte ptr [rcx+1Ch], 1
0x18008ce3c  jz      short loc_18008CE73
0x18008ce3e  mov     edx, 3Fh ; '?'
0x18008ce43  jmp     short loc_18008CE63
0x18008ce45  lea     rax, WPP_GLOBAL_Control
0x18008ce4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce53  cmp     rcx, rax
0x18008ce56  jz      short loc_18008CE73
0x18008ce58  test    byte ptr [rcx+1Ch], 1
0x18008ce5c  jz      short loc_18008CE73
0x18008ce5e  mov     edx, 3Eh ; '>'
0x18008ce63  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008ce6a  mov     rcx, [rcx+10h]
0x18008ce6e  call    WPP_SF_
0x18008ce73  call    cs:__imp_GetLastError
0x18008ce79  mov     ecx, eax; unsigned int
0x18008ce7b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008ce80  mov     edi, eax
0x18008ce82  test    eax, eax
0x18008ce84  jns     short loc_18008CEA5
0x18008ce86  inc     rbx
0x18008ce89  cmp     rbx, 1
0x18008ce8d  jbe     short loc_18008CEA5
0x18008ce8f  cmp     [rbp+1E0h+FileName], r14w
0x18008ce94  jz      short loc_18008CEA5
0x18008ce96  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x18008ce9a  call    cs:__imp_DeleteFileW
0x18008cea0  jmp     short loc_18008CEA5
0x18008cea2  mov     edi, r14d
0x18008cea5  lea     rcx, [rsp+2E0h+hFile]
0x18008ceaa  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008ceaf  nop
0x18008ceb0  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x18008ceb5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008ceba  nop
0x18008cebb  lea     rcx, [rsp+2E0h+var_270]; void *
0x18008cec0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008cec5  nop
0x18008cec6  lea     rcx, [rbp+1E0h+var_250]
0x18008ceca  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x18008cecf  mov     eax, edi
0x18008ced1  mov     rcx, [rbp+1E0h+var_20]
0x18008ced8  xor     rcx, rsp; StackCookie
0x18008cedb  call    __security_check_cookie
0x18008cee0  lea     r11, [rsp+2E0h+var_10]
0x18008cee8  mov     rbx, [r11+30h]
0x18008ceec  mov     rsi, [r11+38h]
0x18008cef0  mov     rsp, r11
0x18008cef3  pop     r14
0x18008cef5  pop     rdi
0x18008cef6  pop     rbp
0x18008cef7  retn
```
