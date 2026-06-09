# pwstrGenerateGPDfilename

- ea: `0x18000881c`
- end: `0x180008986`
- name: `pwstrGenerateGPDfilename`
- size: `362`
- prototype: `wchar_t *__fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008c9c`
- `0x1800728c8`

## callees

- `0x180007150`
- `0x18000881c`
- `0x180024c98`
- `0x180046748`
- `0x18004a668`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000884b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000884b`
- `KERNEL32!LocalAlloc` at `0x1800088bc`
- `KERNEL32!LocalAlloc` at `0x1800088bc`

## string_xrefs

- `0x18000895c`: `Bad GPD filename extension: %ws`

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
    WriteDbgTraceWarningGpd((__int64)"pwstrGenerateGPDfilename", "Bad GPD filename extension: %ws", pszSrc);
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
0x18000881c  push    rbx
0x18000881e  push    rbp
0x18000881f  push    rsi
0x180008820  push    rdi
0x180008821  push    r14
0x180008823  push    r15
0x180008825  sub     rsp, 28h
0x180008829  xor     r15d, r15d
0x18000882c  mov     rdi, rcx
0x18000882f  test    rcx, rcx
0x180008832  jz      loc_180008952
0x180008838  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000883c  inc     rbx
0x18000883f  cmp     [rcx+rbx*2], r15w
0x180008844  jnz     short loc_18000883C
0x180008846  mov     edx, 2Eh ; '.'; Ch
0x18000884b  call    cs:__imp_wcsrchr
0x180008852  nop     dword ptr [rax+rax+00h]
0x180008857  mov     rsi, rax
0x18000885a  test    rax, rax
0x18000885d  jz      loc_180008959
0x180008863  lea     rdx, aGpd; ".GPD"
0x18000886a  mov     rcx, rax; String1
0x18000886d  call    _wcsicmp
0x180008872  test    eax, eax
0x180008874  jnz     loc_180008959
0x18000887a  lea     eax, [rbx+1]
0x18000887d  cmp     eax, ebx
0x18000887f  jb      short loc_180008891
0x180008881  lea     rbp, [rax+rax]
0x180008885  mov     ebx, eax
0x180008887  mov     eax, 0FFFFFFFFh
0x18000888c  cmp     rbp, rax
0x18000888f  jbe     short loc_1800088B8
0x180008891  lea     rdx, aFatalPwstrgene; "Fatal: pwstrGenerateGPDfilename - arith"...
0x180008898  mov     r14, r15
0x18000889b  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x1800088a2  call    WriteDbgTraceErrorGpd
0x1800088a7  mov     rax, r14
0x1800088aa  add     rsp, 28h
0x1800088ae  pop     r15
0x1800088b0  pop     r14
0x1800088b2  pop     rdi
0x1800088b3  pop     rsi
0x1800088b4  pop     rbp
0x1800088b5  pop     rbx
0x1800088b6  retn
0x1800088b8  mov     edx, ebp; uBytes
0x1800088ba  xor     ecx, ecx; uFlags
0x1800088bc  call    cs:__imp_LocalAlloc
0x1800088c3  nop     dword ptr [rax+rax+00h]
0x1800088c8  mov     r14, rax
0x1800088cb  test    rax, rax
0x1800088ce  jnz     short loc_1800088E8
0x1800088d0  mov     r8, rbp
0x1800088d3  lea     rdx, aFatalPwstrgene_0; "Fatal: pwstrGenerateGPDfilename - unabl"...
0x1800088da  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x1800088e1  call    WriteDbgTraceErrorGpd
0x1800088e6  jmp     short loc_1800088A7
0x1800088e8  mov     r8, rdi; pszSrc
0x1800088eb  mov     rdx, rbx; cchDest
0x1800088ee  mov     rcx, r14; pszDest
0x1800088f1  call    StringCchCopyW
0x1800088f6  sub     rsi, rdi
0x1800088f9  sar     rsi, 1
0x1800088fc  sub     rbx, rsi
0x1800088ff  jz      short loc_1800088A7
0x180008901  lea     rdx, [r14+rsi*2]
0x180008905  cmp     rbx, 7FFFFFFFh
0x18000890c  ja      short loc_18000897D
0x18000890e  mov     eax, 7FFFFFFEh
0x180008913  lea     rcx, aBud; ".BUD"
0x18000891a  test    rax, rax
0x18000891d  jz      short loc_18000893E
0x18000891f  movzx   r8d, word ptr [rcx]
0x180008923  test    r8w, r8w
0x180008927  jz      short loc_18000893E
0x180008929  mov     [rdx], r8w
0x18000892d  add     rcx, 2
0x180008931  add     rdx, 2
0x180008935  dec     rax
0x180008938  sub     rbx, 1
0x18000893c  jnz     short loc_18000891A
0x18000893e  test    rbx, rbx
0x180008941  lea     rcx, [rdx-2]
0x180008945  cmovnz  rcx, rdx
0x180008949  mov     [rcx], r15w
0x18000894d  jmp     loc_1800088A7
0x180008952  xor     eax, eax
0x180008954  jmp     loc_1800088AA
0x180008959  mov     r8, rdi
0x18000895c  lea     rdx, aBadGpdFilename; "Bad GPD filename extension: %ws"
0x180008963  lea     rcx, aPwstrgenerateg; "pwstrGenerateGPDfilename"
0x18000896a  call    WriteDbgTraceWarningGpd
0x18000896f  mov     eax, ebx
0x180008971  add     ebx, 4
0x180008974  lea     rsi, [rdi+rax*2]
0x180008978  jmp     loc_18000887A
0x18000897d  mov     [rdx], r15w
0x180008981  jmp     loc_1800088A7
```
