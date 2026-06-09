# GetThisModulePath(ushort *,int)

- ea: `0x180006c80`
- end: `0x180006d1c`
- name: `?GetThisModulePath@@YAHPEAGH@Z`
- size: `156`
- prototype: `__int64 __fastcall(WCHAR *lpszStart)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f2c`
- `0x18000a918`

## callees

- `0x180006c80`

## import_xrefs

- `USER32!CharNextW` at `0x180006cfa`
- `USER32!CharNextW` at `0x180006cfa`
- `USER32!CharPrevW` at `0x180006cd2`
- `USER32!CharPrevW` at `0x180006ce6`
- `USER32!CharPrevW` at `0x180006cd2`
- `USER32!CharPrevW` at `0x180006ce6`
- `KERNEL32!GetModuleFileNameW` at `0x180006ca2`
- `KERNEL32!GetModuleFileNameW` at `0x180006ca2`

## pseudocode

```c
__int64 __fastcall GetThisModulePath(WCHAR *lpszStart)
{
  __int64 v2; // rax
  const WCHAR *i; // rdx
  LPWSTR v4; // rax
  const WCHAR *v5; // rbx

  if ( !GetModuleFileNameW(g_hInst, lpszStart, 0x104u) )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( lpszStart[v2] );
  for ( i = &lpszStart[v2]; ; i = v4 )
  {
    v4 = CharPrevW(lpszStart, i);
    v5 = v4;
    if ( v4 <= lpszStart || !*v4 || *v4 == 92 )
      break;
  }
  if ( *CharPrevW(lpszStart, v4) == 58 )
    *CharNextW(v5) = 0;
  else
    *v5 = 0;
  return 1;
}

```

## disassembly

```asm
0x180006c80  mov     [rsp+arg_0], rbx
0x180006c85  mov     [rsp+arg_8], rsi
0x180006c8a  push    rdi
0x180006c8b  sub     rsp, 20h
0x180006c8f  mov     rdi, rcx
0x180006c92  mov     rdx, rcx; lpFilename
0x180006c95  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x180006c9c  mov     r8d, 104h; nSize
0x180006ca2  call    cs:__imp_GetModuleFileNameW
0x180006ca8  xor     esi, esi
0x180006caa  test    eax, eax
0x180006cac  jz      short loc_180006D0A
0x180006cae  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006cb2  inc     rax
0x180006cb5  cmp     [rdi+rax*2], si
0x180006cb9  jnz     short loc_180006CB2
0x180006cbb  lea     rdx, [rdi+rax*2]
0x180006cbf  jmp     short loc_180006CCF
0x180006cc1  cmp     [rbx], si
0x180006cc4  jz      short loc_180006CE0
0x180006cc6  cmp     word ptr [rbx], 5Ch ; '\'
0x180006cca  jz      short loc_180006CE0
0x180006ccc  mov     rdx, rbx; lpszCurrent
0x180006ccf  mov     rcx, rdi; lpszStart
0x180006cd2  call    cs:__imp_CharPrevW
0x180006cd8  mov     rbx, rax
0x180006cdb  cmp     rax, rdi
0x180006cde  ja      short loc_180006CC1
0x180006ce0  mov     rdx, rbx; lpszCurrent
0x180006ce3  mov     rcx, rdi; lpszStart
0x180006ce6  call    cs:__imp_CharPrevW
0x180006cec  cmp     word ptr [rax], 3Ah ; ':'
0x180006cf0  jz      short loc_180006CF7
0x180006cf2  mov     [rbx], si
0x180006cf5  jmp     short loc_180006D03
0x180006cf7  mov     rcx, rbx; lpsz
0x180006cfa  call    cs:__imp_CharNextW
0x180006d00  mov     [rax], si
0x180006d03  mov     eax, 1
0x180006d08  jmp     short loc_180006D0C
0x180006d0a  xor     eax, eax
0x180006d0c  mov     rbx, [rsp+28h+arg_0]
0x180006d11  mov     rsi, [rsp+28h+arg_8]
0x180006d16  add     rsp, 20h
0x180006d1a  pop     rdi
0x180006d1b  retn
```
