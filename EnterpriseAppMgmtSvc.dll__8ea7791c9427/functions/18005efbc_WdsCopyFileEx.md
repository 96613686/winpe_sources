# WdsCopyFileEx

- ea: `0x18005efbc`
- end: `0x18005f1f4`
- name: `WdsCopyFileEx`
- size: `568`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18005e658`

## callees

- `0x18005e748`
- `0x18005eea8`
- `0x18005efbc`
- `0x18005f1fc`
- `0x18005fd24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f1ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f1c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f1ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f1c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005eff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1a7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f111`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005f111`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005f12d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18005f12d`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18005f06a`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18005f06a`

## string_xrefs

- `0x18005f185`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`
- `0x18005f14b`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x18005f0e2`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`

## pseudocode

```c
__int64 WdsCopyFileEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        DWORD (__stdcall *a3)(LARGE_INTEGER TotalFileSize, LARGE_INTEGER TotalBytesTransferred, LARGE_INTEGER StreamSize, LARGE_INTEGER StreamBytesTransferred, DWORD dwStreamNumber, DWORD dwCallbackReason, HANDLE hSourceFile, HANDLE hDestinationFile, LPVOID lpData),
        void *a4,
        ...)
{
  char v4; // bl
  unsigned int v8; // edi
  DWORD v9; // r15d
  void *v10; // r13
  void *v11; // rbp
  unsigned int v12; // r14d
  DWORD LastError; // eax
  int v14; // r11d
  DWORD v15; // edi
  DWORD v16; // ebx
  DWORD v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  LPBOOL pbCancel; // [rsp+20h] [rbp-58h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-58h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  __int64 dwMilliseconds; // [rsp+A0h] [rbp+28h] BYREF
  va_list dwMillisecondsa; // [rsp+A0h] [rbp+28h]
  __int64 v28; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(dwMillisecondsa, a4);
  dwMilliseconds = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v28 = va_arg(va2, _QWORD);
  v4 = v28;
  if ( (v28 & 0xFFFFFFE0) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    v8 = 0;
    v9 = v28 & 1 | 0x1000;
    if ( (v28 & 8) == 0 )
      v9 = v28 & 1;
    v10 = (void *)PrepareUnicodePathEx(a1);
    if ( v10 )
    {
      v11 = (void *)PrepareUnicodePathEx(a2);
      if ( v11 )
      {
        v12 = 0;
        while ( 1 )
        {
          v8 = CopyFileExW(a1, a2, a3, a4, 0, v9);
          if ( v8 )
            break;
          if ( (v4 & 2) == 0 )
            goto LABEL_26;
          LastError = GetLastError();
          LODWORD(v28) = v8;
          LODWORD(dwMilliseconds) = v8;
          ++v12;
          if ( (unsigned int)WdsGetCopyRetryData(LastError, (__int64 *)va1, (__int64 *)dwMillisecondsa) )
          {
            if ( v12 >= (unsigned int)v28 )
              goto LABEL_26;
            v15 = dwMilliseconds;
          }
          else
          {
            if ( v12 >= 2 )
              goto LABEL_26;
            v15 = 3000;
          }
          LODWORD(v23) = v15;
          LODWORD(dwCopyFlags) = v14;
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms",
            a1,
            a2,
            dwCopyFlags,
            v23);
          if ( v15 )
            Sleep(v15);
        }
        if ( (v4 & 4) != 0 )
        {
          v8 = SetFileAttributesW(a2, 0x80u);
          if ( !v8 )
          {
            v16 = GetLastError();
            if ( !v16 )
              v16 = 31;
            LODWORD(pbCancel) = v16;
            LibLog(
              &g_WdsLibLog,
              0x2000000,
              L"WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x",
              a2,
              pbCancel);
            if ( !DeleteFileEx2((__int64)a2, 0) )
            {
              v17 = GetLastError();
              if ( !v17 )
                v17 = 31;
              LODWORD(pbCancela) = v17;
              LibLog(&g_WdsLibLog, 0x2000000, L"WdsCopyFileEx: Failed to delete %s. GLE = 0x%x", a2, pbCancela);
            }
            SetLastError(v16);
          }
        }
      }
LABEL_26:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
      if ( v11 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v11);
      }
    }
    return v8;
  }
}

```

## disassembly

```asm
0x18005efbc  mov     [rsp+arg_0], rbx
0x18005efc1  mov     [rsp+lpData], r9
0x18005efc6  mov     [rsp+lpProgressRoutine], r8
0x18005efcb  push    rbp
0x18005efcc  push    rsi
0x18005efcd  push    rdi
0x18005efce  push    r12
0x18005efd0  push    r13
0x18005efd2  push    r14
0x18005efd4  push    r15
0x18005efd6  sub     rsp, 40h
0x18005efda  mov     ebx, dword ptr [rsp+78h+arg_28]
0x18005efe1  mov     rsi, rdx
0x18005efe4  mov     r12, rcx
0x18005efe7  test    ebx, 0FFFFFFE0h
0x18005efed  jz      short loc_18005F001
0x18005efef  mov     ecx, 57h ; 'W'; dwErrCode
0x18005eff4  call    cs:__imp_SetLastError
0x18005effa  xor     eax, eax
0x18005effc  jmp     loc_18005F1DC
0x18005f001  mov     ecx, ebx
0x18005f003  xor     edi, edi
0x18005f005  and     ecx, 1
0x18005f008  mov     r15d, ecx
0x18005f00b  bts     r15d, 0Ch
0x18005f010  test    bl, 8
0x18005f013  cmovz   r15d, ecx
0x18005f017  xor     edx, edx
0x18005f019  mov     rcx, r12; unsigned __int16 *
0x18005f01c  call    PrepareUnicodePathEx
0x18005f021  mov     r13, rax
0x18005f024  test    rax, rax
0x18005f027  jz      loc_18005F1DA
0x18005f02d  xor     edx, edx
0x18005f02f  mov     rcx, rsi; unsigned __int16 *
0x18005f032  call    PrepareUnicodePathEx
0x18005f037  mov     rbp, rax
0x18005f03a  test    rax, rax
0x18005f03d  jz      loc_18005F1AD
0x18005f043  xor     r14d, r14d
0x18005f046  mov     r9, [rsp+78h+lpData]; lpData
0x18005f04e  mov     rdx, rsi; lpNewFileName
0x18005f051  mov     r8, [rsp+78h+lpProgressRoutine]; lpProgressRoutine
0x18005f059  mov     rcx, r12; lpExistingFileName
0x18005f05c  mov     dword ptr [rsp+78h+dwCopyFlags], r15d; dwCopyFlags
0x18005f061  mov     [rsp+78h+pbCancel], 0; pbCancel
0x18005f06a  call    cs:__imp_CopyFileExW
0x18005f070  mov     edi, eax
0x18005f072  test    eax, eax
0x18005f074  jnz     loc_18005F11C
0x18005f07a  test    bl, 2
0x18005f07d  jz      loc_18005F1AD
0x18005f083  call    cs:__imp_GetLastError
0x18005f089  lea     r8, [rsp+78h+dwMilliseconds]
0x18005f091  mov     dword ptr [rsp+78h+arg_28], edi
0x18005f098  mov     ecx, eax
0x18005f09a  mov     dword ptr [rsp+78h+dwMilliseconds], edi
0x18005f0a1  lea     rdx, [rsp+78h+arg_28]
0x18005f0a9  mov     r11d, eax
0x18005f0ac  inc     r14d
0x18005f0af  call    WdsGetCopyRetryData
0x18005f0b4  test    eax, eax
0x18005f0b6  jz      short loc_18005F0CF
0x18005f0b8  cmp     r14d, dword ptr [rsp+78h+arg_28]
0x18005f0c0  jnb     loc_18005F1AD
0x18005f0c6  mov     edi, dword ptr [rsp+78h+dwMilliseconds]
0x18005f0cd  jmp     short loc_18005F0DE
0x18005f0cf  cmp     r14d, 2
0x18005f0d3  jnb     loc_18005F1AD
0x18005f0d9  mov     edi, 0BB8h
0x18005f0de  mov     dword ptr [rsp+78h+var_48], edi
0x18005f0e2  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x18005f0e9  mov     dword ptr [rsp+78h+dwCopyFlags], r11d
0x18005f0ee  lea     rcx, g_WdsLibLog
0x18005f0f5  mov     r9, r12
0x18005f0f8  mov     [rsp+78h+pbCancel], rsi
0x18005f0fd  mov     edx, 4000000h
0x18005f102  call    LibLog
0x18005f107  test    edi, edi
0x18005f109  jz      loc_18005F046
0x18005f10f  mov     ecx, edi; dwMilliseconds
0x18005f111  call    cs:__imp_Sleep
0x18005f117  jmp     loc_18005F046
0x18005f11c  test    bl, 4
0x18005f11f  jz      loc_18005F1AD
0x18005f125  mov     edx, 80h; dwFileAttributes
0x18005f12a  mov     rcx, rsi; lpFileName
0x18005f12d  call    cs:__imp_SetFileAttributesW
0x18005f133  mov     edi, eax
0x18005f135  test    eax, eax
0x18005f137  jnz     short loc_18005F1AD
0x18005f139  call    cs:__imp_GetLastError
0x18005f13f  lea     r15d, [rdi+1Fh]
0x18005f143  mov     r14d, 2000000h
0x18005f149  test    eax, eax
0x18005f14b  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x18005f152  mov     ebx, eax
0x18005f154  lea     rcx, g_WdsLibLog
0x18005f15b  cmovz   ebx, r15d
0x18005f15f  mov     r9, rsi
0x18005f162  mov     edx, r14d
0x18005f165  mov     dword ptr [rsp+78h+pbCancel], ebx
0x18005f169  call    LibLog
0x18005f16e  xor     edx, edx
0x18005f170  mov     rcx, rsi
0x18005f173  call    DeleteFileEx2
0x18005f178  test    eax, eax
0x18005f17a  jnz     short loc_18005F1A5
0x18005f17c  call    cs:__imp_GetLastError
0x18005f182  mov     r9, rsi
0x18005f185  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x18005f18c  test    eax, eax
0x18005f18e  lea     rcx, g_WdsLibLog
0x18005f195  mov     edx, r14d
0x18005f198  cmovz   eax, r15d
0x18005f19c  mov     dword ptr [rsp+78h+pbCancel], eax
0x18005f1a0  call    LibLog
0x18005f1a5  mov     ecx, ebx; dwErrCode
0x18005f1a7  call    cs:__imp_SetLastError
0x18005f1ad  call    cs:__imp_GetProcessHeap
0x18005f1b3  mov     r8, r13; lpMem
0x18005f1b6  xor     edx, edx; dwFlags
0x18005f1b8  mov     rcx, rax; hHeap
0x18005f1bb  call    cs:__imp_HeapFree
0x18005f1c1  test    rbp, rbp
0x18005f1c4  jz      short loc_18005F1DA
0x18005f1c6  call    cs:__imp_GetProcessHeap
0x18005f1cc  mov     r8, rbp; lpMem
0x18005f1cf  xor     edx, edx; dwFlags
0x18005f1d1  mov     rcx, rax; hHeap
0x18005f1d4  call    cs:__imp_HeapFree
0x18005f1da  mov     eax, edi
0x18005f1dc  mov     rbx, [rsp+78h+arg_0]
0x18005f1e4  add     rsp, 40h
0x18005f1e8  pop     r15
0x18005f1ea  pop     r14
0x18005f1ec  pop     r13
0x18005f1ee  pop     r12
0x18005f1f0  pop     rdi
0x18005f1f1  pop     rsi
0x18005f1f2  pop     rbp
0x18005f1f3  retn
```
