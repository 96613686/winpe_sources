# CRestoreDialog::TaskDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14002927c`
- end: `0x140029490`
- name: `?TaskDlgProc@CRestoreDialog@@IEAAJPEAUHWND__@@I_K_J@Z`
- size: `532`
- prototype: `int(CRestoreDialog *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140029970`

## callees

- `0x140003ce4`
- `0x140014474`
- `0x14002448c`
- `0x140028728`
- `0x14002877c`
- `0x14002927c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029457`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002931f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002947c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002931f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002947c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x140029308`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1400293ec`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x140029308`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1400293ec`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1400293c8`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1400293c8`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002933d`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002937d`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002933d`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002937d`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpSetWindowSubclass` at `0x140029421`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpSetWindowSubclass` at `0x140029421`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpRemoveWindowSubclass` at `0x1400292d2`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpRemoveWindowSubclass` at `0x1400292d2`

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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, LastError);
    }
    *((_DWORD *)this + 16) = GetTickCount();
  }
  return v4;
}

```

## disassembly

```asm
0x14002927c  push    rbx
0x14002927e  push    rbp
0x14002927f  push    rsi
0x140029280  push    rdi
0x140029281  sub     rsp, 28h
0x140029285  xor     ebp, ebp
0x140029287  mov     rsi, rdx
0x14002928a  mov     rdi, rcx
0x14002928d  test    r8d, r8d
0x140029290  jz      loc_1400293D3
0x140029296  sub     r8d, 1
0x14002929a  jz      loc_1400293AC
0x1400292a0  sub     r8d, 1
0x1400292a4  jz      loc_140029348
0x1400292aa  sub     r8d, 2
0x1400292ae  jz      short loc_1400292EE
0x1400292b0  cmp     r8d, 1
0x1400292b4  jnz     loc_140029485
0x1400292ba  cmp     [rcx+30h], ebp
0x1400292bd  jz      short loc_1400292D8
0x1400292bf  call    IsWerUIpSetWindowSubclassPresent
0x1400292c4  test    al, al
0x1400292c6  jz      short loc_1400292D8
0x1400292c8  lea     rdx, ?static_TaskDlgSubclassProc@CRestoreDialog@@KA_JPEAUHWND__@@I_K_J11@Z; CRestoreDialog::static_TaskDlgSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x1400292cf  mov     rcx, rsi
0x1400292d2  call    cs:__imp_WerUIpRemoveWindowSubclass
0x1400292d8  mov     rcx, [rdi+60h]
0x1400292dc  xor     edx, edx
0x1400292de  mov     rax, [rcx]
0x1400292e1  mov     rax, [rax]
0x1400292e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400292e9  jmp     loc_140029485
0x1400292ee  cmp     [rcx+34h], ebp
0x1400292f1  jz      short loc_140029313
0x1400292f3  mov     rcx, [rcx]; hDlg
0x1400292f6  test    rcx, rcx
0x1400292f9  jz      loc_140029485
0x1400292ff  xor     edx, edx; nResult
0x140029301  mov     dword ptr [rdi+58h], 3
0x140029308  call    cs:__imp_EndDialog
0x14002930e  jmp     loc_140029485
0x140029313  cmp     [rcx+3Ch], ebp
0x140029316  jz      loc_140029485
0x14002931c  mov     ebx, [rcx+38h]
0x14002931f  call    cs:__imp_GetTickCount
0x140029325  sub     eax, ebx
0x140029327  cmp     eax, 3E8h
0x14002932c  jbe     loc_140029485
0x140029332  mov     edx, 5; nCmdShow
0x140029337  mov     [rdi+3Ch], ebp
0x14002933a  mov     rcx, rsi; hWnd
0x14002933d  call    cs:__imp_ShowWindow
0x140029343  jmp     loc_140029485
0x140029348  cmp     [rcx+8], ebp
0x14002934b  jnz     short loc_140029353
0x14002934d  cmp     r9, 2
0x140029351  jz      short loc_14002936F
0x140029353  sub     r9, 2
0x140029357  jz      short loc_1400293A0
0x140029359  sub     r9, 8
0x14002935d  jz      short loc_140029391
0x14002935f  sub     r9, 1
0x140029363  jz      short loc_140029385
0x140029365  cmp     r9, 1
0x140029369  jnz     loc_140029485
0x14002936f  add     rcx, 48h ; 'H'; this
0x140029373  call    ?NotifyDialogHidden@CGhostCommunication@@QEAAXXZ; CGhostCommunication::NotifyDialogHidden(void)
0x140029378  xor     edx, edx; nCmdShow
0x14002937a  mov     rcx, rsi; hWnd
0x14002937d  call    cs:__imp_ShowWindow
0x140029383  jmp     short loc_140029396
0x140029385  mov     dword ptr [rcx+58h], 5
0x14002938c  jmp     loc_140029485
0x140029391  call    ?OnRestoreButton@CRestoreDialog@@IEAAJXZ; CRestoreDialog::OnRestoreButton(void)
0x140029396  mov     ebp, 1
0x14002939b  jmp     loc_140029485
0x1400293a0  mov     dword ptr [rcx+58h], 4
0x1400293a7  jmp     loc_140029485
0x1400293ac  cmp     dword ptr [rcx+8], 1
0x1400293b0  jnz     loc_140029485
0x1400293b6  mov     r9d, 1Eh; lParam
0x1400293bc  mov     edx, 46Bh; Msg
0x1400293c1  mov     rcx, rsi; hWnd
0x1400293c4  lea     r8d, [r9-1Dh]; wParam
0x1400293c8  call    cs:__imp_SendMessageW
0x1400293ce  jmp     loc_140029485
0x1400293d3  mov     [rcx], rsi
0x1400293d6  cmp     [rcx+34h], ebp
0x1400293d9  jz      short loc_1400293F2
0x1400293db  test    rsi, rsi
0x1400293de  jz      short loc_1400293F2
0x1400293e0  mov     dword ptr [rcx+58h], 3
0x1400293e7  xor     edx, edx; nResult
0x1400293e9  mov     rcx, rsi; hDlg
0x1400293ec  call    cs:__imp_EndDialog
0x1400293f2  mov     rcx, [rdi+60h]
0x1400293f6  mov     rdx, rsi
0x1400293f9  mov     rax, [rcx]
0x1400293fc  mov     rax, [rax]
0x1400293ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029404  mov     [rdi+8], ebp
0x140029407  call    IsWerUIpSetWindowSubclassPresent
0x14002940c  test    al, al
0x14002940e  jz      short loc_140029427
0x140029410  lea     rcx, [rdi+30h]
0x140029414  mov     r9, rdi
0x140029417  lea     r8, ?static_TaskDlgSubclassProc@CRestoreDialog@@KA_JPEAUHWND__@@I_K_J11@Z; CRestoreDialog::static_TaskDlgSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x14002941e  mov     rdx, rsi
0x140029421  call    cs:__imp_WerUIpSetWindowSubclass
0x140029427  mov     edx, [rdi+0Ch]; unsigned int
0x14002942a  lea     r8, [rdi+50h]; unsigned int *
0x14002942e  mov     rcx, rsi; hwnd
0x140029431  mov     [rdi+48h], rsi
0x140029435  call    ?UtilRegisterErrorReportingDialog@@YAHPEAUHWND__@@KPEAI@Z; UtilRegisterErrorReportingDialog(HWND__ *,ulong,uint *)
0x14002943a  test    eax, eax
0x14002943c  jnz     short loc_14002947C
0x14002943e  mov     rax, cs:WPP_GLOBAL_Control
0x140029445  lea     rcx, WPP_GLOBAL_Control
0x14002944c  cmp     rax, rcx
0x14002944f  jz      short loc_14002947C
0x140029451  test    byte ptr [rax+1Ch], 1
0x140029455  jz      short loc_14002947C
0x140029457  call    cs:__imp_GetLastError
0x14002945d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029464  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002946b  mov     edx, 11h
0x140029470  mov     r9d, eax
0x140029473  mov     rcx, [rcx+10h]
0x140029477  call    WPP_SF_d
0x14002947c  call    cs:__imp_GetTickCount
0x140029482  mov     [rdi+40h], eax
0x140029485  mov     eax, ebp
0x140029487  add     rsp, 28h
0x14002948b  pop     rdi
0x14002948c  pop     rsi
0x14002948d  pop     rbp
0x14002948e  pop     rbx
0x14002948f  retn
```
