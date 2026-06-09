# WdsRemoveDirectory

- ea: `0x180066c74`
- end: `0x180066d84`
- name: `WdsRemoveDirectory`
- size: `272`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180066d8c`

## callees

- `0x18006631c`
- `0x180066484`
- `0x180066c74`
- `0x1800673b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180066d64`
- `KERNEL32!SetLastError` at `0x180066d73`
- `KERNEL32!SetLastError` at `0x180066d64`
- `KERNEL32!SetLastError` at `0x180066d73`
- `KERNEL32!GetLastError` at `0x180066cbb`
- `KERNEL32!GetLastError` at `0x180066cf6`
- `KERNEL32!GetLastError` at `0x180066cfe`
- `KERNEL32!GetLastError` at `0x180066d3b`
- `KERNEL32!GetLastError` at `0x180066cbb`
- `KERNEL32!GetLastError` at `0x180066cf6`
- `KERNEL32!GetLastError` at `0x180066cfe`
- `KERNEL32!GetLastError` at `0x180066d3b`
- `KERNEL32!HeapFree` at `0x180066d31`
- `KERNEL32!HeapFree` at `0x180066d31`
- `KERNEL32!GetProcessHeap` at `0x180066d23`
- `KERNEL32!GetProcessHeap` at `0x180066d23`
- `KERNEL32!SetFileAttributesW` at `0x180066cb1`
- `KERNEL32!SetFileAttributesW` at `0x180066cb1`

## string_xrefs

- `0x180066cc4`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x180066d44`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`
- `0x180066d07`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180066c74  push    rbx
0x180066c76  push    rbp
0x180066c77  push    rsi
0x180066c78  push    rdi
0x180066c79  sub     rsp, 38h
0x180066c7d  mov     rdi, rcx
0x180066c80  test    rcx, rcx
0x180066c83  jz      loc_180066D6E
0x180066c89  xor     eax, eax
0x180066c8b  cmp     ax, [rcx]
0x180066c8e  jz      loc_180066D6E
0x180066c94  xor     edx, edx
0x180066c96  call    PrepareUnicodePathEx
0x180066c9b  mov     rsi, rax
0x180066c9e  test    rax, rax
0x180066ca1  jz      loc_180066D39
0x180066ca7  mov     edx, 80h; dwFileAttributes
0x180066cac  mov     rcx, rax; lpFileName
0x180066caf  xor     ebx, ebx
0x180066cb1  call    cs:__imp_SetFileAttributesW
0x180066cb7  test    eax, eax
0x180066cb9  jnz     short loc_180066CE2
0x180066cbb  call    cs:__imp_GetLastError
0x180066cc1  mov     r9, rsi
0x180066cc4  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x180066ccb  lea     rcx, g_WdsLibLog
0x180066cd2  mov     dword ptr [rsp+58h+var_38], eax
0x180066cd6  mov     edx, 3000000h
0x180066cdb  mov     ebx, eax
0x180066cdd  call    LibLog
0x180066ce2  xor     edx, edx
0x180066ce4  mov     rcx, rsi
0x180066ce7  call    DeleteFileEx2
0x180066cec  mov     ebp, eax
0x180066cee  test    eax, eax
0x180066cf0  jnz     short loc_180066D23
0x180066cf2  test    ebx, ebx
0x180066cf4  jnz     short loc_180066CFE
0x180066cf6  call    cs:__imp_GetLastError
0x180066cfc  mov     ebx, eax
0x180066cfe  call    cs:__imp_GetLastError
0x180066d04  mov     r9, rsi
0x180066d07  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x180066d0e  lea     rcx, g_WdsLibLog
0x180066d15  mov     dword ptr [rsp+58h+var_38], eax
0x180066d19  mov     edx, 3000000h
0x180066d1e  call    LibLog
0x180066d23  call    cs:__imp_GetProcessHeap
0x180066d29  mov     r8, rsi; lpMem
0x180066d2c  xor     edx, edx; dwFlags
0x180066d2e  mov     rcx, rax; hHeap
0x180066d31  call    cs:__imp_HeapFree
0x180066d37  jmp     short loc_180066D62
0x180066d39  xor     ebp, ebp
0x180066d3b  call    cs:__imp_GetLastError
0x180066d41  mov     r9, rdi
0x180066d44  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x180066d4b  lea     rcx, g_WdsLibLog
0x180066d52  mov     dword ptr [rsp+58h+var_38], eax
0x180066d56  mov     edx, 3000000h
0x180066d5b  mov     ebx, eax
0x180066d5d  call    LibLog
0x180066d62  mov     ecx, ebx; dwErrCode
0x180066d64  call    cs:__imp_SetLastError
0x180066d6a  mov     eax, ebp
0x180066d6c  jmp     short loc_180066D7B
0x180066d6e  mov     ecx, 57h ; 'W'; dwErrCode
0x180066d73  call    cs:__imp_SetLastError
0x180066d79  xor     eax, eax
0x180066d7b  add     rsp, 38h
0x180066d7f  pop     rdi
0x180066d80  pop     rsi
0x180066d81  pop     rbp
0x180066d82  pop     rbx
0x180066d83  retn
```
