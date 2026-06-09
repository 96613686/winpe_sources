# GetPersistentRegPath

- ea: `0x1800073c0`
- end: `0x18000755d`
- name: `GetPersistentRegPath`
- size: `413`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, unsigned int *, wchar_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006c80`
- `0x180006d90`
- `0x1800087c0`
- `0x18000b1c0`
- `0x18000b2e0`
- `0x18000b470`

## callees

- `0x1800073c0`
- `0x180007570`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180007416`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180007416`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPath(unsigned int a1, const wchar_t *a2, unsigned int *a3, wchar_t *a4)
{
  size_t v7; // rdi
  unsigned int PersistedRegistryLocationW; // ebp
  unsigned int v9; // eax
  __int64 v10; // rdx
  size_t v11; // rcx
  wchar_t *v12; // rax
  size_t v13; // r9
  int v14; // eax
  const wchar_t *v15; // rcx
  bool v16; // zf
  size_t v17; // r8
  wchar_t *v18; // r9
  wchar_t *v19; // rcx
  __int64 v21; // rcx
  const wchar_t *i; // rax
  unsigned int v23; // [rsp+50h] [rbp+8h] BYREF

  v23 = 0;
  if ( a1 > 0x28 )
    return 87;
  v7 = *a3;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 RegistryPaths[2 * (int)a1 + 1],
                                 RegistryPaths[2 * (int)a1],
                                 a4,
                                 (unsigned int)(2 * v7),
                                 &v23);
  if ( a2 && *a2 )
  {
    v21 = 0x7FFFFFFF;
    for ( i = a2; *i; ++i )
    {
      if ( !--v21 )
        return 87;
    }
    v9 = (v23 >> 1) - v21 + 0x80000000;
  }
  else
  {
    v9 = v23 >> 1;
  }
  *a3 = v9;
  if ( PersistedRegistryLocationW )
    return PersistedRegistryLocationW;
  if ( (unsigned int)v7 < v9 )
    return 234;
  if ( !a2 || !*a2 )
    return PersistedRegistryLocationW;
  v10 = 2147483646;
  if ( v7 - 1 <= 0x7FFFFFFE )
  {
    v11 = v7;
    v12 = a4;
    while ( *v12 )
    {
      ++v12;
      if ( !--v11 )
      {
        v13 = 0;
        v14 = -2147024809;
        goto LABEL_14;
      }
    }
    v13 = v7 - v11;
    v14 = 0;
LABEL_14:
    if ( v14 >= 0 )
    {
      v15 = L"\\";
      v17 = v7 - v13;
      v16 = v7 == v13;
      v18 = &a4[v13];
      if ( !v16 )
      {
        do
        {
          if ( !v10 )
            break;
          if ( !*v15 )
            break;
          *v18++ = *v15++;
          --v10;
          --v17;
        }
        while ( v17 );
      }
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
      if ( v17 )
      {
        if ( StringCchCatW(a4, v7, a2) < 0 )
          return 31;
        return PersistedRegistryLocationW;
      }
    }
  }
  return 31;
}

```

## disassembly

```asm
0x1800073c0  mov     [rsp+arg_8], rbx
0x1800073c5  mov     [rsp+arg_10], rbp
0x1800073ca  push    rsi
0x1800073cb  push    rdi
0x1800073cc  push    r14
0x1800073ce  sub     rsp, 30h
0x1800073d2  mov     [rsp+48h+arg_0], 0
0x1800073da  mov     r14, r9
0x1800073dd  mov     rbx, r8
0x1800073e0  mov     rsi, rdx
0x1800073e3  cmp     ecx, 28h ; '('
0x1800073e6  ja      loc_180007536
0x1800073ec  mov     edi, [r8]
0x1800073ef  lea     r10, RegistryPaths
0x1800073f6  movsxd  rcx, ecx
0x1800073f9  lea     rax, [rsp+48h+arg_0]
0x1800073fe  add     rcx, rcx
0x180007401  mov     [rsp+48h+var_28], rax
0x180007406  mov     r8, r14
0x180007409  lea     r9d, [rdi+rdi]
0x18000740d  mov     rdx, [r10+rcx*8]
0x180007411  mov     rcx, [r10+rcx*8+8]
0x180007416  call    cs:__imp_GetPersistedRegistryLocationW
0x18000741c  mov     ebp, eax
0x18000741e  test    rsi, rsi
0x180007421  jnz     loc_180007514
0x180007427  mov     eax, [rsp+48h+arg_0]
0x18000742b  shr     eax, 1
0x18000742d  mov     [rbx], eax
0x18000742f  test    ebp, ebp
0x180007431  jnz     loc_1800074FF
0x180007437  cmp     edi, eax
0x180007439  jb      loc_18000754F
0x18000743f  test    rsi, rsi
0x180007442  jz      loc_1800074FF
0x180007448  cmp     [rsi], bp
0x18000744b  jz      loc_1800074FF
0x180007451  lea     rax, [rdi-1]
0x180007455  mov     edx, 7FFFFFFEh
0x18000745a  cmp     rax, rdx
0x18000745d  ja      loc_180007556
0x180007463  mov     rcx, rdi
0x180007466  mov     rax, r14
0x180007469  mov     r9, rdi
0x18000746c  nop     dword ptr [rax+00h]
0x180007470  cmp     word ptr [rax], 0
0x180007474  jz      short loc_18000748A
0x180007476  add     rax, 2
0x18000747a  sub     rcx, 1
0x18000747e  jnz     short loc_180007470
0x180007480  xor     r9d, r9d
0x180007483  mov     eax, 80070057h
0x180007488  jmp     short loc_18000748F
0x18000748a  sub     r9, rcx
0x18000748d  xor     eax, eax
0x18000748f  test    eax, eax
0x180007491  js      loc_180007556
0x180007497  mov     r8, rdi
0x18000749a  lea     rcx, asc_180013DE4; "\\"
0x1800074a1  sub     r8, r9
0x1800074a4  lea     r9, [r14+r9*2]
0x1800074a8  jz      short loc_1800074D2
0x1800074aa  nop     word ptr [rax+rax+00h]
0x1800074b0  test    rdx, rdx
0x1800074b3  jz      short loc_1800074D2
0x1800074b5  movzx   eax, word ptr [rcx]
0x1800074b8  test    ax, ax
0x1800074bb  jz      short loc_1800074D2
0x1800074bd  mov     [r9], ax
0x1800074c1  add     rcx, 2
0x1800074c5  add     r9, 2
0x1800074c9  dec     rdx
0x1800074cc  sub     r8, 1
0x1800074d0  jnz     short loc_1800074B0
0x1800074d2  test    r8, r8
0x1800074d5  lea     rcx, [r9-2]
0x1800074d9  cmovnz  rcx, r9
0x1800074dd  xor     eax, eax
0x1800074df  mov     [rcx], ax
0x1800074e2  test    r8, r8
0x1800074e5  jz      short loc_180007556
0x1800074e7  mov     r8, rsi; pszSrc
0x1800074ea  mov     rdx, rdi; cchDest
0x1800074ed  mov     rcx, r14; pszDest
0x1800074f0  call    StringCchCatW
0x1800074f5  test    eax, eax
0x1800074f7  mov     ecx, 1Fh
0x1800074fc  cmovs   ebp, ecx
0x1800074ff  mov     eax, ebp
0x180007501  mov     rbx, [rsp+48h+arg_8]
0x180007506  mov     rbp, [rsp+48h+arg_10]
0x18000750b  add     rsp, 30h
0x18000750f  pop     r14
0x180007511  pop     rdi
0x180007512  pop     rsi
0x180007513  retn
0x180007514  cmp     word ptr [rsi], 0
0x180007518  jz      loc_180007427
0x18000751e  mov     ecx, 7FFFFFFFh
0x180007523  mov     rax, rsi
0x180007526  cmp     word ptr [rax], 0
0x18000752a  jz      short loc_18000753D
0x18000752c  add     rax, 2
0x180007530  sub     rcx, 1
0x180007534  jnz     short loc_180007526
0x180007536  mov     eax, 57h ; 'W'
0x18000753b  jmp     short loc_180007501
0x18000753d  mov     eax, [rsp+48h+arg_0]
0x180007541  shr     eax, 1
0x180007543  sub     eax, ecx
0x180007545  add     eax, 80000000h
0x18000754a  jmp     loc_18000742D
0x18000754f  mov     eax, 0EAh
0x180007554  jmp     short loc_180007501
0x180007556  mov     eax, 1Fh
0x18000755b  jmp     short loc_180007501
```
