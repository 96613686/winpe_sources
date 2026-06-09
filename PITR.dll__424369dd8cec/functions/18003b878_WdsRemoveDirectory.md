# WdsRemoveDirectory

- ea: `0x18003b878`
- end: `0x18003b988`
- name: `WdsRemoveDirectory`
- size: `272`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003bbe0`

## callees

- `0x18003a8d8`
- `0x18003b094`
- `0x18003b878`
- `0x18003d238`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003b8b5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003b8b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b977`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b93f`

## string_xrefs

- `0x18003b8c8`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x18003b90b`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x18003b948`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x18003b878  push    rbx
0x18003b87a  push    rbp
0x18003b87b  push    rsi
0x18003b87c  push    rdi
0x18003b87d  sub     rsp, 38h
0x18003b881  mov     rdi, rcx
0x18003b884  test    rcx, rcx
0x18003b887  jz      loc_18003B972
0x18003b88d  xor     eax, eax
0x18003b88f  cmp     ax, [rcx]
0x18003b892  jz      loc_18003B972
0x18003b898  xor     edx, edx
0x18003b89a  call    PrepareUnicodePathEx
0x18003b89f  mov     rsi, rax
0x18003b8a2  test    rax, rax
0x18003b8a5  jz      loc_18003B93D
0x18003b8ab  mov     edx, 80h; dwFileAttributes
0x18003b8b0  mov     rcx, rax; lpFileName
0x18003b8b3  xor     ebx, ebx
0x18003b8b5  call    cs:__imp_SetFileAttributesW
0x18003b8bb  test    eax, eax
0x18003b8bd  jnz     short loc_18003B8E6
0x18003b8bf  call    cs:__imp_GetLastError
0x18003b8c5  mov     r9, rsi
0x18003b8c8  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x18003b8cf  lea     rcx, g_WdsLibLog
0x18003b8d6  mov     dword ptr [rsp+58h+var_38], eax
0x18003b8da  mov     edx, 3000000h
0x18003b8df  mov     ebx, eax
0x18003b8e1  call    LibLog
0x18003b8e6  xor     edx, edx
0x18003b8e8  mov     rcx, rsi
0x18003b8eb  call    DeleteFileEx2
0x18003b8f0  mov     ebp, eax
0x18003b8f2  test    eax, eax
0x18003b8f4  jnz     short loc_18003B927
0x18003b8f6  test    ebx, ebx
0x18003b8f8  jnz     short loc_18003B902
0x18003b8fa  call    cs:__imp_GetLastError
0x18003b900  mov     ebx, eax
0x18003b902  call    cs:__imp_GetLastError
0x18003b908  mov     r9, rsi
0x18003b90b  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x18003b912  lea     rcx, g_WdsLibLog
0x18003b919  mov     dword ptr [rsp+58h+var_38], eax
0x18003b91d  mov     edx, 3000000h
0x18003b922  call    LibLog
0x18003b927  call    cs:__imp_GetProcessHeap
0x18003b92d  mov     r8, rsi; lpMem
0x18003b930  xor     edx, edx; dwFlags
0x18003b932  mov     rcx, rax; hHeap
0x18003b935  call    cs:__imp_HeapFree
0x18003b93b  jmp     short loc_18003B966
0x18003b93d  xor     ebp, ebp
0x18003b93f  call    cs:__imp_GetLastError
0x18003b945  mov     r9, rdi
0x18003b948  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x18003b94f  lea     rcx, g_WdsLibLog
0x18003b956  mov     dword ptr [rsp+58h+var_38], eax
0x18003b95a  mov     edx, 3000000h
0x18003b95f  mov     ebx, eax
0x18003b961  call    LibLog
0x18003b966  mov     ecx, ebx; dwErrCode
0x18003b968  call    cs:__imp_SetLastError
0x18003b96e  mov     eax, ebp
0x18003b970  jmp     short loc_18003B97F
0x18003b972  mov     ecx, 57h ; 'W'; dwErrCode
0x18003b977  call    cs:__imp_SetLastError
0x18003b97d  xor     eax, eax
0x18003b97f  add     rsp, 38h
0x18003b983  pop     rdi
0x18003b984  pop     rsi
0x18003b985  pop     rbp
0x18003b986  pop     rbx
0x18003b987  retn
```
