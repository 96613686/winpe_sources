# WdsCopyFileEx

- ea: `0x180223f9c`
- end: `0x180224221`
- name: `WdsCopyFileEx`
- size: `645`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, wchar_t *@<rdx>, DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1802235c4`

## callees

- `0x180222764`
- `0x1802227f8`
- `0x1802236ec`
- `0x180223f9c`
- `0x180224228`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180224125`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180224125`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180224050`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180224050`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180224103`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180224103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802241c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802241e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802241c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802241e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802241d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802241fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802241d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802241fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180223fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802241b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180223fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802241b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022406f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022413b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180224184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022406f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022413b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180224184`

## string_xrefs

- `0x1802240d4`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`
- `0x180224153`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x180224193`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`

## pseudocode

```c
__int64 WdsCopyFileEx(
        wchar_t *a1,
        wchar_t *a2,
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
0x180223f9c  mov     [rsp+arg_0], rbx
0x180223fa1  mov     [rsp+lpData], r9
0x180223fa6  mov     [rsp+lpProgressRoutine], r8
0x180223fab  push    rbp
0x180223fac  push    rsi
0x180223fad  push    rdi
0x180223fae  push    r12
0x180223fb0  push    r13
0x180223fb2  push    r14
0x180223fb4  push    r15
0x180223fb6  sub     rsp, 40h
0x180223fba  mov     ebx, dword ptr [rsp+78h+arg_28]
0x180223fc1  mov     rsi, rdx
0x180223fc4  mov     r12, rcx
0x180223fc7  test    ebx, 0FFFFFFE0h
0x180223fcd  jz      short loc_180223FE7
0x180223fcf  mov     ecx, 57h ; 'W'; dwErrCode
0x180223fd4  call    cs:__imp_SetLastError
0x180223fdb  nop     dword ptr [rax+rax+00h]
0x180223fe0  xor     eax, eax
0x180223fe2  jmp     loc_180224208
0x180223fe7  mov     ecx, ebx
0x180223fe9  xor     edi, edi
0x180223feb  and     ecx, 1
0x180223fee  mov     r15d, ecx
0x180223ff1  bts     r15d, 0Ch
0x180223ff6  test    bl, 8
0x180223ff9  cmovz   r15d, ecx
0x180223ffd  xor     edx, edx
0x180223fff  mov     rcx, r12; wchar_t *
0x180224002  call    PrepareUnicodePathEx
0x180224007  mov     r13, rax
0x18022400a  test    rax, rax
0x18022400d  jz      loc_180224206
0x180224013  xor     edx, edx
0x180224015  mov     rcx, rsi; wchar_t *
0x180224018  call    PrepareUnicodePathEx
0x18022401d  mov     rbp, rax
0x180224020  test    rax, rax
0x180224023  jz      loc_1802241C1
0x180224029  xor     r14d, r14d
0x18022402c  mov     r9, [rsp+78h+lpData]; lpData
0x180224034  mov     rdx, rsi; lpNewFileName
0x180224037  mov     r8, [rsp+78h+lpProgressRoutine]; lpProgressRoutine
0x18022403f  mov     rcx, r12; lpExistingFileName
0x180224042  mov     dword ptr [rsp+78h+dwCopyFlags], r15d; dwCopyFlags
0x180224047  mov     [rsp+78h+pbCancel], 0; pbCancel
0x180224050  call    cs:__imp_CopyFileExW
0x180224057  nop     dword ptr [rax+rax+00h]
0x18022405c  mov     edi, eax
0x18022405e  test    eax, eax
0x180224060  jnz     loc_180224114
0x180224066  test    bl, 2
0x180224069  jz      loc_1802241C1
0x18022406f  call    cs:__imp_GetLastError
0x180224076  nop     dword ptr [rax+rax+00h]
0x18022407b  lea     r8, [rsp+78h+dwMilliseconds]
0x180224083  mov     dword ptr [rsp+78h+arg_28], edi
0x18022408a  mov     ecx, eax
0x18022408c  mov     dword ptr [rsp+78h+dwMilliseconds], edi
0x180224093  lea     rdx, [rsp+78h+arg_28]
0x18022409b  mov     r11d, eax
0x18022409e  inc     r14d
0x1802240a1  call    WdsGetCopyRetryData
0x1802240a6  test    eax, eax
0x1802240a8  jz      short loc_1802240C1
0x1802240aa  cmp     r14d, dword ptr [rsp+78h+arg_28]
0x1802240b2  jnb     loc_1802241C1
0x1802240b8  mov     edi, dword ptr [rsp+78h+dwMilliseconds]
0x1802240bf  jmp     short loc_1802240D0
0x1802240c1  cmp     r14d, 2
0x1802240c5  jnb     loc_1802241C1
0x1802240cb  mov     edi, 0BB8h
0x1802240d0  mov     dword ptr [rsp+78h+var_48], edi
0x1802240d4  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x1802240db  mov     dword ptr [rsp+78h+dwCopyFlags], r11d
0x1802240e0  lea     rcx, g_WdsLibLog
0x1802240e7  mov     r9, r12
0x1802240ea  mov     [rsp+78h+pbCancel], rsi
0x1802240ef  mov     edx, 4000000h
0x1802240f4  call    LibLog
0x1802240f9  test    edi, edi
0x1802240fb  jz      loc_18022402C
0x180224101  mov     ecx, edi; dwMilliseconds
0x180224103  call    cs:__imp_Sleep
0x18022410a  nop     dword ptr [rax+rax+00h]
0x18022410f  jmp     loc_18022402C
0x180224114  test    bl, 4
0x180224117  jz      loc_1802241C1
0x18022411d  mov     edx, 80h; dwFileAttributes
0x180224122  mov     rcx, rsi; lpFileName
0x180224125  call    cs:__imp_SetFileAttributesW
0x18022412c  nop     dword ptr [rax+rax+00h]
0x180224131  mov     edi, eax
0x180224133  test    eax, eax
0x180224135  jnz     loc_1802241C1
0x18022413b  call    cs:__imp_GetLastError
0x180224142  nop     dword ptr [rax+rax+00h]
0x180224147  lea     r15d, [rdi+1Fh]
0x18022414b  mov     r14d, 2000000h
0x180224151  test    eax, eax
0x180224153  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x18022415a  mov     ebx, eax
0x18022415c  lea     rcx, g_WdsLibLog
0x180224163  cmovz   ebx, r15d
0x180224167  mov     r9, rsi
0x18022416a  mov     edx, r14d
0x18022416d  mov     dword ptr [rsp+78h+pbCancel], ebx
0x180224171  call    LibLog
0x180224176  xor     edx, edx
0x180224178  mov     rcx, rsi
0x18022417b  call    DeleteFileEx2
0x180224180  test    eax, eax
0x180224182  jnz     short loc_1802241B3
0x180224184  call    cs:__imp_GetLastError
0x18022418b  nop     dword ptr [rax+rax+00h]
0x180224190  mov     r9, rsi
0x180224193  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x18022419a  test    eax, eax
0x18022419c  lea     rcx, g_WdsLibLog
0x1802241a3  mov     edx, r14d
0x1802241a6  cmovz   eax, r15d
0x1802241aa  mov     dword ptr [rsp+78h+pbCancel], eax
0x1802241ae  call    LibLog
0x1802241b3  mov     ecx, ebx; dwErrCode
0x1802241b5  call    cs:__imp_SetLastError
0x1802241bc  nop     dword ptr [rax+rax+00h]
0x1802241c1  call    cs:__imp_GetProcessHeap
0x1802241c8  nop     dword ptr [rax+rax+00h]
0x1802241cd  mov     r8, r13; lpMem
0x1802241d0  xor     edx, edx; dwFlags
0x1802241d2  mov     rcx, rax; hHeap
0x1802241d5  call    cs:__imp_HeapFree
0x1802241dc  nop     dword ptr [rax+rax+00h]
0x1802241e1  test    rbp, rbp
0x1802241e4  jz      short loc_180224206
0x1802241e6  call    cs:__imp_GetProcessHeap
0x1802241ed  nop     dword ptr [rax+rax+00h]
0x1802241f2  mov     r8, rbp; lpMem
0x1802241f5  xor     edx, edx; dwFlags
0x1802241f7  mov     rcx, rax; hHeap
0x1802241fa  call    cs:__imp_HeapFree
0x180224201  nop     dword ptr [rax+rax+00h]
0x180224206  mov     eax, edi
0x180224208  mov     rbx, [rsp+78h+arg_0]
0x180224210  add     rsp, 40h
0x180224214  pop     r15
0x180224216  pop     r14
0x180224218  pop     r13
0x18022421a  pop     r12
0x18022421c  pop     rdi
0x18022421d  pop     rsi
0x18022421e  pop     rbp
0x18022421f  retn
```
