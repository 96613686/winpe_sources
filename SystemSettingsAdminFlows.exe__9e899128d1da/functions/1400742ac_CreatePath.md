# CreatePath

- ea: `0x1400742ac`
- end: `0x140074486`
- name: `CreatePath`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140073db8`

## callees

- `0x14007421c`
- `0x1400742ac`
- `0x140074694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007432f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14007432f`
- `KERNEL32!HeapFree` at `0x140074441`
- `KERNEL32!HeapFree` at `0x140074441`
- `KERNEL32!GetProcessHeap` at `0x140074433`
- `KERNEL32!GetProcessHeap` at `0x140074433`
- `KERNEL32!GetLastError` at `0x140074353`
- `KERNEL32!GetLastError` at `0x1400743ae`
- `KERNEL32!GetLastError` at `0x1400743cd`
- `KERNEL32!GetLastError` at `0x140074412`
- `KERNEL32!GetLastError` at `0x140074449`
- `KERNEL32!GetLastError` at `0x140074353`
- `KERNEL32!GetLastError` at `0x1400743ae`
- `KERNEL32!GetLastError` at `0x1400743cd`
- `KERNEL32!GetLastError` at `0x140074412`
- `KERNEL32!GetLastError` at `0x140074449`
- `KERNEL32!SetLastError` at `0x140074382`
- `KERNEL32!SetLastError` at `0x140074453`
- `KERNEL32!SetLastError` at `0x140074467`
- `KERNEL32!SetLastError` at `0x140074382`
- `KERNEL32!SetLastError` at `0x140074453`
- `KERNEL32!SetLastError` at `0x140074467`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140074349`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400743c3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140074349`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400743c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400743eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400743eb`

## string_xrefs

- `0x140074406`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`
- `0x14007436e`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x1400743b7`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x1400743df`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x14007441b`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`

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
0x1400742ac  mov     r11, rsp
0x1400742af  mov     [r11+10h], rbx
0x1400742b3  mov     [r11+18h], rbp
0x1400742b7  push    rsi
0x1400742b8  push    rdi
0x1400742b9  push    r13
0x1400742bb  push    r14
0x1400742bd  push    r15
0x1400742bf  sub     rsp, 30h
0x1400742c3  mov     qword ptr [r11+8], 0
0x1400742cb  mov     rsi, rcx
0x1400742ce  test    rcx, rcx
0x1400742d1  jz      loc_140074462
0x1400742d7  xor     eax, eax
0x1400742d9  cmp     ax, [rcx]
0x1400742dc  jz      loc_140074462
0x1400742e2  lea     rdx, [r11+8]
0x1400742e6  call    PrepareUnicodePathEx
0x1400742eb  mov     rdi, rax
0x1400742ee  test    rax, rax
0x1400742f1  jz      loc_140074449
0x1400742f7  mov     rax, [rsp+58h+arg_0]
0x1400742fc  xor     ebx, ebx
0x1400742fe  mov     ebp, 1
0x140074303  test    rax, rax
0x140074306  jz      short loc_14007430E
0x140074308  add     rax, 2
0x14007430c  jmp     short loc_140074311
0x14007430e  mov     rax, rdi
0x140074311  mov     [rsp+58h+arg_0], rax
0x140074316  lea     r15, g_WdsLibLog
0x14007431d  mov     r13d, 5Ch ; '\'
0x140074323  mov     r14d, 3000000h
0x140074329  mov     edx, r13d; Ch
0x14007432c  mov     rcx, rax; Str
0x14007432f  call    cs:__imp_wcschr
0x140074335  xor     edx, edx; lpSecurityAttributes
0x140074337  mov     [rsp+58h+arg_0], rax
0x14007433c  test    rax, rax
0x14007433f  jz      short loc_1400743C0
0x140074341  xor     ecx, ecx
0x140074343  mov     [rax], cx
0x140074346  mov     rcx, rdi; lpPathName
0x140074349  call    cs:__imp_CreateDirectoryW
0x14007434f  test    eax, eax
0x140074351  jnz     short loc_14007438E
0x140074353  call    cs:__imp_GetLastError
0x140074359  mov     ebx, eax
0x14007435b  cmp     eax, 5
0x14007435e  jz      short loc_14007438C
0x140074360  cmp     eax, 0B7h
0x140074365  jz      short loc_14007438C
0x140074367  mov     r9, rdi
0x14007436a  mov     dword ptr [rsp+58h+var_38], eax
0x14007436e  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x140074375  mov     edx, r14d
0x140074378  mov     rcx, r15
0x14007437b  call    LibLog
0x140074380  mov     ecx, ebx; dwErrCode
0x140074382  call    cs:__imp_SetLastError
0x140074388  xor     ebp, ebp
0x14007438a  jmp     short loc_14007438E
0x14007438c  xor     ebx, ebx
0x14007438e  mov     rax, [rsp+58h+arg_0]
0x140074393  mov     [rax], r13w
0x140074397  mov     rax, [rsp+58h+arg_0]
0x14007439c  add     rax, 2
0x1400743a0  mov     [rsp+58h+arg_0], rax
0x1400743a5  cmp     ebp, 1
0x1400743a8  jz      loc_140074329
0x1400743ae  call    cs:__imp_GetLastError
0x1400743b4  mov     r9, rsi
0x1400743b7  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x1400743be  jmp     short loc_140074422
0x1400743c0  mov     rcx, rdi; lpPathName
0x1400743c3  call    cs:__imp_CreateDirectoryW
0x1400743c9  test    eax, eax
0x1400743cb  jnz     short loc_140074433
0x1400743cd  call    cs:__imp_GetLastError
0x1400743d3  mov     ebx, eax
0x1400743d5  cmp     eax, 0B7h
0x1400743da  jz      short loc_1400743E8
0x1400743dc  mov     r9, rdi
0x1400743df  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x1400743e6  jmp     short loc_140074424
0x1400743e8  mov     rcx, rdi; lpFileName
0x1400743eb  call    cs:__imp_GetFileAttributesW
0x1400743f1  cmp     eax, 0FFFFFFFFh
0x1400743f4  jz      short loc_140074412
0x1400743f6  test    al, 10h
0x1400743f8  jz      short loc_1400743FE
0x1400743fa  xor     ebx, ebx
0x1400743fc  jmp     short loc_140074433
0x1400743fe  mov     dword ptr [rsp+58h+var_38], 0B7h
0x140074406  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x14007440d  mov     r9, rdi
0x140074410  jmp     short loc_140074428
0x140074412  call    cs:__imp_GetLastError
0x140074418  mov     r9, rdi
0x14007441b  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x140074422  mov     ebx, eax
0x140074424  mov     dword ptr [rsp+58h+var_38], eax
0x140074428  mov     edx, r14d
0x14007442b  mov     rcx, r15
0x14007442e  call    LibLog
0x140074433  call    cs:__imp_GetProcessHeap
0x140074439  mov     r8, rdi; lpMem
0x14007443c  xor     edx, edx; dwFlags
0x14007443e  mov     rcx, rax; hHeap
0x140074441  call    cs:__imp_HeapFree
0x140074447  jmp     short loc_140074451
0x140074449  call    cs:__imp_GetLastError
0x14007444f  mov     ebx, eax
0x140074451  mov     ecx, ebx; dwErrCode
0x140074453  call    cs:__imp_SetLastError
0x140074459  xor     eax, eax
0x14007445b  test    ebx, ebx
0x14007445d  setz    al
0x140074460  jmp     short loc_14007446F
0x140074462  mov     ecx, 57h ; 'W'; dwErrCode
0x140074467  call    cs:__imp_SetLastError
0x14007446d  xor     eax, eax
0x14007446f  mov     rbx, [rsp+58h+arg_8]
0x140074474  mov     rbp, [rsp+58h+arg_10]
0x140074479  add     rsp, 30h
0x14007447d  pop     r15
0x14007447f  pop     r14
0x140074481  pop     r13
0x140074483  pop     rdi
0x140074484  pop     rsi
0x140074485  retn
```
