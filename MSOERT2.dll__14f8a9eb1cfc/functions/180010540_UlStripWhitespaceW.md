# UlStripWhitespaceW

- ea: `0x180010540`
- end: `0x18001062d`
- name: `UlStripWhitespaceW`
- size: `237`
- prototype: `__int64 __fastcall(LPCWCH lpSrcStr)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001240`
- `0x180010540`

## import_xrefs

- `KERNEL32!RtlMoveMemory` at `0x1800105d9`
- `KERNEL32!RtlMoveMemory` at `0x1800105d9`

## pseudocode

```c
__int64 __fastcall UlStripWhitespaceW(LPCWCH lpSrcStr, int a2, int a3, _DWORD *a4)
{
  unsigned __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  const WCHAR *v10; // rsi
  const WCHAR *i; // rdi

  if ( a4 )
  {
    v7 = (unsigned int)*a4;
    lpSrcStr[v7] = 0;
    v8 = -1;
    do
      ++v8;
    while ( lpSrcStr[v8] );
    if ( v7 > v8 + 1 )
      LODWORD(v7) = v8;
  }
  else
  {
    if ( !lpSrcStr )
    {
      LODWORD(v7) = 0;
      goto LABEL_26;
    }
    v9 = -1;
    do
      ++v9;
    while ( lpSrcStr[v9] );
    LODWORD(v7) = v9;
  }
  if ( (_DWORD)v7 )
  {
    if ( !a2 )
      goto LABEL_17;
    goto LABEL_13;
  }
LABEL_26:
  if ( !a2 )
  {
    if ( !a3 )
      return 0;
    goto LABEL_18;
  }
LABEL_13:
  v10 = lpSrcStr;
  if ( (unsigned int)FIsSpaceW(lpSrcStr) )
  {
    do
    {
      ++v10;
      LODWORD(v7) = v7 - 1;
    }
    while ( (unsigned int)FIsSpaceW(v10) );
    if ( v10 != lpSrcStr )
      RtlMoveMemory(lpSrcStr, v10, (unsigned int)(2 * v7 + 2));
  }
LABEL_17:
  if ( a3 )
  {
LABEL_18:
    for ( i = &lpSrcStr[(unsigned int)v7]; (_DWORD)v7; LODWORD(v7) = v7 - 1 )
    {
      if ( !(unsigned int)FIsSpaceW(i - 1) )
        break;
      --i;
    }
    *i = 0;
  }
  if ( a4 )
    *a4 = v7;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010540  push    rbx
0x180010542  push    rbp
0x180010543  push    rsi
0x180010544  push    rdi
0x180010545  push    r14
0x180010547  push    r15
0x180010549  sub     rsp, 28h
0x18001054d  xor     r15d, r15d
0x180010550  mov     r14, r9
0x180010553  mov     ebp, r8d
0x180010556  mov     rdi, rcx
0x180010559  test    r9, r9
0x18001055c  jz      short loc_180010580
0x18001055e  mov     ebx, [r9]
0x180010561  mov     [rcx+rbx*2], r15w
0x180010566  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001056a  inc     rcx
0x18001056d  cmp     [rdi+rcx*2], r15w
0x180010572  jnz     short loc_18001056A
0x180010574  lea     rax, [rcx+1]
0x180010578  cmp     rbx, rax
0x18001057b  cmova   ebx, ecx
0x18001057e  jmp     short loc_180010599
0x180010580  test    rdi, rdi
0x180010583  jz      loc_18001061E
0x180010589  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001058d  inc     rcx
0x180010590  cmp     [rdi+rcx*2], r15w
0x180010595  jnz     short loc_18001058D
0x180010597  mov     ebx, ecx
0x180010599  test    ebx, ebx
0x18001059b  jz      loc_180010621
0x1800105a1  test    edx, edx
0x1800105a3  jz      short loc_1800105DF
0x1800105a5  mov     rcx, rdi; lpSrcStr
0x1800105a8  mov     rsi, rdi
0x1800105ab  call    FIsSpaceW
0x1800105b0  test    eax, eax
0x1800105b2  jz      short loc_1800105DF
0x1800105b4  add     rsi, 2
0x1800105b8  dec     ebx
0x1800105ba  mov     rcx, rsi; lpSrcStr
0x1800105bd  call    FIsSpaceW
0x1800105c2  test    eax, eax
0x1800105c4  jnz     short loc_1800105B4
0x1800105c6  cmp     rsi, rdi
0x1800105c9  jz      short loc_1800105DF
0x1800105cb  lea     r8d, ds:2[rbx*2]
0x1800105d3  mov     rdx, rsi
0x1800105d6  mov     rcx, rdi
0x1800105d9  call    cs:__imp_RtlMoveMemory
0x1800105df  test    ebp, ebp
0x1800105e1  jz      short loc_180010607
0x1800105e3  mov     eax, ebx
0x1800105e5  lea     rdi, [rdi+rax*2]
0x1800105e9  test    ebx, ebx
0x1800105eb  jz      short loc_180010603
0x1800105ed  lea     rcx, [rdi-2]; lpSrcStr
0x1800105f1  call    FIsSpaceW
0x1800105f6  test    eax, eax
0x1800105f8  jz      short loc_180010603
0x1800105fa  add     rdi, 0FFFFFFFFFFFFFFFEh
0x1800105fe  add     ebx, 0FFFFFFFFh
0x180010601  jnz     short loc_1800105ED
0x180010603  mov     [rdi], r15w
0x180010607  test    r14, r14
0x18001060a  jz      short loc_18001060F
0x18001060c  mov     [r14], ebx
0x18001060f  mov     eax, ebx
0x180010611  add     rsp, 28h
0x180010615  pop     r15
0x180010617  pop     r14
0x180010619  pop     rdi
0x18001061a  pop     rsi
0x18001061b  pop     rbp
0x18001061c  pop     rbx
0x18001061d  retn
0x18001061e  mov     ebx, r15d
0x180010621  test    edx, edx
0x180010623  jnz     short loc_1800105A5
0x180010625  test    ebp, ebp
0x180010627  jnz     short loc_1800105E3
0x180010629  xor     eax, eax
0x18001062b  jmp     short loc_180010611
```
