# SysTray_EnableService(int,int)

- ea: `0x180005528`
- end: `0x1800055e1`
- name: `?SysTray_EnableService@@YAHHH@Z`
- size: `185`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180005234`

## callees

- `0x180003048`
- `0x180005528`
- `0x180008760`

## import_xrefs

- `USER32!FindWindowW` at `0x18000554c`
- `USER32!FindWindowW` at `0x18000554c`
- `USER32!SendMessageW` at `0x180005568`
- `USER32!SendMessageW` at `0x180005568`
- `SHELL32!ShellExecuteW` at `0x1800055ce`
- `SHELL32!ShellExecuteW` at `0x1800055ce`

## string_xrefs

- `0x1800055b5`: `%windir%\system32\SYSTRAY.EXE`

## pseudocode

```c
_BOOL8 __fastcall SysTray_EnableService(__int64 a1, int a2)
{
  LPARAM v2; // rbx
  HWND WindowW; // rax
  WCHAR Parameters[32]; // [rsp+30h] [rbp-58h] BYREF

  v2 = a2;
  WindowW = FindWindowW(L"SystemTray_Main", 0);
  if ( WindowW )
  {
    SendMessageW(WindowW, 0x4DCu, 2u, v2);
    return 1;
  }
  if ( !(_DWORD)v2 )
    return 1;
  StringCchPrintfW(Parameters, 0x20u, L"%i");
  return (unsigned __int64)ShellExecuteW(0, L"open", L"%windir%\\system32\\SYSTRAY.EXE", Parameters, 0, 4) > 0x20;
}

```

## disassembly

```asm
0x180005528  push    rbx
0x18000552a  sub     rsp, 80h
0x180005531  mov     rax, cs:__security_cookie
0x180005538  xor     rax, rsp
0x18000553b  mov     [rsp+88h+var_18], rax
0x180005540  movsxd  rbx, edx
0x180005543  lea     rcx, aSystemtrayMain; "SystemTray_Main"
0x18000554a  xor     edx, edx; lpWindowName
0x18000554c  call    cs:__imp_FindWindowW
0x180005552  test    rax, rax
0x180005555  jz      short loc_180005589
0x180005557  mov     r9, rbx; lParam
0x18000555a  mov     edx, 4DCh; Msg
0x18000555f  mov     r8d, 2; wParam
0x180005565  mov     rcx, rax; hWnd
0x180005568  call    cs:__imp_SendMessageW
0x18000556e  mov     eax, 1
0x180005573  mov     rcx, [rsp+88h+var_18]
0x180005578  xor     rcx, rsp; StackCookie
0x18000557b  call    __security_check_cookie
0x180005580  add     rsp, 80h
0x180005587  pop     rbx
0x180005588  retn
0x180005589  test    ebx, ebx
0x18000558b  jz      short loc_18000556E
0x18000558d  mov     r9d, 2
0x180005593  lea     r8, ?szFORMAT@?9??SysTray_EnableService@@YAHHH@Z@4QBGB; "%i"
0x18000559a  lea     rcx, [rsp+88h+Parameters]; unsigned __int16 *
0x18000559f  lea     edx, [r9+1Eh]; unsigned __int64
0x1800055a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800055a8  lea     r9, [rsp+88h+Parameters]; lpParameters
0x1800055ad  mov     [rsp+88h+nShowCmd], 4; nShowCmd
0x1800055b5  lea     r8, ?szFILE@?9??SysTray_EnableService@@YAHHH@Z@4QBGB; "%windir%\\system32\\SYSTRAY.EXE"
0x1800055bc  mov     [rsp+88h+lpDirectory], 0; lpDirectory
0x1800055c5  lea     rdx, ?szOPEN@?9??SysTray_EnableService@@YAHHH@Z@4QBGB; "open"
0x1800055cc  xor     ecx, ecx; hwnd
0x1800055ce  call    cs:__imp_ShellExecuteW
0x1800055d4  xor     ecx, ecx
0x1800055d6  cmp     rax, 20h ; ' '
0x1800055da  setnbe  cl
0x1800055dd  mov     eax, ecx
0x1800055df  jmp     short loc_180005573
```
