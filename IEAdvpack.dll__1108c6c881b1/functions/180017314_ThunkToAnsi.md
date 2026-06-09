# ThunkToAnsi

- ea: `0x180017314`
- end: `0x180017398`
- name: `ThunkToAnsi`
- size: `132`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, HLOCAL *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009928`
- `0x18000a24c`
- `0x18000c574`
- `0x180012110`

## callees

- `0x180017314`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180017374`
- `KERNEL32!WideCharToMultiByte` at `0x180017374`
- `KERNEL32!LocalFree` at `0x180017381`
- `KERNEL32!LocalFree` at `0x180017381`
- `KERNEL32!LocalAlloc` at `0x180017348`
- `KERNEL32!LocalAlloc` at `0x180017348`

## pseudocode

```c
__int64 __fastcall ThunkToAnsi(LPCWCH lpWideCharStr, HLOCAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax

  if ( !lpWideCharStr )
  {
    *a2 = 0;
    return 0;
  }
  v5 = -1;
  do
    ++v5;
  while ( lpWideCharStr[v5] );
  cbMultiByte = v5 + 1;
  lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, (unsigned int)(v5 + 1));
  *a2 = lpMultiByteStr;
  if ( lpMultiByteStr )
  {
    if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
      return 0;
    LocalFree(*a2);
  }
  result = 2147500037LL;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180017314  push    rbx
0x180017316  push    rbp
0x180017317  push    rsi
0x180017318  push    rdi
0x180017319  sub     rsp, 48h
0x18001731d  xor     ebp, ebp
0x18001731f  mov     rbx, rdx
0x180017322  mov     rdi, rcx
0x180017325  test    rcx, rcx
0x180017328  jnz     short loc_180017331
0x18001732a  mov     [rdx], rbp
0x18001732d  mov     eax, ebp
0x18001732f  jmp     short loc_18001738F
0x180017331  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017335  inc     rax
0x180017338  cmp     [rcx+rax*2], bp
0x18001733c  jnz     short loc_180017335
0x18001733e  lea     esi, [rax+1]
0x180017341  mov     ecx, 40h ; '@'; uFlags
0x180017346  mov     edx, esi; uBytes
0x180017348  call    cs:__imp_LocalAlloc
0x18001734e  mov     [rbx], rax
0x180017351  test    rax, rax
0x180017354  jz      short loc_180017387
0x180017356  mov     [rsp+68h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18001735b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001735f  mov     [rsp+68h+lpDefaultChar], rbp; lpDefaultChar
0x180017364  mov     r8, rdi; lpWideCharStr
0x180017367  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x18001736b  xor     edx, edx; dwFlags
0x18001736d  xor     ecx, ecx; CodePage
0x18001736f  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x180017374  call    cs:__imp_WideCharToMultiByte
0x18001737a  test    eax, eax
0x18001737c  jnz     short loc_18001732D
0x18001737e  mov     rcx, [rbx]; hMem
0x180017381  call    cs:__imp_LocalFree
0x180017387  mov     eax, 80004005h
0x18001738c  mov     [rbx], rbp
0x18001738f  add     rsp, 48h
0x180017393  pop     rdi
0x180017394  pop     rsi
0x180017395  pop     rbp
0x180017396  pop     rbx
0x180017397  retn
```
