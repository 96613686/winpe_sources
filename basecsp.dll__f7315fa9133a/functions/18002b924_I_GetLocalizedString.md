# I_GetLocalizedString

- ea: `0x18002b924`
- end: `0x18002b9ca`
- name: `I_GetLocalizedString`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b9d0`

## callees

- `0x18002b924`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002b958`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002b958`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002b9a4`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18002b9a4`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002b939`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002b939`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002b94c`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002b94c`

## pseudocode

```c
LCID __fastcall I_GetLocalizedString(__int64 a1, unsigned int a2, _QWORD *a3)
{
  LCID result; // eax
  LCID v7; // esi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // r14

  result = GetThreadLocale();
  v7 = result;
  if ( a1 )
  {
    v8 = 0;
    if ( !result )
    {
      result = GetUserDefaultLCID();
      v7 = result;
      if ( !result )
      {
        result = GetSystemDefaultLCID();
        v7 = result;
      }
    }
    while ( (unsigned int)v8 < a2 )
    {
      v9 = (unsigned int)v8;
      while ( *(_WORD *)(a1 + 2 * v8) != 44 )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= a2 )
        {
          if ( (_DWORD)v8 == a2 )
            return result;
          break;
        }
      }
      *(_WORD *)(a1 + 2 * v8) = 0;
      v10 = (unsigned int)(v8 + 1);
      v11 = (unsigned int)v10;
      while ( (unsigned int)v10 < a2 && *(_WORD *)(a1 + 2 * v10) != 59 )
        v10 = (unsigned int)(v10 + 1);
      *(_WORD *)(a1 + 2 * v10) = 0;
      result = LocaleNameToLCID((LPCWSTR)(a1 + 2 * v9), 0);
      if ( result && result == v7 )
      {
        *a3 = a1 + 2 * v11;
        return result;
      }
      v8 = (unsigned int)(v10 + 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b924  push    rbx
0x18002b926  push    rbp
0x18002b927  push    rsi
0x18002b928  push    rdi
0x18002b929  push    r14
0x18002b92b  push    r15
0x18002b92d  sub     rsp, 28h
0x18002b931  mov     r15, r8
0x18002b934  mov     ebp, edx
0x18002b936  mov     rdi, rcx
0x18002b939  call    cs:__imp_GetThreadLocale
0x18002b93f  mov     esi, eax
0x18002b941  test    rdi, rdi
0x18002b944  jz      short loc_18002B9BD
0x18002b946  xor     ebx, ebx
0x18002b948  test    eax, eax
0x18002b94a  jnz     short loc_18002B960
0x18002b94c  call    cs:__imp_GetUserDefaultLCID
0x18002b952  mov     esi, eax
0x18002b954  test    eax, eax
0x18002b956  jnz     short loc_18002B960
0x18002b958  call    cs:__imp_GetSystemDefaultLCID
0x18002b95e  mov     esi, eax
0x18002b960  cmp     ebx, ebp
0x18002b962  jnb     short loc_18002B9BD
0x18002b964  mov     ecx, ebx
0x18002b966  mov     edx, 2Ch ; ','
0x18002b96b  cmp     dx, [rdi+rbx*2]
0x18002b96f  jz      short loc_18002B979
0x18002b971  inc     ebx
0x18002b973  cmp     ebx, ebp
0x18002b975  jb      short loc_18002B966
0x18002b977  jz      short loc_18002B9BD
0x18002b979  xor     eax, eax
0x18002b97b  lea     r8, [rdi+rcx*2]
0x18002b97f  mov     [rdi+rbx*2], ax
0x18002b983  inc     ebx
0x18002b985  mov     r14d, ebx
0x18002b988  jmp     short loc_18002B997
0x18002b98a  mov     ecx, 3Bh ; ';'
0x18002b98f  cmp     cx, [rdi+rbx*2]
0x18002b993  jz      short loc_18002B99B
0x18002b995  inc     ebx
0x18002b997  cmp     ebx, ebp
0x18002b999  jb      short loc_18002B98A
0x18002b99b  xor     edx, edx; dwFlags
0x18002b99d  mov     [rdi+rbx*2], ax
0x18002b9a1  mov     rcx, r8; lpName
0x18002b9a4  call    cs:__imp_LocaleNameToLCID
0x18002b9aa  test    eax, eax
0x18002b9ac  jz      short loc_18002B9B6
0x18002b9ae  lea     rcx, [rdi+r14*2]
0x18002b9b2  cmp     eax, esi
0x18002b9b4  jz      short loc_18002B9BA
0x18002b9b6  inc     ebx
0x18002b9b8  jmp     short loc_18002B960
0x18002b9ba  mov     [r15], rcx
0x18002b9bd  add     rsp, 28h
0x18002b9c1  pop     r15
0x18002b9c3  pop     r14
0x18002b9c5  pop     rdi
0x18002b9c6  pop     rsi
0x18002b9c7  pop     rbp
0x18002b9c8  pop     rbx
0x18002b9c9  retn
```
