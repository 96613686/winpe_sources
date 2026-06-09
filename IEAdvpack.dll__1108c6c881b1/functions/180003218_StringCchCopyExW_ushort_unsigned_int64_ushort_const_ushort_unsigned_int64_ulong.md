# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180003218`
- end: `0x18000339f`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `391`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, size_t, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, DWORD dwFlags)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003034`
- `0x1800121d8`
- `0x1800135d8`
- `0x180019fb8`
- `0x18001b1d8`

## callees

- `0x180003218`
- `0x180003654`
- `0x1800036d0`
- `0x1800036fc`
- `0x1800037a0`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        size_t a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5,
        DWORD dwFlags)
{
  size_t v9; // rdx
  wchar_t *v10; // rcx
  HRESULT v11; // ebx
  const wchar_t *v12; // r8
  wchar_t *v13; // r15
  unsigned __int64 v14; // rsi
  const WCHAR *v15; // rax
  HRESULT v16; // eax
  size_t v17; // rcx
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-58h] BYREF
  size_t pcchNewDestLength[10]; // [rsp+38h] [rbp-50h] BYREF

  v11 = StringExValidateDestW(pszDest, a2, (const size_t)a3, dwFlags);
  if ( v11 < 0 )
  {
    if ( a2 )
      *v10 = 0;
  }
  else
  {
    ppszDestEnd = v10;
    v13 = v10;
    pcchNewDestLength[0] = v9;
    v14 = v9;
    if ( (dwFlags & 0x100) != 0 )
    {
      v15 = &word_18001DE6C;
      if ( v12 )
        v15 = v12;
      v12 = v15;
    }
    if ( (dwFlags & 0xFFFFE000) != 0 )
    {
      v11 = -2147024809;
      if ( a2 )
        *v10 = 0;
    }
    else if ( a2 )
    {
      pcchNewDestLength[0] = 0;
      v16 = StringCopyWorkerW_0(v10, v9, pcchNewDestLength, v12, 0x7FFFFFFEu);
      v17 = pcchNewDestLength[0];
      v11 = v16;
      v14 -= pcchNewDestLength[0];
      pcchNewDestLength[0] = v14;
      v13 = &pszDest[v17];
      ppszDestEnd = v13;
      if ( v16 >= 0 )
      {
        if ( (dwFlags & 0x200) != 0 && v14 > 1 )
          StringExHandleFillBehindNullW(&pszDest[v17], 2 * v14, dwFlags);
        goto LABEL_14;
      }
    }
    else
    {
      v11 = 0;
      if ( !*v12 )
      {
LABEL_14:
        if ( a4 )
          *a4 = v13;
        if ( a5 )
          *a5 = v14;
        return (unsigned int)v11;
      }
      v11 = pszDest != 0 ? -2147024774 : -2147024809;
    }
    if ( (dwFlags & 0x1C00) != 0 && a2 )
    {
      StringExHandleOtherFlagsW(pszDest, 2 * a2, (size_t)v12, &ppszDestEnd, pcchNewDestLength, dwFlags);
      v13 = ppszDestEnd;
      v14 = pcchNewDestLength[0];
    }
    if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147024774 )
      goto LABEL_14;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003218  push    rbx
0x18000321a  push    rbp
0x18000321b  push    rsi
0x18000321c  push    rdi
0x18000321d  push    r12
0x18000321f  push    r13
0x180003221  push    r14
0x180003223  push    r15
0x180003225  sub     rsp, 48h
0x180003229  mov     ebp, [rsp+88h+dwFlags]
0x180003230  mov     r12, r9
0x180003233  mov     r9d, ebp; dwFlags
0x180003236  mov     rdi, rdx
0x180003239  mov     r14, rcx
0x18000323c  call    StringExValidateDestW
0x180003241  xor     r13d, r13d
0x180003244  mov     ebx, eax
0x180003246  test    eax, eax
0x180003248  js      loc_180003383
0x18000324e  mov     [rsp+88h+ppszDestEnd], rcx
0x180003253  mov     r15, rcx
0x180003256  mov     [rsp+88h+pcchNewDestLength], rdx
0x18000325b  mov     rsi, rdx
0x18000325e  bt      ebp, 8
0x180003262  jnb     short loc_180003275
0x180003264  test    r8, r8
0x180003267  lea     rax, word_18001DE6C
0x18000326e  cmovnz  rax, r8
0x180003272  mov     r8, rax; cchOriginalDestLength
0x180003275  test    ebp, 0FFFFE000h
0x18000327b  jz      short loc_1800032FB
0x18000327d  mov     ebx, 80070057h
0x180003282  test    rdi, rdi
0x180003285  jz      short loc_18000328B
0x180003287  mov     [rcx], r13w
0x18000328b  test    ebp, 1C00h
0x180003291  jz      short loc_1800032C1
0x180003293  test    rdi, rdi
0x180003296  jz      short loc_1800032C1
0x180003298  lea     rax, [rsp+88h+pcchNewDestLength]
0x18000329d  mov     [rsp+88h+var_60], ebp; dwFlags
0x1800032a1  lea     rdx, [rdi+rdi]; cbDest
0x1800032a5  mov     [rsp+88h+pcchRemaining], rax; pcchRemaining
0x1800032aa  lea     r9, [rsp+88h+ppszDestEnd]; ppszDestEnd
0x1800032af  mov     rcx, r14; pszDest
0x1800032b2  call    StringExHandleOtherFlagsW
0x1800032b7  mov     r15, [rsp+88h+ppszDestEnd]
0x1800032bc  mov     rsi, [rsp+88h+pcchNewDestLength]
0x1800032c1  mov     ecx, 80000000h
0x1800032c6  lea     eax, [rbx+rcx]
0x1800032c9  test    ecx, eax
0x1800032cb  jnz     short loc_1800032D9
0x1800032cd  cmp     ebx, 8007007Ah
0x1800032d3  jnz     loc_18000338C
0x1800032d9  test    r12, r12
0x1800032dc  jz      short loc_1800032E2
0x1800032de  mov     [r12], r15
0x1800032e2  mov     rax, [rsp+88h+arg_20]
0x1800032ea  test    rax, rax
0x1800032ed  jz      loc_18000338C
0x1800032f3  mov     [rax], rsi
0x1800032f6  jmp     loc_18000338C
0x1800032fb  test    rdi, rdi
0x1800032fe  jnz     short loc_180003320
0x180003300  mov     ebx, r13d
0x180003303  cmp     [r8], r13w
0x180003307  jz      short loc_1800032D9
0x180003309  mov     rax, r14
0x18000330c  mov     ebx, 80070057h
0x180003311  neg     rax
0x180003314  sbb     ecx, ecx
0x180003316  and     ecx, 23h
0x180003319  add     ebx, ecx
0x18000331b  jmp     loc_18000328B
0x180003320  mov     r9, r8; pszSrc
0x180003323  mov     [rsp+88h+pcchNewDestLength], r13
0x180003328  lea     r8, [rsp+88h+pcchNewDestLength]; pcchNewDestLength
0x18000332d  mov     [rsp+88h+pcchRemaining], 7FFFFFFEh; cchToCopy
0x180003336  call    StringCopyWorkerW_0
0x18000333b  mov     rcx, [rsp+88h+pcchNewDestLength]
0x180003340  mov     ebx, eax
0x180003342  sub     rsi, rcx
0x180003345  mov     [rsp+88h+pcchNewDestLength], rsi
0x18000334a  lea     r15, [r14+rcx*2]
0x18000334e  mov     [rsp+88h+ppszDestEnd], r15
0x180003353  test    eax, eax
0x180003355  js      loc_18000328B
0x18000335b  bt      ebp, 9
0x18000335f  jnb     loc_1800032D9
0x180003365  cmp     rsi, 1
0x180003369  jbe     loc_1800032D9
0x18000336f  lea     rdx, [rsi+rsi]; cbRemaining
0x180003373  mov     r8d, ebp; dwFlags
0x180003376  mov     rcx, r15; pszDestEnd
0x180003379  call    StringExHandleFillBehindNullW
0x18000337e  jmp     loc_1800032D9
0x180003383  test    rdi, rdi
0x180003386  jz      short loc_18000338C
0x180003388  mov     [rcx], r13w
0x18000338c  mov     eax, ebx
0x18000338e  add     rsp, 48h
0x180003392  pop     r15
0x180003394  pop     r14
0x180003396  pop     r13
0x180003398  pop     r12
0x18000339a  pop     rdi
0x18000339b  pop     rsi
0x18000339c  pop     rbp
0x18000339d  pop     rbx
0x18000339e  retn
```
