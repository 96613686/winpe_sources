# CUpdateScenarioCtrl::ProjectEsdFile(ushort const *,ushort const *)

- ea: `0x14001b310`
- end: `0x14001b6d8`
- name: `?ProjectEsdFile@CUpdateScenarioCtrl@@AEAAJPEBG0@Z`
- size: `968`
- prototype: `__int64 __fastcall(CUpdateScenarioCtrl *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x14001a670`

## callees

- `0x1400076c8`
- `0x140009700`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001b310`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14001b47a`
- `KERNEL32!DeleteFileW` at `0x14001b47a`
- `KERNEL32!MoveFileExW` at `0x14001b55e`
- `KERNEL32!MoveFileExW` at `0x14001b55e`
- `KERNEL32!CopyFileW` at `0x14001b640`
- `KERNEL32!CopyFileW` at `0x14001b640`
- `KERNEL32!GetLastError` at `0x14001b5bc`
- `KERNEL32!GetLastError` at `0x14001b650`
- `KERNEL32!GetLastError` at `0x14001b5bc`
- `KERNEL32!GetLastError` at `0x14001b650`
- `KERNEL32!SetFileAttributesW` at `0x14001b463`
- `KERNEL32!SetFileAttributesW` at `0x14001b463`
- `KERNEL32!GetFileAttributesW` at `0x14001b3b4`
- `KERNEL32!GetFileAttributesW` at `0x14001b3f5`
- `KERNEL32!GetFileAttributesW` at `0x14001b4a3`
- `KERNEL32!GetFileAttributesW` at `0x14001b3b4`
- `KERNEL32!GetFileAttributesW` at `0x14001b3f5`
- `KERNEL32!GetFileAttributesW` at `0x14001b4a3`
- `KERNEL32!CreateHardLinkW` at `0x14001b580`
- `KERNEL32!CreateHardLinkW` at `0x14001b580`

## string_xrefs

- `0x14001b4f6`: `Creating path: [%s]...`
- `0x14001b5b0`: `Successfully hardlinked: [%s] -> [%s]`
- `0x14001b5f8`: `Unable to hardlink: [%s] -> [%s] (not same device)`
- `0x14001b62b`: `Copying file: [%s] -> [%s]...`
- `0x14001b686`: `CUpdateScenarioCtrl::ProjectEsdFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdateScenarioCtrl::ProjectEsdFile(
        CUpdateScenarioCtrl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  HANDLE v8; // rcx
  HANDLE v9; // rcx
  DWORD FileAttributesW; // eax
  BOOL v11; // ebx
  DWORD v12; // eax
  BOOL v13; // edi
  HANDLE v14; // rcx
  const WCHAR *v15; // rcx
  DWORD v16; // edi
  int v17; // edi
  __int64 v18; // rcx
  int FolderPath; // eax
  signed int LastError; // eax
  __int64 v22; // [rsp+20h] [rbp-28h]

  if ( !a2 || !a3 )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_45:
    LODWORD(v22) = v7;
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"%s: Error = 0x%X",
      L"CUpdateScenarioCtrl::ProjectEsdFile",
      v22);
    goto LABEL_46;
  }
  v8 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v8 = g_shLogFile;
  OutputMsg(v8, g_shLogEvent, L"ESD source file: [%s]", a2);
  v9 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v9 = g_shLogFile;
  OutputMsg(v9, g_shLogEvent, L"ESD target file: [%s]", a3);
  FileAttributesW = GetFileAttributesW(a2);
  v11 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v11 )
  {
    v7 = -2147024894;
    v6 = 2147942402LL;
    goto LABEL_3;
  }
  v12 = GetFileAttributesW(a3);
  v13 = v12 != -1 && (v12 & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v7 = 0;
  if ( v13 )
  {
    v14 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v14 = g_shLogFile;
    OutputMsg(v14, g_shLogEvent, L"Found ESD target file: [%s]", a3);
    if ( !SetFileAttributesW(a3, 0x80u) || !DeleteFileW(a3) )
      goto LABEL_39;
  }
  if ( *((_DWORD *)this + 18) )
  {
    v15 = (const WCHAR *)*((_QWORD *)this + 10);
    if ( !v15 )
      v15 = 0;
    v16 = GetFileAttributesW(v15);
    if ( v16 == -1 )
      v17 = 0;
    else
      v17 = (v16 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v17 )
    {
      OutputMsg(
        (HANDLE)((unsigned __int64)g_shLogFile
               & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
        g_shLogEvent,
        L"Creating path: [%s]...",
        *((_QWORD *)this + 10));
      v18 = *((_QWORD *)this + 10);
      if ( !v18 )
        v18 = 0;
      FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v18);
      v7 = FolderPath;
      if ( FolderPath < 0 )
      {
        v6 = (unsigned int)FolderPath;
        goto LABEL_3;
      }
    }
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Moving file [%s] to [%s]",
      a2,
      a3);
    if ( MoveFileExW(a2, a3, 0xBu) )
      goto LABEL_44;
    goto LABEL_39;
  }
  if ( CreateHardLinkW(a3, a2, 0) )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Successfully hardlinked: [%s] -> [%s]",
      a3,
      a2);
    goto LABEL_46;
  }
  if ( GetLastError() == 17 )
  {
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Unable to hardlink: [%s] -> [%s] (not same device)",
      a2,
      a3);
    OutputMsg(
      (HANDLE)((unsigned __int64)g_shLogFile
             & -(__int64)((((unsigned __int64)g_shLogFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0)),
      g_shLogEvent,
      L"Copying file: [%s] -> [%s]...",
      a2,
      a3);
    if ( !CopyFileW(a2, a3, 0) )
    {
LABEL_39:
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_44:
      if ( (v7 & 0x80000000) != 0 )
        goto LABEL_45;
    }
  }
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x14001b310  mov     [rsp+arg_0], rbx
0x14001b315  mov     [rsp+arg_8], rbp
0x14001b31a  mov     [rsp+arg_10], rsi
0x14001b31f  push    rdi
0x14001b320  push    r14
0x14001b322  push    r15
0x14001b324  sub     rsp, 30h
0x14001b328  xor     r15d, r15d
0x14001b32b  mov     rsi, r8
0x14001b32e  mov     rbp, rdx
0x14001b331  mov     r14, rcx
0x14001b334  test    rdx, rdx
0x14001b337  jnz     short loc_14001B34A
0x14001b339  mov     ecx, 80070057h
0x14001b33e  mov     ebx, ecx
0x14001b340  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001b345  jmp     loc_14001B67F
0x14001b34a  test    rsi, rsi
0x14001b34d  jz      short loc_14001B339
0x14001b34f  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b356  mov     rcx, r15
0x14001b359  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b360  mov     r9, rbp
0x14001b363  lea     rax, [r8-1]
0x14001b367  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b36b  setnbe  al
0x14001b36e  test    al, al
0x14001b370  cmovz   rcx, r8; hFile
0x14001b374  lea     r8, aEsdSourceFileS; "ESD source file: [%s]"
0x14001b37b  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b380  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b387  mov     rcx, r15
0x14001b38a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b391  mov     r9, rsi
0x14001b394  lea     rax, [r8-1]
0x14001b398  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b39c  setnbe  al
0x14001b39f  test    al, al
0x14001b3a1  cmovz   rcx, r8; hFile
0x14001b3a5  lea     r8, aEsdTargetFileS; "ESD target file: [%s]"
0x14001b3ac  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b3b1  mov     rcx, rbp; lpFileName
0x14001b3b4  call    cs:__imp_GetFileAttributesW
0x14001b3bb  nop     dword ptr [rax+rax+00h]
0x14001b3c0  mov     ebx, eax
0x14001b3c2  cmp     eax, 0FFFFFFFFh
0x14001b3c5  jz      short loc_14001B3D1
0x14001b3c7  shr     ebx, 4
0x14001b3ca  not     ebx
0x14001b3cc  and     ebx, 1
0x14001b3cf  jmp     short loc_14001B3D4
0x14001b3d1  mov     ebx, r15d
0x14001b3d4  xor     ecx, ecx
0x14001b3d6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b3db  xor     ecx, ecx
0x14001b3dd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b3e2  test    ebx, ebx
0x14001b3e4  jnz     short loc_14001B3F2
0x14001b3e6  mov     ebx, 80070002h
0x14001b3eb  mov     ecx, ebx
0x14001b3ed  jmp     loc_14001B340
0x14001b3f2  mov     rcx, rsi; lpFileName
0x14001b3f5  call    cs:__imp_GetFileAttributesW
0x14001b3fc  nop     dword ptr [rax+rax+00h]
0x14001b401  mov     edi, eax
0x14001b403  cmp     eax, 0FFFFFFFFh
0x14001b406  jz      short loc_14001B412
0x14001b408  shr     edi, 4
0x14001b40b  not     edi
0x14001b40d  and     edi, 1
0x14001b410  jmp     short loc_14001B415
0x14001b412  mov     edi, r15d
0x14001b415  xor     ecx, ecx
0x14001b417  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b41c  xor     ecx, ecx
0x14001b41e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b423  mov     ebx, r15d
0x14001b426  test    edi, edi
0x14001b428  jz      short loc_14001B48E
0x14001b42a  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b431  mov     rcx, r15
0x14001b434  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b43b  mov     r9, rsi
0x14001b43e  lea     rax, [r8-1]
0x14001b442  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b446  setnbe  al
0x14001b449  test    al, al
0x14001b44b  cmovz   rcx, r8; hFile
0x14001b44f  lea     r8, aFoundEsdTarget; "Found ESD target file: [%s]"
0x14001b456  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b45b  mov     edx, 80h; dwFileAttributes
0x14001b460  mov     rcx, rsi; lpFileName
0x14001b463  call    cs:__imp_SetFileAttributesW
0x14001b46a  nop     dword ptr [rax+rax+00h]
0x14001b46f  test    eax, eax
0x14001b471  jz      loc_14001B650
0x14001b477  mov     rcx, rsi; lpFileName
0x14001b47a  call    cs:__imp_DeleteFileW
0x14001b481  nop     dword ptr [rax+rax+00h]
0x14001b486  test    eax, eax
0x14001b488  jz      loc_14001B650
0x14001b48e  cmp     [r14+48h], r15d
0x14001b492  jz      loc_14001B577
0x14001b498  mov     rcx, [r14+50h]
0x14001b49c  test    rcx, rcx
0x14001b49f  cmovz   rcx, r15; lpFileName
0x14001b4a3  call    cs:__imp_GetFileAttributesW
0x14001b4aa  nop     dword ptr [rax+rax+00h]
0x14001b4af  mov     edi, eax
0x14001b4b1  cmp     eax, 0FFFFFFFFh
0x14001b4b4  jz      short loc_14001B4BE
0x14001b4b6  shr     edi, 4
0x14001b4b9  and     edi, 1
0x14001b4bc  jmp     short loc_14001B4C1
0x14001b4be  mov     edi, r15d
0x14001b4c1  xor     ecx, ecx
0x14001b4c3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b4c8  xor     ecx, ecx
0x14001b4ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b4cf  test    edi, edi
0x14001b4d1  jnz     short loc_14001B51F
0x14001b4d3  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b4da  mov     r9, [r14+50h]
0x14001b4de  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b4e5  lea     rax, [r8+1]
0x14001b4e9  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b4ed  neg     rax
0x14001b4f0  sbb     rcx, rcx
0x14001b4f3  and     rcx, r8; hFile
0x14001b4f6  lea     r8, aCreatingPathS; "Creating path: [%s]..."
0x14001b4fd  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b502  mov     rcx, [r14+50h]
0x14001b506  test    rcx, rcx
0x14001b509  cmovz   rcx, r15
0x14001b50d  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x14001b512  mov     ebx, eax
0x14001b514  test    eax, eax
0x14001b516  jns     short loc_14001B51F
0x14001b518  mov     ecx, eax
0x14001b51a  jmp     loc_14001B340
0x14001b51f  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b526  mov     r9, rbp
0x14001b529  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b530  mov     [rsp+48h+var_28], rsi
0x14001b535  lea     rax, [r8+1]
0x14001b539  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b53d  neg     rax
0x14001b540  sbb     rcx, rcx
0x14001b543  and     rcx, r8; hFile
0x14001b546  lea     r8, aMovingFileSToS; "Moving file [%s] to [%s]"
0x14001b54d  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b552  mov     r8d, 0Bh; dwFlags
0x14001b558  mov     rdx, rsi; lpNewFileName
0x14001b55b  mov     rcx, rbp; lpExistingFileName
0x14001b55e  call    cs:__imp_MoveFileExW
0x14001b565  nop     dword ptr [rax+rax+00h]
0x14001b56a  test    eax, eax
0x14001b56c  jnz     loc_14001B67B
0x14001b572  jmp     loc_14001B650
0x14001b577  xor     r8d, r8d; lpSecurityAttributes
0x14001b57a  mov     rdx, rbp; lpExistingFileName
0x14001b57d  mov     rcx, rsi; lpFileName
0x14001b580  call    cs:__imp_CreateHardLinkW
0x14001b587  nop     dword ptr [rax+rax+00h]
0x14001b58c  test    eax, eax
0x14001b58e  jz      short loc_14001B5BC
0x14001b590  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b597  mov     r9, rsi
0x14001b59a  mov     [rsp+48h+var_28], rbp
0x14001b59f  lea     rax, [r8+1]
0x14001b5a3  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b5a7  neg     rax
0x14001b5aa  sbb     rcx, rcx
0x14001b5ad  and     rcx, r8
0x14001b5b0  lea     r8, aSuccessfullyHa; "Successfully hardlinked: [%s] -> [%s]"
0x14001b5b7  jmp     loc_14001B6A9
0x14001b5bc  call    cs:__imp_GetLastError
0x14001b5c3  nop     dword ptr [rax+rax+00h]
0x14001b5c8  cmp     eax, 11h
0x14001b5cb  jnz     loc_14001B6B5
0x14001b5d1  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b5d8  mov     r9, rbp
0x14001b5db  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b5e2  mov     [rsp+48h+var_28], rsi
0x14001b5e7  lea     rax, [r8+1]
0x14001b5eb  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b5ef  neg     rax
0x14001b5f2  sbb     rcx, rcx
0x14001b5f5  and     rcx, r8; hFile
0x14001b5f8  lea     r8, aUnableToHardli; "Unable to hardlink: [%s] -> [%s] (not s"...
0x14001b5ff  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b604  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b60b  mov     r9, rbp
0x14001b60e  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b615  mov     [rsp+48h+var_28], rsi
0x14001b61a  lea     rax, [r8+1]
0x14001b61e  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b622  neg     rax
0x14001b625  sbb     rcx, rcx
0x14001b628  and     rcx, r8; hFile
0x14001b62b  lea     r8, aCopyingFileSS; "Copying file: [%s] -> [%s]..."
0x14001b632  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b637  xor     r8d, r8d; bFailIfExists
0x14001b63a  mov     rdx, rsi; lpNewFileName
0x14001b63d  mov     rcx, rbp; lpExistingFileName
0x14001b640  call    cs:__imp_CopyFileW
0x14001b647  nop     dword ptr [rax+rax+00h]
0x14001b64c  test    eax, eax
0x14001b64e  jnz     short loc_14001B6B5
0x14001b650  call    cs:__imp_GetLastError
0x14001b657  nop     dword ptr [rax+rax+00h]
0x14001b65c  mov     ebx, eax
0x14001b65e  test    eax, eax
0x14001b660  jnz     short loc_14001B669
0x14001b662  mov     ebx, 80004005h
0x14001b667  jmp     short loc_14001B674
0x14001b669  jle     short loc_14001B674
0x14001b66b  movzx   ebx, ax
0x14001b66e  or      ebx, 80070000h
0x14001b674  mov     ecx, ebx
0x14001b676  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001b67b  test    ebx, ebx
0x14001b67d  jns     short loc_14001B6B5
0x14001b67f  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001b686  lea     r9, aCupdatescenari_4; "CUpdateScenarioCtrl::ProjectEsdFile"
0x14001b68d  mov     dword ptr [rsp+48h+var_28], ebx
0x14001b691  lea     rax, [r8+1]
0x14001b695  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001b699  neg     rax
0x14001b69c  sbb     rcx, rcx
0x14001b69f  and     rcx, r8; hFile
0x14001b6a2  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x14001b6a9  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001b6b0  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001b6b5  mov     ecx, ebx
0x14001b6b7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001b6bc  mov     rbp, [rsp+48h+arg_8]
0x14001b6c1  mov     eax, ebx
0x14001b6c3  mov     rbx, [rsp+48h+arg_0]
0x14001b6c8  mov     rsi, [rsp+48h+arg_10]
0x14001b6cd  add     rsp, 30h
0x14001b6d1  pop     r15
0x14001b6d3  pop     r14
0x14001b6d5  pop     rdi
0x14001b6d6  retn
```
