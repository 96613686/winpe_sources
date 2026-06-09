# CreateFullPath(ushort const *,int)

- ea: `0x18000521c`
- end: `0x1800053e8`
- name: `?CreateFullPath@@YAJPEBGH@Z`
- size: `460`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800056d0`
- `0x1800063c4`
- `0x18000e060`
- `0x18000ec98`
- `0x1800152d8`
- `0x180015ef8`
- `0x1800166cc`

## callees

- `0x1800022bc`
- `0x18000521c`
- `0x1800082f0`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x1800052ed`
- `USER32!CharNextW` at `0x18000530f`
- `USER32!CharNextW` at `0x18000533b`
- `USER32!CharNextW` at `0x1800053a0`
- `USER32!CharNextW` at `0x1800052ed`
- `USER32!CharNextW` at `0x18000530f`
- `USER32!CharNextW` at `0x18000533b`
- `USER32!CharNextW` at `0x1800053a0`
- `USER32!CharPrevW` at `0x1800052a1`
- `USER32!CharPrevW` at `0x1800052a1`
- `KERNEL32!GetLastError` at `0x1800053ae`
- `KERNEL32!GetLastError` at `0x1800053ae`
- `KERNEL32!GetFileAttributesW` at `0x18000535e`
- `KERNEL32!GetFileAttributesW` at `0x18000535e`
- `KERNEL32!CreateDirectoryW` at `0x180005370`
- `KERNEL32!CreateDirectoryW` at `0x180005370`
- `KERNEL32!SetFileAttributesW` at `0x18000538d`
- `KERNEL32!SetFileAttributesW` at `0x18000538d`

## pseudocode

```c
__int64 __fastcall CreateFullPath(const unsigned __int16 *a1, int a2)
{
  const unsigned __int16 *v3; // rcx
  unsigned int v4; // ebx
  unsigned __int64 v5; // rax
  LPWSTR v6; // rax
  WCHAR *p_sz; // rax
  int v8; // ebx
  LPWSTR v9; // rdi
  int v10; // esi
  WCHAR v11; // ax
  bool v12; // zf
  signed int LastError; // eax
  WCHAR szStart[2]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR sz; // [rsp+24h] [rbp-DCh] BYREF
  char v17; // [rsp+26h] [rbp-DAh] BYREF

  if ( !(unsigned int)IsFullPath(a1) )
    return (unsigned int)-2147024735;
  StringCchCopyW(szStart, 0x104u, v3);
  v5 = -1;
  do
    ++v5;
  while ( szStart[v5] );
  if ( v5 > 3 )
  {
    v6 = CharPrevW(szStart, &szStart[v5]);
    if ( v6 > szStart && *v6 == 92 )
      *v6 = 0;
  }
  if ( szStart[0] == 92 && szStart[1] == 92 )
  {
    p_sz = &sz;
    v8 = 0;
LABEL_12:
    if ( v8 < 2 )
    {
      while ( 1 )
      {
        if ( *p_sz == 92 )
        {
          ++v8;
          goto LABEL_12;
        }
        if ( !*p_sz )
          return v8 != 0 ? 0 : 0x800700A1;
        p_sz = CharNextW(p_sz);
      }
    }
    v9 = CharNextW(p_sz);
  }
  else
  {
    v9 = (LPWSTR)&v17;
  }
  v10 = 0;
  v4 = 0;
  while ( 1 )
  {
    v11 = *v9;
    if ( !*v9 )
      break;
    while ( v11 != 92 && v11 )
    {
      v9 = CharNextW(v9);
      v11 = *v9;
    }
    v12 = *v9 == 0;
    *v9 = 0;
    if ( v12 )
      v10 = 1;
    if ( GetFileAttributesW(szStart) == -1 )
    {
      if ( !CreateDirectoryW(szStart, 0) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return v4;
      }
      if ( v10 )
      {
        if ( a2 )
          SetFileAttributesW(szStart, 2u);
        return v4;
      }
    }
    else if ( v10 )
    {
      return v4;
    }
    *v9 = 92;
    v9 = CharNextW(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x18000521c  push    rbp
0x18000521e  push    rbx
0x18000521f  push    rsi
0x180005220  push    rdi
0x180005221  push    r12
0x180005223  push    r13
0x180005225  push    r14
0x180005227  push    r15
0x180005229  lea     rbp, [rsp-148h]
0x180005231  sub     rsp, 248h
0x180005238  mov     rax, cs:__security_cookie
0x18000523f  xor     rax, rsp
0x180005242  mov     [rbp+180h+var_50], rax
0x180005249  mov     r14d, edx
0x18000524c  call    ?IsFullPath@@YAHPEBG@Z
0x180005251  xor     r15d, r15d
0x180005254  test    eax, eax
0x180005256  jnz     short loc_180005262
0x180005258  mov     ebx, 800700A1h
0x18000525d  jmp     loc_1800053C3
0x180005262  mov     r8, rcx; unsigned __int16 *
0x180005265  mov     edx, 104h; unsigned __int64
0x18000526a  lea     rcx, [rsp+280h+szStart]; unsigned __int16 *
0x18000526f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x180005274  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005278  lea     r11, [rsp+280h+szStart]
0x18000527d  inc     rax
0x180005280  cmp     [r11+rax*2], r15w
0x180005285  jnz     short loc_18000527D
0x180005287  mov     r12d, 5Ch ; '\'
0x18000528d  cmp     rax, 3
0x180005291  jbe     short loc_1800052BB
0x180005293  lea     rdx, [rsp+280h+szStart]
0x180005298  lea     rdx, [rdx+rax*2]; lpszCurrent
0x18000529c  lea     rcx, [rsp+280h+szStart]; lpszStart
0x1800052a1  call    cs:__imp_CharPrevW
0x1800052a7  lea     rcx, [rsp+280h+szStart]
0x1800052ac  cmp     rax, rcx
0x1800052af  jbe     short loc_1800052BB
0x1800052b1  cmp     [rax], r12w
0x1800052b5  jnz     short loc_1800052BB
0x1800052b7  mov     [rax], r15w
0x1800052bb  mov     r13d, 1
0x1800052c1  cmp     [rsp+280h+szStart], r12w
0x1800052c7  jnz     short loc_18000531A
0x1800052c9  cmp     [rsp+280h+var_25E], r12w
0x1800052cf  jnz     short loc_18000531A
0x1800052d1  lea     rax, [rsp+280h+sz]
0x1800052d6  mov     ebx, r15d
0x1800052d9  cmp     ebx, 2
0x1800052dc  jge     short loc_18000530C
0x1800052de  cmp     [rax], r12w
0x1800052e2  jz      short loc_1800052F5
0x1800052e4  cmp     [rax], r15w
0x1800052e8  jz      short loc_1800052FA
0x1800052ea  mov     rcx, rax; lpsz
0x1800052ed  call    cs:__imp_CharNextW
0x1800052f3  jmp     short loc_1800052DE
0x1800052f5  add     ebx, r13d
0x1800052f8  jmp     short loc_1800052D9
0x1800052fa  neg     ebx
0x1800052fc  mov     ebx, 800700A1h
0x180005301  sbb     eax, eax
0x180005303  not     eax
0x180005305  and     ebx, eax
0x180005307  jmp     loc_1800053C3
0x18000530c  mov     rcx, rax; lpsz
0x18000530f  call    cs:__imp_CharNextW
0x180005315  mov     rdi, rax
0x180005318  jmp     short loc_18000531F
0x18000531a  lea     rdi, [rsp+280h+var_25A]
0x18000531f  mov     esi, r15d
0x180005322  mov     ebx, r15d
0x180005325  movzx   eax, word ptr [rdi]
0x180005328  test    ax, ax
0x18000532b  jz      loc_1800053C3
0x180005331  jmp     short loc_180005347
0x180005333  test    ax, ax
0x180005336  jz      short loc_18000534D
0x180005338  mov     rcx, rdi; lpsz
0x18000533b  call    cs:__imp_CharNextW
0x180005341  mov     rdi, rax
0x180005344  movzx   eax, word ptr [rax]
0x180005347  cmp     ax, r12w
0x18000534b  jnz     short loc_180005333
0x18000534d  cmp     [rdi], r15w
0x180005351  lea     rcx, [rsp+280h+szStart]; lpFileName
0x180005356  mov     [rdi], r15w
0x18000535a  cmovz   esi, r13d
0x18000535e  call    cs:__imp_GetFileAttributesW
0x180005364  cmp     eax, 0FFFFFFFFh
0x180005367  jnz     short loc_180005395
0x180005369  xor     edx, edx; lpSecurityAttributes
0x18000536b  lea     rcx, [rsp+280h+szStart]; lpPathName
0x180005370  call    cs:__imp_CreateDirectoryW
0x180005376  test    eax, eax
0x180005378  jz      short loc_1800053AE
0x18000537a  test    esi, esi
0x18000537c  jz      short loc_180005399
0x18000537e  test    r14d, r14d
0x180005381  jz      short loc_1800053C3
0x180005383  mov     edx, 2; dwFileAttributes
0x180005388  lea     rcx, [rsp+280h+szStart]; lpFileName
0x18000538d  call    cs:__imp_SetFileAttributesW
0x180005393  jmp     short loc_1800053C3
0x180005395  test    esi, esi
0x180005397  jnz     short loc_1800053C3
0x180005399  mov     rcx, rdi; lpsz
0x18000539c  mov     [rdi], r12w
0x1800053a0  call    cs:__imp_CharNextW
0x1800053a6  mov     rdi, rax
0x1800053a9  jmp     loc_180005325
0x1800053ae  call    cs:__imp_GetLastError
0x1800053b4  mov     ebx, eax
0x1800053b6  test    eax, eax
0x1800053b8  jle     short loc_1800053C3
0x1800053ba  movzx   ebx, ax
0x1800053bd  or      ebx, 80070000h
0x1800053c3  mov     eax, ebx
0x1800053c5  mov     rcx, [rbp+180h+var_50]
0x1800053cc  xor     rcx, rsp; StackCookie
0x1800053cf  call    __security_check_cookie
0x1800053d4  add     rsp, 248h
0x1800053db  pop     r15
0x1800053dd  pop     r14
0x1800053df  pop     r13
0x1800053e1  pop     r12
0x1800053e3  pop     rdi
0x1800053e4  pop     rsi
0x1800053e5  pop     rbx
0x1800053e6  pop     rbp
0x1800053e7  retn
```
