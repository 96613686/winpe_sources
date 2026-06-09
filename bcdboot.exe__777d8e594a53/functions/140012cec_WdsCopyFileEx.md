# WdsCopyFileEx

- ea: `0x140012cec`
- end: `0x140012f01`
- name: `WdsCopyFileEx`
- size: `533`
- prototype: `__int64(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, __int64, __int64, int, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000bd28`

## callees

- `0x140011a88`
- `0x140011b18`
- `0x140012810`
- `0x140012cec`
- `0x140012f08`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140012d1b`
- `KERNEL32!SetLastError` at `0x140012ebb`
- `KERNEL32!SetLastError` at `0x140012d1b`
- `KERNEL32!SetLastError` at `0x140012ebb`
- `KERNEL32!GetLastError` at `0x140012d9f`
- `KERNEL32!GetLastError` at `0x140012e52`
- `KERNEL32!GetLastError` at `0x140012e91`
- `KERNEL32!GetLastError` at `0x140012d9f`
- `KERNEL32!GetLastError` at `0x140012e52`
- `KERNEL32!GetLastError` at `0x140012e91`
- `KERNEL32!HeapFree` at `0x140012ecf`
- `KERNEL32!HeapFree` at `0x140012ee8`
- `KERNEL32!HeapFree` at `0x140012ecf`
- `KERNEL32!HeapFree` at `0x140012ee8`
- `KERNEL32!GetProcessHeap` at `0x140012ec1`
- `KERNEL32!GetProcessHeap` at `0x140012eda`
- `KERNEL32!GetProcessHeap` at `0x140012ec1`
- `KERNEL32!GetProcessHeap` at `0x140012eda`
- `KERNEL32!Sleep` at `0x140012e2a`
- `KERNEL32!Sleep` at `0x140012e2a`
- `KERNEL32!SetFileAttributesW` at `0x140012e46`
- `KERNEL32!SetFileAttributesW` at `0x140012e46`
- `KERNEL32!CopyFileExW` at `0x140012d86`
- `KERNEL32!CopyFileExW` at `0x140012d86`

## string_xrefs

- `0x140012dfb`: `WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms`
- `0x140012e63`: `WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x`
- `0x140012e9a`: `WdsCopyFileEx: Failed to delete %s. GLE = 0x%x`

## pseudocode

```c
__int64 WdsCopyFileEx(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, __int64 a3, __int64 a4, int a5, ...)
{
  char v5; // bl
  unsigned int v9; // edi
  DWORD v10; // r15d
  void *v11; // r13
  void *v12; // r14
  unsigned int v13; // ebp
  DWORD LastError; // eax
  int v15; // r11d
  DWORD v16; // edi
  DWORD v17; // ebx
  DWORD v18; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  LPBOOL pbCancel; // [rsp+20h] [rbp-68h]
  LPBOOL pbCancela; // [rsp+20h] [rbp-68h]
  __int64 dwCopyFlags; // [rsp+28h] [rbp-60h]
  __int64 v24; // [rsp+30h] [rbp-58h]
  __int64 dwMilliseconds; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v26 = va_arg(va1, _QWORD);
  dwMilliseconds = a4;
  v5 = v26;
  if ( (v26 & 0xFFFFFFE0) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    v9 = 0;
    v10 = v26 & 1 | 0x1000;
    if ( (v26 & 8) == 0 )
      v10 = v26 & 1;
    v11 = (void *)PrepareUnicodePathEx(pszSrc);
    if ( v11 )
    {
      v12 = (void *)PrepareUnicodePathEx(a2);
      if ( v12 )
      {
        v13 = 0;
        while ( 1 )
        {
          v9 = CopyFileExW(pszSrc, a2, 0, 0, 0, v10);
          if ( v9 )
            break;
          if ( (v5 & 2) == 0 )
            goto LABEL_26;
          LastError = GetLastError();
          LODWORD(v26) = v9;
          LODWORD(dwMilliseconds) = v9;
          ++v13;
          if ( (unsigned int)WdsGetCopyRetryData(LastError, (__int64 *)va, &dwMilliseconds) )
          {
            if ( v13 >= (unsigned int)v26 )
              goto LABEL_26;
            v16 = dwMilliseconds;
          }
          else
          {
            if ( v13 >= 2 )
              goto LABEL_26;
            v16 = 3000;
          }
          LODWORD(v24) = v16;
          LODWORD(dwCopyFlags) = v15;
          LibLog(
            &g_WdsLibLog,
            0x4000000,
            L"WdsCopyFileEx: Failed to copy [%s] to [%s], GLE = 0x%x; will retry in %u ms",
            pszSrc,
            a2,
            dwCopyFlags,
            v24);
          if ( v16 )
            Sleep(v16);
        }
        if ( (v5 & 4) != 0 )
        {
          v9 = SetFileAttributesW(a2, 0x80u);
          if ( !v9 )
          {
            v17 = GetLastError();
            if ( !v17 )
              v17 = 31;
            LODWORD(pbCancel) = v17;
            LibLog(
              &g_WdsLibLog,
              0x2000000,
              L"WdsCopyFileEx: Failed to strip file attributes for %s, will delete. GLE = 0x%x",
              a2,
              pbCancel);
            if ( !(unsigned int)DeleteFileEx2(a2) )
            {
              v18 = GetLastError();
              if ( !v18 )
                v18 = 31;
              LODWORD(pbCancela) = v18;
              LibLog(&g_WdsLibLog, 0x2000000, L"WdsCopyFileEx: Failed to delete %s. GLE = 0x%x", a2, pbCancela);
            }
            SetLastError(v17);
          }
        }
      }
LABEL_26:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      if ( v12 )
      {
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v12);
      }
    }
    return v9;
  }
}

```

## disassembly

```asm
0x140012cec  mov     [rsp+dwMilliseconds], r9
0x140012cf1  push    rbx
0x140012cf2  push    rbp
0x140012cf3  push    rsi
0x140012cf4  push    rdi
0x140012cf5  push    r12
0x140012cf7  push    r13
0x140012cf9  push    r14
0x140012cfb  push    r15
0x140012cfd  sub     rsp, 48h
0x140012d01  mov     ebx, dword ptr [rsp+88h+arg_28]
0x140012d08  mov     rsi, rdx
0x140012d0b  mov     r12, rcx
0x140012d0e  test    ebx, 0FFFFFFE0h
0x140012d14  jz      short loc_140012D28
0x140012d16  mov     ecx, 57h ; 'W'; dwErrCode
0x140012d1b  call    cs:__imp_SetLastError
0x140012d21  xor     eax, eax
0x140012d23  jmp     loc_140012EF0
0x140012d28  mov     ecx, ebx
0x140012d2a  xor     edi, edi
0x140012d2c  and     ecx, 1
0x140012d2f  mov     r15d, ecx
0x140012d32  bts     r15d, 0Ch
0x140012d37  test    bl, 8
0x140012d3a  cmovz   r15d, ecx
0x140012d3e  xor     edx, edx
0x140012d40  mov     rcx, r12; pszSrc
0x140012d43  call    PrepareUnicodePathEx
0x140012d48  mov     r13, rax
0x140012d4b  test    rax, rax
0x140012d4e  jz      loc_140012EEE
0x140012d54  xor     edx, edx
0x140012d56  mov     rcx, rsi; pszSrc
0x140012d59  call    PrepareUnicodePathEx
0x140012d5e  mov     r14, rax
0x140012d61  test    rax, rax
0x140012d64  jz      loc_140012EC1
0x140012d6a  xor     ebp, ebp
0x140012d6c  mov     dword ptr [rsp+88h+dwCopyFlags], r15d; dwCopyFlags
0x140012d71  xor     r9d, r9d; lpData
0x140012d74  xor     r8d, r8d; lpProgressRoutine
0x140012d77  mov     [rsp+88h+pbCancel], 0; pbCancel
0x140012d80  mov     rdx, rsi; lpNewFileName
0x140012d83  mov     rcx, r12; lpExistingFileName
0x140012d86  call    cs:__imp_CopyFileExW
0x140012d8c  mov     edi, eax
0x140012d8e  test    eax, eax
0x140012d90  jnz     loc_140012E35
0x140012d96  test    bl, 2
0x140012d99  jz      loc_140012EC1
0x140012d9f  call    cs:__imp_GetLastError
0x140012da5  lea     r8, [rsp+88h+dwMilliseconds]
0x140012dad  mov     dword ptr [rsp+88h+arg_28], edi
0x140012db4  mov     ecx, eax
0x140012db6  mov     dword ptr [rsp+88h+dwMilliseconds], edi
0x140012dbd  lea     rdx, [rsp+88h+arg_28]
0x140012dc5  mov     r11d, eax
0x140012dc8  inc     ebp
0x140012dca  call    WdsGetCopyRetryData
0x140012dcf  test    eax, eax
0x140012dd1  jz      short loc_140012DE9
0x140012dd3  cmp     ebp, dword ptr [rsp+88h+arg_28]
0x140012dda  jnb     loc_140012EC1
0x140012de0  mov     edi, dword ptr [rsp+88h+dwMilliseconds]
0x140012de7  jmp     short loc_140012DF7
0x140012de9  cmp     ebp, 2
0x140012dec  jnb     loc_140012EC1
0x140012df2  mov     edi, 0BB8h
0x140012df7  mov     dword ptr [rsp+88h+var_58], edi
0x140012dfb  lea     r8, aWdscopyfileexF_0; "WdsCopyFileEx: Failed to copy [%s] to ["...
0x140012e02  mov     dword ptr [rsp+88h+dwCopyFlags], r11d
0x140012e07  lea     rcx, g_WdsLibLog
0x140012e0e  mov     r9, r12
0x140012e11  mov     [rsp+88h+pbCancel], rsi
0x140012e16  mov     edx, 4000000h
0x140012e1b  call    LibLog
0x140012e20  test    edi, edi
0x140012e22  jz      loc_140012D6C
0x140012e28  mov     ecx, edi; dwMilliseconds
0x140012e2a  call    cs:__imp_Sleep
0x140012e30  jmp     loc_140012D6C
0x140012e35  test    bl, 4
0x140012e38  jz      loc_140012EC1
0x140012e3e  mov     edx, 80h; dwFileAttributes
0x140012e43  mov     rcx, rsi; lpFileName
0x140012e46  call    cs:__imp_SetFileAttributesW
0x140012e4c  mov     edi, eax
0x140012e4e  test    eax, eax
0x140012e50  jnz     short loc_140012EC1
0x140012e52  call    cs:__imp_GetLastError
0x140012e58  lea     r15d, [rdi+1Fh]
0x140012e5c  mov     ebp, 2000000h
0x140012e61  test    eax, eax
0x140012e63  lea     r8, aWdscopyfileexF_1; "WdsCopyFileEx: Failed to strip file att"...
0x140012e6a  mov     ebx, eax
0x140012e6c  lea     rcx, g_WdsLibLog
0x140012e73  cmovz   ebx, r15d
0x140012e77  mov     r9, rsi
0x140012e7a  mov     edx, ebp
0x140012e7c  mov     dword ptr [rsp+88h+pbCancel], ebx
0x140012e80  call    LibLog
0x140012e85  mov     rcx, rsi
0x140012e88  call    DeleteFileEx2
0x140012e8d  test    eax, eax
0x140012e8f  jnz     short loc_140012EB9
0x140012e91  call    cs:__imp_GetLastError
0x140012e97  mov     r9, rsi
0x140012e9a  lea     r8, aWdscopyfileexF; "WdsCopyFileEx: Failed to delete %s. GLE"...
0x140012ea1  test    eax, eax
0x140012ea3  lea     rcx, g_WdsLibLog
0x140012eaa  mov     edx, ebp
0x140012eac  cmovz   eax, r15d
0x140012eb0  mov     dword ptr [rsp+88h+pbCancel], eax
0x140012eb4  call    LibLog
0x140012eb9  mov     ecx, ebx; dwErrCode
0x140012ebb  call    cs:__imp_SetLastError
0x140012ec1  call    cs:__imp_GetProcessHeap
0x140012ec7  mov     r8, r13; lpMem
0x140012eca  xor     edx, edx; dwFlags
0x140012ecc  mov     rcx, rax; hHeap
0x140012ecf  call    cs:__imp_HeapFree
0x140012ed5  test    r14, r14
0x140012ed8  jz      short loc_140012EEE
0x140012eda  call    cs:__imp_GetProcessHeap
0x140012ee0  mov     r8, r14; lpMem
0x140012ee3  xor     edx, edx; dwFlags
0x140012ee5  mov     rcx, rax; hHeap
0x140012ee8  call    cs:__imp_HeapFree
0x140012eee  mov     eax, edi
0x140012ef0  add     rsp, 48h
0x140012ef4  pop     r15
0x140012ef6  pop     r14
0x140012ef8  pop     r13
0x140012efa  pop     r12
0x140012efc  pop     rdi
0x140012efd  pop     rsi
0x140012efe  pop     rbp
0x140012eff  pop     rbx
0x140012f00  retn
```
