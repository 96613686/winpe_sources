# WdsCopyFileEx

- ea: `0x180063f08`
- end: `0x18006418d`
- name: `WdsCopyFileEx`
- size: `645`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180063410`

## callees

- `0x180063538`
- `0x180063df0`
- `0x180063f08`
- `0x180064194`
- `0x180064e8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006412d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006412d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064121`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006406f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006406f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180064091`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180064091`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180063fbc`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180063fbc`

## string_xrefs

- `0x1800640ff`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`
- `0x1800640bf`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x180064040`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`

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
0x180063f08  mov     [rsp+arg_0], rbx
0x180063f0d  mov     [rsp+lpData], r9
0x180063f12  mov     [rsp+lpProgressRoutine], r8
0x180063f17  push    rbp
0x180063f18  push    rsi
0x180063f19  push    rdi
0x180063f1a  push    r12
0x180063f1c  push    r13
0x180063f1e  push    r14
0x180063f20  push    r15
0x180063f22  sub     rsp, 40h
0x180063f26  mov     ebx, dword ptr [rsp+78h+arg_28]
0x180063f2d  mov     rsi, rdx
0x180063f30  mov     r12, rcx
0x180063f33  test    ebx, 0FFFFFFE0h
0x180063f39  jz      short loc_180063F53
0x180063f3b  mov     ecx, 57h ; 'W'; dwErrCode
0x180063f40  call    cs:__imp_SetLastError
0x180063f47  nop     dword ptr [rax+rax+00h]
0x180063f4c  xor     eax, eax
0x180063f4e  jmp     loc_180064174
0x180063f53  mov     ecx, ebx
0x180063f55  xor     edi, edi
0x180063f57  and     ecx, 1
0x180063f5a  mov     r15d, ecx
0x180063f5d  bts     r15d, 0Ch
0x180063f62  test    bl, 8
0x180063f65  cmovz   r15d, ecx
0x180063f69  xor     edx, edx
0x180063f6b  mov     rcx, r12; unsigned __int16 *
0x180063f6e  call    PrepareUnicodePathEx
0x180063f73  mov     r13, rax
0x180063f76  test    rax, rax
0x180063f79  jz      loc_180064172
0x180063f7f  xor     edx, edx
0x180063f81  mov     rcx, rsi; unsigned __int16 *
0x180063f84  call    PrepareUnicodePathEx
0x180063f89  mov     rbp, rax
0x180063f8c  test    rax, rax
0x180063f8f  jz      loc_18006412D
0x180063f95  xor     r14d, r14d
0x180063f98  mov     r9, [rsp+78h+lpData]; lpData
0x180063fa0  mov     rdx, rsi; lpNewFileName
0x180063fa3  mov     r8, [rsp+78h+lpProgressRoutine]; lpProgressRoutine
0x180063fab  mov     rcx, r12; lpExistingFileName
0x180063fae  mov     dword ptr [rsp+78h+dwCopyFlags], r15d; dwCopyFlags
0x180063fb3  mov     [rsp+78h+pbCancel], 0; pbCancel
0x180063fbc  call    cs:__imp_CopyFileExW
0x180063fc3  nop     dword ptr [rax+rax+00h]
0x180063fc8  mov     edi, eax
0x180063fca  test    eax, eax
0x180063fcc  jnz     loc_180064080
0x180063fd2  test    bl, 2
0x180063fd5  jz      loc_18006412D
0x180063fdb  call    cs:__imp_GetLastError
0x180063fe2  nop     dword ptr [rax+rax+00h]
0x180063fe7  lea     r8, [rsp+78h+dwMilliseconds]
0x180063fef  mov     dword ptr [rsp+78h+arg_28], edi
0x180063ff6  mov     ecx, eax
0x180063ff8  mov     dword ptr [rsp+78h+dwMilliseconds], edi
0x180063fff  lea     rdx, [rsp+78h+arg_28]
0x180064007  mov     r11d, eax
0x18006400a  inc     r14d
0x18006400d  call    WdsGetCopyRetryData
0x180064012  test    eax, eax
0x180064014  jz      short loc_18006402D
0x180064016  cmp     r14d, dword ptr [rsp+78h+arg_28]
0x18006401e  jnb     loc_18006412D
0x180064024  mov     edi, dword ptr [rsp+78h+dwMilliseconds]
0x18006402b  jmp     short loc_18006403C
0x18006402d  cmp     r14d, 2
0x180064031  jnb     loc_18006412D
0x180064037  mov     edi, 0BB8h
0x18006403c  mov     dword ptr [rsp+78h+var_48], edi
0x180064040  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x180064047  mov     dword ptr [rsp+78h+dwCopyFlags], r11d
0x18006404c  lea     rcx, g_WdsLibLog
0x180064053  mov     r9, r12
0x180064056  mov     [rsp+78h+pbCancel], rsi
0x18006405b  mov     edx, 4000000h
0x180064060  call    LibLog
0x180064065  test    edi, edi
0x180064067  jz      loc_180063F98
0x18006406d  mov     ecx, edi; dwMilliseconds
0x18006406f  call    cs:__imp_Sleep
0x180064076  nop     dword ptr [rax+rax+00h]
0x18006407b  jmp     loc_180063F98
0x180064080  test    bl, 4
0x180064083  jz      loc_18006412D
0x180064089  mov     edx, 80h; dwFileAttributes
0x18006408e  mov     rcx, rsi; lpFileName
0x180064091  call    cs:__imp_SetFileAttributesW
0x180064098  nop     dword ptr [rax+rax+00h]
0x18006409d  mov     edi, eax
0x18006409f  test    eax, eax
0x1800640a1  jnz     loc_18006412D
0x1800640a7  call    cs:__imp_GetLastError
0x1800640ae  nop     dword ptr [rax+rax+00h]
0x1800640b3  lea     r15d, [rdi+1Fh]
0x1800640b7  mov     r14d, 2000000h
0x1800640bd  test    eax, eax
0x1800640bf  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x1800640c6  mov     ebx, eax
0x1800640c8  lea     rcx, g_WdsLibLog
0x1800640cf  cmovz   ebx, r15d
0x1800640d3  mov     r9, rsi
0x1800640d6  mov     edx, r14d
0x1800640d9  mov     dword ptr [rsp+78h+pbCancel], ebx
0x1800640dd  call    LibLog
0x1800640e2  xor     edx, edx
0x1800640e4  mov     rcx, rsi
0x1800640e7  call    DeleteFileEx2
0x1800640ec  test    eax, eax
0x1800640ee  jnz     short loc_18006411F
0x1800640f0  call    cs:__imp_GetLastError
0x1800640f7  nop     dword ptr [rax+rax+00h]
0x1800640fc  mov     r9, rsi
0x1800640ff  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x180064106  test    eax, eax
0x180064108  lea     rcx, g_WdsLibLog
0x18006410f  mov     edx, r14d
0x180064112  cmovz   eax, r15d
0x180064116  mov     dword ptr [rsp+78h+pbCancel], eax
0x18006411a  call    LibLog
0x18006411f  mov     ecx, ebx; dwErrCode
0x180064121  call    cs:__imp_SetLastError
0x180064128  nop     dword ptr [rax+rax+00h]
0x18006412d  call    cs:__imp_GetProcessHeap
0x180064134  nop     dword ptr [rax+rax+00h]
0x180064139  mov     r8, r13; lpMem
0x18006413c  xor     edx, edx; dwFlags
0x18006413e  mov     rcx, rax; hHeap
0x180064141  call    cs:__imp_HeapFree
0x180064148  nop     dword ptr [rax+rax+00h]
0x18006414d  test    rbp, rbp
0x180064150  jz      short loc_180064172
0x180064152  call    cs:__imp_GetProcessHeap
0x180064159  nop     dword ptr [rax+rax+00h]
0x18006415e  mov     r8, rbp; lpMem
0x180064161  xor     edx, edx; dwFlags
0x180064163  mov     rcx, rax; hHeap
0x180064166  call    cs:__imp_HeapFree
0x18006416d  nop     dword ptr [rax+rax+00h]
0x180064172  mov     eax, edi
0x180064174  mov     rbx, [rsp+78h+arg_0]
0x18006417c  add     rsp, 40h
0x180064180  pop     r15
0x180064182  pop     r14
0x180064184  pop     r13
0x180064186  pop     r12
0x180064188  pop     rdi
0x180064189  pop     rsi
0x18006418a  pop     rbp
0x18006418b  retn
```
