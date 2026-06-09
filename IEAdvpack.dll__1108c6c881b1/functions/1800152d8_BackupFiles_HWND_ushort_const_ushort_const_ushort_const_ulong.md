# BackupFiles(HWND__ *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800152d8`
- end: `0x1800156b1`
- name: `?BackupFiles@@YAJPEAUHWND__@@PEBG11K@Z`
- size: `985`
- prototype: `__int64 __fastcall(HWND hWnd, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x1800171b0`

## callees

- `0x180003180`
- `0x18000521c`
- `0x180008a6c`
- `0x1800152d8`
- `0x1800156b8`
- `0x180015c74`
- `0x180016094`
- `0x18001614c`
- `0x180016ad0`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `USER32!DestroyWindow` at `0x18001558f`
- `USER32!DestroyWindow` at `0x18001558f`
- `USER32!UpdateWindow` at `0x1800153fd`
- `USER32!UpdateWindow` at `0x180015601`
- `USER32!UpdateWindow` at `0x1800153fd`
- `USER32!UpdateWindow` at `0x180015601`
- `USER32!ShowWindow` at `0x1800153ce`
- `USER32!ShowWindow` at `0x1800153ce`
- `USER32!GetDlgItem` at `0x180015414`
- `USER32!GetDlgItem` at `0x180015436`
- `USER32!GetDlgItem` at `0x18001560f`
- `USER32!GetDlgItem` at `0x180015414`
- `USER32!GetDlgItem` at `0x180015436`
- `USER32!GetDlgItem` at `0x18001560f`
- `USER32!SendMessageW` at `0x180015428`
- `USER32!SendMessageW` at `0x18001544b`
- `USER32!SendMessageW` at `0x180015623`
- `USER32!SendMessageW` at `0x180015428`
- `USER32!SendMessageW` at `0x18001544b`
- `USER32!SendMessageW` at `0x180015623`
- `USER32!CreateDialogParamW` at `0x1800153bf`
- `USER32!CreateDialogParamW` at `0x1800153bf`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001557d`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800155f3`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001557d`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800155f3`
- `KERNEL32!CloseHandle` at `0x18001556b`
- `KERNEL32!CloseHandle` at `0x18001556b`
- `KERNEL32!GetFileAttributesW` at `0x1800154ed`
- `KERNEL32!GetFileAttributesW` at `0x1800154ed`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001548b`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001548b`

## pseudocode

```c
__int64 __fastcall BackupFiles(
        HWND hWnd,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5)
{
  const unsigned __int16 *v5; // rbx
  unsigned int v9; // edi
  HWND DialogParamW; // r14
  unsigned __int16 v11; // bx
  const unsigned __int16 *i; // rdx
  __int64 v13; // rcx
  HWND DlgItem; // rax
  HWND v15; // rax
  const unsigned __int16 **v16; // rdx
  int v17; // r8d
  int v18; // r9d
  DWORD FileAttributesW; // eax
  WCHAR *v20; // r8
  HWND v21; // rax
  __int64 v22; // rax
  int v23; // eax
  int v24; // r8d
  _OWORD v28[3]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[522]; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 v31[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR ReturnedString[1024]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v5 = a4;
  v9 = 0;
  memset_0(&hObject, 0, 0x420u);
  memset(v28, 0, sizeof(v28));
  if ( !a2 || !*a2 )
    goto LABEL_38;
  if ( (int)CreateFullPath(a3, 1) >= 0 && UninstallInfoInit((struct _BAKDATA *)&hObject, a3, v5, 1) )
  {
    DialogParamW = 0;
    if ( (a5 & 0x10) == 0 )
    {
      v11 = 0;
      DialogParamW = CreateDialogParamW(g_hinstMUI, (LPCWSTR)0x48A, hWnd, SaveRestoreProgressDlgProc, 1);
      ShowWindow(DialogParamW, 1);
      for ( i = a2; *i; i += v13 + 1 )
      {
        ++v11;
        v13 = -1;
        do
          ++v13;
        while ( i[v13] );
      }
      UpdateWindow(DialogParamW);
      DlgItem = GetDlgItem(DialogParamW, 1163);
      SendMessageW(DlgItem, 0x401u, 0, v11 << 16);
      v15 = GetDlgItem(DialogParamW, 1163);
      SendMessageW(v15, 0x404u, 1u, 0);
      v5 = a4;
    }
    while ( 1 )
    {
      if ( !*a2 )
      {
LABEL_21:
        if ( hObject != (HANDLE)-1LL )
          CloseHandle(hObject);
        WritePrivateProfileStringW(0, 0, 0, FileName);
        if ( DialogParamW )
          DestroyWindow(DialogParamW);
        goto LABEL_38;
      }
      if ( GetPrivateProfileStringW(L"backup", a2, &word_18001DE6C, ReturnedString, 0x400u, FileName) )
      {
        *((_QWORD *)&v28[0] + 1) = 0xFFFFFFFF00000001uLL;
        if ( GetFieldString(ReturnedString, 0, v31, 260) )
        {
          HIDWORD(v28[0]) = Mystrtoxl(v31, v16, v17, v18);
          if ( HIDWORD(v28[0]) != -1 )
            break;
        }
        if ( (a5 & 2) == 0 )
          break;
      }
      FileAttributesW = GetFileAttributesW(a2);
      DWORD2(v28[0]) = 0;
      HIDWORD(v28[0]) = FileAttributesW;
      if ( FileAttributesW == -1 )
      {
        v20 = L"-1,0,0,0,0,0,-1";
LABEL_28:
        WritePrivateProfileStringW(L"backup", a2, v20, FileName);
        goto LABEL_29;
      }
      *(_QWORD *)&v28[0] = a2;
      if ( !BackupSingleFile((struct _FILELIST *)v28, (struct _BAKDATA *)&hObject)
        && (a5 & 8) == 0
        && (unsigned int)MsgBox2Param(hWnd, 0x483u, a2, 0, 0x30u, 4u) == 7 )
      {
        v9 = -2147467259;
        goto LABEL_21;
      }
LABEL_29:
      if ( (a5 & 0x10) == 0 )
      {
        UpdateWindow(DialogParamW);
        v21 = GetDlgItem(DialogParamW, 1163);
        SendMessageW(v21, 0x405u, 0, 0);
      }
      v22 = -1;
      do
        ++v22;
      while ( a2[v22] );
      a2 += v22 + 1;
    }
    if ( GetFieldString(ReturnedString, 6, v31, 260) )
      goto LABEL_29;
    StringCchCatW(ReturnedString, 0x400u, L",-1");
    v20 = ReturnedString;
    goto LABEL_28;
  }
  if ( (a5 & 8) == 0 )
  {
    v23 = MsgBox2Param(hWnd, 0x484u, 0, 0, 0x30u, 4u);
    v24 = 0;
    if ( v23 == 7 )
      v24 = -2147467259;
    v9 = v24;
  }
LABEL_38:
  MySetUninstallFileAttrib(a3, v5);
  return v9;
}

```

## disassembly

```asm
0x1800152d8  push    rbp
0x1800152da  push    rbx
0x1800152db  push    rsi
0x1800152dc  push    rdi
0x1800152dd  push    r12
0x1800152df  push    r14
0x1800152e1  push    r15
0x1800152e3  lea     rbp, [rsp-0DB0h]
0x1800152eb  sub     rsp, 0EB0h
0x1800152f2  mov     rax, cs:__security_cookie
0x1800152f9  xor     rax, rsp
0x1800152fc  mov     [rbp+0DE0h+var_40], rax
0x180015303  mov     rbx, r9
0x180015306  mov     [rsp+0EE0h+hWndParent], rcx
0x18001530b  mov     r15, r8
0x18001530e  mov     [rsp+0EE0h+var_EA8], rbx
0x180015313  mov     rsi, rdx
0x180015316  mov     r14, rcx
0x180015319  xor     r12d, r12d
0x18001531c  lea     rcx, [rsp+0EE0h+hObject]; void *
0x180015321  xor     edx, edx; Val
0x180015323  mov     r8d, 420h; Size
0x180015329  mov     edi, r12d
0x18001532c  call    memset_0
0x180015331  xorps   xmm0, xmm0
0x180015334  movups  [rsp+0EE0h+var_EA0], xmm0
0x180015339  movups  [rsp+0EE0h+var_E90], xmm0
0x18001533e  movups  [rsp+0EE0h+var_E80], xmm0
0x180015343  test    rsi, rsi
0x180015346  jz      loc_180015683
0x18001534c  cmp     [rsi], r12w
0x180015350  jz      loc_180015683
0x180015356  lea     edx, [r12+1]; int
0x18001535b  mov     rcx, r15; unsigned __int16 *
0x18001535e  call    ?CreateFullPath@@YAJPEBGH@Z; CreateFullPath(ushort const *,int)
0x180015363  test    eax, eax
0x180015365  js      loc_180015645
0x18001536b  lea     r9d, [r12+1]; int
0x180015370  mov     r8, rbx; unsigned __int16 *
0x180015373  mov     rdx, r15; unsigned __int16 *
0x180015376  lea     rcx, [rsp+0EE0h+hObject]; struct _BAKDATA *
0x18001537b  call    ?UninstallInfoInit@@YAHPEAU_BAKDATA@@PEBG1H@Z; UninstallInfoInit(_BAKDATA *,ushort const *,ushort const *,int)
0x180015380  test    eax, eax
0x180015382  jz      loc_180015645
0x180015388  mov     r14d, r12d
0x18001538b  mov     r12d, [rbp+0DE0h+arg_20]
0x180015392  and     r12d, 10h
0x180015396  jnz     loc_180015456
0x18001539c  mov     r8, [rsp+0EE0h+hWndParent]; hWndParent
0x1800153a1  lea     r9, ?SaveRestoreProgressDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800153a8  mov     rcx, cs:g_hinstMUI; hInstance
0x1800153af  mov     edx, 48Ah; lpTemplateName
0x1800153b4  xor     ebx, ebx
0x1800153b6  mov     [rsp+0EE0h+dwInitParam], 1; dwInitParam
0x1800153bf  call    cs:__imp_CreateDialogParamW
0x1800153c5  mov     rcx, rax; hWnd
0x1800153c8  lea     edx, [rbx+1]; nCmdShow
0x1800153cb  mov     r14, rax
0x1800153ce  call    cs:__imp_ShowWindow
0x1800153d4  xor     eax, eax
0x1800153d6  mov     rdx, rsi
0x1800153d9  cmp     [rsi], ax
0x1800153dc  jz      short loc_1800153FA
0x1800153de  inc     ebx
0x1800153e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800153e4  inc     rcx
0x1800153e7  cmp     [rdx+rcx*2], ax
0x1800153eb  jnz     short loc_1800153E4
0x1800153ed  lea     rdx, [rdx+rcx*2]
0x1800153f1  add     rdx, 2
0x1800153f5  cmp     [rdx], ax
0x1800153f8  jnz     short loc_1800153DE
0x1800153fa  mov     rcx, r14; hWnd
0x1800153fd  call    cs:__imp_UpdateWindow
0x180015403  movzx   eax, bx
0x180015406  mov     edx, 48Bh; nIDDlgItem
0x18001540b  shl     eax, 10h
0x18001540e  mov     rcx, r14; hDlg
0x180015411  movsxd  rbx, eax
0x180015414  call    cs:__imp_GetDlgItem
0x18001541a  mov     r9, rbx; lParam
0x18001541d  xor     r8d, r8d; wParam
0x180015420  mov     rcx, rax; hWnd
0x180015423  mov     edx, 401h; Msg
0x180015428  call    cs:__imp_SendMessageW
0x18001542e  mov     edx, 48Bh; nIDDlgItem
0x180015433  mov     rcx, r14; hDlg
0x180015436  call    cs:__imp_GetDlgItem
0x18001543c  xor     r9d, r9d; lParam
0x18001543f  mov     edx, 404h; Msg
0x180015444  mov     rcx, rax; hWnd
0x180015447  lea     r8d, [r9+1]; wParam
0x18001544b  call    cs:__imp_SendMessageW
0x180015451  mov     rbx, [rsp+0EE0h+var_EA8]
0x180015456  xor     eax, eax
0x180015458  cmp     [rsi], ax
0x18001545b  jz      loc_180015560
0x180015461  lea     rax, [rsp+0EE0h+FileName]
0x180015466  mov     rdx, rsi; lpKeyName
0x180015469  mov     [rsp+0EE0h+lpFileName], rax; lpFileName
0x18001546e  lea     r9, [rbp+0DE0h+ReturnedString]; lpReturnedString
0x180015475  lea     r8, word_18001DE6C; lpDefault
0x18001547c  mov     dword ptr [rsp+0EE0h+dwInitParam], 400h; nSize
0x180015484  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x18001548b  call    cs:__imp_GetPrivateProfileStringW
0x180015491  test    eax, eax
0x180015493  jz      short loc_1800154EA
0x180015495  mov     r9d, 104h; int
0x18001549b  mov     dword ptr [rsp+0EE0h+var_EA0+8], 1
0x1800154a3  lea     r8, [rbp+0DE0h+var_A50]; unsigned __int16 *
0x1800154aa  mov     dword ptr [rsp+0EE0h+var_EA0+0Ch], 0FFFFFFFFh
0x1800154b2  xor     edx, edx; int
0x1800154b4  lea     rcx, [rbp+0DE0h+ReturnedString]; unsigned __int16 *
0x1800154bb  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x1800154c0  test    eax, eax
0x1800154c2  jz      short loc_1800154DD
0x1800154c4  lea     rcx, [rbp+0DE0h+var_A50]; unsigned __int16 *
0x1800154cb  call    ?Mystrtoxl@@YAKPEBGPEAPEBGHH@Z; Mystrtoxl(ushort const *,ushort const * *,int,int)
0x1800154d0  mov     dword ptr [rsp+0EE0h+var_EA0+0Ch], eax
0x1800154d4  cmp     eax, 0FFFFFFFFh
0x1800154d7  jnz     loc_1800155A3
0x1800154dd  test    byte ptr [rbp+0DE0h+arg_20], 2
0x1800154e4  jz      loc_1800155A3
0x1800154ea  mov     rcx, rsi; lpFileName
0x1800154ed  call    cs:__imp_GetFileAttributesW
0x1800154f3  mov     dword ptr [rsp+0EE0h+var_EA0+8], edi
0x1800154f7  mov     dword ptr [rsp+0EE0h+var_EA0+0Ch], eax
0x1800154fb  cmp     eax, 0FFFFFFFFh
0x1800154fe  jz      loc_18001559A
0x180015504  lea     rdx, [rsp+0EE0h+hObject]; struct _BAKDATA *
0x180015509  mov     qword ptr [rsp+0EE0h+var_EA0], rsi
0x18001550e  lea     rcx, [rsp+0EE0h+var_EA0]; struct _FILELIST *
0x180015513  call    ?BackupSingleFile@@YAHPEAU_FILELIST@@PEAU_BAKDATA@@@Z; BackupSingleFile(_FILELIST *,_BAKDATA *)
0x180015518  test    eax, eax
0x18001551a  jnz     loc_1800155F9
0x180015520  test    byte ptr [rbp+0DE0h+arg_20], 8
0x180015527  jnz     loc_1800155F9
0x18001552d  mov     rcx, [rsp+0EE0h+hWndParent]; hWnd
0x180015532  xor     r9d, r9d; unsigned __int16 *
0x180015535  mov     dword ptr [rsp+0EE0h+lpFileName], 4; unsigned int
0x18001553d  mov     r8, rsi; unsigned __int16 *
0x180015540  mov     edx, 483h; uID
0x180015545  mov     dword ptr [rsp+0EE0h+dwInitParam], 30h ; '0'; unsigned int
0x18001554d  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180015552  cmp     eax, 7
0x180015555  jnz     loc_1800155F9
0x18001555b  mov     edi, 80004005h
0x180015560  mov     rcx, [rsp+0EE0h+hObject]; hObject
0x180015565  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015569  jz      short loc_180015571
0x18001556b  call    cs:__imp_CloseHandle
0x180015571  lea     r9, [rsp+0EE0h+FileName]; lpFileName
0x180015576  xor     r8d, r8d; lpString
0x180015579  xor     edx, edx; lpKeyName
0x18001557b  xor     ecx, ecx; lpAppName
0x18001557d  call    cs:__imp_WritePrivateProfileStringW
0x180015583  test    r14, r14
0x180015586  jz      loc_180015683
0x18001558c  mov     rcx, r14; hWnd
0x18001558f  call    cs:__imp_DestroyWindow
0x180015595  jmp     loc_180015683
0x18001559a  lea     r8, a1000001; "-1,0,0,0,0,0,-1"
0x1800155a1  jmp     short loc_1800155E4
0x1800155a3  mov     r9d, 104h; int
0x1800155a9  lea     r8, [rbp+0DE0h+var_A50]; unsigned __int16 *
0x1800155b0  mov     edx, 6; int
0x1800155b5  lea     rcx, [rbp+0DE0h+ReturnedString]; unsigned __int16 *
0x1800155bc  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x1800155c1  test    eax, eax
0x1800155c3  jnz     short loc_1800155F9
0x1800155c5  lea     r8, a1_2; ",-1"
0x1800155cc  mov     edx, 400h; unsigned __int64
0x1800155d1  lea     rcx, [rbp+0DE0h+ReturnedString]; unsigned __int16 *
0x1800155d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800155dd  lea     r8, [rbp+0DE0h+ReturnedString]; lpString
0x1800155e4  lea     r9, [rsp+0EE0h+FileName]; lpFileName
0x1800155e9  mov     rdx, rsi; lpKeyName
0x1800155ec  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x1800155f3  call    cs:__imp_WritePrivateProfileStringW
0x1800155f9  test    r12d, r12d
0x1800155fc  jnz     short loc_180015629
0x1800155fe  mov     rcx, r14; hWnd
0x180015601  call    cs:__imp_UpdateWindow
0x180015607  mov     edx, 48Bh; nIDDlgItem
0x18001560c  mov     rcx, r14; hDlg
0x18001560f  call    cs:__imp_GetDlgItem
0x180015615  xor     r9d, r9d; lParam
0x180015618  xor     r8d, r8d; wParam
0x18001561b  mov     rcx, rax; hWnd
0x18001561e  mov     edx, 405h; Msg
0x180015623  call    cs:__imp_SendMessageW
0x180015629  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001562d  xor     ecx, ecx
0x18001562f  inc     rax
0x180015632  cmp     [rsi+rax*2], cx
0x180015636  jnz     short loc_18001562F
0x180015638  lea     rsi, [rsi+rax*2]
0x18001563c  add     rsi, 2
0x180015640  jmp     loc_180015456
0x180015645  test    byte ptr [rbp+0DE0h+arg_20], 8
0x18001564c  jnz     short loc_180015683
0x18001564e  mov     dword ptr [rsp+0EE0h+lpFileName], 4; unsigned int
0x180015656  xor     r9d, r9d; unsigned __int16 *
0x180015659  xor     r8d, r8d; unsigned __int16 *
0x18001565c  mov     dword ptr [rsp+0EE0h+dwInitParam], 30h ; '0'; unsigned int
0x180015664  mov     edx, 484h; uID
0x180015669  mov     rcx, r14; hWnd
0x18001566c  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180015671  mov     edi, 80004005h
0x180015676  cmp     eax, 7
0x180015679  mov     r8d, r12d
0x18001567c  cmovz   r8d, edi
0x180015680  mov     edi, r8d
0x180015683  mov     rdx, rbx; unsigned __int16 *
0x180015686  mov     rcx, r15; unsigned __int16 *
0x180015689  call    ?MySetUninstallFileAttrib@@YAXPEBG0@Z; MySetUninstallFileAttrib(ushort const *,ushort const *)
0x18001568e  mov     eax, edi
0x180015690  mov     rcx, [rbp+0DE0h+var_40]
0x180015697  xor     rcx, rsp; StackCookie
0x18001569a  call    __security_check_cookie
0x18001569f  add     rsp, 0EB0h
0x1800156a6  pop     r15
0x1800156a8  pop     r14
0x1800156aa  pop     r12
0x1800156ac  pop     rdi
0x1800156ad  pop     rsi
0x1800156ae  pop     rbx
0x1800156af  pop     rbp
0x1800156b0  retn
```
