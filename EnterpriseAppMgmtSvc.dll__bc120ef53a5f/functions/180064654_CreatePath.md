# CreatePath

- ea: `0x180064654`
- end: `0x180064887`
- name: `CreatePath`
- size: `563`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003d52c`
- `0x18004324c`
- `0x180065d70`
- `0x180065ee4`

## callees

- `0x180063df0`
- `0x180064654`
- `0x180064e8c`

## import_xrefs

- `msvcrt!wcschr` at `0x1800646d7`
- `msvcrt!wcschr` at `0x1800646d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064815`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006470b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006479d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006470b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006479d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064847`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064861`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064740`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064847`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064861`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800646fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006478d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800646fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006478d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800647c1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800647c1`

## string_xrefs

- `0x18006472c`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x180064781`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x1800647b5`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x1800647fd`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x1800647e2`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`

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
0x180064654  mov     r11, rsp
0x180064657  mov     [r11+10h], rbx
0x18006465b  mov     [r11+18h], rbp
0x18006465f  push    rsi
0x180064660  push    rdi
0x180064661  push    r13
0x180064663  push    r14
0x180064665  push    r15
0x180064667  sub     rsp, 30h
0x18006466b  mov     qword ptr [r11+8], 0
0x180064673  mov     rsi, rcx
0x180064676  test    rcx, rcx
0x180064679  jz      loc_18006485C
0x18006467f  xor     eax, eax
0x180064681  cmp     ax, [rcx]
0x180064684  jz      loc_18006485C
0x18006468a  lea     rdx, [r11+8]
0x18006468e  call    PrepareUnicodePathEx
0x180064693  mov     rdi, rax
0x180064696  test    rax, rax
0x180064699  jz      loc_180064837
0x18006469f  mov     rax, [rsp+58h+arg_0]
0x1800646a4  xor     ebx, ebx
0x1800646a6  mov     ebp, 1
0x1800646ab  test    rax, rax
0x1800646ae  jz      short loc_1800646B6
0x1800646b0  add     rax, 2
0x1800646b4  jmp     short loc_1800646B9
0x1800646b6  mov     rax, rdi
0x1800646b9  mov     [rsp+58h+arg_0], rax
0x1800646be  lea     r15, g_WdsLibLog
0x1800646c5  mov     r13d, 5Ch ; '\'
0x1800646cb  mov     r14d, 3000000h
0x1800646d1  mov     edx, r13d; Ch
0x1800646d4  mov     rcx, rax; Str
0x1800646d7  call    cs:__imp_wcschr
0x1800646de  nop     dword ptr [rax+rax+00h]
0x1800646e3  xor     edx, edx; lpSecurityAttributes
0x1800646e5  mov     [rsp+58h+arg_0], rax
0x1800646ea  test    rax, rax
0x1800646ed  jz      loc_18006478A
0x1800646f3  xor     ecx, ecx
0x1800646f5  mov     [rax], cx
0x1800646f8  mov     rcx, rdi; lpPathName
0x1800646fb  call    cs:__imp_CreateDirectoryW
0x180064702  nop     dword ptr [rax+rax+00h]
0x180064707  test    eax, eax
0x180064709  jnz     short loc_180064752
0x18006470b  call    cs:__imp_GetLastError
0x180064712  nop     dword ptr [rax+rax+00h]
0x180064717  mov     ebx, eax
0x180064719  cmp     eax, 5
0x18006471c  jz      short loc_180064750
0x18006471e  cmp     eax, 0B7h
0x180064723  jz      short loc_180064750
0x180064725  mov     r9, rdi
0x180064728  mov     dword ptr [rsp+58h+var_38], eax
0x18006472c  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x180064733  mov     edx, r14d
0x180064736  mov     rcx, r15
0x180064739  call    LibLog
0x18006473e  mov     ecx, ebx; dwErrCode
0x180064740  call    cs:__imp_SetLastError
0x180064747  nop     dword ptr [rax+rax+00h]
0x18006474c  xor     ebp, ebp
0x18006474e  jmp     short loc_180064752
0x180064750  xor     ebx, ebx
0x180064752  mov     rax, [rsp+58h+arg_0]
0x180064757  mov     [rax], r13w
0x18006475b  mov     rax, [rsp+58h+arg_0]
0x180064760  add     rax, 2
0x180064764  mov     [rsp+58h+arg_0], rax
0x180064769  cmp     ebp, 1
0x18006476c  jz      loc_1800646D1
0x180064772  call    cs:__imp_GetLastError
0x180064779  nop     dword ptr [rax+rax+00h]
0x18006477e  mov     r9, rsi
0x180064781  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180064788  jmp     short loc_180064804
0x18006478a  mov     rcx, rdi; lpPathName
0x18006478d  call    cs:__imp_CreateDirectoryW
0x180064794  nop     dword ptr [rax+rax+00h]
0x180064799  test    eax, eax
0x18006479b  jnz     short loc_180064815
0x18006479d  call    cs:__imp_GetLastError
0x1800647a4  nop     dword ptr [rax+rax+00h]
0x1800647a9  mov     ebx, eax
0x1800647ab  cmp     eax, 0B7h
0x1800647b0  jz      short loc_1800647BE
0x1800647b2  mov     r9, rdi
0x1800647b5  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x1800647bc  jmp     short loc_180064806
0x1800647be  mov     rcx, rdi; lpFileName
0x1800647c1  call    cs:__imp_GetFileAttributesW
0x1800647c8  nop     dword ptr [rax+rax+00h]
0x1800647cd  cmp     eax, 0FFFFFFFFh
0x1800647d0  jz      short loc_1800647EE
0x1800647d2  test    al, 10h
0x1800647d4  jz      short loc_1800647DA
0x1800647d6  xor     ebx, ebx
0x1800647d8  jmp     short loc_180064815
0x1800647da  mov     dword ptr [rsp+58h+var_38], 0B7h
0x1800647e2  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x1800647e9  mov     r9, rdi
0x1800647ec  jmp     short loc_18006480A
0x1800647ee  call    cs:__imp_GetLastError
0x1800647f5  nop     dword ptr [rax+rax+00h]
0x1800647fa  mov     r9, rdi
0x1800647fd  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x180064804  mov     ebx, eax
0x180064806  mov     dword ptr [rsp+58h+var_38], eax
0x18006480a  mov     edx, r14d
0x18006480d  mov     rcx, r15
0x180064810  call    LibLog
0x180064815  call    cs:__imp_GetProcessHeap
0x18006481c  nop     dword ptr [rax+rax+00h]
0x180064821  mov     r8, rdi; lpMem
0x180064824  xor     edx, edx; dwFlags
0x180064826  mov     rcx, rax; hHeap
0x180064829  call    cs:__imp_HeapFree
0x180064830  nop     dword ptr [rax+rax+00h]
0x180064835  jmp     short loc_180064845
0x180064837  call    cs:__imp_GetLastError
0x18006483e  nop     dword ptr [rax+rax+00h]
0x180064843  mov     ebx, eax
0x180064845  mov     ecx, ebx; dwErrCode
0x180064847  call    cs:__imp_SetLastError
0x18006484e  nop     dword ptr [rax+rax+00h]
0x180064853  xor     eax, eax
0x180064855  test    ebx, ebx
0x180064857  setz    al
0x18006485a  jmp     short loc_18006486F
0x18006485c  mov     ecx, 57h ; 'W'; dwErrCode
0x180064861  call    cs:__imp_SetLastError
0x180064868  nop     dword ptr [rax+rax+00h]
0x18006486d  xor     eax, eax
0x18006486f  mov     rbx, [rsp+58h+arg_8]
0x180064874  mov     rbp, [rsp+58h+arg_10]
0x180064879  add     rsp, 30h
0x18006487d  pop     r15
0x18006487f  pop     r14
0x180064881  pop     r13
0x180064883  pop     rdi
0x180064884  pop     rsi
0x180064885  retn
```
