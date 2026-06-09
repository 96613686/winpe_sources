# CLogger::Write(LogLevel,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)

- ea: `0x180038dd0`
- end: `0x1800391b6`
- name: `?Write@CLogger@@QEAAXW4LogLevel@@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `998`
- prototype: `void __fastcall(CLogger *this, int, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1800391bc`

## callees

- `0x180002300`
- `0x180002714`
- `0x180002a40`
- `0x18000306c`
- `0x18000e6e0`
- `0x18000ee70`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x180037098`
- `0x1800379b0`
- `0x180038018`
- `0x1800380cc`
- `0x180038730`
- `0x180038c10`
- `0x180038d50`
- `0x180038dd0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wctomb` at `0x180039114`
- `api-ms-win-crt-private-l1-1-0!_o_wctomb` at `0x180039114`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180038fb6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180038fb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038f7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038f7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038fe6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038fe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038f8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039000`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039008`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039008`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180039167`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180039167`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039150`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180039150`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180038f46`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180038f64`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180038f46`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180038f64`

## string_xrefs

- `0x180038f3f`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`
- `0x180038f5d`: `psapi.dll`

## pseudocode

```c
void __fastcall CLogger::Write(CLogger *this, int a2, _QWORD *a3)
{
  __int64 v6; // r13
  __int64 v7; // rdx
  int *v8; // r15
  __int64 v9; // rbx
  int v10; // edi
  int v11; // edi
  const char *v12; // rdx
  HMODULE LibraryW; // rax
  HMODULE v14; // rbx
  const CHAR *v15; // rdx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess; // rax
  char *v18; // rax
  char *v19; // rdx
  __int64 v20; // r8
  DWORD CurrentProcessId; // edi
  DWORD CurrentThreadId; // ebx
  wchar_t *v23; // rbx
  wchar_t *v24; // r12
  int v25; // edi
  char *v26; // r13
  char *v27; // r15
  __int64 v28; // rax
  unsigned __int8 v29[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v30[2]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v33; // [rsp+50h] [rbp-B0h]
  char Str[272]; // [rsp+60h] [rbp-A0h] BYREF
  char v35[1024]; // [rsp+170h] [rbp+70h] BYREF

  v33 = a3;
  v6 = -1;
  if ( *((_QWORD *)this + 6) == -1
    || *((_DWORD *)this + 14) > a2
    || (unsigned int)(*((_DWORD *)this + 16) + *((_DWORD *)this + 15) + *(_DWORD *)(*a3 - 16LL)) > 0x80000
    && !(unsigned int)CLogger::RollOver(this) )
  {
    goto LABEL_49;
  }
  ATL::CTime::GetTickCount(v32);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v30);
  v7 = *(_QWORD *)ATL::CTime::Format(v32, NumberOfBytesWritten, L"%m/%d/%Y %H:%M:%S");
  v8 = (int *)(*(_QWORD *)v30 - 24LL);
  if ( v7 - 24 != *(_QWORD *)v30 - 24LL )
  {
    if ( v8[4] >= 0 && *(_QWORD *)(v7 - 24) == *(_QWORD *)v8 )
    {
      v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v8);
      *(_QWORD *)v30 = v9 + 24;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(v30, v7, *(unsigned int *)(v7 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)NumberOfBytesWritten - 24LL));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(v30, "\t");
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_17;
      v12 = "error";
    }
    else
    {
      v12 = "warning";
    }
  }
  else
  {
    v12 = "info";
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(v30, v12);
LABEL_17:
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) - 16LL) )
  {
    memset_0(Str, 0, 0x104u);
    LibraryW = LoadLibraryW(L"api-ms-win-core-psapi-obsolete-l1-1-0.dll");
    v14 = LibraryW;
    if ( LibraryW )
    {
      v15 = "K32GetModuleFileNameExA";
    }
    else
    {
      LibraryW = LoadLibraryW(L"psapi.dll");
      v14 = LibraryW;
      if ( !LibraryW )
        goto LABEL_30;
      v15 = "GetModuleFileNameExA";
    }
    ProcAddress = GetProcAddress(LibraryW, v15);
    if ( ProcAddress )
    {
      CurrentProcess = GetCurrentProcess();
      if ( ((unsigned int (__fastcall *)(HANDLE, _QWORD, char *, __int64))ProcAddress)(CurrentProcess, 0, Str, 260) )
      {
        v18 = strrchr(Str, 92);
        v19 = v18 + 1;
        if ( v18 == (char *)-1LL )
        {
          v20 = 0;
LABEL_29:
          ATL::CSimpleStringT<char,0>::SetString((char *)this + 16, v19, v20);
          FreeLibrary(v14);
          goto LABEL_30;
        }
      }
      else
      {
        v19 = Str;
      }
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      goto LABEL_29;
    }
  }
LABEL_30:
  memset_0(v35, 0, sizeof(v35));
  CurrentProcessId = GetCurrentProcessId();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(v30, "\t");
  if ( (int)StringCbPrintfA(
              v35,
              0x400u,
              "\t%s (PID:%d TID:%d)\t",
              *((const char **)this + 2),
              CurrentProcessId,
              CurrentThreadId) >= 0 )
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(v30, v35);
  ATL::CSimpleStringT<wchar_t,0>::Append(v30, *a3, *(unsigned int *)(*a3 - 16LL));
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(v30, "\r\n");
  v23 = *(wchar_t **)v30;
  v24 = *(wchar_t **)v30;
  do
    ++v6;
  while ( *(_WORD *)(*(_QWORD *)v30 + 2 * v6) );
  v25 = 2 * v6;
  v26 = (char *)operator new[](2 * (int)v6 + 1, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26 )
  {
    v27 = v26;
    if ( *v23 )
    {
      do
      {
        if ( !v25 )
          break;
        if ( (unsigned __int16)(*v24 + 21504) > 0xFFu )
        {
          LODWORD(v28) = wctomb(v27, *v24);
          if ( (int)v28 <= 0 )
            v28 = 2;
          v25 -= v28;
          v27 += v28;
        }
        else if ( v25 >= 2 )
        {
          v29[0] = *(_BYTE *)v24;
          v30[0] = v25;
          if ( (unsigned int)ATL::AtlHexEncode(v29, 1, v27, v30) )
          {
            v27 += 2;
            v25 -= 2;
          }
        }
        ++v24;
      }
      while ( *v24 );
    }
    NumberOfBytesWritten[0] = 0;
    if ( WriteFile(*((HANDLE *)this + 6), v26, (_DWORD)v27 - (_DWORD)v26, NumberOfBytesWritten, 0) )
    {
      *((_DWORD *)this + 16) += NumberOfBytesWritten[0];
      FlushFileBuffers(*((HANDLE *)this + 6));
    }
    operator delete(v26);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
LABEL_49:
  ATL::CStringData::Release((ATL::CStringData *)(*a3 - 24LL));
}

```

## disassembly

```asm
0x180038dd0  mov     [rsp-8+arg_8], rbx
0x180038dd5  mov     [rsp-8+arg_10], r8
0x180038dda  push    rbp
0x180038ddb  push    rsi
0x180038ddc  push    rdi
0x180038ddd  push    r12
0x180038ddf  push    r13
0x180038de1  push    r14
0x180038de3  push    r15
0x180038de5  lea     rbp, [rsp-480h]
0x180038ded  sub     rsp, 580h
0x180038df4  mov     rax, cs:__security_cookie
0x180038dfb  xor     rax, rsp
0x180038dfe  mov     [rbp+4B0h+var_40], rax
0x180038e05  mov     rsi, r8
0x180038e08  mov     edi, edx
0x180038e0a  mov     r14, rcx
0x180038e0d  mov     [rsp+5B0h+var_560], r8
0x180038e12  or      r13, 0FFFFFFFFFFFFFFFFh
0x180038e16  cmp     [rcx+30h], r13
0x180038e1a  jz      loc_180039180
0x180038e20  cmp     [rcx+38h], edx
0x180038e23  jg      loc_180039180
0x180038e29  mov     rax, [r8]
0x180038e2c  mov     ecx, [rax-10h]
0x180038e2f  add     ecx, [r14+3Ch]
0x180038e33  add     ecx, [r14+40h]
0x180038e37  xor     r12d, r12d
0x180038e3a  cmp     ecx, 80000h
0x180038e40  jbe     short loc_180038E52
0x180038e42  mov     rcx, r14; this
0x180038e45  call    ?RollOver@CLogger@@AEAAHXZ; CLogger::RollOver(void)
0x180038e4a  test    eax, eax
0x180038e4c  jz      loc_180039180
0x180038e52  lea     rcx, [rsp+5B0h+var_568]
0x180038e57  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180038e5c  lea     rcx, [rsp+5B0h+var_578]
0x180038e61  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180038e66  nop
0x180038e67  lea     r8, aMDYHMS; "%m/%d/%Y %H:%M:%S"
0x180038e6e  lea     rdx, [rsp+5B0h+NumberOfBytesWritten]
0x180038e73  lea     rcx, [rsp+5B0h+var_568]
0x180038e78  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@PEB_W@Z; ATL::CTime::Format(wchar_t const *)
0x180038e7d  nop
0x180038e7e  mov     rdx, [rax]
0x180038e81  lea     rcx, [rdx-18h]
0x180038e85  mov     r15, qword ptr [rsp+5B0h+var_578]
0x180038e8a  add     r15, 0FFFFFFFFFFFFFFE8h
0x180038e8e  cmp     rcx, r15
0x180038e91  jz      short loc_180038ECB
0x180038e93  cmp     [r15+10h], r12d
0x180038e97  jl      short loc_180038EBC
0x180038e99  mov     rax, [r15]
0x180038e9c  cmp     [rcx], rax
0x180038e9f  jnz     short loc_180038EBC
0x180038ea1  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180038ea6  mov     rbx, rax
0x180038ea9  mov     rcx, r15; this
0x180038eac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038eb1  lea     rax, [rbx+18h]
0x180038eb5  mov     qword ptr [rsp+5B0h+var_578], rax
0x180038eba  jmp     short loc_180038ECB
0x180038ebc  mov     r8d, [rdx-10h]
0x180038ec0  lea     rcx, [rsp+5B0h+var_578]
0x180038ec5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180038eca  nop
0x180038ecb  mov     rcx, qword ptr [rsp+5B0h+NumberOfBytesWritten]
0x180038ed0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038ed4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038ed9  lea     rdx, asc_18004C1D0; "\t"
0x180038ee0  lea     rcx, [rsp+5B0h+var_578]
0x180038ee5  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038eea  sub     edi, 1
0x180038eed  jz      short loc_180038F0B
0x180038eef  sub     edi, 1
0x180038ef2  jz      short loc_180038F02
0x180038ef4  cmp     edi, 1
0x180038ef7  jnz     short loc_180038F1C
0x180038ef9  lea     rdx, aError; "error"
0x180038f00  jmp     short loc_180038F12
0x180038f02  lea     rdx, aWarning; "warning"
0x180038f09  jmp     short loc_180038F12
0x180038f0b  lea     rdx, aInfo; "info"
0x180038f12  lea     rcx, [rsp+5B0h+var_578]
0x180038f17  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180038f1c  lea     r15, [r14+10h]
0x180038f20  mov     rax, [r15]
0x180038f23  cmp     [rax-10h], r12d
0x180038f27  jnz     loc_180038FEC
0x180038f2d  xor     edx, edx; Val
0x180038f2f  mov     r8d, 104h; Size
0x180038f35  lea     rcx, [rsp+5B0h+Str]; void *
0x180038f3a  call    memset_0
0x180038f3f  lea     rcx, aApiMsWinCorePs; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180038f46  call    cs:__imp_LoadLibraryW
0x180038f4c  mov     rbx, rax
0x180038f4f  test    rax, rax
0x180038f52  jz      short loc_180038F5D
0x180038f54  lea     rdx, aK32getmodulefi; "K32GetModuleFileNameExA"
0x180038f5b  jmp     short loc_180038F79
0x180038f5d  lea     rcx, aPsapiDll; "psapi.dll"
0x180038f64  call    cs:__imp_LoadLibraryW
0x180038f6a  mov     rbx, rax
0x180038f6d  test    rax, rax
0x180038f70  jz      short loc_180038FEC
0x180038f72  lea     rdx, aGetmodulefilen; "GetModuleFileNameExA"
0x180038f79  mov     rcx, rax; hModule
0x180038f7c  call    cs:__imp_GetProcAddress
0x180038f82  mov     rdi, rax
0x180038f85  test    rax, rax
0x180038f88  jz      short loc_180038FEC
0x180038f8a  call    cs:__imp_GetCurrentProcess
0x180038f90  mov     rcx, rax
0x180038f93  mov     r9d, 104h
0x180038f99  lea     r8, [rsp+5B0h+Str]
0x180038f9e  xor     edx, edx
0x180038fa0  mov     rax, rdi
0x180038fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fa8  test    eax, eax
0x180038faa  jz      short loc_180038FCA
0x180038fac  mov     edx, 5Ch ; '\'; Ch
0x180038fb1  lea     rcx, [rsp+5B0h+Str]; Str
0x180038fb6  call    cs:__imp_strrchr
0x180038fbc  lea     rdx, [rax+1]
0x180038fc0  test    rdx, rdx
0x180038fc3  jnz     short loc_180038FCF
0x180038fc5  mov     r8d, r12d
0x180038fc8  jmp     short loc_180038FDB
0x180038fca  lea     rdx, [rsp+5B0h+Str]
0x180038fcf  mov     r8, r13
0x180038fd2  inc     r8
0x180038fd5  cmp     [rdx+r8], r12b
0x180038fd9  jnz     short loc_180038FD2
0x180038fdb  mov     rcx, r15
0x180038fde  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x180038fe3  mov     rcx, rbx; hLibModule
0x180038fe6  call    cs:__imp_FreeLibrary
0x180038fec  mov     r12d, 400h
0x180038ff2  mov     r8d, r12d; Size
0x180038ff5  xor     edx, edx; Val
0x180038ff7  lea     rcx, [rbp+4B0h+var_440]; void *
0x180038ffb  call    memset_0
0x180039000  call    cs:__imp_GetCurrentProcessId
0x180039006  mov     edi, eax
0x180039008  call    cs:__imp_GetCurrentThreadId
0x18003900e  mov     ebx, eax
0x180039010  lea     rdx, asc_18004C1D0; "\t"
0x180039017  lea     rcx, [rsp+5B0h+var_578]
0x18003901c  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180039021  mov     [rsp+5B0h+var_588], ebx
0x180039025  mov     dword ptr [rsp+5B0h+lpOverlapped], edi
0x180039029  mov     r9, [r15]
0x18003902c  lea     r8, aSPidDTidD; "\t%s (PID:%d TID:%d)\t"
0x180039033  mov     edx, r12d; unsigned __int64
0x180039036  lea     rcx, [rbp+4B0h+var_440]; char *
0x18003903a  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18003903f  xor     edi, edi
0x180039041  test    eax, eax
0x180039043  js      short loc_180039053
0x180039045  lea     rdx, [rbp+4B0h+var_440]
0x180039049  lea     rcx, [rsp+5B0h+var_578]
0x18003904e  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180039053  mov     rdx, [rsi]
0x180039056  mov     r8d, [rdx-10h]
0x18003905a  lea     rcx, [rsp+5B0h+var_578]
0x18003905f  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180039064  lea     rdx, asc_18004C36C; "\r\n"
0x18003906b  lea     rcx, [rsp+5B0h+var_578]
0x180039070  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x180039075  mov     rbx, qword ptr [rsp+5B0h+var_578]
0x18003907a  mov     r12, rbx
0x18003907d  inc     r13
0x180039080  cmp     [rbx+r13*2], di
0x180039085  jnz     short loc_18003907D
0x180039087  lea     edi, ds:0[r13*2]
0x18003908f  lea     eax, [rdi+1]
0x180039092  movsxd  rcx, eax; unsigned __int64
0x180039095  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003909c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800390a1  mov     r13, rax
0x1800390a4  xor     eax, eax
0x1800390a6  test    r13, r13
0x1800390a9  jz      loc_180039176
0x1800390af  mov     r15, r13
0x1800390b2  cmp     [rbx], ax
0x1800390b5  jz      short loc_180039135
0x1800390b7  lea     edx, [rax+2]
0x1800390ba  test    edi, edi
0x1800390bc  jz      short loc_180039135
0x1800390be  mov     ecx, 5400h
0x1800390c3  movzx   eax, word ptr [r12]
0x1800390c8  add     ax, cx
0x1800390cb  mov     ecx, 0FFh
0x1800390d0  cmp     ax, cx
0x1800390d3  ja      short loc_18003910C
0x1800390d5  cmp     edi, edx
0x1800390d7  jl      short loc_180039129
0x1800390d9  mov     al, [r12]
0x1800390dd  mov     [rsp+5B0h+var_580], al
0x1800390e1  mov     [rsp+5B0h+var_578], edi
0x1800390e5  lea     r9, [rsp+5B0h+var_578]; int *
0x1800390ea  mov     r8, r15; char *
0x1800390ed  mov     edx, 1; int
0x1800390f2  lea     rcx, [rsp+5B0h+var_580]; unsigned __int8 *
0x1800390f7  call    ?AtlHexEncode@ATL@@YAHPEBEHPEADPEAH@Z; ATL::AtlHexEncode(uchar const *,int,char *,int *)
0x1800390fc  mov     edx, 2
0x180039101  test    eax, eax
0x180039103  jz      short loc_180039129
0x180039105  add     r15, rdx
0x180039108  sub     edi, edx
0x18003910a  jmp     short loc_180039129
0x18003910c  movzx   edx, word ptr [r12]; WCh
0x180039111  mov     rcx, r15; MbCh
0x180039114  call    cs:__imp_wctomb
0x18003911a  test    eax, eax
0x18003911c  mov     edx, 2
0x180039121  cmovle  eax, edx
0x180039124  sub     edi, eax
0x180039126  add     r15, rax
0x180039129  add     r12, rdx
0x18003912c  xor     eax, eax
0x18003912e  cmp     [r12], ax
0x180039133  jnz     short loc_1800390BA
0x180039135  mov     [rsp+5B0h+NumberOfBytesWritten], eax
0x180039139  sub     r15d, r13d
0x18003913c  mov     [rsp+5B0h+lpOverlapped], rax; lpOverlapped
0x180039141  lea     r9, [rsp+5B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180039146  mov     r8d, r15d; nNumberOfBytesToWrite
0x180039149  mov     rdx, r13; lpBuffer
0x18003914c  mov     rcx, [r14+30h]; hFile
0x180039150  call    cs:__imp_WriteFile
0x180039156  cmp     eax, 1
0x180039159  jnz     short loc_18003916D
0x18003915b  mov     eax, [rsp+5B0h+NumberOfBytesWritten]
0x18003915f  add     [r14+40h], eax
0x180039163  mov     rcx, [r14+30h]; hFile
0x180039167  call    cs:__imp_FlushFileBuffers
0x18003916d  mov     rcx, r13; Block
0x180039170  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039175  nop
0x180039176  lea     rcx, [rbx-18h]; this
0x18003917a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003917f  nop
0x180039180  mov     rcx, [rsi]
0x180039183  sub     rcx, 18h; this
0x180039187  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003918c  mov     rcx, [rbp+4B0h+var_40]
0x180039193  xor     rcx, rsp; StackCookie
0x180039196  call    __security_check_cookie
0x18003919b  mov     rbx, [rsp+5B0h+arg_8]
0x1800391a3  add     rsp, 580h
0x1800391aa  pop     r15
0x1800391ac  pop     r14
0x1800391ae  pop     r13
0x1800391b0  pop     r12
0x1800391b2  pop     rdi
0x1800391b3  pop     rsi
0x1800391b4  pop     rbp
0x1800391b5  retn
```
