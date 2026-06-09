# PathCchCombineEx

- ea: `0x18001b294`
- end: `0x18001b51e`
- name: `PathCchCombineEx`
- size: `650`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `29`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180001e40`
- `0x180002d50`
- `0x180003fb8`
- `0x180004880`
- `0x180005a8c`
- `0x1800078d8`
- `0x180008524`
- `0x180008f2c`
- `0x180009c14`
- `0x18000a918`
- `0x18000ae68`
- `0x18000b8f0`
- `0x18000c3b8`
- `0x18000c760`
- `0x18000c99c`
- `0x18000cc80`
- `0x18000ced8`
- `0x18000d184`
- `0x18000e060`
- `0x18000ef90`
- `0x18000f7b0`
- `0x180010050`
- `0x1800115b0`
- `0x180011940`
- `0x180013c98`
- `0x180015ef8`
- `0x180017434`
- `0x180017728`
- `0x180017bcc`

## callees

- `0x1800022bc`
- `0x180019fb8`
- `0x18001b1d8`
- `0x18001b294`
- `0x18001b784`
- `0x18001b980`

## import_xrefs

- `msvcrt!iswalpha` at `0x18001b3bb`
- `msvcrt!iswalpha` at `0x18001b3bb`
- `KERNEL32!LocalFree` at `0x18001b4ec`
- `KERNEL32!LocalFree` at `0x18001b4ec`
- `KERNEL32!LocalAlloc` at `0x18001b36e`
- `KERNEL32!LocalAlloc` at `0x18001b36e`

## pseudocode

```c
HRESULT __stdcall PathCchCombineEx(
        PWSTR pszPathOut,
        size_t cchPathOut,
        PCWSTR pszPathIn,
        PCWSTR pszMore,
        ULONG dwFlags)
{
  unsigned __int16 *v8; // rdi
  unsigned __int64 v9; // r15
  HRESULT v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rbx
  size_t v13; // rsi
  size_t *v14; // r8
  PCWSTR v15; // r15
  size_t v16; // rdx
  unsigned __int16 *v17; // rcx
  WCHAR *v18; // r11
  size_t pcchRemaining; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszEnd; // [rsp+28h] [rbp-D8h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-D0h]
  _WORD v23[264]; // [rsp+40h] [rbp-C0h] BYREF

  pszDest = pszPathOut;
  if ( !pszPathOut || cchPathOut - 1 > 0x7FFF )
    return -2147024809;
  v8 = 0;
  if ( pszPathIn )
  {
    v11 = -1;
    do
      ++v11;
    while ( pszPathIn[v11] );
    if ( v11 >= 0x8000 )
      goto LABEL_9;
    v9 = v11 + 1;
    v12 = 0;
    if ( !v11 )
      v9 = 0;
    if ( !pszMore )
    {
LABEL_18:
      v13 = v12 + v9;
      if ( v12 + v9 <= 0x104 )
      {
        v23[0] = 0;
        v8 = v23;
        v13 = 260;
      }
      else
      {
        v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
        if ( !v8 )
        {
          v10 = -2147024882;
          goto LABEL_42;
        }
      }
      if ( v9 )
      {
        if ( !v12 )
        {
          v14 = (size_t *)pszPathIn;
LABEL_40:
          v17 = v8;
          v16 = v13;
          goto LABEL_41;
        }
        if ( *pszMore == 92 )
        {
          v15 = pszMore + 1;
        }
        else if ( !iswalpha(*pszMore) || (v15 = pszMore + 1, pszMore[1] != 58) )
        {
          v10 = StringCchCopyW(v8, v13, (size_t *)pszPathIn);
          if ( v10 < 0 )
            goto LABEL_42;
          pcchRemaining = (size_t)v18;
          ppszEnd = v18;
          v10 = PathCchAddBackslashEx(v8, v13, (PWSTR *)&pcchRemaining, (size_t *)&ppszEnd);
          if ( v10 < 0 )
            goto LABEL_42;
          v16 = (size_t)ppszEnd;
          v14 = (size_t *)pszMore;
          v17 = (unsigned __int16 *)pcchRemaining;
          goto LABEL_41;
        }
        if ( *pszMore == 92 && *v15 != 92 )
        {
          v10 = StringCchCopyW(v8, v13, (size_t *)pszPathIn);
          if ( v10 < 0 )
            goto LABEL_42;
          v10 = PathCchStripToRoot(v8, v13);
          if ( v10 < 0 )
            goto LABEL_42;
          ppszEnd = 0;
          pcchRemaining = 0;
          v10 = PathCchAddBackslashEx(v8, v13, &ppszEnd, &pcchRemaining);
          if ( v10 < 0 )
            goto LABEL_42;
          v16 = pcchRemaining;
          v14 = (size_t *)v15;
          v17 = ppszEnd;
LABEL_41:
          v10 = StringCchCopyW(v17, v16, v14);
          if ( v10 < 0 )
            goto LABEL_42;
LABEL_43:
          v10 = PathCchCanonicalizeEx(pszDest, cchPathOut, v8, (enum PATHCCH_OPTIONS)pszMore);
          goto LABEL_44;
        }
      }
      else if ( !v12 )
      {
        goto LABEL_43;
      }
      v14 = (size_t *)pszMore;
      goto LABEL_40;
    }
LABEL_13:
    v12 = -1;
    do
      ++v12;
    while ( pszMore[v12] );
    if ( v12 < 0x8000 )
    {
      if ( v12 )
        ++v12;
      goto LABEL_18;
    }
LABEL_9:
    v10 = -2147024690;
    goto LABEL_42;
  }
  v9 = 0;
  if ( pszMore )
    goto LABEL_13;
  v10 = -2147024809;
LABEL_42:
  StringCchCopyW(pszDest, cchPathOut, (size_t *)&word_18001DE6C);
LABEL_44:
  if ( v8 != v23 )
    LocalFree(v8);
  return v10;
}

```

## disassembly

```asm
0x18001b294  push    rbp
0x18001b296  push    rbx
0x18001b297  push    rsi
0x18001b298  push    rdi
0x18001b299  push    r12
0x18001b29b  push    r13
0x18001b29d  push    r14
0x18001b29f  push    r15
0x18001b2a1  lea     rbp, [rsp-168h]
0x18001b2a9  sub     rsp, 268h
0x18001b2b0  mov     rax, cs:__security_cookie
0x18001b2b7  xor     rax, rsp
0x18001b2ba  mov     [rbp+1A0h+var_50], rax
0x18001b2c1  xor     r11d, r11d
0x18001b2c4  mov     [rsp+2A0h+pszDest], rcx
0x18001b2c9  mov     r14, r9
0x18001b2cc  mov     r12, r8
0x18001b2cf  mov     r13, rdx
0x18001b2d2  test    rcx, rcx
0x18001b2d5  jz      loc_18001B4F6
0x18001b2db  lea     rax, [rdx-1]
0x18001b2df  cmp     rax, 7FFFh
0x18001b2e5  ja      loc_18001B4F6
0x18001b2eb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001b2ef  mov     edi, r11d
0x18001b2f2  mov     edx, 8000h
0x18001b2f7  test    r8, r8
0x18001b2fa  jnz     short loc_18001B30E
0x18001b2fc  mov     r15d, r11d
0x18001b2ff  test    r9, r9
0x18001b302  jnz     short loc_18001B33D
0x18001b304  mov     ebx, 80070057h
0x18001b309  jmp     loc_18001B4B7
0x18001b30e  mov     rax, rcx
0x18001b311  inc     rax
0x18001b314  cmp     [r8+rax*2], r11w
0x18001b319  jnz     short loc_18001B311
0x18001b31b  cmp     rax, rdx
0x18001b31e  jb      short loc_18001B32A
0x18001b320  mov     ebx, 800700CEh
0x18001b325  jmp     loc_18001B4B7
0x18001b32a  test    rax, rax
0x18001b32d  lea     r15, [rax+1]
0x18001b331  mov     rbx, r11
0x18001b334  cmovz   r15, rax
0x18001b338  test    r14, r14
0x18001b33b  jz      short loc_18001B357
0x18001b33d  mov     rbx, rcx
0x18001b340  inc     rbx
0x18001b343  cmp     [r9+rbx*2], r11w
0x18001b348  jnz     short loc_18001B340
0x18001b34a  cmp     rbx, rdx
0x18001b34d  jnb     short loc_18001B320
0x18001b34f  test    rbx, rbx
0x18001b352  jz      short loc_18001B357
0x18001b354  inc     rbx
0x18001b357  lea     rsi, [rbx+r15]
0x18001b35b  mov     ecx, 104h
0x18001b360  cmp     rsi, rcx
0x18001b363  jbe     short loc_18001B386
0x18001b365  lea     rdx, [rsi+rsi]; uBytes
0x18001b369  mov     ecx, 40h ; '@'; uFlags
0x18001b36e  call    cs:__imp_LocalAlloc
0x18001b374  mov     rdi, rax
0x18001b377  test    rax, rax
0x18001b37a  jnz     short loc_18001B394
0x18001b37c  mov     ebx, 8007000Eh
0x18001b381  jmp     loc_18001B4B7
0x18001b386  mov     [rsp+2A0h+var_260], r11w
0x18001b38c  lea     rdi, [rsp+2A0h+var_260]
0x18001b391  mov     rsi, rcx
0x18001b394  test    r15, r15
0x18001b397  jz      loc_18001B49E
0x18001b39d  test    rbx, rbx
0x18001b3a0  jnz     short loc_18001B3AA
0x18001b3a2  mov     r8, r12
0x18001b3a5  jmp     loc_18001B4A6
0x18001b3aa  cmp     word ptr [r14], 5Ch ; '\'
0x18001b3af  jnz     short loc_18001B3B7
0x18001b3b1  lea     r15, [r14+2]
0x18001b3b5  jmp     short loc_18001B3D7
0x18001b3b7  movzx   ecx, word ptr [r14]; C
0x18001b3bb  call    cs:__imp_iswalpha
0x18001b3c1  xor     r11d, r11d
0x18001b3c4  test    eax, eax
0x18001b3c6  jz      loc_18001B456
0x18001b3cc  lea     r15, [r14+2]
0x18001b3d0  cmp     word ptr [r15], 3Ah ; ':'
0x18001b3d5  jnz     short loc_18001B456
0x18001b3d7  cmp     word ptr [r14], 5Ch ; '\'
0x18001b3dc  jnz     loc_18001B4A3
0x18001b3e2  cmp     word ptr [r15], 5Ch ; '\'
0x18001b3e7  jz      loc_18001B4A3
0x18001b3ed  mov     r8, r12; unsigned __int16 *
0x18001b3f0  mov     rdx, rsi; unsigned __int64
0x18001b3f3  mov     rcx, rdi; unsigned __int16 *
0x18001b3f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b3fb  mov     ebx, eax
0x18001b3fd  test    eax, eax
0x18001b3ff  js      loc_18001B4B7
0x18001b405  mov     rdx, rsi; cchPath
0x18001b408  mov     rcx, rdi; pszPath
0x18001b40b  call    PathCchStripToRoot
0x18001b410  mov     ebx, eax
0x18001b412  test    eax, eax
0x18001b414  js      loc_18001B4B7
0x18001b41a  lea     r9, [rsp+2A0h+pcchRemaining]; pcchRemaining
0x18001b41f  mov     [rsp+2A0h+ppszEnd], 0
0x18001b428  lea     r8, [rsp+2A0h+ppszEnd]; ppszEnd
0x18001b42d  mov     [rsp+2A0h+pcchRemaining], 0
0x18001b436  mov     rdx, rsi; cchPath
0x18001b439  mov     rcx, rdi; pszPath
0x18001b43c  call    PathCchAddBackslashEx
0x18001b441  mov     ebx, eax
0x18001b443  test    eax, eax
0x18001b445  js      short loc_18001B4B7
0x18001b447  mov     rdx, [rsp+2A0h+pcchRemaining]
0x18001b44c  mov     r8, r15
0x18001b44f  mov     rcx, [rsp+2A0h+ppszEnd]
0x18001b454  jmp     short loc_18001B4AC
0x18001b456  mov     r8, r12; unsigned __int16 *
0x18001b459  mov     rdx, rsi; unsigned __int64
0x18001b45c  mov     rcx, rdi; unsigned __int16 *
0x18001b45f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b464  mov     ebx, eax
0x18001b466  test    eax, eax
0x18001b468  js      short loc_18001B4B7
0x18001b46a  lea     r9, [rsp+2A0h+ppszEnd]; pcchRemaining
0x18001b46f  mov     [rsp+2A0h+pcchRemaining], r11
0x18001b474  lea     r8, [rsp+2A0h+pcchRemaining]; ppszEnd
0x18001b479  mov     [rsp+2A0h+ppszEnd], r11
0x18001b47e  mov     rdx, rsi; cchPath
0x18001b481  mov     rcx, rdi; pszPath
0x18001b484  call    PathCchAddBackslashEx
0x18001b489  mov     ebx, eax
0x18001b48b  test    eax, eax
0x18001b48d  js      short loc_18001B4B7
0x18001b48f  mov     rdx, [rsp+2A0h+ppszEnd]
0x18001b494  mov     r8, r14
0x18001b497  mov     rcx, [rsp+2A0h+pcchRemaining]
0x18001b49c  jmp     short loc_18001B4AC
0x18001b49e  test    rbx, rbx
0x18001b4a1  jz      short loc_18001B4CD
0x18001b4a3  mov     r8, r14; unsigned __int16 *
0x18001b4a6  mov     rcx, rdi; unsigned __int16 *
0x18001b4a9  mov     rdx, rsi; unsigned __int64
0x18001b4ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b4b1  mov     ebx, eax
0x18001b4b3  test    eax, eax
0x18001b4b5  jns     short loc_18001B4CD
0x18001b4b7  mov     rcx, [rsp+2A0h+pszDest]; unsigned __int16 *
0x18001b4bc  lea     r8, word_18001DE6C; unsigned __int16 *
0x18001b4c3  mov     rdx, r13; unsigned __int64
0x18001b4c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b4cb  jmp     short loc_18001B4DF
0x18001b4cd  mov     rcx, [rsp+2A0h+pszDest]; pszDest
0x18001b4d2  mov     r8, rdi; unsigned __int16 *
0x18001b4d5  mov     rdx, r13; unsigned __int64
0x18001b4d8  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18001b4dd  mov     ebx, eax
0x18001b4df  lea     rax, [rsp+2A0h+var_260]
0x18001b4e4  cmp     rdi, rax
0x18001b4e7  jz      short loc_18001B4F2
0x18001b4e9  mov     rcx, rdi; hMem
0x18001b4ec  call    cs:__imp_LocalFree
0x18001b4f2  mov     eax, ebx
0x18001b4f4  jmp     short loc_18001B4FB
0x18001b4f6  mov     eax, 80070057h
0x18001b4fb  mov     rcx, [rbp+1A0h+var_50]
0x18001b502  xor     rcx, rsp; StackCookie
0x18001b505  call    __security_check_cookie
0x18001b50a  add     rsp, 268h
0x18001b511  pop     r15
0x18001b513  pop     r14
0x18001b515  pop     r13
0x18001b517  pop     r12
0x18001b519  pop     rdi
0x18001b51a  pop     rsi
0x18001b51b  pop     rbx
0x18001b51c  pop     rbp
0x18001b51d  retn
```
