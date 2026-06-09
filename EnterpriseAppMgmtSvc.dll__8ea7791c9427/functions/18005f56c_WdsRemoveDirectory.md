# WdsRemoveDirectory

- ea: `0x18005f56c`
- end: `0x18005f67c`
- name: `WdsRemoveDirectory`
- size: `272`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180060aa0`
- `0x180060be8`
- `0x180060f20`

## callees

- `0x18005e748`
- `0x18005eea8`
- `0x18005f56c`
- `0x18005fd24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f61b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f61b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f633`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f65c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f66b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f65c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f66b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005f5a9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005f5a9`

## string_xrefs

- `0x18005f5ff`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x18005f5bc`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x18005f63c`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WdsRemoveDirectory(unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  WCHAR *v3; // rsi
  DWORD LastError; // ebx
  BOOL v5; // ebp
  HANDLE ProcessHeap; // rax
  __int64 v8; // [rsp+20h] [rbp-38h]

  if ( a1 && *a1 )
  {
    v2 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v3 = (WCHAR *)v2;
    if ( v2 )
    {
      LastError = 0;
      if ( !SetFileAttributesW(v2, 0x80u) )
      {
        LastError = GetLastError();
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x",
          v3,
          LastError);
      }
      v5 = DeleteFileEx2((__int64)v3, 0);
      if ( !v5 )
      {
        if ( !LastError )
          LastError = GetLastError();
        LODWORD(v8) = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x", v3, v8);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    else
    {
      v5 = 0;
      LastError = GetLastError();
      LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x", a1, LastError);
    }
    SetLastError(LastError);
    return v5;
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
0x18005f56c  push    rbx
0x18005f56e  push    rbp
0x18005f56f  push    rsi
0x18005f570  push    rdi
0x18005f571  sub     rsp, 38h
0x18005f575  mov     rdi, rcx
0x18005f578  test    rcx, rcx
0x18005f57b  jz      loc_18005F666
0x18005f581  xor     eax, eax
0x18005f583  cmp     ax, [rcx]
0x18005f586  jz      loc_18005F666
0x18005f58c  xor     edx, edx
0x18005f58e  call    PrepareUnicodePathEx
0x18005f593  mov     rsi, rax
0x18005f596  test    rax, rax
0x18005f599  jz      loc_18005F631
0x18005f59f  mov     edx, 80h; dwFileAttributes
0x18005f5a4  mov     rcx, rax; lpFileName
0x18005f5a7  xor     ebx, ebx
0x18005f5a9  call    cs:__imp_SetFileAttributesW
0x18005f5af  test    eax, eax
0x18005f5b1  jnz     short loc_18005F5DA
0x18005f5b3  call    cs:__imp_GetLastError
0x18005f5b9  mov     r9, rsi
0x18005f5bc  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x18005f5c3  lea     rcx, g_WdsLibLog
0x18005f5ca  mov     dword ptr [rsp+58h+var_38], eax
0x18005f5ce  mov     edx, 3000000h
0x18005f5d3  mov     ebx, eax
0x18005f5d5  call    LibLog
0x18005f5da  xor     edx, edx
0x18005f5dc  mov     rcx, rsi
0x18005f5df  call    DeleteFileEx2
0x18005f5e4  mov     ebp, eax
0x18005f5e6  test    eax, eax
0x18005f5e8  jnz     short loc_18005F61B
0x18005f5ea  test    ebx, ebx
0x18005f5ec  jnz     short loc_18005F5F6
0x18005f5ee  call    cs:__imp_GetLastError
0x18005f5f4  mov     ebx, eax
0x18005f5f6  call    cs:__imp_GetLastError
0x18005f5fc  mov     r9, rsi
0x18005f5ff  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x18005f606  lea     rcx, g_WdsLibLog
0x18005f60d  mov     dword ptr [rsp+58h+var_38], eax
0x18005f611  mov     edx, 3000000h
0x18005f616  call    LibLog
0x18005f61b  call    cs:__imp_GetProcessHeap
0x18005f621  mov     r8, rsi; lpMem
0x18005f624  xor     edx, edx; dwFlags
0x18005f626  mov     rcx, rax; hHeap
0x18005f629  call    cs:__imp_HeapFree
0x18005f62f  jmp     short loc_18005F65A
0x18005f631  xor     ebp, ebp
0x18005f633  call    cs:__imp_GetLastError
0x18005f639  mov     r9, rdi
0x18005f63c  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x18005f643  lea     rcx, g_WdsLibLog
0x18005f64a  mov     dword ptr [rsp+58h+var_38], eax
0x18005f64e  mov     edx, 3000000h
0x18005f653  mov     ebx, eax
0x18005f655  call    LibLog
0x18005f65a  mov     ecx, ebx; dwErrCode
0x18005f65c  call    cs:__imp_SetLastError
0x18005f662  mov     eax, ebp
0x18005f664  jmp     short loc_18005F673
0x18005f666  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f66b  call    cs:__imp_SetLastError
0x18005f671  xor     eax, eax
0x18005f673  add     rsp, 38h
0x18005f677  pop     rdi
0x18005f678  pop     rsi
0x18005f679  pop     rbp
0x18005f67a  pop     rbx
0x18005f67b  retn
```
