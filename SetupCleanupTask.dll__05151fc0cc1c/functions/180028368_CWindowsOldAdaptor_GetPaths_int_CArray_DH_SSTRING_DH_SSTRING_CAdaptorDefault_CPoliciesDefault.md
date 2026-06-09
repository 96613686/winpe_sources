# CWindowsOldAdaptor::GetPaths(int,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> * *)

- ea: `0x180028368`
- end: `0x1800285ee`
- name: `?GetPaths@CWindowsOldAdaptor@@SAJHPEAPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002b224`

## callees

- `0x180001784`
- `0x180026000`
- `0x180026368`
- `0x180027008`
- `0x180027d04`
- `0x180028368`
- `0x1800293a4`
- `0x18002c658`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800284c5`
- `msvcrt!_wcsicmp` at `0x1800284c5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800285b9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800285b9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002846d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002846d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180028513`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180028513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002856a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028590`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002856a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028590`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002859f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002859f`

## string_xrefs

- `0x1800283f8`: `%systemdrive%\windows.old`
- `0x18002843d`: `%systemdrive%\windows.old\*`

## pseudocode

```c
__int64 __fastcall CWindowsOldAdaptor::GetPaths(int a1, _QWORD *a2)
{
  __int64 v4; // rbx
  LPCWSTR v5; // r14
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  char *FirstFileW; // rax
  void *v13; // r15
  unsigned __int16 *v14; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPWSTR v17; // rdi
  HANDLE v18; // rax
  LPWSTR v20; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v22; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v23 = 0;
  v4 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v20 = 0;
  v5 = 0;
  lpFileName = 0;
  v22 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
LABEL_24:
    v10 = v6;
    goto LABEL_25;
  }
  v7 = operator new(0x10u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_24;
  }
  *v7 = 0;
  v7[1] = 0;
  v23 = v7;
  v9 = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%systemdrive%\\windows.old", &v20);
  v6 = v9;
  if ( v9 >= 0 )
  {
    if ( a1 )
    {
      v9 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(v8, &v20);
      v6 = v9;
      if ( v9 < 0 )
        goto LABEL_5;
    }
    else
    {
      v11 = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%systemdrive%\\windows.old\\*", (LPWSTR *)&lpFileName);
      v6 = v11;
      if ( v11 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
        v5 = lpFileName;
        goto LABEL_26;
      }
      v5 = lpFileName;
      FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
      v13 = FirstFileW;
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v4 = (__int64)FirstFileW;
        do
        {
          if ( (FindFileData.dwFileAttributes & 0x400) == 0
            && (FindFileData.cFileName[0] != 46
             || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
          {
            if ( _wcsicmp(FindFileData.cFileName, L"Users") )
            {
              v9 = STRAPI_Format(&v22, L"%s\\%s", v20, FindFileData.cFileName);
              v6 = v9;
              if ( v9 < 0 )
                goto LABEL_5;
              v9 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(v8, &v22);
              v6 = v9;
              if ( v9 < 0 )
                goto LABEL_5;
            }
          }
        }
        while ( FindNextFileW(v13, &FindFileData) );
      }
    }
    v23 = 0;
    *a2 = v8;
    goto LABEL_26;
  }
LABEL_5:
  v10 = v9;
LABEL_25:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
LABEL_26:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  v14 = v22;
  if ( v22 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v17 = v20;
  if ( v20 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v17 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)v4);
  SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(&v23);
  return v6;
}

```

## disassembly

```asm
0x180028368  push    rbp
0x18002836a  push    rbx
0x18002836b  push    rsi
0x18002836c  push    rdi
0x18002836d  push    r12
0x18002836f  push    r13
0x180028371  push    r14
0x180028373  push    r15
0x180028375  lea     rbp, [rsp-1A8h]
0x18002837d  sub     rsp, 2A8h
0x180028384  mov     rax, cs:__security_cookie
0x18002838b  xor     rax, rsp
0x18002838e  mov     [rbp+1E0h+var_50], rax
0x180028395  mov     r12, rdx
0x180028398  mov     r15d, ecx
0x18002839b  xor     r13d, r13d
0x18002839e  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800283a3  xor     edx, edx; Val
0x1800283a5  mov     [rsp+2E0h+var_2A8], r13
0x1800283aa  mov     r8d, 250h; Size
0x1800283b0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800283b4  call    memset_0
0x1800283b9  mov     [rsp+2E0h+var_2C0], r13
0x1800283be  mov     r14d, r13d
0x1800283c1  mov     [rsp+2E0h+lpFileName], r13
0x1800283c6  mov     [rsp+2E0h+var_2B0], r13
0x1800283cb  test    r12, r12
0x1800283ce  jnz     short loc_1800283DA
0x1800283d0  mov     esi, 80070057h
0x1800283d5  jmp     loc_180028531
0x1800283da  mov     ecx, 10h; Size
0x1800283df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800283e4  mov     rdi, rax
0x1800283e7  test    rax, rax
0x1800283ea  jz      loc_18002852C
0x1800283f0  lea     rdx, [rsp+2E0h+var_2C0]
0x1800283f5  mov     [rax], r13
0x1800283f8  lea     rcx, aSystemdriveWin; "%systemdrive%\\windows.old"
0x1800283ff  mov     [rax+8], r13
0x180028403  mov     [rsp+2E0h+var_2A8], rax
0x180028408  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18002840d  mov     esi, eax
0x18002840f  test    eax, eax
0x180028411  jns     short loc_18002841A
0x180028413  mov     ecx, eax
0x180028415  jmp     loc_180028533
0x18002841a  test    r15d, r15d
0x18002841d  jz      short loc_180028438
0x18002841f  lea     rdx, [rsp+2E0h+var_2C0]
0x180028424  mov     rcx, rdi
0x180028427  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x18002842c  mov     esi, eax
0x18002842e  test    eax, eax
0x180028430  jns     loc_180028521
0x180028436  jmp     short loc_180028413
0x180028438  lea     rdx, [rsp+2E0h+lpFileName]
0x18002843d  lea     rcx, aSystemdriveWin_0; "%systemdrive%\\windows.old\\*"
0x180028444  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x180028449  mov     esi, eax
0x18002844b  test    eax, eax
0x18002844d  jns     short loc_180028460
0x18002844f  mov     ecx, eax
0x180028451  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028456  mov     r14, [rsp+2E0h+lpFileName]
0x18002845b  jmp     loc_180028538
0x180028460  mov     r14, [rsp+2E0h+lpFileName]
0x180028465  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18002846a  mov     rcx, r14; lpFileName
0x18002846d  call    cs:__imp_FindFirstFileW
0x180028473  mov     r15, rax
0x180028476  lea     rcx, [rax-1]
0x18002847a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002847e  ja      loc_180028521
0x180028484  mov     rbx, rax
0x180028487  test    [rsp+2E0h+FindFileData.dwFileAttributes], 400h
0x18002848f  jnz     short loc_18002850B
0x180028491  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x180028497  movzx   eax, [rsp+2E0h+FindFileData.cFileName+2]
0x18002849c  jnz     short loc_1800284B9
0x18002849e  test    ax, ax
0x1800284a1  jz      short loc_18002850B
0x1800284a3  cmp     [rsp+2E0h+FindFileData.cFileName], 2Eh ; '.'
0x1800284a9  jnz     short loc_1800284B9
0x1800284ab  cmp     ax, 2Eh ; '.'
0x1800284af  jnz     short loc_1800284B9
0x1800284b1  cmp     [rsp+2E0h+FindFileData.cFileName+4], r13w
0x1800284b7  jz      short loc_18002850B
0x1800284b9  lea     rdx, aUsers; "Users"
0x1800284c0  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; String1
0x1800284c5  call    cs:__imp__wcsicmp
0x1800284cb  test    eax, eax
0x1800284cd  jz      short loc_18002850B
0x1800284cf  mov     r8, [rsp+2E0h+var_2C0]
0x1800284d4  lea     r9, [rsp+2E0h+FindFileData.cFileName]
0x1800284d9  lea     rdx, aSS; "%s\\%s"
0x1800284e0  lea     rcx, [rsp+2E0h+var_2B0]; unsigned __int16 **
0x1800284e5  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1800284ea  mov     esi, eax
0x1800284ec  test    eax, eax
0x1800284ee  js      loc_180028413
0x1800284f4  lea     rdx, [rsp+2E0h+var_2B0]
0x1800284f9  mov     rcx, rdi
0x1800284fc  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180028501  mov     esi, eax
0x180028503  test    eax, eax
0x180028505  js      loc_180028413
0x18002850b  mov     rcx, r15; hFindFile
0x18002850e  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180028513  call    cs:__imp_FindNextFileW
0x180028519  test    eax, eax
0x18002851b  jnz     loc_180028487
0x180028521  mov     [rsp+2E0h+var_2A8], r13
0x180028526  mov     [r12], rdi
0x18002852a  jmp     short loc_180028538
0x18002852c  mov     esi, 8007000Eh
0x180028531  mov     ecx, esi
0x180028533  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028538  mov     ecx, esi
0x18002853a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002853f  mov     rdi, [rsp+2E0h+var_2B0]
0x180028544  test    rdi, rdi
0x180028547  jz      short loc_180028565
0x180028549  call    cs:__imp_GetProcessHeap
0x18002854f  lea     r8, [rdi-4]; lpMem
0x180028553  xor     edx, edx; dwFlags
0x180028555  mov     rcx, rax; hHeap
0x180028558  call    cs:__imp_HeapFree
0x18002855e  xor     ecx, ecx
0x180028560  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028565  test    r14, r14
0x180028568  jz      short loc_180028586
0x18002856a  call    cs:__imp_GetProcessHeap
0x180028570  lea     r8, [r14-4]; lpMem
0x180028574  xor     edx, edx; dwFlags
0x180028576  mov     rcx, rax; hHeap
0x180028579  call    cs:__imp_HeapFree
0x18002857f  xor     ecx, ecx
0x180028581  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028586  mov     rdi, [rsp+2E0h+var_2C0]
0x18002858b  test    rdi, rdi
0x18002858e  jz      short loc_1800285AC
0x180028590  call    cs:__imp_GetProcessHeap
0x180028596  lea     r8, [rdi-4]; lpMem
0x18002859a  xor     edx, edx; dwFlags
0x18002859c  mov     rcx, rax; hHeap
0x18002859f  call    cs:__imp_HeapFree
0x1800285a5  xor     ecx, ecx
0x1800285a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800285ac  lea     rax, [rbx-1]
0x1800285b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800285b4  ja      short loc_1800285BF
0x1800285b6  mov     rcx, rbx; hFindFile
0x1800285b9  call    cs:__imp_FindClose
0x1800285bf  lea     rcx, [rsp+2E0h+var_2A8]
0x1800285c4  call    ??1?$SP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@V?$SP_CPP@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@@@QEAA@XZ; SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>>(void)
0x1800285c9  mov     eax, esi
0x1800285cb  mov     rcx, [rbp+1E0h+var_50]
0x1800285d2  xor     rcx, rsp; StackCookie
0x1800285d5  call    __security_check_cookie
0x1800285da  add     rsp, 2A8h
0x1800285e1  pop     r15
0x1800285e3  pop     r14
0x1800285e5  pop     r13
0x1800285e7  pop     r12
0x1800285e9  pop     rdi
0x1800285ea  pop     rsi
0x1800285eb  pop     rbx
0x1800285ec  pop     rbp
0x1800285ed  retn
```
