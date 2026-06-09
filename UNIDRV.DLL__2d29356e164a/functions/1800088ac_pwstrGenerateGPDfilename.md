# pwstrGenerateGPDfilename

- ea: `0x1800088ac`
- end: `0x180008a09`
- name: `pwstrGenerateGPDfilename`
- size: `349`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008d2c`
- `0x18007088c`

## callees

- `0x180007220`
- `0x1800088ac`
- `0x180024718`
- `0x1800453c8`
- `0x180049128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800088db`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800088db`
- `KERNEL32!LocalAlloc` at `0x180008945`
- `KERNEL32!LocalAlloc` at `0x180008945`

## string_xrefs

- `0x1800089df`: `Bad GPD filename extension: %ws`

## pseudocode

```c
wchar_t *__fastcall pwstrGenerateGPDfilename(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v2; // rbx
  wchar_t *v3; // rax
  const wchar_t *v4; // rsi
  __int64 v5; // rax
  unsigned int v6; // ebp
  size_t v7; // rbx
  wchar_t *v8; // r14
  wchar_t *v10; // rax
  __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  wchar_t *v13; // rdx
  __int64 v14; // rax
  const wchar_t *v15; // rcx
  wchar_t *v16; // rcx
  __int64 v17; // rax

  if ( !pszSrc )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( pszSrc[v2] );
  v3 = wcsrchr(pszSrc, 0x2Eu);
  v4 = v3;
  if ( !v3 || wcsicmp(v3, L".GPD") )
  {
    WriteDbgTraceWarningGpd("pwstrGenerateGPDfilename", "Bad GPD filename extension: %ws", pszSrc);
    v17 = (unsigned int)v2;
    LODWORD(v2) = v2 + 4;
    v4 = &pszSrc[v17];
  }
  v5 = (unsigned int)(v2 + 1);
  if ( (unsigned int)v5 >= (unsigned int)v2
    && (v6 = 2 * v5, v7 = (unsigned int)v5, (unsigned __int64)(2 * v5) <= 0xFFFFFFFF) )
  {
    v10 = (wchar_t *)LocalAlloc(0, v6);
    v8 = v10;
    if ( v10 )
    {
      StringCchCopyW(v10, v7, pszSrc);
      v11 = v4 - pszSrc;
      v12 = v7 - v11;
      if ( v12 )
      {
        v13 = &v8[v11];
        if ( v12 > 0x7FFFFFFF )
        {
          *v13 = 0;
        }
        else
        {
          v14 = 2147483646;
          v15 = L".BUD";
          do
          {
            if ( !v14 )
              break;
            if ( !*v15 )
              break;
            *v13++ = *v15++;
            --v14;
            --v12;
          }
          while ( v12 );
          v16 = v13 - 1;
          if ( v12 )
            v16 = v13;
          *v16 = 0;
        }
      }
    }
    else
    {
      WriteDbgTraceErrorGpd(
        (__int64)"pwstrGenerateGPDfilename",
        "Fatal: pwstrGenerateGPDfilename - unable to alloc %d bytes.",
        v6);
    }
  }
  else
  {
    v8 = 0;
    WriteDbgTraceErrorGpd((__int64)"pwstrGenerateGPDfilename", "Fatal: pwstrGenerateGPDfilename - arithmetic overflow");
  }
  return v8;
}

```

## disassembly

```asm
0x1800088ac  push    rbx
0x1800088ae  push    rbp
0x1800088af  push    rsi
0x1800088b0  push    rdi
0x1800088b1  push    r14
0x1800088b3  push    r15
0x1800088b5  sub     rsp, 28h
0x1800088b9  xor     r15d, r15d
0x1800088bc  mov     rdi, rcx
0x1800088bf  test    rcx, rcx
0x1800088c2  jz      loc_1800089D5
0x1800088c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800088cc  inc     rbx
0x1800088cf  cmp     [rcx+rbx*2], r15w
0x1800088d4  jnz     short loc_1800088CC
0x1800088d6  mov     edx, 2Eh ; '.'; Ch
0x1800088db  call    cs:__imp_wcsrchr
0x1800088e1  mov     rsi, rax
0x1800088e4  test    rax, rax
0x1800088e7  jz      loc_1800089DC
0x1800088ed  lea     rdx, aGpd; ".GPD"
0x1800088f4  mov     rcx, rax; String1
0x1800088f7  call    _wcsicmp
0x1800088fc  test    eax, eax
0x1800088fe  jnz     loc_1800089DC
0x180008904  lea     eax, [rbx+1]
0x180008907  cmp     eax, ebx
0x180008909  jb      short loc_18000891B
0x18000890b  lea     rbp, [rax+rax]
0x18000890f  mov     ebx, eax
0x180008911  mov     eax, 0FFFFFFFFh
0x180008916  cmp     rbp, rax
0x180008919  jbe     short loc_180008941
0x18000891b  lea     rdx, aFatalPwstrgene; "Fatal: pwstrGenerateGPDfilename - arith"...
0x180008922  mov     r14, r15
0x180008925  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x18000892c  call    WriteDbgTraceErrorGpd
0x180008931  mov     rax, r14
0x180008934  add     rsp, 28h
0x180008938  pop     r15
0x18000893a  pop     r14
0x18000893c  pop     rdi
0x18000893d  pop     rsi
0x18000893e  pop     rbp
0x18000893f  pop     rbx
0x180008940  retn
0x180008941  mov     edx, ebp; uBytes
0x180008943  xor     ecx, ecx; uFlags
0x180008945  call    cs:__imp_LocalAlloc
0x18000894b  mov     r14, rax
0x18000894e  test    rax, rax
0x180008951  jnz     short loc_18000896B
0x180008953  mov     r8, rbp
0x180008956  lea     rdx, aFatalPwstrgene_0; "Fatal: pwstrGenerateGPDfilename - unabl"...
0x18000895d  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x180008964  call    WriteDbgTraceErrorGpd
0x180008969  jmp     short loc_180008931
0x18000896b  mov     r8, rdi; pszSrc
0x18000896e  mov     rdx, rbx; cchDest
0x180008971  mov     rcx, r14; pszDest
0x180008974  call    StringCchCopyW
0x180008979  sub     rsi, rdi
0x18000897c  sar     rsi, 1
0x18000897f  sub     rbx, rsi
0x180008982  jz      short loc_180008931
0x180008984  lea     rdx, [r14+rsi*2]
0x180008988  cmp     rbx, 7FFFFFFFh
0x18000898f  ja      short loc_180008A00
0x180008991  mov     eax, 7FFFFFFEh
0x180008996  lea     rcx, aBud; ".BUD"
0x18000899d  test    rax, rax
0x1800089a0  jz      short loc_1800089C1
0x1800089a2  movzx   r8d, word ptr [rcx]
0x1800089a6  test    r8w, r8w
0x1800089aa  jz      short loc_1800089C1
0x1800089ac  mov     [rdx], r8w
0x1800089b0  add     rcx, 2
0x1800089b4  add     rdx, 2
0x1800089b8  dec     rax
0x1800089bb  sub     rbx, 1
0x1800089bf  jnz     short loc_18000899D
0x1800089c1  test    rbx, rbx
0x1800089c4  lea     rcx, [rdx-2]
0x1800089c8  cmovnz  rcx, rdx
0x1800089cc  mov     [rcx], r15w
0x1800089d0  jmp     loc_180008931
0x1800089d5  xor     eax, eax
0x1800089d7  jmp     loc_180008934
0x1800089dc  mov     r8, rdi
0x1800089df  lea     rdx, aBadGpdFilename; "Bad GPD filename extension: %ws"
0x1800089e6  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x1800089ed  call    WriteDbgTraceWarningGpd
0x1800089f2  mov     eax, ebx
0x1800089f4  add     ebx, 4
0x1800089f7  lea     rsi, [rdi+rax*2]
0x1800089fb  jmp     loc_180008904
0x180008a00  mov     [rdx], r15w
0x180008a04  jmp     loc_180008931
```
