# OnOkRemove(HWND__ *,_DeviceTreeData *)

- ea: `0x180007888`
- end: `0x180007a92`
- name: `?OnOkRemove@@YAHPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(HWND, struct _DeviceTreeData *lpParameter)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007aa0`

## callees

- `0x180003048`
- `0x180005eec`
- `0x180007888`
- `0x1800083a4`
- `0x18000873a`
- `0x180008760`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x1800079cf`
- `KERNEL32!GetExitCodeThread` at `0x180007a3d`
- `KERNEL32!GetExitCodeThread` at `0x1800079cf`
- `KERNEL32!GetExitCodeThread` at `0x180007a3d`
- `KERNEL32!CloseHandle` at `0x180007a57`
- `KERNEL32!CloseHandle` at `0x180007a57`
- `KERNEL32!CreateThread` at `0x180007a0e`
- `KERNEL32!CreateThread` at `0x180007a0e`
- `USER32!GetSystemMetrics` at `0x180007915`
- `USER32!GetSystemMetrics` at `0x180007915`
- `USER32!LoadCursorW` at `0x1800078f6`
- `USER32!LoadCursorW` at `0x1800078f6`
- `USER32!GetDlgItem` at `0x1800078c7`
- `USER32!GetDlgItem` at `0x1800078de`
- `USER32!GetDlgItem` at `0x1800078c7`
- `USER32!GetDlgItem` at `0x1800078de`
- `USER32!EnableWindow` at `0x1800078d2`
- `USER32!EnableWindow` at `0x1800078e9`
- `USER32!EnableWindow` at `0x1800078d2`
- `USER32!EnableWindow` at `0x1800078e9`
- `USER32!SetCursor` at `0x1800078ff`
- `USER32!SetCursor` at `0x180007a60`
- `USER32!SetCursor` at `0x1800078ff`
- `USER32!SetCursor` at `0x180007a60`
- `SHELL32!ShellExecuteExW` at `0x1800079a4`
- `SHELL32!ShellExecuteExW` at `0x1800079a4`

## pseudocode

```c
_BOOL8 __fastcall OnOkRemove(HWND a1, struct _DeviceTreeData *lpParameter)
{
  BOOL v3; // ebx
  HWND DlgItem; // rax
  HWND v6; // rax
  HCURSOR CursorW; // rax
  HCURSOR v8; // rax
  __int64 v9; // r14
  HCURSOR v10; // r15
  const unsigned __int16 *v11; // rcx
  unsigned int v12; // edx
  HANDLE hProcess; // rcx
  unsigned int v14; // edx
  _BOOL8 result; // rax
  DWORD ExitCode; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hThread; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ThreadId[4]; // [rsp+40h] [rbp-C0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[464]; // [rsp+C0h] [rbp-40h] BYREF

  ExitCode = 0;
  v3 = 0;
  DlgItem = GetDlgItem(a1, 1);
  EnableWindow(DlgItem, 0);
  v6 = GetDlgItem(a1, 2);
  EnableWindow(v6, 0);
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v8 = SetCursor(CursorW);
  v9 = *((_QWORD *)lpParameter + 6);
  v10 = v8;
  *((_BYTE *)lpParameter + 99) = 1;
  if ( !GetSystemMetrics(4096) || DoesUserHavePrivilege(v11) )
  {
    ThreadId[0] = 0;
    hThread = CreateThread(0, 0, RemoveThread, lpParameter, 0, ThreadId);
    if ( hThread )
    {
      ExitCode = WaitDlgMessagePump(a1, v14, &hThread);
      if ( !ExitCode && GetExitCodeThread(hThread, &ExitCode) && !ExitCode )
        v3 = 1;
      hProcess = hThread;
      goto LABEL_15;
    }
  }
  else if ( (int)StringCchPrintfW(v20, 0x1CCu, L"%x \"%s\"", *((unsigned int *)lpParameter + 6), *(_QWORD *)(v9 + 32)) >= 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.hwnd = (HWND)*((_QWORD *)lpParameter + 3);
    pExecInfo.lpFile = L"DeviceEject.exe";
    pExecInfo.lpParameters = v20;
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 1088;
    pExecInfo.nShow = 1;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      ExitCode = WaitDlgMessagePump(a1, v12, &pExecInfo.hProcess);
      if ( !ExitCode && GetExitCodeThread(pExecInfo.hProcess, &ExitCode) )
        v3 = ExitCode == 0;
      hProcess = pExecInfo.hProcess;
LABEL_15:
      CloseHandle(hProcess);
    }
  }
  SetCursor(v10);
  result = v3;
  *((_BYTE *)lpParameter + 99) = 0;
  return result;
}

```

## disassembly

```asm
0x180007888  mov     [rsp-8+arg_10], rbx
0x18000788d  push    rbp
0x18000788e  push    rsi
0x18000788f  push    rdi
0x180007890  push    r14
0x180007892  push    r15
0x180007894  lea     rbp, [rsp-370h]
0x18000789c  sub     rsp, 470h
0x1800078a3  mov     rax, cs:__security_cookie
0x1800078aa  xor     rax, rsp
0x1800078ad  mov     [rbp+390h+var_30], rax
0x1800078b4  mov     rdi, rdx
0x1800078b7  mov     [rsp+490h+ExitCode], 0
0x1800078bf  xor     ebx, ebx
0x1800078c1  mov     rsi, rcx
0x1800078c4  lea     edx, [rbx+1]; nIDDlgItem
0x1800078c7  call    cs:__imp_GetDlgItem
0x1800078cd  mov     rcx, rax; hWnd
0x1800078d0  xor     edx, edx; bEnable
0x1800078d2  call    cs:__imp_EnableWindow
0x1800078d8  lea     edx, [rbx+2]; nIDDlgItem
0x1800078db  mov     rcx, rsi; hDlg
0x1800078de  call    cs:__imp_GetDlgItem
0x1800078e4  mov     rcx, rax; hWnd
0x1800078e7  xor     edx, edx; bEnable
0x1800078e9  call    cs:__imp_EnableWindow
0x1800078ef  mov     edx, 7F02h; lpCursorName
0x1800078f4  xor     ecx, ecx; hInstance
0x1800078f6  call    cs:__imp_LoadCursorW
0x1800078fc  mov     rcx, rax; hCursor
0x1800078ff  call    cs:__imp_SetCursor
0x180007905  mov     r14, [rdi+30h]
0x180007909  mov     ecx, 1000h; nIndex
0x18000790e  mov     r15, rax
0x180007911  mov     byte ptr [rdi+63h], 1
0x180007915  call    cs:__imp_GetSystemMetrics
0x18000791b  test    eax, eax
0x18000791d  jz      loc_1800079E9
0x180007923  call    ?DoesUserHavePrivilege@@YAHPEBG@Z; DoesUserHavePrivilege(ushort const *)
0x180007928  test    eax, eax
0x18000792a  jnz     loc_1800079E9
0x180007930  mov     rax, [r14+20h]
0x180007934  lea     r8, aXS; "%x \"%s\""
0x18000793b  mov     r9d, [rdi+18h]
0x18000793f  lea     rcx, [rbp+390h+var_3D0]; unsigned __int16 *
0x180007943  mov     edx, 1CCh; unsigned __int64
0x180007948  mov     qword ptr [rsp+490h+dwCreationFlags], rax
0x18000794d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007952  test    eax, eax
0x180007954  js      loc_180007A5D
0x18000795a  lea     r14d, [rbx+70h]
0x18000795e  xor     edx, edx; Val
0x180007960  mov     r8d, r14d; Size
0x180007963  lea     rcx, [rsp+490h+pExecInfo]; void *
0x180007968  call    memset_0
0x18000796d  mov     rax, [rdi+18h]
0x180007971  lea     rcx, [rsp+490h+pExecInfo]; pExecInfo
0x180007976  mov     [rsp+490h+pExecInfo.hwnd], rax
0x18000797b  lea     rax, aDeviceejectExe; "DeviceEject.exe"
0x180007982  mov     [rsp+490h+pExecInfo.lpFile], rax
0x180007987  lea     rax, [rbp+390h+var_3D0]
0x18000798b  mov     [rsp+490h+pExecInfo.lpParameters], rax
0x180007990  mov     [rsp+490h+pExecInfo.cbSize], r14d
0x180007995  mov     [rsp+490h+pExecInfo.fMask], 440h
0x18000799d  mov     [rbp+390h+pExecInfo.nShow], 1
0x1800079a4  call    cs:__imp_ShellExecuteExW
0x1800079aa  test    eax, eax
0x1800079ac  jz      loc_180007A5D
0x1800079b2  lea     r8, [rbp+390h+pExecInfo.hProcess]; void **
0x1800079b6  mov     rcx, rsi; HWND
0x1800079b9  call    ?WaitDlgMessagePump@@YAKPEAUHWND__@@KPEAPEAX@Z; WaitDlgMessagePump(HWND__ *,ulong,void * *)
0x1800079be  mov     [rsp+490h+ExitCode], eax
0x1800079c2  test    eax, eax
0x1800079c4  jnz     short loc_1800079E3
0x1800079c6  mov     rcx, [rbp+390h+pExecInfo.hProcess]; hThread
0x1800079ca  lea     rdx, [rsp+490h+ExitCode]; lpExitCode
0x1800079cf  call    cs:__imp_GetExitCodeThread
0x1800079d5  test    eax, eax
0x1800079d7  jz      short loc_1800079E3
0x1800079d9  cmp     [rsp+490h+ExitCode], ebx
0x1800079dd  jnz     short loc_1800079E3
0x1800079df  lea     ebx, [r14-6Fh]
0x1800079e3  mov     rcx, [rbp+390h+pExecInfo.hProcess]
0x1800079e7  jmp     short loc_180007A57
0x1800079e9  lea     rax, [rsp+490h+ThreadId]
0x1800079ee  mov     [rsp+490h+hThread], rbx
0x1800079f3  mov     [rsp+490h+lpThreadId], rax; lpThreadId
0x1800079f8  lea     r8, ?RemoveThread@@YAKPEAX@Z; lpStartAddress
0x1800079ff  mov     r9, rdi; lpParameter
0x180007a02  mov     [rsp+490h+dwCreationFlags], ebx; dwCreationFlags
0x180007a06  xor     edx, edx; dwStackSize
0x180007a08  mov     [rsp+490h+ThreadId], ebx
0x180007a0c  xor     ecx, ecx; lpThreadAttributes
0x180007a0e  call    cs:__imp_CreateThread
0x180007a14  mov     [rsp+490h+hThread], rax
0x180007a19  test    rax, rax
0x180007a1c  jz      short loc_180007A5D
0x180007a1e  lea     r8, [rsp+490h+hThread]; void **
0x180007a23  mov     rcx, rsi; HWND
0x180007a26  call    ?WaitDlgMessagePump@@YAKPEAUHWND__@@KPEAPEAX@Z; WaitDlgMessagePump(HWND__ *,ulong,void * *)
0x180007a2b  mov     [rsp+490h+ExitCode], eax
0x180007a2f  test    eax, eax
0x180007a31  jnz     short loc_180007A52
0x180007a33  mov     rcx, [rsp+490h+hThread]; hThread
0x180007a38  lea     rdx, [rsp+490h+ExitCode]; lpExitCode
0x180007a3d  call    cs:__imp_GetExitCodeThread
0x180007a43  test    eax, eax
0x180007a45  jz      short loc_180007A52
0x180007a47  cmp     [rsp+490h+ExitCode], ebx
0x180007a4b  jnz     short loc_180007A52
0x180007a4d  mov     ebx, 1
0x180007a52  mov     rcx, [rsp+490h+hThread]; hObject
0x180007a57  call    cs:__imp_CloseHandle
0x180007a5d  mov     rcx, r15; hCursor
0x180007a60  call    cs:__imp_SetCursor
0x180007a66  mov     eax, ebx
0x180007a68  mov     byte ptr [rdi+63h], 0
0x180007a6c  mov     rcx, [rbp+390h+var_30]
0x180007a73  xor     rcx, rsp; StackCookie
0x180007a76  call    __security_check_cookie
0x180007a7b  mov     rbx, [rsp+490h+arg_10]
0x180007a83  add     rsp, 470h
0x180007a8a  pop     r15
0x180007a8c  pop     r14
0x180007a8e  pop     rdi
0x180007a8f  pop     rsi
0x180007a90  pop     rbp
0x180007a91  retn
```
