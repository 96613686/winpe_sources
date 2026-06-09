# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x180002780`
- end: `0x1800028a4`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `char __fastcall(LPCWSTR lpModuleName, _DWORD *, unsigned int *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002480`

## callees

- `0x180002780`
- `0x180004130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800027c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800027c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180002800`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180002800`

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
0x180002780  mov     [rsp+arg_18], rbx
0x180002785  push    rbp
0x180002786  push    rsi
0x180002787  push    rdi
0x180002788  sub     rsp, 150h
0x18000278f  mov     rax, cs:__security_cookie
0x180002796  xor     rax, rsp
0x180002799  mov     [rsp+168h+var_28], rax
0x1800027a1  mov     rbx, rcx
0x1800027a4  mov     rbp, r9
0x1800027a7  xor     ecx, ecx
0x1800027a9  mov     rdi, r8
0x1800027ac  mov     [rsp+168h+phModule], rcx
0x1800027b1  mov     rsi, rdx
0x1800027b4  test    rbx, rbx
0x1800027b7  jz      short loc_1800027DE
0x1800027b9  lea     r8, [rsp+168h+phModule]; phModule
0x1800027be  mov     rdx, rbx; lpModuleName
0x1800027c1  mov     ecx, 6; dwFlags
0x1800027c6  call    cs:__imp_GetModuleHandleExW
0x1800027cc  test    eax, eax
0x1800027ce  jnz     short loc_1800027D9
0x1800027d0  test    rsi, rsi
0x1800027d3  jz      short loc_18000280A
0x1800027d5  mov     [rsi], eax
0x1800027d7  jmp     short loc_18000280A
0x1800027d9  mov     rcx, [rsp+168h+phModule]; hModule
0x1800027de  test    rsi, rsi
0x1800027e1  jz      short loc_1800027EC
0x1800027e3  test    rbx, rbx
0x1800027e6  jz      short loc_1800027EA
0x1800027e8  sub     ebx, ecx
0x1800027ea  mov     [rsi], ebx
0x1800027ec  test    rdi, rdi
0x1800027ef  jz      loc_18000287F
0x1800027f5  mov     r8d, 104h; nSize
0x1800027fb  lea     rdx, [rsp+168h+Filename]; lpFilename
0x180002800  call    cs:__imp_GetModuleFileNameA
0x180002806  test    eax, eax
0x180002808  jnz     short loc_18000280E
0x18000280a  xor     al, al
0x18000280c  jmp     short loc_180002881
0x18000280e  lea     rcx, [rsp+168h+Filename]
0x180002813  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002817  inc     rax
0x18000281a  cmp     byte ptr [rcx+rax], 0
0x18000281e  jnz     short loc_180002817
0x180002820  lea     rcx, [rsp+168h+Filename]
0x180002825  add     rax, rcx
0x180002828  jmp     short loc_180002833
0x18000282a  cmp     byte ptr [rax-1], 5Ch ; '\'
0x18000282e  jz      short loc_18000283D
0x180002830  dec     rax
0x180002833  lea     rcx, [rsp+168h+Filename]
0x180002838  cmp     rax, rcx
0x18000283b  ja      short loc_18000282A
0x18000283d  test    rbp, rbp
0x180002840  jz      short loc_18000287F
0x180002842  cmp     rbp, 7FFFFFFFh
0x180002849  jbe     short loc_180002850
0x18000284b  mov     byte ptr [rdi], 0
0x18000284e  jmp     short loc_18000287F
0x180002850  mov     ecx, 7FFFFFFEh
0x180002855  test    rcx, rcx
0x180002858  jz      short loc_180002871
0x18000285a  mov     dl, [rax]
0x18000285c  test    dl, dl
0x18000285e  jz      short loc_180002871
0x180002860  mov     [rdi], dl
0x180002862  inc     rax
0x180002865  inc     rdi
0x180002868  dec     rcx
0x18000286b  sub     rbp, 1
0x18000286f  jnz     short loc_180002855
0x180002871  test    rbp, rbp
0x180002874  lea     rcx, [rdi-1]
0x180002878  cmovnz  rcx, rdi
0x18000287c  mov     byte ptr [rcx], 0
0x18000287f  mov     al, 1
0x180002881  mov     rcx, [rsp+168h+var_28]
0x180002889  xor     rcx, rsp; StackCookie
0x18000288c  call    __security_check_cookie
0x180002891  mov     rbx, [rsp+168h+arg_18]
0x180002899  add     rsp, 150h
0x1800028a0  pop     rdi
0x1800028a1  pop     rsi
0x1800028a2  pop     rbp
0x1800028a3  retn
```
