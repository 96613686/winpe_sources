# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x1400056ec`
- end: `0x140005810`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `char __fastcall(LPCWSTR lpModuleName, _DWORD *, unsigned int *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005330`

## callees

- `0x1400056ec`
- `0x140006b90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000576c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000576c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140005732`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140005732`

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
0x1400056ec  mov     [rsp+arg_18], rbx
0x1400056f1  push    rbp
0x1400056f2  push    rsi
0x1400056f3  push    rdi
0x1400056f4  sub     rsp, 150h
0x1400056fb  mov     rax, cs:__security_cookie
0x140005702  xor     rax, rsp
0x140005705  mov     [rsp+168h+var_28], rax
0x14000570d  mov     rbx, rcx
0x140005710  mov     rbp, r9
0x140005713  xor     ecx, ecx
0x140005715  mov     rdi, r8
0x140005718  mov     [rsp+168h+phModule], rcx
0x14000571d  mov     rsi, rdx
0x140005720  test    rbx, rbx
0x140005723  jz      short loc_14000574A
0x140005725  lea     r8, [rsp+168h+phModule]; phModule
0x14000572a  mov     rdx, rbx; lpModuleName
0x14000572d  mov     ecx, 6; dwFlags
0x140005732  call    cs:__imp_GetModuleHandleExW
0x140005738  test    eax, eax
0x14000573a  jnz     short loc_140005745
0x14000573c  test    rsi, rsi
0x14000573f  jz      short loc_140005776
0x140005741  mov     [rsi], eax
0x140005743  jmp     short loc_140005776
0x140005745  mov     rcx, [rsp+168h+phModule]; hModule
0x14000574a  test    rsi, rsi
0x14000574d  jz      short loc_140005758
0x14000574f  test    rbx, rbx
0x140005752  jz      short loc_140005756
0x140005754  sub     ebx, ecx
0x140005756  mov     [rsi], ebx
0x140005758  test    rdi, rdi
0x14000575b  jz      loc_1400057EB
0x140005761  mov     r8d, 104h; nSize
0x140005767  lea     rdx, [rsp+168h+Filename]; lpFilename
0x14000576c  call    cs:__imp_GetModuleFileNameA
0x140005772  test    eax, eax
0x140005774  jnz     short loc_14000577A
0x140005776  xor     al, al
0x140005778  jmp     short loc_1400057ED
0x14000577a  lea     rcx, [rsp+168h+Filename]
0x14000577f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005783  inc     rax
0x140005786  cmp     byte ptr [rcx+rax], 0
0x14000578a  jnz     short loc_140005783
0x14000578c  lea     rcx, [rsp+168h+Filename]
0x140005791  add     rax, rcx
0x140005794  jmp     short loc_14000579F
0x140005796  cmp     byte ptr [rax-1], 5Ch ; '\'
0x14000579a  jz      short loc_1400057A9
0x14000579c  dec     rax
0x14000579f  lea     rcx, [rsp+168h+Filename]
0x1400057a4  cmp     rax, rcx
0x1400057a7  ja      short loc_140005796
0x1400057a9  test    rbp, rbp
0x1400057ac  jz      short loc_1400057EB
0x1400057ae  cmp     rbp, 7FFFFFFFh
0x1400057b5  jbe     short loc_1400057BC
0x1400057b7  mov     byte ptr [rdi], 0
0x1400057ba  jmp     short loc_1400057EB
0x1400057bc  mov     ecx, 7FFFFFFEh
0x1400057c1  test    rcx, rcx
0x1400057c4  jz      short loc_1400057DD
0x1400057c6  mov     dl, [rax]
0x1400057c8  test    dl, dl
0x1400057ca  jz      short loc_1400057DD
0x1400057cc  mov     [rdi], dl
0x1400057ce  inc     rax
0x1400057d1  inc     rdi
0x1400057d4  dec     rcx
0x1400057d7  sub     rbp, 1
0x1400057db  jnz     short loc_1400057C1
0x1400057dd  test    rbp, rbp
0x1400057e0  lea     rcx, [rdi-1]
0x1400057e4  cmovnz  rcx, rdi
0x1400057e8  mov     byte ptr [rcx], 0
0x1400057eb  mov     al, 1
0x1400057ed  mov     rcx, [rsp+168h+var_28]
0x1400057f5  xor     rcx, rsp; StackCookie
0x1400057f8  call    __security_check_cookie
0x1400057fd  mov     rbx, [rsp+168h+arg_18]
0x140005805  add     rsp, 150h
0x14000580c  pop     rdi
0x14000580d  pop     rsi
0x14000580e  pop     rbp
0x14000580f  retn
```
