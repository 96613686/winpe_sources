# CreateTemporaryLogFile

- ea: `0x140016800`
- end: `0x140016aa7`
- name: `CreateTemporaryLogFile`
- size: `679`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140018478`

## callees

- `0x1400070bc`
- `0x14000a570`
- `0x14000c7a0`
- `0x14000f39c`
- `0x140016800`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400168d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400168d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016a6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400169bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016a76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400169bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a3e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016957`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016957`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016a57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140016a57`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140016a03`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140016a03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016931`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400169f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016931`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400169f1`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140016878`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140016878`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140016a21`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140016a21`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x14001684c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x14001684c`

## pseudocode

```c
_BOOL8 __fastcall CreateTemporaryLogFile(WCHAR *lpFileName, unsigned __int64 a2)
{
  __int64 hTemplateFile; // rbx
  DWORD v5; // ebx
  LPVOID v6; // rax
  void *v7; // rsi
  HANDLE FileW; // rax
  __int64 v9; // rdi
  HANDLE v10; // rax
  DWORD dwBytes; // [rsp+40h] [rbp-458h] BYREF
  DWORD dwBytes_4; // [rsp+44h] [rbp-454h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-448h] BYREF
  WCHAR PathName[264]; // [rsp+260h] [rbp-238h] BYREF

  dwBytes = 0;
  *lpFileName = 0;
  dwBytes_4 = 0;
  if ( !(unsigned int)GetTempPath2W(260, PathName) || !GetTempFileNameW(PathName, L"LOG", 0, lpFileName) )
    goto LABEL_2;
  if ( a2 >= 2 )
  {
    if ( (unsigned int)pSetupGetTextLogSectionData(a2, 0, 0, &dwBytes) )
    {
      LODWORD(hTemplateFile) = 1359;
      goto LABEL_34;
    }
    LODWORD(hTemplateFile) = GetLastError();
    if ( (_DWORD)hTemplateFile != 122 )
      goto LABEL_34;
    v5 = dwBytes;
    v6 = HeapAlloc(hHeap, 0, dwBytes);
    v7 = v6;
    if ( !v6 )
    {
      LODWORD(hTemplateFile) = 8;
      goto LABEL_34;
    }
    if ( !(unsigned int)pSetupGetTextLogSectionData(a2, v6, v5, 0)
      || (FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0), v9 = (__int64)FileW, FileW == (HANDLE)-1LL) )
    {
      LODWORD(hTemplateFile) = GetLastError();
LABEL_33:
      HeapFree(hHeap, 0, v7);
      goto LABEL_34;
    }
    if ( WriteFile(FileW, v7, v5, &dwBytes_4, 0) )
      LODWORD(hTemplateFile) = 0;
    else
      LODWORD(hTemplateFile) = GetLastError();
    goto LABEL_29;
  }
  if ( g_sputils_LogInitialized || (unsigned int)pSpUtilsLogInitialize() )
  {
    if ( lpMem )
    {
      hTemplateFile = 0;
      if ( (int)StringCchCopyW(FileName, 0x104u, (size_t *)lpMem) < 0 )
        hTemplateFile = 122;
    }
    else
    {
      hTemplateFile = 1359;
    }
  }
  else
  {
    hTemplateFile = GetLastError();
  }
  SetLastError(hTemplateFile);
  if ( (_DWORD)hTemplateFile )
  {
LABEL_2:
    LODWORD(hTemplateFile) = GetLastError();
    goto LABEL_34;
  }
  v10 = CreateFileW(FileName, 0x40000000u, 1u, 0, 3u, 0x80u, (HANDLE)hTemplateFile);
  v9 = (__int64)v10;
  if ( v10 != (HANDLE)-1LL )
  {
    FlushFileBuffers(v10);
    CloseHandle((HANDLE)v9);
    v9 = -1;
  }
  if ( CopyFileW(FileName, lpFileName, 0) )
    goto LABEL_34;
  LODWORD(hTemplateFile) = GetLastError();
  if ( v9 == -1 )
    goto LABEL_34;
  v7 = 0;
LABEL_29:
  CloseHandle((HANDLE)v9);
  if ( (_DWORD)hTemplateFile && (unsigned int)pSetupFileExists(lpFileName) )
    DeleteFileW(lpFileName);
  if ( v7 )
    goto LABEL_33;
LABEL_34:
  SetLastError(hTemplateFile);
  return (_DWORD)hTemplateFile == 0;
}

```

## disassembly

```asm
0x140016800  mov     [rsp+arg_10], rbx
0x140016805  push    rsi
0x140016806  push    rdi
0x140016807  push    r14
0x140016809  sub     rsp, 480h
0x140016810  mov     rax, cs:__security_cookie
0x140016817  xor     rax, rsp
0x14001681a  mov     [rsp+498h+var_28], rax
0x140016822  xor     eax, eax
0x140016824  mov     [rsp+498h+dwBytes], 0
0x14001682c  mov     [rcx], ax
0x14001682f  mov     rdi, rdx
0x140016832  mov     r14, rcx
0x140016835  mov     [rsp+498h+dwBytes+4], 0
0x14001683d  mov     esi, 104h
0x140016842  lea     rdx, [rsp+498h+PathName]
0x14001684a  mov     ecx, esi
0x14001684c  call    cs:__imp_GetTempPath2W
0x140016852  test    eax, eax
0x140016854  jnz     short loc_140016863
0x140016856  call    cs:__imp_GetLastError
0x14001685c  mov     ebx, eax
0x14001685e  jmp     loc_140016A74
0x140016863  mov     r9, r14; lpTempFileName
0x140016866  lea     rdx, PrefixString; "LOG"
0x14001686d  xor     r8d, r8d; uUnique
0x140016870  lea     rcx, [rsp+498h+PathName]; lpPathName
0x140016878  call    cs:__imp_GetTempFileNameW
0x14001687e  test    eax, eax
0x140016880  jz      short loc_140016856
0x140016882  cmp     rdi, 2
0x140016886  jb      loc_140016975
0x14001688c  lea     r9, [rsp+498h+dwBytes]
0x140016891  xor     r8d, r8d
0x140016894  xor     edx, edx
0x140016896  mov     rcx, rdi
0x140016899  call    pSetupGetTextLogSectionData
0x14001689e  test    eax, eax
0x1400168a0  jz      short loc_1400168AC
0x1400168a2  mov     ebx, 54Fh
0x1400168a7  jmp     loc_140016A74
0x1400168ac  call    cs:__imp_GetLastError
0x1400168b2  mov     ecx, 7Ah ; 'z'
0x1400168b7  mov     ebx, eax
0x1400168b9  cmp     eax, ecx
0x1400168bb  jnz     loc_140016A74
0x1400168c1  mov     ebx, [rsp+498h+dwBytes]
0x1400168c5  xor     edx, edx; dwFlags
0x1400168c7  mov     rcx, cs:hHeap; hHeap
0x1400168ce  mov     r8d, ebx; dwBytes
0x1400168d1  call    cs:__imp_HeapAlloc
0x1400168d7  mov     rsi, rax
0x1400168da  test    rax, rax
0x1400168dd  jnz     short loc_1400168E7
0x1400168df  lea     ebx, [rax+8]
0x1400168e2  jmp     loc_140016A74
0x1400168e7  xor     r9d, r9d
0x1400168ea  mov     r8d, ebx
0x1400168ed  mov     rdx, rsi
0x1400168f0  mov     rcx, rdi
0x1400168f3  call    pSetupGetTextLogSectionData
0x1400168f8  test    eax, eax
0x1400168fa  jnz     short loc_140016909
0x1400168fc  call    cs:__imp_GetLastError
0x140016902  mov     ebx, eax
0x140016904  jmp     loc_140016A62
0x140016909  xor     r9d, r9d; lpSecurityAttributes
0x14001690c  mov     [rsp+498h+hTemplateFile], 0; hTemplateFile
0x140016915  mov     [rsp+498h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14001691d  mov     edx, 40000000h; dwDesiredAccess
0x140016922  mov     rcx, r14; lpFileName
0x140016925  mov     [rsp+498h+dwCreationDisposition], 2; dwCreationDisposition
0x14001692d  lea     r8d, [r9+1]; dwShareMode
0x140016931  call    cs:__imp_CreateFileW
0x140016937  mov     rdi, rax
0x14001693a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001693e  jz      short loc_1400168FC
0x140016940  lea     r9, [rsp+498h+dwBytes+4]; lpNumberOfBytesWritten
0x140016945  mov     qword ptr [rsp+498h+dwCreationDisposition], 0; lpOverlapped
0x14001694e  mov     r8d, ebx; nNumberOfBytesToWrite
0x140016951  mov     rdx, rsi; lpBuffer
0x140016954  mov     rcx, rax; hFile
0x140016957  call    cs:__imp_WriteFile
0x14001695d  test    eax, eax
0x14001695f  jnz     short loc_14001696E
0x140016961  call    cs:__imp_GetLastError
0x140016967  mov     ebx, eax
0x140016969  jmp     loc_140016A3B
0x14001696e  xor     ebx, ebx
0x140016970  jmp     loc_140016A3B
0x140016975  cmp     cs:g_sputils_LogInitialized, 0
0x14001697c  jnz     short loc_140016991
0x14001697e  call    _pSpUtilsLogInitialize
0x140016983  test    eax, eax
0x140016985  jnz     short loc_140016991
0x140016987  call    cs:__imp_GetLastError
0x14001698d  mov     ebx, eax
0x14001698f  jmp     short loc_1400169BB
0x140016991  mov     r8, cs:lpMem; unsigned __int16 *
0x140016998  test    r8, r8
0x14001699b  jnz     short loc_1400169A4
0x14001699d  mov     ebx, 54Fh
0x1400169a2  jmp     short loc_1400169BB
0x1400169a4  mov     rdx, rsi; unsigned __int64
0x1400169a7  lea     rcx, [rsp+498h+FileName]; unsigned __int16 *
0x1400169ac  xor     ebx, ebx
0x1400169ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400169b3  test    eax, eax
0x1400169b5  lea     ecx, [rbx+7Ah]
0x1400169b8  cmovs   ebx, ecx
0x1400169bb  mov     ecx, ebx; dwErrCode
0x1400169bd  call    cs:__imp_SetLastError
0x1400169c3  test    ebx, ebx
0x1400169c5  jnz     loc_140016856
0x1400169cb  mov     [rsp+498h+hTemplateFile], rbx; hTemplateFile
0x1400169d0  lea     r8d, [rbx+1]; dwShareMode
0x1400169d4  mov     [rsp+498h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400169dc  lea     rcx, [rsp+498h+FileName]; lpFileName
0x1400169e1  xor     r9d, r9d; lpSecurityAttributes
0x1400169e4  mov     [rsp+498h+dwCreationDisposition], 3; dwCreationDisposition
0x1400169ec  mov     edx, 40000000h; dwDesiredAccess
0x1400169f1  call    cs:__imp_CreateFileW
0x1400169f7  mov     rdi, rax
0x1400169fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400169fe  jz      short loc_140016A16
0x140016a00  mov     rcx, rax; hFile
0x140016a03  call    cs:__imp_FlushFileBuffers
0x140016a09  mov     rcx, rdi; hObject
0x140016a0c  call    cs:__imp_CloseHandle
0x140016a12  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140016a16  xor     r8d, r8d; bFailIfExists
0x140016a19  lea     rcx, [rsp+498h+FileName]; lpExistingFileName
0x140016a1e  mov     rdx, r14; lpNewFileName
0x140016a21  call    cs:__imp_CopyFileW
0x140016a27  test    eax, eax
0x140016a29  jnz     short loc_140016A74
0x140016a2b  call    cs:__imp_GetLastError
0x140016a31  mov     ebx, eax
0x140016a33  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140016a37  jz      short loc_140016A74
0x140016a39  xor     esi, esi
0x140016a3b  mov     rcx, rdi; hObject
0x140016a3e  call    cs:__imp_CloseHandle
0x140016a44  test    ebx, ebx
0x140016a46  jz      short loc_140016A5D
0x140016a48  mov     rcx, r14; lpFileName
0x140016a4b  call    pSetupFileExists
0x140016a50  test    eax, eax
0x140016a52  jz      short loc_140016A5D
0x140016a54  mov     rcx, r14; lpFileName
0x140016a57  call    cs:__imp_DeleteFileW
0x140016a5d  test    rsi, rsi
0x140016a60  jz      short loc_140016A74
0x140016a62  mov     rcx, cs:hHeap; hHeap
0x140016a69  mov     r8, rsi; lpMem
0x140016a6c  xor     edx, edx; dwFlags
0x140016a6e  call    cs:__imp_HeapFree
0x140016a74  mov     ecx, ebx; dwErrCode
0x140016a76  call    cs:__imp_SetLastError
0x140016a7c  xor     eax, eax
0x140016a7e  test    ebx, ebx
0x140016a80  setz    al
0x140016a83  mov     rcx, [rsp+498h+var_28]
0x140016a8b  xor     rcx, rsp; StackCookie
0x140016a8e  call    __security_check_cookie
0x140016a93  mov     rbx, [rsp+498h+arg_10]
0x140016a9b  add     rsp, 480h
0x140016aa2  pop     r14
0x140016aa4  pop     rdi
0x140016aa5  pop     rsi
0x140016aa6  retn
```
