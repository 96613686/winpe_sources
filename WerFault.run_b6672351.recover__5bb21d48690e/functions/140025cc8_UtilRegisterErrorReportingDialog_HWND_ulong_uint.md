# UtilRegisterErrorReportingDialog(HWND__ *,ulong,uint *)

- ea: `0x140025cc8`
- end: `0x140025df2`
- name: `?UtilRegisterErrorReportingDialog@@YAHPEAUHWND__@@KPEAI@Z`
- size: `298`
- prototype: `__int64 __fastcall(HWND hwnd, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400271e0`
- `0x14002adb8`

## callees

- `0x1400036b8`
- `0x140003798`
- `0x140025cc8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140025dd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140025dd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140025d95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140025d95`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140025d24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140025d24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025d42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025d42`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x140025d79`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x140025d79`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140025d57`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140025d57`

## string_xrefs

- `0x140025d1d`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilRegisterErrorReportingDialog(HWND hwnd, unsigned int a2, unsigned int *a3)
{
  HMODULE Library; // rbx
  DWORD v7; // ecx
  unsigned int v8; // edi
  UINT v9; // eax
  unsigned int v10; // ebp
  FARPROC ProcAddress; // rax

  if ( !hwnd || !a2 )
  {
    v8 = 0;
    goto LABEL_19;
  }
  if ( a3 )
    *a3 = 0;
  if ( !(unsigned __int8)IsRegisterWindowMessageWPresent() || !(unsigned __int8)IsChangeWindowMessageFilterExPresent() )
  {
    v7 = 127;
    goto LABEL_9;
  }
  Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
  if ( !Library )
  {
    v7 = 126;
LABEL_9:
    v8 = 0;
    SetLastError(v7);
LABEL_19:
    Library = 0;
    goto LABEL_20;
  }
  v9 = RegisterWindowMessageW(L"WerHangRepMessage");
  v10 = v9;
  if ( !v9 )
    goto LABEL_11;
  v8 = ChangeWindowMessageFilterEx(hwnd, v9, 1u, 0);
  if ( !v8 )
    goto LABEL_20;
  ProcAddress = GetProcAddress(Library, "RegisterErrorReportingDialog");
  if ( !ProcAddress )
  {
LABEL_11:
    v8 = 0;
    goto LABEL_20;
  }
  v8 = ((__int64 (__fastcall *)(HWND, _QWORD))ProcAddress)(hwnd, a2);
  if ( v8 && a3 )
    *a3 = v10;
LABEL_20:
  if ( Library )
    FreeLibrary(Library);
  return v8;
}

```

## disassembly

```asm
0x140025cc8  push    rbx
0x140025cca  push    rbp
0x140025ccb  push    rsi
0x140025ccc  push    rdi
0x140025ccd  push    r14
0x140025ccf  push    r15
0x140025cd1  sub     rsp, 28h
0x140025cd5  mov     rsi, r8
0x140025cd8  mov     r15d, edx
0x140025cdb  mov     r14, rcx
0x140025cde  test    rcx, rcx
0x140025ce1  jz      loc_140025DCA
0x140025ce7  test    edx, edx
0x140025ce9  jz      loc_140025DCA
0x140025cef  test    r8, r8
0x140025cf2  jz      short loc_140025CFB
0x140025cf4  mov     dword ptr [r8], 0
0x140025cfb  call    IsRegisterWindowMessageWPresent
0x140025d00  test    al, al
0x140025d02  jz      loc_140025DC0
0x140025d08  call    IsChangeWindowMessageFilterExPresent
0x140025d0d  test    al, al
0x140025d0f  jz      loc_140025DC0
0x140025d15  xor     edx, edx; hFile
0x140025d17  mov     r8d, 800h; dwFlags
0x140025d1d  lea     rcx, aUser32Dll; "user32.dll"
0x140025d24  call    cs:__imp_LoadLibraryExW
0x140025d2b  nop     dword ptr [rax+rax+00h]
0x140025d30  mov     rbx, rax
0x140025d33  mov     [rsp+58h+arg_0], rax
0x140025d38  test    rax, rax
0x140025d3b  jnz     short loc_140025D50
0x140025d3d  lea     ecx, [rax+7Eh]; dwErrCode
0x140025d40  xor     edi, edi
0x140025d42  call    cs:__imp_SetLastError
0x140025d49  nop     dword ptr [rax+rax+00h]
0x140025d4e  jmp     short loc_140025DCC
0x140025d50  lea     rcx, String; "WerHangRepMessage"
0x140025d57  call    cs:__imp_RegisterWindowMessageW
0x140025d5e  nop     dword ptr [rax+rax+00h]
0x140025d63  mov     ebp, eax
0x140025d65  test    eax, eax
0x140025d67  jnz     short loc_140025D6D
0x140025d69  xor     edi, edi
0x140025d6b  jmp     short loc_140025DCE
0x140025d6d  xor     r9d, r9d; pChangeFilterStruct
0x140025d70  lea     r8d, [r9+1]; action
0x140025d74  mov     edx, ebp; message
0x140025d76  mov     rcx, r14; hwnd
0x140025d79  call    cs:__imp_ChangeWindowMessageFilterEx
0x140025d80  nop     dword ptr [rax+rax+00h]
0x140025d85  mov     edi, eax
0x140025d87  test    eax, eax
0x140025d89  jz      short loc_140025DCE
0x140025d8b  lea     rdx, aRegistererrorr; "RegisterErrorReportingDialog"
0x140025d92  mov     rcx, rbx; hModule
0x140025d95  call    cs:__imp_GetProcAddress
0x140025d9c  nop     dword ptr [rax+rax+00h]
0x140025da1  test    rax, rax
0x140025da4  jz      short loc_140025D69
0x140025da6  mov     edx, r15d
0x140025da9  mov     rcx, r14
0x140025dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025db1  mov     edi, eax
0x140025db3  test    eax, eax
0x140025db5  jz      short loc_140025DCE
0x140025db7  test    rsi, rsi
0x140025dba  jz      short loc_140025DCE
0x140025dbc  mov     [rsi], ebp
0x140025dbe  jmp     short loc_140025DCE
0x140025dc0  mov     ecx, 7Fh
0x140025dc5  jmp     loc_140025D40
0x140025dca  xor     edi, edi
0x140025dcc  xor     ebx, ebx
0x140025dce  test    rbx, rbx
0x140025dd1  jz      short loc_140025DE2
0x140025dd3  mov     rcx, rbx; hLibModule
0x140025dd6  call    cs:__imp_FreeLibrary
0x140025ddd  nop     dword ptr [rax+rax+00h]
0x140025de2  mov     eax, edi
0x140025de4  add     rsp, 28h
0x140025de8  pop     r15
0x140025dea  pop     r14
0x140025dec  pop     rdi
0x140025ded  pop     rsi
0x140025dee  pop     rbp
0x140025def  pop     rbx
0x140025df0  retn
```
