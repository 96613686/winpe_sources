# CDataCollection::AddDataCollectionFailure(wchar_t const *)

- ea: `0x180035ce0`
- end: `0x1800360c7`
- name: `?AddDataCollectionFailure@CDataCollection@@QEAAJPEB_W@Z`
- size: `999`
- prototype: `int(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x18001b280`
- `0x180035544`
- `0x180035738`
- `0x1800360d0`
- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc10`
- `0x18000dad0`
- `0x180014720`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001bfb0`
- `0x18001fe24`
- `0x180026498`
- `0x18002c220`
- `0x180035ce0`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036076`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035e99`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035fc2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035ff6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035e99`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035fc2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035ff6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035e06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035e06`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataCollection::AddDataCollectionFailure(CReport **this, const wchar_t *a2)
{
  int FileByIndex; // edi
  unsigned int i; // r11d
  unsigned int v6; // r11d
  struct CReportFile *v7; // rsi
  int v8; // r11d
  HANDLE FileW; // rax
  HANDLE v10; // rbx
  __int64 v11; // r8
  DWORD LastError; // eax
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD v16; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  struct CReportFile *v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[40]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v23[264]; // [rsp+80h] [rbp-80h] BYREF

  hFile = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v22);
  Buffer = -257;
  NumberOfBytesWritten = 0;
  v21 = 0;
  v23[0] = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    FileByIndex = -2147024809;
    goto LABEL_44;
  }
  for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)*this + 728) - *((_QWORD *)*this + 727)) >> 3); i = v8 + 1 )
  {
    FileByIndex = CReport::GetFileByIndex(*this, i, &v21);
    if ( FileByIndex < 0 || (v7 = v21) == 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          v6,
          FileByIndex);
      goto LABEL_44;
    }
    if ( (unsigned __int8)utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            (char *)v21 + 80,
                            L"WERDataCollectionStatus.txt") )
    {
      FileW = CreateFileW(*((LPCWSTR *)v7 + 14), 4u, 1u, 0, 3u, 0x80u, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
      v10 = hFile;
      if ( (unsigned __int64)hFile + 1 <= 1 )
      {
        LastError = GetLastError();
        FileByIndex = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            *((_QWORD *)v7 + 14),
            FileByIndex);
        goto LABEL_44;
      }
      FileByIndex = UtilVerifyFilePath(*((const wchar_t **)v7 + 14), hFile);
      if ( FileByIndex < 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            (unsigned int)FileByIndex);
        goto LABEL_44;
      }
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      WriteFile(v10, a2, 2 * v11, &NumberOfBytesWritten, 0);
LABEL_20:
      FileByIndex = 0;
      goto LABEL_44;
    }
  }
  FileByIndex = UtilGetTempFile(&hFile, 0, L".WERDataCollectionStatus.txt", v23);
  if ( FileByIndex < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v14 = 108;
    goto LABEL_31;
  }
  if ( WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    WriteFile(hFile, a2, 2 * v15, &NumberOfBytesWritten, 0);
    FileByIndex = CReport::AddFile(*this, WerFileTypeOther, 3u, v23, L"WERDataCollectionStatus.txt", 0);
    if ( FileByIndex >= 0 )
      goto LABEL_20;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v14 = 110;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)FileByIndex);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
  v16 = GetLastError();
  FileByIndex = ERROR_HR_FROM_WIN32(v16);
LABEL_44:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v22);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)FileByIndex;
}

```

## disassembly

```asm
0x180035ce0  mov     [rsp-8+arg_10], rbx
0x180035ce5  mov     [rsp-8+arg_18], rsi
0x180035cea  push    rbp
0x180035ceb  push    rdi
0x180035cec  push    r12
0x180035cee  push    r14
0x180035cf0  push    r15
0x180035cf2  lea     rbp, [rsp-1A0h]
0x180035cfa  sub     rsp, 2A0h
0x180035d01  mov     rax, cs:__security_cookie
0x180035d08  xor     rax, rsp
0x180035d0b  mov     [rbp+1C0h+var_30], rax
0x180035d12  mov     r14, rdx
0x180035d15  mov     rbx, rcx
0x180035d18  xor     r15d, r15d
0x180035d1b  mov     [rsp+2C0h+hFile], r15
0x180035d20  lea     rcx, [rsp+2C0h+var_268]; void *
0x180035d25  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180035d2a  nop
0x180035d2b  mov     eax, 0FEFFh
0x180035d30  mov     [rsp+2C0h+Buffer], ax
0x180035d35  mov     [rsp+2C0h+NumberOfBytesWritten], r15d
0x180035d3a  mov     [rsp+2C0h+var_270], r15
0x180035d3f  mov     [rbp+1C0h+var_240], r15w
0x180035d44  test    r14, r14
0x180035d47  jnz     short loc_180035D80
0x180035d49  lea     rax, WPP_GLOBAL_Control
0x180035d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d57  cmp     rcx, rax
0x180035d5a  jz      short loc_180035D76
0x180035d5c  test    byte ptr [rcx+1Ch], 1
0x180035d60  jz      short loc_180035D76
0x180035d62  lea     edx, [r15+68h]
0x180035d66  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180035d6d  mov     rcx, [rcx+10h]
0x180035d71  call    WPP_SF_
0x180035d76  mov     edi, 80070057h
0x180035d7b  jmp     loc_180036085
0x180035d80  mov     r11d, r15d
0x180035d83  lea     r12, aWerdatacollect_0; "WERDataCollectionStatus.txt"
0x180035d8a  mov     rcx, [rbx]; this
0x180035d8d  mov     rax, [rcx+16C0h]
0x180035d94  sub     rax, [rcx+16B8h]
0x180035d9b  sar     rax, 3
0x180035d9f  cmp     r11d, eax
0x180035da2  jnb     loc_180035F3B
0x180035da8  lea     r8, [rsp+2C0h+var_270]; struct CReportFile **
0x180035dad  mov     edx, r11d; unsigned int
0x180035db0  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x180035db5  mov     edi, eax
0x180035db7  test    eax, eax
0x180035db9  js      loc_180035EF9
0x180035dbf  mov     rsi, [rsp+2C0h+var_270]
0x180035dc4  test    rsi, rsi
0x180035dc7  jz      loc_180035EF9
0x180035dcd  lea     rcx, [rsi+50h]
0x180035dd1  mov     rdx, r12
0x180035dd4  call    ??$?8_WU?$char_traits@_W@utl@@V?$allocator@_W@1@@utl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@PEB_W@Z; utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *)
0x180035dd9  test    al, al
0x180035ddb  jnz     short loc_180035DE2
0x180035ddd  inc     r11d
0x180035de0  jmp     short loc_180035D8A
0x180035de2  mov     [rsp+2C0h+hTemplateFile], r15; hTemplateFile
0x180035de7  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180035def  mov     [rsp+2C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180035df7  xor     r9d, r9d; lpSecurityAttributes
0x180035dfa  lea     edx, [r9+4]; dwDesiredAccess
0x180035dfe  lea     r8d, [r9+1]; dwShareMode
0x180035e02  mov     rcx, [rsi+70h]; lpFileName
0x180035e06  call    cs:__imp_CreateFileW
0x180035e0c  mov     rdx, rax
0x180035e0f  lea     rcx, [rsp+2C0h+hFile]
0x180035e14  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180035e19  mov     rbx, [rsp+2C0h+hFile]
0x180035e1e  lea     rax, [rbx+1]
0x180035e22  cmp     rax, 1
0x180035e26  jbe     short loc_180035EA7
0x180035e28  mov     rdx, rbx; void *
0x180035e2b  mov     rcx, [rsi+70h]; wchar_t *
0x180035e2f  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180035e34  mov     edi, eax
0x180035e36  test    eax, eax
0x180035e38  jns     short loc_180035E78
0x180035e3a  lea     rax, WPP_GLOBAL_Control
0x180035e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e48  cmp     rcx, rax
0x180035e4b  jz      loc_180036085
0x180035e51  test    byte ptr [rcx+1Ch], 1
0x180035e55  jz      loc_180036085
0x180035e5b  mov     edx, 6Bh ; 'k'
0x180035e60  mov     r9d, edi
0x180035e63  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180035e6a  mov     rcx, [rcx+10h]
0x180035e6e  call    WPP_SF_d
0x180035e73  jmp     loc_180036085
0x180035e78  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035e7c  inc     r8
0x180035e7f  cmp     [r14+r8*2], r15w
0x180035e84  jnz     short loc_180035E7C
0x180035e86  add     r8d, r8d; nNumberOfBytesToWrite
0x180035e89  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180035e8e  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180035e93  mov     rdx, r14; lpBuffer
0x180035e96  mov     rcx, rbx; hFile
0x180035e99  call    cs:__imp_WriteFile
0x180035e9f  mov     edi, r15d
0x180035ea2  jmp     loc_180036085
0x180035ea7  call    cs:__imp_GetLastError
0x180035ead  mov     ecx, eax; unsigned int
0x180035eaf  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180035eb4  mov     edi, eax
0x180035eb6  lea     rax, WPP_GLOBAL_Control
0x180035ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ec4  cmp     rcx, rax
0x180035ec7  jz      loc_180036085
0x180035ecd  test    byte ptr [rcx+1Ch], 1
0x180035ed1  jz      loc_180036085
0x180035ed7  mov     edx, 6Ah ; 'j'
0x180035edc  mov     [rsp+2C0h+dwCreationDisposition], edi
0x180035ee0  mov     r9, [rsi+70h]
0x180035ee4  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180035eeb  mov     rcx, [rcx+10h]
0x180035eef  call    WPP_SF_SD
0x180035ef4  jmp     loc_180036085
0x180035ef9  lea     rax, WPP_GLOBAL_Control
0x180035f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f07  cmp     rcx, rax
0x180035f0a  jz      loc_180036085
0x180035f10  test    byte ptr [rcx+1Ch], 1
0x180035f14  jz      loc_180036085
0x180035f1a  mov     edx, 69h ; 'i'
0x180035f1f  mov     [rsp+2C0h+dwCreationDisposition], edi
0x180035f23  mov     r9d, r11d
0x180035f26  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180035f2d  mov     rcx, [rcx+10h]
0x180035f31  call    WPP_SF_Dd
0x180035f36  jmp     loc_180036085
0x180035f3b  mov     [rsp+2C0h+var_288], r15d
0x180035f40  mov     dword ptr [rsp+2C0h+hTemplateFile], 1
0x180035f48  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15
0x180035f4d  lea     r9, [rbp+1C0h+var_240]
0x180035f51  lea     r8, aWerdatacollect; ".WERDataCollectionStatus.txt"
0x180035f58  xor     edx, edx
0x180035f5a  lea     rcx, [rsp+2C0h+hFile]
0x180035f5f  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180035f64  mov     edi, eax
0x180035f66  test    eax, eax
0x180035f68  jns     short loc_180035FA8
0x180035f6a  lea     rax, WPP_GLOBAL_Control
0x180035f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f78  cmp     rcx, rax
0x180035f7b  jz      loc_180036085
0x180035f81  test    byte ptr [rcx+1Ch], 1
0x180035f85  jz      loc_180036085
0x180035f8b  mov     edx, 6Ch ; 'l'
0x180035f90  mov     r9d, edi
0x180035f93  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180035f9a  mov     rcx, [rcx+10h]
0x180035f9e  call    WPP_SF_d
0x180035fa3  jmp     loc_180036085
0x180035fa8  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180035fad  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180035fb2  mov     r8d, 2; nNumberOfBytesToWrite
0x180035fb8  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x180035fbd  mov     rcx, [rsp+2C0h+hFile]; hFile
0x180035fc2  call    cs:__imp_WriteFile
0x180035fc8  test    eax, eax
0x180035fca  jz      short loc_180036048
0x180035fcc  cmp     [rsp+2C0h+NumberOfBytesWritten], 2
0x180035fd1  jnz     short loc_180036048
0x180035fd3  or      r8, 0FFFFFFFFFFFFFFFFh
0x180035fd7  inc     r8
0x180035fda  cmp     [r14+r8*2], r15w
0x180035fdf  jnz     short loc_180035FD7
0x180035fe1  add     r8d, r8d; nNumberOfBytesToWrite
0x180035fe4  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180035fe9  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180035fee  mov     rdx, r14; lpBuffer
0x180035ff1  mov     rcx, [rsp+2C0h+hFile]; hFile
0x180035ff6  call    cs:__imp_WriteFile
0x180035ffc  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15; wchar_t *
0x180036001  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; wchar_t *
0x180036006  lea     r9, [rbp+1C0h+var_240]; wchar_t *
0x18003600a  mov     edx, 5; enum _WER_FILE_TYPE
0x18003600f  lea     r8d, [rdx-2]; unsigned int
0x180036013  mov     rcx, [rbx]; this
0x180036016  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18003601b  mov     edi, eax
0x18003601d  test    eax, eax
0x18003601f  jns     loc_180035E9F
0x180036025  lea     rax, WPP_GLOBAL_Control
0x18003602c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036033  cmp     rcx, rax
0x180036036  jz      short loc_180036085
0x180036038  test    byte ptr [rcx+1Ch], 1
0x18003603c  jz      short loc_180036085
0x18003603e  mov     edx, 6Eh ; 'n'
0x180036043  jmp     loc_180035F90
0x180036048  lea     rax, WPP_GLOBAL_Control
0x18003604f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036056  cmp     rcx, rax
0x180036059  jz      short loc_180036076
0x18003605b  test    byte ptr [rcx+1Ch], 1
0x18003605f  jz      short loc_180036076
0x180036061  mov     edx, 6Dh ; 'm'
0x180036066  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18003606d  mov     rcx, [rcx+10h]
0x180036071  call    WPP_SF_
0x180036076  call    cs:__imp_GetLastError
0x18003607c  mov     ecx, eax; unsigned int
0x18003607e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180036083  mov     edi, eax
0x180036085  lea     rcx, [rsp+2C0h+var_268]; void *
0x18003608a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003608f  nop
0x180036090  lea     rcx, [rsp+2C0h+hFile]
0x180036095  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003609a  mov     eax, edi
0x18003609c  mov     rcx, [rbp+1C0h+var_30]
0x1800360a3  xor     rcx, rsp; StackCookie
0x1800360a6  call    __security_check_cookie
0x1800360ab  lea     r11, [rsp+2C0h+var_20]
0x1800360b3  mov     rbx, [r11+40h]
0x1800360b7  mov     rsi, [r11+48h]
0x1800360bb  mov     rsp, r11
0x1800360be  pop     r15
0x1800360c0  pop     r14
0x1800360c2  pop     r12
0x1800360c4  pop     rdi
0x1800360c5  pop     rbp
0x1800360c6  retn
```
