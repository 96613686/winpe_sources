# RestoreFiles(HWND__ *,ushort *,ushort const *,ushort const *,ulong)

- ea: `0x180016268`
- end: `0x1800166c3`
- name: `?RestoreFiles@@YAJPEAUHWND__@@PEAGPEBG2K@Z`
- size: `1115`
- prototype: `__int64 __fastcall(HWND, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x1800171b0`

## callees

- `0x1800035c8`
- `0x180008a6c`
- `0x180015aa0`
- `0x180015d34`
- `0x180015e48`
- `0x180015ef8`
- `0x180016268`
- `0x1800166cc`
- `0x180016ad0`
- `0x180016e3c`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!DestroyWindow` at `0x1800164f2`
- `USER32!DestroyWindow` at `0x1800164f2`
- `USER32!UpdateWindow` at `0x1800163d4`
- `USER32!UpdateWindow` at `0x180016671`
- `USER32!UpdateWindow` at `0x1800163d4`
- `USER32!UpdateWindow` at `0x180016671`
- `USER32!ShowWindow` at `0x1800163a5`
- `USER32!ShowWindow` at `0x1800163a5`
- `USER32!GetDlgItem` at `0x1800163eb`
- `USER32!GetDlgItem` at `0x18001640d`
- `USER32!GetDlgItem` at `0x18001667f`
- `USER32!GetDlgItem` at `0x1800163eb`
- `USER32!GetDlgItem` at `0x18001640d`
- `USER32!GetDlgItem` at `0x18001667f`
- `USER32!SendMessageW` at `0x1800163ff`
- `USER32!SendMessageW` at `0x180016422`
- `USER32!SendMessageW` at `0x180016693`
- `USER32!SendMessageW` at `0x1800163ff`
- `USER32!SendMessageW` at `0x180016422`
- `USER32!SendMessageW` at `0x180016693`
- `USER32!CreateDialogParamW` at `0x180016395`
- `USER32!CreateDialogParamW` at `0x180016395`
- `KERNEL32!LocalFree` at `0x18001634a`
- `KERNEL32!LocalFree` at `0x180016511`
- `KERNEL32!LocalFree` at `0x18001634a`
- `KERNEL32!LocalFree` at `0x180016511`
- `KERNEL32!GetWindowsDirectoryW` at `0x180016434`
- `KERNEL32!GetWindowsDirectoryW` at `0x180016434`
- `KERNEL32!CloseHandle` at `0x180016503`
- `KERNEL32!CloseHandle` at `0x180016503`
- `KERNEL32!DeleteFileW` at `0x180016606`
- `KERNEL32!DeleteFileW` at `0x180016625`
- `KERNEL32!DeleteFileW` at `0x180016606`
- `KERNEL32!DeleteFileW` at `0x180016625`
- `KERNEL32!GetFileAttributesW` at `0x180016634`
- `KERNEL32!GetFileAttributesW` at `0x180016634`
- `KERNEL32!SetFileAttributesW` at `0x1800165ce`
- `KERNEL32!SetFileAttributesW` at `0x1800165f9`
- `KERNEL32!SetFileAttributesW` at `0x1800165ce`
- `KERNEL32!SetFileAttributesW` at `0x1800165f9`
- `KERNEL32!CopyFileW` at `0x1800165e3`
- `KERNEL32!CopyFileW` at `0x1800165e3`

## pseudocode

```c
__int64 __fastcall RestoreFiles(
        HWND a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int16 a5)
{
  unsigned __int16 *v6; // rdi
  int v8; // r12d
  unsigned int v10; // r14d
  HWND DialogParamW; // rsi
  unsigned __int16 v12; // bx
  unsigned __int16 *i; // rcx
  __int64 v14; // rdx
  HWND DlgItem; // rax
  HWND v16; // rax
  const WCHAR *v17; // rbx
  unsigned int RefCountFrReg; // eax
  unsigned int v19; // eax
  const unsigned __int16 *v20; // rcx
  const unsigned __int16 *v21; // r8
  WCHAR *v22; // rdx
  __int64 v23; // rax
  HWND v24; // rax
  DWORD dwFileAttributes[4]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h]
  __int128 v28; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v29; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v31[522]; // [rsp+7Ch] [rbp-84h] BYREF
  WCHAR FileName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR Buffer[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v6 = a2;
  v29 = a2;
  memset_0(&hObject, 0, 0x420u);
  v8 = 0;
  *(_OWORD *)dwFileAttributes = 0;
  v27 = 0;
  v28 = 0;
  if ( !v6 )
  {
    GetListFromIniFile(a3, a4, &v29);
    v8 = 1;
    v6 = v29;
    if ( !v29 )
      return 0;
  }
  if ( !*v6 )
    return 0;
  if ( !UninstallInfoInit((struct _BAKDATA *)&hObject, a3, a4, 0) )
  {
    if ( (a5 & 8) == 0 )
      MsgBox2Param(0, 0x485u, 0, 0, 0x30u, 0);
    if ( v8 )
      LocalFree(v6);
    return 2147500037LL;
  }
  v10 = 0;
  DialogParamW = 0;
  if ( (a5 & 0x10) == 0 )
  {
    v12 = 0;
    DialogParamW = CreateDialogParamW(g_hinstMUI, (LPCWSTR)0x48A, a1, SaveRestoreProgressDlgProc, 0);
    ShowWindow(DialogParamW, (a5 & 0x10) + 1);
    for ( i = v6; *i; i += v14 + 1 )
    {
      ++v12;
      v14 = -1;
      do
        ++v14;
      while ( i[v14] );
    }
    UpdateWindow(DialogParamW);
    DlgItem = GetDlgItem(DialogParamW, 1163);
    SendMessageW(DlgItem, 0x401u, 0, v12 << 16);
    v16 = GetDlgItem(DialogParamW, 1163);
    SendMessageW(v16, 0x404u, 1u, 0);
  }
  GetWindowsDirectoryW(Buffer, 0x104u);
  v17 = v6;
  while ( !v10 && *v17 )
  {
    *((_QWORD *)&v27 + 1) = 0xFFFFFFFF00000000uLL;
    *(_QWORD *)dwFileAttributes = v17;
    FillBackupInfo(v31, (struct _FILELIST *)dwFileAttributes);
    if ( dwFileAttributes[3] == -1 || !DWORD2(v27) || HIDWORD(v27) == -1 )
    {
      if ( (a5 & 4) != 0 || DeleteFileW(v17) || GetFileAttributesW(v17) == -1 )
        goto LABEL_48;
      v21 = L"NUL";
      v22 = (WCHAR *)v17;
LABEL_47:
      initcopy(v20, v22, v21);
      goto LABEL_48;
    }
    if ( MakeBakName(*(const unsigned __int16 **)dwFileAttributes, FileName) )
    {
      if ( (a5 & 0x400) != 0 && DWORD1(v28) != -1 )
      {
        RefCountFrReg = GetRefCountFrReg(*(LPCWSTR *)dwFileAttributes);
        if ( RefCountFrReg > DWORD1(v28) )
          goto LABEL_48;
      }
      v19 = RestoreSingleFile((struct _FILELIST *)dwFileAttributes, FileName, hObject);
      if ( !v19 )
      {
        SetFileAttributesW(FileName, dwFileAttributes[3]);
        if ( CopyFileW(FileName, *(LPCWSTR *)dwFileAttributes, 0) )
        {
          SetFileAttributesW(FileName, 0x80u);
          DeleteFileW(FileName);
          goto LABEL_48;
        }
        v21 = *(const unsigned __int16 **)dwFileAttributes;
        v22 = FileName;
        goto LABEL_47;
      }
      if ( (a5 & 8) == 0 )
      {
        StringCchPrintfW(FileName, 0x104u, L"%d", v19);
        if ( (unsigned int)MsgBox2Param(a1, 0x486u, *(const unsigned __int16 **)dwFileAttributes, FileName, 0x30u, 4u) == 7 )
          v10 = -2147467259;
      }
    }
    else if ( (a5 & 8) == 0
           && (unsigned int)MsgBox2Param(a1, 0x487u, *(const unsigned __int16 **)dwFileAttributes, 0, 0x30u, 4u) == 7 )
    {
      v10 = -2147467259;
      break;
    }
LABEL_48:
    v23 = -1;
    do
      ++v23;
    while ( v17[v23] );
    v17 += v23 + 1;
    if ( (a5 & 0x10) == 0 )
    {
      UpdateWindow(DialogParamW);
      v24 = GetDlgItem(DialogParamW, 1163);
      SendMessageW(v24, 0x405u, 0, 0);
    }
  }
  if ( DialogParamW )
    DestroyWindow(DialogParamW);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
    LocalFree(v6);
  return v10;
}

```

## disassembly

```asm
0x180016268  push    rbp
0x18001626a  push    rbx
0x18001626b  push    rsi
0x18001626c  push    rdi
0x18001626d  push    r12
0x18001626f  push    r13
0x180016271  push    r14
0x180016273  push    r15
0x180016275  lea     rbp, [rsp-7C8h]
0x18001627d  sub     rsp, 8C8h
0x180016284  mov     rax, cs:__security_cookie
0x18001628b  xor     rax, rsp
0x18001628e  mov     [rbp+800h+var_50], rax
0x180016295  mov     rbx, r8
0x180016298  mov     [rsp+900h+hWndParent], rcx
0x18001629d  mov     rdi, rdx
0x1800162a0  mov     [rsp+900h+var_898], rdx
0x1800162a5  xor     edx, edx; Val
0x1800162a7  lea     rcx, [rsp+900h+hObject]; void *
0x1800162ac  mov     r8d, 420h; Size
0x1800162b2  mov     rsi, r9
0x1800162b5  call    memset_0
0x1800162ba  xorps   xmm0, xmm0
0x1800162bd  xor     r15d, r15d
0x1800162c0  mov     r12d, r15d
0x1800162c3  movups  xmmword ptr [rsp+900h+dwFileAttributes], xmm0
0x1800162c8  movups  [rsp+900h+var_8B8], xmm0
0x1800162cd  movups  [rsp+900h+var_8A8], xmm0
0x1800162d2  test    rdi, rdi
0x1800162d5  jnz     short loc_1800162F9
0x1800162d7  lea     r8, [rsp+900h+var_898]; unsigned __int16 **
0x1800162dc  mov     rdx, rsi; unsigned __int16 *
0x1800162df  mov     rcx, rbx; unsigned __int16 *
0x1800162e2  call    ?GetListFromIniFile@@YAXPEBG0PEAPEAG@Z; GetListFromIniFile(ushort const *,ushort const *,ushort * *)
0x1800162e7  lea     r12d, [rdi+1]
0x1800162eb  mov     rdi, [rsp+900h+var_898]
0x1800162f0  test    rdi, rdi
0x1800162f3  jz      loc_18001669E
0x1800162f9  cmp     [rdi], r15w
0x1800162fd  jz      loc_18001669E
0x180016303  xor     r9d, r9d; int
0x180016306  lea     rcx, [rsp+900h+hObject]; struct _BAKDATA *
0x18001630b  mov     r8, rsi; unsigned __int16 *
0x18001630e  mov     rdx, rbx; unsigned __int16 *
0x180016311  call    ?UninstallInfoInit@@YAHPEAU_BAKDATA@@PEBG1H@Z; UninstallInfoInit(_BAKDATA *,ushort const *,ushort const *,int)
0x180016316  test    eax, eax
0x180016318  jnz     short loc_18001635A
0x18001631a  test    byte ptr [rbp+800h+arg_20], 8
0x180016321  jnz     short loc_180016342
0x180016323  mov     [rsp+900h+var_8D8], r15d; unsigned int
0x180016328  xor     r9d, r9d; unsigned __int16 *
0x18001632b  xor     r8d, r8d; unsigned __int16 *
0x18001632e  mov     dword ptr [rsp+900h+dwInitParam], 30h ; '0'; unsigned int
0x180016336  mov     edx, 485h; uID
0x18001633b  xor     ecx, ecx; hWnd
0x18001633d  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180016342  test    r12d, r12d
0x180016345  jz      short loc_180016350
0x180016347  mov     rcx, rdi; hMem
0x18001634a  call    cs:__imp_LocalFree
0x180016350  mov     eax, 80004005h
0x180016355  jmp     loc_1800166A0
0x18001635a  mov     r14d, r15d
0x18001635d  mov     rsi, r15
0x180016360  mov     r15d, [rbp+800h+arg_20]
0x180016367  mov     r13d, r15d
0x18001636a  and     r13d, 10h
0x18001636e  jnz     loc_180016428
0x180016374  mov     r8, [rsp+900h+hWndParent]; hWndParent
0x180016379  lea     r9, ?SaveRestoreProgressDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180016380  xor     ecx, ecx
0x180016382  mov     edx, 48Ah; lpTemplateName
0x180016387  mov     ebx, ecx
0x180016389  mov     [rsp+900h+dwInitParam], rcx; dwInitParam
0x18001638e  mov     rcx, cs:g_hinstMUI; hInstance
0x180016395  call    cs:__imp_CreateDialogParamW
0x18001639b  mov     rcx, rax; hWnd
0x18001639e  lea     edx, [r13+1]; nCmdShow
0x1800163a2  mov     rsi, rax
0x1800163a5  call    cs:__imp_ShowWindow
0x1800163ab  xor     eax, eax
0x1800163ad  mov     rcx, rdi
0x1800163b0  cmp     [rdi], ax
0x1800163b3  jz      short loc_1800163D1
0x1800163b5  inc     ebx
0x1800163b7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800163bb  inc     rdx
0x1800163be  cmp     [rcx+rdx*2], ax
0x1800163c2  jnz     short loc_1800163BB
0x1800163c4  lea     rcx, [rcx+rdx*2]
0x1800163c8  add     rcx, 2
0x1800163cc  cmp     [rcx], ax
0x1800163cf  jnz     short loc_1800163B5
0x1800163d1  mov     rcx, rsi; hWnd
0x1800163d4  call    cs:__imp_UpdateWindow
0x1800163da  movzx   eax, bx
0x1800163dd  mov     edx, 48Bh; nIDDlgItem
0x1800163e2  shl     eax, 10h
0x1800163e5  mov     rcx, rsi; hDlg
0x1800163e8  movsxd  rbx, eax
0x1800163eb  call    cs:__imp_GetDlgItem
0x1800163f1  mov     r9, rbx; lParam
0x1800163f4  xor     r8d, r8d; wParam
0x1800163f7  mov     rcx, rax; hWnd
0x1800163fa  mov     edx, 401h; Msg
0x1800163ff  call    cs:__imp_SendMessageW
0x180016405  mov     edx, 48Bh; nIDDlgItem
0x18001640a  mov     rcx, rsi; hDlg
0x18001640d  call    cs:__imp_GetDlgItem
0x180016413  xor     r9d, r9d; lParam
0x180016416  mov     edx, 404h; Msg
0x18001641b  mov     rcx, rax; hWnd
0x18001641e  lea     r8d, [r9+1]; wParam
0x180016422  call    cs:__imp_SendMessageW
0x180016428  mov     edx, 104h; uSize
0x18001642d  lea     rcx, [rbp+800h+Buffer]; lpBuffer
0x180016434  call    cs:__imp_GetWindowsDirectoryW
0x18001643a  mov     rbx, rdi
0x18001643d  xor     ecx, ecx
0x18001643f  test    r14d, r14d
0x180016442  jnz     loc_1800164EA
0x180016448  cmp     [rbx], cx
0x18001644b  jz      loc_1800164EA
0x180016451  mov     dword ptr [rsp+900h+var_8B8+8], ecx
0x180016455  lea     rdx, [rsp+900h+dwFileAttributes]; struct _FILELIST *
0x18001645a  lea     rcx, [rsp+900h+var_884]; lpFileName
0x18001645f  mov     qword ptr [rsp+900h+dwFileAttributes], rbx
0x180016464  mov     dword ptr [rsp+900h+var_8B8+0Ch], 0FFFFFFFFh
0x18001646c  call    ?FillBackupInfo@@YAXPEBGPEAU_FILELIST@@@Z; FillBackupInfo(ushort const *,_FILELIST *)
0x180016471  cmp     [rsp+900h+dwFileAttributes+0Ch], 0FFFFFFFFh
0x180016476  jz      loc_18001661C
0x18001647c  xor     ecx, ecx
0x18001647e  cmp     dword ptr [rsp+900h+var_8B8+8], ecx
0x180016482  jbe     loc_18001661C
0x180016488  cmp     dword ptr [rsp+900h+var_8B8+0Ch], 0FFFFFFFFh
0x18001648d  jz      loc_18001661C
0x180016493  mov     rcx, qword ptr [rsp+900h+dwFileAttributes]; unsigned __int16 *
0x180016498  lea     rdx, [rbp+800h+FileName]; unsigned __int16 *
0x18001649f  call    ?MakeBakName@@YAHPEBGPEAG_K@Z; MakeBakName(ushort const *,ushort *,unsigned __int64)
0x1800164a4  xor     ecx, ecx
0x1800164a6  test    eax, eax
0x1800164a8  jnz     short loc_18001651F
0x1800164aa  test    r15b, 8
0x1800164ae  jnz     loc_180016650
0x1800164b4  mov     r8, qword ptr [rsp+900h+dwFileAttributes]; unsigned __int16 *
0x1800164b9  xor     r9d, r9d; unsigned __int16 *
0x1800164bc  mov     rcx, [rsp+900h+hWndParent]; hWnd
0x1800164c1  mov     edx, 487h; uID
0x1800164c6  mov     [rsp+900h+var_8D8], 4; unsigned int
0x1800164ce  mov     dword ptr [rsp+900h+dwInitParam], 30h ; '0'; unsigned int
0x1800164d6  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800164db  cmp     eax, 7
0x1800164de  jnz     loc_18001664E
0x1800164e4  mov     r14d, 80004005h
0x1800164ea  test    rsi, rsi
0x1800164ed  jz      short loc_1800164F8
0x1800164ef  mov     rcx, rsi; hWnd
0x1800164f2  call    cs:__imp_DestroyWindow
0x1800164f8  mov     rcx, [rsp+900h+hObject]; hObject
0x1800164fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016501  jz      short loc_180016509
0x180016503  call    cs:__imp_CloseHandle
0x180016509  test    r12d, r12d
0x18001650c  jz      short loc_180016517
0x18001650e  mov     rcx, rdi; hMem
0x180016511  call    cs:__imp_LocalFree
0x180016517  mov     eax, r14d
0x18001651a  jmp     loc_1800166A0
0x18001651f  bt      r15d, 0Ah
0x180016524  jnb     short loc_180016541
0x180016526  cmp     dword ptr [rsp+900h+var_8A8+4], 0FFFFFFFFh
0x18001652b  jz      short loc_180016541
0x18001652d  mov     rcx, qword ptr [rsp+900h+dwFileAttributes]; lpValueName
0x180016532  call    ?GetRefCountFrReg@@YAKPEBG@Z; GetRefCountFrReg(ushort const *)
0x180016537  cmp     eax, dword ptr [rsp+900h+var_8A8+4]
0x18001653b  ja      loc_18001664E
0x180016541  mov     r8, [rsp+900h+hObject]; void *
0x180016546  lea     rdx, [rbp+800h+FileName]; unsigned __int16 *
0x18001654d  lea     rcx, [rsp+900h+dwFileAttributes]; struct _FILELIST *
0x180016552  call    ?RestoreSingleFile@@YAHPEAU_FILELIST@@PEBGPEAX@Z; RestoreSingleFile(_FILELIST *,ushort const *,void *)
0x180016557  xor     ecx, ecx
0x180016559  test    eax, eax
0x18001655b  jz      short loc_1800165C3
0x18001655d  test    r15b, 8
0x180016561  jnz     loc_180016650
0x180016567  mov     r9d, eax
0x18001656a  lea     r8, aD; "%d"
0x180016571  mov     edx, 104h; unsigned __int64
0x180016576  lea     rcx, [rbp+800h+FileName]; unsigned __int16 *
0x18001657d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016582  mov     r8, qword ptr [rsp+900h+dwFileAttributes]; unsigned __int16 *
0x180016587  lea     r9, [rbp+800h+FileName]; unsigned __int16 *
0x18001658e  mov     rcx, [rsp+900h+hWndParent]; hWnd
0x180016593  mov     edx, 486h; uID
0x180016598  mov     [rsp+900h+var_8D8], 4; unsigned int
0x1800165a0  mov     dword ptr [rsp+900h+dwInitParam], 30h ; '0'; unsigned int
0x1800165a8  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800165ad  xor     ecx, ecx
0x1800165af  cmp     eax, 7
0x1800165b2  jnz     loc_180016650
0x1800165b8  mov     r14d, 80004005h
0x1800165be  jmp     loc_180016650
0x1800165c3  mov     edx, [rsp+900h+dwFileAttributes+0Ch]; dwFileAttributes
0x1800165c7  lea     rcx, [rbp+800h+FileName]; lpFileName
0x1800165ce  call    cs:__imp_SetFileAttributesW
0x1800165d4  mov     rdx, qword ptr [rsp+900h+dwFileAttributes]; lpNewFileName
0x1800165d9  lea     rcx, [rbp+800h+FileName]; lpExistingFileName
0x1800165e0  xor     r8d, r8d; bFailIfExists
0x1800165e3  call    cs:__imp_CopyFileW
0x1800165e9  test    eax, eax
0x1800165eb  jz      short loc_18001660E
0x1800165ed  mov     edx, 80h; dwFileAttributes
0x1800165f2  lea     rcx, [rbp+800h+FileName]; lpFileName
0x1800165f9  call    cs:__imp_SetFileAttributesW
0x1800165ff  lea     rcx, [rbp+800h+FileName]; lpFileName
0x180016606  call    cs:__imp_DeleteFileW
0x18001660c  jmp     short loc_18001664E
0x18001660e  mov     r8, qword ptr [rsp+900h+dwFileAttributes]
0x180016613  lea     rdx, [rbp+800h+FileName]
0x18001661a  jmp     short loc_180016649
0x18001661c  test    r15b, 4
0x180016620  jnz     short loc_18001664E
0x180016622  mov     rcx, rbx; lpFileName
0x180016625  call    cs:__imp_DeleteFileW
0x18001662b  xor     ecx, ecx
0x18001662d  test    eax, eax
0x18001662f  jnz     short loc_180016650
0x180016631  mov     rcx, rbx; lpFileName
0x180016634  call    cs:__imp_GetFileAttributesW
0x18001663a  cmp     eax, 0FFFFFFFFh
0x18001663d  jz      short loc_18001664E
0x18001663f  lea     r8, aNul; "NUL"
0x180016646  mov     rdx, rbx; unsigned __int16 *
0x180016649  call    ?initcopy@@YAXPEBG00@Z; initcopy(ushort const *,ushort const *,ushort const *)
0x18001664e  xor     ecx, ecx
0x180016650  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016654  inc     rax
0x180016657  cmp     [rbx+rax*2], cx
0x18001665b  jnz     short loc_180016654
0x18001665d  lea     rbx, [rbx+rax*2]
0x180016661  add     rbx, 2
0x180016665  test    r13d, r13d
0x180016668  jnz     loc_18001643F
0x18001666e  mov     rcx, rsi; hWnd
0x180016671  call    cs:__imp_UpdateWindow
0x180016677  mov     edx, 48Bh; nIDDlgItem
0x18001667c  mov     rcx, rsi; hDlg
0x18001667f  call    cs:__imp_GetDlgItem
0x180016685  xor     r9d, r9d; lParam
0x180016688  xor     r8d, r8d; wParam
0x18001668b  mov     rcx, rax; hWnd
0x18001668e  mov     edx, 405h; Msg
0x180016693  call    cs:__imp_SendMessageW
0x180016699  jmp     loc_18001643D
0x18001669e  xor     eax, eax
0x1800166a0  mov     rcx, [rbp+800h+var_50]
0x1800166a7  xor     rcx, rsp; StackCookie
0x1800166aa  call    __security_check_cookie
0x1800166af  add     rsp, 8C8h
0x1800166b6  pop     r15
0x1800166b8  pop     r14
0x1800166ba  pop     r13
0x1800166bc  pop     r12
0x1800166be  pop     rdi
0x1800166bf  pop     rsi
0x1800166c0  pop     rbx
0x1800166c1  pop     rbp
0x1800166c2  retn
```
