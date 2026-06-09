# Windows::Compat::Appraiser::Utilities::DownloadCabFile(ushort const *,ushort const *)

- ea: `0x18008513c`
- end: `0x1800858c1`
- name: `?DownloadCabFile@Utilities@Appraiser@Compat@Windows@@SAJPEBG0@Z`
- size: `1925`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039538`
- `0x1800858c8`

## callees

- `0x180008570`
- `0x18001a2f4`
- `0x1800301d0`
- `0x18008513c`
- `0x18008b878`
- `0x1800911bc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008548e`
- `KERNEL32!CreateFileW` at `0x18008548e`
- `KERNEL32!WriteFile` at `0x180085675`
- `KERNEL32!WriteFile` at `0x180085675`
- `KERNEL32!GetProcessHeap` at `0x1800855f1`
- `KERNEL32!GetProcessHeap` at `0x180085858`
- `KERNEL32!GetProcessHeap` at `0x1800855f1`
- `KERNEL32!GetProcessHeap` at `0x180085858`
- `KERNEL32!HeapAlloc` at `0x180085602`
- `KERNEL32!HeapAlloc` at `0x180085602`
- `KERNEL32!CloseHandle` at `0x18008586f`
- `KERNEL32!CloseHandle` at `0x18008586f`
- `KERNEL32!GetLastError` at `0x18008549d`
- `KERNEL32!GetLastError` at `0x1800854be`
- `KERNEL32!GetLastError` at `0x1800854dd`
- `KERNEL32!GetLastError` at `0x180085570`
- `KERNEL32!GetLastError` at `0x180085591`
- `KERNEL32!GetLastError` at `0x1800855b0`
- `KERNEL32!GetLastError` at `0x18008572e`
- `KERNEL32!GetLastError` at `0x180085752`
- `KERNEL32!GetLastError` at `0x180085771`
- `KERNEL32!GetLastError` at `0x1800857e2`
- `KERNEL32!GetLastError` at `0x180085806`
- `KERNEL32!GetLastError` at `0x180085825`
- `KERNEL32!GetLastError` at `0x18008549d`
- `KERNEL32!GetLastError` at `0x1800854be`
- `KERNEL32!GetLastError` at `0x1800854dd`
- `KERNEL32!GetLastError` at `0x180085570`
- `KERNEL32!GetLastError` at `0x180085591`
- `KERNEL32!GetLastError` at `0x1800855b0`
- `KERNEL32!GetLastError` at `0x18008572e`
- `KERNEL32!GetLastError` at `0x180085752`
- `KERNEL32!GetLastError` at `0x180085771`
- `KERNEL32!GetLastError` at `0x1800857e2`
- `KERNEL32!GetLastError` at `0x180085806`
- `KERNEL32!GetLastError` at `0x180085825`
- `KERNEL32!HeapFree` at `0x180085866`
- `KERNEL32!HeapFree` at `0x180085866`
- `WINHTTP!WinHttpCloseHandle` at `0x18008587f`
- `WINHTTP!WinHttpCloseHandle` at `0x18008588f`
- `WINHTTP!WinHttpCloseHandle` at `0x18008587f`
- `WINHTTP!WinHttpCloseHandle` at `0x18008588f`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180085566`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180085566`
- `WINHTTP!WinHttpReadData` at `0x180085644`
- `WINHTTP!WinHttpReadData` at `0x180085644`

## string_xrefs

- `0x180085254`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800852d2`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180085347`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800853c9`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800854ea`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800855bd`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800857cc`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180085840`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800851d6`: `Cab file link %ls.`
- `0x1800853fb`: `Cab file link %ls.`
- `0x18008544f`: `Cab file link %ls.`
- `0x1800851ca`: `%ls - Cab file link download attempt started.`
- `0x1800851b4`: `Windows::Compat::Appraiser::Utilities::DownloadCabFile`
- `0x18008531d`: `Failed to send request using default proxy with impersonation: [0x%x].`
- `0x1800853ba`: `Failed to send request using auto proxy with impersonation`
- `0x1800853e1`: `All cab file link download attempts failed.`
- `0x180085338`: `Failed to send request using default proxy with impersonation`
- `0x18008539c`: `Failed to send request using auto proxy with impersonation: [0x%x].`
- `0x1800854f6`: `Failed to create file: [0x%x].`
- `0x180085439`: `%ls - Cab file link downloaded.`
- `0x1800854a3`: `Failed to create file to save http data: [%d].`
- `0x180085610`: `Failed to allocate space for the buffer that the http data will be read/written into.`
- `0x1800857e8`: `Failed to read http data: [%d].`
- `0x180085834`: `Failed to read data: [%d].`
- `0x180085734`: `Failed to write to http data file: [%d].`
- `0x180085780`: `Failed to write file: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::DownloadCabFile(WCHAR *a1, LPCWSTR lpFileName)
{
  int v4; // eax
  unsigned __int64 v5; // rdx
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  signed int v10; // ebx
  int v11; // eax
  int v12; // esi
  unsigned __int64 v13; // rdx
  HANDLE FileW; // r14
  DWORD LastError; // eax
  signed int v16; // eax
  DWORD v17; // eax
  signed int v18; // eax
  HANDLE ProcessHeap; // rax
  void *v20; // rsi
  unsigned __int64 v21; // rdx
  DWORD v22; // eax
  signed int v23; // eax
  char v24; // dl
  const char *v25; // rax
  DWORD v26; // eax
  signed int v27; // eax
  HANDLE v28; // rax
  const char *dwCreationDispositionc; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositiond; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositione; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositionf; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositiong; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositionh; // [rsp+20h] [rbp-E0h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFileb; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilec; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFiled; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilee; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilef; // [rsp+30h] [rbp-D0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  HINTERNET hRequest; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  HINTERNET hInternet; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v51[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v52[264]; // [rsp+70h] [rbp-90h] BYREF

  v51[0] = L"*/*";
  v51[1] = 0;
  hInternet = 0;
  hRequest = 0;
  dwNumberOfBytesAvailable = 0;
  NumberOfBytesWritten = 0;
  dwNumberOfBytesRead = 0;
  Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v52, (unsigned __int64)lpFileName);
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
    6914,
    "%ls - Cab file link download attempt started.",
    v52);
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::DownloadCabFile", 6915, "Cab file link %ls.", a1);
  v4 = Windows::Compat::Appraiser::Utilities::SendRequest(
         &hRequest,
         &hInternet,
         a1,
         0,
         (const unsigned __int16 **)v51,
         0,
         0);
  v6 = v4;
  if ( v4 >= 0 )
    goto LABEL_10;
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
    6920,
    "Failed to send request using default proxy: [0x%x].",
    v4);
  LODWORD(dwCreationDispositionc) = v6;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    9,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
    dwCreationDispositionc,
    (int)"Failed to send request using default proxy",
    hTemplateFile);
  v7 = Windows::Compat::Appraiser::Utilities::SendRequest(
         &hRequest,
         &hInternet,
         a1,
         4u,
         (const unsigned __int16 **)v51,
         0,
         0);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_10;
  if ( v7 != -2147024809 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
      6933,
      "Failed to send request using auto proxy: [0x%x].",
      v7);
    LODWORD(dwCreationDispositiond) = v8;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      22,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
      dwCreationDispositiond,
      (int)"Failed to send request using auto proxy",
      hTemplateFilea);
  }
  v9 = Windows::Compat::Appraiser::Utilities::SendRequest(
         &hRequest,
         &hInternet,
         a1,
         0,
         (const unsigned __int16 **)v51,
         1,
         0);
  v10 = v9;
  if ( v9 >= 0
    || (AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
          6946,
          "Failed to send request using default proxy with impersonation: [0x%x].",
          v9),
        LODWORD(dwCreationDispositione) = v10,
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          35,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
          dwCreationDispositione,
          (int)"Failed to send request using default proxy with impersonation",
          hTemplateFileb),
        v11 = Windows::Compat::Appraiser::Utilities::SendRequest(
                &hRequest,
                &hInternet,
                a1,
                4u,
                (const unsigned __int16 **)v51,
                1,
                0),
        v12 = v11,
        v11 >= 0) )
  {
LABEL_10:
    Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v52, v5);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
      6980,
      "%ls - Cab file link downloaded.",
      v52);
    AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::DownloadCabFile", 6981, "Cab file link %ls.", a1);
    FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
        6997,
        "Failed to create file to save http data: [%d].",
        LastError);
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      LODWORD(hTemplateFiled) = GetLastError();
      LODWORD(dwCreationDisposition) = v10;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        86,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
        dwCreationDisposition,
        (int)"Failed to create file: [0x%x].",
        hTemplateFiled);
    }
    else
    {
      Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v52, v13);
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
        7002,
        "%ls - Initialization done at cab file destination.",
        v52);
      AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::DownloadCabFile", 7003, "Cab dest %ls.", lpFileName);
      if ( WinHttpQueryDataAvailable(hRequest, &dwNumberOfBytesAvailable) )
      {
        dwNumberOfBytesAvailable = 0x2000;
        ProcessHeap = GetProcessHeap();
        v20 = HeapAlloc(ProcessHeap, 8u, 0x2000u);
        if ( v20 )
        {
          while ( WinHttpReadData(hRequest, v20, dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
          {
            if ( dwNumberOfBytesRead > dwNumberOfBytesAvailable )
            {
              v10 = -2147418113;
              AslLogCallPrintf(
                3,
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                7043,
                "Downloaded http data size (%lu) > the expected size (%lu): [0x%x].",
                dwNumberOfBytesRead,
                dwNumberOfBytesAvailable,
                -2147418113);
              LODWORD(dwCreationDispositionh) = -2147418113;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                132,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                dwCreationDispositionh,
                (int)"Size was incorrect.",
                hTemplateFilef);
              goto LABEL_43;
            }
            if ( !WriteFile(FileW, v20, dwNumberOfBytesRead, &NumberOfBytesWritten, 0) )
            {
              v22 = GetLastError();
              AslLogCallPrintf(
                3,
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                7049,
                "Failed to write to http data file: [%d].",
                v22);
              v23 = GetLastError();
              v10 = v23;
              if ( v23 > 0 )
                v10 = (unsigned __int16)v23 | 0x80070000;
              if ( v10 >= 0 )
                v10 = -2147467259;
              LODWORD(hTemplateFiled) = GetLastError();
              v24 = -118;
              v25 = "Failed to write file: [%d].";
              goto LABEL_42;
            }
            if ( dwNumberOfBytesRead != NumberOfBytesWritten )
            {
              v10 = -2147467259;
              AslLogCallPrintf(
                3,
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                7056,
                "Downloaded http data size (%lu) != the file size written to the http data file (%lu): [0x%x].",
                dwNumberOfBytesRead,
                NumberOfBytesWritten,
                -2147467259);
              LODWORD(dwCreationDispositiong) = -2147467259;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                145,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                dwCreationDispositiong,
                (int)"Downloaded size was incorrect.",
                hTemplateFilee);
              goto LABEL_43;
            }
            if ( !dwNumberOfBytesRead )
            {
              Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v52, v21);
              AslLogCallPrintf(
                3,
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                7063,
                "%ls - Creation done for cab file destination.",
                v52);
              AslLogCallPrintf(
                3,
                "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
                7064,
                "Cab dest %ls.",
                lpFileName);
              v10 = 0;
              goto LABEL_43;
            }
          }
          v26 = GetLastError();
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
            7036,
            "Failed to read http data: [%d].",
            v26);
          v27 = GetLastError();
          v10 = v27;
          if ( v27 > 0 )
            v10 = (unsigned __int16)v27 | 0x80070000;
          if ( v10 >= 0 )
            v10 = -2147467259;
          LODWORD(hTemplateFiled) = GetLastError();
          v24 = 125;
          v25 = "Failed to read data: [%d].";
LABEL_42:
          LODWORD(dwCreationDispositionb) = v10;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v24,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
            dwCreationDispositionb,
            (int)v25,
            hTemplateFiled);
LABEL_43:
          v28 = GetProcessHeap();
          HeapFree(v28, 0, v20);
        }
        else
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
            7023,
            "Failed to allocate space for the buffer that the http data will be read/written into.");
          v10 = -2147024882;
        }
      }
      else
      {
        v17 = GetLastError();
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
          7011,
          "Failed to verify if http data is available: [%d].",
          v17);
        v18 = GetLastError();
        v10 = v18;
        if ( v18 > 0 )
          v10 = (unsigned __int16)v18 | 0x80070000;
        if ( v10 >= 0 )
          v10 = -2147467259;
        LODWORD(hTemplateFiled) = GetLastError();
        LODWORD(dwCreationDispositiona) = v10;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          100,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
          dwCreationDispositiona,
          (int)"Failed to verify if data is available: [%d].",
          hTemplateFiled);
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    if ( v11 != -2147024809 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
        6960,
        "Failed to send request using auto proxy with impersonation: [0x%x].",
        v11);
      LODWORD(dwCreationDispositionf) = v12;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        49,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
        dwCreationDispositionf,
        (int)"Failed to send request using auto proxy with impersonation",
        hTemplateFilec);
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::DownloadCabFile",
      6974,
      "All cab file link download attempts failed.");
    AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::DownloadCabFile", 6975, "Cab file link %ls.", a1);
  }
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( hRequest )
    WinHttpCloseHandle(hRequest);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008513c  mov     [rsp-8+arg_10], rbx
0x180085141  push    rbp
0x180085142  push    rsi
0x180085143  push    rdi
0x180085144  push    r12
0x180085146  push    r13
0x180085148  push    r14
0x18008514a  push    r15
0x18008514c  lea     rbp, [rsp-190h]
0x180085154  sub     rsp, 290h
0x18008515b  mov     rax, cs:__security_cookie
0x180085162  xor     rax, rsp
0x180085165  mov     [rbp+1C0h+var_40], rax
0x18008516c  xor     r12d, r12d
0x18008516f  lea     rax, asc_180245ED0; "*/*"
0x180085176  mov     rdi, rcx
0x180085179  mov     [rsp+2C0h+var_260], rax
0x18008517e  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180085183  mov     [rsp+2C0h+var_258], r12
0x180085188  mov     [rsp+2C0h+hInternet], r12
0x18008518d  mov     r15, rdx
0x180085190  mov     [rsp+2C0h+hRequest], r12
0x180085195  mov     [rsp+2C0h+dwNumberOfBytesAvailable], r12d
0x18008519a  mov     [rsp+2C0h+NumberOfBytesWritten], r12d
0x18008519f  mov     [rsp+2C0h+dwNumberOfBytesRead], r12d
0x1800851a4  call    ?GetSystemTimeIso8601@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(ushort *,unsigned __int64)
0x1800851a9  lea     rax, [rsp+2C0h+var_250]
0x1800851ae  mov     r8d, 1B02h
0x1800851b4  lea     r13, aWindowsCompatA_500; "Windows::Compat::Appraiser::Utilities::"...
0x1800851bb  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x1800851c0  lea     esi, [r12+3]
0x1800851c5  mov     rdx, r13
0x1800851c8  mov     ecx, esi
0x1800851ca  lea     r9, aLsCabFileLinkD; "%ls - Cab file link download attempt st"...
0x1800851d1  call    AslLogCallPrintf
0x1800851d6  lea     r9, aCabFileLinkLs; "Cab file link %ls."
0x1800851dd  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rdi
0x1800851e2  mov     r8d, 1B03h
0x1800851e8  mov     rdx, r13
0x1800851eb  mov     ecx, esi
0x1800851ed  call    AslLogCallPrintf
0x1800851f2  lea     rax, [rsp+2C0h+var_260]
0x1800851f7  mov     dword ptr [rsp+2C0h+hTemplateFile], r12d; char *
0x1800851fc  mov     byte ptr [rsp+2C0h+dwFlagsAndAttributes], r12b; bool
0x180085201  lea     rdx, [rsp+2C0h+hInternet]; void **
0x180085206  xor     r9d, r9d; unsigned int
0x180085209  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; unsigned __int16 **
0x18008520e  mov     r8, rdi; unsigned __int16 *
0x180085211  lea     rcx, [rsp+2C0h+hRequest]; void **
0x180085216  call    ?SendRequest@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAX0PEBGKPEAPEBG_NK@Z; Windows::Compat::Appraiser::Utilities::SendRequest(void * &,void * &,ushort const *,ulong,ushort const * *,bool,ulong)
0x18008521b  lea     r14d, [r12+1]
0x180085220  mov     ebx, eax
0x180085222  test    eax, eax
0x180085224  jns     loc_180085424
0x18008522a  lea     r9, aFailedToSendRe; "Failed to send request using default pr"...
0x180085231  mov     [rsp+2C0h+dwCreationDisposition], eax
0x180085235  mov     r8d, 1B08h
0x18008523b  mov     rdx, r13
0x18008523e  mov     ecx, esi
0x180085240  call    AslLogCallPrintf
0x180085245  lea     rax, aFailedToSendRe_1; "Failed to send request using default pr"...
0x18008524c  mov     r9, r13; char *
0x18008524f  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x180085254  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008525b  mov     edx, 1B09h; bool
0x180085260  mov     [rsp+2C0h+dwCreationDisposition], ebx; char *
0x180085264  mov     ecx, r14d; this
0x180085267  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008526c  lea     rax, [rsp+2C0h+var_260]
0x180085271  mov     dword ptr [rsp+2C0h+hTemplateFile], r12d; char *
0x180085276  mov     byte ptr [rsp+2C0h+dwFlagsAndAttributes], r12b; bool
0x18008527b  lea     r9d, [r12+4]; unsigned int
0x180085280  mov     r8, rdi; unsigned __int16 *
0x180085283  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; unsigned __int16 **
0x180085288  lea     rdx, [rsp+2C0h+hInternet]; void **
0x18008528d  lea     rcx, [rsp+2C0h+hRequest]; void **
0x180085292  call    ?SendRequest@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAX0PEBGKPEAPEBG_NK@Z; Windows::Compat::Appraiser::Utilities::SendRequest(void * &,void * &,ushort const *,ulong,ushort const * *,bool,ulong)
0x180085297  mov     ebx, eax
0x180085299  test    eax, eax
0x18008529b  jns     loc_180085424
0x1800852a1  cmp     eax, 80070057h
0x1800852a6  jz      short loc_1800852EA
0x1800852a8  lea     r9, aFailedToSendRe_2; "Failed to send request using auto proxy"...
0x1800852af  mov     [rsp+2C0h+dwCreationDisposition], eax
0x1800852b3  mov     r8d, 1B15h
0x1800852b9  mov     rdx, r13
0x1800852bc  mov     ecx, esi
0x1800852be  call    AslLogCallPrintf
0x1800852c3  lea     rax, aFailedToSendRe_5; "Failed to send request using auto proxy"
0x1800852ca  mov     r9, r13; char *
0x1800852cd  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x1800852d2  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800852d9  mov     edx, 1B16h; bool
0x1800852de  mov     [rsp+2C0h+dwCreationDisposition], ebx; char *
0x1800852e2  mov     ecx, r14d; this
0x1800852e5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800852ea  mov     dword ptr [rsp+2C0h+hTemplateFile], r12d; char *
0x1800852ef  lea     rax, [rsp+2C0h+var_260]
0x1800852f4  mov     byte ptr [rsp+2C0h+dwFlagsAndAttributes], r14b; bool
0x1800852f9  lea     rdx, [rsp+2C0h+hInternet]; void **
0x1800852fe  xor     r9d, r9d; unsigned int
0x180085301  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; unsigned __int16 **
0x180085306  mov     r8, rdi; unsigned __int16 *
0x180085309  lea     rcx, [rsp+2C0h+hRequest]; void **
0x18008530e  call    ?SendRequest@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAX0PEBGKPEAPEBG_NK@Z; Windows::Compat::Appraiser::Utilities::SendRequest(void * &,void * &,ushort const *,ulong,ushort const * *,bool,ulong)
0x180085313  mov     ebx, eax
0x180085315  test    eax, eax
0x180085317  jns     loc_180085424
0x18008531d  lea     r9, aFailedToSendRe_4; "Failed to send request using default pr"...
0x180085324  mov     [rsp+2C0h+dwCreationDisposition], eax
0x180085328  mov     r8d, 1B22h
0x18008532e  mov     rdx, r13
0x180085331  mov     ecx, esi
0x180085333  call    AslLogCallPrintf
0x180085338  lea     rax, aFailedToSendRe_0; "Failed to send request using default pr"...
0x18008533f  mov     r9, r13; char *
0x180085342  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x180085347  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008534e  mov     edx, 1B23h; bool
0x180085353  mov     [rsp+2C0h+dwCreationDisposition], ebx; char *
0x180085357  mov     ecx, r14d; this
0x18008535a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008535f  lea     rax, [rsp+2C0h+var_260]
0x180085364  mov     dword ptr [rsp+2C0h+hTemplateFile], r12d; char *
0x180085369  mov     byte ptr [rsp+2C0h+dwFlagsAndAttributes], r14b; bool
0x18008536e  lea     rdx, [rsp+2C0h+hInternet]; void **
0x180085373  mov     r9d, 4; unsigned int
0x180085379  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; unsigned __int16 **
0x18008537e  mov     r8, rdi; unsigned __int16 *
0x180085381  lea     rcx, [rsp+2C0h+hRequest]; void **
0x180085386  call    ?SendRequest@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAX0PEBGKPEAPEBG_NK@Z; Windows::Compat::Appraiser::Utilities::SendRequest(void * &,void * &,ushort const *,ulong,ushort const * *,bool,ulong)
0x18008538b  mov     esi, eax
0x18008538d  test    eax, eax
0x18008538f  jns     loc_18008541F
0x180085395  cmp     eax, 80070057h
0x18008539a  jz      short loc_1800853E1
0x18008539c  lea     r9, aFailedToSendRe_6; "Failed to send request using auto proxy"...
0x1800853a3  mov     [rsp+2C0h+dwCreationDisposition], eax
0x1800853a7  mov     r8d, 1B30h
0x1800853ad  mov     rdx, r13
0x1800853b0  mov     ecx, 3
0x1800853b5  call    AslLogCallPrintf
0x1800853ba  lea     rax, aFailedToSendRe_3; "Failed to send request using auto proxy"...
0x1800853c1  mov     r9, r13; char *
0x1800853c4  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x1800853c9  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800853d0  mov     edx, 1B31h; bool
0x1800853d5  mov     [rsp+2C0h+dwCreationDisposition], esi; char *
0x1800853d9  mov     ecx, r14d; this
0x1800853dc  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800853e1  lea     r9, aAllCabFileLink; "All cab file link download attempts fai"...
0x1800853e8  mov     r8d, 1B3Eh
0x1800853ee  mov     rdx, r13
0x1800853f1  mov     ecx, 3
0x1800853f6  call    AslLogCallPrintf
0x1800853fb  lea     r9, aCabFileLinkLs; "Cab file link %ls."
0x180085402  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rdi
0x180085407  mov     r8d, 1B3Fh
0x18008540d  mov     rdx, r13
0x180085410  mov     ecx, 3
0x180085415  call    AslLogCallPrintf
0x18008541a  jmp     loc_180085875
0x18008541f  mov     esi, 3
0x180085424  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180085429  call    ?GetSystemTimeIso8601@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(ushort *,unsigned __int64)
0x18008542e  lea     rax, [rsp+2C0h+var_250]
0x180085433  mov     r8d, 1B44h
0x180085439  lea     r9, aLsCabFileLinkD_0; "%ls - Cab file link downloaded."
0x180085440  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x180085445  mov     rdx, r13
0x180085448  mov     ecx, esi
0x18008544a  call    AslLogCallPrintf
0x18008544f  lea     r9, aCabFileLinkLs; "Cab file link %ls."
0x180085456  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rdi
0x18008545b  mov     r8d, 1B45h
0x180085461  mov     rdx, r13
0x180085464  mov     ecx, esi
0x180085466  call    AslLogCallPrintf
0x18008546b  mov     [rsp+2C0h+hTemplateFile], r12; hTemplateFile
0x180085470  xor     r9d, r9d; lpSecurityAttributes
0x180085473  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008547b  xor     r8d, r8d; dwShareMode
0x18008547e  mov     edx, 40000000h; dwDesiredAccess
0x180085483  mov     [rsp+2C0h+dwCreationDisposition], 2; dwCreationDisposition
0x18008548b  mov     rcx, r15; lpFileName
0x18008548e  call    cs:__imp_CreateFileW
0x180085494  mov     r14, rax
0x180085497  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008549b  jnz     short loc_180085515
0x18008549d  call    cs:__imp_GetLastError
0x1800854a3  lea     r9, aFailedToCreate_55; "Failed to create file to save http data"...
0x1800854aa  mov     r8d, 1B55h
0x1800854b0  mov     rdx, r13
0x1800854b3  mov     [rsp+2C0h+dwCreationDisposition], eax
0x1800854b7  mov     ecx, esi
0x1800854b9  call    AslLogCallPrintf
0x1800854be  call    cs:__imp_GetLastError
0x1800854c4  mov     ebx, eax
0x1800854c6  test    eax, eax
0x1800854c8  jle     short loc_1800854D3
0x1800854ca  movzx   ebx, ax
0x1800854cd  or      ebx, 80070000h
0x1800854d3  test    ebx, ebx
0x1800854d5  mov     edi, 80004005h
0x1800854da  cmovns  ebx, edi
0x1800854dd  call    cs:__imp_GetLastError
0x1800854e3  mov     dword ptr [rsp+2C0h+hTemplateFile], eax; char *
0x1800854e7  mov     r9, r13; char *
0x1800854ea  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800854f1  mov     edx, 1B56h; bool
0x1800854f6  lea     rax, aFailedToCreate_10; "Failed to create file: [0x%x]."
0x1800854fd  mov     ecx, 1; this
0x180085502  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x180085507  mov     [rsp+2C0h+dwCreationDisposition], ebx; char *
0x18008550b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180085510  jmp     loc_180085875
0x180085515  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18008551a  call    ?GetSystemTimeIso8601@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(ushort *,unsigned __int64)
0x18008551f  lea     rax, [rsp+2C0h+var_250]
0x180085524  mov     r8d, 1B5Ah
0x18008552a  lea     r9, aLsInitializati; "%ls - Initialization done at cab file d"...
0x180085531  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x180085536  mov     rdx, r13
0x180085539  mov     ecx, esi
0x18008553b  call    AslLogCallPrintf
0x180085540  lea     r9, aCabDestLs; "Cab dest %ls."
0x180085547  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15
0x18008554c  mov     r8d, 1B5Bh
0x180085552  mov     rdx, r13
0x180085555  mov     ecx, esi
0x180085557  call    AslLogCallPrintf
0x18008555c  mov     rcx, [rsp+2C0h+hRequest]; hRequest
0x180085561  lea     rdx, [rsp+2C0h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x180085566  call    cs:__imp_WinHttpQueryDataAvailable
0x18008556c  test    eax, eax
0x18008556e  jnz     short loc_1800855E8
0x180085570  call    cs:__imp_GetLastError
0x180085576  lea     r9, aFailedToVerify_7; "Failed to verify if http data is availa"...
0x18008557d  mov     r8d, 1B63h
0x180085583  mov     rdx, r13
0x180085586  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18008558a  mov     ecx, esi
0x18008558c  call    AslLogCallPrintf
0x180085591  call    cs:__imp_GetLastError
0x180085597  mov     ebx, eax
0x180085599  test    eax, eax
0x18008559b  jle     short loc_1800855A6
0x18008559d  movzx   ebx, ax
0x1800855a0  or      ebx, 80070000h
0x1800855a6  test    ebx, ebx
0x1800855a8  mov     edi, 80004005h
0x1800855ad  cmovns  ebx, edi
0x1800855b0  call    cs:__imp_GetLastError
0x1800855b6  mov     dword ptr [rsp+2C0h+hTemplateFile], eax; char *
0x1800855ba  mov     r9, r13; char *
0x1800855bd  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800855c4  mov     edx, 1B64h; bool
0x1800855c9  lea     rax, aFailedToVerify_8; "Failed to verify if data is available: "...
0x1800855d0  mov     ecx, 1; this
0x1800855d5  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax; int
0x1800855da  mov     [rsp+2C0h+dwCreationDisposition], ebx; char *
0x1800855de  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800855e3  jmp     loc_18008586C
0x1800855e8  mov     ebx, 2000h
0x1800855ed  mov     [rsp+2C0h+dwNumberOfBytesAvailable], ebx
0x1800855f1  call    cs:__imp_GetProcessHeap
0x1800855f7  mov     r8d, ebx; dwBytes
0x1800855fa  mov     edx, 8; dwFlags
0x1800855ff  mov     rcx, rax; hHeap
0x180085602  call    cs:__imp_HeapAlloc
0x180085608  mov     rsi, rax
0x18008560b  test    rax, rax
0x18008560e  jnz     short loc_180085632
0x180085610  lea     r9, aFailedToAlloca_4; "Failed to allocate space for the buffer"...
0x180085617  mov     r8d, 1B6Fh
0x18008561d  mov     rdx, r13
0x180085620  lea     ecx, [rax+3]
0x180085623  call    AslLogCallPrintf
0x180085628  mov     ebx, 8007000Eh
0x18008562d  jmp     loc_18008586C
0x180085632  mov     r8d, [rsp+2C0h+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x180085637  lea     r9, [rsp+2C0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18008563c  mov     rcx, [rsp+2C0h+hRequest]; hRequest
0x180085641  mov     rdx, rsi; lpBuffer
0x180085644  call    cs:__imp_WinHttpReadData
0x18008564a  test    eax, eax
0x18008564c  jz      loc_1800857E2
0x180085652  mov     eax, [rsp+2C0h+dwNumberOfBytesRead]
0x180085656  mov     ecx, [rsp+2C0h+dwNumberOfBytesAvailable]
0x18008565a  cmp     eax, ecx
0x18008565c  ja      loc_18008578C
0x180085662  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180085667  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; lpOverlapped
0x18008566c  mov     r8d, eax; nNumberOfBytesToWrite
0x18008566f  mov     rdx, rsi; lpBuffer
0x180085672  mov     rcx, r14; hFile
0x180085675  call    cs:__imp_WriteFile
0x18008567b  test    eax, eax
0x18008567d  jz      loc_18008572E
0x180085683  mov     eax, [rsp+2C0h+dwNumberOfBytesRead]
  ... truncated ...
```
