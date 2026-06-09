# AboutDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180014edc`
- end: `0x180015218`
- name: `?AboutDialogProc@@YAHPEAUHWND__@@I_K_J@Z`
- size: `828`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180013d18`
- `0x180014d88`
- `0x180014edc`
- `0x1800164ec`
- `0x1800169c4`
- `0x180026838`
- `0x180057ba0`
- `0x1800fa1ac`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrcpyA` at `0x180015181`
- `KERNEL32!lstrcpyA` at `0x180015181`
- `KERNEL32!lstrcatA` at `0x180015198`
- `KERNEL32!lstrcatA` at `0x1800151af`
- `KERNEL32!lstrcatA` at `0x180015198`
- `KERNEL32!lstrcatA` at `0x1800151af`
- `KERNEL32!GetShortPathNameA` at `0x180014ff3`
- `KERNEL32!GetShortPathNameA` at `0x180014ff3`
- `KERNEL32!WinExec` at `0x180015005`
- `KERNEL32!WinExec` at `0x180015005`
- `USER32!SendDlgItemMessageA` at `0x18001516a`
- `USER32!SendDlgItemMessageA` at `0x18001516a`
- `USER32!SetDlgItemTextA` at `0x18001505c`
- `USER32!SetDlgItemTextA` at `0x1800150e6`
- `USER32!SetDlgItemTextA` at `0x1800151be`
- `USER32!SetDlgItemTextA` at `0x18001505c`
- `USER32!SetDlgItemTextA` at `0x1800150e6`
- `USER32!SetDlgItemTextA` at `0x1800151be`
- `USER32!EndDialog` at `0x1800151e9`
- `USER32!EndDialog` at `0x1800151e9`
- `USER32!wsprintfA` at `0x1800150d4`
- `USER32!wsprintfA` at `0x1800150d4`
- `USER32!SendMessageA` at `0x180015101`
- `USER32!SendMessageA` at `0x180015101`
- `GDI32!GetObjectA` at `0x18001511b`
- `GDI32!GetObjectA` at `0x18001511b`
- `GDI32!CreateFontIndirectA` at `0x180015137`
- `GDI32!CreateFontIndirectA` at `0x180015137`
- `GDI32!DeleteObject` at `0x1800151de`
- `GDI32!DeleteObject` at `0x1800151de`
- `ADVAPI32!RegOpenKeyExA` at `0x180014f78`
- `ADVAPI32!RegOpenKeyExA` at `0x180014f78`
- `ADVAPI32!RegQueryValueExA` at `0x180014fc2`
- `ADVAPI32!RegQueryValueExA` at `0x180014fc2`
- `ADVAPI32!RegCloseKey` at `0x180014fd1`
- `ADVAPI32!RegCloseKey` at `0x180014fd1`

## string_xrefs

- `0x180014f5c`: `Software\Microsoft\Shared Tools\MSInfo`

## pseudocode

```c
__int64 __fastcall AboutDialogProc(HWND a1, int a2, __int64 a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  const CHAR *v7; // rcx
  const char *v9; // rax
  unsigned int v10; // r11d
  const char *v11; // r8
  HFONT v12; // rax
  const CHAR *v13; // rax
  const CHAR *v14; // rax
  const CHAR *v15; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  int lParam; // [rsp+38h] [rbp-C8h] BYREF
  int lParam_4; // [rsp+3Ch] [rbp-C4h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  LOGFONTA pv; // [rsp+50h] [rbp-B0h] BYREF
  CHAR String[128]; // [rsp+90h] [rbp-70h] BYREF
  CHAR String1[400]; // [rsp+110h] [rbp+10h] BYREF
  BYTE Data[2064]; // [rsp+2A0h] [rbp+1A0h] BYREF
  CHAR szShortPath[2048]; // [rsp+AB0h] [rbp+9B0h] BYREF

  v4 = a2 - 16;
  if ( !v4 )
    goto LABEL_29;
  v5 = v4 - 67;
  if ( !v5 )
  {
    GetStdHelp(1u, 181008);
    return 1;
  }
  v6 = v5 - 189;
  if ( !v6 )
  {
    DlgInit(a1);
    v9 = IntlLpstrStringOfID(584);
    InsertSzsInBuffer(v9, "1153", 0, 0, String, 128);
    SetDlgItemTextA(a1, 117, String);
    EbGetVersion(&v20, &lParam, &v16, &lParam_4);
    v10 = lParam_4 & 0xFFFFFFEF;
    if ( (lParam_4 & 0xFFFFFFEF) != 0 )
    {
      if ( v10 == 4 )
      {
        v11 = "Test";
      }
      else
      {
        v11 = "Unknown";
        if ( v10 == 8 )
          v11 = "Debug";
      }
    }
    else
    {
      v11 = "Retail";
    }
    wsprintfA(String, "VBA: %s %u.%u.%u", v11, v20, lParam, v16);
    SetDlgItemTextA(a1, 118, String);
    GetForms3Version(a1);
    ho = (HGDIOBJ)SendMessageA(a1, 0x31u, 0, 0);
    if ( GetObjectA(ho, 60, &pv) )
    {
      pv.lfWeight = 400;
      pv.lfPitchAndFamily = 34;
      v12 = CreateFontIndirectA(&pv);
      ho = v12;
      if ( !v12 )
      {
LABEL_30:
        EndDialog(a1, 0);
        return 1;
      }
    }
    else
    {
      v12 = (HFONT)ho;
    }
    SendDlgItemMessageA(a1, 128, 0x30u, (WPARAM)v12, 0);
    v13 = IntlLpstrStringOfID(257);
    lstrcpyA(String1, v13);
    v14 = IntlLpstrStringOfID(258);
    lstrcatA(String1, v14);
    v15 = IntlLpstrStringOfID(259);
    lstrcatA(String1, v15);
    SetDlgItemTextA(a1, 128, String1);
    return 1;
  }
  if ( v6 != 1 )
    return 0;
  if ( a3 == 1 || a3 == 2 )
  {
LABEL_29:
    DeleteObject(ho);
    goto LABEL_30;
  }
  if ( a3 != 5301 )
    return 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Shared Tools\\MSInfo", 0, 0x20019u, &hKey) )
  {
    cbData = 2048;
    if ( RegQueryValueExA(hKey, "Path", 0, 0, Data, &cbData) )
    {
      RegCloseKey(hKey);
      goto LABEL_9;
    }
    v7 = (const CHAR *)Data;
    if ( Sys_fWin95Shell )
    {
      GetShortPathNameA((LPCSTR)Data, szShortPath, 0x800u);
      v7 = szShortPath;
    }
    if ( WinExec(v7, 5u) < 0x20 )
      goto LABEL_9;
    return 0;
  }
LABEL_9:
  Error(0xC3AFu);
  return 1;
}

```

## disassembly

```asm
0x180014edc  mov     [rsp-8+arg_8], rbx
0x180014ee1  mov     [rsp-8+arg_10], rsi
0x180014ee6  push    rbp
0x180014ee7  lea     rbp, [rsp-11C0h]
0x180014eef  mov     eax, 12C0h
0x180014ef4  call    _alloca_probe
0x180014ef9  sub     rsp, rax
0x180014efc  mov     rax, cs:__security_cookie
0x180014f03  xor     rax, rsp
0x180014f06  mov     [rbp+11C0h+var_10], rax
0x180014f0d  mov     rbx, rcx
0x180014f10  sub     edx, 10h
0x180014f13  jz      loc_1800151D7
0x180014f19  sub     edx, 43h ; 'C'
0x180014f1c  jz      loc_1800151C6
0x180014f22  sub     edx, 0BDh
0x180014f28  jz      loc_18001501B
0x180014f2e  dec     edx
0x180014f30  jnz     loc_180015014
0x180014f36  cmp     r8, 1
0x180014f3a  jz      loc_1800151D7
0x180014f40  cmp     r8, 2
0x180014f44  jz      loc_1800151D7
0x180014f4a  cmp     r8, 14B5h
0x180014f51  jnz     loc_180015014
0x180014f57  lea     rcx, [rsp+12C0h+hKey]
0x180014f5c  lea     rdx, SubKey; "Software\\Microsoft\\Shared Tools\\MSIn"...
0x180014f63  mov     r9d, 20019h; samDesired
0x180014f69  mov     [rsp+12C0h+phkResult], rcx; phkResult
0x180014f6e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014f75  xor     r8d, r8d; ulOptions
0x180014f78  call    cs:__imp_RegOpenKeyExA
0x180014f7e  test    eax, eax
0x180014f80  jz      short loc_180014F91
0x180014f82  mov     ecx, 0C3AFh; unsigned int
0x180014f87  call    ?Error@@YAXI@Z; Error(uint)
0x180014f8c  jmp     loc_1800151EF
0x180014f91  mov     rcx, [rsp+12C0h+hKey]; hKey
0x180014f96  lea     rax, [rsp+12C0h+cbData]
0x180014f9b  lea     rdx, aPath; "Path"
0x180014fa2  mov     [rsp+12C0h+lpcbData], rax; lpcbData
0x180014fa7  lea     rax, [rbp+11C0h+Data]
0x180014fae  mov     ebx, 800h
0x180014fb3  xor     r9d, r9d; lpType
0x180014fb6  xor     r8d, r8d; lpReserved
0x180014fb9  mov     [rsp+12C0h+phkResult], rax; lpData
0x180014fbe  mov     [rsp+12C0h+cbData], ebx
0x180014fc2  call    cs:__imp_RegQueryValueExA
0x180014fc8  test    eax, eax
0x180014fca  jz      short loc_180014FD9
0x180014fcc  mov     rcx, [rsp+12C0h+hKey]; hKey
0x180014fd1  call    cs:__imp_RegCloseKey
0x180014fd7  jmp     short loc_180014F82
0x180014fd9  cmp     cs:?Sys_fWin95Shell@@3HA, 0; int Sys_fWin95Shell
0x180014fe0  lea     rcx, [rbp+11C0h+Data]; lpszLongPath
0x180014fe7  jz      short loc_180015000
0x180014fe9  lea     rdx, [rbp+11C0h+szShortPath]; lpszShortPath
0x180014ff0  mov     r8d, ebx; cchBuffer
0x180014ff3  call    cs:__imp_GetShortPathNameA
0x180014ff9  lea     rcx, [rbp+11C0h+szShortPath]; lpCmdLine
0x180015000  mov     edx, 5; uCmdShow
0x180015005  call    cs:__imp_WinExec
0x18001500b  cmp     eax, 20h ; ' '
0x18001500e  jb      loc_180014F82
0x180015014  xor     eax, eax
0x180015016  jmp     loc_1800151F4
0x18001501b  call    ?DlgInit@@YAXPEAUHWND__@@@Z; DlgInit(HWND__ *)
0x180015020  mov     ecx, 248h; int
0x180015025  mov     esi, 80h
0x18001502a  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x18001502f  lea     rdx, a1153; "1153"
0x180015036  xor     r9d, r9d; char *
0x180015039  mov     rcx, rax; char *
0x18001503c  lea     rax, [rbp+11C0h+String]
0x180015040  xor     r8d, r8d; char *
0x180015043  mov     word ptr [rsp+12C0h+lpcbData], si; __int16
0x180015048  mov     [rsp+12C0h+phkResult], rax; Destination
0x18001504d  call    ?InsertSzsInBuffer@@YAXPEBD000PEADF@Z; InsertSzsInBuffer(char const *,char const *,char const *,char const *,char *,short)
0x180015052  lea     r8, [rbp+11C0h+String]; lpString
0x180015056  lea     edx, [rsi-0Bh]; nIDDlgItem
0x180015059  mov     rcx, rbx; hDlg
0x18001505c  call    cs:__imp_SetDlgItemTextA
0x180015062  lea     r9, [rsp+12C0h+lParam+4]
0x180015067  lea     r8, [rsp+12C0h+var_1290]
0x18001506c  lea     rdx, [rsp+12C0h+lParam]
0x180015071  lea     rcx, [rsp+12C0h+var_1280]
0x180015076  call    EbGetVersion
0x18001507b  mov     r11d, dword ptr [rsp+12C0h+lParam+4]
0x180015080  and     r11d, 0FFFFFFEFh
0x180015084  jz      short loc_1800150AD
0x180015086  cmp     r11d, 4
0x18001508a  jz      short loc_1800150A4
0x18001508c  lea     r8, aUnknown; "Unknown"
0x180015093  lea     rax, aDebug; "Debug"
0x18001509a  cmp     r11d, 8
0x18001509e  cmovz   r8, rax
0x1800150a2  jmp     short loc_1800150B4
0x1800150a4  lea     r8, aTest_0; "Test"
0x1800150ab  jmp     short loc_1800150B4
0x1800150ad  lea     r8, aRetail; "Retail"
0x1800150b4  mov     eax, [rsp+12C0h+var_1290]
0x1800150b8  mov     r9d, [rsp+12C0h+var_1280]
0x1800150bd  lea     rdx, aVbaSUUU; "VBA: %s %u.%u.%u"
0x1800150c4  mov     dword ptr [rsp+12C0h+lpcbData], eax
0x1800150c8  mov     eax, dword ptr [rsp+12C0h+lParam]
0x1800150cc  lea     rcx, [rbp+11C0h+String]; LPSTR
0x1800150d0  mov     dword ptr [rsp+12C0h+phkResult], eax; lParam
0x1800150d4  call    cs:__imp_wsprintfA
0x1800150da  lea     r8, [rbp+11C0h+String]; lpString
0x1800150de  mov     edx, 76h ; 'v'; nIDDlgItem
0x1800150e3  mov     rcx, rbx; hDlg
0x1800150e6  call    cs:__imp_SetDlgItemTextA
0x1800150ec  mov     rcx, rbx; HWND
0x1800150ef  call    ?GetForms3Version@@YAHPEAUHWND__@@@Z; GetForms3Version(HWND__ *)
0x1800150f4  xor     r9d, r9d; lParam
0x1800150f7  xor     r8d, r8d; wParam
0x1800150fa  lea     edx, [r9+31h]; Msg
0x1800150fe  mov     rcx, rbx; hWnd
0x180015101  call    cs:__imp_SendMessageA
0x180015107  lea     r8, [rsp+12C0h+pv]; pv
0x18001510c  mov     edx, 3Ch ; '<'; c
0x180015111  mov     rcx, rax; h
0x180015114  mov     cs:ho, rax
0x18001511b  call    cs:__imp_GetObjectA
0x180015121  test    eax, eax
0x180015123  jz      short loc_18001514F
0x180015125  lea     rcx, [rsp+12C0h+pv]; lplf
0x18001512a  mov     [rsp+12C0h+var_1260], 190h
0x180015132  mov     [rsp+12C0h+var_1255], 22h ; '"'
0x180015137  call    cs:__imp_CreateFontIndirectA
0x18001513d  mov     cs:ho, rax
0x180015144  test    rax, rax
0x180015147  jz      loc_1800151E4
0x18001514d  jmp     short loc_180015156
0x18001514f  mov     rax, cs:ho
0x180015156  and     [rsp+12C0h+phkResult], 0
0x18001515c  mov     r9, rax; wParam
0x18001515f  mov     r8d, 30h ; '0'; Msg
0x180015165  mov     edx, esi; nIDDlgItem
0x180015167  mov     rcx, rbx; hDlg
0x18001516a  call    cs:__imp_SendDlgItemMessageA
0x180015170  mov     ecx, 101h; int
0x180015175  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x18001517a  lea     rcx, [rbp+11C0h+String1]; lpString1
0x18001517e  mov     rdx, rax; lpString2
0x180015181  call    cs:__imp_lstrcpyA
0x180015187  mov     ecx, 102h; int
0x18001518c  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x180015191  lea     rcx, [rbp+11C0h+String1]; lpString1
0x180015195  mov     rdx, rax; lpString2
0x180015198  call    cs:__imp_lstrcatA
0x18001519e  mov     ecx, 103h; int
0x1800151a3  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800151a8  lea     rcx, [rbp+11C0h+String1]; lpString1
0x1800151ac  mov     rdx, rax; lpString2
0x1800151af  call    cs:__imp_lstrcatA
0x1800151b5  lea     r8, [rbp+11C0h+String1]; lpString
0x1800151b9  mov     edx, esi; nIDDlgItem
0x1800151bb  mov     rcx, rbx; hDlg
0x1800151be  call    cs:__imp_SetDlgItemTextA
0x1800151c4  jmp     short loc_1800151EF
0x1800151c6  mov     edx, 2C310h; int
0x1800151cb  mov     ecx, 1; unsigned int
0x1800151d0  call    ?GetStdHelp@@YAHIJ@Z; GetStdHelp(uint,long)
0x1800151d5  jmp     short loc_1800151EF
0x1800151d7  mov     rcx, cs:ho; ho
0x1800151de  call    cs:__imp_DeleteObject
0x1800151e4  xor     edx, edx; nResult
0x1800151e6  mov     rcx, rbx; hDlg
0x1800151e9  call    cs:__imp_EndDialog
0x1800151ef  mov     eax, 1
0x1800151f4  mov     rcx, [rbp+11C0h+var_10]
0x1800151fb  xor     rcx, rsp; StackCookie
0x1800151fe  call    __security_check_cookie
0x180015203  lea     r11, [rsp+12C0h+var_s0]
0x18001520b  mov     rbx, [r11+18h]
0x18001520f  mov     rsi, [r11+20h]
0x180015213  mov     rsp, r11
0x180015216  pop     rbp
0x180015217  retn
```
