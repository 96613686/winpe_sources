# ThunkToUnicode

- ea: `0x1800173a0`
- end: `0x18001742c`
- name: `ThunkToUnicode`
- size: `140`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, HLOCAL *)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x180002360`
- `0x180003874`
- `0x180003b50`
- `0x180005660`
- `0x180005dc0`
- `0x180008860`
- `0x180009890`
- `0x18000b170`
- `0x18000b560`
- `0x18000b5d0`
- `0x18000bcb0`
- `0x18000bf80`
- `0x18000d370`
- `0x18000f660`
- `0x18000ff40`
- `0x180010670`
- `0x180010810`
- `0x1800109e0`
- `0x180011370`
- `0x180011540`
- `0x1800118d0`
- `0x180014260`
- `0x180014350`
- `0x1800159e0`
- `0x180017020`
- `0x1800170e0`

## callees

- `0x1800173a0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800173fd`
- `KERNEL32!MultiByteToWideChar` at `0x1800173fd`
- `KERNEL32!LocalFree` at `0x18001740a`
- `KERNEL32!LocalFree` at `0x18001740a`
- `KERNEL32!LocalAlloc` at `0x1800173db`
- `KERNEL32!LocalAlloc` at `0x1800173db`

## pseudocode

```c
__int64 __fastcall ThunkToUnicode(LPCCH lpMultiByteStr, HLOCAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax

  if ( !lpMultiByteStr )
  {
    *a2 = 0;
    return 0;
  }
  v5 = -1;
  do
    ++v5;
  while ( lpMultiByteStr[v5] );
  cchWideChar = v5 + 1;
  lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v5 + 1));
  *a2 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
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
0x1800173a0  mov     [rsp+arg_0], rbx
0x1800173a5  mov     [rsp+arg_8], rsi
0x1800173aa  push    rdi
0x1800173ab  sub     rsp, 30h
0x1800173af  mov     rbx, rdx
0x1800173b2  mov     rdi, rcx
0x1800173b5  test    rcx, rcx
0x1800173b8  jnz     short loc_1800173C1
0x1800173ba  mov     [rdx], rcx
0x1800173bd  xor     eax, eax
0x1800173bf  jmp     short loc_18001741C
0x1800173c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800173c5  inc     rax
0x1800173c8  cmp     byte ptr [rcx+rax], 0
0x1800173cc  jnz     short loc_1800173C5
0x1800173ce  lea     esi, [rax+1]
0x1800173d1  mov     ecx, 40h ; '@'; uFlags
0x1800173d6  mov     edx, esi
0x1800173d8  add     rdx, rdx; uBytes
0x1800173db  call    cs:__imp_LocalAlloc
0x1800173e1  mov     [rbx], rax
0x1800173e4  test    rax, rax
0x1800173e7  jz      short loc_180017410
0x1800173e9  mov     [rsp+38h+cchWideChar], esi; cchWideChar
0x1800173ed  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800173f1  mov     r8, rdi; lpMultiByteStr
0x1800173f4  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x1800173f9  xor     edx, edx; dwFlags
0x1800173fb  xor     ecx, ecx; CodePage
0x1800173fd  call    cs:__imp_MultiByteToWideChar
0x180017403  test    eax, eax
0x180017405  jnz     short loc_1800173BD
0x180017407  mov     rcx, [rbx]; hMem
0x18001740a  call    cs:__imp_LocalFree
0x180017410  mov     eax, 80004005h
0x180017415  mov     qword ptr [rbx], 0
0x18001741c  mov     rbx, [rsp+38h+arg_0]
0x180017421  mov     rsi, [rsp+38h+arg_8]
0x180017426  add     rsp, 30h
0x18001742a  pop     rdi
0x18001742b  retn
```
