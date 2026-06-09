# TryLoadIndirectFriendlyName

- ea: `0x1800174e0`
- end: `0x1800175a0`
- name: `TryLoadIndirectFriendlyName`
- size: `192`
- prototype: `void *__fastcall(const WCHAR *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180016d30`
- `0x180017280`
- `0x1800173a0`

## callees

- `0x18000ea18`
- `0x1800174e0`
- `0x180017bc2`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`

## import_xrefs

- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180017534`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180017534`

## pseudocode

```c
void *__fastcall TryLoadIndirectFriendlyName(const WCHAR *a1)
{
  void *v2; // rdi
  __int64 v3; // rax
  SIZE_T v4; // rbx
  void *v5; // rax
  WCHAR pszOutBuf[2048]; // [rsp+20h] [rbp-1018h] BYREF

  v2 = 0;
  memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
  if ( SHLoadIndirectString(a1, pszOutBuf, 0x800u, 0) >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( pszOutBuf[v3] );
    v4 = (unsigned int)(2 * v3 + 2);
    v5 = pMemAlloc(v4);
    v2 = v5;
    if ( v5 )
      memcpy_0(v5, pszOutBuf, (unsigned int)v4);
  }
  return v2;
}

```

## disassembly

```asm
0x1800174e0  mov     [rsp+arg_8], rbx
0x1800174e5  mov     [rsp+arg_10], rsi
0x1800174ea  push    rdi
0x1800174eb  mov     eax, 1030h
0x1800174f0  call    _alloca_probe
0x1800174f5  sub     rsp, rax
0x1800174f8  mov     rax, cs:__security_cookie
0x1800174ff  xor     rax, rsp
0x180017502  mov     [rsp+1038h+var_18], rax
0x18001750a  mov     rbx, rcx
0x18001750d  xor     esi, esi
0x18001750f  lea     rcx, [rsp+1038h+pszOutBuf]; void *
0x180017514  xor     edx, edx; Val
0x180017516  mov     r8d, 1000h; Size
0x18001751c  mov     edi, esi
0x18001751e  call    memset_0
0x180017523  xor     r9d, r9d; ppvReserved
0x180017526  lea     rdx, [rsp+1038h+pszOutBuf]; pszOutBuf
0x18001752b  mov     r8d, 800h; cchOutBuf
0x180017531  mov     rcx, rbx; pszSource
0x180017534  call    cs:__imp_SHLoadIndirectString
0x18001753a  test    eax, eax
0x18001753c  js      short loc_180017578
0x18001753e  lea     rcx, [rsp+1038h+pszOutBuf]
0x180017543  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017547  inc     rax
0x18001754a  cmp     [rcx+rax*2], si
0x18001754e  jnz     short loc_180017547
0x180017550  lea     eax, ds:2[rax*2]
0x180017557  mov     ecx, eax; dwBytes
0x180017559  mov     ebx, eax
0x18001755b  call    pMemAlloc
0x180017560  mov     rdi, rax
0x180017563  test    rax, rax
0x180017566  jz      short loc_180017578
0x180017568  mov     r8d, ebx; Size
0x18001756b  lea     rdx, [rsp+1038h+pszOutBuf]; Src
0x180017570  mov     rcx, rax; void *
0x180017573  call    memcpy_0
0x180017578  mov     rax, rdi
0x18001757b  mov     rcx, [rsp+1038h+var_18]
0x180017583  xor     rcx, rsp; StackCookie
0x180017586  call    __security_check_cookie
0x18001758b  lea     r11, [rsp+1038h+var_8]
0x180017593  mov     rbx, [r11+18h]
0x180017597  mov     rsi, [r11+20h]
0x18001759b  mov     rsp, r11
0x18001759e  pop     rdi
0x18001759f  retn
```
