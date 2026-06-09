# CUser32Api::Initialize(void)

- ea: `0x1800427e0`
- end: `0x1800429d9`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004269c`

## callees

- `0x1800427e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800427fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800427fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004288d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042901`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004291e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004293b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042971`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004298a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004288d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042901`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004291e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004293b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042971`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004298a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429bc`

## string_xrefs

- `0x1800427f4`: `user32.dll`
- `0x180042934`: `OpenWindowStationW`
- `0x18004296a`: `GetThreadDesktop`
- `0x180042983`: `SetThreadDesktop`
- `0x18004299c`: `OpenDesktopW`

## pseudocode

```c
bool __fastcall CUser32Api::Initialize(HMODULE *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax

  Library = *this;
  if ( !*this )
  {
    Library = LoadLibraryExW(L"user32.dll", 0, 0);
    *this = Library;
    if ( !Library )
      return 0;
  }
  ProcAddress = GetProcAddress(Library, "DialogBoxParamW");
  this[1] = (HMODULE)ProcAddress;
  if ( !ProcAddress )
    return 0;
  v4 = GetProcAddress(*this, "SetDlgItemTextW");
  this[2] = (HMODULE)v4;
  if ( !v4 )
    return 0;
  v5 = GetProcAddress(*this, "EndDialog");
  this[3] = (HMODULE)v5;
  if ( !v5 )
    return 0;
  v6 = GetProcAddress(*this, "GetDesktopWindow");
  this[4] = (HMODULE)v6;
  if ( !v6 )
    return 0;
  v7 = GetProcAddress(*this, "GetWindowRect");
  this[5] = (HMODULE)v7;
  if ( !v7 )
    return 0;
  v8 = GetProcAddress(*this, "GetClientRect");
  this[6] = (HMODULE)v8;
  if ( !v8 )
    return 0;
  v9 = GetProcAddress(*this, "MapWindowPoints");
  this[7] = (HMODULE)v9;
  if ( !v9 )
    return 0;
  v10 = GetProcAddress(*this, "SetWindowPos");
  this[8] = (HMODULE)v10;
  if ( !v10 )
    return 0;
  v11 = GetProcAddress(*this, "GetProcessWindowStation");
  this[9] = (HMODULE)v11;
  if ( !v11 )
    return 0;
  v12 = GetProcAddress(*this, "SetProcessWindowStation");
  this[10] = (HMODULE)v12;
  if ( !v12 )
    return 0;
  v13 = GetProcAddress(*this, "OpenWindowStationW");
  this[11] = (HMODULE)v13;
  if ( !v13 )
    return 0;
  v14 = GetProcAddress(*this, "CloseWindowStation");
  this[12] = (HMODULE)v14;
  if ( !v14 )
    return 0;
  v15 = GetProcAddress(*this, "GetThreadDesktop");
  this[13] = (HMODULE)v15;
  if ( !v15 )
    return 0;
  v16 = GetProcAddress(*this, "SetThreadDesktop");
  this[14] = (HMODULE)v16;
  if ( !v16 )
    return 0;
  v17 = GetProcAddress(*this, "OpenDesktopW");
  this[15] = (HMODULE)v17;
  if ( !v17 )
    return 0;
  v18 = GetProcAddress(*this, "CloseDesktop");
  this[16] = (HMODULE)v18;
  return v18 != 0;
}

```

## disassembly

```asm
0x1800427e0  push    rbx
0x1800427e2  sub     rsp, 20h
0x1800427e6  mov     rax, [rcx]
0x1800427e9  mov     rbx, rcx
0x1800427ec  test    rax, rax
0x1800427ef  jnz     short loc_18004280F
0x1800427f1  xor     r8d, r8d; dwFlags
0x1800427f4  lea     rcx, aUser32Dll; "user32.dll"
0x1800427fb  xor     edx, edx; hFile
0x1800427fd  call    cs:__imp_LoadLibraryExW
0x180042803  mov     [rbx], rax
0x180042806  test    rax, rax
0x180042809  jz      loc_1800429D1
0x18004280f  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x180042816  mov     rcx, rax; hModule
0x180042819  call    cs:__imp_GetProcAddress
0x18004281f  mov     [rbx+8], rax
0x180042823  test    rax, rax
0x180042826  jz      loc_1800429D1
0x18004282c  mov     rcx, [rbx]; hModule
0x18004282f  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x180042836  call    cs:__imp_GetProcAddress
0x18004283c  mov     [rbx+10h], rax
0x180042840  test    rax, rax
0x180042843  jz      loc_1800429D1
0x180042849  mov     rcx, [rbx]; hModule
0x18004284c  lea     rdx, aEnddialog; "EndDialog"
0x180042853  call    cs:__imp_GetProcAddress
0x180042859  mov     [rbx+18h], rax
0x18004285d  test    rax, rax
0x180042860  jz      loc_1800429D1
0x180042866  mov     rcx, [rbx]; hModule
0x180042869  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x180042870  call    cs:__imp_GetProcAddress
0x180042876  mov     [rbx+20h], rax
0x18004287a  test    rax, rax
0x18004287d  jz      loc_1800429D1
0x180042883  mov     rcx, [rbx]; hModule
0x180042886  lea     rdx, aGetwindowrect; "GetWindowRect"
0x18004288d  call    cs:__imp_GetProcAddress
0x180042893  mov     [rbx+28h], rax
0x180042897  test    rax, rax
0x18004289a  jz      loc_1800429D1
0x1800428a0  mov     rcx, [rbx]; hModule
0x1800428a3  lea     rdx, aGetclientrect; "GetClientRect"
0x1800428aa  call    cs:__imp_GetProcAddress
0x1800428b0  mov     [rbx+30h], rax
0x1800428b4  test    rax, rax
0x1800428b7  jz      loc_1800429D1
0x1800428bd  mov     rcx, [rbx]; hModule
0x1800428c0  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x1800428c7  call    cs:__imp_GetProcAddress
0x1800428cd  mov     [rbx+38h], rax
0x1800428d1  test    rax, rax
0x1800428d4  jz      loc_1800429D1
0x1800428da  mov     rcx, [rbx]; hModule
0x1800428dd  lea     rdx, aSetwindowpos; "SetWindowPos"
0x1800428e4  call    cs:__imp_GetProcAddress
0x1800428ea  mov     [rbx+40h], rax
0x1800428ee  test    rax, rax
0x1800428f1  jz      loc_1800429D1
0x1800428f7  mov     rcx, [rbx]; hModule
0x1800428fa  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x180042901  call    cs:__imp_GetProcAddress
0x180042907  mov     [rbx+48h], rax
0x18004290b  test    rax, rax
0x18004290e  jz      loc_1800429D1
0x180042914  mov     rcx, [rbx]; hModule
0x180042917  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x18004291e  call    cs:__imp_GetProcAddress
0x180042924  mov     [rbx+50h], rax
0x180042928  test    rax, rax
0x18004292b  jz      loc_1800429D1
0x180042931  mov     rcx, [rbx]; hModule
0x180042934  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x18004293b  call    cs:__imp_GetProcAddress
0x180042941  mov     [rbx+58h], rax
0x180042945  test    rax, rax
0x180042948  jz      loc_1800429D1
0x18004294e  mov     rcx, [rbx]; hModule
0x180042951  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x180042958  call    cs:__imp_GetProcAddress
0x18004295e  mov     [rbx+60h], rax
0x180042962  test    rax, rax
0x180042965  jz      short loc_1800429D1
0x180042967  mov     rcx, [rbx]; hModule
0x18004296a  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x180042971  call    cs:__imp_GetProcAddress
0x180042977  mov     [rbx+68h], rax
0x18004297b  test    rax, rax
0x18004297e  jz      short loc_1800429D1
0x180042980  mov     rcx, [rbx]; hModule
0x180042983  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x18004298a  call    cs:__imp_GetProcAddress
0x180042990  mov     [rbx+70h], rax
0x180042994  test    rax, rax
0x180042997  jz      short loc_1800429D1
0x180042999  mov     rcx, [rbx]; hModule
0x18004299c  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x1800429a3  call    cs:__imp_GetProcAddress
0x1800429a9  mov     [rbx+78h], rax
0x1800429ad  test    rax, rax
0x1800429b0  jz      short loc_1800429D1
0x1800429b2  mov     rcx, [rbx]; hModule
0x1800429b5  lea     rdx, aClosedesktop; "CloseDesktop"
0x1800429bc  call    cs:__imp_GetProcAddress
0x1800429c2  test    rax, rax
0x1800429c5  mov     [rbx+80h], rax
0x1800429cc  setnz   al
0x1800429cf  jmp     short loc_1800429D3
0x1800429d1  xor     al, al
0x1800429d3  add     rsp, 20h
0x1800429d7  pop     rbx
0x1800429d8  retn
```
