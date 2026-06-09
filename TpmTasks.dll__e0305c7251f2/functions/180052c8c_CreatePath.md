# CreatePath

- ea: `0x180052c8c`
- end: `0x180052e66`
- name: `CreatePath`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180049234`
- `0x18004a678`
- `0x18004c194`

## callees

- `0x180052c8c`
- `0x180053040`
- `0x180053234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180052d0f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180052d0f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052d29`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052da3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052d29`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052da3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052dcb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052e21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052e21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e29`

## string_xrefs

- `0x180052dbf`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x180052dfb`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x180052d97`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x180052de6`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180052d4e`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`

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
0x180052c8c  mov     r11, rsp
0x180052c8f  mov     [r11+10h], rbx
0x180052c93  mov     [r11+18h], rbp
0x180052c97  push    rsi
0x180052c98  push    rdi
0x180052c99  push    r13
0x180052c9b  push    r14
0x180052c9d  push    r15
0x180052c9f  sub     rsp, 30h
0x180052ca3  mov     qword ptr [r11+8], 0
0x180052cab  mov     rsi, rcx
0x180052cae  test    rcx, rcx
0x180052cb1  jz      loc_180052E42
0x180052cb7  xor     eax, eax
0x180052cb9  cmp     ax, [rcx]
0x180052cbc  jz      loc_180052E42
0x180052cc2  lea     rdx, [r11+8]
0x180052cc6  call    PrepareUnicodePathEx
0x180052ccb  mov     rdi, rax
0x180052cce  test    rax, rax
0x180052cd1  jz      loc_180052E29
0x180052cd7  mov     rax, [rsp+58h+arg_0]
0x180052cdc  xor     ebx, ebx
0x180052cde  mov     ebp, 1
0x180052ce3  test    rax, rax
0x180052ce6  jz      short loc_180052CEE
0x180052ce8  add     rax, 2
0x180052cec  jmp     short loc_180052CF1
0x180052cee  mov     rax, rdi
0x180052cf1  mov     [rsp+58h+arg_0], rax
0x180052cf6  lea     r15, g_WdsLibLog
0x180052cfd  mov     r13d, 5Ch ; '\'
0x180052d03  mov     r14d, 3000000h
0x180052d09  mov     edx, r13d; Ch
0x180052d0c  mov     rcx, rax; Str
0x180052d0f  call    cs:__imp_wcschr
0x180052d15  xor     edx, edx; lpSecurityAttributes
0x180052d17  mov     [rsp+58h+arg_0], rax
0x180052d1c  test    rax, rax
0x180052d1f  jz      short loc_180052DA0
0x180052d21  xor     ecx, ecx
0x180052d23  mov     [rax], cx
0x180052d26  mov     rcx, rdi; lpPathName
0x180052d29  call    cs:__imp_CreateDirectoryW
0x180052d2f  test    eax, eax
0x180052d31  jnz     short loc_180052D6E
0x180052d33  call    cs:__imp_GetLastError
0x180052d39  mov     ebx, eax
0x180052d3b  cmp     eax, 5
0x180052d3e  jz      short loc_180052D6C
0x180052d40  cmp     eax, 0B7h
0x180052d45  jz      short loc_180052D6C
0x180052d47  mov     r9, rdi
0x180052d4a  mov     dword ptr [rsp+58h+var_38], eax
0x180052d4e  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x180052d55  mov     edx, r14d
0x180052d58  mov     rcx, r15
0x180052d5b  call    LibLog
0x180052d60  mov     ecx, ebx; dwErrCode
0x180052d62  call    cs:__imp_SetLastError
0x180052d68  xor     ebp, ebp
0x180052d6a  jmp     short loc_180052D6E
0x180052d6c  xor     ebx, ebx
0x180052d6e  mov     rax, [rsp+58h+arg_0]
0x180052d73  mov     [rax], r13w
0x180052d77  mov     rax, [rsp+58h+arg_0]
0x180052d7c  add     rax, 2
0x180052d80  mov     [rsp+58h+arg_0], rax
0x180052d85  cmp     ebp, 1
0x180052d88  jz      loc_180052D09
0x180052d8e  call    cs:__imp_GetLastError
0x180052d94  mov     r9, rsi
0x180052d97  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180052d9e  jmp     short loc_180052E02
0x180052da0  mov     rcx, rdi; lpPathName
0x180052da3  call    cs:__imp_CreateDirectoryW
0x180052da9  test    eax, eax
0x180052dab  jnz     short loc_180052E13
0x180052dad  call    cs:__imp_GetLastError
0x180052db3  mov     ebx, eax
0x180052db5  cmp     eax, 0B7h
0x180052dba  jz      short loc_180052DC8
0x180052dbc  mov     r9, rdi
0x180052dbf  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x180052dc6  jmp     short loc_180052E04
0x180052dc8  mov     rcx, rdi; lpFileName
0x180052dcb  call    cs:__imp_GetFileAttributesW
0x180052dd1  cmp     eax, 0FFFFFFFFh
0x180052dd4  jz      short loc_180052DF2
0x180052dd6  test    al, 10h
0x180052dd8  jz      short loc_180052DDE
0x180052dda  xor     ebx, ebx
0x180052ddc  jmp     short loc_180052E13
0x180052dde  mov     dword ptr [rsp+58h+var_38], 0B7h
0x180052de6  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x180052ded  mov     r9, rdi
0x180052df0  jmp     short loc_180052E08
0x180052df2  call    cs:__imp_GetLastError
0x180052df8  mov     r9, rdi
0x180052dfb  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x180052e02  mov     ebx, eax
0x180052e04  mov     dword ptr [rsp+58h+var_38], eax
0x180052e08  mov     edx, r14d
0x180052e0b  mov     rcx, r15
0x180052e0e  call    LibLog
0x180052e13  call    cs:__imp_GetProcessHeap
0x180052e19  mov     r8, rdi; lpMem
0x180052e1c  xor     edx, edx; dwFlags
0x180052e1e  mov     rcx, rax; hHeap
0x180052e21  call    cs:__imp_HeapFree
0x180052e27  jmp     short loc_180052E31
0x180052e29  call    cs:__imp_GetLastError
0x180052e2f  mov     ebx, eax
0x180052e31  mov     ecx, ebx; dwErrCode
0x180052e33  call    cs:__imp_SetLastError
0x180052e39  xor     eax, eax
0x180052e3b  test    ebx, ebx
0x180052e3d  setz    al
0x180052e40  jmp     short loc_180052E4F
0x180052e42  mov     ecx, 57h ; 'W'; dwErrCode
0x180052e47  call    cs:__imp_SetLastError
0x180052e4d  xor     eax, eax
0x180052e4f  mov     rbx, [rsp+58h+arg_8]
0x180052e54  mov     rbp, [rsp+58h+arg_10]
0x180052e59  add     rsp, 30h
0x180052e5d  pop     r15
0x180052e5f  pop     r14
0x180052e61  pop     r13
0x180052e63  pop     rdi
0x180052e64  pop     rsi
0x180052e65  retn
```
