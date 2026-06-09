# WdsRemoveDirectory

- ea: `0x140024cac`
- end: `0x140024e0a`
- name: `WdsRemoveDirectory`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140025770`
- `0x1400258e4`
- `0x140025c80`
- `0x140025f90`

## callees

- `0x140022960`
- `0x140022c14`
- `0x140023dcc`
- `0x140024cac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140024d92`
- `KERNEL32!HeapFree` at `0x140024d92`
- `KERNEL32!GetProcessHeap` at `0x140024d7e`
- `KERNEL32!GetProcessHeap` at `0x140024d7e`
- `KERNEL32!GetLastError` at `0x140024d04`
- `KERNEL32!GetLastError` at `0x140024d45`
- `KERNEL32!GetLastError` at `0x140024d53`
- `KERNEL32!GetLastError` at `0x140024da2`
- `KERNEL32!GetLastError` at `0x140024d04`
- `KERNEL32!GetLastError` at `0x140024d45`
- `KERNEL32!GetLastError` at `0x140024d53`
- `KERNEL32!GetLastError` at `0x140024da2`
- `KERNEL32!SetFileAttributesW` at `0x140024cf4`
- `KERNEL32!SetFileAttributesW` at `0x140024cf4`
- `KERNEL32!SetLastError` at `0x140024dd1`
- `KERNEL32!SetLastError` at `0x140024de6`
- `KERNEL32!SetLastError` at `0x140024dd1`
- `KERNEL32!SetLastError` at `0x140024de6`

## string_xrefs

- `0x140024d13`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x140024d62`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x140024db1`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall WdsRemoveDirectory(unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // edi
  const WCHAR *v4; // rax
  WCHAR *v5; // rbp
  unsigned int v6; // esi
  HANDLE ProcessHeap; // rax
  __int64 v9; // [rsp+20h] [rbp-18h]

  v1 = 0;
  LastError = 0;
  if ( a1 && *a1 )
  {
    v4 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v5 = (WCHAR *)v4;
    if ( v4 )
    {
      if ( !SetFileAttributesW(v4, 0x80u) )
      {
        LastError = GetLastError();
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x",
          v5,
          LastError);
      }
      v6 = DeleteFileEx2((__int64)v5, 0);
      if ( !v6 )
      {
        if ( !LastError )
          LastError = GetLastError();
        LODWORD(v9) = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x", v5, v9);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      v1 = v6;
    }
    else
    {
      LastError = GetLastError();
      LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x", a1, LastError);
    }
    SetLastError(LastError);
    return v1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x140024cac  mov     [rsp+arg_0], rbx
0x140024cb1  mov     [rsp+arg_8], rbp
0x140024cb6  mov     [rsp+arg_10], rsi
0x140024cbb  push    rdi
0x140024cbc  sub     rsp, 30h
0x140024cc0  xor     ebx, ebx
0x140024cc2  mov     rsi, rcx
0x140024cc5  mov     edi, ebx
0x140024cc7  test    rcx, rcx
0x140024cca  jz      loc_140024DE1
0x140024cd0  cmp     bx, [rcx]
0x140024cd3  jz      loc_140024DE1
0x140024cd9  xor     edx, edx
0x140024cdb  call    PrepareUnicodePathEx
0x140024ce0  mov     rbp, rax
0x140024ce3  test    rax, rax
0x140024ce6  jz      loc_140024DA2
0x140024cec  mov     edx, 80h; dwFileAttributes
0x140024cf1  mov     rcx, rax; lpFileName
0x140024cf4  call    cs:__imp_SetFileAttributesW
0x140024cfb  nop     dword ptr [rax+rax+00h]
0x140024d00  test    eax, eax
0x140024d02  jnz     short loc_140024D31
0x140024d04  call    cs:__imp_GetLastError
0x140024d0b  nop     dword ptr [rax+rax+00h]
0x140024d10  mov     r9, rbp
0x140024d13  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x140024d1a  lea     rcx, g_WdsLibLog
0x140024d21  mov     dword ptr [rsp+38h+var_18], eax
0x140024d25  mov     edx, 3000000h
0x140024d2a  mov     edi, eax
0x140024d2c  call    LibLog
0x140024d31  xor     edx, edx
0x140024d33  mov     rcx, rbp
0x140024d36  call    DeleteFileEx2
0x140024d3b  mov     esi, eax
0x140024d3d  test    eax, eax
0x140024d3f  jnz     short loc_140024D7E
0x140024d41  test    edi, edi
0x140024d43  jnz     short loc_140024D53
0x140024d45  call    cs:__imp_GetLastError
0x140024d4c  nop     dword ptr [rax+rax+00h]
0x140024d51  mov     edi, eax
0x140024d53  call    cs:__imp_GetLastError
0x140024d5a  nop     dword ptr [rax+rax+00h]
0x140024d5f  mov     r9, rbp
0x140024d62  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x140024d69  lea     rcx, g_WdsLibLog
0x140024d70  mov     dword ptr [rsp+38h+var_18], eax
0x140024d74  mov     edx, 3000000h
0x140024d79  call    LibLog
0x140024d7e  call    cs:__imp_GetProcessHeap
0x140024d85  nop     dword ptr [rax+rax+00h]
0x140024d8a  mov     r8, rbp; lpMem
0x140024d8d  xor     edx, edx; dwFlags
0x140024d8f  mov     rcx, rax; hHeap
0x140024d92  call    cs:__imp_HeapFree
0x140024d99  nop     dword ptr [rax+rax+00h]
0x140024d9e  mov     ebx, esi
0x140024da0  jmp     short loc_140024DCF
0x140024da2  call    cs:__imp_GetLastError
0x140024da9  nop     dword ptr [rax+rax+00h]
0x140024dae  mov     r9, rsi
0x140024db1  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x140024db8  lea     rcx, g_WdsLibLog
0x140024dbf  mov     dword ptr [rsp+38h+var_18], eax
0x140024dc3  mov     edx, 3000000h
0x140024dc8  mov     edi, eax
0x140024dca  call    LibLog
0x140024dcf  mov     ecx, edi; dwErrCode
0x140024dd1  call    cs:__imp_SetLastError
0x140024dd8  nop     dword ptr [rax+rax+00h]
0x140024ddd  mov     eax, ebx
0x140024ddf  jmp     short loc_140024DF4
0x140024de1  mov     ecx, 57h ; 'W'; dwErrCode
0x140024de6  call    cs:__imp_SetLastError
0x140024ded  nop     dword ptr [rax+rax+00h]
0x140024df2  xor     eax, eax
0x140024df4  mov     rbx, [rsp+38h+arg_0]
0x140024df9  mov     rbp, [rsp+38h+arg_8]
0x140024dfe  mov     rsi, [rsp+38h+arg_10]
0x140024e03  add     rsp, 30h
0x140024e07  pop     rdi
0x140024e08  retn
```
