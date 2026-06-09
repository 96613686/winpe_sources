# AddEnvInPath(ushort const *,ushort *,ulong)

- ea: `0x18000279c`
- end: `0x180002920`
- name: `?AddEnvInPath@@YAHPEBGPEAGK@Z`
- size: `388`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003a5c`
- `0x18000ed4c`
- `0x18000ef90`

## callees

- `0x1800022bc`
- `0x18000279c`
- `0x180002c74`
- `0x180003034`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x1800027e6`
- `KERNEL32!GetEnvironmentVariableW` at `0x180002843`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800027e6`
- `KERNEL32!GetEnvironmentVariableW` at `0x180002843`

## pseudocode

```c
__int64 __fastcall AddEnvInPath(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r15
  wchar_t *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // edx
  unsigned int v9; // edx
  WCHAR v11[8]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[104]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t v14[264]; // [rsp+320h] [rbp+220h] BYREF

  v3 = a3;
  v6 = a1;
  v7 = 0;
  if ( GetEnvironmentVariableW(L"SystemRoot", Buffer, 0x64u)
    && (unsigned int)ReplaceSubString(pszDest, v8, v6, Buffer, L"%SystemRoot%") )
  {
    v7 = 1;
    v6 = pszDest;
  }
  if ( (unsigned int)GetProgramFilesDir(Buffer, 0x64u) && GetEnvironmentVariableW(L"SystemDrive", v11, 5u) )
  {
    if ( ctx >= 3u && (unsigned int)ReplaceSubString(v14, v9, v6, Buffer, L"%ProgramFiles%") )
    {
      v7 = 1;
      StringCchCopyW(pszDest, 0x104u, v14);
      v6 = pszDest;
    }
    if ( (unsigned int)ReplaceSubString(v14, v9, v6, v11, L"%SystemDrive%") )
    {
      StringCchCopyW(pszDest, 0x104u, v14);
      v6 = pszDest;
      v7 = 1;
LABEL_13:
      StringCchCopyW(a2, v3, v6);
      return v7;
    }
  }
  if ( v7 || a2 != a1 )
    goto LABEL_13;
  return v7;
}

```

## disassembly

```asm
0x18000279c  mov     [rsp-8+arg_18], rbx
0x1800027a1  push    rbp
0x1800027a2  push    rsi
0x1800027a3  push    rdi
0x1800027a4  push    r14
0x1800027a6  push    r15
0x1800027a8  lea     rbp, [rsp-440h]
0x1800027b0  sub     rsp, 540h
0x1800027b7  mov     rax, cs:__security_cookie
0x1800027be  xor     rax, rsp
0x1800027c1  mov     [rbp+460h+var_30], rax
0x1800027c8  mov     r15d, r8d
0x1800027cb  mov     rsi, rdx
0x1800027ce  mov     r14, rcx
0x1800027d1  lea     rdx, [rsp+560h+Buffer]; lpBuffer
0x1800027d6  mov     rdi, rcx
0x1800027d9  xor     ebx, ebx
0x1800027db  lea     rcx, Name; "SystemRoot"
0x1800027e2  lea     r8d, [rbx+64h]; nSize
0x1800027e6  call    cs:__imp_GetEnvironmentVariableW
0x1800027ec  test    eax, eax
0x1800027ee  jz      short loc_18000281A
0x1800027f0  lea     rax, aSystemroot_0; "%SystemRoot%"
0x1800027f7  mov     r8, rdi; unsigned __int16 *
0x1800027fa  lea     r9, [rsp+560h+Buffer]; unsigned __int16 *
0x1800027ff  mov     [rsp+560h+var_540], rax; unsigned __int16 *
0x180002804  lea     rcx, [rbp+460h+pszDest]; pszDest
0x180002808  call    ?ReplaceSubString@@YAHPEAGIPEBG11@Z; ReplaceSubString(ushort *,uint,ushort const *,ushort const *,ushort const *)
0x18000280d  test    eax, eax
0x18000280f  jz      short loc_18000281A
0x180002811  mov     ebx, 1
0x180002816  lea     rdi, [rbp+460h+pszDest]
0x18000281a  mov     edx, 64h ; 'd'; unsigned int
0x18000281f  lea     rcx, [rsp+560h+Buffer]; unsigned __int16 *
0x180002824  call    ?GetProgramFilesDir@@YAHPEAGK@Z; GetProgramFilesDir(ushort *,ulong)
0x180002829  test    eax, eax
0x18000282b  jz      loc_1800028E1
0x180002831  mov     r8d, 5; nSize
0x180002837  lea     rdx, [rsp+560h+var_530]; lpBuffer
0x18000283c  lea     rcx, aSystemdrive; "SystemDrive"
0x180002843  call    cs:__imp_GetEnvironmentVariableW
0x180002849  test    eax, eax
0x18000284b  jz      loc_1800028E1
0x180002851  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 3; ADVCONTEXTW ctx
0x180002859  jb      short loc_18000289D
0x18000285b  lea     rax, aProgramfiles; "%ProgramFiles%"
0x180002862  mov     r8, rdi; unsigned __int16 *
0x180002865  lea     r9, [rsp+560h+Buffer]; unsigned __int16 *
0x18000286a  mov     [rsp+560h+var_540], rax; unsigned __int16 *
0x18000286f  lea     rcx, [rbp+460h+var_240]; pszDest
0x180002876  call    ?ReplaceSubString@@YAHPEAGIPEBG11@Z; ReplaceSubString(ushort *,uint,ushort const *,ushort const *,ushort const *)
0x18000287b  test    eax, eax
0x18000287d  jz      short loc_18000289D
0x18000287f  lea     r8, [rbp+460h+var_240]; unsigned __int16 *
0x180002886  mov     edx, 104h; unsigned __int64
0x18000288b  lea     rcx, [rbp+460h+pszDest]; unsigned __int16 *
0x18000288f  mov     ebx, 1
0x180002894  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002899  lea     rdi, [rbp+460h+pszDest]
0x18000289d  lea     rax, aSystemdrive_0; "%SystemDrive%"
0x1800028a4  mov     r8, rdi; unsigned __int16 *
0x1800028a7  lea     r9, [rsp+560h+var_530]; unsigned __int16 *
0x1800028ac  mov     [rsp+560h+var_540], rax; unsigned __int16 *
0x1800028b1  lea     rcx, [rbp+460h+var_240]; pszDest
0x1800028b8  call    ?ReplaceSubString@@YAHPEAGIPEBG11@Z; ReplaceSubString(ushort *,uint,ushort const *,ushort const *,ushort const *)
0x1800028bd  test    eax, eax
0x1800028bf  jz      short loc_1800028E1
0x1800028c1  lea     r8, [rbp+460h+var_240]; unsigned __int16 *
0x1800028c8  mov     edx, 104h; unsigned __int64
0x1800028cd  lea     rcx, [rbp+460h+pszDest]; unsigned __int16 *
0x1800028d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800028d6  lea     rdi, [rbp+460h+pszDest]
0x1800028da  mov     ebx, 1
0x1800028df  jmp     short loc_1800028EA
0x1800028e1  test    ebx, ebx
0x1800028e3  jnz     short loc_1800028EA
0x1800028e5  cmp     rsi, r14
0x1800028e8  jz      short loc_1800028F8
0x1800028ea  mov     rdx, r15; unsigned __int64
0x1800028ed  mov     r8, rdi; unsigned __int16 *
0x1800028f0  mov     rcx, rsi; unsigned __int16 *
0x1800028f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800028f8  mov     eax, ebx
0x1800028fa  mov     rcx, [rbp+460h+var_30]
0x180002901  xor     rcx, rsp; StackCookie
0x180002904  call    __security_check_cookie
0x180002909  mov     rbx, [rsp+560h+arg_18]
0x180002911  add     rsp, 540h
0x180002918  pop     r15
0x18000291a  pop     r14
0x18000291c  pop     rdi
0x18000291d  pop     rsi
0x18000291e  pop     rbp
0x18000291f  retn
```
