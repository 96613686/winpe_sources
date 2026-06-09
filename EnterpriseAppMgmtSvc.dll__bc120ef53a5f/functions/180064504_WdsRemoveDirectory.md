# WdsRemoveDirectory

- ea: `0x180064504`
- end: `0x18006464b`
- name: `WdsRemoveDirectory`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180065d70`
- `0x180065ee4`
- `0x180066270`

## callees

- `0x180063538`
- `0x180063df0`
- `0x180064504`
- `0x180064e8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800645cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800645cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800645df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800645df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006461e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064633`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006461e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064633`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180064541`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180064541`

## string_xrefs

- `0x1800645fe`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`
- `0x1800645af`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x180064560`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`

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
0x180064504  push    rbx
0x180064506  push    rbp
0x180064507  push    rsi
0x180064508  push    rdi
0x180064509  sub     rsp, 38h
0x18006450d  mov     rdi, rcx
0x180064510  test    rcx, rcx
0x180064513  jz      loc_18006462E
0x180064519  xor     eax, eax
0x18006451b  cmp     ax, [rcx]
0x18006451e  jz      loc_18006462E
0x180064524  xor     edx, edx
0x180064526  call    PrepareUnicodePathEx
0x18006452b  mov     rsi, rax
0x18006452e  test    rax, rax
0x180064531  jz      loc_1800645ED
0x180064537  mov     edx, 80h; dwFileAttributes
0x18006453c  mov     rcx, rax; lpFileName
0x18006453f  xor     ebx, ebx
0x180064541  call    cs:__imp_SetFileAttributesW
0x180064548  nop     dword ptr [rax+rax+00h]
0x18006454d  test    eax, eax
0x18006454f  jnz     short loc_18006457E
0x180064551  call    cs:__imp_GetLastError
0x180064558  nop     dword ptr [rax+rax+00h]
0x18006455d  mov     r9, rsi
0x180064560  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x180064567  lea     rcx, g_WdsLibLog
0x18006456e  mov     dword ptr [rsp+58h+var_38], eax
0x180064572  mov     edx, 3000000h
0x180064577  mov     ebx, eax
0x180064579  call    LibLog
0x18006457e  xor     edx, edx
0x180064580  mov     rcx, rsi
0x180064583  call    DeleteFileEx2
0x180064588  mov     ebp, eax
0x18006458a  test    eax, eax
0x18006458c  jnz     short loc_1800645CB
0x18006458e  test    ebx, ebx
0x180064590  jnz     short loc_1800645A0
0x180064592  call    cs:__imp_GetLastError
0x180064599  nop     dword ptr [rax+rax+00h]
0x18006459e  mov     ebx, eax
0x1800645a0  call    cs:__imp_GetLastError
0x1800645a7  nop     dword ptr [rax+rax+00h]
0x1800645ac  mov     r9, rsi
0x1800645af  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x1800645b6  lea     rcx, g_WdsLibLog
0x1800645bd  mov     dword ptr [rsp+58h+var_38], eax
0x1800645c1  mov     edx, 3000000h
0x1800645c6  call    LibLog
0x1800645cb  call    cs:__imp_GetProcessHeap
0x1800645d2  nop     dword ptr [rax+rax+00h]
0x1800645d7  mov     r8, rsi; lpMem
0x1800645da  xor     edx, edx; dwFlags
0x1800645dc  mov     rcx, rax; hHeap
0x1800645df  call    cs:__imp_HeapFree
0x1800645e6  nop     dword ptr [rax+rax+00h]
0x1800645eb  jmp     short loc_18006461C
0x1800645ed  xor     ebp, ebp
0x1800645ef  call    cs:__imp_GetLastError
0x1800645f6  nop     dword ptr [rax+rax+00h]
0x1800645fb  mov     r9, rdi
0x1800645fe  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x180064605  lea     rcx, g_WdsLibLog
0x18006460c  mov     dword ptr [rsp+58h+var_38], eax
0x180064610  mov     edx, 3000000h
0x180064615  mov     ebx, eax
0x180064617  call    LibLog
0x18006461c  mov     ecx, ebx; dwErrCode
0x18006461e  call    cs:__imp_SetLastError
0x180064625  nop     dword ptr [rax+rax+00h]
0x18006462a  mov     eax, ebp
0x18006462c  jmp     short loc_180064641
0x18006462e  mov     ecx, 57h ; 'W'; dwErrCode
0x180064633  call    cs:__imp_SetLastError
0x18006463a  nop     dword ptr [rax+rax+00h]
0x18006463f  xor     eax, eax
0x180064641  add     rsp, 38h
0x180064645  pop     rdi
0x180064646  pop     rsi
0x180064647  pop     rbp
0x180064648  pop     rbx
0x180064649  retn
```
