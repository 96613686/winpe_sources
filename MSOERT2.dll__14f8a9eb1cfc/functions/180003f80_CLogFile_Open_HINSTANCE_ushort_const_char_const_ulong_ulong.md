# CLogFile::Open(HINSTANCE__ *,ushort const *,char const *,ulong,ulong)

- ea: `0x180003f80`
- end: `0x1800044fe`
- name: `?Open@CLogFile@@UEAAJPEAUHINSTANCE__@@PEBGPEBDKK@Z`
- size: `1406`
- prototype: `int(CLogFile *__hidden this, HINSTANCE, const unsigned __int16 *, const char *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callees

- `0x180001c80`
- `0x180003614`
- `0x180003dc0`
- `0x180003f80`
- `0x1800045a0`
- `0x180004640`
- `0x1800046b4`
- `0x18000470c`
- `0x180011a78`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004159`
- `KERNEL32!GetLastError` at `0x180004159`
- `KERNEL32!GetModuleFileNameA` at `0x18000422d`
- `KERNEL32!GetModuleFileNameA` at `0x18000422d`
- `KERNEL32!CreateMutexW` at `0x180004049`
- `KERNEL32!CreateMutexW` at `0x180004049`
- `KERNEL32!WaitForSingleObject` at `0x180004068`
- `KERNEL32!WaitForSingleObject` at `0x180004068`
- `KERNEL32!CreateFileW` at `0x18000414a`
- `KERNEL32!CreateFileW` at `0x18000414a`
- `KERNEL32!GetFileSize` at `0x18000419f`
- `KERNEL32!GetFileSize` at `0x18000419f`
- `KERNEL32!SetFilePointer` at `0x1800041c0`
- `KERNEL32!SetFilePointer` at `0x1800041ef`
- `KERNEL32!SetFilePointer` at `0x1800041c0`
- `KERNEL32!SetFilePointer` at `0x1800041ef`
- `KERNEL32!SetEndOfFile` at `0x1800041d2`
- `KERNEL32!SetEndOfFile` at `0x1800041d2`
- `KERNEL32!GetLocalTime` at `0x18000446c`
- `KERNEL32!GetLocalTime` at `0x18000446c`
- `KERNEL32!WriteFile` at `0x1800044f3`
- `KERNEL32!WriteFile` at `0x1800044f3`
- `KERNEL32!ReleaseMutex` at `0x18000424a`
- `KERNEL32!ReleaseMutex` at `0x18000424a`
- `SHLWAPI!PathFindExtensionW` at `0x18000409a`
- `SHLWAPI!PathFindExtensionW` at `0x18000409a`
- `VERSION!GetFileVersionInfoSizeA` at `0x1800042c5`
- `VERSION!GetFileVersionInfoSizeA` at `0x1800042c5`
- `VERSION!VerQueryValueA` at `0x18000432b`
- `VERSION!VerQueryValueA` at `0x1800043b0`
- `VERSION!VerQueryValueA` at `0x18000443c`
- `VERSION!VerQueryValueA` at `0x18000432b`
- `VERSION!VerQueryValueA` at `0x1800043b0`
- `VERSION!VerQueryValueA` at `0x18000443c`
- `VERSION!GetFileVersionInfoA` at `0x18000430a`
- `VERSION!GetFileVersionInfoA` at `0x18000430a`

## pseudocode

```c
__int64 __fastcall CLogFile::Open(
        CLogFile *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        const char *a4,
        DWORD a5,
        DWORD dwShareMode)
{
  const char *v8; // r8
  int SystemHandleName; // ebx
  HANDLE MutexW; // rax
  const void *v11; // r14
  LPWSTR ExtensionW; // r11
  _WORD *v13; // r11
  int v14; // ebx
  __int64 v15; // rsi
  HANDLE FileW; // rax
  void *v17; // rcx
  DWORD FileSize; // eax
  DWORD ModuleFileNameA; // eax
  DWORD FileVersionInfoSizeA; // eax
  DWORD v22; // edi
  void *v23; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // rdi
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwHandle; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  char *v32; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpName; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpBuffer; // [rsp+80h] [rbp-80h] BYREF
  HMODULE hModule; // [rsp+88h] [rbp-78h]
  const char *v36; // [rsp+90h] [rbp-70h]
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v38; // [rsp+A8h] [rbp-58h] BYREF
  CHAR Filename[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR SubBlock[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v41[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR FileName[264]; // [rsp+3E0h] [rbp+2E0h] BYREF
  WCHAR pszPath[264]; // [rsp+5F0h] [rbp+4F0h] BYREF

  hModule = a2;
  v36 = a4;
  dwHandle = 0;
  v8 = a4;
  puLen = 0;
  if ( !a4 )
    v8 = &byte_180016957;
  lpBuffer = 0;
  v32 = 0;
  NumberOfBytesWritten = 0;
  lpName = 0;
  SystemTime = 0;
  SystemHandleName = StringCchCopyA((char *)this + 24, 0xAu, v8);
  if ( SystemHandleName >= 0 )
  {
    SystemHandleName = CreateSystemHandleName(a3, L"logfile", (unsigned __int16 **)&lpName);
    if ( SystemHandleName >= 0 )
    {
      MutexW = CreateMutexW(0, 0, lpName);
      *((_QWORD *)this + 5) = MutexW;
      if ( MutexW && !WaitForSingleObject(MutexW, 0xFFFFFFFF) )
      {
        v11 = 0;
        SystemHandleName = StringCchCopyW(pszPath, 0x106u, a3);
        if ( SystemHandleName < 0 )
          goto LABEL_29;
        ExtensionW = PathFindExtensionW(pszPath);
        if ( ExtensionW && *ExtensionW == 46 )
        {
          SystemHandleName = StringCchCopyW(&v38, 4u, ExtensionW + 1);
          if ( SystemHandleName < 0 )
            goto LABEL_29;
          *v13 = 0;
        }
        else
        {
          SystemHandleName = StringCchCopyW(&v38, 4u, L"log");
          if ( SystemHandleName < 0 )
            goto LABEL_29;
        }
        v14 = 0;
        StringCchPrintfW(FileName, 0x104u, L"%s.%s", pszPath, &v38);
        v15 = -1;
        do
        {
          FileW = CreateFileW(FileName, 0x40000000u, dwShareMode, 0, 4u, 0x80u, 0);
          *((_QWORD *)this + 2) = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            if ( GetLastError() != 32 )
              goto LABEL_34;
            dwCreationDisposition[0] = ++v14;
            StringCchPrintfW(FileName, 0x104u, L"%s (%d).%s", pszPath, *(_QWORD *)dwCreationDisposition, &v38);
          }
          v17 = (void *)*((_QWORD *)this + 2);
        }
        while ( v17 == (void *)-1LL );
        FileSize = GetFileSize(v17, 0);
        if ( FileSize != -1
          && (FileSize >= a5
           && (SetFilePointer(*((HANDLE *)this + 2), 0, 0, 0) == -1 || !SetEndOfFile(*((HANDLE *)this + 2)))
           || SetFilePointer(*((HANDLE *)this + 2), 0, 0, 2u) == -1) )
        {
LABEL_34:
          SystemHandleName = -2147467259;
          goto LABEL_29;
        }
        SystemHandleName = HrSHUnicodeToAnsiCP(0, FileName, Filename, 260, &NumberOfBytesWritten);
        if ( SystemHandleName < 0 )
          goto LABEL_29;
        ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x104u);
        if ( !ModuleFileNameA )
          goto LABEL_28;
        if ( ModuleFileNameA >= 0x104 )
        {
          Filename[0] = 0;
LABEL_28:
          SystemHandleName = HrGetLastError();
          goto LABEL_29;
        }
        v41[0] = 0;
        FileVersionInfoSizeA = GetFileVersionInfoSizeA(Filename, &dwHandle);
        v22 = FileVersionInfoSizeA;
        if ( !FileVersionInfoSizeA )
          goto LABEL_52;
        v23 = (void *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(
                        g_pMalloc,
                        FileVersionInfoSizeA);
        v11 = v23;
        if ( !v23 )
        {
          SystemHandleName = -2147024882;
          goto LABEL_29;
        }
        if ( !GetFileVersionInfoA(Filename, dwHandle, v22, v23)
          || !VerQueryValueA(v11, "\\VarFileInfo\\Translation", &lpBuffer, &puLen)
          || puLen < 4 )
        {
          goto LABEL_52;
        }
        StringCchPrintfA(
          SubBlock,
          0x104u,
          "\\StringFileInfo\\%04X%04X\\",
          *(unsigned __int16 *)lpBuffer,
          *((unsigned __int16 *)lpBuffer + 1));
        v25 = -1;
        do
          ++v25;
        while ( SubBlock[v25] );
        SystemHandleName = StringCchCatA(SubBlock, v24, "FileDescription");
        if ( SystemHandleName >= 0 )
        {
          if ( !VerQueryValueA(v11, SubBlock, (LPVOID *)&v32, &puLen)
            || !puLen
            || (SystemHandleName = StringCchCopyA(v41, 0x104u, v32), SystemHandleName >= 0)
            && (SystemHandleName = StringCchCatA(v41, v26, " "), SystemHandleName >= 0) )
          {
            SystemHandleName = StringCchCopyA(&SubBlock[(unsigned int)v25], 260LL - (unsigned int)v25, "FileVersion");
            if ( SystemHandleName >= 0 )
            {
              if ( !VerQueryValueA(v11, SubBlock, (LPVOID *)&v32, &puLen)
                || !puLen
                || (SystemHandleName = StringCchCatA(v41, v27, v32), SystemHandleName >= 0) )
              {
LABEL_52:
                GetLocalTime(&SystemTime);
                StringCchPrintfA(
                  Filename,
                  0x104u,
                  "\r\n%s\r\n%s Log started at %.2d/%.2d/%.4d %.2d:%.2d:%.2d\r\n",
                  v41,
                  v36,
                  SystemTime.wMonth,
                  SystemTime.wDay,
                  SystemTime.wYear,
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond);
                do
                  ++v15;
                while ( Filename[v15] );
                WriteFile(*((HANDLE *)this + 2), Filename, v15, &NumberOfBytesWritten, 0);
              }
            }
          }
        }
LABEL_29:
        ReleaseMutex(*((HANDLE *)this + 5));
        if ( v11 )
          ((void (__fastcall *)(LPMALLOC, const void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v11);
        goto LABEL_31;
      }
      SystemHandleName = -2147467259;
    }
LABEL_31:
    if ( lpName )
      ((void (__fastcall *)(LPMALLOC, LPCWSTR))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpName);
  }
  return (unsigned int)SystemHandleName;
}

```

## disassembly

```asm
0x180003f80  push    rbp
0x180003f82  push    rbx
0x180003f83  push    rsi
0x180003f84  push    rdi
0x180003f85  push    r13
0x180003f87  push    r14
0x180003f89  push    r15
0x180003f8b  lea     rbp, [rsp-710h]
0x180003f93  sub     rsp, 810h
0x180003f9a  mov     rax, cs:__security_cookie
0x180003fa1  xor     rax, rsp
0x180003fa4  mov     [rbp+740h+var_40], rax
0x180003fab  mov     r13d, [rbp+740h+dwShareMode]
0x180003fb2  mov     r15, rcx
0x180003fb5  mov     rdi, r8
0x180003fb8  mov     [rbp+740h+hModule], rdx
0x180003fbc  test    r9, r9
0x180003fbf  mov     [rbp+740h+var_7B0], r9
0x180003fc3  lea     rcx, byte_180016957
0x180003fca  mov     [rsp+840h+dwHandle], 0
0x180003fd2  mov     r8, r9
0x180003fd5  mov     [rsp+840h+puLen], 0
0x180003fdd  cmovz   r8, rcx; char *
0x180003fe1  mov     [rbp+740h+lpBuffer], 0
0x180003fe9  xorps   xmm0, xmm0
0x180003fec  mov     [rsp+840h+var_7D0], 0
0x180003ff5  lea     rcx, [r15+18h]; char *
0x180003ff9  mov     [rsp+840h+NumberOfBytesWritten], 0
0x180004001  mov     edx, 0Ah; unsigned __int64
0x180004006  mov     [rsp+840h+lpName], 0
0x18000400f  movups  xmmword ptr [rbp+740h+SystemTime.wYear], xmm0
0x180004013  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180004018  mov     ebx, eax
0x18000401a  test    eax, eax
0x18000401c  js      loc_18000428B
0x180004022  lea     r8, [rsp+840h+lpName]; unsigned __int16 **
0x180004027  mov     rcx, rdi; unsigned __int16 *
0x18000402a  lea     rdx, aLogfile; "logfile"
0x180004031  call    ?CreateSystemHandleName@@YAJPEBG0PEAPEAG@Z; CreateSystemHandleName(ushort const *,ushort const *,ushort * *)
0x180004036  mov     ebx, eax
0x180004038  test    eax, eax
0x18000403a  js      loc_18000426B
0x180004040  mov     r8, [rsp+840h+lpName]; lpName
0x180004045  xor     edx, edx; bInitialOwner
0x180004047  xor     ecx, ecx; lpMutexAttributes
0x180004049  call    cs:__imp_CreateMutexW
0x18000404f  mov     [r15+28h], rax
0x180004053  test    rax, rax
0x180004056  jnz     short loc_180004062
0x180004058  mov     ebx, 80004005h
0x18000405d  jmp     loc_18000426B
0x180004062  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004065  mov     rcx, rax; hHandle
0x180004068  call    cs:__imp_WaitForSingleObject
0x18000406e  test    eax, eax
0x180004070  jnz     short loc_180004058
0x180004072  mov     r8, rdi; unsigned __int16 *
0x180004075  lea     rcx, [rbp+740h+pszPath]; unsigned __int16 *
0x18000407c  mov     edx, 106h; unsigned __int64
0x180004081  xor     r14d, r14d
0x180004084  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004089  mov     ebx, eax
0x18000408b  test    eax, eax
0x18000408d  js      loc_180004246
0x180004093  lea     rcx, [rbp+740h+pszPath]; pszPath
0x18000409a  call    cs:__imp_PathFindExtensionW
0x1800040a0  mov     r11, rax
0x1800040a3  test    rax, rax
0x1800040a6  jz      short loc_1800040D4
0x1800040a8  lea     eax, [r14+2Eh]
0x1800040ac  cmp     ax, [r11]
0x1800040b0  jnz     short loc_1800040D4
0x1800040b2  lea     r8, [r11+2]; unsigned __int16 *
0x1800040b6  lea     edx, [rax-2Ah]; unsigned __int64
0x1800040b9  lea     rcx, [rbp+740h+var_798]; unsigned __int16 *
0x1800040bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800040c2  mov     ebx, eax
0x1800040c4  test    eax, eax
0x1800040c6  js      loc_180004246
0x1800040cc  xor     eax, eax
0x1800040ce  mov     [r11], ax
0x1800040d2  jmp     short loc_1800040F3
0x1800040d4  lea     r8, aLog; "log"
0x1800040db  mov     edx, 4; unsigned __int64
0x1800040e0  lea     rcx, [rbp+740h+var_798]; unsigned __int16 *
0x1800040e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800040e9  mov     ebx, eax
0x1800040eb  test    eax, eax
0x1800040ed  js      loc_180004246
0x1800040f3  lea     rax, [rbp+740h+var_798]
0x1800040f7  mov     edi, 104h
0x1800040fc  mov     edx, edi; unsigned __int64
0x1800040fe  mov     qword ptr [rsp+840h+dwCreationDisposition], rax
0x180004103  lea     r9, [rbp+740h+pszPath]
0x18000410a  xor     ebx, ebx
0x18000410c  lea     r8, aSS; "%s.%s"
0x180004113  lea     rcx, [rbp+740h+FileName]; unsigned __int16 *
0x18000411a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000411f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004123  mov     [rsp+840h+hTemplateFile], r14; hTemplateFile
0x180004128  lea     rcx, [rbp+740h+FileName]; lpFileName
0x18000412f  mov     [rsp+840h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004137  xor     r9d, r9d; lpSecurityAttributes
0x18000413a  mov     r8d, r13d; dwShareMode
0x18000413d  mov     [rsp+840h+dwCreationDisposition], 4; dwCreationDisposition
0x180004145  mov     edx, 40000000h; dwDesiredAccess
0x18000414a  call    cs:__imp_CreateFileW
0x180004150  mov     [r15+10h], rax
0x180004154  cmp     rax, rsi
0x180004157  jnz     short loc_180004194
0x180004159  call    cs:__imp_GetLastError
0x18000415f  cmp     eax, 20h ; ' '
0x180004162  jnz     loc_1800042AE
0x180004168  lea     rax, [rbp+740h+var_798]
0x18000416c  inc     ebx
0x18000416e  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], rax
0x180004173  lea     r9, [rbp+740h+pszPath]
0x18000417a  lea     r8, aSDS; "%s (%d).%s"
0x180004181  mov     [rsp+840h+dwCreationDisposition], ebx
0x180004185  mov     rdx, rdi; unsigned __int64
0x180004188  lea     rcx, [rbp+740h+FileName]; unsigned __int16 *
0x18000418f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004194  mov     rcx, [r15+10h]; hFile
0x180004198  cmp     rcx, rsi
0x18000419b  jz      short loc_180004123
0x18000419d  xor     edx, edx; lpFileSizeHigh
0x18000419f  call    cs:__imp_GetFileSize
0x1800041a5  or      ebx, 0FFFFFFFFh
0x1800041a8  cmp     eax, ebx
0x1800041aa  jz      short loc_1800041FD
0x1800041ac  cmp     eax, [rbp+740h+arg_20]
0x1800041b2  jb      short loc_1800041E0
0x1800041b4  mov     rcx, [r15+10h]; hFile
0x1800041b8  xor     r9d, r9d; dwMoveMethod
0x1800041bb  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800041be  xor     edx, edx; lDistanceToMove
0x1800041c0  call    cs:__imp_SetFilePointer
0x1800041c6  cmp     eax, ebx
0x1800041c8  jz      loc_1800042AE
0x1800041ce  mov     rcx, [r15+10h]; hFile
0x1800041d2  call    cs:__imp_SetEndOfFile
0x1800041d8  test    eax, eax
0x1800041da  jz      loc_1800042AE
0x1800041e0  mov     rcx, [r15+10h]; hFile
0x1800041e4  mov     r9d, 2; dwMoveMethod
0x1800041ea  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800041ed  xor     edx, edx; lDistanceToMove
0x1800041ef  call    cs:__imp_SetFilePointer
0x1800041f5  cmp     eax, ebx
0x1800041f7  jz      loc_1800042AE
0x1800041fd  lea     rax, [rsp+840h+NumberOfBytesWritten]
0x180004202  mov     r9d, edi; int
0x180004205  lea     r8, [rbp+740h+Filename]; char *
0x180004209  mov     qword ptr [rsp+840h+dwCreationDisposition], rax; unsigned int *
0x18000420e  lea     rdx, [rbp+740h+FileName]; unsigned __int16 *
0x180004215  xor     ecx, ecx; unsigned int
0x180004217  call    ?HrSHUnicodeToAnsiCP@@YAJIPEBGPEADHPEAK@Z; HrSHUnicodeToAnsiCP(uint,ushort const *,char *,int,ulong *)
0x18000421c  mov     ebx, eax
0x18000421e  test    eax, eax
0x180004220  js      short loc_180004246
0x180004222  mov     rcx, [rbp+740h+hModule]; hModule
0x180004226  lea     rdx, [rbp+740h+Filename]; lpFilename
0x18000422a  mov     r8d, edi; nSize
0x18000422d  call    cs:__imp_GetModuleFileNameA
0x180004233  test    eax, eax
0x180004235  jz      short loc_18000423F
0x180004237  cmp     eax, edi
0x180004239  jb      short loc_1800042B5
0x18000423b  mov     [rbp+740h+Filename], r14b
0x18000423f  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180004244  mov     ebx, eax
0x180004246  mov     rcx, [r15+28h]; hMutex
0x18000424a  call    cs:__imp_ReleaseMutex
0x180004250  test    r14, r14
0x180004253  jz      short loc_18000426B
0x180004255  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000425c  mov     rdx, r14
0x18000425f  mov     rax, [rcx]
0x180004262  mov     rax, [rax+28h]
0x180004266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426b  cmp     [rsp+840h+lpName], 0
0x180004271  jz      short loc_18000428B
0x180004273  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000427a  mov     rdx, [rsp+840h+lpName]
0x18000427f  mov     rax, [rcx]
0x180004282  mov     rax, [rax+28h]
0x180004286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428b  mov     eax, ebx
0x18000428d  mov     rcx, [rbp+740h+var_40]
0x180004294  xor     rcx, rsp; StackCookie
0x180004297  call    __security_check_cookie
0x18000429c  add     rsp, 810h
0x1800042a3  pop     r15
0x1800042a5  pop     r14
0x1800042a7  pop     r13
0x1800042a9  pop     rdi
0x1800042aa  pop     rsi
0x1800042ab  pop     rbx
0x1800042ac  pop     rbp
0x1800042ad  retn
0x1800042ae  mov     ebx, 80004005h
0x1800042b3  jmp     short loc_180004246
0x1800042b5  lea     rdx, [rsp+840h+dwHandle]; lpdwHandle
0x1800042ba  mov     [rbp+740h+var_570], r14b
0x1800042c1  lea     rcx, [rbp+740h+Filename]; lptstrFilename
0x1800042c5  call    cs:__imp_GetFileVersionInfoSizeA
0x1800042cb  mov     edi, eax
0x1800042cd  test    eax, eax
0x1800042cf  jz      loc_180004468
0x1800042d5  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800042dc  mov     edx, edi
0x1800042de  mov     r8, [rcx]
0x1800042e1  mov     rax, [r8+18h]
0x1800042e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ea  mov     r14, rax
0x1800042ed  test    rax, rax
0x1800042f0  jnz     short loc_1800042FC
0x1800042f2  mov     ebx, 8007000Eh
0x1800042f7  jmp     loc_180004246
0x1800042fc  mov     edx, [rsp+840h+dwHandle]; dwHandle
0x180004300  lea     rcx, [rbp+740h+Filename]; lptstrFilename
0x180004304  mov     r9, r14; lpData
0x180004307  mov     r8d, edi; dwLen
0x18000430a  call    cs:__imp_GetFileVersionInfoA
0x180004310  test    eax, eax
0x180004312  jz      loc_180004468
0x180004318  lea     r9, [rsp+840h+puLen]; puLen
0x18000431d  mov     rcx, r14; pBlock
0x180004320  lea     r8, [rbp+740h+lpBuffer]; lplpBuffer
0x180004324  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18000432b  call    cs:__imp_VerQueryValueA
0x180004331  test    eax, eax
0x180004333  jz      loc_180004468
0x180004339  cmp     [rsp+840h+puLen], 4
0x18000433e  jb      loc_180004468
0x180004344  mov     rax, [rbp+740h+lpBuffer]
0x180004348  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\"
0x18000434f  mov     edx, 104h; unsigned __int64
0x180004354  movzx   ecx, word ptr [rax+2]
0x180004358  movzx   r9d, word ptr [rax]
0x18000435c  mov     [rsp+840h+dwCreationDisposition], ecx
0x180004360  lea     rcx, [rbp+740h+SubBlock]; char *
0x180004367  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000436c  lea     rax, [rbp+740h+SubBlock]
0x180004373  mov     rdi, rsi
0x180004376  inc     rdi
0x180004379  cmp     byte ptr [rax+rdi], 0
0x18000437d  jnz     short loc_180004376
0x18000437f  lea     r8, aFiledescriptio; "FileDescription"
0x180004386  lea     rcx, [rbp+740h+SubBlock]; char *
0x18000438d  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180004392  mov     ebx, eax
0x180004394  test    eax, eax
0x180004396  js      loc_180004246
0x18000439c  lea     r9, [rsp+840h+puLen]; puLen
0x1800043a1  mov     rcx, r14; pBlock
0x1800043a4  lea     r8, [rsp+840h+var_7D0]; lplpBuffer
0x1800043a9  lea     rdx, [rbp+740h+SubBlock]; lpSubBlock
0x1800043b0  call    cs:__imp_VerQueryValueA
0x1800043b6  test    eax, eax
0x1800043b8  jz      short loc_1800043FE
0x1800043ba  cmp     [rsp+840h+puLen], 0
0x1800043bf  jz      short loc_1800043FE
0x1800043c1  mov     r8, [rsp+840h+var_7D0]; char *
0x1800043c6  lea     rcx, [rbp+740h+var_570]; char *
0x1800043cd  mov     edx, 104h; unsigned __int64
0x1800043d2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800043d7  mov     ebx, eax
0x1800043d9  test    eax, eax
0x1800043db  js      loc_180004246
0x1800043e1  lea     r8, asc_180016840; " "
0x1800043e8  lea     rcx, [rbp+740h+var_570]; char *
0x1800043ef  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800043f4  mov     ebx, eax
0x1800043f6  test    eax, eax
0x1800043f8  js      loc_180004246
0x1800043fe  mov     eax, edi
0x180004400  lea     rcx, [rbp+740h+SubBlock]
0x180004407  mov     edx, 104h
0x18000440c  lea     r8, aFileversion; "FileVersion"
0x180004413  sub     rdx, rax; unsigned __int64
0x180004416  add     rcx, rax; char *
0x180004419  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000441e  mov     ebx, eax
0x180004420  test    eax, eax
0x180004422  js      loc_180004246
0x180004428  lea     r9, [rsp+840h+puLen]; puLen
0x18000442d  mov     rcx, r14; pBlock
0x180004430  lea     r8, [rsp+840h+var_7D0]; lplpBuffer
0x180004435  lea     rdx, [rbp+740h+SubBlock]; lpSubBlock
0x18000443c  call    cs:__imp_VerQueryValueA
0x180004442  test    eax, eax
0x180004444  jz      short loc_180004468
0x180004446  cmp     [rsp+840h+puLen], 0
0x18000444b  jz      short loc_180004468
0x18000444d  mov     r8, [rsp+840h+var_7D0]; char *
0x180004452  lea     rcx, [rbp+740h+var_570]; char *
0x180004459  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000445e  mov     ebx, eax
0x180004460  test    eax, eax
  ... truncated ...
```
