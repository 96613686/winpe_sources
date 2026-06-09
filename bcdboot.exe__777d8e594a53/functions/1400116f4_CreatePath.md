# CreatePath

- ea: `0x1400116f4`
- end: `0x1400118ce`
- name: `CreatePath`
- size: `474`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140009fd4`
- `0x14000b57c`

## callees

- `0x1400116f4`
- `0x140011a88`
- `0x140011b18`

## import_xrefs

- `msvcrt!wcschr` at `0x140011777`
- `msvcrt!wcschr` at `0x140011777`
- `KERNEL32!SetLastError` at `0x1400117ca`
- `KERNEL32!SetLastError` at `0x14001189b`
- `KERNEL32!SetLastError` at `0x1400118af`
- `KERNEL32!SetLastError` at `0x1400117ca`
- `KERNEL32!SetLastError` at `0x14001189b`
- `KERNEL32!SetLastError` at `0x1400118af`
- `KERNEL32!GetLastError` at `0x14001179b`
- `KERNEL32!GetLastError` at `0x1400117f6`
- `KERNEL32!GetLastError` at `0x140011815`
- `KERNEL32!GetLastError` at `0x14001185a`
- `KERNEL32!GetLastError` at `0x140011891`
- `KERNEL32!GetLastError` at `0x14001179b`
- `KERNEL32!GetLastError` at `0x1400117f6`
- `KERNEL32!GetLastError` at `0x140011815`
- `KERNEL32!GetLastError` at `0x14001185a`
- `KERNEL32!GetLastError` at `0x140011891`
- `KERNEL32!HeapFree` at `0x140011889`
- `KERNEL32!HeapFree` at `0x140011889`
- `KERNEL32!GetProcessHeap` at `0x14001187b`
- `KERNEL32!GetProcessHeap` at `0x14001187b`
- `KERNEL32!GetFileAttributesW` at `0x140011833`
- `KERNEL32!GetFileAttributesW` at `0x140011833`
- `KERNEL32!CreateDirectoryW` at `0x140011791`
- `KERNEL32!CreateDirectoryW` at `0x14001180b`
- `KERNEL32!CreateDirectoryW` at `0x140011791`
- `KERNEL32!CreateDirectoryW` at `0x14001180b`

## string_xrefs

- `0x140011863`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x140011827`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1400117ff`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x1400117b6`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x14001184e`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall CreatePath(const wchar_t *a1)
{
  WCHAR *v2; // rdi
  DWORD v3; // ebx
  int v4; // ebp
  const wchar_t *v5; // rax
  wchar_t *v6; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  void *v9; // r9
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
          v9 = (void *)a1;
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
0x1400116f4  mov     r11, rsp
0x1400116f7  mov     [r11+10h], rbx
0x1400116fb  mov     [r11+18h], rbp
0x1400116ff  push    rsi
0x140011700  push    rdi
0x140011701  push    r13
0x140011703  push    r14
0x140011705  push    r15
0x140011707  sub     rsp, 30h
0x14001170b  mov     qword ptr [r11+8], 0
0x140011713  mov     rsi, rcx
0x140011716  test    rcx, rcx
0x140011719  jz      loc_1400118AA
0x14001171f  xor     eax, eax
0x140011721  cmp     ax, [rcx]
0x140011724  jz      loc_1400118AA
0x14001172a  lea     rdx, [r11+8]
0x14001172e  call    PrepareUnicodePathEx
0x140011733  mov     rdi, rax
0x140011736  test    rax, rax
0x140011739  jz      loc_140011891
0x14001173f  mov     rax, [rsp+58h+arg_0]
0x140011744  xor     ebx, ebx
0x140011746  mov     ebp, 1
0x14001174b  test    rax, rax
0x14001174e  jz      short loc_140011756
0x140011750  add     rax, 2
0x140011754  jmp     short loc_140011759
0x140011756  mov     rax, rdi
0x140011759  mov     [rsp+58h+arg_0], rax
0x14001175e  lea     r15, g_WdsLibLog
0x140011765  mov     r13d, 5Ch ; '\'
0x14001176b  mov     r14d, 3000000h
0x140011771  mov     edx, r13d; Ch
0x140011774  mov     rcx, rax; Str
0x140011777  call    cs:__imp_wcschr
0x14001177d  xor     edx, edx; lpSecurityAttributes
0x14001177f  mov     [rsp+58h+arg_0], rax
0x140011784  test    rax, rax
0x140011787  jz      short loc_140011808
0x140011789  xor     ecx, ecx
0x14001178b  mov     [rax], cx
0x14001178e  mov     rcx, rdi; lpPathName
0x140011791  call    cs:__imp_CreateDirectoryW
0x140011797  test    eax, eax
0x140011799  jnz     short loc_1400117D6
0x14001179b  call    cs:__imp_GetLastError
0x1400117a1  mov     ebx, eax
0x1400117a3  cmp     eax, 5
0x1400117a6  jz      short loc_1400117D4
0x1400117a8  cmp     eax, 0B7h
0x1400117ad  jz      short loc_1400117D4
0x1400117af  mov     r9, rdi
0x1400117b2  mov     dword ptr [rsp+58h+var_38], eax
0x1400117b6  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x1400117bd  mov     edx, r14d
0x1400117c0  mov     rcx, r15
0x1400117c3  call    LibLog
0x1400117c8  mov     ecx, ebx; dwErrCode
0x1400117ca  call    cs:__imp_SetLastError
0x1400117d0  xor     ebp, ebp
0x1400117d2  jmp     short loc_1400117D6
0x1400117d4  xor     ebx, ebx
0x1400117d6  mov     rax, [rsp+58h+arg_0]
0x1400117db  mov     [rax], r13w
0x1400117df  mov     rax, [rsp+58h+arg_0]
0x1400117e4  add     rax, 2
0x1400117e8  mov     [rsp+58h+arg_0], rax
0x1400117ed  cmp     ebp, 1
0x1400117f0  jz      loc_140011771
0x1400117f6  call    cs:__imp_GetLastError
0x1400117fc  mov     r9, rsi
0x1400117ff  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x140011806  jmp     short loc_14001186A
0x140011808  mov     rcx, rdi; lpPathName
0x14001180b  call    cs:__imp_CreateDirectoryW
0x140011811  test    eax, eax
0x140011813  jnz     short loc_14001187B
0x140011815  call    cs:__imp_GetLastError
0x14001181b  mov     ebx, eax
0x14001181d  cmp     eax, 0B7h
0x140011822  jz      short loc_140011830
0x140011824  mov     r9, rdi
0x140011827  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x14001182e  jmp     short loc_14001186C
0x140011830  mov     rcx, rdi; lpFileName
0x140011833  call    cs:__imp_GetFileAttributesW
0x140011839  cmp     eax, 0FFFFFFFFh
0x14001183c  jz      short loc_14001185A
0x14001183e  test    al, 10h
0x140011840  jz      short loc_140011846
0x140011842  xor     ebx, ebx
0x140011844  jmp     short loc_14001187B
0x140011846  mov     dword ptr [rsp+58h+var_38], 0B7h
0x14001184e  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x140011855  mov     r9, rdi
0x140011858  jmp     short loc_140011870
0x14001185a  call    cs:__imp_GetLastError
0x140011860  mov     r9, rdi
0x140011863  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x14001186a  mov     ebx, eax
0x14001186c  mov     dword ptr [rsp+58h+var_38], eax
0x140011870  mov     edx, r14d
0x140011873  mov     rcx, r15
0x140011876  call    LibLog
0x14001187b  call    cs:__imp_GetProcessHeap
0x140011881  mov     r8, rdi; lpMem
0x140011884  xor     edx, edx; dwFlags
0x140011886  mov     rcx, rax; hHeap
0x140011889  call    cs:__imp_HeapFree
0x14001188f  jmp     short loc_140011899
0x140011891  call    cs:__imp_GetLastError
0x140011897  mov     ebx, eax
0x140011899  mov     ecx, ebx; dwErrCode
0x14001189b  call    cs:__imp_SetLastError
0x1400118a1  xor     eax, eax
0x1400118a3  test    ebx, ebx
0x1400118a5  setz    al
0x1400118a8  jmp     short loc_1400118B7
0x1400118aa  mov     ecx, 57h ; 'W'; dwErrCode
0x1400118af  call    cs:__imp_SetLastError
0x1400118b5  xor     eax, eax
0x1400118b7  mov     rbx, [rsp+58h+arg_8]
0x1400118bc  mov     rbp, [rsp+58h+arg_10]
0x1400118c1  add     rsp, 30h
0x1400118c5  pop     r15
0x1400118c7  pop     r14
0x1400118c9  pop     r13
0x1400118cb  pop     rdi
0x1400118cc  pop     rsi
0x1400118cd  retn
```
