# __la_win_permissive_name_w

- ea: `0x1800ef3f8`
- end: `0x1800ef5c8`
- name: `__la_win_permissive_name_w`
- size: `464`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f5c`
- `0x1800bd620`
- `0x1800bfe84`
- `0x1800c10b0`
- `0x1800ef374`
- `0x1800ef5d0`
- `0x1800f5e24`
- `0x1800f6098`
- `0x1800f656c`
- `0x1800f65c4`
- `0x1800f661c`
- `0x1800f6ba4`
- `0x1800f7330`
- `0x1800f7890`
- `0x1800f7aa0`
- `0x1800f8380`

## callees

- `0x1800ef3f8`
- `0x180119986`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef54e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef5bd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef54e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef5bd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ef42b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ef53d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ef42b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ef53d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800ef412`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800ef448`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800ef412`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800ef448`

## pseudocode

```c
wchar_t *__fastcall _la_win_permissive_name_w(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // eax
  DWORD v3; // edi
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  DWORD v6; // edx
  WCHAR *v7; // r14
  int v8; // esi
  WCHAR v9; // cx
  WCHAR v11; // cx
  _WORD *v12; // rax
  _WORD *v13; // rax
  __int16 v14; // cx
  _WORD *v15; // r9
  unsigned int v16; // ebp
  wchar_t *v17; // rax
  wchar_t *v18; // rdi
  wchar_t *v19; // r15
  wchar_t *v20; // rdi
  unsigned int v21; // ebp

  FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
  if ( !FullPathNameW )
    return 0;
  v3 = FullPathNameW + 3;
  v4 = (WCHAR *)malloc(2LL * (FullPathNameW + 3));
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = GetFullPathNameW(lpFileName, v3, v4, 0);
  if ( *v5 != 92 || v5[1] != 92 )
    goto LABEL_16;
  if ( v5[2] != 63 )
  {
    if ( v5[2] == 46 && v5[3] == 92 )
    {
      v9 = v5[4];
      if ( ((unsigned __int16)(v9 - 97) <= 0x19u || (unsigned __int16)(v9 - 65) <= 0x19u) && v5[5] == 58 && v5[6] == 92 )
        v5[2] = 63;
      return v5;
    }
LABEL_16:
    v7 = v5;
    v8 = 0;
    if ( *v5 != 92 )
      goto LABEL_30;
    goto LABEL_17;
  }
  if ( v5[3] == 92 )
    return v5;
  v7 = v5;
  v8 = 0;
LABEL_17:
  if ( v5[1] == 92 )
  {
    v11 = v5[2];
    if ( v11 != 92 )
    {
      v12 = v5 + 2;
      do
      {
        if ( !v11 )
          break;
        v11 = *++v12;
      }
      while ( *v12 != 92 );
      if ( *v12 == 92 )
      {
        v13 = v12 + 1;
        v14 = *v13;
        if ( *v13 != 92 )
        {
          v15 = v13;
          do
          {
            if ( !v14 )
              break;
            v14 = *++v13;
          }
          while ( *v13 != 92 );
          if ( *v13 == 92 && v13 != v15 )
          {
            v5 += 2;
            v6 -= 2;
            v8 = 1;
          }
        }
      }
    }
  }
LABEL_30:
  v16 = v6 + 5 + 4 * v8;
  v17 = (wchar_t *)malloc(2LL * v16);
  v18 = v17;
  if ( !v17 )
  {
    free(v7);
    return 0;
  }
  v19 = v17;
  wcsncpy_0(v17, L"\\\\?\\", 4u);
  v20 = v18 + 4;
  v21 = v16 - 4;
  if ( v8 )
  {
    wcsncpy_0(v20, L"UNC\\", 4u);
    v20 += 4;
    v21 -= 4;
  }
  wcsncpy_0(v20, v5, v21);
  v20[v21 - 1] = 0;
  free(v7);
  return v19;
}

```

## disassembly

```asm
0x1800ef3f8  push    rbx
0x1800ef3fa  push    rbp
0x1800ef3fb  push    rsi
0x1800ef3fc  push    rdi
0x1800ef3fd  push    r12
0x1800ef3ff  push    r14
0x1800ef401  push    r15
0x1800ef403  sub     rsp, 20h
0x1800ef407  xor     r9d, r9d; lpFilePart
0x1800ef40a  xor     r8d, r8d; lpBuffer
0x1800ef40d  xor     edx, edx; nBufferLength
0x1800ef40f  mov     rsi, rcx
0x1800ef412  call    cs:__imp_GetFullPathNameW
0x1800ef418  xor     r12d, r12d
0x1800ef41b  test    eax, eax
0x1800ef41d  jz      loc_1800EF554
0x1800ef423  lea     edi, [rax+3]
0x1800ef426  mov     ecx, edi
0x1800ef428  add     rcx, rcx; Size
0x1800ef42b  call    cs:__imp_malloc
0x1800ef431  mov     rbx, rax
0x1800ef434  test    rax, rax
0x1800ef437  jz      loc_1800EF554
0x1800ef43d  xor     r9d, r9d; lpFilePart
0x1800ef440  mov     r8, rax; lpBuffer
0x1800ef443  mov     edx, edi; nBufferLength
0x1800ef445  mov     rcx, rsi; lpFileName
0x1800ef448  call    cs:__imp_GetFullPathNameW
0x1800ef44e  mov     r10w, 5Ch ; '\'
0x1800ef453  mov     edx, eax
0x1800ef455  cmp     [rbx], r10w
0x1800ef459  jnz     short loc_1800EF4BD
0x1800ef45b  cmp     [rbx+2], r10w
0x1800ef460  jnz     short loc_1800EF4BD
0x1800ef462  lea     r8d, [r12+3Fh]
0x1800ef467  cmp     [rbx+4], r8w
0x1800ef46c  jnz     short loc_1800EF47D
0x1800ef46e  cmp     [rbx+6], r10w
0x1800ef473  jz      short loc_1800EF4B5
0x1800ef475  mov     r14, rbx
0x1800ef478  mov     esi, r12d
0x1800ef47b  jmp     short loc_1800EF4C9
0x1800ef47d  cmp     word ptr [rbx+4], 2Eh ; '.'
0x1800ef482  jnz     short loc_1800EF4BD
0x1800ef484  cmp     [rbx+6], r10w
0x1800ef489  jnz     short loc_1800EF4BD
0x1800ef48b  movzx   ecx, word ptr [rbx+8]
0x1800ef48f  lea     eax, [rcx-61h]
0x1800ef492  cmp     ax, 19h
0x1800ef496  jbe     short loc_1800EF4A2
0x1800ef498  sub     cx, 41h ; 'A'
0x1800ef49c  cmp     cx, 19h
0x1800ef4a0  ja      short loc_1800EF4B5
0x1800ef4a2  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x1800ef4a7  jnz     short loc_1800EF4B5
0x1800ef4a9  cmp     [rbx+0Ch], r10w
0x1800ef4ae  jnz     short loc_1800EF4B5
0x1800ef4b0  mov     [rbx+4], r8w
0x1800ef4b5  mov     rax, rbx
0x1800ef4b8  jmp     loc_1800EF556
0x1800ef4bd  mov     r14, rbx
0x1800ef4c0  mov     esi, r12d
0x1800ef4c3  cmp     [rbx], r10w
0x1800ef4c7  jnz     short loc_1800EF531
0x1800ef4c9  cmp     [rbx+2], r10w
0x1800ef4ce  jnz     short loc_1800EF531
0x1800ef4d0  lea     r8, [rbx+4]
0x1800ef4d4  movzx   ecx, word ptr [r8]
0x1800ef4d8  cmp     cx, r10w
0x1800ef4dc  jz      short loc_1800EF531
0x1800ef4de  mov     rax, r8
0x1800ef4e1  test    cx, cx
0x1800ef4e4  jz      short loc_1800EF4F3
0x1800ef4e6  add     rax, 2
0x1800ef4ea  movzx   ecx, word ptr [rax]
0x1800ef4ed  cmp     cx, r10w
0x1800ef4f1  jnz     short loc_1800EF4E1
0x1800ef4f3  cmp     [rax], r10w
0x1800ef4f7  jnz     short loc_1800EF531
0x1800ef4f9  add     rax, 2
0x1800ef4fd  movzx   ecx, word ptr [rax]
0x1800ef500  cmp     cx, r10w
0x1800ef504  jz      short loc_1800EF531
0x1800ef506  mov     r9, rax
0x1800ef509  test    cx, cx
0x1800ef50c  jz      short loc_1800EF51B
0x1800ef50e  add     rax, 2
0x1800ef512  movzx   ecx, word ptr [rax]
0x1800ef515  cmp     cx, r10w
0x1800ef519  jnz     short loc_1800EF509
0x1800ef51b  cmp     [rax], r10w
0x1800ef51f  jnz     short loc_1800EF531
0x1800ef521  cmp     rax, r9
0x1800ef524  jz      short loc_1800EF531
0x1800ef526  mov     rbx, r8
0x1800ef529  add     edx, 0FFFFFFFEh
0x1800ef52c  mov     esi, 1
0x1800ef531  lea     ebp, [rdx+5]
0x1800ef534  lea     ebp, [rbp+rsi*4+0]
0x1800ef538  mov     ecx, ebp
0x1800ef53a  add     rcx, rcx; Size
0x1800ef53d  call    cs:__imp_malloc
0x1800ef543  mov     rdi, rax
0x1800ef546  test    rax, rax
0x1800ef549  jnz     short loc_1800EF565
0x1800ef54b  mov     rcx, r14; Block
0x1800ef54e  call    cs:__imp_free
0x1800ef554  xor     eax, eax
0x1800ef556  add     rsp, 20h
0x1800ef55a  pop     r15
0x1800ef55c  pop     r14
0x1800ef55e  pop     r12
0x1800ef560  pop     rdi
0x1800ef561  pop     rsi
0x1800ef562  pop     rbp
0x1800ef563  pop     rbx
0x1800ef564  retn
0x1800ef565  mov     r8d, 4; Count
0x1800ef56b  lea     rdx, Source; "\\\\?\\"
0x1800ef572  mov     rcx, rdi; Destination
0x1800ef575  mov     r15, rdi
0x1800ef578  call    wcsncpy_0
0x1800ef57d  add     rdi, 8
0x1800ef581  add     ebp, 0FFFFFFFCh
0x1800ef584  test    esi, esi
0x1800ef586  jz      short loc_1800EF5A4
0x1800ef588  mov     r8d, 4; Count
0x1800ef58e  lea     rdx, aUnc; "UNC\\"
0x1800ef595  mov     rcx, rdi; Destination
0x1800ef598  call    wcsncpy_0
0x1800ef59d  add     rdi, 8
0x1800ef5a1  add     ebp, 0FFFFFFFCh
0x1800ef5a4  mov     r8d, ebp; Count
0x1800ef5a7  mov     rdx, rbx; Source
0x1800ef5aa  mov     rcx, rdi; Destination
0x1800ef5ad  call    wcsncpy_0
0x1800ef5b2  lea     ecx, [rbp-1]
0x1800ef5b5  mov     [rdi+rcx*2], r12w
0x1800ef5ba  mov     rcx, r14; Block
0x1800ef5bd  call    cs:__imp_free
0x1800ef5c3  mov     rax, r15
0x1800ef5c6  jmp     short loc_1800EF556
```
