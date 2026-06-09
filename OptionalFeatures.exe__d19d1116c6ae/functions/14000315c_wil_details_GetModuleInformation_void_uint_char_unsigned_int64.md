# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x14000315c`
- end: `0x140003280`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `bool __fastcall(LPCWSTR lpModuleName, void *, unsigned int *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002da0`

## callees

- `0x14000315c`
- `0x140004ba0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x1400031a2`
- `KERNEL32!GetModuleHandleExW` at `0x1400031a2`
- `KERNEL32!GetModuleFileNameA` at `0x1400031dc`
- `KERNEL32!GetModuleFileNameA` at `0x1400031dc`

## pseudocode

```c
char __fastcall wil::details::GetModuleInformation(LPCWSTR lpModuleName, _DWORD *a2, unsigned int *a3, char *a4)
{
  HMODULE v6; // rcx
  __int64 v10; // rax
  CHAR *i; // rax
  __int64 v12; // rcx
  unsigned int *v13; // rcx
  HMODULE phModule; // [rsp+20h] [rbp-148h] BYREF
  CHAR Filename[272]; // [rsp+30h] [rbp-138h] BYREF

  v6 = 0;
  phModule = 0;
  if ( lpModuleName )
  {
    if ( !GetModuleHandleExW(6u, lpModuleName, &phModule) )
    {
      if ( a2 )
        *a2 = 0;
      return 0;
    }
    v6 = phModule;
  }
  if ( a2 )
  {
    if ( lpModuleName )
      LODWORD(lpModuleName) = (_DWORD)lpModuleName - (_DWORD)v6;
    *a2 = (_DWORD)lpModuleName;
  }
  if ( a3 )
  {
    if ( !GetModuleFileNameA(v6, Filename, 0x104u) )
      return 0;
    v10 = -1;
    do
      ++v10;
    while ( Filename[v10] );
    for ( i = &Filename[v10]; i > Filename && *(i - 1) != 92; --i )
      ;
    if ( a4 )
    {
      if ( (unsigned __int64)a4 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        do
        {
          if ( !v12 )
            break;
          if ( !*i )
            break;
          *(_BYTE *)a3 = *i++;
          a3 = (unsigned int *)((char *)a3 + 1);
          --v12;
          --a4;
        }
        while ( a4 );
        v13 = (unsigned int *)((char *)a3 - 1);
        if ( a4 )
          v13 = a3;
        *(_BYTE *)v13 = 0;
      }
      else
      {
        *(_BYTE *)a3 = 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000315c  mov     [rsp+arg_18], rbx
0x140003161  push    rbp
0x140003162  push    rsi
0x140003163  push    rdi
0x140003164  sub     rsp, 150h
0x14000316b  mov     rax, cs:__security_cookie
0x140003172  xor     rax, rsp
0x140003175  mov     [rsp+168h+var_28], rax
0x14000317d  mov     rbx, rcx
0x140003180  mov     rbp, r9
0x140003183  xor     ecx, ecx
0x140003185  mov     rdi, r8
0x140003188  mov     [rsp+168h+phModule], rcx
0x14000318d  mov     rsi, rdx
0x140003190  test    rbx, rbx
0x140003193  jz      short loc_1400031BA
0x140003195  lea     r8, [rsp+168h+phModule]; phModule
0x14000319a  mov     rdx, rbx; lpModuleName
0x14000319d  mov     ecx, 6; dwFlags
0x1400031a2  call    cs:__imp_GetModuleHandleExW
0x1400031a8  test    eax, eax
0x1400031aa  jnz     short loc_1400031B5
0x1400031ac  test    rsi, rsi
0x1400031af  jz      short loc_1400031E6
0x1400031b1  mov     [rsi], eax
0x1400031b3  jmp     short loc_1400031E6
0x1400031b5  mov     rcx, [rsp+168h+phModule]; hModule
0x1400031ba  test    rsi, rsi
0x1400031bd  jz      short loc_1400031C8
0x1400031bf  test    rbx, rbx
0x1400031c2  jz      short loc_1400031C6
0x1400031c4  sub     ebx, ecx
0x1400031c6  mov     [rsi], ebx
0x1400031c8  test    rdi, rdi
0x1400031cb  jz      loc_14000325B
0x1400031d1  mov     r8d, 104h; nSize
0x1400031d7  lea     rdx, [rsp+168h+Filename]; lpFilename
0x1400031dc  call    cs:__imp_GetModuleFileNameA
0x1400031e2  test    eax, eax
0x1400031e4  jnz     short loc_1400031EA
0x1400031e6  xor     al, al
0x1400031e8  jmp     short loc_14000325D
0x1400031ea  lea     rcx, [rsp+168h+Filename]
0x1400031ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400031f3  inc     rax
0x1400031f6  cmp     byte ptr [rcx+rax], 0
0x1400031fa  jnz     short loc_1400031F3
0x1400031fc  lea     rcx, [rsp+168h+Filename]
0x140003201  add     rax, rcx
0x140003204  jmp     short loc_14000320F
0x140003206  cmp     byte ptr [rax-1], 5Ch ; '\'
0x14000320a  jz      short loc_140003219
0x14000320c  dec     rax
0x14000320f  lea     rcx, [rsp+168h+Filename]
0x140003214  cmp     rax, rcx
0x140003217  ja      short loc_140003206
0x140003219  test    rbp, rbp
0x14000321c  jz      short loc_14000325B
0x14000321e  cmp     rbp, 7FFFFFFFh
0x140003225  jbe     short loc_14000322C
0x140003227  mov     byte ptr [rdi], 0
0x14000322a  jmp     short loc_14000325B
0x14000322c  mov     ecx, 7FFFFFFEh
0x140003231  test    rcx, rcx
0x140003234  jz      short loc_14000324D
0x140003236  mov     dl, [rax]
0x140003238  test    dl, dl
0x14000323a  jz      short loc_14000324D
0x14000323c  mov     [rdi], dl
0x14000323e  inc     rax
0x140003241  inc     rdi
0x140003244  dec     rcx
0x140003247  sub     rbp, 1
0x14000324b  jnz     short loc_140003231
0x14000324d  test    rbp, rbp
0x140003250  lea     rcx, [rdi-1]
0x140003254  cmovnz  rcx, rdi
0x140003258  mov     byte ptr [rcx], 0
0x14000325b  mov     al, 1
0x14000325d  mov     rcx, [rsp+168h+var_28]
0x140003265  xor     rcx, rsp; StackCookie
0x140003268  call    __security_check_cookie
0x14000326d  mov     rbx, [rsp+168h+arg_18]
0x140003275  add     rsp, 150h
0x14000327c  pop     rdi
0x14000327d  pop     rsi
0x14000327e  pop     rbp
0x14000327f  retn
```
