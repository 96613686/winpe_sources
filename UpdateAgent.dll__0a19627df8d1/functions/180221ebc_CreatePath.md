# CreatePath

- ea: `0x180221ebc`
- end: `0x1802220ef`
- name: `CreatePath`
- size: `563`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180224b80`
- `0x180224cf4`
- `0x1802266e4`
- `0x1802268a0`

## callees

- `0x180221ebc`
- `0x180222764`
- `0x1802227f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180221f3f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180221f3f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180221f63`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180221ff5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180221f63`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180221ff5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180222029`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180222029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022207d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022207d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180222091`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180221fa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802220af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802220c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180221fa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802220af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802220c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022209f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180222056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022209f`

## string_xrefs

- `0x18022201d`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x180221fe9`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x180221f94`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18022204a`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180222065`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(wchar_t *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  wchar_t *v9; // r9
  const wchar_t *v10; // r8
  DWORD FileAttributesW; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // [rsp+20h] [rbp-38h]
  wchar_t *v15; // [rsp+60h] [rbp+8h]

  if ( a1 && *a1 )
  {
    v2 = (WCHAR *)PrepareUnicodePathEx(a1);
    if ( v2 )
    {
      v3 = 0;
      v4 = 1;
      v5 = v2;
      while ( 1 )
      {
        v6 = wcschr(v5, 0x5Cu);
        v15 = v6;
        if ( !v6 )
          break;
        *v6 = 0;
        if ( !CreateDirectoryW(v2, 0) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError == 5 || LastError == 183 )
          {
            v3 = 0;
          }
          else
          {
            LODWORD(v14) = LastError;
            LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x", v2, v14);
            SetLastError(v3);
            v4 = 0;
          }
        }
        *v15 = 92;
        v5 = v15 + 1;
        if ( v4 != 1 )
        {
          v8 = GetLastError();
          v9 = a1;
          v10 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
          goto LABEL_21;
        }
      }
      if ( CreateDirectoryW(v2, 0) )
        goto LABEL_23;
      v8 = GetLastError();
      v3 = v8;
      if ( v8 != 183 )
      {
        v9 = v2;
        v10 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
        goto LABEL_22;
      }
      FileAttributesW = GetFileAttributesW(v2);
      if ( FileAttributesW == -1 )
      {
        v8 = GetLastError();
        v9 = v2;
        v10 = L"CreatePath: Unable to get attributes for [%s]; GLE = 0x%x";
LABEL_21:
        v3 = v8;
LABEL_22:
        LODWORD(v14) = v8;
        LibLog(&g_WdsLibLog, 50331648, v10, v9, v14);
        goto LABEL_23;
      }
      if ( (FileAttributesW & 0x10) != 0 )
      {
        v3 = 0;
      }
      else
      {
        LODWORD(v14) = 183;
        LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Existing path [%s] is not a directory; GLE = 0x%x", v2, v14);
      }
LABEL_23:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    else
    {
      v3 = GetLastError();
    }
    SetLastError(v3);
    return v3 == 0;
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
0x180221ebc  mov     r11, rsp
0x180221ebf  mov     [r11+10h], rbx
0x180221ec3  mov     [r11+18h], rbp
0x180221ec7  push    rsi
0x180221ec8  push    rdi
0x180221ec9  push    r13
0x180221ecb  push    r14
0x180221ecd  push    r15
0x180221ecf  sub     rsp, 30h
0x180221ed3  mov     qword ptr [r11+8], 0
0x180221edb  mov     rsi, rcx
0x180221ede  test    rcx, rcx
0x180221ee1  jz      loc_1802220C4
0x180221ee7  xor     eax, eax
0x180221ee9  cmp     ax, [rcx]
0x180221eec  jz      loc_1802220C4
0x180221ef2  lea     rdx, [r11+8]
0x180221ef6  call    PrepareUnicodePathEx
0x180221efb  mov     rdi, rax
0x180221efe  test    rax, rax
0x180221f01  jz      loc_18022209F
0x180221f07  mov     rax, [rsp+58h+arg_0]
0x180221f0c  xor     ebx, ebx
0x180221f0e  mov     ebp, 1
0x180221f13  test    rax, rax
0x180221f16  jz      short loc_180221F1E
0x180221f18  add     rax, 2
0x180221f1c  jmp     short loc_180221F21
0x180221f1e  mov     rax, rdi
0x180221f21  mov     [rsp+58h+arg_0], rax
0x180221f26  lea     r15, g_WdsLibLog
0x180221f2d  mov     r13d, 5Ch ; '\'
0x180221f33  mov     r14d, 3000000h
0x180221f39  mov     edx, r13d; Ch
0x180221f3c  mov     rcx, rax; Str
0x180221f3f  call    cs:__imp_wcschr
0x180221f46  nop     dword ptr [rax+rax+00h]
0x180221f4b  xor     edx, edx; lpSecurityAttributes
0x180221f4d  mov     [rsp+58h+arg_0], rax
0x180221f52  test    rax, rax
0x180221f55  jz      loc_180221FF2
0x180221f5b  xor     ecx, ecx
0x180221f5d  mov     [rax], cx
0x180221f60  mov     rcx, rdi; lpPathName
0x180221f63  call    cs:__imp_CreateDirectoryW
0x180221f6a  nop     dword ptr [rax+rax+00h]
0x180221f6f  test    eax, eax
0x180221f71  jnz     short loc_180221FBA
0x180221f73  call    cs:__imp_GetLastError
0x180221f7a  nop     dword ptr [rax+rax+00h]
0x180221f7f  mov     ebx, eax
0x180221f81  cmp     eax, 5
0x180221f84  jz      short loc_180221FB8
0x180221f86  cmp     eax, 0B7h
0x180221f8b  jz      short loc_180221FB8
0x180221f8d  mov     r9, rdi
0x180221f90  mov     dword ptr [rsp+58h+var_38], eax
0x180221f94  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x180221f9b  mov     edx, r14d
0x180221f9e  mov     rcx, r15
0x180221fa1  call    LibLog
0x180221fa6  mov     ecx, ebx; dwErrCode
0x180221fa8  call    cs:__imp_SetLastError
0x180221faf  nop     dword ptr [rax+rax+00h]
0x180221fb4  xor     ebp, ebp
0x180221fb6  jmp     short loc_180221FBA
0x180221fb8  xor     ebx, ebx
0x180221fba  mov     rax, [rsp+58h+arg_0]
0x180221fbf  mov     [rax], r13w
0x180221fc3  mov     rax, [rsp+58h+arg_0]
0x180221fc8  add     rax, 2
0x180221fcc  mov     [rsp+58h+arg_0], rax
0x180221fd1  cmp     ebp, 1
0x180221fd4  jz      loc_180221F39
0x180221fda  call    cs:__imp_GetLastError
0x180221fe1  nop     dword ptr [rax+rax+00h]
0x180221fe6  mov     r9, rsi
0x180221fe9  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180221ff0  jmp     short loc_18022206C
0x180221ff2  mov     rcx, rdi; lpPathName
0x180221ff5  call    cs:__imp_CreateDirectoryW
0x180221ffc  nop     dword ptr [rax+rax+00h]
0x180222001  test    eax, eax
0x180222003  jnz     short loc_18022207D
0x180222005  call    cs:__imp_GetLastError
0x18022200c  nop     dword ptr [rax+rax+00h]
0x180222011  mov     ebx, eax
0x180222013  cmp     eax, 0B7h
0x180222018  jz      short loc_180222026
0x18022201a  mov     r9, rdi
0x18022201d  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x180222024  jmp     short loc_18022206E
0x180222026  mov     rcx, rdi; lpFileName
0x180222029  call    cs:__imp_GetFileAttributesW
0x180222030  nop     dword ptr [rax+rax+00h]
0x180222035  cmp     eax, 0FFFFFFFFh
0x180222038  jz      short loc_180222056
0x18022203a  test    al, 10h
0x18022203c  jz      short loc_180222042
0x18022203e  xor     ebx, ebx
0x180222040  jmp     short loc_18022207D
0x180222042  mov     dword ptr [rsp+58h+var_38], 0B7h
0x18022204a  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x180222051  mov     r9, rdi
0x180222054  jmp     short loc_180222072
0x180222056  call    cs:__imp_GetLastError
0x18022205d  nop     dword ptr [rax+rax+00h]
0x180222062  mov     r9, rdi
0x180222065  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x18022206c  mov     ebx, eax
0x18022206e  mov     dword ptr [rsp+58h+var_38], eax
0x180222072  mov     edx, r14d
0x180222075  mov     rcx, r15
0x180222078  call    LibLog
0x18022207d  call    cs:__imp_GetProcessHeap
0x180222084  nop     dword ptr [rax+rax+00h]
0x180222089  mov     r8, rdi; lpMem
0x18022208c  xor     edx, edx; dwFlags
0x18022208e  mov     rcx, rax; hHeap
0x180222091  call    cs:__imp_HeapFree
0x180222098  nop     dword ptr [rax+rax+00h]
0x18022209d  jmp     short loc_1802220AD
0x18022209f  call    cs:__imp_GetLastError
0x1802220a6  nop     dword ptr [rax+rax+00h]
0x1802220ab  mov     ebx, eax
0x1802220ad  mov     ecx, ebx; dwErrCode
0x1802220af  call    cs:__imp_SetLastError
0x1802220b6  nop     dword ptr [rax+rax+00h]
0x1802220bb  xor     eax, eax
0x1802220bd  test    ebx, ebx
0x1802220bf  setz    al
0x1802220c2  jmp     short loc_1802220D7
0x1802220c4  mov     ecx, 57h ; 'W'; dwErrCode
0x1802220c9  call    cs:__imp_SetLastError
0x1802220d0  nop     dword ptr [rax+rax+00h]
0x1802220d5  xor     eax, eax
0x1802220d7  mov     rbx, [rsp+58h+arg_8]
0x1802220dc  mov     rbp, [rsp+58h+arg_10]
0x1802220e1  add     rsp, 30h
0x1802220e5  pop     r15
0x1802220e7  pop     r14
0x1802220e9  pop     r13
0x1802220eb  pop     rdi
0x1802220ec  pop     rsi
0x1802220ed  retn
```
