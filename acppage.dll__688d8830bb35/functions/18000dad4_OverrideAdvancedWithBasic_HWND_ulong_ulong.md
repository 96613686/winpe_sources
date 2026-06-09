# OverrideAdvancedWithBasic(HWND__ *,ulong,ulong)

- ea: `0x18000dad4`
- end: `0x18000dd80`
- name: `?OverrideAdvancedWithBasic@@YAXPEAUHWND__@@KK@Z`
- size: `684`
- prototype: `void __fastcall(HWND hDlg, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000e7d0`

## callees

- `0x18000dad4`
- `0x18000f0dc`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000db16`
- `USER32!GetDlgItem` at `0x18000db2e`
- `USER32!GetDlgItem` at `0x18000db46`
- `USER32!GetDlgItem` at `0x18000db5e`
- `USER32!GetDlgItem` at `0x18000db76`
- `USER32!GetDlgItem` at `0x18000db8e`
- `USER32!GetDlgItem` at `0x18000dba6`
- `USER32!GetDlgItem` at `0x18000db16`
- `USER32!GetDlgItem` at `0x18000db2e`
- `USER32!GetDlgItem` at `0x18000db46`
- `USER32!GetDlgItem` at `0x18000db5e`
- `USER32!GetDlgItem` at `0x18000db76`
- `USER32!GetDlgItem` at `0x18000db8e`
- `USER32!GetDlgItem` at `0x18000dba6`
- `USER32!EnableWindow` at `0x18000db21`
- `USER32!EnableWindow` at `0x18000db39`
- `USER32!EnableWindow` at `0x18000db51`
- `USER32!EnableWindow` at `0x18000db69`
- `USER32!EnableWindow` at `0x18000db81`
- `USER32!EnableWindow` at `0x18000db99`
- `USER32!EnableWindow` at `0x18000dbb1`
- `USER32!EnableWindow` at `0x18000db21`
- `USER32!EnableWindow` at `0x18000db39`
- `USER32!EnableWindow` at `0x18000db51`
- `USER32!EnableWindow` at `0x18000db69`
- `USER32!EnableWindow` at `0x18000db81`
- `USER32!EnableWindow` at `0x18000db99`
- `USER32!EnableWindow` at `0x18000dbb1`
- `USER32!SendDlgItemMessageW` at `0x18000db01`
- `USER32!SendDlgItemMessageW` at `0x18000dbcf`
- `USER32!SendDlgItemMessageW` at `0x18000dc1b`
- `USER32!SendDlgItemMessageW` at `0x18000dc99`
- `USER32!SendDlgItemMessageW` at `0x18000dcee`
- `USER32!SendDlgItemMessageW` at `0x18000dd07`
- `USER32!SendDlgItemMessageW` at `0x18000dd20`
- `USER32!SendDlgItemMessageW` at `0x18000dd39`
- `USER32!SendDlgItemMessageW` at `0x18000dd52`
- `USER32!SendDlgItemMessageW` at `0x18000dd6b`
- `USER32!SendDlgItemMessageW` at `0x18000db01`
- `USER32!SendDlgItemMessageW` at `0x18000dbcf`
- `USER32!SendDlgItemMessageW` at `0x18000dc1b`
- `USER32!SendDlgItemMessageW` at `0x18000dc99`
- `USER32!SendDlgItemMessageW` at `0x18000dcee`
- `USER32!SendDlgItemMessageW` at `0x18000dd07`
- `USER32!SendDlgItemMessageW` at `0x18000dd20`
- `USER32!SendDlgItemMessageW` at `0x18000dd39`
- `USER32!SendDlgItemMessageW` at `0x18000dd52`
- `USER32!SendDlgItemMessageW` at `0x18000dd6b`

## pseudocode

```c
void __fastcall OverrideAdvancedWithBasic(HWND hDlg, unsigned int a2, unsigned int a3)
{
  LRESULT v6; // rbx
  HWND DlgItem; // rax
  HWND v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  HWND v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  WPARAM v17; // r9

  v6 = SendDlgItemMessageW(hDlg, 5019, 0x147u, 0, 0);
  DlgItem = GetDlgItem(hDlg, 5021);
  EnableWindow(DlgItem, 0);
  v8 = GetDlgItem(hDlg, 5023);
  EnableWindow(v8, 0);
  v9 = GetDlgItem(hDlg, 5024);
  EnableWindow(v9, 0);
  v10 = GetDlgItem(hDlg, 5046);
  EnableWindow(v10, 0);
  v11 = GetDlgItem(hDlg, 5031);
  EnableWindow(v11, 0);
  v12 = GetDlgItem(hDlg, 5025);
  EnableWindow(v12, 0);
  v13 = GetDlgItem(hDlg, 5043);
  EnableWindow(v13, 0);
  SendDlgItemMessageW(hDlg, 5043, 0xF1u, 0, 0);
  v14 = 0;
  if ( v6 != -1 )
    v14 = v6;
  if ( !v14 )
  {
    SendDlgItemMessageW(hDlg, 5021, 0x14Eu, 0, 0);
    SendDlgItemMessageW(hDlg, 5023, 0xF1u, 0, 0);
    SendDlgItemMessageW(hDlg, 5024, 0xF1u, 0, 0);
    SendDlgItemMessageW(hDlg, 5046, 0xF1u, 0, 0);
    goto LABEL_12;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    SendDlgItemMessageW(hDlg, 5021, 0x14Eu, 0, 0);
    SetFlagIfFiletypeAllows(hDlg, 5023, a2, a3);
    SetFlagIfFiletypeAllows(hDlg, 5024, a2, a3);
    SetFlagIfFiletypeAllows(hDlg, 5046, a2, a3);
LABEL_12:
    SendDlgItemMessageW(hDlg, 5031, 0xF1u, 0, 0);
    SendDlgItemMessageW(hDlg, 5025, 0xF1u, 0, 0);
    return;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    if ( v16 != 1 )
      return;
    v17 = 2;
  }
  else
  {
    v17 = 1;
  }
  SendDlgItemMessageW(hDlg, 5021, 0x14Eu, v17, 0);
  SetFlagIfFiletypeAllows(hDlg, 5023, a2, a3);
  SetFlagIfFiletypeAllows(hDlg, 5024, a2, a3);
  SetFlagIfFiletypeAllows(hDlg, 5046, a2, a3);
  SetFlagIfFiletypeAllows(hDlg, 5031, a2, a3);
  SetFlagIfFiletypeAllows(hDlg, 5025, a2, a3);
}

```

## disassembly

```asm
0x18000dad4  push    rbx
0x18000dad6  push    rbp
0x18000dad7  push    rsi
0x18000dad8  push    rdi
0x18000dad9  push    r12
0x18000dadb  push    r13
0x18000dadd  push    r15
0x18000dadf  sub     rsp, 30h
0x18000dae3  mov     esi, r8d
0x18000dae6  mov     ebp, edx
0x18000dae8  xor     r15d, r15d
0x18000daeb  mov     edx, 139Bh; nIDDlgItem
0x18000daf0  mov     r8d, 147h; Msg
0x18000daf6  mov     [rsp+68h+lParam], r15; lParam
0x18000dafb  xor     r9d, r9d; wParam
0x18000dafe  mov     rdi, rcx
0x18000db01  call    cs:__imp_SendDlgItemMessageW
0x18000db07  mov     r13d, 139Dh
0x18000db0d  mov     rcx, rdi; hDlg
0x18000db10  mov     edx, r13d; nIDDlgItem
0x18000db13  mov     rbx, rax
0x18000db16  call    cs:__imp_GetDlgItem
0x18000db1c  mov     rcx, rax; hWnd
0x18000db1f  xor     edx, edx; bEnable
0x18000db21  call    cs:__imp_EnableWindow
0x18000db27  lea     edx, [r13+2]; nIDDlgItem
0x18000db2b  mov     rcx, rdi; hDlg
0x18000db2e  call    cs:__imp_GetDlgItem
0x18000db34  mov     rcx, rax; hWnd
0x18000db37  xor     edx, edx; bEnable
0x18000db39  call    cs:__imp_EnableWindow
0x18000db3f  lea     edx, [r13+3]; nIDDlgItem
0x18000db43  mov     rcx, rdi; hDlg
0x18000db46  call    cs:__imp_GetDlgItem
0x18000db4c  mov     rcx, rax; hWnd
0x18000db4f  xor     edx, edx; bEnable
0x18000db51  call    cs:__imp_EnableWindow
0x18000db57  lea     edx, [r13+19h]; nIDDlgItem
0x18000db5b  mov     rcx, rdi; hDlg
0x18000db5e  call    cs:__imp_GetDlgItem
0x18000db64  mov     rcx, rax; hWnd
0x18000db67  xor     edx, edx; bEnable
0x18000db69  call    cs:__imp_EnableWindow
0x18000db6f  lea     edx, [r13+0Ah]; nIDDlgItem
0x18000db73  mov     rcx, rdi; hDlg
0x18000db76  call    cs:__imp_GetDlgItem
0x18000db7c  mov     rcx, rax; hWnd
0x18000db7f  xor     edx, edx; bEnable
0x18000db81  call    cs:__imp_EnableWindow
0x18000db87  lea     edx, [r13+4]; nIDDlgItem
0x18000db8b  mov     rcx, rdi; hDlg
0x18000db8e  call    cs:__imp_GetDlgItem
0x18000db94  mov     rcx, rax; hWnd
0x18000db97  xor     edx, edx; bEnable
0x18000db99  call    cs:__imp_EnableWindow
0x18000db9f  lea     edx, [r13+16h]; nIDDlgItem
0x18000dba3  mov     rcx, rdi; hDlg
0x18000dba6  call    cs:__imp_GetDlgItem
0x18000dbac  mov     rcx, rax; hWnd
0x18000dbaf  xor     edx, edx; bEnable
0x18000dbb1  call    cs:__imp_EnableWindow
0x18000dbb7  mov     r12d, 0F1h
0x18000dbbd  mov     [rsp+68h+lParam], r15; lParam
0x18000dbc2  mov     r8d, r12d; Msg
0x18000dbc5  lea     edx, [r13+16h]; nIDDlgItem
0x18000dbc9  xor     r9d, r9d; wParam
0x18000dbcc  mov     rcx, rdi; hDlg
0x18000dbcf  call    cs:__imp_SendDlgItemMessageW
0x18000dbd5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000dbd9  mov     ecx, r15d
0x18000dbdc  cmovnz  ecx, ebx
0x18000dbdf  test    ecx, ecx
0x18000dbe1  jz      loc_18000DCDA
0x18000dbe7  sub     ecx, 1
0x18000dbea  jz      loc_18000DC85
0x18000dbf0  sub     ecx, 1
0x18000dbf3  jz      short loc_18000DC04
0x18000dbf5  cmp     ecx, 1
0x18000dbf8  jnz     loc_18000DD71
0x18000dbfe  lea     r9d, [r15+2]
0x18000dc02  jmp     short loc_18000DC0A
0x18000dc04  mov     r9d, 1; wParam
0x18000dc0a  mov     r8d, 14Eh; Msg
0x18000dc10  mov     [rsp+68h+lParam], r15; lParam
0x18000dc15  mov     edx, r13d; nIDDlgItem
0x18000dc18  mov     rcx, rdi; hDlg
0x18000dc1b  call    cs:__imp_SendDlgItemMessageW
0x18000dc21  mov     r9d, esi; unsigned int
0x18000dc24  mov     r8d, ebp; unsigned int
0x18000dc27  mov     edx, 139Fh; int
0x18000dc2c  mov     rcx, rdi; hDlg
0x18000dc2f  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dc34  mov     r9d, esi; unsigned int
0x18000dc37  mov     r8d, ebp; unsigned int
0x18000dc3a  mov     edx, 13A0h; int
0x18000dc3f  mov     rcx, rdi; hDlg
0x18000dc42  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dc47  mov     r9d, esi; unsigned int
0x18000dc4a  mov     r8d, ebp; unsigned int
0x18000dc4d  mov     edx, 13B6h; int
0x18000dc52  mov     rcx, rdi; hDlg
0x18000dc55  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dc5a  mov     r9d, esi; unsigned int
0x18000dc5d  mov     r8d, ebp; unsigned int
0x18000dc60  mov     edx, 13A7h; int
0x18000dc65  mov     rcx, rdi; hDlg
0x18000dc68  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dc6d  mov     r9d, esi; unsigned int
0x18000dc70  mov     r8d, ebp; unsigned int
0x18000dc73  mov     edx, 13A1h; int
0x18000dc78  mov     rcx, rdi; hDlg
0x18000dc7b  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dc80  jmp     loc_18000DD71
0x18000dc85  xor     r9d, r9d; wParam
0x18000dc88  mov     [rsp+68h+lParam], r15; lParam
0x18000dc8d  mov     r8d, 14Eh; Msg
0x18000dc93  mov     edx, r13d; nIDDlgItem
0x18000dc96  mov     rcx, rdi; hDlg
0x18000dc99  call    cs:__imp_SendDlgItemMessageW
0x18000dc9f  mov     r9d, esi; unsigned int
0x18000dca2  mov     r8d, ebp; unsigned int
0x18000dca5  mov     edx, 139Fh; int
0x18000dcaa  mov     rcx, rdi; hDlg
0x18000dcad  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dcb2  mov     r9d, esi; unsigned int
0x18000dcb5  mov     r8d, ebp; unsigned int
0x18000dcb8  mov     edx, 13A0h; int
0x18000dcbd  mov     rcx, rdi; hDlg
0x18000dcc0  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dcc5  mov     r9d, esi; unsigned int
0x18000dcc8  mov     r8d, ebp; unsigned int
0x18000dccb  mov     edx, 13B6h; int
0x18000dcd0  mov     rcx, rdi; hDlg
0x18000dcd3  call    ?SetFlagIfFiletypeAllows@@YAXPEAUHWND__@@HKK@Z; SetFlagIfFiletypeAllows(HWND__ *,int,ulong,ulong)
0x18000dcd8  jmp     short loc_18000DD3F
0x18000dcda  xor     r9d, r9d; wParam
0x18000dcdd  mov     [rsp+68h+lParam], r15; lParam
0x18000dce2  mov     r8d, 14Eh; Msg
0x18000dce8  mov     edx, r13d; nIDDlgItem
0x18000dceb  mov     rcx, rdi; hDlg
0x18000dcee  call    cs:__imp_SendDlgItemMessageW
0x18000dcf4  xor     r9d, r9d; wParam
0x18000dcf7  mov     [rsp+68h+lParam], r15; lParam
0x18000dcfc  mov     r8d, r12d; Msg
0x18000dcff  mov     edx, 139Fh; nIDDlgItem
0x18000dd04  mov     rcx, rdi; hDlg
0x18000dd07  call    cs:__imp_SendDlgItemMessageW
0x18000dd0d  xor     r9d, r9d; wParam
0x18000dd10  mov     [rsp+68h+lParam], r15; lParam
0x18000dd15  mov     r8d, r12d; Msg
0x18000dd18  mov     edx, 13A0h; nIDDlgItem
0x18000dd1d  mov     rcx, rdi; hDlg
0x18000dd20  call    cs:__imp_SendDlgItemMessageW
0x18000dd26  xor     r9d, r9d; wParam
0x18000dd29  mov     [rsp+68h+lParam], r15; lParam
0x18000dd2e  mov     r8d, r12d; Msg
0x18000dd31  mov     edx, 13B6h; nIDDlgItem
0x18000dd36  mov     rcx, rdi; hDlg
0x18000dd39  call    cs:__imp_SendDlgItemMessageW
0x18000dd3f  xor     r9d, r9d; wParam
0x18000dd42  mov     [rsp+68h+lParam], r15; lParam
0x18000dd47  mov     r8d, r12d; Msg
0x18000dd4a  mov     edx, 13A7h; nIDDlgItem
0x18000dd4f  mov     rcx, rdi; hDlg
0x18000dd52  call    cs:__imp_SendDlgItemMessageW
0x18000dd58  xor     r9d, r9d; wParam
0x18000dd5b  mov     [rsp+68h+lParam], r15; lParam
0x18000dd60  mov     r8d, r12d; Msg
0x18000dd63  mov     edx, 13A1h; nIDDlgItem
0x18000dd68  mov     rcx, rdi; hDlg
0x18000dd6b  call    cs:__imp_SendDlgItemMessageW
0x18000dd71  add     rsp, 30h
0x18000dd75  pop     r15
0x18000dd77  pop     r13
0x18000dd79  pop     r12
0x18000dd7b  pop     rdi
0x18000dd7c  pop     rsi
0x18000dd7d  pop     rbp
0x18000dd7e  pop     rbx
0x18000dd7f  retn
```
