# CheckSogouIME(int *,ushort const *,ushort const *,void *)

- ea: `0x180036bb0`
- end: `0x180036cd1`
- name: `?CheckSogouIME@@YAJPEAHPEBG1PEAX@Z`
- size: `289`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180001cf0`
- `0x180036bb0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180036c33`
- `KERNEL32!CreateFileW` at `0x180036c33`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180036bea`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180036bea`
- `KERNEL32!CloseHandle` at `0x180036ca6`
- `KERNEL32!CloseHandle` at `0x180036ca6`
- `KERNEL32!GetLastError` at `0x180036bf4`
- `KERNEL32!GetLastError` at `0x180036c3f`
- `KERNEL32!GetLastError` at `0x180036bf4`
- `KERNEL32!GetLastError` at `0x180036c3f`

## string_xrefs

- `0x180036c00`: `Failed to expand setup binary path. %d`

## pseudocode

```c
__int64 __fastcall CheckSogouIME(int *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, void *a4)
{
  DWORD LastError; // eax
  __int64 v6; // r8
  const char *v7; // r9
  HANDLE FileW; // rax
  int v9; // ebx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-248h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-228h] BYREF

  *a1 = 0;
  if ( ExpandEnvironmentStringsW(L"%windir%\\syswow64\\ime\\sogoupy\\SogouWin10Setup.exe", Dst, 0x103u) )
  {
    FileW = CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandle(FileW);
      return 0;
    }
    LastError = GetLastError();
    v6 = 239;
    v7 = "Failed to find the setup binary. %d";
  }
  else
  {
    LastError = GetLastError();
    v6 = 225;
    v7 = "Failed to expand setup binary path. %d";
  }
  v9 = LastError;
  LODWORD(dwCreationDisposition) = LastError;
  AslLogCallPrintf(1, "CSogouIMEShim::IsSetupBinaryPresent", v6, v7, dwCreationDisposition);
  if ( v9 )
  {
    AslLogCallPrintf(1, "CheckSogouIME", 89, "sogouIMEShim setup binary not found [%d]", v9);
    *a1 = 1;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180036bb0  mov     [rsp+arg_8], rbx
0x180036bb5  push    rsi
0x180036bb6  sub     rsp, 260h
0x180036bbd  mov     rax, cs:__security_cookie
0x180036bc4  xor     rax, rsp
0x180036bc7  mov     [rsp+268h+var_18], rax
0x180036bcf  mov     rsi, rcx
0x180036bd2  mov     dword ptr [rcx], 0
0x180036bd8  lea     rcx, aWindirSyswow64; "%windir%\\syswow64\\ime\\sogoupy\\Sogou"...
0x180036bdf  mov     r8d, 103h; nSize
0x180036be5  lea     rdx, [rsp+268h+Dst]; lpDst
0x180036bea  call    cs:__imp_ExpandEnvironmentStringsW
0x180036bf0  test    eax, eax
0x180036bf2  jnz     short loc_180036C09
0x180036bf4  call    cs:__imp_GetLastError
0x180036bfa  mov     r8d, 0E1h
0x180036c00  lea     r9, aFailedToExpand_1; "Failed to expand setup binary path. %d"
0x180036c07  jmp     short loc_180036C52
0x180036c09  xor     r9d, r9d; lpSecurityAttributes
0x180036c0c  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180036c15  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180036c1d  lea     rcx, [rsp+268h+Dst]; lpFileName
0x180036c22  mov     edx, 80000000h; dwDesiredAccess
0x180036c27  mov     dword ptr [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x180036c2f  lea     r8d, [r9+1]; dwShareMode
0x180036c33  call    cs:__imp_CreateFileW
0x180036c39  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036c3d  jnz     short loc_180036CA3
0x180036c3f  call    cs:__imp_GetLastError
0x180036c45  mov     r8d, 0EFh
0x180036c4b  lea     r9, aFailedToFindTh; "Failed to find the setup binary. %d"
0x180036c52  lea     rdx, aCsogouimeshimI; "CSogouIMEShim::IsSetupBinaryPresent"
0x180036c59  mov     ecx, 1
0x180036c5e  mov     ebx, eax
0x180036c60  mov     dword ptr [rsp+268h+dwCreationDisposition], eax
0x180036c64  call    AslLogCallPrintf
0x180036c69  test    ebx, ebx
0x180036c6b  jz      short loc_180036CAE
0x180036c6d  mov     r8d, 59h ; 'Y'
0x180036c73  mov     dword ptr [rsp+268h+dwCreationDisposition], ebx
0x180036c77  lea     r9, aSogouimeshimSe; "sogouIMEShim setup binary not found [%d"...
0x180036c7e  lea     rdx, aChecksogouime; "CheckSogouIME"
0x180036c85  lea     ecx, [r8-58h]
0x180036c89  call    AslLogCallPrintf
0x180036c8e  mov     dword ptr [rsi], 1
0x180036c94  test    ebx, ebx
0x180036c96  jle     short loc_180036CAE
0x180036c98  movzx   ebx, bx
0x180036c9b  or      ebx, 80070000h
0x180036ca1  jmp     short loc_180036CAE
0x180036ca3  mov     rcx, rax; hObject
0x180036ca6  call    cs:__imp_CloseHandle
0x180036cac  xor     ebx, ebx
0x180036cae  mov     eax, ebx
0x180036cb0  mov     rcx, [rsp+268h+var_18]
0x180036cb8  xor     rcx, rsp; StackCookie
0x180036cbb  call    __security_check_cookie
0x180036cc0  mov     rbx, [rsp+268h+arg_8]
0x180036cc8  add     rsp, 260h
0x180036ccf  pop     rsi
0x180036cd0  retn
```
