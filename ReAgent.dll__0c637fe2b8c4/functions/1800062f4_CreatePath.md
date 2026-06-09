# CreatePath

- ea: `0x1800062f4`
- end: `0x1800064ce`
- name: `CreatePath`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005694`
- `0x180028948`

## callees

- `0x1800061c0`
- `0x1800062f4`
- `0x1800067f0`

## import_xrefs

- `msvcrt!wcschr` at `0x180006377`
- `msvcrt!wcschr` at `0x180006377`
- `KERNEL32!GetLastError` at `0x18000639b`
- `KERNEL32!GetLastError` at `0x1800063f6`
- `KERNEL32!GetLastError` at `0x180006415`
- `KERNEL32!GetLastError` at `0x18000645a`
- `KERNEL32!GetLastError` at `0x180006491`
- `KERNEL32!GetLastError` at `0x18000639b`
- `KERNEL32!GetLastError` at `0x1800063f6`
- `KERNEL32!GetLastError` at `0x180006415`
- `KERNEL32!GetLastError` at `0x18000645a`
- `KERNEL32!GetLastError` at `0x180006491`
- `KERNEL32!HeapFree` at `0x180006489`
- `KERNEL32!HeapFree` at `0x180006489`
- `KERNEL32!GetProcessHeap` at `0x18000647b`
- `KERNEL32!GetProcessHeap` at `0x18000647b`
- `KERNEL32!SetLastError` at `0x1800063ca`
- `KERNEL32!SetLastError` at `0x18000649b`
- `KERNEL32!SetLastError` at `0x1800064af`
- `KERNEL32!SetLastError` at `0x1800063ca`
- `KERNEL32!SetLastError` at `0x18000649b`
- `KERNEL32!SetLastError` at `0x1800064af`
- `KERNEL32!GetFileAttributesW` at `0x180006433`
- `KERNEL32!GetFileAttributesW` at `0x180006433`
- `KERNEL32!CreateDirectoryW` at `0x180006391`
- `KERNEL32!CreateDirectoryW` at `0x18000640b`
- `KERNEL32!CreateDirectoryW` at `0x180006391`
- `KERNEL32!CreateDirectoryW` at `0x18000640b`

## string_xrefs

- `0x1800063b6`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x18000644e`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x180006463`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x180006427`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1800063ff`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`

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
0x1800062f4  mov     r11, rsp
0x1800062f7  mov     [r11+10h], rbx
0x1800062fb  mov     [r11+18h], rbp
0x1800062ff  push    rsi
0x180006300  push    rdi
0x180006301  push    r13
0x180006303  push    r14
0x180006305  push    r15
0x180006307  sub     rsp, 30h
0x18000630b  mov     qword ptr [r11+8], 0
0x180006313  mov     rsi, rcx
0x180006316  test    rcx, rcx
0x180006319  jz      loc_1800064AA
0x18000631f  xor     eax, eax
0x180006321  cmp     ax, [rcx]
0x180006324  jz      loc_1800064AA
0x18000632a  lea     rdx, [r11+8]
0x18000632e  call    PrepareUnicodePathEx
0x180006333  mov     rdi, rax
0x180006336  test    rax, rax
0x180006339  jz      loc_180006491
0x18000633f  mov     rax, [rsp+58h+arg_0]
0x180006344  xor     ebx, ebx
0x180006346  mov     ebp, 1
0x18000634b  test    rax, rax
0x18000634e  jz      short loc_180006356
0x180006350  add     rax, 2
0x180006354  jmp     short loc_180006359
0x180006356  mov     rax, rdi
0x180006359  mov     [rsp+58h+arg_0], rax
0x18000635e  lea     r15, g_WdsLibLog
0x180006365  mov     r13d, 5Ch ; '\'
0x18000636b  mov     r14d, 3000000h
0x180006371  mov     edx, r13d; Ch
0x180006374  mov     rcx, rax; Str
0x180006377  call    cs:__imp_wcschr
0x18000637d  xor     edx, edx; lpSecurityAttributes
0x18000637f  mov     [rsp+58h+arg_0], rax
0x180006384  test    rax, rax
0x180006387  jz      short loc_180006408
0x180006389  xor     ecx, ecx
0x18000638b  mov     [rax], cx
0x18000638e  mov     rcx, rdi; lpPathName
0x180006391  call    cs:__imp_CreateDirectoryW
0x180006397  test    eax, eax
0x180006399  jnz     short loc_1800063D6
0x18000639b  call    cs:__imp_GetLastError
0x1800063a1  mov     ebx, eax
0x1800063a3  cmp     eax, 5
0x1800063a6  jz      short loc_1800063D4
0x1800063a8  cmp     eax, 0B7h
0x1800063ad  jz      short loc_1800063D4
0x1800063af  mov     r9, rdi
0x1800063b2  mov     dword ptr [rsp+58h+var_38], eax
0x1800063b6  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x1800063bd  mov     edx, r14d
0x1800063c0  mov     rcx, r15
0x1800063c3  call    LibLog
0x1800063c8  mov     ecx, ebx; dwErrCode
0x1800063ca  call    cs:__imp_SetLastError
0x1800063d0  xor     ebp, ebp
0x1800063d2  jmp     short loc_1800063D6
0x1800063d4  xor     ebx, ebx
0x1800063d6  mov     rax, [rsp+58h+arg_0]
0x1800063db  mov     [rax], r13w
0x1800063df  mov     rax, [rsp+58h+arg_0]
0x1800063e4  add     rax, 2
0x1800063e8  mov     [rsp+58h+arg_0], rax
0x1800063ed  cmp     ebp, 1
0x1800063f0  jz      loc_180006371
0x1800063f6  call    cs:__imp_GetLastError
0x1800063fc  mov     r9, rsi
0x1800063ff  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180006406  jmp     short loc_18000646A
0x180006408  mov     rcx, rdi; lpPathName
0x18000640b  call    cs:__imp_CreateDirectoryW
0x180006411  test    eax, eax
0x180006413  jnz     short loc_18000647B
0x180006415  call    cs:__imp_GetLastError
0x18000641b  mov     ebx, eax
0x18000641d  cmp     eax, 0B7h
0x180006422  jz      short loc_180006430
0x180006424  mov     r9, rdi
0x180006427  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x18000642e  jmp     short loc_18000646C
0x180006430  mov     rcx, rdi; lpFileName
0x180006433  call    cs:__imp_GetFileAttributesW
0x180006439  cmp     eax, 0FFFFFFFFh
0x18000643c  jz      short loc_18000645A
0x18000643e  test    al, 10h
0x180006440  jz      short loc_180006446
0x180006442  xor     ebx, ebx
0x180006444  jmp     short loc_18000647B
0x180006446  mov     dword ptr [rsp+58h+var_38], 0B7h
0x18000644e  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x180006455  mov     r9, rdi
0x180006458  jmp     short loc_180006470
0x18000645a  call    cs:__imp_GetLastError
0x180006460  mov     r9, rdi
0x180006463  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x18000646a  mov     ebx, eax
0x18000646c  mov     dword ptr [rsp+58h+var_38], eax
0x180006470  mov     edx, r14d
0x180006473  mov     rcx, r15
0x180006476  call    LibLog
0x18000647b  call    cs:__imp_GetProcessHeap
0x180006481  mov     r8, rdi; lpMem
0x180006484  xor     edx, edx; dwFlags
0x180006486  mov     rcx, rax; hHeap
0x180006489  call    cs:__imp_HeapFree
0x18000648f  jmp     short loc_180006499
0x180006491  call    cs:__imp_GetLastError
0x180006497  mov     ebx, eax
0x180006499  mov     ecx, ebx; dwErrCode
0x18000649b  call    cs:__imp_SetLastError
0x1800064a1  xor     eax, eax
0x1800064a3  test    ebx, ebx
0x1800064a5  setz    al
0x1800064a8  jmp     short loc_1800064B7
0x1800064aa  mov     ecx, 57h ; 'W'; dwErrCode
0x1800064af  call    cs:__imp_SetLastError
0x1800064b5  xor     eax, eax
0x1800064b7  mov     rbx, [rsp+58h+arg_8]
0x1800064bc  mov     rbp, [rsp+58h+arg_10]
0x1800064c1  add     rsp, 30h
0x1800064c5  pop     r15
0x1800064c7  pop     r14
0x1800064c9  pop     r13
0x1800064cb  pop     rdi
0x1800064cc  pop     rsi
0x1800064cd  retn
```
