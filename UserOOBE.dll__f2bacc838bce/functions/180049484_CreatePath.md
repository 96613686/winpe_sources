# CreatePath

- ea: `0x180049484`
- end: `0x18004965e`
- name: `CreatePath`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180047ad8`
- `0x180048650`

## callees

- `0x180049370`
- `0x180049484`
- `0x18004997c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180049507`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180049507`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004960b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004960b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049619`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004952b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004952b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049621`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004955a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004962b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004963f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004955a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004962b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004963f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180049521`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004959b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180049521`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004959b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800495c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800495c3`

## string_xrefs

- `0x1800495de`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180049546`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18004958f`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x1800495b7`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1800495f3`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`

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
0x180049484  mov     r11, rsp
0x180049487  mov     [r11+10h], rbx
0x18004948b  mov     [r11+18h], rbp
0x18004948f  push    rsi
0x180049490  push    rdi
0x180049491  push    r13
0x180049493  push    r14
0x180049495  push    r15
0x180049497  sub     rsp, 30h
0x18004949b  mov     qword ptr [r11+8], 0
0x1800494a3  mov     rsi, rcx
0x1800494a6  test    rcx, rcx
0x1800494a9  jz      loc_18004963A
0x1800494af  xor     eax, eax
0x1800494b1  cmp     ax, [rcx]
0x1800494b4  jz      loc_18004963A
0x1800494ba  lea     rdx, [r11+8]
0x1800494be  call    PrepareUnicodePathEx
0x1800494c3  mov     rdi, rax
0x1800494c6  test    rax, rax
0x1800494c9  jz      loc_180049621
0x1800494cf  mov     rax, [rsp+58h+arg_0]
0x1800494d4  xor     ebx, ebx
0x1800494d6  mov     ebp, 1
0x1800494db  test    rax, rax
0x1800494de  jz      short loc_1800494E6
0x1800494e0  add     rax, 2
0x1800494e4  jmp     short loc_1800494E9
0x1800494e6  mov     rax, rdi
0x1800494e9  mov     [rsp+58h+arg_0], rax
0x1800494ee  lea     r15, g_WdsLibLog
0x1800494f5  mov     r13d, 5Ch ; '\'
0x1800494fb  mov     r14d, 3000000h
0x180049501  mov     edx, r13d; Ch
0x180049504  mov     rcx, rax; Str
0x180049507  call    cs:__imp_wcschr
0x18004950d  xor     edx, edx; lpSecurityAttributes
0x18004950f  mov     [rsp+58h+arg_0], rax
0x180049514  test    rax, rax
0x180049517  jz      short loc_180049598
0x180049519  xor     ecx, ecx
0x18004951b  mov     [rax], cx
0x18004951e  mov     rcx, rdi; lpPathName
0x180049521  call    cs:__imp_CreateDirectoryW
0x180049527  test    eax, eax
0x180049529  jnz     short loc_180049566
0x18004952b  call    cs:__imp_GetLastError
0x180049531  mov     ebx, eax
0x180049533  cmp     eax, 5
0x180049536  jz      short loc_180049564
0x180049538  cmp     eax, 0B7h
0x18004953d  jz      short loc_180049564
0x18004953f  mov     r9, rdi
0x180049542  mov     dword ptr [rsp+58h+var_38], eax
0x180049546  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x18004954d  mov     edx, r14d
0x180049550  mov     rcx, r15
0x180049553  call    LibLog
0x180049558  mov     ecx, ebx; dwErrCode
0x18004955a  call    cs:__imp_SetLastError
0x180049560  xor     ebp, ebp
0x180049562  jmp     short loc_180049566
0x180049564  xor     ebx, ebx
0x180049566  mov     rax, [rsp+58h+arg_0]
0x18004956b  mov     [rax], r13w
0x18004956f  mov     rax, [rsp+58h+arg_0]
0x180049574  add     rax, 2
0x180049578  mov     [rsp+58h+arg_0], rax
0x18004957d  cmp     ebp, 1
0x180049580  jz      loc_180049501
0x180049586  call    cs:__imp_GetLastError
0x18004958c  mov     r9, rsi
0x18004958f  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180049596  jmp     short loc_1800495FA
0x180049598  mov     rcx, rdi; lpPathName
0x18004959b  call    cs:__imp_CreateDirectoryW
0x1800495a1  test    eax, eax
0x1800495a3  jnz     short loc_18004960B
0x1800495a5  call    cs:__imp_GetLastError
0x1800495ab  mov     ebx, eax
0x1800495ad  cmp     eax, 0B7h
0x1800495b2  jz      short loc_1800495C0
0x1800495b4  mov     r9, rdi
0x1800495b7  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x1800495be  jmp     short loc_1800495FC
0x1800495c0  mov     rcx, rdi; lpFileName
0x1800495c3  call    cs:__imp_GetFileAttributesW
0x1800495c9  cmp     eax, 0FFFFFFFFh
0x1800495cc  jz      short loc_1800495EA
0x1800495ce  test    al, 10h
0x1800495d0  jz      short loc_1800495D6
0x1800495d2  xor     ebx, ebx
0x1800495d4  jmp     short loc_18004960B
0x1800495d6  mov     dword ptr [rsp+58h+var_38], 0B7h
0x1800495de  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x1800495e5  mov     r9, rdi
0x1800495e8  jmp     short loc_180049600
0x1800495ea  call    cs:__imp_GetLastError
0x1800495f0  mov     r9, rdi
0x1800495f3  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x1800495fa  mov     ebx, eax
0x1800495fc  mov     dword ptr [rsp+58h+var_38], eax
0x180049600  mov     edx, r14d
0x180049603  mov     rcx, r15
0x180049606  call    LibLog
0x18004960b  call    cs:__imp_GetProcessHeap
0x180049611  mov     r8, rdi; lpMem
0x180049614  xor     edx, edx; dwFlags
0x180049616  mov     rcx, rax; hHeap
0x180049619  call    cs:__imp_HeapFree
0x18004961f  jmp     short loc_180049629
0x180049621  call    cs:__imp_GetLastError
0x180049627  mov     ebx, eax
0x180049629  mov     ecx, ebx; dwErrCode
0x18004962b  call    cs:__imp_SetLastError
0x180049631  xor     eax, eax
0x180049633  test    ebx, ebx
0x180049635  setz    al
0x180049638  jmp     short loc_180049647
0x18004963a  mov     ecx, 57h ; 'W'; dwErrCode
0x18004963f  call    cs:__imp_SetLastError
0x180049645  xor     eax, eax
0x180049647  mov     rbx, [rsp+58h+arg_8]
0x18004964c  mov     rbp, [rsp+58h+arg_10]
0x180049651  add     rsp, 30h
0x180049655  pop     r15
0x180049657  pop     r14
0x180049659  pop     r13
0x18004965b  pop     rdi
0x18004965c  pop     rsi
0x18004965d  retn
```
