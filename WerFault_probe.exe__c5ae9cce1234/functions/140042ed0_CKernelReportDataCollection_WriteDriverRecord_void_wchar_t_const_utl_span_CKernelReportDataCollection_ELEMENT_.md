# CKernelReportDataCollection::WriteDriverRecord(void *,wchar_t const *,utl::span<CKernelReportDataCollection::ELEMENT_VALUE const,-1>,wchar_t const *,wchar_t const *,_GUID,wchar_t const *,_FILETIME *)

- ea: `0x140042ed0`
- end: `0x1400437e5`
- name: `?WriteDriverRecord@CKernelReportDataCollection@@AEAAJPEAXPEB_WV?$span@$$CBUELEMENT_VALUE@CKernelReportDataCollection@@$0?0@utl@@11U_GUID@@1PEAU_FILETIME@@@Z`
- size: `2325`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14003f768`
- `0x140040fc8`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400041bc`
- `0x140004230`
- `0x140005430`
- `0x14000b540`
- `0x14000ea94`
- `0x14000fb60`
- `0x140034d9c`
- `0x140038fd0`
- `0x140042bc4`
- `0x140042ed0`
- `0x140043c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043024`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x14004301a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x14004301a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043072`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400430b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043149`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043174`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400431ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400431ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004320a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004326b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004328b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400432ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433ff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004341f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043458`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004347b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434f8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004353e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043572`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043592`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400435ba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400435ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004360a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400436eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043711`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043072`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400430b0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043149`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043174`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400431ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400431ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004320a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004326b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004328b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400432ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433a6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433c6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400433ff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004341f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043458`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004347b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400434f8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004353e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043572`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043592`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400435ba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400435ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004360a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400436eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140043711`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400430be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400431ea`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400430be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400431ea`

## string_xrefs

- `0x1400432e7`: `CKernelReportDataCollection::WriteDriverRecord`
- `0x140043358`: `CKernelReportDataCollection::WriteDriverRecord`
- `0x14004373b`: `CKernelReportDataCollection::WriteDriverRecord`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CKernelReportDataCollection::WriteDriverRecord(
        __int64 a1,
        void *a2,
        const char *a3,
        __int64 a4,
        wchar_t *a5,
        wchar_t *a6,
        __int64 a7,
        wchar_t *a8,
        FILETIME *lpFileTime)
{
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // rbx
  signed int LastError; // eax
  signed int v17; // ebx
  const char *v18; // rax
  __int64 v19; // rdx
  CKernelReportDataCollection *v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // r8
  CKernelReportDataCollection *v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // r8
  CKernelReportDataCollection *v26; // rcx
  unsigned int v27; // eax
  CKernelReportDataCollection *v28; // rcx
  unsigned int v29; // eax
  CKernelReportDataCollection *v30; // rcx
  unsigned int v31; // eax
  CKernelReportDataCollection *v32; // rcx
  CKernelReportDataCollection *v33; // rcx
  unsigned int v34; // eax
  CKernelReportDataCollection *v35; // rcx
  unsigned int v36; // eax
  CKernelReportDataCollection *v37; // rcx
  unsigned int v38; // eax
  _QWORD *v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  wil::details *lpOverlapped; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlappedb; // [rsp+20h] [rbp-E0h]
  const char *lpOverlappedc; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlappedd; // [rsp+20h] [rbp-E0h]
  const char *lpOverlappede; // [rsp+20h] [rbp-E0h]
  int v50[2]; // [rsp+28h] [rbp-D8h]
  int v51[2]; // [rsp+28h] [rbp-D8h]
  char *v52; // [rsp+30h] [rbp-D0h]
  char *v53; // [rsp+30h] [rbp-D0h]
  char *v54; // [rsp+30h] [rbp-D0h]
  DWORD NumberOfBytesWritten[4]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v56; // [rsp+60h] [rbp-A0h] BYREF
  void *v57; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v58; // [rsp+78h] [rbp-88h]
  _WORD v59[8]; // [rsp+80h] [rbp-80h] BYREF
  void *v60; // [rsp+90h] [rbp-70h] BYREF
  _WORD *v61; // [rsp+98h] [rbp-68h]
  _WORD v62[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v63[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPCVOID lpBuffer; // [rsp+C0h] [rbp-40h] BYREF
  char *v65; // [rsp+C8h] [rbp-38h]
  _WORD v66[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+F0h] [rbp-10h]
  __int128 v69; // [rsp+100h] [rbp+0h]
  int v70; // [rsp+110h] [rbp+10h]
  wchar_t *v71[8]; // [rsp+120h] [rbp+20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+160h] [rbp+60h] BYREF
  _OWORD FileInformation[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v74; // [rsp+190h] [rbp+90h]
  wchar_t v75[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t v76[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t Buffer[1032]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+AB8h] [rbp+9B8h]

  v63[0] = a4;
  *(_QWORD *)&v56.Data1 = a7;
  memset(FileInformation, 0, sizeof(FileInformation));
  v74 = 0;
  SystemTime = 0;
  NumberOfBytesWritten[0] = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v60 = v62;
  v61 = v62;
  v62[0] = 0;
  v57 = v59;
  v58 = v59;
  v59[0] = 0;
  lpBuffer = v66;
  v65 = (char *)v66;
  v66[0] = 0;
  `eh vector constructor iterator'(
    v71,
    0x20u,
    2u,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,
    (void (*)(void *))KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT);
  if ( !a3 )
    goto LABEL_48;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&a3[2 * v11] );
  v12 = (const wchar_t *)&a3[2 * v11];
  while ( 1 )
  {
    v15 = v12;
    if ( v12 <= (const wchar_t *)a3 )
      break;
    v13 = *--v12;
    LOWORD(v13) = v13 - 47;
    if ( (unsigned __int16)v13 <= 0x2Du )
    {
      v14 = 0x200000000801LL;
      if ( _bittest64(&v14, v13) )
        break;
    }
  }
  if ( !v15 )
  {
LABEL_48:
    v17 = -2147024809;
    v18 = "Invalid file '%ws'";
    v19 = 657;
LABEL_49:
    LODWORD(lpOverlapped) = v17;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
      "CKernelReportDataCollection::WriteDriverRecord",
      lpOverlapped,
      (int)v18,
      a3);
    goto LABEL_50;
  }
  if ( !GetFileAttributesExW((LPCWSTR)a3, GetFileExInfoStandard, FileInformation) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( v17 >= 0 )
      v17 = -2147467259;
    v18 = "GetFileAttributesEx failed for %ws";
    v19 = 666;
    goto LABEL_49;
  }
  WriteFile(a2, L"\t<DRIVER>\r\n\t\t<FILENAME>", 0x2Eu, NumberOfBytesWritten, 0);
  Buffer[0] = 0;
  v21 = CKernelReportDataCollection::XMLEncodeString(v20, v15, Buffer, 0x402u);
  WriteFile(a2, Buffer, 2 * v21, NumberOfBytesWritten, 0);
  FileTimeToSystemTime((const FILETIME *)((char *)FileInformation + 4), &SystemTime);
  LODWORD(lpOverlappeda) = SystemTime.wMonth;
  if ( (int)StringCchPrintfW(
              Buffer,
              0x402u,
              L"</FILENAME>\r\n"
               "\t\t<FILESIZE>%u</FILESIZE>\r\n"
               "\t\t<CREATIONDATE>%02d-%02d-%04d %02d:%02d:%02d</CREATIONDATE>",
              v74,
              lpOverlappeda,
              SystemTime.wDay,
              SystemTime.wYear,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              *(_QWORD *)NumberOfBytesWritten) >= 0 )
  {
    v22 = -1;
    do
      ++v22;
    while ( Buffer[v22] );
    WriteFile(a2, Buffer, 2 * v22, NumberOfBytesWritten, 0);
  }
  if ( a8 && *a8 )
  {
    WriteFile(a2, L"\r\n\t\t<INFNAME>", 0x1Au, NumberOfBytesWritten, 0);
    v24 = CKernelReportDataCollection::XMLEncodeString(v23, a8, Buffer, 0x402u);
    WriteFile(a2, Buffer, 2 * v24, NumberOfBytesWritten, 0);
    WriteFile(a2, L"</INFNAME>", 0x14u, NumberOfBytesWritten, 0);
  }
  if ( lpFileTime )
  {
    FileTimeToSystemTime(lpFileTime, &SystemTime);
    WriteFile(a2, L"\r\n\t\t<INFDATE>", 0x1Au, NumberOfBytesWritten, 0);
    v50[0] = SystemTime.wYear;
    LODWORD(lpOverlappedb) = SystemTime.wDay;
    if ( (int)StringCchPrintfW(Buffer, 0x402u, L"%02d-%02d-%04d", SystemTime.wMonth, lpOverlappedb, *(_QWORD *)v50) >= 0 )
    {
      v25 = -1;
      do
        ++v25;
      while ( Buffer[v25] );
      WriteFile(a2, Buffer, 2 * v25, NumberOfBytesWritten, 0);
    }
    WriteFile(a2, L"</INFDATE>", 0x14u, NumberOfBytesWritten, 0);
  }
  WriteFile(a2, L"\r\n\t\t<VERSION>", 0x1Au, NumberOfBytesWritten, 0);
  LODWORD(lpOverlappedc) = UtilGetFileInfo((LPCWSTR)a3, 2);
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x2EA,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::WriteDriverRecord",
    lpOverlappedc,
    (int)"UtilGetFileInfo failed",
    v52);
  v75[0] = 0;
  LODWORD(v53) = WORD6(v67);
  v51[0] = HIWORD(HIDWORD(v67));
  LODWORD(lpOverlappedd) = WORD4(v67);
  LODWORD(lpOverlappede) = StringCchPrintfW(
                             v75,
                             0x20u,
                             L"%u.%u.%u.%u",
                             HIWORD(DWORD2(v67)),
                             lpOverlappedd,
                             *(_QWORD *)v51,
                             v53);
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x2F7,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::WriteDriverRecord",
    lpOverlappede,
    (int)"StringCchPrintf failed",
    v54);
  Buffer[0] = 0;
  v27 = CKernelReportDataCollection::XMLEncodeString(v26, v75, Buffer, 0x402u);
  WriteFile(a2, Buffer, 2 * v27, NumberOfBytesWritten, 0);
  WriteFile(a2, L"</VERSION>\r\n\t\t<MANUFACTURER>", 0x38u, NumberOfBytesWritten, 0);
  Buffer[0] = 0;
  v29 = CKernelReportDataCollection::XMLEncodeString(v28, v71[4], Buffer, 0x402u);
  WriteFile(a2, Buffer, 2 * v29, NumberOfBytesWritten, 0);
  WriteFile(a2, L"</MANUFACTURER>\r\n\t\t<PRODUCTNAME>", 0x40u, NumberOfBytesWritten, 0);
  Buffer[0] = 0;
  v31 = CKernelReportDataCollection::XMLEncodeString(v30, v71[0], Buffer, 0x402u);
  WriteFile(a2, Buffer, 2 * v31, NumberOfBytesWritten, 0);
  WriteFile(a2, L"</PRODUCTNAME>", 0x1Cu, NumberOfBytesWritten, 0);
  if ( a5 && *a5 )
  {
    WriteFile(a2, L"\r\n\t\t<SUBMISSIONID>", 0x24u, NumberOfBytesWritten, 0);
    v34 = CKernelReportDataCollection::XMLEncodeString(v33, a5, Buffer, 0x402u);
    WriteFile(a2, Buffer, 2 * v34, NumberOfBytesWritten, 0);
    WriteFile(a2, L"</SUBMISSIONID>", 0x1Eu, NumberOfBytesWritten, 0);
  }
  v56 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
  if ( CKernelReportDataCollection::GuidToString(v32, v76, 0x40u, &v56) >= 0 )
  {
    WriteFile(a2, L"\r\n\t\t<CLASSGUID>", 0x1Eu, NumberOfBytesWritten, 0);
    v36 = CKernelReportDataCollection::XMLEncodeString(v35, v76, Buffer, 0x402u);
    WriteFile(a2, Buffer, 2 * v36, NumberOfBytesWritten, 0);
    WriteFile(a2, L"</CLASSGUID>", 0x18u, NumberOfBytesWritten, 0);
  }
  if ( a6 && *a6 )
  {
    WriteFile(a2, L"\r\n\t\t<FLIGHTID>", 0x1Cu, NumberOfBytesWritten, 0);
    v38 = CKernelReportDataCollection::XMLEncodeString(v37, a6, Buffer, 0x402u);
    WriteFile(a2, Buffer, 2 * v38, NumberOfBytesWritten, 0);
    WriteFile(a2, L"</FLIGHTID>", 0x16u, NumberOfBytesWritten, 0);
  }
  v39 = *(_QWORD **)v63[0];
  v40 = *(_QWORD *)v63[0] + 16LL * *(_QWORD *)(v63[0] + 8LL);
  while ( v39 != (_QWORD *)v40 )
  {
    if ( *v39 )
    {
      if ( v39[1] )
      {
        v61 = v60;
        *(_WORD *)v60 = 0;
        v41 = -1;
        do
          ++v41;
        while ( *(_WORD *)(*v39 + 2 * v41) );
        v63[0] = *v39;
        v63[1] = v41;
        AppendXmlEncodedString(&v60, v63);
        v58 = v57;
        *(_WORD *)v57 = 0;
        v42 = -1;
        do
          ++v42;
        while ( *(_WORD *)(v39[1] + 2 * v42) );
        *(_QWORD *)&v56.Data1 = v39[1];
        *(_QWORD *)v56.Data4 = v42;
        AppendXmlEncodedString(&v57, &v56);
        if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    &lpBuffer,
                    L"\r\n\t\t<%ls>%ls</%ls>",
                    v60,
                    v57,
                    v60) >= 0 )
          WriteFile(a2, lpBuffer, 2 * ((v65 - (_BYTE *)lpBuffer) >> 1), NumberOfBytesWritten, 0);
      }
    }
    v39 += 2;
  }
  WriteFile(a2, L"\r\n\t</DRIVER>\r\n", 0x1Cu, NumberOfBytesWritten, 0);
  v17 = 0;
LABEL_50:
  `eh vector destructor iterator'(v71, 0x20u, 2u, (void (*)(void *))KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT);
  if ( lpBuffer != v66 )
    operator delete((void *)lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  if ( v57 != v59 )
    operator delete(v57, (const struct std::nothrow_t *)&std::nothrow);
  if ( v60 != v62 )
    operator delete(v60, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140042ed0  mov     [rsp-8+arg_0], rbx
0x140042ed5  push    rbp
0x140042ed6  push    rsi
0x140042ed7  push    rdi
0x140042ed8  push    r12
0x140042eda  push    r13
0x140042edc  push    r14
0x140042ede  push    r15
0x140042ee0  lea     rbp, [rsp-980h]
0x140042ee8  sub     rsp, 0A80h
0x140042eef  mov     rax, cs:__security_cookie
0x140042ef6  xor     rax, rsp
0x140042ef9  mov     [rbp+9B0h+var_40], rax
0x140042f00  mov     [rbp+9B0h+var_A00], r9
0x140042f04  mov     rdi, r8
0x140042f07  mov     rsi, rdx
0x140042f0a  mov     r13, [rbp+9B0h+arg_20]
0x140042f11  mov     r15, [rbp+9B0h+arg_28]
0x140042f18  mov     rax, [rbp+9B0h+arg_30]
0x140042f1f  mov     qword ptr [rsp+0AB0h+var_A50.Data1], rax
0x140042f24  mov     r14, [rbp+9B0h+arg_38]
0x140042f2b  mov     r12, [rbp+9B0h+lpFileTime]
0x140042f32  xorps   xmm0, xmm0
0x140042f35  xor     eax, eax
0x140042f37  movups  [rbp+9B0h+FileInformation], xmm0
0x140042f3b  movups  [rbp+9B0h+var_930], xmm0
0x140042f42  mov     [rbp+9B0h+var_920], eax
0x140042f48  movups  xmmword ptr [rbp+9B0h+SystemTime.wYear], xmm0
0x140042f4c  xor     ebx, ebx
0x140042f4e  mov     [rsp+0AB0h+NumberOfBytesWritten], ebx
0x140042f52  movups  [rbp+9B0h+var_9D0], xmm0
0x140042f56  movups  [rbp+9B0h+var_9C0], xmm0
0x140042f5a  movups  [rbp+9B0h+var_9B0], xmm0
0x140042f5e  mov     [rbp+9B0h+var_9A0], eax
0x140042f61  lea     rax, [rbp+9B0h+var_A10]
0x140042f65  mov     [rbp+9B0h+var_A20], rax
0x140042f69  lea     rax, [rbp+9B0h+var_A10]
0x140042f6d  mov     [rbp+9B0h+var_A18], rax
0x140042f71  mov     [rbp+9B0h+var_A10], bx
0x140042f75  lea     rax, [rbp+9B0h+var_A30]
0x140042f79  mov     [rsp+0AB0h+var_A40], rax
0x140042f7e  lea     rax, [rbp+9B0h+var_A30]
0x140042f82  mov     [rsp+0AB0h+var_A38], rax
0x140042f87  mov     [rbp+9B0h+var_A30], bx
0x140042f8b  lea     rax, [rbp+9B0h+var_9E0]
0x140042f8f  mov     [rbp+9B0h+lpBuffer], rax
0x140042f93  lea     rax, [rbp+9B0h+var_9E0]
0x140042f97  mov     [rbp+9B0h+var_9E8], rax
0x140042f9b  mov     [rbp+9B0h+var_9E0], bx
0x140042f9f  lea     rax, ??1KERNEL_QUEUED_REPORT@@QEAA@XZ; KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT(void)
0x140042fa6  mov     [rsp+0AB0h+lpOverlapped], rax; void (*)(void *)
0x140042fab  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x140042fb2  lea     edx, [rbx+20h]; unsigned __int64
0x140042fb5  lea     r8d, [rbx+2]; unsigned __int64
0x140042fb9  lea     rcx, [rbp+9B0h+var_990]; void *
0x140042fbd  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140042fc2  nop
0x140042fc3  test    rdi, rdi
0x140042fc6  jz      loc_14004371C
0x140042fcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140042fd0  inc     rax
0x140042fd3  cmp     [rdi+rax*2], bx
0x140042fd7  jnz     short loc_140042FD0
0x140042fd9  lea     rcx, [rdi+rax*2]
0x140042fdd  jmp     short loc_140043000
0x140042fdf  sub     rcx, 2
0x140042fe3  movzx   eax, word ptr [rcx]
0x140042fe6  sub     ax, 2Fh ; '/'
0x140042fea  cmp     ax, 2Dh ; '-'
0x140042fee  ja      short loc_140043000
0x140042ff0  mov     rdx, 200000000801h
0x140042ffa  bt      rdx, rax
0x140042ffe  jb      short loc_140043008
0x140043000  mov     rbx, rcx
0x140043003  cmp     rcx, rdi
0x140043006  ja      short loc_140042FDF
0x140043008  test    rbx, rbx
0x14004300b  jz      loc_14004371C
0x140043011  lea     r8, [rbp+9B0h+FileInformation]; lpFileInformation
0x140043015  xor     edx, edx; fInfoLevelId
0x140043017  mov     rcx, rdi; lpFileName
0x14004301a  call    cs:__imp_GetFileAttributesExW
0x140043020  test    eax, eax
0x140043022  jnz     short loc_140043054
0x140043024  call    cs:__imp_GetLastError
0x14004302a  mov     ebx, eax
0x14004302c  test    eax, eax
0x14004302e  jle     short loc_140043039
0x140043030  movzx   ebx, ax
0x140043033  or      ebx, 80070000h
0x140043039  mov     eax, 80004005h
0x14004303e  test    ebx, ebx
0x140043040  cmovns  ebx, eax
0x140043043  lea     rax, aGetfileattribu; "GetFileAttributesEx failed for %ws"
0x14004304a  mov     edx, 29Ah
0x14004304f  jmp     loc_14004372D
0x140043054  mov     [rsp+0AB0h+lpOverlapped], 0; lpOverlapped
0x14004305d  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140043062  mov     r8d, 2Eh ; '.'; nNumberOfBytesToWrite
0x140043068  lea     rdx, aDriverFilename; "\t<DRIVER>\r\n\t\t<FILENAME>"
0x14004306f  mov     rcx, rsi; hFile
0x140043072  call    cs:__imp_WriteFile
0x140043078  xor     eax, eax
0x14004307a  mov     [rbp+9B0h+Buffer], ax
0x140043081  mov     r9d, 402h; unsigned int
0x140043087  lea     r8, [rbp+9B0h+Buffer]; wchar_t *
0x14004308e  mov     rdx, rbx; wchar_t *
0x140043091  call    ?XMLEncodeString@CKernelReportDataCollection@@AEAAKPEB_WPEA_WK@Z; CKernelReportDataCollection::XMLEncodeString(wchar_t const *,wchar_t *,ulong)
0x140043096  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x14004309a  xor     ebx, ebx
0x14004309c  mov     [rsp+0AB0h+lpOverlapped], rbx; lpOverlapped
0x1400430a1  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400430a6  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x1400430ad  mov     rcx, rsi; hFile
0x1400430b0  call    cs:__imp_WriteFile
0x1400430b6  lea     rdx, [rbp+9B0h+SystemTime]; lpSystemTime
0x1400430ba  lea     rcx, [rbp+9B0h+FileInformation+4]; lpFileTime
0x1400430be  call    cs:__imp_FileTimeToSystemTime
0x1400430c4  movzx   eax, [rbp+9B0h+SystemTime.wSecond]
0x1400430c8  movzx   ecx, [rbp+9B0h+SystemTime.wMinute]
0x1400430cc  movzx   edx, [rbp+9B0h+SystemTime.wHour]
0x1400430d0  movzx   r8d, [rbp+9B0h+SystemTime.wYear]
0x1400430d5  movzx   r9d, [rbp+9B0h+SystemTime.wDay]
0x1400430da  movzx   r10d, [rbp+9B0h+SystemTime.wMonth]
0x1400430df  mov     [rsp+0AB0h+var_A68], eax
0x1400430e3  mov     [rsp+0AB0h+var_A70], ecx
0x1400430e7  mov     [rsp+0AB0h+var_A78], edx
0x1400430eb  mov     dword ptr [rsp+0AB0h+var_A80], r8d; char *
0x1400430f0  mov     [rsp+0AB0h+var_A88], r9d
0x1400430f5  mov     dword ptr [rsp+0AB0h+lpOverlapped], r10d
0x1400430fa  mov     r9d, [rbp+9B0h+var_920]
0x140043101  lea     r8, aFilenameFilesi; "</FILENAME>\r\n\t\t<FILESIZE>%u</FILESI"...
0x140043108  mov     edx, 402h; unsigned __int64
0x14004310d  lea     rcx, [rbp+9B0h+Buffer]; wchar_t *
0x140043114  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140043119  test    eax, eax
0x14004311b  js      short loc_14004314F
0x14004311d  lea     rax, [rbp+9B0h+Buffer]
0x140043124  or      r8, 0FFFFFFFFFFFFFFFFh
0x140043128  inc     r8
0x14004312b  cmp     [rax+r8*2], bx
0x140043130  jnz     short loc_140043128
0x140043132  add     r8d, r8d; nNumberOfBytesToWrite
0x140043135  mov     [rsp+0AB0h+lpOverlapped], rbx; lpOverlapped
0x14004313a  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004313f  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x140043146  mov     rcx, rsi; hFile
0x140043149  call    cs:__imp_WriteFile
0x14004314f  test    r14, r14
0x140043152  jz      short loc_1400431D2
0x140043154  cmp     [r14], bx
0x140043158  jz      short loc_1400431D2
0x14004315a  mov     [rsp+0AB0h+lpOverlapped], rbx; lpOverlapped
0x14004315f  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140043164  mov     r8d, 1Ah; nNumberOfBytesToWrite
0x14004316a  lea     rdx, aInfname_1; "\r\n\t\t<INFNAME>"
0x140043171  mov     rcx, rsi; hFile
0x140043174  call    cs:__imp_WriteFile
0x14004317a  mov     ebx, 402h
0x14004317f  mov     r9d, ebx; unsigned int
0x140043182  lea     r8, [rbp+9B0h+Buffer]; wchar_t *
0x140043189  mov     rdx, r14; wchar_t *
0x14004318c  call    ?XMLEncodeString@CKernelReportDataCollection@@AEAAKPEB_WPEA_WK@Z; CKernelReportDataCollection::XMLEncodeString(wchar_t const *,wchar_t *,ulong)
0x140043191  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140043195  xor     r14d, r14d
0x140043198  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x14004319d  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400431a2  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x1400431a9  mov     rcx, rsi; hFile
0x1400431ac  call    cs:__imp_WriteFile
0x1400431b2  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x1400431b7  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400431bc  lea     r8d, [r14+14h]; nNumberOfBytesToWrite
0x1400431c0  lea     rdx, aInfname_2; "</INFNAME>"
0x1400431c7  mov     rcx, rsi; hFile
0x1400431ca  call    cs:__imp_WriteFile
0x1400431d0  jmp     short loc_1400431DA
0x1400431d2  mov     ebx, 402h
0x1400431d7  xor     r14d, r14d
0x1400431da  test    r12, r12
0x1400431dd  jz      loc_140043291
0x1400431e3  lea     rdx, [rbp+9B0h+SystemTime]; lpSystemTime
0x1400431e7  mov     rcx, r12; lpFileTime
0x1400431ea  call    cs:__imp_FileTimeToSystemTime
0x1400431f0  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x1400431f5  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400431fa  mov     r8d, 1Ah; nNumberOfBytesToWrite
0x140043200  lea     rdx, aInfdate_1; "\r\n\t\t<INFDATE>"
0x140043207  mov     rcx, rsi; hFile
0x14004320a  call    cs:__imp_WriteFile
0x140043210  movzx   eax, [rbp+9B0h+SystemTime.wYear]
0x140043214  movzx   ecx, [rbp+9B0h+SystemTime.wDay]
0x140043218  movzx   r9d, [rbp+9B0h+SystemTime.wMonth]
0x14004321d  mov     [rsp+0AB0h+var_A88], eax
0x140043221  mov     dword ptr [rsp+0AB0h+lpOverlapped], ecx
0x140043225  lea     r8, a02d02d04d; "%02d-%02d-%04d"
0x14004322c  mov     rdx, rbx; unsigned __int64
0x14004322f  lea     rcx, [rbp+9B0h+Buffer]; wchar_t *
0x140043236  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14004323b  test    eax, eax
0x14004323d  js      short loc_140043271
0x14004323f  lea     rax, [rbp+9B0h+Buffer]
0x140043246  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004324a  inc     r8
0x14004324d  cmp     [rax+r8*2], r14w
0x140043252  jnz     short loc_14004324A
0x140043254  add     r8d, r8d; nNumberOfBytesToWrite
0x140043257  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x14004325c  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140043261  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x140043268  mov     rcx, rsi; hFile
0x14004326b  call    cs:__imp_WriteFile
0x140043271  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x140043276  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004327b  mov     r8d, 14h; nNumberOfBytesToWrite
0x140043281  lea     rdx, aInfdate_2; "</INFDATE>"
0x140043288  mov     rcx, rsi; hFile
0x14004328b  call    cs:__imp_WriteFile
0x140043291  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x140043296  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004329b  mov     r8d, 1Ah; nNumberOfBytesToWrite
0x1400432a1  lea     rdx, aVersion_2; "\r\n\t\t<VERSION>"
0x1400432a8  mov     rcx, rsi; hFile
0x1400432ab  call    cs:__imp_WriteFile
0x1400432b1  mov     dword ptr [rsp+0AB0h+lpOverlapped], 2; int
0x1400432b9  lea     r9, [rbp+9B0h+var_990]
0x1400432bd  lea     r8, off_1400602C0; "ProductName"
0x1400432c4  lea     rdx, [rbp+9B0h+var_9D0]
0x1400432c8  mov     rcx, rdi; lpwstrFilename
0x1400432cb  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x1400432d0  mov     rcx, [rbp+9B8h]; this
0x1400432d7  lea     rdx, aUtilgetfileinf; "UtilGetFileInfo failed"
0x1400432de  mov     qword ptr [rsp+0AB0h+var_A88], rdx; int
0x1400432e3  mov     dword ptr [rsp+0AB0h+lpOverlapped], eax; char *
0x1400432e7  lea     r9, aCkernelreportd_10; "CKernelReportDataCollection::WriteDrive"...
0x1400432ee  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400432f5  mov     edx, 2EAh; void *
0x1400432fa  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400432ff  mov     [rbp+9B0h+var_910], r14w
0x140043307  movzx   ecx, word ptr [rbp+9B0h+var_9D0+0Ch]
0x14004330b  mov     edx, dword ptr [rbp+9B0h+var_9D0+0Ch]
0x14004330e  shr     edx, 10h
0x140043311  movzx   eax, word ptr [rbp+9B0h+var_9D0+8]
0x140043315  mov     r9d, dword ptr [rbp+9B0h+var_9D0+8]
0x140043319  shr     r9d, 10h
0x14004331d  mov     dword ptr [rsp+0AB0h+var_A80], ecx; char *
0x140043321  mov     [rsp+0AB0h+var_A88], edx
0x140043325  mov     dword ptr [rsp+0AB0h+lpOverlapped], eax
0x140043329  lea     r8, aUUUU; "%u.%u.%u.%u"
0x140043330  mov     edx, 20h ; ' '; unsigned __int64
0x140043335  lea     rcx, [rbp+9B0h+var_910]; wchar_t *
0x14004333c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140043341  mov     rcx, [rbp+9B8h]; this
0x140043348  lea     rdx, aStringcchprint; "StringCchPrintf failed"
0x14004334f  mov     qword ptr [rsp+0AB0h+var_A88], rdx; int
0x140043354  mov     dword ptr [rsp+0AB0h+lpOverlapped], eax; char *
0x140043358  lea     r9, aCkernelreportd_10; "CKernelReportDataCollection::WriteDrive"...
0x14004335f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140043366  mov     edx, 2F7h; void *
0x14004336b  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043370  mov     [rbp+9B0h+Buffer], r14w
0x140043378  mov     r9d, ebx; unsigned int
0x14004337b  lea     r8, [rbp+9B0h+Buffer]; wchar_t *
0x140043382  lea     rdx, [rbp+9B0h+var_910]; wchar_t *
0x140043389  call    ?XMLEncodeString@CKernelReportDataCollection@@AEAAKPEB_WPEA_WK@Z; CKernelReportDataCollection::XMLEncodeString(wchar_t const *,wchar_t *,ulong)
0x14004338e  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x140043392  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x140043397  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004339c  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x1400433a3  mov     rcx, rsi; hFile
0x1400433a6  call    cs:__imp_WriteFile
0x1400433ac  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x1400433b1  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400433b6  mov     r8d, 38h ; '8'; nNumberOfBytesToWrite
0x1400433bc  lea     rdx, aVersionManufac; "</VERSION>\r\n\t\t<MANUFACTURER>"
0x1400433c3  mov     rcx, rsi; hFile
0x1400433c6  call    cs:__imp_WriteFile
0x1400433cc  mov     [rbp+9B0h+Buffer], r14w
0x1400433d4  mov     r9d, ebx; unsigned int
0x1400433d7  lea     r8, [rbp+9B0h+Buffer]; wchar_t *
0x1400433de  mov     rdx, [rbp+9B0h+var_970]; wchar_t *
0x1400433e2  call    ?XMLEncodeString@CKernelReportDataCollection@@AEAAKPEB_WPEA_WK@Z; CKernelReportDataCollection::XMLEncodeString(wchar_t const *,wchar_t *,ulong)
0x1400433e7  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x1400433eb  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x1400433f0  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400433f5  lea     rdx, [rbp+9B0h+Buffer]; lpBuffer
0x1400433fc  mov     rcx, rsi; hFile
0x1400433ff  call    cs:__imp_WriteFile
0x140043405  mov     [rsp+0AB0h+lpOverlapped], r14; lpOverlapped
0x14004340a  lea     r9, [rsp+0AB0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004340f  mov     r8d, 40h ; '@'; nNumberOfBytesToWrite
0x140043415  lea     rdx, aManufacturerPr; "</MANUFACTURER>\r\n\t\t<PRODUCTNAME>"
0x14004341c  mov     rcx, rsi; hFile
0x14004341f  call    cs:__imp_WriteFile
0x140043425  mov     [rbp+9B0h+Buffer], r14w
0x14004342d  mov     r9d, ebx; unsigned int
0x140043430  lea     r8, [rbp+9B0h+Buffer]; wchar_t *
0x140043437  mov     rdx, [rbp+9B0h+var_990]; wchar_t *
0x14004343b  call    ?XMLEncodeString@CKernelReportDataCollection@@AEAAKPEB_WPEA_WK@Z; CKernelReportDataCollection::XMLEncodeString(wchar_t const *,wchar_t *,ulong)
0x140043440  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
  ... truncated ...
```
