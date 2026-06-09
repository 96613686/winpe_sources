# _HrRename(FILEREF * *,CFileRep *)

- ea: `0x18001b544`
- end: `0x18001b7b4`
- name: `?_HrRename@@YAJPEAPEAUFILEREF@@PEAVCFileRep@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct FILEREF **, struct CFileRep *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x18001a708`

## callees

- `0x180016028`
- `0x180019ecc`
- `0x18001a5ec`
- `0x18001b1d4`
- `0x18001b2b4`
- `0x18001b544`
- `0x18001b8b0`
- `0x18001b8c8`
- `0x18001b9ec`
- `0x18001bf20`
- `0x18001c154`
- `0x18001c1b0`
- `0x18001cc04`
- `0x1800208c4`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b604`
- `KERNEL32!GetLastError` at `0x18001b604`
- `KERNEL32!DeleteFileA` at `0x18001b6fa`
- `KERNEL32!DeleteFileA` at `0x18001b709`
- `KERNEL32!DeleteFileA` at `0x18001b751`
- `KERNEL32!DeleteFileA` at `0x18001b77a`
- `KERNEL32!DeleteFileA` at `0x18001b6fa`
- `KERNEL32!DeleteFileA` at `0x18001b709`
- `KERNEL32!DeleteFileA` at `0x18001b751`
- `KERNEL32!DeleteFileA` at `0x18001b77a`
- `KERNEL32!GetTempFileNameA` at `0x18001b5fa`
- `KERNEL32!GetTempFileNameA` at `0x18001b5fa`
- `KERNEL32!GetFileAttributesA` at `0x18001b59b`
- `KERNEL32!GetFileAttributesA` at `0x18001b59b`
- `KERNEL32!MoveFileA` at `0x18001b6ec`
- `KERNEL32!MoveFileA` at `0x18001b73c`
- `KERNEL32!MoveFileA` at `0x18001b767`
- `KERNEL32!MoveFileA` at `0x18001b6ec`
- `KERNEL32!MoveFileA` at `0x18001b73c`
- `KERNEL32!MoveFileA` at `0x18001b767`

## pseudocode

```c
__int64 __fastcall _HrRename(struct FILEREF **a1, struct CFileRep *a2)
{
  __int64 v2; // rax
  CFileRep *v3; // r15
  const CHAR *NonPrintFullPath; // rax
  DWORD FileAttributesA; // r14d
  const CHAR *NonPrintDriveDir; // rax
  DWORD LastError; // eax
  int ReplacableFileErr; // edi
  struct FILEREF *v10; // rbx
  unsigned int FileLength; // eax
  const CHAR *v12; // rax
  const char *v13; // rax
  const CHAR *v14; // rbx
  const CHAR *v15; // rax
  const CHAR *v16; // rax
  const CHAR *v17; // rax
  struct FILEREF *v19; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[24]; // [rsp+28h] [rbp-D8h] BYREF
  struct FILEREF *v21; // [rsp+40h] [rbp-C0h] BYREF
  CHAR v22[24]; // [rsp+48h] [rbp-B8h] BYREF
  CHAR TempFileName[4112]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = (__int64)*a1;
  v19 = 0;
  v3 = *(CFileRep **)(v2 + 24);
  CFileRep::CFileRep((CFileRep *)v22);
  NonPrintFullPath = CFileRep::GetNonPrintFullPath(a2);
  FileAttributesA = GetFileAttributesA(NonPrintFullPath);
  if ( FileAttributesA != -1 )
  {
    CFileRep::CFileRep((CFileRep *)v20);
    if ( CFileRep::GetNonPrintDriveDir(a2) && *CFileRep::GetNonPrintDriveDir(a2) )
    {
      CFileRep::SetFullPath((CFileRep *)v20, a2);
    }
    else if ( !(unsigned int)RbyGetCwd((struct CFileRep *)v20) )
    {
      ReplacableFileErr = -2147287035;
      goto LABEL_7;
    }
    NonPrintDriveDir = CFileRep::GetNonPrintDriveDir((CFileRep *)v20);
    if ( !GetTempFileNameA(NonPrintDriveDir, "VB", 0, TempFileName) )
    {
      LastError = GetLastError();
      ReplacableFileErr = HrFromDosError(LastError);
LABEL_7:
      CFileRep::~CFileRep((CFileRep *)v20);
      goto LABEL_23;
    }
    CFileRep::~CFileRep((CFileRep *)v20);
    CFileRep::SetFullPath((CFileRep *)v22, TempFileName);
    ReplacableFileErr = HrFrefOpen(&v19, (struct CFileRep *)v22, 0x1001u);
    if ( ReplacableFileErr < 0 )
      goto LABEL_23;
    CFileRep::SetFullPath((CFileRep *)v22, a2);
    ReplacableFileErr = HrFrefOpen(&v21, a2, 0);
    if ( ReplacableFileErr < 0 )
    {
      _FrefDeleteFileRef(v19, 0);
      goto LABEL_23;
    }
    v10 = v21;
    FileLength = RbyGetFileLength(v21);
    ReplacableFileErr = (unsigned int)RbyCopyFile(v10, v19, FileLength);
    _FrefDeleteFileRef(v19, 0);
    _FrefDeleteFileRef(v10, 0);
    v12 = CFileRep::GetNonPrintFullPath(a2);
    if ( ReplacableFileErr < 0 )
    {
      MoveFileA(TempFileName, v12);
      goto LABEL_23;
    }
    if ( !DeleteFileA(v12) )
    {
      DeleteFileA(TempFileName);
LABEL_17:
      v13 = CFileRep::GetNonPrintFullPath(a2);
      ReplacableFileErr = _HrGetReplacableFileErr(v13);
      goto LABEL_23;
    }
  }
  v14 = CFileRep::GetNonPrintFullPath(a2);
  v15 = CFileRep::GetNonPrintFullPath(v3);
  if ( !MoveFileA(v15, v14) )
  {
    v16 = CFileRep::GetNonPrintFullPath(a2);
    DeleteFileA(v16);
    v17 = CFileRep::GetNonPrintFullPath(a2);
    MoveFileA(TempFileName, v17);
    goto LABEL_17;
  }
  if ( FileAttributesA != -1 )
    DeleteFileA(TempFileName);
  ReplacableFileErr = 0;
LABEL_23:
  CFileRep::~CFileRep((CFileRep *)v22);
  return (unsigned int)ReplacableFileErr;
}

```

## disassembly

```asm
0x18001b544  mov     [rsp-8+arg_10], rbx
0x18001b549  push    rbp
0x18001b54a  push    rsi
0x18001b54b  push    rdi
0x18001b54c  push    r14
0x18001b54e  push    r15
0x18001b550  lea     rbp, [rsp-0F80h]
0x18001b558  mov     eax, 1080h
0x18001b55d  call    _alloca_probe
0x18001b562  sub     rsp, rax
0x18001b565  mov     rax, cs:__security_cookie
0x18001b56c  xor     rax, rsp
0x18001b56f  mov     [rbp+0FA0h+var_30], rax
0x18001b576  mov     rax, [rcx]
0x18001b579  and     [rsp+10A0h+var_1080], 0
0x18001b57f  lea     rcx, [rsp+10A0h+var_1058]; this
0x18001b584  mov     r15, [rax+18h]
0x18001b588  mov     rsi, rdx
0x18001b58b  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x18001b590  mov     rcx, rsi; this
0x18001b593  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b598  mov     rcx, rax; lpFileName
0x18001b59b  call    cs:__imp_GetFileAttributesA
0x18001b5a1  mov     r14d, eax
0x18001b5a4  cmp     eax, 0FFFFFFFFh
0x18001b5a7  jz      loc_18001B723
0x18001b5ad  lea     rcx, [rsp+10A0h+var_1078]; this
0x18001b5b2  call    ??0CFileRep@@QEAA@XZ; CFileRep::CFileRep(void)
0x18001b5b7  mov     rcx, rsi; this
0x18001b5ba  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18001b5bf  test    rax, rax
0x18001b5c2  jz      short loc_18001B622
0x18001b5c4  mov     rcx, rsi; this
0x18001b5c7  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18001b5cc  cmp     byte ptr [rax], 0
0x18001b5cf  jz      short loc_18001B622
0x18001b5d1  lea     rcx, [rsp+10A0h+var_1078]; this
0x18001b5d6  mov     rdx, rsi; struct CFileRep *
0x18001b5d9  call    ?SetFullPath@CFileRep@@QEAAHPEAV1@@Z; CFileRep::SetFullPath(CFileRep *)
0x18001b5de  lea     rcx, [rsp+10A0h+var_1078]; this
0x18001b5e3  call    ?GetNonPrintDriveDir@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintDriveDir(void)
0x18001b5e8  lea     r9, [rsp+10A0h+TempFileName]; lpTempFileName
0x18001b5ed  lea     rdx, PrefixString; "VB"
0x18001b5f4  mov     rcx, rax; lpPathName
0x18001b5f7  xor     r8d, r8d; uUnique
0x18001b5fa  call    cs:__imp_GetTempFileNameA
0x18001b600  test    eax, eax
0x18001b602  jnz     short loc_18001B637
0x18001b604  call    cs:__imp_GetLastError
0x18001b60a  mov     ecx, eax; unsigned int
0x18001b60c  call    ?HrFromDosError@@YAJI@Z; HrFromDosError(uint)
0x18001b611  mov     edi, eax
0x18001b613  lea     rcx, [rsp+10A0h+var_1078]; this
0x18001b618  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18001b61d  jmp     loc_18001B782
0x18001b622  lea     rcx, [rsp+10A0h+var_1078]; struct CFileRep *
0x18001b627  call    ?RbyGetCwd@@YAHPEAVCFileRep@@@Z; RbyGetCwd(CFileRep *)
0x18001b62c  test    eax, eax
0x18001b62e  jnz     short loc_18001B5DE
0x18001b630  mov     edi, 80030005h
0x18001b635  jmp     short loc_18001B613
0x18001b637  lea     rcx, [rsp+10A0h+var_1078]; this
0x18001b63c  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18001b641  lea     rdx, [rsp+10A0h+TempFileName]; char *
0x18001b646  lea     rcx, [rsp+10A0h+var_1058]; this
0x18001b64b  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x18001b650  lea     rdx, [rsp+10A0h+var_1058]; struct CFileRep *
0x18001b655  lea     rcx, [rsp+10A0h+var_1080]; struct FILEREF **
0x18001b65a  mov     r8d, 1001h; unsigned int
0x18001b660  call    ?HrFrefOpen@@YAJPEAPEAUFILEREF@@PEAVCFileRep@@I@Z; HrFrefOpen(FILEREF * *,CFileRep *,uint)
0x18001b665  mov     edi, eax
0x18001b667  test    eax, eax
0x18001b669  js      loc_18001B782
0x18001b66f  lea     rcx, [rsp+10A0h+var_1058]; this
0x18001b674  mov     rdx, rsi; struct CFileRep *
0x18001b677  call    ?SetFullPath@CFileRep@@QEAAHPEAV1@@Z; CFileRep::SetFullPath(CFileRep *)
0x18001b67c  lea     rcx, [rsp+10A0h+var_1060]; struct FILEREF **
0x18001b681  xor     r8d, r8d; unsigned int
0x18001b684  mov     rdx, rsi; struct CFileRep *
0x18001b687  call    ?HrFrefOpen@@YAJPEAPEAUFILEREF@@PEAVCFileRep@@I@Z; HrFrefOpen(FILEREF * *,CFileRep *,uint)
0x18001b68c  mov     edi, eax
0x18001b68e  test    eax, eax
0x18001b690  jns     short loc_18001B6A3
0x18001b692  mov     rcx, [rsp+10A0h+var_1080]; struct FILEREF *
0x18001b697  xor     edx, edx; int
0x18001b699  call    ?_FrefDeleteFileRef@@YAXPEAUFILEREF@@H@Z; _FrefDeleteFileRef(FILEREF *,int)
0x18001b69e  jmp     loc_18001B782
0x18001b6a3  mov     rbx, [rsp+10A0h+var_1060]
0x18001b6a8  mov     rcx, rbx; struct FILEREF *
0x18001b6ab  call    ?RbyGetFileLength@@YAJPEAUFILEREF@@@Z; RbyGetFileLength(FILEREF *)
0x18001b6b0  mov     rdx, [rsp+10A0h+var_1080]; struct FILEREF *
0x18001b6b5  mov     rcx, rbx; struct FILEREF *
0x18001b6b8  mov     r8d, eax; int
0x18001b6bb  call    ?RbyCopyFile@@YAJPEAUFILEREF@@0J@Z; RbyCopyFile(FILEREF *,FILEREF *,long)
0x18001b6c0  mov     rcx, [rsp+10A0h+var_1080]; struct FILEREF *
0x18001b6c5  xor     edx, edx; int
0x18001b6c7  mov     edi, eax
0x18001b6c9  call    ?_FrefDeleteFileRef@@YAXPEAUFILEREF@@H@Z; _FrefDeleteFileRef(FILEREF *,int)
0x18001b6ce  xor     edx, edx; int
0x18001b6d0  mov     rcx, rbx; struct FILEREF *
0x18001b6d3  call    ?_FrefDeleteFileRef@@YAXPEAUFILEREF@@H@Z; _FrefDeleteFileRef(FILEREF *,int)
0x18001b6d8  mov     rcx, rsi; this
0x18001b6db  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b6e0  test    edi, edi
0x18001b6e2  jns     short loc_18001B6F7
0x18001b6e4  lea     rcx, [rsp+10A0h+TempFileName]; lpExistingFileName
0x18001b6e9  mov     rdx, rax; lpNewFileName
0x18001b6ec  call    cs:__imp_MoveFileA
0x18001b6f2  jmp     loc_18001B782
0x18001b6f7  mov     rcx, rax; lpFileName
0x18001b6fa  call    cs:__imp_DeleteFileA
0x18001b700  test    eax, eax
0x18001b702  jnz     short loc_18001B723
0x18001b704  lea     rcx, [rsp+10A0h+TempFileName]; lpFileName
0x18001b709  call    cs:__imp_DeleteFileA
0x18001b70f  mov     rcx, rsi; this
0x18001b712  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b717  mov     rcx, rax; char *
0x18001b71a  call    ?_HrGetReplacableFileErr@@YAJPEBD@Z; _HrGetReplacableFileErr(char const *)
0x18001b71f  mov     edi, eax
0x18001b721  jmp     short loc_18001B782
0x18001b723  mov     rcx, rsi; this
0x18001b726  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b72b  mov     rcx, r15; this
0x18001b72e  mov     rbx, rax
0x18001b731  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b736  mov     rdx, rbx; lpNewFileName
0x18001b739  mov     rcx, rax; lpExistingFileName
0x18001b73c  call    cs:__imp_MoveFileA
0x18001b742  test    eax, eax
0x18001b744  jnz     short loc_18001B76F
0x18001b746  mov     rcx, rsi; this
0x18001b749  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b74e  mov     rcx, rax; lpFileName
0x18001b751  call    cs:__imp_DeleteFileA
0x18001b757  mov     rcx, rsi; this
0x18001b75a  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x18001b75f  lea     rcx, [rsp+10A0h+TempFileName]; lpExistingFileName
0x18001b764  mov     rdx, rax; lpNewFileName
0x18001b767  call    cs:__imp_MoveFileA
0x18001b76d  jmp     short loc_18001B70F
0x18001b76f  cmp     r14d, 0FFFFFFFFh
0x18001b773  jz      short loc_18001B780
0x18001b775  lea     rcx, [rsp+10A0h+TempFileName]; lpFileName
0x18001b77a  call    cs:__imp_DeleteFileA
0x18001b780  xor     edi, edi
0x18001b782  lea     rcx, [rsp+10A0h+var_1058]; this
0x18001b787  call    ??1CFileRep@@QEAA@XZ; CFileRep::~CFileRep(void)
0x18001b78c  mov     eax, edi
0x18001b78e  mov     rcx, [rbp+0FA0h+var_30]
0x18001b795  xor     rcx, rsp; StackCookie
0x18001b798  call    __security_check_cookie
0x18001b79d  mov     rbx, [rsp+10A0h+arg_10]
0x18001b7a5  add     rsp, 1080h
0x18001b7ac  pop     r15
0x18001b7ae  pop     r14
0x18001b7b0  pop     rdi
0x18001b7b1  pop     rsi
0x18001b7b2  pop     rbp
0x18001b7b3  retn
```
