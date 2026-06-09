# CreatePathWithVerification(ushort const *,int,void * *,void * *)

- ea: `0x14000a7d0`
- end: `0x14000ac47`
- name: `?CreatePathWithVerification@@YAJPEBGHPEAPEAX1@Z`
- size: `1143`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, void **, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140006238`
- `0x14000a7d0`

## callees

- `0x140002116`
- `0x140003ad0`
- `0x1400076c8`
- `0x14000a7d0`
- `0x14000c20c`
- `0x14000ff50`
- `0x1400135b8`
- `0x140016260`
- `0x140020498`
- `0x140027a70`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000abb0`
- `KERNEL32!CloseHandle` at `0x14000abc7`
- `KERNEL32!CloseHandle` at `0x14000ac0e`
- `KERNEL32!CloseHandle` at `0x14000abb0`
- `KERNEL32!CloseHandle` at `0x14000abc7`
- `KERNEL32!CloseHandle` at `0x14000ac0e`
- `KERNEL32!GetTempFileNameW` at `0x14000aad7`
- `KERNEL32!GetTempFileNameW` at `0x14000aad7`
- `KERNEL32!HeapFree` at `0x14000aa75`
- `KERNEL32!HeapFree` at `0x14000ab98`
- `KERNEL32!HeapFree` at `0x14000abf2`
- `KERNEL32!HeapFree` at `0x14000aa75`
- `KERNEL32!HeapFree` at `0x14000ab98`
- `KERNEL32!HeapFree` at `0x14000abf2`
- `KERNEL32!GetProcessHeap` at `0x14000aa60`
- `KERNEL32!GetProcessHeap` at `0x14000ab84`
- `KERNEL32!GetProcessHeap` at `0x14000abdd`
- `KERNEL32!GetProcessHeap` at `0x14000aa60`
- `KERNEL32!GetProcessHeap` at `0x14000ab84`
- `KERNEL32!GetProcessHeap` at `0x14000abdd`
- `KERNEL32!GetLastError` at `0x14000a8a4`
- `KERNEL32!GetLastError` at `0x14000aa08`
- `KERNEL32!GetLastError` at `0x14000a8a4`
- `KERNEL32!GetLastError` at `0x14000aa08`
- `KERNEL32!GetFileInformationByHandle` at `0x14000a9f8`
- `KERNEL32!GetFileInformationByHandle` at `0x14000a9f8`

## pseudocode

```c
__int64 __fastcall CreatePathWithVerification(unsigned __int16 *a1, int a2, void **a3, void **a4)
{
  void *v7; // r15
  HANDLE v8; // r14
  LPCWSTR v9; // rdi
  void *v10; // rbx
  unsigned int v11; // esi
  int v12; // ecx
  signed int LastError; // eax
  int v14; // ecx
  int v15; // eax
  void *v16; // r8
  int v17; // ecx
  int ParentPath; // eax
  int v19; // eax
  signed int v20; // eax
  HANDLE ProcessHeap; // rax
  int v22; // eax
  int v23; // eax
  void *v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE hFile; // [rsp+48h] [rbp-C0h] BYREF
  void *v29; // [rsp+50h] [rbp-B8h] BYREF
  LPCWSTR lpPathName; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A8h] BYREF
  void *v32; // [rsp+68h] [rbp-A0h] BYREF
  void **v33; // [rsp+70h] [rbp-98h]
  void *v34; // [rsp+78h] [rbp-90h] BYREF
  _DWORD v35[4]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v36; // [rsp+90h] [rbp-78h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+98h] [rbp-70h] BYREF
  WCHAR TempFileName[264]; // [rsp+D8h] [rbp-30h] BYREF

  v36 = -2;
  v33 = a4;
  v7 = 0;
  v8 = 0;
  hFile = 0;
  v9 = 0;
  lpPathName = 0;
  hObject = 0;
  memset_0(TempFileName, 0, 0x208u);
  v10 = 0;
  v32 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v29 = 0;
  v34 = 0;
  v35[0] = 17;
  v35[1] = 18;
  v35[2] = 8;
  if ( !a1 )
  {
    v11 = -2147024809;
LABEL_3:
    v12 = v11;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_50;
  }
  if ( !a2 )
    goto LABEL_17;
  if ( !(unsigned int)CreateWorkingDirectorySecurityDescriptor(&v29) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    v14 = v11;
    goto LABEL_12;
  }
  v15 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(&v34, v35, 3);
  v11 = v15;
  if ( v15 < 0 )
  {
    v14 = v15;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    v7 = v29;
    goto LABEL_50;
  }
  v7 = v29;
  if ( v29 )
    v16 = v29;
  else
LABEL_17:
    v16 = 0;
  v11 = NtCreateFileWrapper(a1, 0, v16, 0x12019Fu, 1u, 1u, 0x200001u, &hFile);
  if ( v11 + 2147024894 <= 1 )
  {
    ParentPath = GetParentPath(a1, (unsigned __int16 **)&lpPathName);
    v11 = ParentPath;
    if ( ParentPath < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(ParentPath);
      v8 = hFile;
      v9 = lpPathName;
      goto LABEL_50;
    }
    v9 = lpPathName;
    v19 = CreatePathWithVerification(lpPathName, 0, &hObject, 0);
    v11 = v19;
    if ( v19 < 0
      || (v19 = NtCreateFileWrapper(a1, hObject, v7, 0x12019Fu, 1u, 2u, 0x200001u, &hFile), v11 = v19, v19 < 0) )
    {
      v17 = v19;
      goto LABEL_25;
    }
  }
  else if ( (v11 & 0x80000000) != 0 )
  {
    v17 = v11;
LABEL_25:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
    v8 = hFile;
    goto LABEL_50;
  }
  v8 = hFile;
  if ( !GetFileInformationByHandle(hFile, &FileInformation) )
  {
LABEL_28:
    v20 = GetLastError();
    v11 = v20;
    if ( v20 )
    {
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    goto LABEL_3;
  }
  if ( (FileInformation.dwFileAttributes & 0x10) == 0 )
  {
    v11 = -2147024629;
    goto LABEL_3;
  }
  if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
  {
    v11 = -2147024215;
    goto LABEL_3;
  }
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v9 = 0;
    lpPathName = 0;
  }
  if ( (int)GetParentPath(a1, 0) >= 0 )
  {
    v22 = VerifyAndAcquireFinalPath(a1, 0);
    v11 = v22;
    if ( v22 < 0 )
    {
      v12 = v22;
      goto LABEL_4;
    }
  }
  if ( v33 )
  {
    if ( !GetTempFileNameW(a1, L"tmp", 1u, TempFileName) )
      goto LABEL_28;
    TempFileName[259] = 0;
    if ( !TempFileName[0] )
    {
      v11 = -2147418113;
      goto LABEL_3;
    }
    v23 = NtCreateFileWrapper(TempFileName, v8, 0, 0x13019Fu, 0, 2u, 0x1040u, &v32);
    v11 = v23;
    if ( v23 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
      v10 = v32;
      goto LABEL_50;
    }
    v10 = 0;
    *v33 = v32;
  }
  if ( a3 )
  {
    v24 = v8;
    v8 = 0;
    *a3 = v24;
  }
LABEL_50:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(&v34);
  if ( v7 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v7);
  }
  if ( v10 )
    CloseHandle(v10);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v9 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, (LPVOID)(v9 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
    CloseHandle(v8);
  return v11;
}

```

## disassembly

```asm
0x14000a7d0  mov     rax, rsp
0x14000a7d3  push    rbp
0x14000a7d4  push    rsi
0x14000a7d5  push    rdi
0x14000a7d6  push    r12
0x14000a7d8  push    r13
0x14000a7da  push    r14
0x14000a7dc  push    r15
0x14000a7de  lea     rbp, [rax-228h]
0x14000a7e5  sub     rsp, 2F0h
0x14000a7ec  mov     [rbp+220h+var_298], 0FFFFFFFFFFFFFFFEh
0x14000a7f4  mov     [rax+10h], rbx
0x14000a7f8  mov     rax, cs:__security_cookie
0x14000a7ff  xor     rax, rsp
0x14000a802  mov     [rbp+220h+var_40], rax
0x14000a809  mov     [rsp+320h+var_2B8], r9
0x14000a80e  mov     r13, r8
0x14000a811  mov     esi, edx
0x14000a813  mov     r12, rcx
0x14000a816  xor     r15d, r15d
0x14000a819  mov     r14d, r15d
0x14000a81c  mov     [rsp+320h+hFile], r15
0x14000a821  mov     edi, r15d
0x14000a824  mov     [rsp+320h+lpPathName], r15
0x14000a829  mov     [rsp+320h+hObject], r15
0x14000a82e  xor     edx, edx; Val
0x14000a830  mov     r8d, 208h; Size
0x14000a836  lea     rcx, [rbp+220h+TempFileName]; void *
0x14000a83a  call    memset_0
0x14000a83f  mov     ebx, r15d
0x14000a842  mov     [rsp+320h+var_2C0], rbx
0x14000a847  xorps   xmm0, xmm0
0x14000a84a  xor     eax, eax
0x14000a84c  movups  xmmword ptr [rbp+220h+FileInformation.dwFileAttributes], xmm0
0x14000a850  movups  xmmword ptr [rbp+220h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14000a854  movups  xmmword ptr [rbp+220h+FileInformation.nFileSizeHigh], xmm0
0x14000a858  mov     [rbp+220h+FileInformation.nFileIndexLow], eax
0x14000a85b  mov     [rsp+320h+var_2D8], r15
0x14000a860  mov     qword ptr [rsp+320h+var_2B0], rax
0x14000a865  mov     dword ptr [rsp+78h], 11h
0x14000a86d  mov     dword ptr [rsp+7Ch], 12h
0x14000a875  mov     [rbp+220h+var_2A0], 8
0x14000a87c  test    r12, r12
0x14000a87f  jnz     short loc_14000A892
0x14000a881  mov     esi, 80070057h
0x14000a886  mov     ecx, esi
0x14000a888  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a88d  jmp     loc_14000AB6C
0x14000a892  test    esi, esi
0x14000a894  jz      short loc_14000A90A
0x14000a896  lea     rcx, [rsp+320h+var_2D8]
0x14000a89b  call    CreateWorkingDirectorySecurityDescriptor
0x14000a8a0  test    eax, eax
0x14000a8a2  jnz     short loc_14000A8D9
0x14000a8a4  call    cs:__imp_GetLastError
0x14000a8ab  nop     dword ptr [rax+rax+00h]
0x14000a8b0  mov     esi, eax
0x14000a8b2  test    eax, eax
0x14000a8b4  jnz     short loc_14000A8BD
0x14000a8b6  mov     esi, 80004005h
0x14000a8bb  jmp     short loc_14000A8C8
0x14000a8bd  jle     short loc_14000A8C8
0x14000a8bf  movzx   esi, ax
0x14000a8c2  or      esi, 80070000h
0x14000a8c8  mov     ecx, esi
0x14000a8ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a8cf  mov     r15, [rsp+320h+var_2D8]
0x14000a8d4  jmp     loc_14000AB6C
0x14000a8d9  mov     r8d, 3
0x14000a8df  lea     rdx, [rsp+78h]
0x14000a8e4  lea     rcx, [rsp+320h+var_2B0]
0x14000a8e9  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x14000a8ee  mov     esi, eax
0x14000a8f0  test    eax, eax
0x14000a8f2  jns     short loc_14000A8F8
0x14000a8f4  mov     ecx, eax
0x14000a8f6  jmp     short loc_14000A8CA
0x14000a8f8  mov     r15, [rsp+320h+var_2D8]
0x14000a8fd  xor     r14d, r14d
0x14000a900  test    r15, r15
0x14000a903  jz      short loc_14000A90D
0x14000a905  mov     r8, r15
0x14000a908  jmp     short loc_14000A910
0x14000a90a  xor     r14d, r14d
0x14000a90d  mov     r8, r14; void *
0x14000a910  lea     rax, [rsp+320h+hFile]
0x14000a915  mov     [rsp+320h+var_2E8], rax; void **
0x14000a91a  mov     [rsp+320h+var_2F0], 200001h; unsigned int
0x14000a922  mov     eax, 1
0x14000a927  mov     [rsp+320h+var_2F8], eax; unsigned int
0x14000a92b  mov     [rsp+320h+var_300], eax; unsigned int
0x14000a92f  xor     edx, edx; void *
0x14000a931  mov     r9d, 12019Fh; unsigned int
0x14000a937  mov     rcx, r12; unsigned __int16 *
0x14000a93a  call    ?NtCreateFileWrapper@@YAJPEBGPEAX1KKKKPEAPEAX@Z; NtCreateFileWrapper(ushort const *,void *,void *,ulong,ulong,ulong,ulong,void * *)
0x14000a93f  mov     esi, eax
0x14000a941  add     eax, 7FF8FFFEh
0x14000a946  cmp     eax, 1
0x14000a949  jbe     short loc_14000A957
0x14000a94b  test    esi, esi
0x14000a94d  jns     loc_14000A9EC
0x14000a953  mov     ecx, esi
0x14000a955  jmp     short loc_14000A99F
0x14000a957  lea     rdx, [rsp+320h+lpPathName]; unsigned __int16 **
0x14000a95c  mov     rcx, r12; unsigned __int16 *
0x14000a95f  call    ?GetParentPath@@YAJPEBGPEAPEAG@Z; GetParentPath(ushort const *,ushort * *)
0x14000a964  mov     esi, eax
0x14000a966  test    eax, eax
0x14000a968  jns     short loc_14000A980
0x14000a96a  mov     ecx, eax
0x14000a96c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a971  mov     r14, [rsp+320h+hFile]
0x14000a976  mov     rdi, [rsp+320h+lpPathName]
0x14000a97b  jmp     loc_14000AB6C
0x14000a980  mov     rdi, [rsp+320h+lpPathName]
0x14000a985  xor     r9d, r9d; void **
0x14000a988  lea     r8, [rsp+320h+hObject]; void **
0x14000a98d  xor     edx, edx; int
0x14000a98f  mov     rcx, rdi; unsigned __int16 *
0x14000a992  call    ?CreatePathWithVerification@@YAJPEBGHPEAPEAX1@Z; CreatePathWithVerification(ushort const *,int,void * *,void * *)
0x14000a997  mov     esi, eax
0x14000a999  test    eax, eax
0x14000a99b  jns     short loc_14000A9AE
0x14000a99d  mov     ecx, eax
0x14000a99f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000a9a4  mov     r14, [rsp+320h+hFile]
0x14000a9a9  jmp     loc_14000AB6C
0x14000a9ae  lea     rax, [rsp+320h+hFile]
0x14000a9b3  mov     [rsp+320h+var_2E8], rax; void **
0x14000a9b8  mov     [rsp+320h+var_2F0], 200001h; unsigned int
0x14000a9c0  mov     [rsp+320h+var_2F8], 2; unsigned int
0x14000a9c8  mov     [rsp+320h+var_300], 1; unsigned int
0x14000a9d0  mov     r9d, 12019Fh; unsigned int
0x14000a9d6  mov     r8, r15; void *
0x14000a9d9  mov     rdx, [rsp+320h+hObject]; void *
0x14000a9de  mov     rcx, r12; unsigned __int16 *
0x14000a9e1  call    ?NtCreateFileWrapper@@YAJPEBGPEAX1KKKKPEAPEAX@Z; NtCreateFileWrapper(ushort const *,void *,void *,ulong,ulong,ulong,ulong,void * *)
0x14000a9e6  mov     esi, eax
0x14000a9e8  test    eax, eax
0x14000a9ea  js      short loc_14000A99D
0x14000a9ec  mov     r14, [rsp+320h+hFile]
0x14000a9f1  lea     rdx, [rbp+220h+FileInformation]; lpFileInformation
0x14000a9f5  mov     rcx, r14; hFile
0x14000a9f8  call    cs:__imp_GetFileInformationByHandle
0x14000a9ff  nop     dword ptr [rax+rax+00h]
0x14000aa04  test    eax, eax
0x14000aa06  jnz     short loc_14000AA38
0x14000aa08  call    cs:__imp_GetLastError
0x14000aa0f  nop     dword ptr [rax+rax+00h]
0x14000aa14  mov     esi, eax
0x14000aa16  test    eax, eax
0x14000aa18  jnz     short loc_14000AA24
0x14000aa1a  mov     esi, 80004005h
0x14000aa1f  jmp     loc_14000A886
0x14000aa24  jle     loc_14000A886
0x14000aa2a  movzx   esi, si
0x14000aa2d  or      esi, 80070000h
0x14000aa33  jmp     loc_14000A886
0x14000aa38  test    byte ptr [rbp+220h+FileInformation.dwFileAttributes], 10h
0x14000aa3c  jnz     short loc_14000AA48
0x14000aa3e  mov     esi, 8007010Bh
0x14000aa43  jmp     loc_14000A886
0x14000aa48  test    [rbp+220h+FileInformation.dwFileAttributes], 400h
0x14000aa4f  jz      short loc_14000AA5B
0x14000aa51  mov     esi, 800702A9h
0x14000aa56  jmp     loc_14000A886
0x14000aa5b  test    rdi, rdi
0x14000aa5e  jz      short loc_14000AA91
0x14000aa60  call    cs:__imp_GetProcessHeap
0x14000aa67  nop     dword ptr [rax+rax+00h]
0x14000aa6c  mov     rcx, rax; hHeap
0x14000aa6f  lea     r8, [rdi-4]; lpMem
0x14000aa73  xor     edx, edx; dwFlags
0x14000aa75  call    cs:__imp_HeapFree
0x14000aa7c  nop     dword ptr [rax+rax+00h]
0x14000aa81  xor     ecx, ecx
0x14000aa83  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000aa88  xor     eax, eax
0x14000aa8a  mov     edi, eax
0x14000aa8c  mov     [rsp+320h+lpPathName], rax
0x14000aa91  xor     edx, edx; unsigned __int16 **
0x14000aa93  mov     rcx, r12; unsigned __int16 *
0x14000aa96  call    ?GetParentPath@@YAJPEBGPEAPEAG@Z; GetParentPath(ushort const *,ushort * *)
0x14000aa9b  xor     edx, edx; unsigned __int16 **
0x14000aa9d  test    eax, eax
0x14000aa9f  js      short loc_14000AAB8
0x14000aaa1  mov     rcx, r12; unsigned __int16 *
0x14000aaa4  call    ?VerifyAndAcquireFinalPath@@YAJPEBGPEAPEAG@Z; VerifyAndAcquireFinalPath(ushort const *,ushort * *)
0x14000aaa9  mov     esi, eax
0x14000aaab  xor     edx, edx
0x14000aaad  test    eax, eax
0x14000aaaf  jns     short loc_14000AAB8
0x14000aab1  mov     ecx, eax
0x14000aab3  jmp     loc_14000A888
0x14000aab8  cmp     [rsp+320h+var_2B8], rdx
0x14000aabd  jz      loc_14000AB5D
0x14000aac3  lea     r9, [rbp+220h+TempFileName]; lpTempFileName
0x14000aac7  mov     r8d, 1; uUnique
0x14000aacd  lea     rdx, PrefixString; "tmp"
0x14000aad4  mov     rcx, r12; lpPathName
0x14000aad7  call    cs:__imp_GetTempFileNameW
0x14000aade  nop     dword ptr [rax+rax+00h]
0x14000aae3  xor     ecx, ecx
0x14000aae5  test    eax, eax
0x14000aae7  jz      loc_14000AA08
0x14000aaed  mov     [rbp+220h+var_4A], cx
0x14000aaf4  cmp     [rbp+220h+TempFileName], cx
0x14000aaf8  jnz     short loc_14000AB04
0x14000aafa  mov     esi, 8000FFFFh
0x14000aaff  jmp     loc_14000A886
0x14000ab04  lea     rax, [rsp+320h+var_2C0]
0x14000ab09  mov     [rsp+320h+var_2E8], rax; void **
0x14000ab0e  mov     [rsp+320h+var_2F0], 1040h; unsigned int
0x14000ab16  mov     [rsp+320h+var_2F8], 2; unsigned int
0x14000ab1e  mov     [rsp+320h+var_300], ecx; unsigned int
0x14000ab22  mov     r9d, 13019Fh; unsigned int
0x14000ab28  xor     r8d, r8d; void *
0x14000ab2b  mov     rdx, r14; void *
0x14000ab2e  lea     rcx, [rbp+220h+TempFileName]; unsigned __int16 *
0x14000ab32  call    ?NtCreateFileWrapper@@YAJPEBGPEAX1KKKKPEAPEAX@Z; NtCreateFileWrapper(ushort const *,void *,void *,ulong,ulong,ulong,ulong,void * *)
0x14000ab37  mov     esi, eax
0x14000ab39  xor     edx, edx
0x14000ab3b  test    eax, eax
0x14000ab3d  jns     short loc_14000AB4D
0x14000ab3f  mov     ecx, eax
0x14000ab41  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000ab46  mov     rbx, [rsp+320h+var_2C0]
0x14000ab4b  jmp     short loc_14000AB6C
0x14000ab4d  mov     rax, [rsp+320h+var_2C0]
0x14000ab52  mov     rbx, rdx
0x14000ab55  mov     rcx, [rsp+320h+var_2B8]
0x14000ab5a  mov     [rcx], rax
0x14000ab5d  test    r13, r13
0x14000ab60  jz      short loc_14000AB6C
0x14000ab62  mov     rax, r14
0x14000ab65  mov     r14, rdx
0x14000ab68  mov     [r13+0], rax
0x14000ab6c  mov     ecx, esi
0x14000ab6e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ab73  nop
0x14000ab74  lea     rcx, [rsp+320h+var_2B0]
0x14000ab79  call    ??1?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::~CAutoRevertApplyPrivilegesT<CEmptyType>(void)
0x14000ab7e  nop
0x14000ab7f  test    r15, r15
0x14000ab82  jz      short loc_14000ABA5
0x14000ab84  call    cs:__imp_GetProcessHeap
0x14000ab8b  nop     dword ptr [rax+rax+00h]
0x14000ab90  mov     rcx, rax; hHeap
0x14000ab93  mov     r8, r15; lpMem
0x14000ab96  xor     edx, edx; dwFlags
0x14000ab98  call    cs:__imp_HeapFree
0x14000ab9f  nop     dword ptr [rax+rax+00h]
0x14000aba4  nop
0x14000aba5  xor     r15d, r15d
0x14000aba8  test    rbx, rbx
0x14000abab  jz      short loc_14000ABBD
0x14000abad  mov     rcx, rbx; hObject
0x14000abb0  call    cs:__imp_CloseHandle
0x14000abb7  nop     dword ptr [rax+rax+00h]
0x14000abbc  nop
0x14000abbd  mov     rcx, [rsp+320h+hObject]; hObject
0x14000abc2  test    rcx, rcx
0x14000abc5  jz      short loc_14000ABD8
0x14000abc7  call    cs:__imp_CloseHandle
0x14000abce  nop     dword ptr [rax+rax+00h]
0x14000abd3  mov     [rsp+320h+hObject], r15
0x14000abd8  test    rdi, rdi
0x14000abdb  jz      short loc_14000AC06
0x14000abdd  call    cs:__imp_GetProcessHeap
0x14000abe4  nop     dword ptr [rax+rax+00h]
0x14000abe9  mov     rcx, rax; hHeap
0x14000abec  lea     r8, [rdi-4]; lpMem
0x14000abf0  xor     edx, edx; dwFlags
0x14000abf2  call    cs:__imp_HeapFree
0x14000abf9  nop     dword ptr [rax+rax+00h]
0x14000abfe  xor     ecx, ecx
0x14000ac00  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ac05  nop
0x14000ac06  test    r14, r14
0x14000ac09  jz      short loc_14000AC1A
0x14000ac0b  mov     rcx, r14; hObject
0x14000ac0e  call    cs:__imp_CloseHandle
0x14000ac15  nop     dword ptr [rax+rax+00h]
0x14000ac1a  mov     eax, esi
0x14000ac1c  mov     rcx, [rbp+220h+var_40]
0x14000ac23  xor     rcx, rsp; StackCookie
0x14000ac26  call    __security_check_cookie
0x14000ac2b  mov     rbx, [rsp+320h+arg_8]
0x14000ac33  add     rsp, 2F0h
0x14000ac3a  pop     r15
0x14000ac3c  pop     r14
0x14000ac3e  pop     r13
0x14000ac40  pop     r12
0x14000ac42  pop     rdi
0x14000ac43  pop     rsi
0x14000ac44  pop     rbp
0x14000ac45  retn
```
