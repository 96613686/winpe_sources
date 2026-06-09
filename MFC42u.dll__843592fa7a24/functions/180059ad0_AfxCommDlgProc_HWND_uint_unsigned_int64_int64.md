# _AfxCommDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180059ad0`
- end: `0x180059cdc`
- name: `?_AfxCommDlgProc@@YA_KPEAUHWND__@@I_K_J@Z`
- size: `524`
- prototype: `unsigned __int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180011480`
- `0x180012d60`
- `0x18001a410`
- `0x18001cce0`
- `0x18001d860`
- `0x180059ad0`
- `0x1800d7010`

## import_xrefs

- `USER32!RegisterWindowMessageW` at `0x180059b33`
- `USER32!RegisterWindowMessageW` at `0x180059b46`
- `USER32!RegisterWindowMessageW` at `0x180059b59`
- `USER32!RegisterWindowMessageW` at `0x180059b6c`
- `USER32!RegisterWindowMessageW` at `0x180059b7f`
- `USER32!RegisterWindowMessageW` at `0x180059b92`
- `USER32!RegisterWindowMessageW` at `0x180059b33`
- `USER32!RegisterWindowMessageW` at `0x180059b46`
- `USER32!RegisterWindowMessageW` at `0x180059b59`
- `USER32!RegisterWindowMessageW` at `0x180059b6c`
- `USER32!RegisterWindowMessageW` at `0x180059b7f`
- `USER32!RegisterWindowMessageW` at `0x180059b92`
- `USER32!SendMessageW` at `0x180059ccf`
- `USER32!SendMessageW` at `0x180059ccf`

## string_xrefs

- `0x180059b2c`: `commdlg_LBSelChangedNotify`
- `0x180059b39`: `commdlg_ShareViolation`
- `0x180059b4c`: `commdlg_FileNameOK`
- `0x180059b5f`: `commdlg_ColorOK`
- `0x180059b72`: `commdlg_help`
- `0x180059b85`: `commdlg_SetRGBColor`

## pseudocode

```c
unsigned __int64 __fastcall _AfxCommDlgProc(HWND a1, __int64 a2, WPARAM a3, LPARAM a4)
{
  unsigned int v6; // edi
  __int64 Data; // rbp
  unsigned __int64 result; // rax
  struct CWnd *v10; // rbx

  v6 = a2;
  if ( !a1 )
    return 0;
  Data = CThreadLocal<_AFX_THREAD_STATE>::GetData(a1, a2);
  if ( *(_QWORD *)(Data + 48) && !CWnd::FromHandlePermanent(a1) )
  {
    CWnd::SubclassWindow(*(CWnd **)(Data + 48), a1);
    *(_QWORD *)(Data + 48) = 0;
  }
  if ( v6 == 272 )
  {
    _afxMsgLBSELCHANGE = RegisterWindowMessageW(L"commdlg_LBSelChangedNotify");
    _afxMsgSHAREVI = RegisterWindowMessageW(L"commdlg_ShareViolation");
    _afxMsgFILEOK = RegisterWindowMessageW(L"commdlg_FileNameOK");
    _afxMsgCOLOROK = RegisterWindowMessageW(L"commdlg_ColorOK");
    _afxMsgHELP = RegisterWindowMessageW(L"commdlg_help");
    _afxMsgSETRGB = RegisterWindowMessageW(L"commdlg_SetRGBColor");
    LODWORD(result) = AfxDlgProc(a1, 0x110u, a3, a4);
    return (unsigned int)result;
  }
  if ( v6 != _afxMsgHELP && (v6 != 273 || (_WORD)a3 != 1038) )
  {
    if ( v6 >= 0xC000 )
    {
      v10 = CWnd::FromHandlePermanent(a1);
      if ( !(unsigned int)CObject::IsKindOf(v10, (const struct CRuntimeClass *)&CFileDialog::classCFileDialog)
        || (*((_DWORD *)v10 + 72) & 0x80000) == 0 )
      {
        if ( v6 == _afxMsgSHAREVI )
        {
          LODWORD(result) = (*(__int64 (__fastcall **)(struct CWnd *, LPARAM))(*(_QWORD *)v10 + 432LL))(v10, a4);
          return (unsigned int)result;
        }
        if ( v6 == _afxMsgFILEOK )
        {
          if ( dword_180131A40 )
            *((_QWORD *)v10 + 124) = a4;
          LODWORD(result) = (*(__int64 (__fastcall **)(struct CWnd *))(*(_QWORD *)v10 + 440LL))(v10);
          *((_QWORD *)v10 + 124) = 0;
          return (int)result;
        }
        if ( v6 == _afxMsgLBSELCHANGE )
        {
          (*(void (__fastcall **)(struct CWnd *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 448LL))(
            v10,
            (unsigned int)a3,
            (unsigned __int16)a4,
            WORD1(a4));
        }
        else if ( v6 == _afxMsgCOLOROK )
        {
          LODWORD(result) = (*(__int64 (__fastcall **)(struct CWnd *))(*(_QWORD *)v10 + 432LL))(v10);
          return (int)result;
        }
      }
    }
    return 0;
  }
  SendMessageW(a1, 0x111u, 0xE146u, 0);
  return 1;
}

```

## disassembly

```asm
0x180059ad0  push    rbx
0x180059ad2  push    rbp
0x180059ad3  push    rsi
0x180059ad4  push    rdi
0x180059ad5  push    r14
0x180059ad7  sub     rsp, 30h
0x180059adb  mov     rsi, r9
0x180059ade  mov     r14, r8
0x180059ae1  mov     edi, edx
0x180059ae3  mov     rbx, rcx
0x180059ae6  test    rcx, rcx
0x180059ae9  jz      loc_180059C9A
0x180059aef  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x180059af4  mov     rbp, rax
0x180059af7  cmp     qword ptr [rax+30h], 0
0x180059afc  jz      short loc_180059B1F
0x180059afe  mov     rcx, rbx; HWND
0x180059b01  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x180059b06  test    rax, rax
0x180059b09  jnz     short loc_180059B1F
0x180059b0b  mov     rcx, [rbp+30h]; this
0x180059b0f  mov     rdx, rbx; HWND
0x180059b12  call    ?SubclassWindow@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::SubclassWindow(HWND__ *)
0x180059b17  mov     qword ptr [rbp+30h], 0
0x180059b1f  mov     ebp, 110h
0x180059b24  cmp     edi, ebp
0x180059b26  jnz     loc_180059BB5
0x180059b2c  lea     rcx, aCommdlgLbselch; "commdlg_LBSelChangedNotify"
0x180059b33  call    cs:__imp_RegisterWindowMessageW
0x180059b39  lea     rcx, aCommdlgSharevi; "commdlg_ShareViolation"
0x180059b40  mov     cs:?_afxMsgLBSELCHANGE@@3IA, eax; uint _afxMsgLBSELCHANGE
0x180059b46  call    cs:__imp_RegisterWindowMessageW
0x180059b4c  lea     rcx, aCommdlgFilenam; "commdlg_FileNameOK"
0x180059b53  mov     cs:?_afxMsgSHAREVI@@3IA, eax; uint _afxMsgSHAREVI
0x180059b59  call    cs:__imp_RegisterWindowMessageW
0x180059b5f  lea     rcx, aCommdlgColorok; "commdlg_ColorOK"
0x180059b66  mov     cs:?_afxMsgFILEOK@@3IA, eax; uint _afxMsgFILEOK
0x180059b6c  call    cs:__imp_RegisterWindowMessageW
0x180059b72  lea     rcx, aCommdlgHelp; "commdlg_help"
0x180059b79  mov     cs:?_afxMsgCOLOROK@@3IA, eax; uint _afxMsgCOLOROK
0x180059b7f  call    cs:__imp_RegisterWindowMessageW
0x180059b85  lea     rcx, aCommdlgSetrgbc; "commdlg_SetRGBColor"
0x180059b8c  mov     cs:?_afxMsgHELP@@3IA, eax; uint _afxMsgHELP
0x180059b92  call    cs:__imp_RegisterWindowMessageW
0x180059b98  mov     r9, rsi; LPARAM
0x180059b9b  mov     r8, r14; WPARAM
0x180059b9e  mov     edx, ebp; UINT
0x180059ba0  mov     cs:?_afxMsgSETRGB@@3IA, eax; uint _afxMsgSETRGB
0x180059ba6  mov     rcx, rbx; HWND
0x180059ba9  call    ?AfxDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; AfxDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180059bae  mov     eax, eax
0x180059bb0  jmp     loc_180059C9C
0x180059bb5  cmp     edi, cs:?_afxMsgHELP@@3IA; uint _afxMsgHELP
0x180059bbb  mov     edx, 111h; Msg
0x180059bc0  jz      loc_180059CC3
0x180059bc6  cmp     edi, edx
0x180059bc8  jnz     short loc_180059BD9
0x180059bca  mov     eax, 40Eh
0x180059bcf  cmp     r14w, ax
0x180059bd3  jz      loc_180059CC3
0x180059bd9  cmp     edi, 0C000h
0x180059bdf  jb      loc_180059C9A
0x180059be5  mov     rcx, rbx; HWND
0x180059be8  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x180059bed  lea     rdx, ?classCFileDialog@CFileDialog@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x180059bf4  mov     rcx, rax; this
0x180059bf7  mov     rbx, rax
0x180059bfa  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180059bff  test    eax, eax
0x180059c01  jz      short loc_180059C13
0x180059c03  test    dword ptr [rbx+120h], 80000h
0x180059c0d  jnz     loc_180059C9A
0x180059c13  cmp     edi, cs:?_afxMsgSHAREVI@@3IA; uint _afxMsgSHAREVI
0x180059c19  jnz     short loc_180059C35
0x180059c1b  mov     rax, [rbx]
0x180059c1e  mov     rdx, rsi
0x180059c21  mov     rcx, rbx
0x180059c24  mov     rax, [rax+1B0h]
0x180059c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c30  jmp     loc_180059BAE
0x180059c35  cmp     edi, cs:?_afxMsgFILEOK@@3IA; uint _afxMsgFILEOK
0x180059c3b  jnz     short loc_180059C6E
0x180059c3d  cmp     cs:dword_180131A40, 0
0x180059c44  jz      short loc_180059C4D
0x180059c46  mov     [rbx+3E0h], rsi
0x180059c4d  mov     rax, [rbx]
0x180059c50  mov     rcx, rbx
0x180059c53  mov     rax, [rax+1B8h]
0x180059c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c5f  mov     qword ptr [rbx+3E0h], 0
0x180059c6a  cdqe
0x180059c6c  jmp     short loc_180059C9C
0x180059c6e  cmp     edi, cs:?_afxMsgLBSELCHANGE@@3IA; uint _afxMsgLBSELCHANGE
0x180059c74  jnz     short loc_180059CA7
0x180059c76  mov     r10, [rbx]
0x180059c79  mov     rax, rsi
0x180059c7c  shr     rax, 10h
0x180059c80  mov     edx, r14d
0x180059c83  movzx   r9d, ax
0x180059c87  mov     rcx, rbx
0x180059c8a  movzx   r8d, si
0x180059c8e  mov     rax, [r10+1C0h]
0x180059c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c9a  xor     eax, eax
0x180059c9c  add     rsp, 30h
0x180059ca0  pop     r14
0x180059ca2  pop     rdi
0x180059ca3  pop     rsi
0x180059ca4  pop     rbp
0x180059ca5  pop     rbx
0x180059ca6  retn
0x180059ca7  cmp     edi, cs:?_afxMsgCOLOROK@@3IA; uint _afxMsgCOLOROK
0x180059cad  jnz     short loc_180059C9A
0x180059caf  mov     rax, [rbx]
0x180059cb2  mov     rcx, rbx
0x180059cb5  mov     rax, [rax+1B0h]
0x180059cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cc1  jmp     short loc_180059C6A
0x180059cc3  xor     r9d, r9d; lParam
0x180059cc6  mov     r8d, 0E146h; wParam
0x180059ccc  mov     rcx, rbx; hWnd
0x180059ccf  call    cs:__imp_SendMessageW
0x180059cd5  mov     eax, 1
0x180059cda  jmp     short loc_180059C9C
```
