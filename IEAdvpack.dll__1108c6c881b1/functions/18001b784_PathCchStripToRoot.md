# PathCchStripToRoot

- ea: `0x18001b784`
- end: `0x18001b897`
- name: `PathCchStripToRoot`
- size: `275`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18001b294`

## callees

- `0x1800022bc`
- `0x18001b524`
- `0x18001b634`
- `0x18001b784`

## pseudocode

```c
HRESULT __stdcall PathCchStripToRoot(PWSTR pszPath, size_t cchPath)
{
  int v4; // ebx
  size_t v6; // rdi
  WCHAR *v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  if ( pszPath && cchPath - 1 <= 0x7FFF )
  {
    v4 = PathCchSkipRoot(pszPath, (PCWSTR *)&v7);
    if ( v4 >= 0 )
    {
      if ( v7 < &pszPath[cchPath] )
      {
        v6 = -1;
        if ( *v7 )
        {
          *v7 = 0;
          do
            ++v6;
          while ( pszPath[v6] );
          if ( v6 < cchPath && v6 && pszPath[v6 - 1] == 92 && !PathCchIsRoot(pszPath) )
            pszPath[v6 - 1] = 0;
          return 0;
        }
        do
          ++v6;
        while ( pszPath[v6] );
        if ( v6 < cchPath )
        {
          v4 = 1;
          if ( v6 && pszPath[v6 - 1] == 92 && !PathCchIsRoot(pszPath) )
          {
            pszPath[v6 - 1] = 0;
            v4 = 0;
          }
        }
        else
        {
          v4 = -2147024809;
        }
        if ( v4 >= 0 )
          return v4;
      }
      else
      {
        v4 = -2147024809;
      }
    }
    StringCchCopyW(pszPath, cchPath, (size_t *)&word_18001DE6C);
    return v4;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18001b784  mov     r11, rsp
0x18001b787  mov     [r11+10h], rbx
0x18001b78b  mov     [r11+18h], rbp
0x18001b78f  push    rsi
0x18001b790  push    rdi
0x18001b791  push    r14
0x18001b793  sub     rsp, 20h
0x18001b797  xor     r14d, r14d
0x18001b79a  mov     rbp, rdx
0x18001b79d  mov     [r11+8], r14
0x18001b7a1  mov     rsi, rcx
0x18001b7a4  test    rcx, rcx
0x18001b7a7  jz      loc_18001B87F
0x18001b7ad  lea     rax, [rdx-1]
0x18001b7b1  cmp     rax, 7FFFh
0x18001b7b7  ja      loc_18001B87F
0x18001b7bd  lea     rdx, [r11+8]; ppszRootEnd
0x18001b7c1  call    PathCchSkipRoot
0x18001b7c6  mov     ebx, eax
0x18001b7c8  test    eax, eax
0x18001b7ca  js      short loc_18001B7DF
0x18001b7cc  mov     rcx, [rsp+38h+arg_0]
0x18001b7d1  lea     rax, [rsi+rbp*2]
0x18001b7d5  cmp     rcx, rax
0x18001b7d8  jb      short loc_18001B7F8
0x18001b7da  mov     ebx, 80070057h
0x18001b7df  lea     r8, word_18001DE6C; unsigned __int16 *
0x18001b7e6  mov     rdx, rbp; unsigned __int64
0x18001b7e9  mov     rcx, rsi; unsigned __int16 *
0x18001b7ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b7f1  mov     eax, ebx
0x18001b7f3  jmp     loc_18001B884
0x18001b7f8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b7fc  cmp     [rcx], r14w
0x18001b800  jnz     short loc_18001B845
0x18001b802  inc     rdi
0x18001b805  cmp     [rsi+rdi*2], r14w
0x18001b80a  jnz     short loc_18001B802
0x18001b80c  cmp     rdi, rbp
0x18001b80f  jb      short loc_18001B818
0x18001b811  mov     ebx, 80070057h
0x18001b816  jmp     short loc_18001B83F
0x18001b818  mov     ebx, 1
0x18001b81d  test    rdi, rdi
0x18001b820  jz      short loc_18001B83F
0x18001b822  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x18001b828  jnz     short loc_18001B83F
0x18001b82a  mov     rcx, rsi; pszPath
0x18001b82d  call    PathCchIsRoot
0x18001b832  test    eax, eax
0x18001b834  jnz     short loc_18001B83F
0x18001b836  mov     [rsi+rdi*2-2], r14w
0x18001b83c  mov     ebx, r14d
0x18001b83f  test    ebx, ebx
0x18001b841  jns     short loc_18001B7F1
0x18001b843  jmp     short loc_18001B7DF
0x18001b845  mov     [rcx], r14w
0x18001b849  inc     rdi
0x18001b84c  cmp     [rsi+rdi*2], r14w
0x18001b851  jnz     short loc_18001B849
0x18001b853  cmp     rdi, rbp
0x18001b856  jnb     short loc_18001B877
0x18001b858  test    rdi, rdi
0x18001b85b  jz      short loc_18001B877
0x18001b85d  cmp     word ptr [rsi+rdi*2-2], 5Ch ; '\'
0x18001b863  jnz     short loc_18001B877
0x18001b865  mov     rcx, rsi; pszPath
0x18001b868  call    PathCchIsRoot
0x18001b86d  test    eax, eax
0x18001b86f  jnz     short loc_18001B877
0x18001b871  mov     [rsi+rdi*2-2], r14w
0x18001b877  mov     ebx, r14d
0x18001b87a  jmp     loc_18001B7F1
0x18001b87f  mov     eax, 80070057h
0x18001b884  mov     rbx, [rsp+38h+arg_8]
0x18001b889  mov     rbp, [rsp+38h+arg_10]
0x18001b88e  add     rsp, 20h
0x18001b892  pop     r14
0x18001b894  pop     rdi
0x18001b895  pop     rsi
0x18001b896  retn
```
