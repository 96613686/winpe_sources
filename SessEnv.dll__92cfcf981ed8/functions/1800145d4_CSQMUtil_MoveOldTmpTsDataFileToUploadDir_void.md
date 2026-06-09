# CSQMUtil::MoveOldTmpTsDataFileToUploadDir(void)

- ea: `0x1800145d4`
- end: `0x18001475c`
- name: `?MoveOldTmpTsDataFileToUploadDir@CSQMUtil@@SAJXZ`
- size: `392`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800407a8`

## callees

- `0x180003f30`
- `0x1800145d4`
- `0x180017b30`
- `0x18001a280`
- `0x18001a8d0`
- `0x18001ad5c`
- `0x180040b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146f4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180014685`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180014685`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001472c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001472c`
- `api-ms-win-core-file-l2-1-0!MoveFileWithProgressW` at `0x1800146ea`
- `api-ms-win-core-file-l2-1-0!MoveFileWithProgressW` at `0x1800146ea`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180014646`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180014646`

## string_xrefs

- `0x18001470c`: `MoveFile failed: 0x%x in %s`
- `0x180014718`: `CSQMUtil::MoveOldTmpTsDataFileToUploadDir`

## pseudocode

```c
__int64 CSQMUtil::MoveOldTmpTsDataFileToUploadDir(void)
{
  WCHAR *v0; // rdi
  unsigned int v1; // ebx
  HANDLE FirstFileW; // rsi
  int v3; // eax
  signed int LastError; // eax
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[528]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR FileName[1024]; // [rsp+4A0h] [rbp+3A0h] BYREF

  memset_0(v8, 0, 0x208u);
  memset_0(FileName, 0, sizeof(FileName));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v0 = 0;
  lpNewFileName = 0;
  GetTempPath2W(260, v8);
  v1 = StringCchPrintfW(FileName, 0x400u, L"%s%s.sqm", v8, L"tsSessEnv");
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    _DbgPrintMessage(1, "%ws file doesn't exists", FileName);
LABEL_10:
    FindClose(FirstFileW);
    goto LABEL_11;
  }
  v3 = CSQMUtil::BuildUploadFileNameStr((unsigned __int16 **)&lpNewFileName);
  v0 = (WCHAR *)lpNewFileName;
  v1 = v3;
  if ( v3 >= 0 )
  {
    if ( !MoveFileWithProgressW(FileName, lpNewFileName, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(4, "MoveFile failed: 0x%x in %s", v1, "CSQMUtil::MoveOldTmpTsDataFileToUploadDir");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "BuildUploadFileNameStr failed: 0x%x in %s",
      (unsigned int)v3,
      "CSQMUtil::MoveOldTmpTsDataFileToUploadDir");
  }
  if ( FirstFileW )
    goto LABEL_10;
LABEL_11:
  if ( v0 )
    operator delete(v0);
  return v1;
}

```

## disassembly

```asm
0x1800145d4  push    rbp
0x1800145d6  push    rbx
0x1800145d7  push    rsi
0x1800145d8  push    rdi
0x1800145d9  lea     rbp, [rsp-0BB8h]
0x1800145e1  sub     rsp, 0CB8h
0x1800145e8  mov     rax, cs:__security_cookie
0x1800145ef  xor     rax, rsp
0x1800145f2  mov     [rbp+0BD0h+var_30], rax
0x1800145f9  xor     edx, edx; Val
0x1800145fb  lea     rcx, [rbp+0BD0h+var_A40]; void *
0x180014602  mov     r8d, 208h; Size
0x180014608  call    memset_0
0x18001460d  xor     edx, edx; Val
0x18001460f  lea     rcx, [rbp+0BD0h+FileName]; void *
0x180014616  mov     r8d, 800h; Size
0x18001461c  call    memset_0
0x180014621  xor     edx, edx; Val
0x180014623  lea     rcx, [rsp+0CD0h+FindFileData]; void *
0x180014628  mov     r8d, 250h; Size
0x18001462e  call    memset_0
0x180014633  xor     edi, edi
0x180014635  lea     rdx, [rbp+0BD0h+var_A40]
0x18001463c  mov     ecx, 104h
0x180014641  mov     [rsp+0CD0h+lpNewFileName], rdi
0x180014646  call    cs:__imp_GetTempPath2W
0x18001464c  lea     rax, aTssessenv; "tsSessEnv"
0x180014653  mov     edx, 400h; unsigned __int64
0x180014658  lea     r9, [rbp+0BD0h+var_A40]
0x18001465f  mov     qword ptr [rsp+0CD0h+dwFlags], rax
0x180014664  lea     r8, aSSSqm; "%s%s.sqm"
0x18001466b  lea     rcx, [rbp+0BD0h+FileName]; unsigned __int16 *
0x180014672  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014677  lea     rdx, [rsp+0CD0h+FindFileData]; lpFindFileData
0x18001467c  mov     ebx, eax
0x18001467e  lea     rcx, [rbp+0BD0h+FileName]; lpFileName
0x180014685  call    cs:__imp_FindFirstFileW
0x18001468b  mov     rsi, rax
0x18001468e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014692  jnz     short loc_1800146AC
0x180014694  lea     r8, [rbp+0BD0h+FileName]
0x18001469b  lea     rdx, aWsFileDoesnTEx; "%ws file doesn't exists"
0x1800146a2  lea     ecx, [rdi+1]; int
0x1800146a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800146aa  jmp     short loc_180014729
0x1800146ac  lea     rcx, [rsp+0CD0h+lpNewFileName]; unsigned __int16 **
0x1800146b1  call    ?BuildUploadFileNameStr@CSQMUtil@@CAJPEAPEAG@Z; CSQMUtil::BuildUploadFileNameStr(ushort * *)
0x1800146b6  mov     rdi, [rsp+0CD0h+lpNewFileName]
0x1800146bb  mov     ebx, eax
0x1800146bd  test    eax, eax
0x1800146bf  jns     short loc_1800146D2
0x1800146c1  mov     r8d, eax
0x1800146c4  lea     rdx, aBuilduploadfil_0; "BuildUploadFileNameStr failed: 0x%x in "...
0x1800146cb  mov     ecx, 8
0x1800146d0  jmp     short loc_180014718
0x1800146d2  xor     r9d, r9d; lpData
0x1800146d5  mov     [rsp+0CD0h+dwFlags], 2; dwFlags
0x1800146dd  xor     r8d, r8d; lpProgressRoutine
0x1800146e0  lea     rcx, [rbp+0BD0h+FileName]; lpExistingFileName
0x1800146e7  mov     rdx, rdi; lpNewFileName
0x1800146ea  call    cs:__imp_MoveFileWithProgressW
0x1800146f0  test    eax, eax
0x1800146f2  jnz     short loc_180014724
0x1800146f4  call    cs:__imp_GetLastError
0x1800146fa  mov     ebx, eax
0x1800146fc  test    eax, eax
0x1800146fe  jle     short loc_180014709
0x180014700  movzx   ebx, ax
0x180014703  or      ebx, 80070000h
0x180014709  mov     r8d, ebx
0x18001470c  lea     rdx, aMovefileFailed; "MoveFile failed: 0x%x in %s"
0x180014713  mov     ecx, 4; int
0x180014718  lea     r9, aCsqmutilMoveol; "CSQMUtil::MoveOldTmpTsDataFileToUploadD"...
0x18001471f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014724  test    rsi, rsi
0x180014727  jz      short loc_180014732
0x180014729  mov     rcx, rsi; hFindFile
0x18001472c  call    cs:__imp_FindClose
0x180014732  test    rdi, rdi
0x180014735  jz      short loc_18001473F
0x180014737  mov     rcx, rdi; Block
0x18001473a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001473f  mov     eax, ebx
0x180014741  mov     rcx, [rbp+0BD0h+var_30]
0x180014748  xor     rcx, rsp; StackCookie
0x18001474b  call    __security_check_cookie
0x180014750  add     rsp, 0CB8h
0x180014757  pop     rdi
0x180014758  pop     rsi
0x180014759  pop     rbx
0x18001475a  pop     rbp
0x18001475b  retn
```
