# MakeDirectory

- ea: `0x18002c42c`
- end: `0x18002c749`
- name: `MakeDirectory`
- size: `797`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180032688`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x18002bb58`
- `0x18002bcf8`
- `0x18002c42c`
- `0x18003d4e2`

## import_xrefs

- `msvcrt!iswalpha` at `0x18002c59b`
- `msvcrt!iswalpha` at `0x18002c59b`
- `msvcrt!wcschr` at `0x18002c531`
- `msvcrt!wcschr` at `0x18002c550`
- `msvcrt!wcschr` at `0x18002c632`
- `msvcrt!wcschr` at `0x18002c531`
- `msvcrt!wcschr` at `0x18002c550`
- `msvcrt!wcschr` at `0x18002c632`
- `KERNEL32!GetFileAttributesW` at `0x18002c4de`
- `KERNEL32!GetFileAttributesW` at `0x18002c4de`
- `KERNEL32!CreateDirectoryW` at `0x18002c5d0`
- `KERNEL32!CreateDirectoryW` at `0x18002c64f`
- `KERNEL32!CreateDirectoryW` at `0x18002c6b1`
- `KERNEL32!CreateDirectoryW` at `0x18002c5d0`
- `KERNEL32!CreateDirectoryW` at `0x18002c64f`
- `KERNEL32!CreateDirectoryW` at `0x18002c6b1`
- `KERNEL32!SetLastError` at `0x18002c724`
- `KERNEL32!SetLastError` at `0x18002c724`
- `KERNEL32!GetLastError` at `0x18002c48e`
- `KERNEL32!GetLastError` at `0x18002c5e0`
- `KERNEL32!GetLastError` at `0x18002c65f`
- `KERNEL32!GetLastError` at `0x18002c684`
- `KERNEL32!GetLastError` at `0x18002c6c1`
- `KERNEL32!GetLastError` at `0x18002c6d4`
- `KERNEL32!GetLastError` at `0x18002c48e`
- `KERNEL32!GetLastError` at `0x18002c5e0`
- `KERNEL32!GetLastError` at `0x18002c65f`
- `KERNEL32!GetLastError` at `0x18002c684`
- `KERNEL32!GetLastError` at `0x18002c6c1`
- `KERNEL32!GetLastError` at `0x18002c6d4`

## pseudocode

```c
_BOOL8 __fastcall MakeDirectory(unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rax
  wchar_t *v3; // rbx
  WCHAR *v4; // rbp
  DWORD LastError; // eax
  DWORD v6; // edi
  DWORD FileAttributesW; // eax
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rax
  DWORD v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  wchar_t *v13; // rax
  const wchar_t *v14; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  v2 = ExpandEnvironmentString(a1);
  v3 = v2;
  v4 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids, LastError);
    }
    goto LABEL_52;
  }
  FileAttributesW = GetFileAttributesW(v2);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
LABEL_12:
    v6 = 0;
    goto LABEL_52;
  }
  v8 = -1;
  do
    ++v8;
  while ( v3[v8] );
  if ( v8 <= 2 )
  {
    if ( v8 <= 1 )
      goto LABEL_34;
  }
  else if ( !wcsncmp_0(v3, L"\\\\", 2u) )
  {
    v9 = wcschr(v3 + 2, 0x5Cu);
    v3 = v9;
    if ( !v9 )
      goto LABEL_28;
    v3 = wcschr(v9 + 1, 0x5Cu);
    if ( !v3 )
      goto LABEL_28;
    goto LABEL_22;
  }
  if ( wcsncmp_0(v3, L"\\", 1u) )
  {
    if ( v8 <= 3 || !iswalpha(*v3) || wcsncmp_0(v3 + 1, L":\\", 2u) )
    {
LABEL_34:
      v6 = 0;
      while ( 1 )
      {
        v14 = v3 + 1;
        if ( !*v14 )
          goto LABEL_52;
        v13 = wcschr(v14, 0x5Cu);
        v3 = v13;
        if ( !v13 )
        {
          if ( !CreateDirectoryW(v4, 0) && GetLastError() != 183 )
          {
            v10 = GetLastError();
            v6 = v10;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 21;
              goto LABEL_51;
            }
          }
          goto LABEL_52;
        }
        *v13 = 0;
        if ( !CreateDirectoryW(v4, 0) && GetLastError() != 183 )
        {
          v10 = GetLastError();
          v6 = v10;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 22;
            goto LABEL_51;
          }
          goto LABEL_52;
        }
        *v3 = 92;
      }
    }
    v3 += 3;
    goto LABEL_27;
  }
LABEL_22:
  ++v3;
LABEL_27:
  if ( v3 )
    goto LABEL_34;
LABEL_28:
  if ( CreateDirectoryW(v4, 0) )
    goto LABEL_34;
  v10 = GetLastError();
  v6 = v10;
  if ( v10 == 183 )
    goto LABEL_12;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 20;
LABEL_51:
    WPP_SF_Sd(v11[2], v12, (unsigned int)&WPP_04fb59550d79390d980a26525e0212b0_Traceguids, (_DWORD)v4, v10);
  }
LABEL_52:
  pMemFree(v4);
  if ( v6 )
    SetLastError(v6);
  return v6 == 0;
}

```

## disassembly

```asm
0x18002c42c  push    rbx
0x18002c42e  push    rbp
0x18002c42f  push    rdi
0x18002c430  push    r12
0x18002c432  push    r13
0x18002c434  push    r14
0x18002c436  push    r15
0x18002c438  sub     rsp, 30h
0x18002c43c  mov     rbx, rcx
0x18002c43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c446  lea     r12, WPP_GLOBAL_Control
0x18002c44d  mov     r15d, 2
0x18002c453  cmp     rcx, r12
0x18002c456  jz      short loc_18002C478
0x18002c458  test    [rcx+1Ch], r15b
0x18002c45c  jz      short loc_18002C478
0x18002c45e  cmp     byte ptr [rcx+19h], 5
0x18002c462  jb      short loc_18002C478
0x18002c464  mov     rcx, [rcx+10h]
0x18002c468  lea     edx, [r15+10h]
0x18002c46c  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c473  call    WPP_SF_
0x18002c478  mov     rcx, rbx; unsigned __int16 *
0x18002c47b  call    ExpandEnvironmentString
0x18002c480  xor     r14d, r14d
0x18002c483  mov     rbx, rax
0x18002c486  mov     rbp, rax
0x18002c489  test    rax, rax
0x18002c48c  jnz     short loc_18002C4DB
0x18002c48e  call    cs:__imp_GetLastError
0x18002c495  nop     dword ptr [rax+rax+00h]
0x18002c49a  mov     edi, eax
0x18002c49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4a3  cmp     rcx, r12
0x18002c4a6  jz      loc_18002C716
0x18002c4ac  test    [rcx+1Ch], r15b
0x18002c4b0  jz      loc_18002C716
0x18002c4b6  cmp     [rcx+19h], r15b
0x18002c4ba  jb      loc_18002C716
0x18002c4c0  mov     rcx, [rcx+10h]
0x18002c4c4  lea     edx, [rbp+13h]
0x18002c4c7  mov     r9d, eax
0x18002c4ca  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c4d1  call    WPP_SF_d
0x18002c4d6  jmp     loc_18002C716
0x18002c4db  mov     rcx, rbx; lpFileName
0x18002c4de  call    cs:__imp_GetFileAttributesW
0x18002c4e5  nop     dword ptr [rax+rax+00h]
0x18002c4ea  cmp     eax, 0FFFFFFFFh
0x18002c4ed  jz      short loc_18002C4FB
0x18002c4ef  test    al, 10h
0x18002c4f1  jz      short loc_18002C4FB
0x18002c4f3  mov     edi, r14d
0x18002c4f6  jmp     loc_18002C716
0x18002c4fb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c4ff  inc     rdi
0x18002c502  cmp     [rbx+rdi*2], r14w
0x18002c507  jnz     short loc_18002C4FF
0x18002c509  mov     r13d, 5Ch ; '\'
0x18002c50f  cmp     rdi, r15
0x18002c512  jbe     short loc_18002C566
0x18002c514  mov     r8d, r15d; MaxCount
0x18002c517  lea     rdx, SubStr; "\\\\"
0x18002c51e  mov     rcx, rbx; String1
0x18002c521  call    wcsncmp_0
0x18002c526  test    eax, eax
0x18002c528  jnz     short loc_18002C570
0x18002c52a  mov     edx, r13d; Ch
0x18002c52d  lea     rcx, [rbx+4]; Str
0x18002c531  call    cs:__imp_wcschr
0x18002c538  nop     dword ptr [rax+rax+00h]
0x18002c53d  mov     rbx, rax
0x18002c540  test    rax, rax
0x18002c543  jz      loc_18002C5CB
0x18002c549  mov     edx, r13d; Ch
0x18002c54c  lea     rcx, [rax+2]; Str
0x18002c550  call    cs:__imp_wcschr
0x18002c557  nop     dword ptr [rax+rax+00h]
0x18002c55c  mov     rbx, rax
0x18002c55f  test    rax, rax
0x18002c562  jz      short loc_18002C5CB
0x18002c564  jmp     short loc_18002C589
0x18002c566  cmp     rdi, 1
0x18002c56a  jbe     loc_18002C627
0x18002c570  mov     r8d, 1; MaxCount
0x18002c576  lea     rdx, SubBlock; "\\"
0x18002c57d  mov     rcx, rbx; String1
0x18002c580  call    wcsncmp_0
0x18002c585  test    eax, eax
0x18002c587  jnz     short loc_18002C58E
0x18002c589  add     rbx, r15
0x18002c58c  jmp     short loc_18002C5C6
0x18002c58e  cmp     rdi, 3
0x18002c592  jbe     loc_18002C627
0x18002c598  movzx   ecx, word ptr [rbx]; C
0x18002c59b  call    cs:__imp_iswalpha
0x18002c5a2  nop     dword ptr [rax+rax+00h]
0x18002c5a7  test    eax, eax
0x18002c5a9  jz      short loc_18002C627
0x18002c5ab  lea     rcx, [rbx+2]; String1
0x18002c5af  mov     r8d, r15d; MaxCount
0x18002c5b2  lea     rdx, asc_180043CEC; ":\\"
0x18002c5b9  call    wcsncmp_0
0x18002c5be  test    eax, eax
0x18002c5c0  jnz     short loc_18002C627
0x18002c5c2  add     rbx, 6
0x18002c5c6  test    rbx, rbx
0x18002c5c9  jnz     short loc_18002C627
0x18002c5cb  xor     edx, edx; lpSecurityAttributes
0x18002c5cd  mov     rcx, rbp; lpPathName
0x18002c5d0  call    cs:__imp_CreateDirectoryW
0x18002c5d7  nop     dword ptr [rax+rax+00h]
0x18002c5dc  test    eax, eax
0x18002c5de  jnz     short loc_18002C627
0x18002c5e0  call    cs:__imp_GetLastError
0x18002c5e7  nop     dword ptr [rax+rax+00h]
0x18002c5ec  mov     edi, eax
0x18002c5ee  cmp     eax, 0B7h
0x18002c5f3  jz      loc_18002C4F3
0x18002c5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c600  cmp     rcx, r12
0x18002c603  jz      loc_18002C716
0x18002c609  test    [rcx+1Ch], r15b
0x18002c60d  jz      loc_18002C716
0x18002c613  cmp     [rcx+19h], r15b
0x18002c617  jb      loc_18002C716
0x18002c61d  mov     edx, 14h
0x18002c622  jmp     loc_18002C6FF
0x18002c627  mov     edi, r14d
0x18002c62a  jmp     short loc_18002C676
0x18002c62c  mov     edx, r13d; Ch
0x18002c62f  mov     rcx, rbx; Str
0x18002c632  call    cs:__imp_wcschr
0x18002c639  nop     dword ptr [rax+rax+00h]
0x18002c63e  xor     edx, edx; lpSecurityAttributes
0x18002c640  mov     rcx, rbp; lpPathName
0x18002c643  mov     rbx, rax
0x18002c646  test    rax, rax
0x18002c649  jz      short loc_18002C6B1
0x18002c64b  mov     [rax], r14w
0x18002c64f  call    cs:__imp_CreateDirectoryW
0x18002c656  nop     dword ptr [rax+rax+00h]
0x18002c65b  test    eax, eax
0x18002c65d  jnz     short loc_18002C672
0x18002c65f  call    cs:__imp_GetLastError
0x18002c666  nop     dword ptr [rax+rax+00h]
0x18002c66b  cmp     eax, 0B7h
0x18002c670  jnz     short loc_18002C684
0x18002c672  mov     [rbx], r13w
0x18002c676  add     rbx, r15
0x18002c679  cmp     [rbx], r14w
0x18002c67d  jnz     short loc_18002C62C
0x18002c67f  jmp     loc_18002C716
0x18002c684  call    cs:__imp_GetLastError
0x18002c68b  nop     dword ptr [rax+rax+00h]
0x18002c690  mov     edi, eax
0x18002c692  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c699  cmp     rcx, r12
0x18002c69c  jz      short loc_18002C716
0x18002c69e  test    [rcx+1Ch], r15b
0x18002c6a2  jz      short loc_18002C716
0x18002c6a4  cmp     [rcx+19h], r15b
0x18002c6a8  jb      short loc_18002C716
0x18002c6aa  mov     edx, 16h
0x18002c6af  jmp     short loc_18002C6FF
0x18002c6b1  call    cs:__imp_CreateDirectoryW
0x18002c6b8  nop     dword ptr [rax+rax+00h]
0x18002c6bd  test    eax, eax
0x18002c6bf  jnz     short loc_18002C716
0x18002c6c1  call    cs:__imp_GetLastError
0x18002c6c8  nop     dword ptr [rax+rax+00h]
0x18002c6cd  cmp     eax, 0B7h
0x18002c6d2  jz      short loc_18002C716
0x18002c6d4  call    cs:__imp_GetLastError
0x18002c6db  nop     dword ptr [rax+rax+00h]
0x18002c6e0  mov     edi, eax
0x18002c6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6e9  cmp     rcx, r12
0x18002c6ec  jz      short loc_18002C716
0x18002c6ee  test    [rcx+1Ch], r15b
0x18002c6f2  jz      short loc_18002C716
0x18002c6f4  cmp     [rcx+19h], r15b
0x18002c6f8  jb      short loc_18002C716
0x18002c6fa  mov     edx, 15h
0x18002c6ff  mov     rcx, [rcx+10h]
0x18002c703  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c70a  mov     r9, rbp
0x18002c70d  mov     [rsp+68h+var_48], eax
0x18002c711  call    WPP_SF_Sd
0x18002c716  mov     rcx, rbp; lpMem
0x18002c719  call    pMemFree
0x18002c71e  test    edi, edi
0x18002c720  jz      short loc_18002C730
0x18002c722  mov     ecx, edi; dwErrCode
0x18002c724  call    cs:__imp_SetLastError
0x18002c72b  nop     dword ptr [rax+rax+00h]
0x18002c730  test    edi, edi
0x18002c732  mov     eax, r14d
0x18002c735  setz    al
0x18002c738  add     rsp, 30h
0x18002c73c  pop     r15
0x18002c73e  pop     r14
0x18002c740  pop     r13
0x18002c742  pop     r12
0x18002c744  pop     rdi
0x18002c745  pop     rbp
0x18002c746  pop     rbx
0x18002c747  retn
```
