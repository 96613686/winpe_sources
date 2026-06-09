# MakeDirectory

- ea: `0x14006ab10`
- end: `0x14006ae2d`
- name: `MakeDirectory`
- size: `797`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140078b10`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14006998c`
- `0x14006a574`
- `0x14006ab10`
- `0x140086e8e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006ab72`
- `KERNEL32!GetLastError` at `0x14006acc4`
- `KERNEL32!GetLastError` at `0x14006ad43`
- `KERNEL32!GetLastError` at `0x14006ad68`
- `KERNEL32!GetLastError` at `0x14006ada5`
- `KERNEL32!GetLastError` at `0x14006adb8`
- `KERNEL32!GetLastError` at `0x14006ab72`
- `KERNEL32!GetLastError` at `0x14006acc4`
- `KERNEL32!GetLastError` at `0x14006ad43`
- `KERNEL32!GetLastError` at `0x14006ad68`
- `KERNEL32!GetLastError` at `0x14006ada5`
- `KERNEL32!GetLastError` at `0x14006adb8`
- `KERNEL32!SetLastError` at `0x14006ae08`
- `KERNEL32!SetLastError` at `0x14006ae08`
- `KERNEL32!GetFileAttributesW` at `0x14006abc2`
- `KERNEL32!GetFileAttributesW` at `0x14006abc2`
- `KERNEL32!CreateDirectoryW` at `0x14006acb4`
- `KERNEL32!CreateDirectoryW` at `0x14006ad33`
- `KERNEL32!CreateDirectoryW` at `0x14006ad95`
- `KERNEL32!CreateDirectoryW` at `0x14006acb4`
- `KERNEL32!CreateDirectoryW` at `0x14006ad33`
- `KERNEL32!CreateDirectoryW` at `0x14006ad95`
- `msvcrt!iswalpha` at `0x14006ac7f`
- `msvcrt!iswalpha` at `0x14006ac7f`
- `msvcrt!wcschr` at `0x14006ac15`
- `msvcrt!wcschr` at `0x14006ac34`
- `msvcrt!wcschr` at `0x14006ad16`
- `msvcrt!wcschr` at `0x14006ac15`
- `msvcrt!wcschr` at `0x14006ac34`
- `msvcrt!wcschr` at `0x14006ad16`

## pseudocode

```c
_BOOL8 __fastcall MakeDirectory(unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  wchar_t *v3; // rbx
  WCHAR *v4; // rbp
  DWORD LastError; // eax
  DWORD v6; // edi
  DWORD FileAttributesW; // eax
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rax
  DWORD v10; // eax
  CMapDeviceId *v11; // rcx
  int v12; // edx
  wchar_t *v13; // rax
  const wchar_t *v14; // rbx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  v2 = (const WCHAR *)ExpandEnvironmentString(a1);
  v3 = (wchar_t *)v2;
  v4 = (WCHAR *)v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_04fb59550d79390d980a26525e0212b0_Traceguids, LastError);
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
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 20;
LABEL_51:
    WPP_SF_Sd(*((_QWORD *)v11 + 2), v12, (unsigned int)WPP_04fb59550d79390d980a26525e0212b0_Traceguids, (_DWORD)v4, v10);
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
0x14006ab10  push    rbx
0x14006ab12  push    rbp
0x14006ab13  push    rdi
0x14006ab14  push    r12
0x14006ab16  push    r13
0x14006ab18  push    r14
0x14006ab1a  push    r15
0x14006ab1c  sub     rsp, 30h
0x14006ab20  mov     rbx, rcx
0x14006ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ab2a  lea     r12, WPP_GLOBAL_Control
0x14006ab31  mov     r15d, 2
0x14006ab37  cmp     rcx, r12
0x14006ab3a  jz      short loc_14006AB5C
0x14006ab3c  test    [rcx+1Ch], r15b
0x14006ab40  jz      short loc_14006AB5C
0x14006ab42  cmp     byte ptr [rcx+19h], 5
0x14006ab46  jb      short loc_14006AB5C
0x14006ab48  mov     rcx, [rcx+10h]
0x14006ab4c  lea     edx, [r15+10h]
0x14006ab50  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x14006ab57  call    WPP_SF_
0x14006ab5c  mov     rcx, rbx; unsigned __int16 *
0x14006ab5f  call    ExpandEnvironmentString
0x14006ab64  xor     r14d, r14d
0x14006ab67  mov     rbx, rax
0x14006ab6a  mov     rbp, rax
0x14006ab6d  test    rax, rax
0x14006ab70  jnz     short loc_14006ABBF
0x14006ab72  call    cs:__imp_GetLastError
0x14006ab79  nop     dword ptr [rax+rax+00h]
0x14006ab7e  mov     edi, eax
0x14006ab80  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ab87  cmp     rcx, r12
0x14006ab8a  jz      loc_14006ADFA
0x14006ab90  test    [rcx+1Ch], r15b
0x14006ab94  jz      loc_14006ADFA
0x14006ab9a  cmp     [rcx+19h], r15b
0x14006ab9e  jb      loc_14006ADFA
0x14006aba4  mov     rcx, [rcx+10h]
0x14006aba8  lea     edx, [rbp+13h]
0x14006abab  mov     r9d, eax
0x14006abae  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x14006abb5  call    WPP_SF_d
0x14006abba  jmp     loc_14006ADFA
0x14006abbf  mov     rcx, rbx; lpFileName
0x14006abc2  call    cs:__imp_GetFileAttributesW
0x14006abc9  nop     dword ptr [rax+rax+00h]
0x14006abce  cmp     eax, 0FFFFFFFFh
0x14006abd1  jz      short loc_14006ABDF
0x14006abd3  test    al, 10h
0x14006abd5  jz      short loc_14006ABDF
0x14006abd7  mov     edi, r14d
0x14006abda  jmp     loc_14006ADFA
0x14006abdf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006abe3  inc     rdi
0x14006abe6  cmp     [rbx+rdi*2], r14w
0x14006abeb  jnz     short loc_14006ABE3
0x14006abed  mov     r13d, 5Ch ; '\'
0x14006abf3  cmp     rdi, r15
0x14006abf6  jbe     short loc_14006AC4A
0x14006abf8  mov     r8d, r15d; MaxCount
0x14006abfb  lea     rdx, asc_1400954A8; "\\\\"
0x14006ac02  mov     rcx, rbx; String1
0x14006ac05  call    wcsncmp_0
0x14006ac0a  test    eax, eax
0x14006ac0c  jnz     short loc_14006AC54
0x14006ac0e  mov     edx, r13d; Ch
0x14006ac11  lea     rcx, [rbx+4]; Str
0x14006ac15  call    cs:__imp_wcschr
0x14006ac1c  nop     dword ptr [rax+rax+00h]
0x14006ac21  mov     rbx, rax
0x14006ac24  test    rax, rax
0x14006ac27  jz      loc_14006ACAF
0x14006ac2d  mov     edx, r13d; Ch
0x14006ac30  lea     rcx, [rax+2]; Str
0x14006ac34  call    cs:__imp_wcschr
0x14006ac3b  nop     dword ptr [rax+rax+00h]
0x14006ac40  mov     rbx, rax
0x14006ac43  test    rax, rax
0x14006ac46  jz      short loc_14006ACAF
0x14006ac48  jmp     short loc_14006AC6D
0x14006ac4a  cmp     rdi, 1
0x14006ac4e  jbe     loc_14006AD0B
0x14006ac54  mov     r8d, 1; MaxCount
0x14006ac5a  lea     rdx, SubBlock; "\\"
0x14006ac61  mov     rcx, rbx; String1
0x14006ac64  call    wcsncmp_0
0x14006ac69  test    eax, eax
0x14006ac6b  jnz     short loc_14006AC72
0x14006ac6d  add     rbx, r15
0x14006ac70  jmp     short loc_14006ACAA
0x14006ac72  cmp     rdi, 3
0x14006ac76  jbe     loc_14006AD0B
0x14006ac7c  movzx   ecx, word ptr [rbx]; C
0x14006ac7f  call    cs:__imp_iswalpha
0x14006ac86  nop     dword ptr [rax+rax+00h]
0x14006ac8b  test    eax, eax
0x14006ac8d  jz      short loc_14006AD0B
0x14006ac8f  lea     rcx, [rbx+2]; String1
0x14006ac93  mov     r8d, r15d; MaxCount
0x14006ac96  lea     rdx, asc_1400954B0; ":\\"
0x14006ac9d  call    wcsncmp_0
0x14006aca2  test    eax, eax
0x14006aca4  jnz     short loc_14006AD0B
0x14006aca6  add     rbx, 6
0x14006acaa  test    rbx, rbx
0x14006acad  jnz     short loc_14006AD0B
0x14006acaf  xor     edx, edx; lpSecurityAttributes
0x14006acb1  mov     rcx, rbp; lpPathName
0x14006acb4  call    cs:__imp_CreateDirectoryW
0x14006acbb  nop     dword ptr [rax+rax+00h]
0x14006acc0  test    eax, eax
0x14006acc2  jnz     short loc_14006AD0B
0x14006acc4  call    cs:__imp_GetLastError
0x14006accb  nop     dword ptr [rax+rax+00h]
0x14006acd0  mov     edi, eax
0x14006acd2  cmp     eax, 0B7h
0x14006acd7  jz      loc_14006ABD7
0x14006acdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ace4  cmp     rcx, r12
0x14006ace7  jz      loc_14006ADFA
0x14006aced  test    [rcx+1Ch], r15b
0x14006acf1  jz      loc_14006ADFA
0x14006acf7  cmp     [rcx+19h], r15b
0x14006acfb  jb      loc_14006ADFA
0x14006ad01  mov     edx, 14h
0x14006ad06  jmp     loc_14006ADE3
0x14006ad0b  mov     edi, r14d
0x14006ad0e  jmp     short loc_14006AD5A
0x14006ad10  mov     edx, r13d; Ch
0x14006ad13  mov     rcx, rbx; Str
0x14006ad16  call    cs:__imp_wcschr
0x14006ad1d  nop     dword ptr [rax+rax+00h]
0x14006ad22  xor     edx, edx; lpSecurityAttributes
0x14006ad24  mov     rcx, rbp; lpPathName
0x14006ad27  mov     rbx, rax
0x14006ad2a  test    rax, rax
0x14006ad2d  jz      short loc_14006AD95
0x14006ad2f  mov     [rax], r14w
0x14006ad33  call    cs:__imp_CreateDirectoryW
0x14006ad3a  nop     dword ptr [rax+rax+00h]
0x14006ad3f  test    eax, eax
0x14006ad41  jnz     short loc_14006AD56
0x14006ad43  call    cs:__imp_GetLastError
0x14006ad4a  nop     dword ptr [rax+rax+00h]
0x14006ad4f  cmp     eax, 0B7h
0x14006ad54  jnz     short loc_14006AD68
0x14006ad56  mov     [rbx], r13w
0x14006ad5a  add     rbx, r15
0x14006ad5d  cmp     [rbx], r14w
0x14006ad61  jnz     short loc_14006AD10
0x14006ad63  jmp     loc_14006ADFA
0x14006ad68  call    cs:__imp_GetLastError
0x14006ad6f  nop     dword ptr [rax+rax+00h]
0x14006ad74  mov     edi, eax
0x14006ad76  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad7d  cmp     rcx, r12
0x14006ad80  jz      short loc_14006ADFA
0x14006ad82  test    [rcx+1Ch], r15b
0x14006ad86  jz      short loc_14006ADFA
0x14006ad88  cmp     [rcx+19h], r15b
0x14006ad8c  jb      short loc_14006ADFA
0x14006ad8e  mov     edx, 16h
0x14006ad93  jmp     short loc_14006ADE3
0x14006ad95  call    cs:__imp_CreateDirectoryW
0x14006ad9c  nop     dword ptr [rax+rax+00h]
0x14006ada1  test    eax, eax
0x14006ada3  jnz     short loc_14006ADFA
0x14006ada5  call    cs:__imp_GetLastError
0x14006adac  nop     dword ptr [rax+rax+00h]
0x14006adb1  cmp     eax, 0B7h
0x14006adb6  jz      short loc_14006ADFA
0x14006adb8  call    cs:__imp_GetLastError
0x14006adbf  nop     dword ptr [rax+rax+00h]
0x14006adc4  mov     edi, eax
0x14006adc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006adcd  cmp     rcx, r12
0x14006add0  jz      short loc_14006ADFA
0x14006add2  test    [rcx+1Ch], r15b
0x14006add6  jz      short loc_14006ADFA
0x14006add8  cmp     [rcx+19h], r15b
0x14006addc  jb      short loc_14006ADFA
0x14006adde  mov     edx, 15h
0x14006ade3  mov     rcx, [rcx+10h]
0x14006ade7  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x14006adee  mov     r9, rbp
0x14006adf1  mov     [rsp+68h+var_48], eax
0x14006adf5  call    WPP_SF_Sd
0x14006adfa  mov     rcx, rbp; lpMem
0x14006adfd  call    pMemFree
0x14006ae02  test    edi, edi
0x14006ae04  jz      short loc_14006AE14
0x14006ae06  mov     ecx, edi; dwErrCode
0x14006ae08  call    cs:__imp_SetLastError
0x14006ae0f  nop     dword ptr [rax+rax+00h]
0x14006ae14  test    edi, edi
0x14006ae16  mov     eax, r14d
0x14006ae19  setz    al
0x14006ae1c  add     rsp, 30h
0x14006ae20  pop     r15
0x14006ae22  pop     r14
0x14006ae24  pop     r13
0x14006ae26  pop     r12
0x14006ae28  pop     rdi
0x14006ae29  pop     rbp
0x14006ae2a  pop     rbx
0x14006ae2b  retn
```
