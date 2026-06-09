# AppReadiness::Tasks::Store::DumpStoreMetdataXmTolFile

- ea: `0x180068390`
- end: `0x180068593`
- name: `AppReadiness::Tasks::Store::DumpStoreMetdataXmTolFile`
- size: `515`
- prototype: `int __fastcall(const wchar_t *, _WORD *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180067d6c`
- `0x180067f58`

## callees

- `0x180009d80`
- `0x18001be10`
- `0x18003e210`
- `0x18003eca8`
- `0x180068390`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068566`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006843c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006843c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068530`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006855d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180068530`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006855d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180068501`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180068501`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800684ce`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800684ce`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180068421`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180068421`

## string_xrefs

- `0x1800683d1`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`
- `0x1800683e4`: `DumpGetMetadataXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int __fastcall AppReadiness::Tasks::Store::DumpStoreMetdataXmTolFile(
        const wchar_t *a1,
        _WORD *a2,
        __int64 a3,
        unsigned int a4)
{
  HANDLE FileW; // rax
  __int64 v7; // rbx
  void *v8; // rdi
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int hTemplateFile; // [rsp+30h] [rbp-D0h]
  int wHour; // [rsp+38h] [rbp-C8h]
  int wMinute; // [rsp+40h] [rbp-C0h]
  int wSecond; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszMore[264]; // [rsp+280h] [rbp+180h] BYREF

  NumberOfBytesWritten = 0;
  LODWORD(FileW) = SHRegGetBOOLWithREGSAM(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness",
                     L"DumpGetMetadataXml",
                     a4,
                     (int *)&NumberOfBytesWritten);
  if ( (int)FileW >= 0 )
  {
    if ( NumberOfBytesWritten )
    {
      memset_0(pszPath, 0, 0x208u);
      LODWORD(FileW) = GetTempPath2W(260, pszPath);
      if ( (_DWORD)FileW )
      {
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        memset_0(pszMore, 0, 0x208u);
        if ( !a1 )
          a1 = L"none";
        wSecond = SystemTime.wSecond;
        wMinute = SystemTime.wMinute;
        wHour = SystemTime.wHour;
        hTemplateFile = SystemTime.wDay;
        dwFlagsAndAttributes = SystemTime.wMonth;
        dwCreationDisposition[0] = SystemTime.wYear;
        LODWORD(FileW) = StringCchPrintfW(
                           pszMore,
                           0x104u,
                           L"ARS-GetMetadata(%ls)-%04d-%02d-%02d-%02d-%02d-%02d.txt",
                           a1,
                           *(_QWORD *)dwCreationDisposition,
                           dwFlagsAndAttributes,
                           hTemplateFile,
                           wHour,
                           wMinute,
                           wSecond);
        if ( (int)FileW >= 0 )
        {
          LODWORD(FileW) = PathCchAppend(pszPath, 0x104u, pszMore);
          if ( (int)FileW >= 0 )
          {
            FileW = CreateFileW(pszPath, 0x40000000u, 0, 0, 2u, 0x20u, 0);
            v7 = -1;
            v8 = FileW;
            if ( FileW != (HANDLE)-1LL )
            {
              NumberOfBytesWritten = 0;
              if ( WriteFile(FileW, &qword_18008D438, 2u, &NumberOfBytesWritten, 0) && a2 )
              {
                do
                  ++v7;
                while ( a2[v7] );
                WriteFile(v8, a2, 2 * v7, &NumberOfBytesWritten, 0);
              }
              LODWORD(FileW) = CloseHandle(v8);
            }
          }
        }
      }
    }
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x180068390  mov     [rsp-8+arg_10], rbx
0x180068395  mov     [rsp-8+arg_18], rsi
0x18006839a  push    rbp
0x18006839b  push    rdi
0x18006839c  push    r14
0x18006839e  lea     rbp, [rsp-3A0h]
0x1800683a6  sub     rsp, 4A0h
0x1800683ad  mov     rax, cs:__security_cookie
0x1800683b4  xor     rax, rsp
0x1800683b7  mov     [rbp+3B0h+var_20], rax
0x1800683be  mov     rsi, rdx
0x1800683c1  lea     rax, [rsp+4B0h+NumberOfBytesWritten]
0x1800683c6  mov     rbx, rcx
0x1800683c9  mov     qword ptr [rsp+4B0h+dwCreationDisposition], rax; int *
0x1800683ce  xor     r14d, r14d
0x1800683d1  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800683d8  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800683df  mov     [rsp+4B0h+NumberOfBytesWritten], r14d
0x1800683e4  lea     r8, aDumpgetmetadat; "DumpGetMetadataXml"
0x1800683eb  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800683f0  test    eax, eax
0x1800683f2  js      loc_18006856C
0x1800683f8  cmp     [rsp+4B0h+NumberOfBytesWritten], r14d
0x1800683fd  jz      loc_18006856C
0x180068403  xor     edx, edx; Val
0x180068405  lea     rcx, [rsp+4B0h+pszPath]; void *
0x18006840a  mov     r8d, 208h; Size
0x180068410  call    memset_0
0x180068415  mov     edi, 104h
0x18006841a  lea     rdx, [rsp+4B0h+pszPath]
0x18006841f  mov     ecx, edi
0x180068421  call    cs:__imp_GetTempPath2W
0x180068427  test    eax, eax
0x180068429  jz      loc_18006856C
0x18006842f  xorps   xmm0, xmm0
0x180068432  lea     rcx, [rsp+4B0h+SystemTime]; lpSystemTime
0x180068437  movups  xmmword ptr [rsp+4B0h+SystemTime.wYear], xmm0
0x18006843c  call    cs:__imp_GetLocalTime
0x180068442  xor     edx, edx; Val
0x180068444  lea     rcx, [rbp+3B0h+pszMore]; void *
0x18006844b  mov     r8d, 208h; Size
0x180068451  call    memset_0
0x180068456  movzx   ecx, [rsp+4B0h+SystemTime.wMinute]
0x18006845b  lea     r11, aNone; "none"
0x180068462  movzx   edx, [rsp+4B0h+SystemTime.wHour]
0x180068467  test    rbx, rbx
0x18006846a  movzx   r8d, [rsp+4B0h+SystemTime.wDay]
0x180068470  movzx   r9d, [rsp+4B0h+SystemTime.wMonth]
0x180068476  cmovz   rbx, r11
0x18006847a  movzx   eax, [rsp+4B0h+SystemTime.wSecond]
0x18006847f  movzx   r10d, [rsp+4B0h+SystemTime.wYear]
0x180068485  mov     [rsp+4B0h+var_468], eax
0x180068489  mov     [rsp+4B0h+var_470], ecx
0x18006848d  lea     rcx, [rbp+3B0h+pszMore]; unsigned __int16 *
0x180068494  mov     [rsp+4B0h+var_478], edx
0x180068498  mov     edx, edi; unsigned __int64
0x18006849a  mov     dword ptr [rsp+4B0h+hTemplateFile], r8d
0x18006849f  lea     r8, aArsGetmetadata; "ARS-GetMetadata(%ls)-%04d-%02d-%02d-%02"...
0x1800684a6  mov     [rsp+4B0h+dwFlagsAndAttributes], r9d
0x1800684ab  mov     r9, rbx
0x1800684ae  mov     [rsp+4B0h+dwCreationDisposition], r10d
0x1800684b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800684b8  test    eax, eax
0x1800684ba  js      loc_18006856C
0x1800684c0  lea     r8, [rbp+3B0h+pszMore]; pszMore
0x1800684c7  mov     edx, edi; cchPath
0x1800684c9  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x1800684ce  call    cs:__imp_PathCchAppend
0x1800684d4  test    eax, eax
0x1800684d6  js      loc_18006856C
0x1800684dc  mov     [rsp+4B0h+hTemplateFile], r14; hTemplateFile
0x1800684e1  lea     rcx, [rsp+4B0h+pszPath]; lpFileName
0x1800684e6  mov     [rsp+4B0h+dwFlagsAndAttributes], 20h ; ' '; dwFlagsAndAttributes
0x1800684ee  xor     r9d, r9d; lpSecurityAttributes
0x1800684f1  xor     r8d, r8d; dwShareMode
0x1800684f4  mov     [rsp+4B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800684fc  mov     edx, 40000000h; dwDesiredAccess
0x180068501  call    cs:__imp_CreateFileW
0x180068507  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006850b  mov     rdi, rax
0x18006850e  cmp     rax, rbx
0x180068511  jz      short loc_18006856C
0x180068513  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180068518  mov     [rsp+4B0h+NumberOfBytesWritten], r14d
0x18006851d  lea     r8d, [r14+2]; nNumberOfBytesToWrite
0x180068521  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r14; lpOverlapped
0x180068526  lea     rdx, qword_18008D438; lpBuffer
0x18006852d  mov     rcx, rax; hFile
0x180068530  call    cs:__imp_WriteFile
0x180068536  test    eax, eax
0x180068538  jz      short loc_180068563
0x18006853a  test    rsi, rsi
0x18006853d  jz      short loc_180068563
0x18006853f  inc     rbx
0x180068542  cmp     [rsi+rbx*2], r14w
0x180068547  jnz     short loc_18006853F
0x180068549  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x18006854d  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r14; lpOverlapped
0x180068552  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180068557  mov     rdx, rsi; lpBuffer
0x18006855a  mov     rcx, rdi; hFile
0x18006855d  call    cs:__imp_WriteFile
0x180068563  mov     rcx, rdi; hObject
0x180068566  call    cs:__imp_CloseHandle
0x18006856c  mov     rcx, [rbp+3B0h+var_20]
0x180068573  xor     rcx, rsp; StackCookie
0x180068576  call    __security_check_cookie
0x18006857b  lea     r11, [rsp+4B0h+var_10]
0x180068583  mov     rbx, [r11+30h]
0x180068587  mov     rsi, [r11+38h]
0x18006858b  mov     rsp, r11
0x18006858e  pop     r14
0x180068590  pop     rdi
0x180068591  pop     rbp
0x180068592  retn
```
