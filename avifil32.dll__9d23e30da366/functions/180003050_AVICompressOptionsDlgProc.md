# AVICompressOptionsDlgProc

- ea: `0x180003050`
- end: `0x1800032cc`
- name: `AVICompressOptionsDlgProc`
- size: `636`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180003050`
- `0x1800034e4`
- `0x180003968`
- `0x180008300`

## import_xrefs

- `USER32!EnableWindow` at `0x18000310d`
- `USER32!EnableWindow` at `0x18000329b`
- `USER32!EnableWindow` at `0x18000310d`
- `USER32!EnableWindow` at `0x18000329b`
- `USER32!SetDlgItemInt` at `0x180003282`
- `USER32!SetDlgItemInt` at `0x180003282`
- `USER32!CheckDlgButton` at `0x18000326f`
- `USER32!CheckDlgButton` at `0x18000326f`
- `USER32!GetDlgItem` at `0x180003102`
- `USER32!GetDlgItem` at `0x180003290`
- `USER32!GetDlgItem` at `0x180003102`
- `USER32!GetDlgItem` at `0x180003290`
- `USER32!GetDlgItemInt` at `0x180003133`
- `USER32!GetDlgItemInt` at `0x180003133`
- `USER32!IsDlgButtonChecked` at `0x1800030f2`
- `USER32!IsDlgButtonChecked` at `0x18000311d`
- `USER32!IsDlgButtonChecked` at `0x1800030f2`
- `USER32!IsDlgButtonChecked` at `0x18000311d`
- `USER32!SendDlgItemMessageW` at `0x180003202`
- `USER32!SendDlgItemMessageW` at `0x180003226`
- `USER32!SendDlgItemMessageW` at `0x180003202`
- `USER32!SendDlgItemMessageW` at `0x180003226`
- `USER32!EndDialog` at `0x180003184`
- `USER32!EndDialog` at `0x1800031b4`
- `USER32!EndDialog` at `0x180003184`
- `USER32!EndDialog` at `0x1800031b4`
- `USER32!SendMessageW` at `0x18000323d`
- `USER32!SendMessageW` at `0x18000323d`

## pseudocode

```c
INT_PTR __fastcall AVICompressOptionsDlgProc(HWND a1, int a2, __int64 a3)
{
  int v6; // ebx
  INT_PTR v8; // rdi
  UINT v9; // ebx
  HWND DlgItem; // rax
  UINT v11; // r14d
  UINT DlgItemInt; // eax
  int v13; // r10d
  int v14; // r8d
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  int i; // ebp
  UINT v19; // r14d
  int v20; // ebp
  HWND v21; // rax
  struct _AVISTREAMINFOW psi; // [rsp+30h] [rbp-F8h] BYREF

  memset_0(&psi, 0, sizeof(psi));
  v6 = a2 - 272;
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v8 = 0;
      if ( (unsigned __int16)a3 == 1 )
      {
        v11 = IsDlgButtonChecked(a1, 110);
        DlgItemInt = GetDlgItemInt(a1, 111, 0, 0);
        v13 = gnNumStreams;
        v14 = 0;
        if ( gnNumStreams > 0 )
        {
          v15 = gapOpt;
          do
          {
            *(_DWORD *)(*(_QWORD *)(v15 + 8LL * v14) + 52LL) = DlgItemInt;
            v16 = *(_QWORD *)(v15 + 8LL * v14);
            if ( v11 )
              *(_DWORD *)(v16 + 20) |= 1u;
            else
              *(_DWORD *)(v16 + 20) &= ~1u;
            ++v14;
          }
          while ( v14 < v13 );
        }
      }
      else if ( (unsigned __int16)a3 != 2 )
      {
        switch ( (unsigned __int16)a3 )
        {
          case 'n':
            v9 = IsDlgButtonChecked(a1, 110);
            DlgItem = GetDlgItem(a1, 111);
            EnableWindow(DlgItem, v9);
            break;
          case 'q':
            if ( WORD1(a3) == 1 )
              NewStreamChosen(a1);
            break;
          case 'r':
            StreamOptions(a1);
            break;
        }
        return 0;
      }
      LOBYTE(v8) = a3 == 1;
      EndDialog(a1, v8);
    }
    return 0;
  }
  if ( gnNumStreams == 1 )
  {
    gnCurStream = 0;
    v17 = StreamOptions(a1);
    EndDialog(a1, v17);
  }
  else
  {
    for ( i = 0; i < gnNumStreams; ++i )
    {
      AVIStreamInfoW(*(PAVISTREAM *)(gapAVI + 8LL * i), &psi, 204);
      SendDlgItemMessageW(a1, 113, 0x143u, 0, (LPARAM)psi.szName);
    }
    SendDlgItemMessageW(a1, 113, 0x14Eu, 0, 0);
    SendMessageW(a1, 0x111u, 0x10071u, (LPARAM)a1);
    if ( (*(_DWORD *)(*(_QWORD *)gapOpt + 20LL) & 8) != 0 )
    {
      v19 = *(_DWORD *)(*(_QWORD *)gapOpt + 52LL);
      v20 = *(_DWORD *)(*(_QWORD *)gapOpt + 20LL) & 1;
    }
    else
    {
      v19 = 1;
      v20 = 0;
    }
    CheckDlgButton(a1, 110, v20);
    SetDlgItemInt(a1, 111, v19, 0);
    v21 = GetDlgItem(a1, 111);
    EnableWindow(v21, v20);
  }
  return 1;
}

```

## disassembly

```asm
0x180003050  mov     [rsp+arg_8], rbx
0x180003055  mov     [rsp+arg_10], rbp
0x18000305a  push    rsi
0x18000305b  push    rdi
0x18000305c  push    r14
0x18000305e  sub     rsp, 110h
0x180003065  mov     rax, cs:__security_cookie
0x18000306c  xor     rax, rsp
0x18000306f  mov     [rsp+128h+var_28], rax
0x180003077  mov     rbp, r8
0x18000307a  mov     ebx, edx
0x18000307c  mov     rsi, rcx
0x18000307f  xor     edx, edx; Val
0x180003081  mov     r8d, 0CCh; Size
0x180003087  lea     rcx, [rsp+128h+psi]; void *
0x18000308c  call    memset_0
0x180003091  sub     ebx, 110h
0x180003097  jz      loc_18000318F
0x18000309d  cmp     ebx, 1
0x1800030a0  jz      short loc_1800030A9
0x1800030a2  xor     eax, eax
0x1800030a4  jmp     loc_1800032A4
0x1800030a9  movzx   edx, bp
0x1800030ac  mov     ebx, 1
0x1800030b1  xor     edi, edi
0x1800030b3  sub     edx, ebx
0x1800030b5  jz      short loc_180003115
0x1800030b7  sub     edx, ebx
0x1800030b9  jz      loc_180003177
0x1800030bf  sub     edx, 6Ch ; 'l'
0x1800030c2  jz      short loc_1800030EA
0x1800030c4  sub     edx, 3
0x1800030c7  jz      short loc_1800030D7
0x1800030c9  cmp     edx, ebx
0x1800030cb  jnz     short loc_1800030A2
0x1800030cd  mov     rcx, rsi; hWnd
0x1800030d0  call    StreamOptions
0x1800030d5  jmp     short loc_1800030A2
0x1800030d7  shr     rbp, 10h
0x1800030db  cmp     bp, bx
0x1800030de  jnz     short loc_1800030A2
0x1800030e0  mov     rcx, rsi; hDlg
0x1800030e3  call    NewStreamChosen
0x1800030e8  jmp     short loc_1800030A2
0x1800030ea  mov     edx, 6Eh ; 'n'; nIDButton
0x1800030ef  mov     rcx, rsi; hDlg
0x1800030f2  call    cs:__imp_IsDlgButtonChecked
0x1800030f8  mov     edx, 6Fh ; 'o'; nIDDlgItem
0x1800030fd  mov     rcx, rsi; hDlg
0x180003100  mov     ebx, eax
0x180003102  call    cs:__imp_GetDlgItem
0x180003108  mov     rcx, rax; hWnd
0x18000310b  mov     edx, ebx; bEnable
0x18000310d  call    cs:__imp_EnableWindow
0x180003113  jmp     short loc_1800030A2
0x180003115  mov     edx, 6Eh ; 'n'; nIDButton
0x18000311a  mov     rcx, rsi; hDlg
0x18000311d  call    cs:__imp_IsDlgButtonChecked
0x180003123  xor     r9d, r9d; bSigned
0x180003126  xor     r8d, r8d; lpTranslated
0x180003129  mov     rcx, rsi; hDlg
0x18000312c  mov     r14d, eax
0x18000312f  lea     edx, [r9+6Fh]; nIDDlgItem
0x180003133  call    cs:__imp_GetDlgItemInt
0x180003139  mov     r10d, cs:gnNumStreams
0x180003140  mov     r8d, edi
0x180003143  mov     r11d, eax
0x180003146  test    r10d, r10d
0x180003149  jle     short loc_180003177
0x18000314b  mov     r9, cs:gapOpt
0x180003152  movsxd  rcx, r8d
0x180003155  mov     rax, [r9+rcx*8]
0x180003159  mov     [rax+34h], r11d
0x18000315d  mov     rdx, [r9+rcx*8]
0x180003161  test    r14d, r14d
0x180003164  jz      short loc_18000316B
0x180003166  or      [rdx+14h], ebx
0x180003169  jmp     short loc_18000316F
0x18000316b  and     dword ptr [rdx+14h], 0FFFFFFFEh
0x18000316f  add     r8d, ebx
0x180003172  cmp     r8d, r10d
0x180003175  jl      short loc_180003152
0x180003177  cmp     rbp, rbx
0x18000317a  mov     rcx, rsi; hDlg
0x18000317d  setz    dil
0x180003181  mov     rdx, rdi; nResult
0x180003184  call    cs:__imp_EndDialog
0x18000318a  jmp     loc_1800030A2
0x18000318f  mov     eax, cs:gnNumStreams
0x180003195  mov     ebx, 1
0x18000319a  xor     edi, edi
0x18000319c  cmp     eax, ebx
0x18000319e  jnz     short loc_1800031BF
0x1800031a0  mov     rcx, rsi; hWnd
0x1800031a3  mov     cs:gnCurStream, edi
0x1800031a9  call    StreamOptions
0x1800031ae  movsxd  rdx, eax; nResult
0x1800031b1  mov     rcx, rsi; hDlg
0x1800031b4  call    cs:__imp_EndDialog
0x1800031ba  jmp     loc_1800032A1
0x1800031bf  mov     ebp, edi
0x1800031c1  mov     r14d, 71h ; 'q'
0x1800031c7  test    eax, eax
0x1800031c9  jle     short loc_180003212
0x1800031cb  mov     rcx, cs:gapAVI
0x1800031d2  lea     rdx, [rsp+128h+psi]; psi
0x1800031d7  movsxd  rax, ebp
0x1800031da  mov     r8d, 0CCh; lSize
0x1800031e0  mov     rcx, [rcx+rax*8]; pavi
0x1800031e4  call    AVIStreamInfoW
0x1800031e9  lea     rax, [rsp+128h+psi.szName]
0x1800031ee  xor     r9d, r9d; wParam
0x1800031f1  mov     r8d, 143h; Msg
0x1800031f7  mov     [rsp+128h+lParam], rax; lParam
0x1800031fc  mov     edx, r14d; nIDDlgItem
0x1800031ff  mov     rcx, rsi; hDlg
0x180003202  call    cs:__imp_SendDlgItemMessageW
0x180003208  add     ebp, ebx
0x18000320a  cmp     ebp, cs:gnNumStreams
0x180003210  jl      short loc_1800031CB
0x180003212  xor     r9d, r9d; wParam
0x180003215  mov     [rsp+128h+lParam], rdi; lParam
0x18000321a  mov     r8d, 14Eh; Msg
0x180003220  mov     edx, r14d; nIDDlgItem
0x180003223  mov     rcx, rsi; hDlg
0x180003226  call    cs:__imp_SendDlgItemMessageW
0x18000322c  mov     r9, rsi; lParam
0x18000322f  mov     edx, 111h; Msg
0x180003234  mov     r8d, 10071h; wParam
0x18000323a  mov     rcx, rsi; hWnd
0x18000323d  call    cs:__imp_SendMessageW
0x180003243  mov     rax, cs:gapOpt
0x18000324a  mov     r14, [rax]
0x18000324d  mov     ebp, [r14+14h]
0x180003251  test    bpl, 8
0x180003255  jz      short loc_18000325F
0x180003257  mov     r14d, [r14+34h]
0x18000325b  and     ebp, ebx
0x18000325d  jmp     short loc_180003264
0x18000325f  mov     r14d, ebx
0x180003262  mov     ebp, edi
0x180003264  mov     r8d, ebp; uCheck
0x180003267  mov     edx, 6Eh ; 'n'; nIDButton
0x18000326c  mov     rcx, rsi; hDlg
0x18000326f  call    cs:__imp_CheckDlgButton
0x180003275  xor     r9d, r9d; bSigned
0x180003278  mov     r8d, r14d; uValue
0x18000327b  mov     rcx, rsi; hDlg
0x18000327e  lea     edx, [r9+6Fh]; nIDDlgItem
0x180003282  call    cs:__imp_SetDlgItemInt
0x180003288  mov     edx, 6Fh ; 'o'; nIDDlgItem
0x18000328d  mov     rcx, rsi; hDlg
0x180003290  call    cs:__imp_GetDlgItem
0x180003296  mov     rcx, rax; hWnd
0x180003299  mov     edx, ebp; bEnable
0x18000329b  call    cs:__imp_EnableWindow
0x1800032a1  mov     rax, rbx
0x1800032a4  mov     rcx, [rsp+128h+var_28]
0x1800032ac  xor     rcx, rsp; StackCookie
0x1800032af  call    __security_check_cookie
0x1800032b4  lea     r11, [rsp+128h+var_18]
0x1800032bc  mov     rbx, [r11+28h]
0x1800032c0  mov     rbp, [r11+30h]
0x1800032c4  mov     rsp, r11
0x1800032c7  pop     r14
0x1800032c9  pop     rdi
0x1800032ca  pop     rsi
0x1800032cb  retn
```
