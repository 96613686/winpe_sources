# CRestoreDialog::TaskDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14002adb8`
- end: `0x14002b009`
- name: `?TaskDlgProc@CRestoreDialog@@IEAAJPEAUHWND__@@I_K_J@Z`
- size: `593`
- prototype: `int(CRestoreDialog *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002b530`

## callees

- `0x140003d34`
- `0x140014f14`
- `0x140025cc8`
- `0x14002a1f8`
- `0x14002a25c`
- `0x14002adb8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002ae67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002afee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002ae67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002afee`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x14002ae4a`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x14002af4c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x14002ae4a`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x14002af4c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14002af22`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14002af22`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002ae8b`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002aed1`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002ae8b`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002aed1`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpSetWindowSubclass` at `0x14002af87`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpSetWindowSubclass` at `0x14002af87`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpRemoveWindowSubclass` at `0x14002ae0e`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpRemoveWindowSubclass` at `0x14002ae0e`

## pseudocode

```c
__int64 __fastcall CRestoreDialog::TaskDlgProc(CRestoreDialog *this, HWND a2, int a3, __int64 a4)
{
  unsigned int v4; // ebp
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  HWND v10; // rcx
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  unsigned int v15; // edx
  DWORD LastError; // eax

  v4 = 0;
  if ( a3 )
  {
    v7 = a3 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 2;
        if ( v9 )
        {
          if ( v9 == 1 )
          {
            if ( *((_DWORD *)this + 12) && (unsigned __int8)IsWerUIpSetWindowSubclassPresent() )
              WerUIpRemoveWindowSubclass(a2, CRestoreDialog::static_TaskDlgSubclassProc);
            (***((void (__fastcall ****)(_QWORD, _QWORD))this + 12))(*((_QWORD *)this + 12), 0);
          }
        }
        else if ( *((_DWORD *)this + 13) )
        {
          v10 = *(HWND *)this;
          if ( v10 )
          {
            *((_DWORD *)this + 22) = 3;
            EndDialog(v10, 0);
          }
        }
        else if ( *((_DWORD *)this + 15) )
        {
          v11 = *((_DWORD *)this + 14);
          if ( GetTickCount() - v11 > 0x3E8 )
          {
            *((_DWORD *)this + 15) = 0;
            ShowWindow(a2, 5);
          }
        }
        return v4;
      }
      if ( !*((_DWORD *)this + 2) && a4 == 2 )
        goto LABEL_22;
      v12 = a4 - 2;
      if ( !v12 )
      {
        *((_DWORD *)this + 22) = 4;
        return v4;
      }
      v13 = v12 - 8;
      if ( !v13 )
      {
        CRestoreDialog::OnRestoreButton(this);
        return 1;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        *((_DWORD *)this + 22) = 5;
        return v4;
      }
      if ( v14 == 1 )
      {
LABEL_22:
        CGhostCommunication::NotifyDialogHidden((CRestoreDialog *)((char *)this + 72));
        ShowWindow(a2, 0);
        return 1;
      }
    }
    else if ( *((_DWORD *)this + 2) == 1 )
    {
      SendMessageW(a2, 0x46Bu, 1u, 30);
    }
  }
  else
  {
    *(_QWORD *)this = a2;
    if ( *((_DWORD *)this + 13) && a2 )
    {
      *((_DWORD *)this + 22) = 3;
      EndDialog(a2, 0);
    }
    (***((void (__fastcall ****)(_QWORD, HWND))this + 12))(*((_QWORD *)this + 12), a2);
    *((_DWORD *)this + 2) = 0;
    if ( (unsigned __int8)IsWerUIpSetWindowSubclassPresent() )
      WerUIpSetWindowSubclass((char *)this + 48, a2, CRestoreDialog::static_TaskDlgSubclassProc, this);
    v15 = *((_DWORD *)this + 3);
    *((_QWORD *)this + 9) = a2;
    if ( !(unsigned int)UtilRegisterErrorReportingDialog(a2, v15, (unsigned int *)this + 20)
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
    }
    *((_DWORD *)this + 16) = GetTickCount();
  }
  return v4;
}

```

## disassembly

```asm
0x14002adb8  push    rbx
0x14002adba  push    rbp
0x14002adbb  push    rsi
0x14002adbc  push    rdi
0x14002adbd  sub     rsp, 28h
0x14002adc1  xor     ebp, ebp
0x14002adc3  mov     rsi, rdx
0x14002adc6  mov     rdi, rcx
0x14002adc9  test    r8d, r8d
0x14002adcc  jz      loc_14002AF33
0x14002add2  sub     r8d, 1
0x14002add6  jz      loc_14002AF06
0x14002addc  sub     r8d, 1
0x14002ade0  jz      loc_14002AE9C
0x14002ade6  sub     r8d, 2
0x14002adea  jz      short loc_14002AE30
0x14002adec  cmp     r8d, 1
0x14002adf0  jnz     loc_14002AFFD
0x14002adf6  cmp     [rcx+30h], ebp
0x14002adf9  jz      short loc_14002AE1A
0x14002adfb  call    IsWerUIpSetWindowSubclassPresent
0x14002ae00  test    al, al
0x14002ae02  jz      short loc_14002AE1A
0x14002ae04  lea     rdx, ?static_TaskDlgSubclassProc@CRestoreDialog@@KA_JPEAUHWND__@@I_K_J11@Z; CRestoreDialog::static_TaskDlgSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x14002ae0b  mov     rcx, rsi
0x14002ae0e  call    cs:__imp_WerUIpRemoveWindowSubclass
0x14002ae15  nop     dword ptr [rax+rax+00h]
0x14002ae1a  mov     rcx, [rdi+60h]
0x14002ae1e  xor     edx, edx
0x14002ae20  mov     rax, [rcx]
0x14002ae23  mov     rax, [rax]
0x14002ae26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae2b  jmp     loc_14002AFFD
0x14002ae30  cmp     [rcx+34h], ebp
0x14002ae33  jz      short loc_14002AE5B
0x14002ae35  mov     rcx, [rcx]; hDlg
0x14002ae38  test    rcx, rcx
0x14002ae3b  jz      loc_14002AFFD
0x14002ae41  xor     edx, edx; nResult
0x14002ae43  mov     dword ptr [rdi+58h], 3
0x14002ae4a  call    cs:__imp_EndDialog
0x14002ae51  nop     dword ptr [rax+rax+00h]
0x14002ae56  jmp     loc_14002AFFD
0x14002ae5b  cmp     [rcx+3Ch], ebp
0x14002ae5e  jz      loc_14002AFFD
0x14002ae64  mov     ebx, [rcx+38h]
0x14002ae67  call    cs:__imp_GetTickCount
0x14002ae6e  nop     dword ptr [rax+rax+00h]
0x14002ae73  sub     eax, ebx
0x14002ae75  cmp     eax, 3E8h
0x14002ae7a  jbe     loc_14002AFFD
0x14002ae80  mov     edx, 5; nCmdShow
0x14002ae85  mov     [rdi+3Ch], ebp
0x14002ae88  mov     rcx, rsi; hWnd
0x14002ae8b  call    cs:__imp_ShowWindow
0x14002ae92  nop     dword ptr [rax+rax+00h]
0x14002ae97  jmp     loc_14002AFFD
0x14002ae9c  cmp     [rcx+8], ebp
0x14002ae9f  jnz     short loc_14002AEA7
0x14002aea1  cmp     r9, 2
0x14002aea5  jz      short loc_14002AEC3
0x14002aea7  sub     r9, 2
0x14002aeab  jz      short loc_14002AEFA
0x14002aead  sub     r9, 8
0x14002aeb1  jz      short loc_14002AEEB
0x14002aeb3  sub     r9, 1
0x14002aeb7  jz      short loc_14002AEDF
0x14002aeb9  cmp     r9, 1
0x14002aebd  jnz     loc_14002AFFD
0x14002aec3  add     rcx, 48h ; 'H'; this
0x14002aec7  call    ?NotifyDialogHidden@CGhostCommunication@@QEAAXXZ; CGhostCommunication::NotifyDialogHidden(void)
0x14002aecc  xor     edx, edx; nCmdShow
0x14002aece  mov     rcx, rsi; hWnd
0x14002aed1  call    cs:__imp_ShowWindow
0x14002aed8  nop     dword ptr [rax+rax+00h]
0x14002aedd  jmp     short loc_14002AEF0
0x14002aedf  mov     dword ptr [rcx+58h], 5
0x14002aee6  jmp     loc_14002AFFD
0x14002aeeb  call    ?OnRestoreButton@CRestoreDialog@@IEAAJXZ; CRestoreDialog::OnRestoreButton(void)
0x14002aef0  mov     ebp, 1
0x14002aef5  jmp     loc_14002AFFD
0x14002aefa  mov     dword ptr [rcx+58h], 4
0x14002af01  jmp     loc_14002AFFD
0x14002af06  cmp     dword ptr [rcx+8], 1
0x14002af0a  jnz     loc_14002AFFD
0x14002af10  mov     r9d, 1Eh; lParam
0x14002af16  mov     edx, 46Bh; Msg
0x14002af1b  mov     rcx, rsi; hWnd
0x14002af1e  lea     r8d, [r9-1Dh]; wParam
0x14002af22  call    cs:__imp_SendMessageW
0x14002af29  nop     dword ptr [rax+rax+00h]
0x14002af2e  jmp     loc_14002AFFD
0x14002af33  mov     [rcx], rsi
0x14002af36  cmp     [rcx+34h], ebp
0x14002af39  jz      short loc_14002AF58
0x14002af3b  test    rsi, rsi
0x14002af3e  jz      short loc_14002AF58
0x14002af40  mov     dword ptr [rcx+58h], 3
0x14002af47  xor     edx, edx; nResult
0x14002af49  mov     rcx, rsi; hDlg
0x14002af4c  call    cs:__imp_EndDialog
0x14002af53  nop     dword ptr [rax+rax+00h]
0x14002af58  mov     rcx, [rdi+60h]
0x14002af5c  mov     rdx, rsi
0x14002af5f  mov     rax, [rcx]
0x14002af62  mov     rax, [rax]
0x14002af65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af6a  mov     [rdi+8], ebp
0x14002af6d  call    IsWerUIpSetWindowSubclassPresent
0x14002af72  test    al, al
0x14002af74  jz      short loc_14002AF93
0x14002af76  lea     rcx, [rdi+30h]
0x14002af7a  mov     r9, rdi
0x14002af7d  lea     r8, ?static_TaskDlgSubclassProc@CRestoreDialog@@KA_JPEAUHWND__@@I_K_J11@Z; CRestoreDialog::static_TaskDlgSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x14002af84  mov     rdx, rsi
0x14002af87  call    cs:__imp_WerUIpSetWindowSubclass
0x14002af8e  nop     dword ptr [rax+rax+00h]
0x14002af93  mov     edx, [rdi+0Ch]; unsigned int
0x14002af96  lea     r8, [rdi+50h]; unsigned int *
0x14002af9a  mov     rcx, rsi; hwnd
0x14002af9d  mov     [rdi+48h], rsi
0x14002afa1  call    ?UtilRegisterErrorReportingDialog@@YAHPEAUHWND__@@KPEAI@Z; UtilRegisterErrorReportingDialog(HWND__ *,ulong,uint *)
0x14002afa6  test    eax, eax
0x14002afa8  jnz     short loc_14002AFEE
0x14002afaa  mov     rax, cs:WPP_GLOBAL_Control
0x14002afb1  lea     rcx, WPP_GLOBAL_Control
0x14002afb8  cmp     rax, rcx
0x14002afbb  jz      short loc_14002AFEE
0x14002afbd  test    byte ptr [rax+1Ch], 1
0x14002afc1  jz      short loc_14002AFEE
0x14002afc3  call    cs:__imp_GetLastError
0x14002afca  nop     dword ptr [rax+rax+00h]
0x14002afcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afd6  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002afdd  mov     edx, 11h
0x14002afe2  mov     r9d, eax
0x14002afe5  mov     rcx, [rcx+10h]
0x14002afe9  call    WPP_SF_d
0x14002afee  call    cs:__imp_GetTickCount
0x14002aff5  nop     dword ptr [rax+rax+00h]
0x14002affa  mov     [rdi+40h], eax
0x14002affd  mov     eax, ebp
0x14002afff  add     rsp, 28h
0x14002b003  pop     rdi
0x14002b004  pop     rsi
0x14002b005  pop     rbp
0x14002b006  pop     rbx
0x14002b007  retn
```
