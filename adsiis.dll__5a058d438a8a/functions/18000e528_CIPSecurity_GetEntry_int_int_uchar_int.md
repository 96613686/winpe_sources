# CIPSecurity::GetEntry(int,int,uchar * *,int)

- ea: `0x18000e528`
- end: `0x18000e72d`
- name: `?GetEntry@CIPSecurity@@QEAAHHHPEAPEAEH@Z`
- size: `517`
- prototype: `int(CIPSecurity *__hidden this, int, int, unsigned __int8 **, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eab0`
- `0x18000ec00`
- `0x18000ed80`
- `0x18000eee0`

## callees

- `0x18000e528`
- `0x180019230`
- `0x18001ce84`
- `0x18001cf18`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e60c`
- `msvcrt!sprintf_s` at `0x18000e60c`
- `msvcrt!wcscpy_s` at `0x18000e6bd`
- `msvcrt!wcscpy_s` at `0x18000e6bd`
- `KERNEL32!MultiByteToWideChar` at `0x18000e6ea`
- `KERNEL32!MultiByteToWideChar` at `0x18000e6ea`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e682`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e69a`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e682`
- `ACTIVEDS!__imp_AllocADsMem` at `0x18000e69a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000e6f7`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000e6f7`

## pseudocode

```c
__int64 __fastcall CIPSecurity::GetEntry(CIPSecurity *this, int a2, int a3, LPVOID *a4, unsigned int a5)
{
  unsigned int Name; // r14d
  const CHAR *v7; // r13
  __int64 v8; // rbx
  __int64 v9; // rax
  int cchWideChar; // esi
  unsigned __int8 *lpWideCharStr; // rax
  unsigned int v12; // r12d
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rdi
  unsigned int v16; // [rsp+60h] [rbp-61h] BYREF
  LPCCH lpMultiByteStr; // [rsp+68h] [rbp-59h] BYREF
  unsigned __int8 *v18; // [rsp+70h] [rbp-51h] BYREF
  unsigned __int8 *v19; // [rsp+78h] [rbp-49h] BYREF
  char Buffer[80]; // [rsp+80h] [rbp-41h] BYREF

  v16 = 0;
  lpMultiByteStr = 0;
  Name = 0;
  *a4 = 0;
  if ( !a2 )
  {
    lpMultiByteStr = 0;
    Name = ADDRESS_CHECK::GetName((CIPSecurity *)((char *)this + 24), a3, a5, (char **)&lpMultiByteStr, &v16);
    if ( !Name )
      return Name;
    v7 = lpMultiByteStr;
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( lpMultiByteStr[v9] );
    cchWideChar = v9 + 1;
    if ( (v16 & 0x80000000) == 0 )
    {
      v12 = v9 + 3;
      v13 = (unsigned __int8 *)AllocADsMem(2 * ((int)v9 + 3));
      v14 = v13;
      if ( !v13 )
        return 0;
      *a4 = v13;
      wcscpy_s((wchar_t *)v13, v12, L"*.");
      do
        ++v8;
      while ( *(_WORD *)&v14[2 * v8] );
      lpWideCharStr = &v14[2 * v8];
    }
    else
    {
      lpWideCharStr = (unsigned __int8 *)AllocADsMem(2 * cchWideChar);
      if ( !lpWideCharStr )
        return 0;
      *a4 = lpWideCharStr;
    }
    if ( MultiByteToWideChar(0, 1u, v7, cchWideChar, (LPWSTR)lpWideCharStr, cchWideChar) )
      return Name;
    FreeADsMem(*a4);
    *a4 = 0;
    return 0;
  }
  if ( a2 == 1 )
  {
    v18 = 0;
    v19 = 0;
    Name = ADDRESS_CHECK::GetAddr((CIPSecurity *)((char *)this + 24), a3, a5, &v16, &v18, &v19);
    if ( Name )
    {
      sprintf_s(Buffer, 0x50u, "%d.%d.%d.%d, %d.%d.%d.%d", *v19, v19[1], v19[2], v19[3], *v18, v18[1], v18[2], v18[3]);
      if ( !AllocUnicode(Buffer, (unsigned __int16 **)&lpMultiByteStr) )
      {
        *a4 = (LPVOID)lpMultiByteStr;
        return Name;
      }
      return 0;
    }
  }
  return Name;
}

```

## disassembly

```asm
0x18000e528  mov     [rsp-8+arg_8], rbx
0x18000e52d  push    rbp
0x18000e52e  push    rsi
0x18000e52f  push    rdi
0x18000e530  push    r12
0x18000e532  push    r13
0x18000e534  push    r14
0x18000e536  push    r15
0x18000e538  lea     rbp, [rsp-1Fh]
0x18000e53d  sub     rsp, 0E0h
0x18000e544  mov     rax, cs:__security_cookie
0x18000e54b  xor     rax, rsp
0x18000e54e  mov     [rbp+4Fh+var_40], rax
0x18000e552  xor     r12d, r12d
0x18000e555  mov     r15, r9
0x18000e558  mov     [rbp+4Fh+var_B0], r12d
0x18000e55c  mov     r10d, r8d
0x18000e55f  mov     [rbp+4Fh+lpMultiByteStr], r12
0x18000e563  mov     r14d, r12d
0x18000e566  mov     [r9], r12
0x18000e569  test    edx, edx
0x18000e56b  jz      loc_18000E633
0x18000e571  cmp     edx, 1
0x18000e574  jnz     loc_18000E703
0x18000e57a  mov     r8d, [rbp+4Fh+arg_20]; unsigned int
0x18000e57e  lea     rax, [rbp+4Fh+var_98]
0x18000e582  mov     qword ptr [rsp+110h+cchWideChar], rax; unsigned __int8 **
0x18000e587  lea     r9, [rbp+4Fh+var_B0]; unsigned int *
0x18000e58b  lea     rax, [rbp+4Fh+var_A0]
0x18000e58f  mov     [rbp+4Fh+var_A0], r12
0x18000e593  add     rcx, 18h; this
0x18000e597  mov     [rsp+110h+lpWideCharStr], rax; unsigned __int8 **
0x18000e59c  mov     edx, r10d; int
0x18000e59f  mov     [rbp+4Fh+var_98], r12
0x18000e5a3  call    ?GetAddr@ADDRESS_CHECK@@QEAAHHKPEAKPEAPEAE1@Z; ADDRESS_CHECK::GetAddr(int,ulong,ulong *,uchar * *,uchar * *)
0x18000e5a8  mov     r14d, eax
0x18000e5ab  test    eax, eax
0x18000e5ad  jz      loc_18000E703
0x18000e5b3  mov     rcx, [rbp+4Fh+var_A0]
0x18000e5b7  movzx   r11d, byte ptr [rcx+3]
0x18000e5bc  movzx   ebx, byte ptr [rcx+2]
0x18000e5c0  movzx   edi, byte ptr [rcx+1]
0x18000e5c4  movzx   esi, byte ptr [rcx]
0x18000e5c7  mov     rcx, [rbp+4Fh+var_98]
0x18000e5cb  mov     [rsp+110h+var_C0], r11d
0x18000e5d0  mov     [rsp+110h+var_C8], ebx
0x18000e5d4  mov     [rsp+110h+var_D0], edi
0x18000e5d8  movzx   edx, byte ptr [rcx+3]
0x18000e5dc  movzx   r8d, byte ptr [rcx+2]
0x18000e5e1  movzx   r10d, byte ptr [rcx+1]
0x18000e5e6  movzx   r9d, byte ptr [rcx]
0x18000e5ea  lea     rcx, [rbp+4Fh+Buffer]; Buffer
0x18000e5ee  mov     [rsp+110h+var_D8], esi
0x18000e5f2  mov     [rsp+110h+var_E0], edx
0x18000e5f6  lea     edx, [r12+50h]; BufferCount
0x18000e5fb  mov     [rsp+110h+cchWideChar], r8d
0x18000e600  lea     r8, Format; "%d.%d.%d.%d, %d.%d.%d.%d"
0x18000e607  mov     dword ptr [rsp+110h+lpWideCharStr], r10d
0x18000e60c  call    cs:__imp_sprintf_s
0x18000e612  lea     rdx, [rbp+4Fh+lpMultiByteStr]; unsigned __int16 **
0x18000e616  lea     rcx, [rbp+4Fh+Buffer]; lpMultiByteStr
0x18000e61a  call    ?AllocUnicode@@YAIPEBDPEAPEAG@Z; AllocUnicode(char const *,ushort * *)
0x18000e61f  test    eax, eax
0x18000e621  jnz     loc_18000E700
0x18000e627  mov     rax, [rbp+4Fh+lpMultiByteStr]
0x18000e62b  mov     [r15], rax
0x18000e62e  jmp     loc_18000E703
0x18000e633  mov     r8d, [rbp+4Fh+arg_20]; unsigned int
0x18000e637  lea     rax, [rbp+4Fh+var_B0]
0x18000e63b  add     rcx, 18h; this
0x18000e63f  mov     [rsp+110h+lpWideCharStr], rax; unsigned int *
0x18000e644  lea     r9, [rbp+4Fh+lpMultiByteStr]; char **
0x18000e648  mov     [rbp+4Fh+lpMultiByteStr], r12
0x18000e64c  mov     edx, r10d; int
0x18000e64f  call    ?GetName@ADDRESS_CHECK@@QEAAHHKPEAPEADPEAK@Z; ADDRESS_CHECK::GetName(int,ulong,char * *,ulong *)
0x18000e654  mov     r14d, eax
0x18000e657  test    eax, eax
0x18000e659  jz      loc_18000E703
0x18000e65f  mov     r13, [rbp+4Fh+lpMultiByteStr]
0x18000e663  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e667  mov     rax, rbx
0x18000e66a  inc     rax
0x18000e66d  cmp     [rax+r13], r12b
0x18000e671  jnz     short loc_18000E66A
0x18000e673  test    [rbp+4Fh+var_B0], 80000000h
0x18000e67a  lea     esi, [rax+1]
0x18000e67d  jz      short loc_18000E692
0x18000e67f  lea     ecx, [rsi+rsi]; cb
0x18000e682  call    cs:__imp_AllocADsMem
0x18000e688  test    rax, rax
0x18000e68b  jz      short loc_18000E700
0x18000e68d  mov     [r15], rax
0x18000e690  jmp     short loc_18000E6D4
0x18000e692  lea     r12d, [rsi+2]
0x18000e696  lea     ecx, [r12+r12]; cb
0x18000e69a  call    cs:__imp_AllocADsMem
0x18000e6a0  mov     rdi, rax
0x18000e6a3  test    rax, rax
0x18000e6a6  jnz     short loc_18000E6AD
0x18000e6a8  xor     r14d, r14d
0x18000e6ab  jmp     short loc_18000E703
0x18000e6ad  mov     edx, r12d; SizeInWords
0x18000e6b0  lea     r8, asc_1800211FC; "*."
0x18000e6b7  mov     rcx, rdi; Destination
0x18000e6ba  mov     [r15], rdi
0x18000e6bd  call    cs:__imp_wcscpy_s
0x18000e6c3  xor     r12d, r12d
0x18000e6c6  inc     rbx
0x18000e6c9  cmp     [rdi+rbx*2], r12w
0x18000e6ce  jnz     short loc_18000E6C6
0x18000e6d0  lea     rax, [rdi+rbx*2]
0x18000e6d4  mov     [rsp+110h+cchWideChar], esi; cchWideChar
0x18000e6d8  mov     r9d, esi; cbMultiByte
0x18000e6db  mov     r8, r13; lpMultiByteStr
0x18000e6de  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x18000e6e3  mov     edx, 1; dwFlags
0x18000e6e8  xor     ecx, ecx; CodePage
0x18000e6ea  call    cs:__imp_MultiByteToWideChar
0x18000e6f0  test    eax, eax
0x18000e6f2  jnz     short loc_18000E703
0x18000e6f4  mov     rcx, [r15]; pMem
0x18000e6f7  call    cs:__imp_FreeADsMem
0x18000e6fd  mov     [r15], r12
0x18000e700  mov     r14d, r12d
0x18000e703  mov     eax, r14d
0x18000e706  mov     rcx, [rbp+4Fh+var_40]
0x18000e70a  xor     rcx, rsp; StackCookie
0x18000e70d  call    __security_check_cookie
0x18000e712  mov     rbx, [rsp+110h+arg_8]
0x18000e71a  add     rsp, 0E0h
0x18000e721  pop     r15
0x18000e723  pop     r14
0x18000e725  pop     r13
0x18000e727  pop     r12
0x18000e729  pop     rdi
0x18000e72a  pop     rsi
0x18000e72b  pop     rbp
0x18000e72c  retn
```
