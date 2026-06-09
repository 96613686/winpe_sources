# RemoveConfirmDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180007aa0`
- end: `0x180007bf7`
- name: `?RemoveConfirmDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `343`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180005eec`
- `0x180007558`
- `0x180007888`
- `0x180007aa0`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x180007b20`
- `USER32!GetWindowLongPtrW` at `0x180007b20`
- `USER32!EndDialog` at `0x180007b8c`
- `USER32!EndDialog` at `0x180007b8c`
- `USER32!SetWindowLongPtrW` at `0x180007acb`
- `USER32!SetWindowLongPtrW` at `0x180007bbe`
- `USER32!SetWindowLongPtrW` at `0x180007acb`
- `USER32!SetWindowLongPtrW` at `0x180007bbe`
- `USER32!GetSystemMetrics` at `0x180007ae6`
- `USER32!GetSystemMetrics` at `0x180007ae6`
- `USER32!LoadCursorW` at `0x180007ba7`
- `USER32!LoadCursorW` at `0x180007ba7`
- `USER32!SendMessageW` at `0x180007bd4`
- `USER32!SendMessageW` at `0x180007bd4`
- `USER32!GetDlgItem` at `0x180007b07`
- `USER32!GetDlgItem` at `0x180007b07`
- `USER32!SetCursor` at `0x180007bb0`
- `USER32!SetCursor` at `0x180007bb0`

## pseudocode

```c
INT_PTR __fastcall RemoveConfirmDlgProc(HWND a1, int a2, __int64 a3, struct _DeviceTreeData *a4)
{
  const unsigned __int16 *v8; // rcx
  HWND DlgItem; // rax
  LPARAM v10; // r9
  WPARAM v11; // r8
  HWND v12; // rcx
  UINT v13; // edx
  LONG_PTR WindowLongPtrW; // rax
  __int64 v16; // rbx
  __int64 v17; // rbx
  INT_PTR v18; // rdx
  HCURSOR CursorW; // rax

  if ( a2 == 272 )
  {
    SetWindowLongPtrW(a1, 16, (LONG_PTR)a4);
    if ( a4 )
      InitRemoveConfirmDlgProc(a1, a4);
    if ( !GetSystemMetrics(4096) || DoesUserHavePrivilege(v8) )
      return 1;
    DlgItem = GetDlgItem(a1, 1);
    v10 = 1;
    v11 = 0;
    v12 = DlgItem;
    v13 = 5644;
    goto LABEL_24;
  }
  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  if ( a2 == 2 )
  {
    if ( WindowLongPtrW )
      *(_QWORD *)(WindowLongPtrW + 24) = 0;
    return 1;
  }
  if ( a2 == 16 )
  {
    v10 = 0;
    v11 = 2;
    v13 = 273;
    v12 = a1;
LABEL_24:
    SendMessageW(v12, v13, v11, v10);
    return 1;
  }
  if ( a2 != 21 )
  {
    switch ( a2 )
    {
      case 32:
        if ( *(_BYTE *)(WindowLongPtrW + 99) || *(_BYTE *)(WindowLongPtrW + 100) )
        {
          CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
          SetCursor(CursorW);
          SetWindowLongPtrW(a1, 0, 1);
        }
        return 1;
      case 273:
        v16 = a3 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 && v17 != 6 )
            return 1;
          v18 = 2;
          goto LABEL_19;
        }
        break;
      case 1303:
        break;
      default:
        return 0;
    }
    v18 = 2 - OnOkRemove(a1, (struct _DeviceTreeData *)WindowLongPtrW);
LABEL_19:
    EndDialog(a1, v18);
  }
  return 1;
}

```

## disassembly

```asm
0x180007aa0  push    rbx
0x180007aa2  push    rbp
0x180007aa3  push    rsi
0x180007aa4  push    rdi
0x180007aa5  push    r14
0x180007aa7  sub     rsp, 20h
0x180007aab  mov     r14d, 1
0x180007ab1  mov     esi, edx
0x180007ab3  cmp     edx, 110h
0x180007ab9  mov     rbp, r9
0x180007abc  mov     rbx, r8
0x180007abf  mov     rdi, rcx
0x180007ac2  lea     edx, [r14+0Fh]; nIndex
0x180007ac6  jnz     short loc_180007B20
0x180007ac8  mov     r8, r9; dwNewLong
0x180007acb  call    cs:__imp_SetWindowLongPtrW
0x180007ad1  test    rbp, rbp
0x180007ad4  jz      short loc_180007AE1
0x180007ad6  mov     rdx, rbp; struct _DeviceTreeData *
0x180007ad9  mov     rcx, rdi; hDlg
0x180007adc  call    ?InitRemoveConfirmDlgProc@@YAHPEAUHWND__@@PEAU_DeviceTreeData@@@Z; InitRemoveConfirmDlgProc(HWND__ *,_DeviceTreeData *)
0x180007ae1  mov     ecx, 1000h; nIndex
0x180007ae6  call    cs:__imp_GetSystemMetrics
0x180007aec  test    eax, eax
0x180007aee  jz      loc_180007BE9
0x180007af4  call    ?DoesUserHavePrivilege@@YAHPEBG@Z; DoesUserHavePrivilege(ushort const *)
0x180007af9  test    eax, eax
0x180007afb  jnz     loc_180007BE9
0x180007b01  mov     edx, r14d; nIDDlgItem
0x180007b04  mov     rcx, rdi; hDlg
0x180007b07  call    cs:__imp_GetDlgItem
0x180007b0d  mov     r9, r14
0x180007b10  xor     r8d, r8d
0x180007b13  mov     rcx, rax; hWnd
0x180007b16  mov     edx, 160Ch
0x180007b1b  jmp     loc_180007BD4
0x180007b20  call    cs:__imp_GetWindowLongPtrW
0x180007b26  mov     ebp, 2
0x180007b2b  cmp     esi, ebp
0x180007b2d  jz      loc_180007BDC
0x180007b33  cmp     esi, 10h
0x180007b36  jz      loc_180007BC6
0x180007b3c  cmp     esi, 15h
0x180007b3f  jz      loc_180007BE9
0x180007b45  cmp     esi, 20h ; ' '
0x180007b48  jz      short loc_180007B94
0x180007b4a  cmp     esi, 111h
0x180007b50  jz      short loc_180007B61
0x180007b52  cmp     esi, 517h
0x180007b58  jz      short loc_180007B76
0x180007b5a  xor     eax, eax
0x180007b5c  jmp     loc_180007BEC
0x180007b61  sub     rbx, r14
0x180007b64  jz      short loc_180007B76
0x180007b66  sub     rbx, r14
0x180007b69  jz      short loc_180007B71
0x180007b6b  cmp     rbx, 6
0x180007b6f  jnz     short loc_180007BE9
0x180007b71  mov     rdx, rbp
0x180007b74  jmp     short loc_180007B89
0x180007b76  mov     rdx, rax; lpParameter
0x180007b79  mov     rcx, rdi; HWND
0x180007b7c  call    ?OnOkRemove@@YAHPEAUHWND__@@PEAU_DeviceTreeData@@@Z; OnOkRemove(HWND__ *,_DeviceTreeData *)
0x180007b81  neg     eax
0x180007b83  sbb     rdx, rdx
0x180007b86  add     rdx, rbp; nResult
0x180007b89  mov     rcx, rdi; hDlg
0x180007b8c  call    cs:__imp_EndDialog
0x180007b92  jmp     short loc_180007BE9
0x180007b94  cmp     byte ptr [rax+63h], 0
0x180007b98  jnz     short loc_180007BA0
0x180007b9a  cmp     byte ptr [rax+64h], 0
0x180007b9e  jz      short loc_180007BE9
0x180007ba0  mov     edx, 7F02h; lpCursorName
0x180007ba5  xor     ecx, ecx; hInstance
0x180007ba7  call    cs:__imp_LoadCursorW
0x180007bad  mov     rcx, rax; hCursor
0x180007bb0  call    cs:__imp_SetCursor
0x180007bb6  mov     r8, r14; dwNewLong
0x180007bb9  xor     edx, edx; nIndex
0x180007bbb  mov     rcx, rdi; hWnd
0x180007bbe  call    cs:__imp_SetWindowLongPtrW
0x180007bc4  jmp     short loc_180007BE9
0x180007bc6  xor     r9d, r9d; lParam
0x180007bc9  mov     r8, rbp; wParam
0x180007bcc  mov     edx, 111h; Msg
0x180007bd1  mov     rcx, rdi; hWnd
0x180007bd4  call    cs:__imp_SendMessageW
0x180007bda  jmp     short loc_180007BE9
0x180007bdc  test    rax, rax
0x180007bdf  jz      short loc_180007BE9
0x180007be1  mov     qword ptr [rax+18h], 0
0x180007be9  mov     rax, r14
0x180007bec  add     rsp, 20h
0x180007bf0  pop     r14
0x180007bf2  pop     rdi
0x180007bf3  pop     rsi
0x180007bf4  pop     rbp
0x180007bf5  pop     rbx
0x180007bf6  retn
```
