# GetExeNameAndAppId(ushort * *,_GUID *)

- ea: `0x180014e80`
- end: `0x180015186`
- name: `?GetExeNameAndAppId@@YAJPEAPEAGPEAU_GUID@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022928`

## callees

- `0x180003cf0`
- `0x180006324`
- `0x18000d5f4`
- `0x18000e6f4`
- `0x180014e80`
- `0x180021dcc`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800150ef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800150ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800150cd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800150cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f9c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014f26`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180014f26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014f12`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180014f92`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180014f92`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180014fe1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180014fe1`
- `msvcrt!_stricmp` at `0x18001507a`
- `msvcrt!_stricmp` at `0x18001507a`
- `msvcrt!strchr` at `0x180014fef`
- `msvcrt!strchr` at `0x180014fef`
- `msvcrt!_wcsicmp` at `0x180014fcc`
- `msvcrt!_wcsicmp` at `0x180014fcc`

## string_xrefs

- `0x180014fb1`: `GetFullPathNameW failed`
- `0x180014f5e`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x18001510b`: `com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp`
- `0x180014ee1`: `GetExeNameAndAppId (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@176): GetExeNameAndAppId - NULL != ppwszExeName`
- `0x180014ef3`: `GetExeNameAndAppId (com\complus\dtc\dtc\msdtcprx\src\dllgettmcore.cpp@177): GetExeNameAndAppId - NULL != pAppId`
- `0x180014fc5`: `dllhost.exe`
- `0x180015014`: `/ProcessID`
- `0x18001503c`: `CommandLine has no arguments, skipping AppId.`
- `0x1800150d7`: `Unable to convert command line argument to WCHAR, skipping AppId.`
- `0x1800150f9`: `Unable to convert command line argument to a GUID, skipping AppId.`

## pseudocode

```c
__int64 __fastcall GetExeNameAndAppId(unsigned __int16 **a1, struct _GUID *a2)
{
  HANDLE CurrentProcess; // rax
  signed int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  signed int LastError; // eax
  const char *CommandLineA; // rax
  char *v11; // rax
  int v12; // r8d
  int v13; // r9d
  char *v14; // rcx
  char *v15; // rbx
  char *i; // rax
  const CHAR *v17; // r15
  int v18; // r11d
  int cchWideChar[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwSize; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  char *String1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  char String2[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR WideCharStr[48]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ExeName[264]; // [rsp+E0h] [rbp-20h] BYREF
  char v29; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR Buffer[264]; // [rsp+400h] [rbp+300h] BYREF

  FilePart = 0;
  dwSize = 261;
  v24 = 0;
  pclsid = GUID_NULL;
  if ( !a1 )
    DtcInternalErrorW(
      L"GetExeNameAndAppId (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@176): GetExeNameAndAppId - NULL != ppwszExeName");
  if ( !a2 )
    DtcInternalErrorW(
      L"GetExeNameAndAppId (com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp@177): GetExeNameAndAppId - NULL != pAppId");
  *a1 = 0;
  *a2 = GUID_NULL;
  CurrentProcess = GetCurrentProcess();
  if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
  {
    if ( GetFullPathNameW(ExeName, 0x105u, Buffer, &FilePart) )
    {
      if ( !_wcsicmp(L"dllhost.exe", FilePart) )
      {
        CommandLineA = GetCommandLineA();
        v11 = strchr(CommandLineA, 32);
        v14 = v11 + 1;
        if ( !v11 )
          v14 = 0;
        if ( v14 )
        {
          strcpy(String2, "/ProcessID");
          String1 = &v29;
          if ( (int)GetCommandLineArguments(v14, &String1, v12, v13) >= 1 )
          {
            v15 = String1;
            for ( i = String1; ; ++i )
            {
              if ( !*i )
                goto LABEL_26;
              v17 = i + 1;
              if ( *i == 58 )
                break;
            }
            *i = 0;
            if ( !*v17 || _stricmp(v15, String2) )
LABEL_26:
              v17 = v15;
            if ( (int)StringCchLengthA(v17, 0x29u, &v24) >= 0 )
            {
              if ( MultiByteToWideChar(0, 0, v17, v24 + 1, WideCharStr, v18) )
              {
                if ( CLSIDFromString(WideCharStr, &pclsid) < 0 )
                  TraceStringInline(
                    15,
                    4,
                    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
                    296,
                    L"GetExeNameAndAppId",
                    0,
                    L"Unable to convert command line argument to a GUID, skipping AppId.");
              }
              else
              {
                TraceStringInline(
                  15,
                  4,
                  L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
                  288,
                  L"GetExeNameAndAppId",
                  0,
                  L"Unable to convert command line argument to WCHAR, skipping AppId.");
              }
            }
            else
            {
              TraceStringInline(
                15,
                4,
                L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
                280,
                L"GetExeNameAndAppId",
                0,
                L"Unable to get AppId string length, skipping AppId.");
            }
          }
          else
          {
            TraceStringInline(
              15,
              4,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
              255,
              L"GetExeNameAndAppId",
              0,
              L"CommandLine has no arguments, skipping AppId.");
          }
        }
      }
      v6 = DuplicateString(ExeName, a1);
      if ( (v6 & 0x80000000) == 0 )
      {
        *a2 = pclsid;
        return v6;
      }
      v7 = L"DuplicateString for ExeName failed.";
      v8 = 309;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = L"GetFullPathNameW failed";
      v8 = 203;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = L"QueryFullProcessImageNameW failed";
    v8 = 190;
  }
  cchWideChar[0] = v6;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dllgettmcore.cpp",
    v8,
    L"GetExeNameAndAppId",
    *(_QWORD *)cchWideChar,
    v7);
  return v6;
}

```

## disassembly

```asm
0x180014e80  mov     [rsp-8+arg_10], rbx
0x180014e85  push    rbp
0x180014e86  push    r12
0x180014e88  push    r13
0x180014e8a  push    r14
0x180014e8c  push    r15
0x180014e8e  lea     rbp, [rsp-520h]
0x180014e96  sub     rsp, 620h
0x180014e9d  mov     rax, cs:__security_cookie
0x180014ea4  xor     rax, rsp
0x180014ea7  mov     [rbp+540h+var_30], rax
0x180014eae  mov     [rsp+640h+FilePart], 0
0x180014eb7  mov     ebx, 105h
0x180014ebc  mov     [rsp+640h+dwSize], ebx
0x180014ec0  mov     r12, rdx
0x180014ec3  mov     [rsp+640h+var_5E8], 0
0x180014ecc  mov     r13, rcx
0x180014ecf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014ed6  movdqu  xmmword ptr [rsp+640h+pclsid.Data1], xmm0
0x180014edc  test    rcx, rcx
0x180014edf  jnz     short loc_180014EEE
0x180014ee1  lea     rcx, aGetexenameanda; "GetExeNameAndAppId (com\\complus\\dtc\\"...
0x180014ee8  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180014eee  test    r12, r12
0x180014ef1  jnz     short loc_180014F00
0x180014ef3  lea     rcx, aGetexenameanda_1; "GetExeNameAndAppId (com\\complus\\dtc\\"...
0x180014efa  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180014f00  mov     qword ptr [rcx], 0
0x180014f07  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014f0e  movdqu  xmmword ptr [rdx], xmm0
0x180014f12  call    cs:__imp_GetCurrentProcess
0x180014f18  lea     r9, [rsp+640h+dwSize]; lpdwSize
0x180014f1d  xor     edx, edx; dwFlags
0x180014f1f  mov     rcx, rax; hProcess
0x180014f22  lea     r8, [rbp+540h+ExeName]; lpExeName
0x180014f26  call    cs:__imp_QueryFullProcessImageNameW
0x180014f2c  test    eax, eax
0x180014f2e  jnz     short loc_180014F80
0x180014f30  call    cs:__imp_GetLastError
0x180014f36  mov     ebx, eax
0x180014f38  test    eax, eax
0x180014f3a  jle     short loc_180014F45
0x180014f3c  movzx   ebx, ax
0x180014f3f  or      ebx, 80070000h
0x180014f45  lea     rax, aQueryfullproce; "QueryFullProcessImageNameW failed"
0x180014f4c  mov     r9d, 0BEh
0x180014f52  lea     r14, aGetexenameanda_2; "GetExeNameAndAppId"
0x180014f59  mov     [rsp+640h+var_610], rax
0x180014f5e  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180014f65  mov     edx, 1
0x180014f6a  mov     [rsp+640h+cchWideChar], ebx
0x180014f6e  mov     [rsp+640h+lpWideCharStr], r14
0x180014f73  lea     ecx, [rdx+0Eh]
0x180014f76  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014f7b  jmp     loc_18001515C
0x180014f80  lea     r9, [rsp+640h+FilePart]; lpFilePart
0x180014f85  mov     edx, ebx; nBufferLength
0x180014f87  lea     r8, [rbp+540h+Buffer]; lpBuffer
0x180014f8e  lea     rcx, [rbp+540h+ExeName]; lpFileName
0x180014f92  call    cs:__imp_GetFullPathNameW
0x180014f98  test    eax, eax
0x180014f9a  jnz     short loc_180014FC0
0x180014f9c  call    cs:__imp_GetLastError
0x180014fa2  mov     ebx, eax
0x180014fa4  test    eax, eax
0x180014fa6  jle     short loc_180014FB1
0x180014fa8  movzx   ebx, ax
0x180014fab  or      ebx, 80070000h
0x180014fb1  lea     rax, aGetfullpathnam_0; "GetFullPathNameW failed"
0x180014fb8  mov     r9d, 0CBh
0x180014fbe  jmp     short loc_180014F52
0x180014fc0  mov     rdx, [rsp+640h+FilePart]; String2
0x180014fc5  lea     rcx, aDllhostExe; "dllhost.exe"
0x180014fcc  call    cs:__imp__wcsicmp
0x180014fd2  lea     r14, aGetexenameanda_2; "GetExeNameAndAppId"
0x180014fd9  test    eax, eax
0x180014fdb  jnz     loc_18001512D
0x180014fe1  call    cs:__imp_GetCommandLineA
0x180014fe7  mov     rcx, rax; Str
0x180014fea  mov     edx, 20h ; ' '; Val
0x180014fef  call    cs:__imp_strchr
0x180014ff5  test    rax, rax
0x180014ff8  lea     rcx, [rax+1]
0x180014ffc  cmovz   rcx, rax; char *
0x180015000  test    rcx, rcx
0x180015003  jz      loc_18001512D
0x180015009  mov     eax, dword ptr cs:aProcessid+7; "sID"
0x18001500f  lea     rdx, [rsp+640h+String1]; char **
0x180015014  movsd   xmm0, qword ptr cs:aProcessid; "/ProcessID"
0x18001501c  movsd   qword ptr [rsp+640h+String2], xmm0
0x180015022  mov     dword ptr [rsp+640h+String2+7], eax
0x180015026  lea     rax, [rbp+540h+var_350]
0x18001502d  mov     [rsp+640h+String1], rax
0x180015032  call    ?GetCommandLineArguments@@YAHPEADQEAPEADHH@Z; GetCommandLineArguments(char *,char * * const,int,int)
0x180015037  cmp     eax, 1
0x18001503a  jge     short loc_18001504E
0x18001503c  lea     rax, aCommandlineHas; "CommandLine has no arguments, skipping "...
0x180015043  mov     r9d, 0FFh
0x180015049  jmp     loc_180015106
0x18001504e  mov     rbx, [rsp+640h+String1]
0x180015053  mov     rax, rbx
0x180015056  cmp     byte ptr [rax], 0
0x180015059  jz      short loc_180015084
0x18001505b  cmp     byte ptr [rax], 3Ah ; ':'
0x18001505e  lea     r15, [rax+1]
0x180015062  jz      short loc_180015069
0x180015064  mov     rax, r15
0x180015067  jmp     short loc_180015056
0x180015069  mov     byte ptr [rax], 0
0x18001506c  cmp     byte ptr [r15], 0
0x180015070  jz      short loc_180015084
0x180015072  lea     rdx, [rsp+640h+String2]; String2
0x180015077  mov     rcx, rbx; String1
0x18001507a  call    cs:__imp__stricmp
0x180015080  test    eax, eax
0x180015082  jz      short loc_180015087
0x180015084  mov     r15, rbx
0x180015087  mov     r11d, 29h ; ')'
0x18001508d  lea     r8, [rsp+640h+var_5E8]; unsigned __int64 *
0x180015092  mov     edx, r11d; unsigned __int64
0x180015095  mov     rcx, r15; char *
0x180015098  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18001509d  test    eax, eax
0x18001509f  jns     short loc_1800150B0
0x1800150a1  lea     rax, aUnableToGetApp; "Unable to get AppId string length, skip"...
0x1800150a8  mov     r9d, 118h
0x1800150ae  jmp     short loc_180015106
0x1800150b0  mov     r9d, dword ptr [rsp+640h+var_5E8]
0x1800150b5  lea     rax, [rbp+540h+WideCharStr]
0x1800150b9  mov     [rsp+640h+cchWideChar], r11d; cchWideChar
0x1800150be  inc     r9d; cbMultiByte
0x1800150c1  mov     r8, r15; lpMultiByteStr
0x1800150c4  mov     [rsp+640h+lpWideCharStr], rax; lpWideCharStr
0x1800150c9  xor     edx, edx; dwFlags
0x1800150cb  xor     ecx, ecx; CodePage
0x1800150cd  call    cs:__imp_MultiByteToWideChar
0x1800150d3  test    eax, eax
0x1800150d5  jnz     short loc_1800150E6
0x1800150d7  lea     rax, aUnableToConver_0; "Unable to convert command line argument"...
0x1800150de  mov     r9d, 120h
0x1800150e4  jmp     short loc_180015106
0x1800150e6  lea     rdx, [rsp+640h+pclsid]; pclsid
0x1800150eb  lea     rcx, [rbp+540h+WideCharStr]; lpsz
0x1800150ef  call    cs:__imp_CLSIDFromString
0x1800150f5  test    eax, eax
0x1800150f7  jns     short loc_18001512D
0x1800150f9  lea     rax, aUnableToConver; "Unable to convert command line argument"...
0x180015100  mov     r9d, 128h
0x180015106  mov     [rsp+640h+var_610], rax
0x18001510b  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180015112  mov     edx, 4
0x180015117  mov     qword ptr [rsp+640h+cchWideChar], 0
0x180015120  mov     [rsp+640h+lpWideCharStr], r14
0x180015125  lea     ecx, [rdx+0Bh]
0x180015128  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001512d  mov     rdx, r13; unsigned __int16 **
0x180015130  lea     rcx, [rbp+540h+ExeName]; unsigned __int16 *
0x180015134  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180015139  mov     ebx, eax
0x18001513b  test    eax, eax
0x18001513d  jns     short loc_180015151
0x18001513f  lea     rax, aDuplicatestrin; "DuplicateString for ExeName failed."
0x180015146  mov     r9d, 135h
0x18001514c  jmp     loc_180014F59
0x180015151  movups  xmm0, xmmword ptr [rsp+640h+pclsid.Data1]
0x180015156  movdqu  xmmword ptr [r12], xmm0
0x18001515c  mov     eax, ebx
0x18001515e  mov     rcx, [rbp+540h+var_30]
0x180015165  xor     rcx, rsp; StackCookie
0x180015168  call    __security_check_cookie
0x18001516d  mov     rbx, [rsp+640h+arg_10]
0x180015175  add     rsp, 620h
0x18001517c  pop     r15
0x18001517e  pop     r14
0x180015180  pop     r13
0x180015182  pop     r12
0x180015184  pop     rbp
0x180015185  retn
```
