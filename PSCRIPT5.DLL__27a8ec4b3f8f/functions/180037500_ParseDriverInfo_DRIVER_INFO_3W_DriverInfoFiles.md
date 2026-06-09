# ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)

- ea: `0x180037500`
- end: `0x18003762b`
- name: `?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z`
- size: `299`
- prototype: `void __fastcall(struct _DRIVER_INFO_3W *, const wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800355d0`
- `0x180035ae0`

## callees

- `0x18000289c`
- `0x180002938`
- `0x180037500`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180037559`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800375c6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180037559`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800375c6`

## string_xrefs

- `0x18003756e`: `-manifest.ini`
- `0x1800375d7`: `-manifest.ini`

## pseudocode

```c
void __fastcall ParseDriverInfo(struct _DRIVER_INFO_3W *a1, LPWSTR *a2)
{
  const wchar_t *pDependentFiles; // rcx
  wchar_t *v5; // rax
  const wchar_t *v6; // rbx
  __int64 v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // rax

  memset_0(a2, 0, 0x50u);
  *a2 = a1->pConfigFile;
  a2[1] = a1->pDriverPath;
  a2[2] = a1->pDataFile;
  a2[4] = a1->pDependentFiles;
  if ( a1->cVersion >= 4 )
  {
    pDependentFiles = a1->pDependentFiles;
    if ( !pDependentFiles )
      return;
    v5 = wcsrchr(pDependentFiles, 0x2Du);
    if ( !v5 || wcsicmp(v5, L"-manifest.ini") )
      return;
    a2[3] = a1->pDependentFiles;
  }
  v6 = a2[4];
  if ( v6 )
  {
    do
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      v6 += v7 + 1;
      if ( a2[7] )
      {
        a2[9] = (LPWSTR)v6;
        if ( !*v6 )
          return;
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        if ( !v6[v9 + 1] )
          a2[6] = (LPWSTR)v6;
      }
      else
      {
        a2[5] = (LPWSTR)v6;
        if ( v6 )
        {
          v8 = wcsrchr(v6, 0x2Du);
          if ( v8 )
          {
            if ( !wcsicmp(v8, L"-manifest.ini") )
            {
              a2[7] = (LPWSTR)v6;
              a2[8] = (LPWSTR)v6;
            }
          }
        }
      }
    }
    while ( *v6 );
  }
}

```

## disassembly

```asm
0x180037500  mov     [rsp+arg_0], rbx
0x180037505  mov     [rsp+arg_8], rsi
0x18003750a  push    rdi
0x18003750b  sub     rsp, 20h
0x18003750f  mov     rdi, rdx
0x180037512  mov     rbx, rcx
0x180037515  xor     edx, edx; Val
0x180037517  mov     rcx, rdi; void *
0x18003751a  lea     r8d, [rdx+50h]; Size
0x18003751e  call    memset_0
0x180037523  mov     rax, [rbx+28h]
0x180037527  xor     esi, esi
0x180037529  mov     [rdi], rax
0x18003752c  mov     rax, [rbx+18h]
0x180037530  mov     [rdi+8], rax
0x180037534  mov     rax, [rbx+20h]
0x180037538  mov     [rdi+10h], rax
0x18003753c  mov     rax, [rbx+38h]
0x180037540  mov     [rdi+20h], rax
0x180037544  cmp     dword ptr [rbx], 4
0x180037547  jb      short loc_18003758D
0x180037549  mov     rcx, [rbx+38h]; Str
0x18003754d  test    rcx, rcx
0x180037550  jz      loc_18003761A
0x180037556  lea     edx, [rsi+2Dh]; Ch
0x180037559  call    cs:__imp_wcsrchr
0x180037560  nop     dword ptr [rax+rax+00h]
0x180037565  test    rax, rax
0x180037568  jz      loc_18003761A
0x18003756e  lea     rdx, aManifestIni; "-manifest.ini"
0x180037575  mov     rcx, rax; String1
0x180037578  call    _wcsicmp
0x18003757d  test    eax, eax
0x18003757f  jnz     loc_18003761A
0x180037585  mov     rax, [rbx+38h]
0x180037589  mov     [rdi+18h], rax
0x18003758d  mov     rbx, [rdi+20h]
0x180037591  test    rbx, rbx
0x180037594  jz      loc_18003761A
0x18003759a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003759e  inc     rax
0x1800375a1  cmp     [rbx+rax*2], si
0x1800375a5  jnz     short loc_18003759E
0x1800375a7  lea     rbx, [rbx+rax*2]
0x1800375ab  add     rbx, 2
0x1800375af  cmp     [rdi+38h], rsi
0x1800375b3  jnz     short loc_1800375F4
0x1800375b5  mov     [rdi+28h], rbx
0x1800375b9  test    rbx, rbx
0x1800375bc  jz      short loc_180037615
0x1800375be  mov     edx, 2Dh ; '-'; Ch
0x1800375c3  mov     rcx, rbx; Str
0x1800375c6  call    cs:__imp_wcsrchr
0x1800375cd  nop     dword ptr [rax+rax+00h]
0x1800375d2  test    rax, rax
0x1800375d5  jz      short loc_180037615
0x1800375d7  lea     rdx, aManifestIni; "-manifest.ini"
0x1800375de  mov     rcx, rax; String1
0x1800375e1  call    _wcsicmp
0x1800375e6  test    eax, eax
0x1800375e8  jnz     short loc_180037615
0x1800375ea  mov     [rdi+38h], rbx
0x1800375ee  mov     [rdi+40h], rbx
0x1800375f2  jmp     short loc_180037615
0x1800375f4  mov     [rdi+48h], rbx
0x1800375f8  cmp     [rbx], si
0x1800375fb  jz      short loc_18003761A
0x1800375fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037601  inc     rax
0x180037604  cmp     [rbx+rax*2], si
0x180037608  jnz     short loc_180037601
0x18003760a  cmp     [rbx+rax*2+2], si
0x18003760f  jnz     short loc_180037615
0x180037611  mov     [rdi+30h], rbx
0x180037615  cmp     [rbx], si
0x180037618  jnz     short loc_18003759A
0x18003761a  mov     rbx, [rsp+28h+arg_0]
0x18003761f  mov     rsi, [rsp+28h+arg_8]
0x180037624  add     rsp, 20h
0x180037628  pop     rdi
0x180037629  retn
```
