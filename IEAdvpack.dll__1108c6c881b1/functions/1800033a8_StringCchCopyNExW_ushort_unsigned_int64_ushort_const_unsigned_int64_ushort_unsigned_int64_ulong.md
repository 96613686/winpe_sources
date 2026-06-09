# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1800033a8`
- end: `0x180003541`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `409`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, size_t cchDest, const unsigned __int16 *, size_t, unsigned __int16 **, unsigned __int64 *, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180003034`
- `0x180019fb8`

## callees

- `0x1800033a8`
- `0x180003654`
- `0x1800036d0`
- `0x1800036fc`
- `0x1800037a0`
- `0x1800037d0`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        const unsigned __int16 *a3,
        size_t a4,
        unsigned __int16 **a5,
        unsigned __int64 *a6,
        DWORD dwFlags)
{
  DWORD v7; // r15d
  size_t v10; // rdx
  wchar_t *v11; // rcx
  HRESULT v12; // ebx
  size_t v13; // r8
  DWORD v14; // r9d
  wchar_t *v15; // r12
  unsigned __int64 v16; // r14
  size_t v17; // r8
  size_t v18; // rax
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-10h] BYREF
  size_t pcchNewDestLength; // [rsp+38h] [rbp-8h] BYREF
  STRSAFE_PCNZWCH ppszSrc; // [rsp+90h] [rbp+50h] BYREF
  size_t pcchToRead; // [rsp+98h] [rbp+58h] BYREF

  pcchToRead = a4;
  ppszSrc = a3;
  v7 = dwFlags;
  v12 = StringExValidateDestW(pszDest, cchDest, (const size_t)a3, dwFlags);
  if ( v12 < 0 )
  {
    if ( cchDest )
      *v11 = 0;
    return (unsigned int)v12;
  }
  v15 = v11;
  ppszDestEnd = v11;
  v16 = v10;
  pcchNewDestLength = v10;
  v12 = StringExValidateSrcW(&ppszSrc, &pcchToRead, v13, v14);
  if ( v12 >= 0 )
  {
    if ( (v7 & 0xFFFFE000) == 0 )
    {
      if ( cchDest )
      {
        pcchNewDestLength = 0;
        v12 = StringCopyWorkerW_0(pszDest, cchDest, &pcchNewDestLength, ppszSrc, pcchToRead);
        v18 = pcchNewDestLength;
        v16 -= pcchNewDestLength;
        pcchNewDestLength = v16;
        v15 = &pszDest[v18];
        ppszDestEnd = v15;
        if ( v12 < 0 )
          goto LABEL_7;
        if ( (v7 & 0x200) != 0 && v16 > 1 )
          StringExHandleFillBehindNullW(&pszDest[v18], 2 * v16, v7);
      }
      else if ( pcchToRead && *ppszSrc )
      {
        if ( !pszDest )
        {
          v12 = -2147024809;
          goto LABEL_7;
        }
        v12 = -2147024774;
      }
      if ( v12 >= 0 )
      {
LABEL_12:
        if ( a5 )
          *a5 = v15;
        if ( a6 )
          *a6 = v16;
        return (unsigned int)v12;
      }
      goto LABEL_7;
    }
    v12 = -2147024809;
  }
  if ( cchDest )
    *pszDest = 0;
LABEL_7:
  if ( (v7 & 0x1C00) != 0 && cchDest )
  {
    StringExHandleOtherFlagsW(pszDest, 2 * cchDest, v17, &ppszDestEnd, &pcchNewDestLength, v7);
    v15 = ppszDestEnd;
    v16 = pcchNewDestLength;
  }
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147024774 )
    goto LABEL_12;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800033a8  mov     [rsp-38h+arg_0], rbx
0x1800033ad  mov     [rsp-38h+pcchToRead], r9
0x1800033b2  mov     [rsp-38h+ppszSrc], r8
0x1800033b7  push    rbp
0x1800033b8  push    rsi
0x1800033b9  push    rdi
0x1800033ba  push    r12
0x1800033bc  push    r13
0x1800033be  push    r14
0x1800033c0  push    r15
0x1800033c2  mov     rbp, rsp
0x1800033c5  sub     rsp, 40h
0x1800033c9  mov     r15d, [rbp+dwFlags]
0x1800033cd  mov     rdi, rdx
0x1800033d0  mov     r9d, r15d; dwFlags
0x1800033d3  mov     rsi, rcx
0x1800033d6  call    StringExValidateDestW
0x1800033db  xor     r13d, r13d
0x1800033de  mov     ebx, eax
0x1800033e0  test    eax, eax
0x1800033e2  js      loc_18000351E
0x1800033e8  mov     r12, rcx
0x1800033eb  mov     [rbp+ppszDestEnd], rcx
0x1800033ef  mov     r14, rdx
0x1800033f2  mov     [rbp+pcchNewDestLength], rdx
0x1800033f6  lea     rdx, [rbp+pcchToRead]; pcchToRead
0x1800033fa  lea     rcx, [rbp+ppszSrc]; ppszSrc
0x1800033fe  call    StringExValidateSrcW
0x180003403  mov     ebx, eax
0x180003405  test    eax, eax
0x180003407  js      short loc_180003417
0x180003409  test    r15d, 0FFFFE000h
0x180003410  jz      short loc_18000348D
0x180003412  mov     ebx, 80070057h
0x180003417  test    rdi, rdi
0x18000341a  jz      short loc_180003420
0x18000341c  mov     [rsi], r13w
0x180003420  test    r15d, 1C00h
0x180003427  jz      short loc_180003454
0x180003429  test    rdi, rdi
0x18000342c  jz      short loc_180003454
0x18000342e  lea     rax, [rbp+pcchNewDestLength]
0x180003432  mov     [rsp+40h+var_18], r15d; dwFlags
0x180003437  lea     rdx, [rdi+rdi]; cbDest
0x18000343b  mov     [rsp+40h+pcchRemaining], rax; pcchRemaining
0x180003440  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x180003444  mov     rcx, rsi; pszDest
0x180003447  call    StringExHandleOtherFlagsW
0x18000344c  mov     r12, [rbp+ppszDestEnd]
0x180003450  mov     r14, [rbp+pcchNewDestLength]
0x180003454  mov     ecx, 80000000h
0x180003459  lea     eax, [rbx+rcx]
0x18000345c  test    ecx, eax
0x18000345e  jnz     short loc_18000346C
0x180003460  cmp     ebx, 8007007Ah
0x180003466  jnz     loc_180003527
0x18000346c  mov     rax, [rbp+arg_20]
0x180003470  test    rax, rax
0x180003473  jz      short loc_180003478
0x180003475  mov     [rax], r12
0x180003478  mov     rax, [rbp+arg_28]
0x18000347c  test    rax, rax
0x18000347f  jz      loc_180003527
0x180003485  mov     [rax], r14
0x180003488  jmp     loc_180003527
0x18000348d  test    rdi, rdi
0x180003490  jnz     short loc_1800034B8
0x180003492  cmp     [rbp+pcchToRead], r13
0x180003496  jz      short loc_180003511
0x180003498  mov     rax, [rbp+ppszSrc]
0x18000349c  cmp     [rax], r13w
0x1800034a0  jz      short loc_180003511
0x1800034a2  test    rsi, rsi
0x1800034a5  jnz     short loc_1800034B1
0x1800034a7  mov     ebx, 80070057h
0x1800034ac  jmp     loc_180003420
0x1800034b1  mov     ebx, 8007007Ah
0x1800034b6  jmp     short loc_180003511
0x1800034b8  mov     rax, [rbp+pcchToRead]
0x1800034bc  lea     r8, [rbp+pcchNewDestLength]; pcchNewDestLength
0x1800034c0  mov     r9, [rbp+ppszSrc]; pszSrc
0x1800034c4  mov     rdx, rdi; cchDest
0x1800034c7  mov     rcx, rsi; pszDest
0x1800034ca  mov     [rsp+40h+pcchRemaining], rax; cchToCopy
0x1800034cf  mov     [rbp+pcchNewDestLength], r13
0x1800034d3  call    StringCopyWorkerW_0
0x1800034d8  mov     ebx, eax
0x1800034da  mov     rax, [rbp+pcchNewDestLength]
0x1800034de  sub     r14, rax
0x1800034e1  mov     [rbp+pcchNewDestLength], r14
0x1800034e5  lea     r12, [rsi+rax*2]
0x1800034e9  mov     [rbp+ppszDestEnd], r12
0x1800034ed  test    ebx, ebx
0x1800034ef  js      loc_180003420
0x1800034f5  bt      r15d, 9
0x1800034fa  jnb     short loc_180003511
0x1800034fc  cmp     r14, 1
0x180003500  jbe     short loc_180003511
0x180003502  lea     rdx, [r14+r14]; cbRemaining
0x180003506  mov     r8d, r15d; dwFlags
0x180003509  mov     rcx, r12; pszDestEnd
0x18000350c  call    StringExHandleFillBehindNullW
0x180003511  test    ebx, ebx
0x180003513  jns     loc_18000346C
0x180003519  jmp     loc_180003420
0x18000351e  test    rdi, rdi
0x180003521  jz      short loc_180003527
0x180003523  mov     [rcx], r13w
0x180003527  mov     eax, ebx
0x180003529  mov     rbx, [rsp+40h+arg_0]
0x180003531  add     rsp, 40h
0x180003535  pop     r15
0x180003537  pop     r14
0x180003539  pop     r13
0x18000353b  pop     r12
0x18000353d  pop     rdi
0x18000353e  pop     rsi
0x18000353f  pop     rbp
0x180003540  retn
```
