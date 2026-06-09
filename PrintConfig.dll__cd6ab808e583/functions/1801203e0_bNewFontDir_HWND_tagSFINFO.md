# bNewFontDir(HWND__ *,tagSFINFO *)

- ea: `0x1801203e0`
- end: `0x180120853`
- name: `?bNewFontDir@@YAHPEAUHWND__@@PEAUtagSFINFO@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(HWND hWnd, struct tagSFINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180121330`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18000be0c`
- `0x180106510`
- `0x18011d1b8`
- `0x1801203e0`
- `0x1801243c0`
- `0x180149ae8`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1801205c3`
- `KERNEL32!CreateFileMappingW` at `0x1801205c3`
- `KERNEL32!MapViewOfFile` at `0x1801205e7`
- `KERNEL32!MapViewOfFile` at `0x1801205e7`
- `KERNEL32!HeapAlloc` at `0x180120650`
- `KERNEL32!HeapAlloc` at `0x180120650`
- `KERNEL32!CreateFileW` at `0x18012059a`
- `KERNEL32!CreateFileW` at `0x18012059a`
- `KERNEL32!CloseHandle` at `0x1801205f3`
- `KERNEL32!CloseHandle` at `0x18012079a`
- `KERNEL32!CloseHandle` at `0x1801205f3`
- `KERNEL32!CloseHandle` at `0x18012079a`
- `KERNEL32!GetLastError` at `0x1801204e9`
- `KERNEL32!GetLastError` at `0x1801204e9`
- `KERNEL32!FindFirstFileW` at `0x1801204d2`
- `KERNEL32!FindFirstFileW` at `0x1801204d2`
- `KERNEL32!FindNextFileW` at `0x1801207ac`
- `KERNEL32!FindNextFileW` at `0x1801207ac`
- `KERNEL32!FindClose` at `0x1801207f6`
- `KERNEL32!FindClose` at `0x1801207f6`
- `USER32!EnableWindow` at `0x180120681`
- `USER32!EnableWindow` at `0x180120681`
- `USER32!SendMessageW` at `0x180120530`
- `USER32!SendMessageW` at `0x1801207d3`
- `USER32!SendMessageW` at `0x180120530`
- `USER32!SendMessageW` at `0x1801207d3`
- `USER32!GetDlgItem` at `0x180120674`
- `USER32!GetDlgItem` at `0x180120674`
- `USER32!SendDlgItemMessageW` at `0x180120774`
- `USER32!SendDlgItemMessageW` at `0x18012078b`
- `USER32!SendDlgItemMessageW` at `0x180120774`
- `USER32!SendDlgItemMessageW` at `0x18012078b`
- `USER32!GetDlgItemTextW` at `0x18012043c`
- `USER32!GetDlgItemTextW` at `0x18012043c`
- `USER32!SetCursor` at `0x180120518`
- `USER32!SetCursor` at `0x1801207ed`
- `USER32!SetCursor` at `0x180120518`
- `USER32!SetCursor` at `0x1801207ed`
- `USER32!LoadCursorW` at `0x18012050f`
- `USER32!LoadCursorW` at `0x18012050f`
- `USER32!InvalidateRect` at `0x1801207e2`
- `USER32!InvalidateRect` at `0x1801207e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1801204dd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180120610`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180120610`

## pseudocode

```c
__int64 __fastcall bNewFontDir(HWND hWnd, void **a2)
{
  signed int DlgItemTextW; // eax
  signed int v5; // esi
  int v6; // r9d
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
  LPVOID v21; // rax
  LPARAM v22; // rbx
  HWND DlgItem; // rax
  LPARAM *v24; // rax
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
  int v40; // r9d
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
    StringCchCatW(String, 0x104u, L"\\");
    ++v5;
  }
  StringCchCatW(String, 0x104u, L"*.*");
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
        v20 = bSFontToFIData((struct _FI_DATA *)v45, a2[2], (unsigned __int8 *)hTemplateFile, v19);
        UnmapFileFromMemory(hTemplateFile, v16);
        hTemplateFile = 0;
        if ( v20 )
        {
          v21 = HeapAlloc(a2[2], 8u, 0x2A8u);
          v22 = (LPARAM)v21;
          if ( !v21 )
            break;
          if ( !a2[5] )
          {
            a2[5] = v21;
            DlgItem = GetDlgItem(hWnd, 302);
            EnableWindow(DlgItem, 1);
          }
          v24 = (LPARAM *)a2[6];
          if ( v24 )
            *v24 = v22;
          v25 = v45[0];
          v26 = v45[1];
          v27 = v45[5];
          v28 = v46;
          a2[6] = (void *)v22;
          *(_QWORD *)v22 = 0;
          *(_QWORD *)(v22 + 8) = 0;
          *(_DWORD *)(v22 + 16) = 0;
          *(_OWORD *)(v22 + 24) = v25;
          v29 = v45[2];
          *(_OWORD *)(v22 + 40) = v26;
          v30 = v45[3];
          *(_OWORD *)(v22 + 56) = v29;
          v31 = v45[4];
          *(_OWORD *)(v22 + 72) = v30;
          v32 = v45[7];
          *(_OWORD *)(v22 + 88) = v31;
          v33 = v45[6];
          *(_OWORD *)(v22 + 104) = v27;
          *(_OWORD *)(v22 + 120) = v33;
          *(_OWORD *)(v22 + 136) = v32;
          *(_QWORD *)(v22 + 152) = v28;
          if ( v12 <= 0x7FFFFFFE )
          {
            v34 = v12;
            v35 = String;
            v36 = 260;
            v37 = (_WORD *)(v22 + 160);
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
            *(_WORD *)(v22 + 160) = 0;
          }
          StringCchCatW((unsigned __int16 *)(v22 + 160), 0x104u, FindFileData.cFileName);
          v39 = SendDlgItemMessageW(hWnd, 305, 0x180u, 0, v27);
          SendDlgItemMessageW(hWnd, 305, 0x19Au, v39, v22);
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
0x1801203e0  mov     [rsp-8+arg_10], rbx
0x1801203e5  push    rbp
0x1801203e6  push    rsi
0x1801203e7  push    rdi
0x1801203e8  push    r12
0x1801203ea  push    r13
0x1801203ec  push    r14
0x1801203ee  push    r15
0x1801203f0  lea     rbp, [rsp-460h]
0x1801203f8  sub     rsp, 560h
0x1801203ff  mov     rax, cs:__security_cookie
0x180120406  xor     rax, rsp
0x180120409  mov     [rbp+490h+var_40], rax
0x180120410  mov     r14, rdx
0x180120413  mov     rdi, rcx
0x180120416  xor     edx, edx; Val
0x180120418  lea     rcx, [rbp+490h+FindFileData]; void *
0x18012041c  mov     r8d, 250h; Size
0x180120422  call    memset_0
0x180120427  mov     ebx, 104h
0x18012042c  lea     r8, [rbp+490h+String]; lpString
0x180120433  mov     r9d, ebx; cchMax
0x180120436  mov     rcx, rdi; hDlg
0x180120439  lea     edx, [rbx+2Ch]; nIDDlgItem
0x18012043c  call    cs:__imp_GetDlgItemTextW
0x180120442  movsxd  rsi, eax
0x180120445  cmp     esi, 0FFh
0x18012044b  jb      short loc_18012046D
0x18012044d  mov     r9d, 1FEh; int
0x180120453  mov     edx, 10h; uType
0x180120458  mov     r8d, 1FFh; uID
0x18012045e  mov     rcx, rdi; hWnd
0x180120461  call    ?IDisplayErrorMessageBox@UniDrvUI@@YAHPEAUHWND__@@IHHZZ; UniDrvUI::IDisplayErrorMessageBox(HWND__ *,uint,int,int,...)
0x180120466  xor     eax, eax
0x180120468  jmp     loc_180120829
0x18012046d  xor     r15d, r15d
0x180120470  test    eax, eax
0x180120472  jle     loc_18012080B
0x180120478  cmp     [rbp+rsi*2+490h+FindFileData.cAlternateFileName+1Ah], 5Ch ; '\'
0x180120481  jz      short loc_18012049B
0x180120483  lea     r8, SubBlock; "\\"
0x18012048a  mov     rdx, rbx; unsigned __int64
0x18012048d  lea     rcx, [rbp+490h+String]; unsigned __int16 *
0x180120494  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180120499  inc     esi
0x18012049b  lea     r8, asc_180206A58; "*.*"
0x1801204a2  mov     rdx, rbx; unsigned __int64
0x1801204a5  lea     rcx, [rbp+490h+String]; unsigned __int16 *
0x1801204ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801204b1  xor     ecx, ecx; uMode
0x1801204b3  call    cs:__imp_SetErrorMode
0x1801204b9  mov     ecx, eax
0x1801204bb  mov     ebx, eax
0x1801204bd  btr     ecx, 0Fh; uMode
0x1801204c1  call    cs:__imp_SetErrorMode
0x1801204c7  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x1801204cb  lea     rcx, [rbp+490h+String]; lpFileName
0x1801204d2  call    cs:__imp_FindFirstFileW
0x1801204d8  mov     ecx, ebx; uMode
0x1801204da  mov     r12, rax
0x1801204dd  call    cs:__imp_SetErrorMode
0x1801204e3  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1801204e7  jnz     short loc_180120503
0x1801204e9  call    cs:__imp_GetLastError
0x1801204ef  cmp     eax, 3
0x1801204f2  jnz     loc_180120466
0x1801204f8  mov     r9d, 200h
0x1801204fe  jmp     loc_180120453
0x180120503  mov     edx, 7F02h; lpCursorName
0x180120508  mov     [rsp+590h+var_550], r15d
0x18012050d  xor     ecx, ecx; hInstance
0x18012050f  call    cs:__imp_LoadCursorW
0x180120515  mov     rcx, rax; hCursor
0x180120518  call    cs:__imp_SetCursor
0x18012051e  xor     r9d, r9d; lParam
0x180120521  xor     r8d, r8d; wParam
0x180120524  mov     rcx, rdi; hWnd
0x180120527  mov     [rsp+590h+hCursor], rax
0x18012052c  lea     edx, [r9+0Bh]; Msg
0x180120530  call    cs:__imp_SendMessageW
0x180120536  movsxd  r13, esi
0x180120539  mov     ebx, 104h
0x18012053e  sub     rbx, r13
0x180120541  lea     rsi, [rbp+490h+String]
0x180120548  mov     [rsp+590h+var_548], rbx
0x18012054d  lea     rsi, [rsi+r13*2]
0x180120551  xor     edx, edx; Val
0x180120553  lea     rcx, [rsp+590h+var_530]; void *
0x180120558  mov     r8d, 88h; Size
0x18012055e  call    memset_0
0x180120563  lea     r8, [rbp+490h+FindFileData.cFileName]; pszSrc
0x180120567  mov     rdx, rbx; cchDest
0x18012056a  mov     rcx, rsi; pszDest
0x18012056d  call    StringCchCopyW
0x180120572  xor     r9d, r9d; lpSecurityAttributes
0x180120575  mov     [rsp+590h+hTemplateFile], r15; hTemplateFile
0x18012057a  mov     [rsp+590h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180120582  lea     rcx, [rbp+490h+String]; lpFileName
0x180120589  mov     edx, 80000000h; dwDesiredAccess
0x18012058e  mov     [rsp+590h+dwCreationDisposition], 3; dwCreationDisposition
0x180120596  lea     r8d, [r9+1]; dwShareMode
0x18012059a  call    cs:__imp_CreateFileW
0x1801205a0  mov     rsi, rax
0x1801205a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801205a7  jz      loc_1801207A5
0x1801205ad  xor     r9d, r9d; dwMaximumSizeHigh
0x1801205b0  mov     qword ptr [rsp+590h+dwFlagsAndAttributes], r15; lpName
0x1801205b5  xor     edx, edx; lpFileMappingAttributes
0x1801205b7  mov     [rsp+590h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x1801205bc  mov     rcx, rax; hFile
0x1801205bf  lea     r8d, [r9+2]; flProtect
0x1801205c3  call    cs:__imp_CreateFileMappingW
0x1801205c9  mov     rbx, rax
0x1801205cc  test    rax, rax
0x1801205cf  jz      loc_180120797
0x1801205d5  xor     r9d, r9d; dwFileOffsetLow
0x1801205d8  mov     qword ptr [rsp+590h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x1801205dd  xor     r8d, r8d; dwFileOffsetHigh
0x1801205e0  mov     rcx, rax; hFileMappingObject
0x1801205e3  lea     edx, [r9+4]; dwDesiredAccess
0x1801205e7  call    cs:__imp_MapViewOfFile
0x1801205ed  mov     rcx, rbx; hObject
0x1801205f0  mov     r15, rax
0x1801205f3  call    cs:__imp_CloseHandle
0x1801205f9  test    r15, r15
0x1801205fc  jz      loc_180120797
0x180120602  mov     r9d, 2; dwMoveMethod
0x180120608  xor     r8d, r8d; lpDistanceToMoveHigh
0x18012060b  xor     edx, edx; lDistanceToMove
0x18012060d  mov     rcx, rsi; hFile
0x180120610  call    cs:__imp_SetFilePointer
0x180120616  mov     rdx, [r14+10h]; void *
0x18012061a  lea     rcx, [rsp+590h+var_530]; struct _FI_DATA *
0x18012061f  mov     r9d, eax; unsigned int
0x180120622  mov     r8, r15; unsigned __int8 *
0x180120625  call    ?bSFontToFIData@@YAHPEAU_FI_DATA@@PEAXPEAEK@Z; bSFontToFIData(_FI_DATA *,void *,uchar *,ulong)
0x18012062a  mov     rdx, rsi
0x18012062d  mov     rcx, r15
0x180120630  mov     ebx, eax
0x180120632  call    UnmapFileFromMemory
0x180120637  xor     r15d, r15d
0x18012063a  test    ebx, ebx
0x18012063c  jz      loc_1801207A0
0x180120642  mov     rcx, [r14+10h]; hHeap
0x180120646  lea     edx, [r15+8]; dwFlags
0x18012064a  mov     r8d, 2A8h; dwBytes
0x180120650  call    cs:__imp_HeapAlloc
0x180120656  mov     rbx, rax
0x180120659  test    rax, rax
0x18012065c  jz      loc_1801207C5
0x180120662  cmp     [r14+28h], r15
0x180120666  jnz     short loc_180120687
0x180120668  mov     edx, 12Eh; nIDDlgItem
0x18012066d  mov     [r14+28h], rax
0x180120671  mov     rcx, rdi; hDlg
0x180120674  call    cs:__imp_GetDlgItem
0x18012067a  mov     rcx, rax; hWnd
0x18012067d  lea     edx, [r15+1]; bEnable
0x180120681  call    cs:__imp_EnableWindow
0x180120687  mov     rax, [r14+30h]
0x18012068b  test    rax, rax
0x18012068e  jz      short loc_180120693
0x180120690  mov     [rax], rbx
0x180120693  movaps  xmm0, [rsp+590h+var_530]
0x180120698  lea     r10, [rbx+0A0h]
0x18012069f  movaps  xmm1, [rsp+590h+var_520]
0x1801206a4  movaps  xmm2, [rbp+490h+var_4E0]
0x1801206a8  mov     rax, [rbp+490h+var_4B0]
0x1801206ac  mov     [r14+30h], rbx
0x1801206b0  mov     [rbx], r15
0x1801206b3  mov     [rbx+8], r15
0x1801206b7  mov     [rbx+10h], r15d
0x1801206bb  movups  xmmword ptr [rbx+18h], xmm0
0x1801206bf  movaps  xmm0, [rbp+490h+var_510]
0x1801206c3  movups  xmmword ptr [rbx+28h], xmm1
0x1801206c7  movaps  xmm1, [rbp+490h+var_500]
0x1801206cb  movups  xmmword ptr [rbx+38h], xmm0
0x1801206cf  movaps  xmm0, [rbp+490h+var_4F0]
0x1801206d3  movups  xmmword ptr [rbx+48h], xmm1
0x1801206d7  movaps  xmm1, [rbp+490h+var_4C0]
0x1801206db  movups  xmmword ptr [rbx+58h], xmm0
0x1801206df  movaps  xmm0, [rbp+490h+var_4D0]
0x1801206e3  movups  xmmword ptr [rbx+68h], xmm2
0x1801206e7  movups  xmmword ptr [rbx+78h], xmm0
0x1801206eb  movups  xmmword ptr [rbx+88h], xmm1
0x1801206f2  mov     [rbx+98h], rax
0x1801206f9  cmp     r13, 7FFFFFFEh
0x180120700  jbe     short loc_180120708
0x180120702  mov     [r10], r15w
0x180120706  jmp     short loc_18012074C
0x180120708  mov     rdx, r13
0x18012070b  lea     r9, [rbp+490h+String]
0x180120712  mov     r8d, 104h
0x180120718  mov     rax, r10
0x18012071b  test    rdx, rdx
0x18012071e  jz      short loc_18012073D
0x180120720  movzx   ecx, word ptr [r9]
0x180120724  test    cx, cx
0x180120727  jz      short loc_18012073D
0x180120729  mov     [rax], cx
0x18012072c  add     r9, 2
0x180120730  add     rax, 2
0x180120734  dec     rdx
0x180120737  sub     r8, 1
0x18012073b  jnz     short loc_18012071B
0x18012073d  test    r8, r8
0x180120740  lea     rdx, [rax-2]
0x180120744  cmovnz  rdx, rax
0x180120748  mov     [rdx], r15w
0x18012074c  lea     r8, [rbp+490h+FindFileData.cFileName]; unsigned __int16 *
0x180120750  mov     edx, 104h; unsigned __int64
0x180120755  mov     rcx, r10; unsigned __int16 *
0x180120758  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012075d  mov     esi, 131h
0x180120762  movsd   qword ptr [rsp+590h+dwCreationDisposition], xmm2; lParam
0x180120768  xor     r9d, r9d; wParam
0x18012076b  mov     edx, esi; nIDDlgItem
0x18012076d  mov     rcx, rdi; hDlg
0x180120770  lea     r8d, [rsi+4Fh]; Msg
0x180120774  call    cs:__imp_SendDlgItemMessageW
0x18012077a  lea     r8d, [rsi+69h]; Msg
0x18012077e  mov     qword ptr [rsp+590h+dwCreationDisposition], rbx; lParam
0x180120783  mov     r9, rax; wParam
0x180120786  mov     edx, esi; nIDDlgItem
0x180120788  mov     rcx, rdi; hDlg
0x18012078b  call    cs:__imp_SendDlgItemMessageW
0x180120791  inc     [rsp+590h+var_550]
0x180120795  jmp     short loc_1801207A0
0x180120797  mov     rcx, rsi; hObject
0x18012079a  call    cs:__imp_CloseHandle
0x1801207a0  mov     rbx, [rsp+590h+var_548]
0x1801207a5  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x1801207a9  mov     rcx, r12; hFindFile
0x1801207ac  call    cs:__imp_FindNextFileW
0x1801207b2  lea     rsi, [rbp+490h+String]
0x1801207b9  lea     rsi, [rsi+r13*2]
0x1801207bd  test    eax, eax
0x1801207bf  jnz     loc_180120551
0x1801207c5  xor     r9d, r9d; lParam
0x1801207c8  mov     rcx, rdi; hWnd
0x1801207cb  lea     edx, [r9+0Bh]; Msg
0x1801207cf  lea     r8d, [r9+1]; wParam
0x1801207d3  call    cs:__imp_SendMessageW
0x1801207d9  xor     edx, edx; lpRect
0x1801207db  mov     rcx, rdi; hWnd
0x1801207de  lea     r8d, [rdx+1]; bErase
0x1801207e2  call    cs:__imp_InvalidateRect
0x1801207e8  mov     rcx, [rsp+590h+hCursor]; hCursor
0x1801207ed  call    cs:__imp_SetCursor
0x1801207f3  mov     rcx, r12; hFindFile
0x1801207f6  call    cs:__imp_FindClose
0x1801207fc  cmp     [rsp+590h+var_550], 0
0x180120801  jnz     short loc_180120824
0x180120803  mov     r9d, 201h
0x180120809  jmp     short loc_180120811
0x18012080b  mov     r9d, 202h; int
0x180120811  mov     r8d, 1FFh; uID
0x180120817  mov     edx, 10h; uType
0x18012081c  mov     rcx, rdi; hWnd
0x18012081f  call    ?IDisplayErrorMessageBox@UniDrvUI@@YAHPEAUHWND__@@IHHZZ; UniDrvUI::IDisplayErrorMessageBox(HWND__ *,uint,int,int,...)
0x180120824  mov     eax, 1
0x180120829  mov     rcx, [rbp+490h+var_40]
0x180120830  xor     rcx, rsp; StackCookie
0x180120833  call    __security_check_cookie
0x180120838  mov     rbx, [rsp+590h+arg_10]
0x180120840  add     rsp, 560h
0x180120847  pop     r15
0x180120849  pop     r14
0x18012084b  pop     r13
0x18012084d  pop     r12
0x18012084f  pop     rdi
0x180120850  pop     rsi
0x180120851  pop     rbp
0x180120852  retn
```
