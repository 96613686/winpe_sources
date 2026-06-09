# WdsCopyFileEx

- ea: `0x180053e6c`
- end: `0x180054072`
- name: `WdsCopyFileEx`
- size: `518`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800538b8`

## callees

- `0x180053020`
- `0x180053040`
- `0x180053234`
- `0x180053994`
- `0x180053e6c`
- `0x180054078`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053fae`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053fae`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180053fc6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180053fc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054059`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005404b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054032`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005404b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005402c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005402c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f20`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180053f07`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180053f07`

## string_xrefs

- `0x180053fe4`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x180053f7f`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`
- `0x180054014`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`

## pseudocode

```c
__int64 WdsCopyFileEx(unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, __int64 a4, int a5, ...)
{
  char v5; // bl
  unsigned int v9; // esi
  DWORD v10; // r15d
  void *v11; // r13
  void *v12; // rbp
  unsigned int v13; // r14d
  DWORD LastError; // eax
  int v15; // r11d
  DWORD v16; // esi
  DWORD v17; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  LPBOOL pbCancel; // [rsp+20h] [rbp-68h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-68h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-60h]
  __int64 v23; // [rsp+30h] [rbp-58h]
  __int64 dwMilliseconds; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v25 = va_arg(va1, _QWORD);
  dwMilliseconds = a4;
  v5 = v25;
  if ( (v25 & 0xFFFFFFE0) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    v9 = 0;
    v10 = v25 & 1 | 0x1000;
    if ( (v25 & 8) == 0 )
      v10 = v25 & 1;
    v11 = (void *)PrepareUnicodePathEx(a1);
    if ( v11 )
    {
      v12 = (void *)PrepareUnicodePathEx(a2);
      if ( v12 )
      {
        v13 = 0;
        while ( 1 )
        {
          v9 = CopyFileExW(a1, a2, 0, 0, 0, v10);
          if ( v9 )
            break;
          if ( (v5 & 2) == 0 )
            goto LABEL_22;
          LastError = GetLastError();
          LODWORD(v25) = v9;
          LODWORD(dwMilliseconds) = v9;
          ++v13;
          if ( (unsigned int)WdsGetCopyRetryData(LastError, (__int64 *)va, &dwMilliseconds) )
          {
            if ( v13 >= (unsigned int)v25 )
              goto LABEL_22;
            v16 = dwMilliseconds;
          }
          else
          {
            if ( v13 >= 2 )
              goto LABEL_22;
            v16 = 3000;
          }
          LODWORD(v23) = v16;
          LODWORD(dwCopyFlags) = v15;
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms",
            a1,
            a2,
            dwCopyFlags,
            v23);
          if ( v16 )
            Sleep(v16);
        }
        if ( (v5 & 4) != 0 )
        {
          v9 = SetFileAttributesW(a2, 0x80u);
          if ( !v9 )
          {
            LODWORD(pbCancel) = GET_LASTERROR_FORCE();
            v17 = (unsigned int)pbCancel;
            LibLog(
              &g_WdsLibLog,
              0x2000000,
              L"WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x",
              a2,
              pbCancel);
            if ( !DeleteFileEx2((__int64)a2) )
            {
              LODWORD(pbCancela) = GET_LASTERROR_FORCE();
              LibLog(&g_WdsLibLog, 0x2000000, L"WdsCopyFileEx: Failed to delete %s. GLE = 0x%x", a2, pbCancela);
            }
            SetLastError(v17);
          }
        }
      }
LABEL_22:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      if ( v12 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v12);
      }
    }
    return v9;
  }
}

```

## disassembly

```asm
0x180053e6c  mov     [rsp+dwMilliseconds], r9
0x180053e71  push    rbx
0x180053e72  push    rbp
0x180053e73  push    rsi
0x180053e74  push    rdi
0x180053e75  push    r12
0x180053e77  push    r13
0x180053e79  push    r14
0x180053e7b  push    r15
0x180053e7d  sub     rsp, 48h
0x180053e81  mov     ebx, dword ptr [rsp+88h+arg_28]
0x180053e88  mov     rdi, rdx
0x180053e8b  mov     r12, rcx
0x180053e8e  test    ebx, 0FFFFFFE0h
0x180053e94  jz      short loc_180053EA8
0x180053e96  mov     ecx, 57h ; 'W'; dwErrCode
0x180053e9b  call    cs:__imp_SetLastError
0x180053ea1  xor     eax, eax
0x180053ea3  jmp     loc_180054061
0x180053ea8  mov     ecx, ebx
0x180053eaa  xor     esi, esi
0x180053eac  and     ecx, 1
0x180053eaf  mov     r15d, ecx
0x180053eb2  bts     r15d, 0Ch
0x180053eb7  test    bl, 8
0x180053eba  cmovz   r15d, ecx
0x180053ebe  xor     edx, edx
0x180053ec0  mov     rcx, r12; unsigned __int16 *
0x180053ec3  call    PrepareUnicodePathEx
0x180053ec8  mov     r13, rax
0x180053ecb  test    rax, rax
0x180053ece  jz      loc_18005405F
0x180053ed4  xor     edx, edx
0x180053ed6  mov     rcx, rdi; unsigned __int16 *
0x180053ed9  call    PrepareUnicodePathEx
0x180053ede  mov     rbp, rax
0x180053ee1  test    rax, rax
0x180053ee4  jz      loc_180054032
0x180053eea  xor     r14d, r14d
0x180053eed  mov     dword ptr [rsp+88h+dwCopyFlags], r15d; dwCopyFlags
0x180053ef2  xor     r9d, r9d; lpData
0x180053ef5  xor     r8d, r8d; lpProgressRoutine
0x180053ef8  mov     [rsp+88h+pbCancel], 0; pbCancel
0x180053f01  mov     rdx, rdi; lpNewFileName
0x180053f04  mov     rcx, r12; lpExistingFileName
0x180053f07  call    cs:__imp_CopyFileExW
0x180053f0d  mov     esi, eax
0x180053f0f  test    eax, eax
0x180053f11  jnz     loc_180053FB9
0x180053f17  test    bl, 2
0x180053f1a  jz      loc_180054032
0x180053f20  call    cs:__imp_GetLastError
0x180053f26  lea     r8, [rsp+88h+dwMilliseconds]
0x180053f2e  mov     dword ptr [rsp+88h+arg_28], esi
0x180053f35  mov     ecx, eax
0x180053f37  mov     dword ptr [rsp+88h+dwMilliseconds], esi
0x180053f3e  lea     rdx, [rsp+88h+arg_28]
0x180053f46  mov     r11d, eax
0x180053f49  inc     r14d
0x180053f4c  call    WdsGetCopyRetryData
0x180053f51  test    eax, eax
0x180053f53  jz      short loc_180053F6C
0x180053f55  cmp     r14d, dword ptr [rsp+88h+arg_28]
0x180053f5d  jnb     loc_180054032
0x180053f63  mov     esi, dword ptr [rsp+88h+dwMilliseconds]
0x180053f6a  jmp     short loc_180053F7B
0x180053f6c  cmp     r14d, 2
0x180053f70  jnb     loc_180054032
0x180053f76  mov     esi, 0BB8h
0x180053f7b  mov     dword ptr [rsp+88h+var_58], esi
0x180053f7f  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x180053f86  mov     dword ptr [rsp+88h+dwCopyFlags], r11d
0x180053f8b  lea     rcx, g_WdsLibLog
0x180053f92  mov     r9, r12
0x180053f95  mov     [rsp+88h+pbCancel], rdi
0x180053f9a  mov     edx, 4000000h
0x180053f9f  call    LibLog
0x180053fa4  test    esi, esi
0x180053fa6  jz      loc_180053EED
0x180053fac  mov     ecx, esi; dwMilliseconds
0x180053fae  call    cs:__imp_Sleep
0x180053fb4  jmp     loc_180053EED
0x180053fb9  test    bl, 4
0x180053fbc  jz      short loc_180054032
0x180053fbe  mov     edx, 80h; dwFileAttributes
0x180053fc3  mov     rcx, rdi; lpFileName
0x180053fc6  call    cs:__imp_SetFileAttributesW
0x180053fcc  mov     esi, eax
0x180053fce  test    eax, eax
0x180053fd0  jnz     short loc_180054032
0x180053fd2  call    GET_LASTERROR_FORCE
0x180053fd7  mov     r14d, 2000000h
0x180053fdd  mov     dword ptr [rsp+88h+pbCancel], eax
0x180053fe1  mov     edx, r14d
0x180053fe4  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x180053feb  mov     r9, rdi
0x180053fee  lea     rcx, g_WdsLibLog
0x180053ff5  mov     ebx, eax
0x180053ff7  call    LibLog
0x180053ffc  mov     rcx, rdi
0x180053fff  call    DeleteFileEx2
0x180054004  test    eax, eax
0x180054006  jnz     short loc_18005402A
0x180054008  call    GET_LASTERROR_FORCE
0x18005400d  mov     r9, rdi
0x180054010  mov     dword ptr [rsp+88h+pbCancel], eax
0x180054014  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x18005401b  mov     edx, r14d
0x18005401e  lea     rcx, g_WdsLibLog
0x180054025  call    LibLog
0x18005402a  mov     ecx, ebx; dwErrCode
0x18005402c  call    cs:__imp_SetLastError
0x180054032  call    cs:__imp_GetProcessHeap
0x180054038  mov     r8, r13; lpMem
0x18005403b  xor     edx, edx; dwFlags
0x18005403d  mov     rcx, rax; hHeap
0x180054040  call    cs:__imp_HeapFree
0x180054046  test    rbp, rbp
0x180054049  jz      short loc_18005405F
0x18005404b  call    cs:__imp_GetProcessHeap
0x180054051  mov     r8, rbp; lpMem
0x180054054  xor     edx, edx; dwFlags
0x180054056  mov     rcx, rax; hHeap
0x180054059  call    cs:__imp_HeapFree
0x18005405f  mov     eax, esi
0x180054061  add     rsp, 48h
0x180054065  pop     r15
0x180054067  pop     r14
0x180054069  pop     r13
0x18005406b  pop     r12
0x18005406d  pop     rdi
0x18005406e  pop     rsi
0x18005406f  pop     rbp
0x180054070  pop     rbx
0x180054071  retn
```
