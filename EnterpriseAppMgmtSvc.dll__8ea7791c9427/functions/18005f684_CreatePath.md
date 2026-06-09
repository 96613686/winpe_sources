# CreatePath

- ea: `0x18005f684`
- end: `0x18005f85e`
- name: `CreatePath`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180039edc`
- `0x18003f79c`
- `0x180060aa0`
- `0x180060be8`

## callees

- `0x18005eea8`
- `0x18005f684`
- `0x18005fd24`

## import_xrefs

- `msvcrt!wcschr` at `0x18005f707`
- `msvcrt!wcschr` at `0x18005f707`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f80b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f80b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f819`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f821`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f83f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f83f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005f721`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005f79b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005f721`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005f79b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005f7c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005f7c3`

## string_xrefs

- `0x18005f7b7`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x18005f7f3`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x18005f7de`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x18005f746`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18005f78f`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(unsigned __int16 *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  unsigned __int16 *v9; // r9
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
0x18005f684  mov     r11, rsp
0x18005f687  mov     [r11+10h], rbx
0x18005f68b  mov     [r11+18h], rbp
0x18005f68f  push    rsi
0x18005f690  push    rdi
0x18005f691  push    r13
0x18005f693  push    r14
0x18005f695  push    r15
0x18005f697  sub     rsp, 30h
0x18005f69b  mov     qword ptr [r11+8], 0
0x18005f6a3  mov     rsi, rcx
0x18005f6a6  test    rcx, rcx
0x18005f6a9  jz      loc_18005F83A
0x18005f6af  xor     eax, eax
0x18005f6b1  cmp     ax, [rcx]
0x18005f6b4  jz      loc_18005F83A
0x18005f6ba  lea     rdx, [r11+8]
0x18005f6be  call    PrepareUnicodePathEx
0x18005f6c3  mov     rdi, rax
0x18005f6c6  test    rax, rax
0x18005f6c9  jz      loc_18005F821
0x18005f6cf  mov     rax, [rsp+58h+arg_0]
0x18005f6d4  xor     ebx, ebx
0x18005f6d6  mov     ebp, 1
0x18005f6db  test    rax, rax
0x18005f6de  jz      short loc_18005F6E6
0x18005f6e0  add     rax, 2
0x18005f6e4  jmp     short loc_18005F6E9
0x18005f6e6  mov     rax, rdi
0x18005f6e9  mov     [rsp+58h+arg_0], rax
0x18005f6ee  lea     r15, g_WdsLibLog
0x18005f6f5  mov     r13d, 5Ch ; '\'
0x18005f6fb  mov     r14d, 3000000h
0x18005f701  mov     edx, r13d; Ch
0x18005f704  mov     rcx, rax; Str
0x18005f707  call    cs:__imp_wcschr
0x18005f70d  xor     edx, edx; lpSecurityAttributes
0x18005f70f  mov     [rsp+58h+arg_0], rax
0x18005f714  test    rax, rax
0x18005f717  jz      short loc_18005F798
0x18005f719  xor     ecx, ecx
0x18005f71b  mov     [rax], cx
0x18005f71e  mov     rcx, rdi; lpPathName
0x18005f721  call    cs:__imp_CreateDirectoryW
0x18005f727  test    eax, eax
0x18005f729  jnz     short loc_18005F766
0x18005f72b  call    cs:__imp_GetLastError
0x18005f731  mov     ebx, eax
0x18005f733  cmp     eax, 5
0x18005f736  jz      short loc_18005F764
0x18005f738  cmp     eax, 0B7h
0x18005f73d  jz      short loc_18005F764
0x18005f73f  mov     r9, rdi
0x18005f742  mov     dword ptr [rsp+58h+var_38], eax
0x18005f746  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x18005f74d  mov     edx, r14d
0x18005f750  mov     rcx, r15
0x18005f753  call    LibLog
0x18005f758  mov     ecx, ebx; dwErrCode
0x18005f75a  call    cs:__imp_SetLastError
0x18005f760  xor     ebp, ebp
0x18005f762  jmp     short loc_18005F766
0x18005f764  xor     ebx, ebx
0x18005f766  mov     rax, [rsp+58h+arg_0]
0x18005f76b  mov     [rax], r13w
0x18005f76f  mov     rax, [rsp+58h+arg_0]
0x18005f774  add     rax, 2
0x18005f778  mov     [rsp+58h+arg_0], rax
0x18005f77d  cmp     ebp, 1
0x18005f780  jz      loc_18005F701
0x18005f786  call    cs:__imp_GetLastError
0x18005f78c  mov     r9, rsi
0x18005f78f  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x18005f796  jmp     short loc_18005F7FA
0x18005f798  mov     rcx, rdi; lpPathName
0x18005f79b  call    cs:__imp_CreateDirectoryW
0x18005f7a1  test    eax, eax
0x18005f7a3  jnz     short loc_18005F80B
0x18005f7a5  call    cs:__imp_GetLastError
0x18005f7ab  mov     ebx, eax
0x18005f7ad  cmp     eax, 0B7h
0x18005f7b2  jz      short loc_18005F7C0
0x18005f7b4  mov     r9, rdi
0x18005f7b7  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x18005f7be  jmp     short loc_18005F7FC
0x18005f7c0  mov     rcx, rdi; lpFileName
0x18005f7c3  call    cs:__imp_GetFileAttributesW
0x18005f7c9  cmp     eax, 0FFFFFFFFh
0x18005f7cc  jz      short loc_18005F7EA
0x18005f7ce  test    al, 10h
0x18005f7d0  jz      short loc_18005F7D6
0x18005f7d2  xor     ebx, ebx
0x18005f7d4  jmp     short loc_18005F80B
0x18005f7d6  mov     dword ptr [rsp+58h+var_38], 0B7h
0x18005f7de  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x18005f7e5  mov     r9, rdi
0x18005f7e8  jmp     short loc_18005F800
0x18005f7ea  call    cs:__imp_GetLastError
0x18005f7f0  mov     r9, rdi
0x18005f7f3  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x18005f7fa  mov     ebx, eax
0x18005f7fc  mov     dword ptr [rsp+58h+var_38], eax
0x18005f800  mov     edx, r14d
0x18005f803  mov     rcx, r15
0x18005f806  call    LibLog
0x18005f80b  call    cs:__imp_GetProcessHeap
0x18005f811  mov     r8, rdi; lpMem
0x18005f814  xor     edx, edx; dwFlags
0x18005f816  mov     rcx, rax; hHeap
0x18005f819  call    cs:__imp_HeapFree
0x18005f81f  jmp     short loc_18005F829
0x18005f821  call    cs:__imp_GetLastError
0x18005f827  mov     ebx, eax
0x18005f829  mov     ecx, ebx; dwErrCode
0x18005f82b  call    cs:__imp_SetLastError
0x18005f831  xor     eax, eax
0x18005f833  test    ebx, ebx
0x18005f835  setz    al
0x18005f838  jmp     short loc_18005F847
0x18005f83a  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f83f  call    cs:__imp_SetLastError
0x18005f845  xor     eax, eax
0x18005f847  mov     rbx, [rsp+58h+arg_8]
0x18005f84c  mov     rbp, [rsp+58h+arg_10]
0x18005f851  add     rsp, 30h
0x18005f855  pop     r15
0x18005f857  pop     r14
0x18005f859  pop     r13
0x18005f85b  pop     rdi
0x18005f85c  pop     rsi
0x18005f85d  retn
```
