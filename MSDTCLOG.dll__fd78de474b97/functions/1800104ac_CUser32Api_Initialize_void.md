# CUser32Api::Initialize(void)

- ea: `0x1800104ac`
- end: `0x1800106a5`
- name: `?Initialize@CUser32Api@@QEAA_NXZ`
- size: `505`
- prototype: `bool __fastcall(CUser32Api *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010364`

## callees

- `0x1800104ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800104c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800104c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800104e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001051f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001053c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010559`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010593`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010607`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010624`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001063d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010656`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001066f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010688`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800104e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010502`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001051f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001053c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010559`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010593`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010607`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010624`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001063d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010656`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001066f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010688`

## string_xrefs

- `0x1800104c0`: `user32.dll`
- `0x180010600`: `OpenWindowStationW`
- `0x180010636`: `GetThreadDesktop`
- `0x18001064f`: `SetThreadDesktop`
- `0x180010668`: `OpenDesktopW`

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
0x1800104ac  push    rbx
0x1800104ae  sub     rsp, 20h
0x1800104b2  mov     rax, [rcx]
0x1800104b5  mov     rbx, rcx
0x1800104b8  test    rax, rax
0x1800104bb  jnz     short loc_1800104DB
0x1800104bd  xor     r8d, r8d; dwFlags
0x1800104c0  lea     rcx, aUser32Dll; "user32.dll"
0x1800104c7  xor     edx, edx; hFile
0x1800104c9  call    cs:__imp_LoadLibraryExW
0x1800104cf  mov     [rbx], rax
0x1800104d2  test    rax, rax
0x1800104d5  jz      loc_18001069D
0x1800104db  lea     rdx, aDialogboxparam; "DialogBoxParamW"
0x1800104e2  mov     rcx, rax; hModule
0x1800104e5  call    cs:__imp_GetProcAddress
0x1800104eb  mov     [rbx+8], rax
0x1800104ef  test    rax, rax
0x1800104f2  jz      loc_18001069D
0x1800104f8  mov     rcx, [rbx]; hModule
0x1800104fb  lea     rdx, aSetdlgitemtext; "SetDlgItemTextW"
0x180010502  call    cs:__imp_GetProcAddress
0x180010508  mov     [rbx+10h], rax
0x18001050c  test    rax, rax
0x18001050f  jz      loc_18001069D
0x180010515  mov     rcx, [rbx]; hModule
0x180010518  lea     rdx, aEnddialog; "EndDialog"
0x18001051f  call    cs:__imp_GetProcAddress
0x180010525  mov     [rbx+18h], rax
0x180010529  test    rax, rax
0x18001052c  jz      loc_18001069D
0x180010532  mov     rcx, [rbx]; hModule
0x180010535  lea     rdx, aGetdesktopwind; "GetDesktopWindow"
0x18001053c  call    cs:__imp_GetProcAddress
0x180010542  mov     [rbx+20h], rax
0x180010546  test    rax, rax
0x180010549  jz      loc_18001069D
0x18001054f  mov     rcx, [rbx]; hModule
0x180010552  lea     rdx, aGetwindowrect; "GetWindowRect"
0x180010559  call    cs:__imp_GetProcAddress
0x18001055f  mov     [rbx+28h], rax
0x180010563  test    rax, rax
0x180010566  jz      loc_18001069D
0x18001056c  mov     rcx, [rbx]; hModule
0x18001056f  lea     rdx, aGetclientrect; "GetClientRect"
0x180010576  call    cs:__imp_GetProcAddress
0x18001057c  mov     [rbx+30h], rax
0x180010580  test    rax, rax
0x180010583  jz      loc_18001069D
0x180010589  mov     rcx, [rbx]; hModule
0x18001058c  lea     rdx, aMapwindowpoint; "MapWindowPoints"
0x180010593  call    cs:__imp_GetProcAddress
0x180010599  mov     [rbx+38h], rax
0x18001059d  test    rax, rax
0x1800105a0  jz      loc_18001069D
0x1800105a6  mov     rcx, [rbx]; hModule
0x1800105a9  lea     rdx, aSetwindowpos; "SetWindowPos"
0x1800105b0  call    cs:__imp_GetProcAddress
0x1800105b6  mov     [rbx+40h], rax
0x1800105ba  test    rax, rax
0x1800105bd  jz      loc_18001069D
0x1800105c3  mov     rcx, [rbx]; hModule
0x1800105c6  lea     rdx, aGetprocesswind; "GetProcessWindowStation"
0x1800105cd  call    cs:__imp_GetProcAddress
0x1800105d3  mov     [rbx+48h], rax
0x1800105d7  test    rax, rax
0x1800105da  jz      loc_18001069D
0x1800105e0  mov     rcx, [rbx]; hModule
0x1800105e3  lea     rdx, aSetprocesswind; "SetProcessWindowStation"
0x1800105ea  call    cs:__imp_GetProcAddress
0x1800105f0  mov     [rbx+50h], rax
0x1800105f4  test    rax, rax
0x1800105f7  jz      loc_18001069D
0x1800105fd  mov     rcx, [rbx]; hModule
0x180010600  lea     rdx, aOpenwindowstat; "OpenWindowStationW"
0x180010607  call    cs:__imp_GetProcAddress
0x18001060d  mov     [rbx+58h], rax
0x180010611  test    rax, rax
0x180010614  jz      loc_18001069D
0x18001061a  mov     rcx, [rbx]; hModule
0x18001061d  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x180010624  call    cs:__imp_GetProcAddress
0x18001062a  mov     [rbx+60h], rax
0x18001062e  test    rax, rax
0x180010631  jz      short loc_18001069D
0x180010633  mov     rcx, [rbx]; hModule
0x180010636  lea     rdx, aGetthreaddeskt; "GetThreadDesktop"
0x18001063d  call    cs:__imp_GetProcAddress
0x180010643  mov     [rbx+68h], rax
0x180010647  test    rax, rax
0x18001064a  jz      short loc_18001069D
0x18001064c  mov     rcx, [rbx]; hModule
0x18001064f  lea     rdx, aSetthreaddeskt; "SetThreadDesktop"
0x180010656  call    cs:__imp_GetProcAddress
0x18001065c  mov     [rbx+70h], rax
0x180010660  test    rax, rax
0x180010663  jz      short loc_18001069D
0x180010665  mov     rcx, [rbx]; hModule
0x180010668  lea     rdx, aOpendesktopw; "OpenDesktopW"
0x18001066f  call    cs:__imp_GetProcAddress
0x180010675  mov     [rbx+78h], rax
0x180010679  test    rax, rax
0x18001067c  jz      short loc_18001069D
0x18001067e  mov     rcx, [rbx]; hModule
0x180010681  lea     rdx, aClosedesktop; "CloseDesktop"
0x180010688  call    cs:__imp_GetProcAddress
0x18001068e  test    rax, rax
0x180010691  mov     [rbx+80h], rax
0x180010698  setnz   al
0x18001069b  jmp     short loc_18001069F
0x18001069d  xor     al, al
0x18001069f  add     rsp, 20h
0x1800106a3  pop     rbx
0x1800106a4  retn
```
