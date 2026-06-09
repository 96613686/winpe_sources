# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x180005020`
- end: `0x180005144`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `bool __fastcall(LPCWSTR lpModuleName, void *, unsigned int *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d20`

## callees

- `0x180005020`
- `0x180006980`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005066`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180005066`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800050a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800050a0`

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
0x180005020  mov     [rsp+arg_18], rbx
0x180005025  push    rbp
0x180005026  push    rsi
0x180005027  push    rdi
0x180005028  sub     rsp, 150h
0x18000502f  mov     rax, cs:__security_cookie
0x180005036  xor     rax, rsp
0x180005039  mov     [rsp+168h+var_28], rax
0x180005041  mov     rbx, rcx
0x180005044  mov     rbp, r9
0x180005047  xor     ecx, ecx
0x180005049  mov     rdi, r8
0x18000504c  mov     [rsp+168h+phModule], rcx
0x180005051  mov     rsi, rdx
0x180005054  test    rbx, rbx
0x180005057  jz      short loc_18000507E
0x180005059  lea     r8, [rsp+168h+phModule]; phModule
0x18000505e  mov     rdx, rbx; lpModuleName
0x180005061  mov     ecx, 6; dwFlags
0x180005066  call    cs:__imp_GetModuleHandleExW
0x18000506c  test    eax, eax
0x18000506e  jnz     short loc_180005079
0x180005070  test    rsi, rsi
0x180005073  jz      short loc_1800050AA
0x180005075  mov     [rsi], eax
0x180005077  jmp     short loc_1800050AA
0x180005079  mov     rcx, [rsp+168h+phModule]; hModule
0x18000507e  test    rsi, rsi
0x180005081  jz      short loc_18000508C
0x180005083  test    rbx, rbx
0x180005086  jz      short loc_18000508A
0x180005088  sub     ebx, ecx
0x18000508a  mov     [rsi], ebx
0x18000508c  test    rdi, rdi
0x18000508f  jz      loc_18000511F
0x180005095  mov     r8d, 104h; nSize
0x18000509b  lea     rdx, [rsp+168h+Filename]; lpFilename
0x1800050a0  call    cs:__imp_GetModuleFileNameA
0x1800050a6  test    eax, eax
0x1800050a8  jnz     short loc_1800050AE
0x1800050aa  xor     al, al
0x1800050ac  jmp     short loc_180005121
0x1800050ae  lea     rcx, [rsp+168h+Filename]
0x1800050b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800050b7  inc     rax
0x1800050ba  cmp     byte ptr [rcx+rax], 0
0x1800050be  jnz     short loc_1800050B7
0x1800050c0  lea     rcx, [rsp+168h+Filename]
0x1800050c5  add     rax, rcx
0x1800050c8  jmp     short loc_1800050D3
0x1800050ca  cmp     byte ptr [rax-1], 5Ch ; '\'
0x1800050ce  jz      short loc_1800050DD
0x1800050d0  dec     rax
0x1800050d3  lea     rcx, [rsp+168h+Filename]
0x1800050d8  cmp     rax, rcx
0x1800050db  ja      short loc_1800050CA
0x1800050dd  test    rbp, rbp
0x1800050e0  jz      short loc_18000511F
0x1800050e2  cmp     rbp, 7FFFFFFFh
0x1800050e9  jbe     short loc_1800050F0
0x1800050eb  mov     byte ptr [rdi], 0
0x1800050ee  jmp     short loc_18000511F
0x1800050f0  mov     ecx, 7FFFFFFEh
0x1800050f5  test    rcx, rcx
0x1800050f8  jz      short loc_180005111
0x1800050fa  mov     dl, [rax]
0x1800050fc  test    dl, dl
0x1800050fe  jz      short loc_180005111
0x180005100  mov     [rdi], dl
0x180005102  inc     rax
0x180005105  inc     rdi
0x180005108  dec     rcx
0x18000510b  sub     rbp, 1
0x18000510f  jnz     short loc_1800050F5
0x180005111  test    rbp, rbp
0x180005114  lea     rcx, [rdi-1]
0x180005118  cmovnz  rcx, rdi
0x18000511c  mov     byte ptr [rcx], 0
0x18000511f  mov     al, 1
0x180005121  mov     rcx, [rsp+168h+var_28]
0x180005129  xor     rcx, rsp; StackCookie
0x18000512c  call    __security_check_cookie
0x180005131  mov     rbx, [rsp+168h+arg_18]
0x180005139  add     rsp, 150h
0x180005140  pop     rdi
0x180005141  pop     rsi
0x180005142  pop     rbp
0x180005143  retn
```
