# CStartupImpactHelper::GetSIFileNames(void)

- ea: `0x1800d9908`
- end: `0x1800d9b13`
- name: `?GetSIFileNames@CStartupImpactHelper@@AEAAJXZ`
- size: `523`
- prototype: `__int64 __fastcall(CStartupImpactHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d9b1c`

## callees

- `0x180006e50`
- `0x18000f07c`
- `0x1800d02bc`
- `0x1800d9834`
- `0x1800d9908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d9ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d9ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d9ad0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d99b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9ab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d99b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9ab2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9a56`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d9a56`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9a43`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9a43`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800d9a73`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800d9a73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800d9a2c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800d9a2c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d9a12`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d9a12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9ae0`

## string_xrefs

- `0x1800d9983`: `%WINDIR%\system32\WDI\LogFiles\StartupInfo\%s_StartupInfo%d.xml`

## pseudocode

```c
__int64 __fastcall CStartupImpactHelper::GetSIFileNames(CStartupImpactHelper *this)
{
  FILETIME *v1; // r12
  int CurrentUserSidStr; // ebx
  __int64 FileW; // rdi
  int i; // r14d
  OLECHAR *v6; // rcx
  BSTR v7; // rax
  HANDLE ProcessHeap; // rax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime1[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+70h] [rbp-90h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  lpMem = 0;
  hMem = 0;
  v1 = (FILETIME *)((char *)this + 72);
  v15 = 0;
  *((_QWORD *)this + 9) = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  CurrentUserSidStr = CStartupImpactHelper::GetCurrentUserSidStr(this, (unsigned __int16 **)&hMem);
  if ( CurrentUserSidStr >= 0 )
  {
    CurrentUserSidStr = TmExpandEnvironmentVariables(
                          L"%WINDIR%\\system32\\WDI\\LogFiles\\StartupInfo\\%s_StartupInfo%d.xml",
                          (unsigned __int16 **)&lpMem);
    if ( CurrentUserSidStr >= 0 )
    {
      FileW = -1;
      for ( i = 0; i < 5; ++i )
      {
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle((HANDLE)FileW);
          FileW = 0;
        }
        LODWORD(dwCreationDisposition) = i + 1;
        CurrentUserSidStr = StringCchPrintfW(
                              FileName,
                              0x104u,
                              (const unsigned __int16 *)lpMem,
                              hMem,
                              dwCreationDisposition);
        if ( CurrentUserSidStr < 0 )
          goto LABEL_19;
        FileW = (__int64)CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
        if ( FileW != -1 && GetFileAttributesExW(FileName, GetFileExInfoStandard, &FileInformation) )
        {
          v6 = (OLECHAR *)*((_QWORD *)this + i + 3);
          if ( v6 )
          {
            SysFreeString(v6);
            *((_QWORD *)this + i + 3) = 0;
          }
          v7 = SysAllocString(FileName);
          if ( !v7 )
          {
            CurrentUserSidStr = -2147024882;
            goto LABEL_19;
          }
          *((_QWORD *)this + i + 3) = v7;
          ++*((_DWORD *)this + 16);
          CurrentUserSidStr = 0;
          if ( CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, v1) > 0 )
          {
            *v1 = *(FILETIME *)&FileTime1[0].dwHighDateTime;
            *((_DWORD *)this + 17) = i;
          }
        }
      }
      if ( !*((_DWORD *)this + 16) )
        CurrentUserSidStr = 1;
LABEL_19:
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)FileW);
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)CurrentUserSidStr;
}

```

## disassembly

```asm
0x1800d9908  mov     [rsp-8+arg_8], rbx
0x1800d990d  mov     [rsp-8+arg_10], rsi
0x1800d9912  push    rbp
0x1800d9913  push    rdi
0x1800d9914  push    r12
0x1800d9916  push    r13
0x1800d9918  push    r14
0x1800d991a  lea     rbp, [rsp-1A0h]
0x1800d9922  sub     rsp, 2A0h
0x1800d9929  mov     rax, cs:__security_cookie
0x1800d9930  xor     rax, rsp
0x1800d9933  mov     [rbp+1C0h+var_30], rax
0x1800d993a  xorps   xmm0, xmm0
0x1800d993d  mov     [rsp+2C0h+lpMem], 0
0x1800d9946  xor     eax, eax
0x1800d9948  mov     [rsp+2C0h+hMem], 0
0x1800d9951  lea     r12, [rcx+48h]
0x1800d9955  mov     [rsp+2C0h+var_250], eax
0x1800d9959  lea     rdx, [rsp+2C0h+hMem]; unsigned __int16 **
0x1800d995e  mov     [r12], rax
0x1800d9962  movups  [rsp+2C0h+FileInformation], xmm0
0x1800d9967  mov     rsi, rcx
0x1800d996a  movups  xmmword ptr [rsp+2C0h+FileTime1.dwLowDateTime], xmm0
0x1800d996f  call    ?GetCurrentUserSidStr@CStartupImpactHelper@@AEAAJPEAPEAG@Z; CStartupImpactHelper::GetCurrentUserSidStr(ushort * *)
0x1800d9974  mov     ebx, eax
0x1800d9976  test    eax, eax
0x1800d9978  js      loc_1800D9AD6
0x1800d997e  lea     rdx, [rsp+2C0h+lpMem]; unsigned __int16 **
0x1800d9983  lea     rcx, aWindirSystem32_0; "%WINDIR%\\system32\\WDI\\LogFiles\\Star"...
0x1800d998a  call    ?TmExpandEnvironmentVariables@@YAJPEBGPEAPEAG@Z; TmExpandEnvironmentVariables(ushort const *,ushort * *)
0x1800d998f  mov     ebx, eax
0x1800d9991  test    eax, eax
0x1800d9993  js      loc_1800D9AB8
0x1800d9999  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d999d  xor     r14d, r14d
0x1800d99a0  cmp     r14d, 5
0x1800d99a4  jge     loc_1800D9A99
0x1800d99aa  lea     rax, [rdi-1]
0x1800d99ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d99b2  ja      short loc_1800D99BF
0x1800d99b4  mov     rcx, rdi; hObject
0x1800d99b7  call    cs:__imp_CloseHandle
0x1800d99bd  xor     edi, edi
0x1800d99bf  mov     r9, [rsp+2C0h+hMem]
0x1800d99c4  lea     r13d, [r14+1]
0x1800d99c8  mov     r8, [rsp+2C0h+lpMem]; unsigned __int16 *
0x1800d99cd  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x1800d99d1  mov     edx, 104h; unsigned __int64
0x1800d99d6  mov     dword ptr [rsp+2C0h+dwCreationDisposition], r13d
0x1800d99db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d99e0  mov     ebx, eax
0x1800d99e2  test    eax, eax
0x1800d99e4  js      loc_1800D9AA5
0x1800d99ea  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800d99f3  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x1800d99f7  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d99ff  xor     r9d, r9d; lpSecurityAttributes
0x1800d9a02  xor     r8d, r8d; dwShareMode
0x1800d9a05  mov     dword ptr [rsp+2C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800d9a0d  mov     edx, 80000000h; dwDesiredAccess
0x1800d9a12  call    cs:__imp_CreateFileW
0x1800d9a18  mov     rdi, rax
0x1800d9a1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d9a1f  jz      short loc_1800D9A8A
0x1800d9a21  lea     r8, [rsp+2C0h+FileInformation]; lpFileInformation
0x1800d9a26  xor     edx, edx; fInfoLevelId
0x1800d9a28  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x1800d9a2c  call    cs:__imp_GetFileAttributesExW
0x1800d9a32  test    eax, eax
0x1800d9a34  jz      short loc_1800D9A8A
0x1800d9a36  movsxd  rbx, r14d
0x1800d9a39  mov     rcx, [rsi+rbx*8+18h]; bstrString
0x1800d9a3e  test    rcx, rcx
0x1800d9a41  jz      short loc_1800D9A52
0x1800d9a43  call    cs:__imp_SysFreeString
0x1800d9a49  mov     qword ptr [rsi+rbx*8+18h], 0
0x1800d9a52  lea     rcx, [rbp+1C0h+FileName]; psz
0x1800d9a56  call    cs:__imp_SysAllocString
0x1800d9a5c  test    rax, rax
0x1800d9a5f  jz      short loc_1800D9A92
0x1800d9a61  mov     [rsi+rbx*8+18h], rax
0x1800d9a66  inc     dword ptr [rsi+40h]
0x1800d9a69  lea     rcx, [rsp+2C0h+FileTime1.dwHighDateTime]; lpFileTime1
0x1800d9a6e  mov     rdx, r12; lpFileTime2
0x1800d9a71  xor     ebx, ebx
0x1800d9a73  call    cs:__imp_CompareFileTime
0x1800d9a79  test    eax, eax
0x1800d9a7b  jle     short loc_1800D9A8A
0x1800d9a7d  mov     rax, qword ptr [rsp+2C0h+FileTime1.dwHighDateTime]
0x1800d9a82  mov     [r12], rax
0x1800d9a86  mov     [rsi+44h], r14d
0x1800d9a8a  mov     r14d, r13d
0x1800d9a8d  jmp     loc_1800D99A0
0x1800d9a92  mov     ebx, 8007000Eh
0x1800d9a97  jmp     short loc_1800D9AA5
0x1800d9a99  cmp     dword ptr [rsi+40h], 0
0x1800d9a9d  mov     eax, 1
0x1800d9aa2  cmovz   ebx, eax
0x1800d9aa5  lea     rax, [rdi-1]
0x1800d9aa9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d9aad  ja      short loc_1800D9AB8
0x1800d9aaf  mov     rcx, rdi; hObject
0x1800d9ab2  call    cs:__imp_CloseHandle
0x1800d9ab8  cmp     [rsp+2C0h+lpMem], 0
0x1800d9abe  jz      short loc_1800D9AD6
0x1800d9ac0  call    cs:__imp_GetProcessHeap
0x1800d9ac6  mov     r8, [rsp+2C0h+lpMem]; lpMem
0x1800d9acb  xor     edx, edx; dwFlags
0x1800d9acd  mov     rcx, rax; hHeap
0x1800d9ad0  call    cs:__imp_HeapFree
0x1800d9ad6  mov     rcx, [rsp+2C0h+hMem]; hMem
0x1800d9adb  test    rcx, rcx
0x1800d9ade  jz      short loc_1800D9AE6
0x1800d9ae0  call    cs:__imp_LocalFree
0x1800d9ae6  mov     eax, ebx
0x1800d9ae8  mov     rcx, [rbp+1C0h+var_30]
0x1800d9aef  xor     rcx, rsp; StackCookie
0x1800d9af2  call    __security_check_cookie
0x1800d9af7  lea     r11, [rsp+2C0h+var_20]
0x1800d9aff  mov     rbx, [r11+38h]
0x1800d9b03  mov     rsi, [r11+40h]
0x1800d9b07  mov     rsp, r11
0x1800d9b0a  pop     r14
0x1800d9b0c  pop     r13
0x1800d9b0e  pop     r12
0x1800d9b10  pop     rdi
0x1800d9b11  pop     rbp
0x1800d9b12  retn
```
