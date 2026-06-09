# bNewFontDir(HWND__ *,tagSFINFO *)

- ea: `0x180125a84`
- end: `0x180125f8e`
- name: `?bNewFontDir@@YAHPEAUHWND__@@PEAUtagSFINFO@@@Z`
- size: `1290`
- prototype: `__int64 __fastcall(HWND hWnd, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180126ba0`

## callees

- `0x180003400`
- `0x180004558`
- `0x18000be68`
- `0x18010b1e4`
- `0x180122628`
- `0x180125a84`
- `0x180129fac`
- `0x180150854`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x180125ca3`
- `KERNEL32!CreateFileMappingW` at `0x180125ca3`
- `KERNEL32!MapViewOfFile` at `0x180125ccd`
- `KERNEL32!MapViewOfFile` at `0x180125ccd`
- `KERNEL32!HeapAlloc` at `0x180125d48`
- `KERNEL32!HeapAlloc` at `0x180125d48`
- `KERNEL32!CreateFileW` at `0x180125c74`
- `KERNEL32!CreateFileW` at `0x180125c74`
- `KERNEL32!CloseHandle` at `0x180125cdf`
- `KERNEL32!CloseHandle` at `0x180125eb0`
- `KERNEL32!CloseHandle` at `0x180125cdf`
- `KERNEL32!CloseHandle` at `0x180125eb0`
- `KERNEL32!GetLastError` at `0x180125bab`
- `KERNEL32!GetLastError` at `0x180125bab`
- `KERNEL32!FindFirstFileW` at `0x180125b88`
- `KERNEL32!FindFirstFileW` at `0x180125b88`
- `KERNEL32!FindNextFileW` at `0x180125ec8`
- `KERNEL32!FindNextFileW` at `0x180125ec8`
- `KERNEL32!FindClose` at `0x180125f2a`
- `KERNEL32!FindClose` at `0x180125f2a`
- `USER32!EnableWindow` at `0x180125d85`
- `USER32!EnableWindow` at `0x180125d85`
- `USER32!SendMessageW` at `0x180125c04`
- `USER32!SendMessageW` at `0x180125ef5`
- `USER32!SendMessageW` at `0x180125c04`
- `USER32!SendMessageW` at `0x180125ef5`
- `USER32!GetDlgItem` at `0x180125d72`
- `USER32!GetDlgItem` at `0x180125d72`
- `USER32!SendDlgItemMessageW` at `0x180125e7e`
- `USER32!SendDlgItemMessageW` at `0x180125e9b`
- `USER32!SendDlgItemMessageW` at `0x180125e7e`
- `USER32!SendDlgItemMessageW` at `0x180125e9b`
- `USER32!GetDlgItemTextW` at `0x180125ae0`
- `USER32!GetDlgItemTextW` at `0x180125ae0`
- `USER32!SetCursor` at `0x180125be6`
- `USER32!SetCursor` at `0x180125f1b`
- `USER32!SetCursor` at `0x180125be6`
- `USER32!SetCursor` at `0x180125f1b`
- `USER32!LoadCursorW` at `0x180125bd7`
- `USER32!LoadCursorW` at `0x180125bd7`
- `USER32!InvalidateRect` at `0x180125f0a`
- `USER32!InvalidateRect` at `0x180125f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180125b99`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180125d02`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180125d02`

## pseudocode

```c
__int64 __fastcall bNewFontDir(HWND hWnd, void **a2)
{
  signed int DlgItemTextW; // eax
  signed int v5; // esi
  UINT v6; // r9d
  void *hTemplateFile; // r15
  UINT v9; // ebx
  HANDLE FirstFileW; // r12
  HCURSOR CursorW; // rax
  unsigned __int64 v12; // r13
  size_t v13; // rbx
  wchar_t *v14; // rsi
  HANDLE FileW; // rax
  void *v16; // rsi
  HANDLE FileMappingW; // rax
  void *v18; // rbx
  DWORD v19; // eax
  int v20; // ebx
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  HWND DlgItem; // rax
  _QWORD *v24; // rax
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm2
  __int64 v28; // rax
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  unsigned __int64 v34; // rdx
  WCHAR *v35; // r9
  __int64 v36; // r8
  _WORD *v37; // rax
  _WORD *v38; // rdx
  WPARAM v39; // rax
  UINT v40; // r9d
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+40h] [rbp-C0h]
  size_t v43; // [rsp+48h] [rbp-B8h]
  HCURSOR hCursor; // [rsp+50h] [rbp-B0h]
  _OWORD v45[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-20h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR String[264]; // [rsp+340h] [rbp+240h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  DlgItemTextW = GetDlgItemTextW(hWnd, 304, String, 260);
  v5 = DlgItemTextW;
  if ( (unsigned int)DlgItemTextW >= 0xFF )
  {
    v6 = 510;
    goto LABEL_3;
  }
  hTemplateFile = 0;
  if ( DlgItemTextW <= 0 )
  {
    v40 = 514;
    goto LABEL_37;
  }
  if ( FindFileData.cAlternateFileName[DlgItemTextW + 13] != 92 )
  {
    StringCchCatW(String, 260, L"\\");
    ++v5;
  }
  StringCchCatW(String, 260, L"*.*");
  v9 = SetErrorMode(0);
  SetErrorMode(v9 & 0xFFFF7FFF);
  FirstFileW = FindFirstFileW(String, &FindFileData);
  SetErrorMode(v9);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() != 3 )
      return 0;
    v6 = 512;
LABEL_3:
    UniDrvUI::IDisplayErrorMessageBox(hWnd, (HWND)0x10, 0x1FFu, v6, dwCreationDisposition);
    return 0;
  }
  v42 = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  hCursor = SetCursor(CursorW);
  SendMessageW(hWnd, 0xBu, 0, 0);
  v12 = v5;
  v13 = 260LL - v5;
  v43 = v13;
  v14 = &String[v5];
  do
  {
    memset_0(v45, 0, 0x88u);
    StringCchCopyW(v14, v13, FindFileData.cFileName);
    FileW = CreateFileW(String, 0x80000000, 1u, 0, 3u, 0x100080u, hTemplateFile);
    v16 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, (DWORD)hTemplateFile, (LPCWSTR)hTemplateFile);
      v18 = FileMappingW;
      if ( FileMappingW
        && (hTemplateFile = MapViewOfFile(FileMappingW, 4u, 0, 0, (SIZE_T)hTemplateFile), CloseHandle(v18),
                                                                                          hTemplateFile) )
      {
        v19 = SetFilePointer(v16, 0, 0, 2u);
        v20 = bSFontToFIData((struct _IFIMETRICS **)v45, a2[2], (unsigned __int8 *)hTemplateFile, v19);
        UnmapFileFromMemory(hTemplateFile, v16);
        hTemplateFile = 0;
        if ( v20 )
        {
          v21 = HeapAlloc(a2[2], 8u, 0x2A8u);
          v22 = v21;
          if ( !v21 )
            break;
          if ( !a2[5] )
          {
            a2[5] = v21;
            DlgItem = GetDlgItem(hWnd, 302);
            EnableWindow(DlgItem, 1);
          }
          v24 = a2[6];
          if ( v24 )
            *v24 = v22;
          v25 = v45[0];
          v26 = v45[1];
          v27 = v45[5];
          v28 = v46;
          a2[6] = v22;
          *v22 = 0;
          v22[1] = 0;
          *((_DWORD *)v22 + 4) = 0;
          *(_OWORD *)(v22 + 3) = v25;
          v29 = v45[2];
          *(_OWORD *)(v22 + 5) = v26;
          v30 = v45[3];
          *(_OWORD *)(v22 + 7) = v29;
          v31 = v45[4];
          *(_OWORD *)(v22 + 9) = v30;
          v32 = v45[7];
          *(_OWORD *)(v22 + 11) = v31;
          v33 = v45[6];
          *(_OWORD *)(v22 + 13) = v27;
          *(_OWORD *)(v22 + 15) = v33;
          *(_OWORD *)(v22 + 17) = v32;
          v22[19] = v28;
          if ( v12 <= 0x7FFFFFFE )
          {
            v34 = v12;
            v35 = String;
            v36 = 260;
            v37 = v22 + 20;
            do
            {
              if ( !v34 )
                break;
              if ( !*v35 )
                break;
              *v37++ = *v35++;
              --v34;
              --v36;
            }
            while ( v36 );
            v38 = v37 - 1;
            if ( v36 )
              v38 = v37;
            *v38 = 0;
          }
          else
          {
            *((_WORD *)v22 + 80) = 0;
          }
          StringCchCatW((unsigned __int16 *)v22 + 80, 260, FindFileData.cFileName);
          v39 = SendDlgItemMessageW(hWnd, 305, 0x180u, 0, v27);
          SendDlgItemMessageW(hWnd, 305, 0x19Au, v39, (LPARAM)v22);
          ++v42;
        }
      }
      else
      {
        CloseHandle(v16);
      }
      v13 = v43;
    }
    v14 = &String[v12];
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  SendMessageW(hWnd, 0xBu, 1u, 0);
  InvalidateRect(hWnd, 0, 1);
  SetCursor(hCursor);
  FindClose(FirstFileW);
  if ( !v42 )
  {
    v40 = 513;
LABEL_37:
    UniDrvUI::IDisplayErrorMessageBox(hWnd, (HWND)0x10, 0x1FFu, v40, dwCreationDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x180125a84  mov     [rsp-8+arg_10], rbx
0x180125a89  push    rbp
0x180125a8a  push    rsi
0x180125a8b  push    rdi
0x180125a8c  push    r12
0x180125a8e  push    r13
0x180125a90  push    r14
0x180125a92  push    r15
0x180125a94  lea     rbp, [rsp-460h]
0x180125a9c  sub     rsp, 560h
0x180125aa3  mov     rax, cs:__security_cookie
0x180125aaa  xor     rax, rsp
0x180125aad  mov     [rbp+490h+var_40], rax
0x180125ab4  mov     r14, rdx
0x180125ab7  mov     rdi, rcx
0x180125aba  xor     edx, edx; Val
0x180125abc  lea     rcx, [rbp+490h+FindFileData]; void *
0x180125ac0  mov     r8d, 250h; Size
0x180125ac6  call    memset_0
0x180125acb  mov     ebx, 104h
0x180125ad0  lea     r8, [rbp+490h+String]; lpString
0x180125ad7  mov     r9d, ebx; cchMax
0x180125ada  mov     rcx, rdi; hDlg
0x180125add  lea     edx, [rbx+2Ch]; nIDDlgItem
0x180125ae0  call    cs:__imp_GetDlgItemTextW
0x180125ae7  nop     dword ptr [rax+rax+00h]
0x180125aec  movsxd  rsi, eax
0x180125aef  cmp     esi, 0FFh
0x180125af5  jb      short loc_180125B17
0x180125af7  mov     r9d, 1FEh; int
0x180125afd  mov     edx, 10h; uType
0x180125b02  mov     r8d, 1FFh; uID
0x180125b08  mov     rcx, rdi; hWnd
0x180125b0b  call    ?IDisplayErrorMessageBox@UniDrvUI@@YAHPEAUHWND__@@IHHZZ; UniDrvUI::IDisplayErrorMessageBox(HWND__ *,uint,int,int,...)
0x180125b10  xor     eax, eax
0x180125b12  jmp     loc_180125F63
0x180125b17  xor     r15d, r15d
0x180125b1a  test    eax, eax
0x180125b1c  jle     loc_180125F45
0x180125b22  cmp     [rbp+rsi*2+490h+FindFileData.cAlternateFileName+1Ah], 5Ch ; '\'
0x180125b2b  jz      short loc_180125B45
0x180125b2d  lea     r8, SubBlock; "\\"
0x180125b34  mov     rdx, rbx; unsigned __int64
0x180125b37  lea     rcx, [rbp+490h+String]; unsigned __int16 *
0x180125b3e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180125b43  inc     esi
0x180125b45  lea     r8, asc_18020E880; "*.*"
0x180125b4c  mov     rdx, rbx; unsigned __int64
0x180125b4f  lea     rcx, [rbp+490h+String]; unsigned __int16 *
0x180125b56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180125b5b  xor     ecx, ecx; uMode
0x180125b5d  call    cs:__imp_SetErrorMode
0x180125b64  nop     dword ptr [rax+rax+00h]
0x180125b69  mov     ecx, eax
0x180125b6b  mov     ebx, eax
0x180125b6d  btr     ecx, 0Fh; uMode
0x180125b71  call    cs:__imp_SetErrorMode
0x180125b78  nop     dword ptr [rax+rax+00h]
0x180125b7d  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x180125b81  lea     rcx, [rbp+490h+String]; lpFileName
0x180125b88  call    cs:__imp_FindFirstFileW
0x180125b8f  nop     dword ptr [rax+rax+00h]
0x180125b94  mov     ecx, ebx; uMode
0x180125b96  mov     r12, rax
0x180125b99  call    cs:__imp_SetErrorMode
0x180125ba0  nop     dword ptr [rax+rax+00h]
0x180125ba5  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180125ba9  jnz     short loc_180125BCB
0x180125bab  call    cs:__imp_GetLastError
0x180125bb2  nop     dword ptr [rax+rax+00h]
0x180125bb7  cmp     eax, 3
0x180125bba  jnz     loc_180125B10
0x180125bc0  mov     r9d, 200h
0x180125bc6  jmp     loc_180125AFD
0x180125bcb  mov     edx, 7F02h; lpCursorName
0x180125bd0  mov     [rsp+590h+var_550], r15d
0x180125bd5  xor     ecx, ecx; hInstance
0x180125bd7  call    cs:__imp_LoadCursorW
0x180125bde  nop     dword ptr [rax+rax+00h]
0x180125be3  mov     rcx, rax; hCursor
0x180125be6  call    cs:__imp_SetCursor
0x180125bed  nop     dword ptr [rax+rax+00h]
0x180125bf2  xor     r9d, r9d; lParam
0x180125bf5  xor     r8d, r8d; wParam
0x180125bf8  mov     rcx, rdi; hWnd
0x180125bfb  mov     [rsp+590h+hCursor], rax
0x180125c00  lea     edx, [r9+0Bh]; Msg
0x180125c04  call    cs:__imp_SendMessageW
0x180125c0b  nop     dword ptr [rax+rax+00h]
0x180125c10  movsxd  r13, esi
0x180125c13  mov     ebx, 104h
0x180125c18  sub     rbx, r13
0x180125c1b  lea     rsi, [rbp+490h+String]
0x180125c22  mov     [rsp+590h+var_548], rbx
0x180125c27  lea     rsi, [rsi+r13*2]
0x180125c2b  xor     edx, edx; Val
0x180125c2d  lea     rcx, [rsp+590h+var_530]; void *
0x180125c32  mov     r8d, 88h; Size
0x180125c38  call    memset_0
0x180125c3d  lea     r8, [rbp+490h+FindFileData.cFileName]; pszSrc
0x180125c41  mov     rdx, rbx; cchDest
0x180125c44  mov     rcx, rsi; pszDest
0x180125c47  call    StringCchCopyW
0x180125c4c  xor     r9d, r9d; lpSecurityAttributes
0x180125c4f  mov     [rsp+590h+hTemplateFile], r15; hTemplateFile
0x180125c54  mov     [rsp+590h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180125c5c  lea     rcx, [rbp+490h+String]; lpFileName
0x180125c63  mov     edx, 80000000h; dwDesiredAccess
0x180125c68  mov     [rsp+590h+dwCreationDisposition], 3; dwCreationDisposition
0x180125c70  lea     r8d, [r9+1]; dwShareMode
0x180125c74  call    cs:__imp_CreateFileW
0x180125c7b  nop     dword ptr [rax+rax+00h]
0x180125c80  mov     rsi, rax
0x180125c83  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180125c87  jz      loc_180125EC1
0x180125c8d  xor     r9d, r9d; dwMaximumSizeHigh
0x180125c90  mov     qword ptr [rsp+590h+dwFlagsAndAttributes], r15; lpName
0x180125c95  xor     edx, edx; lpFileMappingAttributes
0x180125c97  mov     [rsp+590h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x180125c9c  mov     rcx, rax; hFile
0x180125c9f  lea     r8d, [r9+2]; flProtect
0x180125ca3  call    cs:__imp_CreateFileMappingW
0x180125caa  nop     dword ptr [rax+rax+00h]
0x180125caf  mov     rbx, rax
0x180125cb2  test    rax, rax
0x180125cb5  jz      loc_180125EAD
0x180125cbb  xor     r9d, r9d; dwFileOffsetLow
0x180125cbe  mov     qword ptr [rsp+590h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x180125cc3  xor     r8d, r8d; dwFileOffsetHigh
0x180125cc6  mov     rcx, rax; hFileMappingObject
0x180125cc9  lea     edx, [r9+4]; dwDesiredAccess
0x180125ccd  call    cs:__imp_MapViewOfFile
0x180125cd4  nop     dword ptr [rax+rax+00h]
0x180125cd9  mov     rcx, rbx; hObject
0x180125cdc  mov     r15, rax
0x180125cdf  call    cs:__imp_CloseHandle
0x180125ce6  nop     dword ptr [rax+rax+00h]
0x180125ceb  test    r15, r15
0x180125cee  jz      loc_180125EAD
0x180125cf4  mov     r9d, 2; dwMoveMethod
0x180125cfa  xor     r8d, r8d; lpDistanceToMoveHigh
0x180125cfd  xor     edx, edx; lDistanceToMove
0x180125cff  mov     rcx, rsi; hFile
0x180125d02  call    cs:__imp_SetFilePointer
0x180125d09  nop     dword ptr [rax+rax+00h]
0x180125d0e  mov     rdx, [r14+10h]; void *
0x180125d12  lea     rcx, [rsp+590h+var_530]; struct _FI_DATA *
0x180125d17  mov     r9d, eax; unsigned int
0x180125d1a  mov     r8, r15; unsigned __int8 *
0x180125d1d  call    ?bSFontToFIData@@YAHPEAU_FI_DATA@@PEAXPEAEK@Z; bSFontToFIData(_FI_DATA *,void *,uchar *,ulong)
0x180125d22  mov     rdx, rsi
0x180125d25  mov     rcx, r15
0x180125d28  mov     ebx, eax
0x180125d2a  call    UnmapFileFromMemory
0x180125d2f  xor     r15d, r15d
0x180125d32  test    ebx, ebx
0x180125d34  jz      loc_180125EBC
0x180125d3a  mov     rcx, [r14+10h]; hHeap
0x180125d3e  lea     edx, [r15+8]; dwFlags
0x180125d42  mov     r8d, 2A8h; dwBytes
0x180125d48  call    cs:__imp_HeapAlloc
0x180125d4f  nop     dword ptr [rax+rax+00h]
0x180125d54  mov     rbx, rax
0x180125d57  test    rax, rax
0x180125d5a  jz      loc_180125EE7
0x180125d60  cmp     [r14+28h], r15
0x180125d64  jnz     short loc_180125D91
0x180125d66  mov     edx, 12Eh; nIDDlgItem
0x180125d6b  mov     [r14+28h], rax
0x180125d6f  mov     rcx, rdi; hDlg
0x180125d72  call    cs:__imp_GetDlgItem
0x180125d79  nop     dword ptr [rax+rax+00h]
0x180125d7e  mov     rcx, rax; hWnd
0x180125d81  lea     edx, [r15+1]; bEnable
0x180125d85  call    cs:__imp_EnableWindow
0x180125d8c  nop     dword ptr [rax+rax+00h]
0x180125d91  mov     rax, [r14+30h]
0x180125d95  test    rax, rax
0x180125d98  jz      short loc_180125D9D
0x180125d9a  mov     [rax], rbx
0x180125d9d  movaps  xmm0, [rsp+590h+var_530]
0x180125da2  lea     r10, [rbx+0A0h]
0x180125da9  movaps  xmm1, [rsp+590h+var_520]
0x180125dae  movaps  xmm2, [rbp+490h+var_4E0]
0x180125db2  mov     rax, [rbp+490h+var_4B0]
0x180125db6  mov     [r14+30h], rbx
0x180125dba  mov     [rbx], r15
0x180125dbd  mov     [rbx+8], r15
0x180125dc1  mov     [rbx+10h], r15d
0x180125dc5  movups  xmmword ptr [rbx+18h], xmm0
0x180125dc9  movaps  xmm0, [rbp+490h+var_510]
0x180125dcd  movups  xmmword ptr [rbx+28h], xmm1
0x180125dd1  movaps  xmm1, [rbp+490h+var_500]
0x180125dd5  movups  xmmword ptr [rbx+38h], xmm0
0x180125dd9  movaps  xmm0, [rbp+490h+var_4F0]
0x180125ddd  movups  xmmword ptr [rbx+48h], xmm1
0x180125de1  movaps  xmm1, [rbp+490h+var_4C0]
0x180125de5  movups  xmmword ptr [rbx+58h], xmm0
0x180125de9  movaps  xmm0, [rbp+490h+var_4D0]
0x180125ded  movups  xmmword ptr [rbx+68h], xmm2
0x180125df1  movups  xmmword ptr [rbx+78h], xmm0
0x180125df5  movups  xmmword ptr [rbx+88h], xmm1
0x180125dfc  mov     [rbx+98h], rax
0x180125e03  cmp     r13, 7FFFFFFEh
0x180125e0a  jbe     short loc_180125E12
0x180125e0c  mov     [r10], r15w
0x180125e10  jmp     short loc_180125E56
0x180125e12  mov     rdx, r13
0x180125e15  lea     r9, [rbp+490h+String]
0x180125e1c  mov     r8d, 104h
0x180125e22  mov     rax, r10
0x180125e25  test    rdx, rdx
0x180125e28  jz      short loc_180125E47
0x180125e2a  movzx   ecx, word ptr [r9]
0x180125e2e  test    cx, cx
0x180125e31  jz      short loc_180125E47
0x180125e33  mov     [rax], cx
0x180125e36  add     r9, 2
0x180125e3a  add     rax, 2
0x180125e3e  dec     rdx
0x180125e41  sub     r8, 1
0x180125e45  jnz     short loc_180125E25
0x180125e47  test    r8, r8
0x180125e4a  lea     rdx, [rax-2]
0x180125e4e  cmovnz  rdx, rax
0x180125e52  mov     [rdx], r15w
0x180125e56  lea     r8, [rbp+490h+FindFileData.cFileName]; unsigned __int16 *
0x180125e5a  mov     edx, 104h; unsigned __int64
0x180125e5f  mov     rcx, r10; unsigned __int16 *
0x180125e62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180125e67  mov     esi, 131h
0x180125e6c  movsd   qword ptr [rsp+590h+dwCreationDisposition], xmm2; lParam
0x180125e72  xor     r9d, r9d; wParam
0x180125e75  mov     edx, esi; nIDDlgItem
0x180125e77  mov     rcx, rdi; hDlg
0x180125e7a  lea     r8d, [rsi+4Fh]; Msg
0x180125e7e  call    cs:__imp_SendDlgItemMessageW
0x180125e85  nop     dword ptr [rax+rax+00h]
0x180125e8a  lea     r8d, [rsi+69h]; Msg
0x180125e8e  mov     qword ptr [rsp+590h+dwCreationDisposition], rbx; lParam
0x180125e93  mov     r9, rax; wParam
0x180125e96  mov     edx, esi; nIDDlgItem
0x180125e98  mov     rcx, rdi; hDlg
0x180125e9b  call    cs:__imp_SendDlgItemMessageW
0x180125ea2  nop     dword ptr [rax+rax+00h]
0x180125ea7  inc     [rsp+590h+var_550]
0x180125eab  jmp     short loc_180125EBC
0x180125ead  mov     rcx, rsi; hObject
0x180125eb0  call    cs:__imp_CloseHandle
0x180125eb7  nop     dword ptr [rax+rax+00h]
0x180125ebc  mov     rbx, [rsp+590h+var_548]
0x180125ec1  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x180125ec5  mov     rcx, r12; hFindFile
0x180125ec8  call    cs:__imp_FindNextFileW
0x180125ecf  nop     dword ptr [rax+rax+00h]
0x180125ed4  lea     rsi, [rbp+490h+String]
0x180125edb  lea     rsi, [rsi+r13*2]
0x180125edf  test    eax, eax
0x180125ee1  jnz     loc_180125C2B
0x180125ee7  xor     r9d, r9d; lParam
0x180125eea  mov     rcx, rdi; hWnd
0x180125eed  lea     edx, [r9+0Bh]; Msg
0x180125ef1  lea     r8d, [r9+1]; wParam
0x180125ef5  call    cs:__imp_SendMessageW
0x180125efc  nop     dword ptr [rax+rax+00h]
0x180125f01  xor     edx, edx; lpRect
0x180125f03  mov     rcx, rdi; hWnd
0x180125f06  lea     r8d, [rdx+1]; bErase
0x180125f0a  call    cs:__imp_InvalidateRect
0x180125f11  nop     dword ptr [rax+rax+00h]
0x180125f16  mov     rcx, [rsp+590h+hCursor]; hCursor
0x180125f1b  call    cs:__imp_SetCursor
0x180125f22  nop     dword ptr [rax+rax+00h]
0x180125f27  mov     rcx, r12; hFindFile
0x180125f2a  call    cs:__imp_FindClose
0x180125f31  nop     dword ptr [rax+rax+00h]
0x180125f36  cmp     [rsp+590h+var_550], 0
0x180125f3b  jnz     short loc_180125F5E
0x180125f3d  mov     r9d, 201h
0x180125f43  jmp     short loc_180125F4B
0x180125f45  mov     r9d, 202h; int
0x180125f4b  mov     r8d, 1FFh; uID
0x180125f51  mov     edx, 10h; uType
0x180125f56  mov     rcx, rdi; hWnd
0x180125f59  call    ?IDisplayErrorMessageBox@UniDrvUI@@YAHPEAUHWND__@@IHHZZ; UniDrvUI::IDisplayErrorMessageBox(HWND__ *,uint,int,int,...)
0x180125f5e  mov     eax, 1
0x180125f63  mov     rcx, [rbp+490h+var_40]
0x180125f6a  xor     rcx, rsp; StackCookie
0x180125f6d  call    __security_check_cookie
0x180125f72  mov     rbx, [rsp+590h+arg_10]
0x180125f7a  add     rsp, 560h
0x180125f81  pop     r15
0x180125f83  pop     r14
0x180125f85  pop     r13
0x180125f87  pop     r12
0x180125f89  pop     rdi
0x180125f8a  pop     rsi
0x180125f8b  pop     rbp
0x180125f8c  retn
```
