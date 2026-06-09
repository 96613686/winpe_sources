# DavCanonicalizeUncPathAndDetermineType

- ea: `0x180003570`
- end: `0x180003829`
- name: `DavCanonicalizeUncPathAndDetermineType`
- size: `697`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180001460`
- `0x180001e80`
- `0x1800027c0`
- `0x180003830`

## callees

- `0x180003570`
- `0x1800048b0`
- `0x180005d38`
- `0x1800060cd`

## import_xrefs

- `msvcrt!wcschr` at `0x1800036d7`
- `msvcrt!wcschr` at `0x1800036e6`
- `msvcrt!wcschr` at `0x1800036d7`
- `msvcrt!wcschr` at `0x1800036e6`
- `KERNEL32!LocalFree` at `0x180003717`
- `KERNEL32!LocalFree` at `0x18000374e`
- `KERNEL32!LocalFree` at `0x18000375c`
- `KERNEL32!LocalFree` at `0x180003717`
- `KERNEL32!LocalFree` at `0x18000374e`
- `KERNEL32!LocalFree` at `0x18000375c`
- `KERNEL32!LocalAlloc` at `0x1800035e1`
- `KERNEL32!LocalAlloc` at `0x180003669`
- `KERNEL32!LocalAlloc` at `0x18000378e`
- `KERNEL32!LocalAlloc` at `0x1800035e1`
- `KERNEL32!LocalAlloc` at `0x180003669`
- `KERNEL32!LocalAlloc` at `0x18000378e`
- `netutils!NetpwPathType` at `0x180003626`
- `netutils!NetpwPathType` at `0x180003626`
- `netutils!NetpwPathCanonicalize` at `0x1800036bb`
- `netutils!NetpwPathCanonicalize` at `0x1800037e0`
- `netutils!NetpwPathCanonicalize` at `0x1800036bb`
- `netutils!NetpwPathCanonicalize` at `0x1800037e0`

## pseudocode

```c
__int64 __fastcall DavCanonicalizeUncPathAndDetermineType(_WORD *Src, wchar_t **a2, _DWORD *a3)
{
  _WORD *v5; // rbx
  unsigned int v6; // r15d
  __int64 v7; // rax
  bool v8; // zf
  __int16 v9; // cx
  unsigned __int64 v10; // rsi
  __int64 v11; // rdi
  _WORD *v12; // rax
  _WORD *v13; // rbp
  SIZE_T v15; // r12
  wchar_t *v16; // rdi
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  wchar_t *v20; // r14
  const wchar_t *v21; // r8
  __int64 v22; // rcx
  int v23; // [rsp+70h] [rbp+8h] BYREF

  v23 = 0;
  *a2 = 0;
  v5 = Src;
  v6 = 0;
  if ( a3 )
    *a3 = 0;
  v7 = -1;
  do
    v8 = Src[++v7] == 0;
  while ( !v8 );
  v9 = Src[v7 - 1];
  v10 = v7 + 1;
  if ( v9 == 92 || (v13 = 0, v9 == 47) )
  {
    v11 = v7;
    v12 = LocalAlloc(0, 2 * v7);
    v13 = v12;
    if ( !v12 )
      return v6;
    memcpy_0(v12, v5, v11 * 2 - 2);
    v13[v11 - 1] = 0;
    v5 = v13;
  }
  if ( !(unsigned int)NetpwPathType(v5, &v23, 0) )
  {
    if ( v23 == 4144 )
    {
      if ( v10 + 2 < v10 )
        goto LABEL_23;
      v10 += 2LL;
    }
    v15 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) || v15 >= 0xFFFFFFFF )
    {
      v10 = 0x7FFFFFFF;
      v15 = 4294967294LL;
    }
    v16 = (wchar_t *)LocalAlloc(0, v15);
    if ( !v16 )
      goto LABEL_23;
    if ( v23 == 4144 )
    {
      v19 = (wchar_t *)LocalAlloc(0, v15);
      v20 = v19;
      if ( v19 )
      {
        if ( StringCchCopyW(v19, v10, v5) >= 0 && StringCchCatW(v20, v10, v21) >= 0 )
        {
          v23 = 4096;
          if ( !(unsigned int)NetpwPathCanonicalize(v20, v16, (unsigned int)v15, 0, &v23, 0) )
          {
            v16[v10 - 1] = 0;
            v22 = -1;
            do
              v8 = v16[++v22] == 0;
            while ( !v8 );
            v16[v22 - 2] = 0;
            v6 = 1;
            *a2 = v16;
            v16 = 0;
          }
        }
        LocalFree(v20);
        if ( !v16 )
          goto LABEL_23;
      }
    }
    else if ( (unsigned int)(v23 - 4096) <= 1 )
    {
      v23 = 4096;
      if ( !(unsigned int)NetpwPathCanonicalize(v5, v16, (unsigned int)v15, 0, &v23, 0) )
      {
        v16[v10 - 1] = 0;
        v17 = wcschr(v16 + 2, 0x5Cu);
        v18 = wcschr(v17 + 1, 0x5Cu);
        if ( v18 && v18[1] )
        {
          if ( a3 )
            *a3 = v18 - v16;
          v6 = 3;
        }
        else
        {
          v6 = 2;
        }
        *a2 = v16;
        goto LABEL_23;
      }
    }
    LocalFree(v16);
  }
LABEL_23:
  if ( v13 )
    LocalFree(v13);
  return v6;
}

```

## disassembly

```asm
0x180003570  push    rbx
0x180003572  push    rsi
0x180003573  push    r12
0x180003575  push    r13
0x180003577  push    r14
0x180003579  push    r15
0x18000357b  sub     rsp, 38h
0x18000357f  xor     r12d, r12d
0x180003582  mov     r14, r8
0x180003585  mov     [rsp+68h+arg_0], r12d
0x18000358a  mov     r13, rdx
0x18000358d  mov     [rdx], r12
0x180003590  mov     rbx, rcx
0x180003593  mov     r15d, r12d
0x180003596  test    r8, r8
0x180003599  jnz     loc_180003764
0x18000359f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800035a6  nop     word ptr [rax+rax+00000000h]
0x1800035b0  cmp     [rcx+rax*2+2], r12w
0x1800035b6  lea     rax, [rax+1]
0x1800035ba  jnz     short loc_1800035B0
0x1800035bc  movzx   ecx, word ptr [rcx+rax*2-2]
0x1800035c1  lea     rsi, [rax+1]
0x1800035c5  mov     [rsp+68h+arg_10], rbp
0x1800035cd  mov     [rsp+68h+var_38], rdi
0x1800035d2  cmp     cx, 5Ch ; '\'
0x1800035d6  jnz     short loc_180003612
0x1800035d8  lea     rdi, [rax+rax]
0x1800035dc  xor     ecx, ecx; uFlags
0x1800035de  mov     rdx, rdi; uBytes
0x1800035e1  call    cs:__imp_LocalAlloc
0x1800035e7  mov     rbp, rax
0x1800035ea  test    rax, rax
0x1800035ed  jnz     loc_18000376C
0x1800035f3  mov     rdi, [rsp+68h+var_38]
0x1800035f8  mov     eax, r15d
0x1800035fb  mov     rbp, [rsp+68h+arg_10]
0x180003603  add     rsp, 38h
0x180003607  pop     r15
0x180003609  pop     r14
0x18000360b  pop     r13
0x18000360d  pop     r12
0x18000360f  pop     rsi
0x180003610  pop     rbx
0x180003611  retn
0x180003612  mov     rbp, r12
0x180003615  cmp     cx, 2Fh ; '/'
0x180003619  jz      short loc_1800035D8
0x18000361b  xor     r8d, r8d
0x18000361e  lea     rdx, [rsp+68h+arg_0]
0x180003623  mov     rcx, rbx
0x180003626  call    cs:__imp_NetpwPathType
0x18000362c  test    eax, eax
0x18000362e  jnz     loc_18000370B
0x180003634  cmp     [rsp+68h+arg_0], 1030h
0x18000363c  jz      loc_180003722
0x180003642  mov     eax, 2
0x180003647  mul     rsi
0x18000364a  mov     r12, rax
0x18000364d  test    rdx, rdx
0x180003650  jnz     loc_18000373B
0x180003656  mov     eax, 0FFFFFFFFh
0x18000365b  cmp     r12, rax
0x18000365e  jnb     loc_18000373B
0x180003664  mov     rdx, r12; uBytes
0x180003667  xor     ecx, ecx; uFlags
0x180003669  call    cs:__imp_LocalAlloc
0x18000366f  mov     rdi, rax
0x180003672  test    rax, rax
0x180003675  jz      loc_18000370B
0x18000367b  mov     eax, [rsp+68h+arg_0]
0x18000367f  cmp     eax, 1030h
0x180003684  jz      loc_180003789
0x18000368a  add     eax, 0FFFFF000h
0x18000368f  cmp     eax, 1
0x180003692  ja      loc_180003759
0x180003698  lea     rax, [rsp+68h+arg_0]
0x18000369d  mov     [rsp+68h+var_40], r15d
0x1800036a2  mov     r8d, r12d
0x1800036a5  mov     [rsp+68h+var_48], rax
0x1800036aa  xor     r9d, r9d
0x1800036ad  mov     [rsp+68h+arg_0], 1000h
0x1800036b5  mov     rdx, rdi
0x1800036b8  mov     rcx, rbx
0x1800036bb  call    cs:__imp_NetpwPathCanonicalize
0x1800036c1  test    eax, eax
0x1800036c3  jnz     loc_180003759
0x1800036c9  mov     edx, 5Ch ; '\'; Ch
0x1800036ce  mov     [rdi+rsi*2-2], ax
0x1800036d3  lea     rcx, [rdi+4]; Str
0x1800036d7  call    cs:__imp_wcschr
0x1800036dd  mov     edx, 5Ch ; '\'; Ch
0x1800036e2  lea     rcx, [rax+2]; Str
0x1800036e6  call    cs:__imp_wcschr
0x1800036ec  test    rax, rax
0x1800036ef  jz      short loc_180003733
0x1800036f1  cmp     [rax+2], r15w
0x1800036f6  jz      short loc_180003733
0x1800036f8  test    r14, r14
0x1800036fb  jnz     loc_18000381B
0x180003701  mov     r15d, 3
0x180003707  mov     [r13+0], rdi
0x18000370b  test    rbp, rbp
0x18000370e  jz      loc_1800035F3
0x180003714  mov     rcx, rbp; hMem
0x180003717  call    cs:__imp_LocalFree
0x18000371d  jmp     loc_1800035F3
0x180003722  lea     rax, [rsi+2]
0x180003726  cmp     rax, rsi
0x180003729  jb      short loc_18000370B
0x18000372b  mov     rsi, rax
0x18000372e  jmp     loc_180003642
0x180003733  mov     r15d, 2
0x180003739  jmp     short loc_180003707
0x18000373b  mov     esi, 7FFFFFFFh
0x180003740  mov     r12d, 0FFFFFFFEh
0x180003746  jmp     loc_180003664
0x18000374b  mov     rcx, r14; hMem
0x18000374e  call    cs:__imp_LocalFree
0x180003754  test    rdi, rdi
0x180003757  jz      short loc_18000370B
0x180003759  mov     rcx, rdi; hMem
0x18000375c  call    cs:__imp_LocalFree
0x180003762  jmp     short loc_18000370B
0x180003764  mov     [r8], r12d
0x180003767  jmp     loc_18000359F
0x18000376c  lea     r8, [rdi-2]; Size
0x180003770  mov     rdx, rbx; Src
0x180003773  mov     rcx, rbp; void *
0x180003776  call    memcpy_0
0x18000377b  mov     [rdi+rbp-2], r12w
0x180003781  mov     rbx, rbp
0x180003784  jmp     loc_18000361B
0x180003789  mov     rdx, r12; uBytes
0x18000378c  xor     ecx, ecx; uFlags
0x18000378e  call    cs:__imp_LocalAlloc
0x180003794  mov     r14, rax
0x180003797  test    rax, rax
0x18000379a  jz      short loc_180003759
0x18000379c  mov     r8, rbx; pszSrc
0x18000379f  mov     rdx, rsi; cchDest
0x1800037a2  mov     rcx, rax; pszDest
0x1800037a5  call    StringCchCopyW
0x1800037aa  test    eax, eax
0x1800037ac  js      short loc_18000374B
0x1800037ae  mov     rdx, rsi; cchDest
0x1800037b1  mov     rcx, r14; pszDest
0x1800037b4  call    StringCchCatW
0x1800037b9  test    eax, eax
0x1800037bb  js      short loc_18000374B
0x1800037bd  lea     rax, [rsp+68h+arg_0]
0x1800037c2  mov     [rsp+68h+var_40], r15d
0x1800037c7  mov     r8d, r12d
0x1800037ca  mov     [rsp+68h+var_48], rax
0x1800037cf  xor     r9d, r9d
0x1800037d2  mov     [rsp+68h+arg_0], 1000h
0x1800037da  mov     rdx, rdi
0x1800037dd  mov     rcx, r14
0x1800037e0  call    cs:__imp_NetpwPathCanonicalize
0x1800037e6  test    eax, eax
0x1800037e8  jnz     loc_18000374B
0x1800037ee  mov     [rdi+rsi*2-2], ax
0x1800037f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800037fa  cmp     [rdi+rcx*2+2], ax
0x1800037ff  lea     rcx, [rcx+1]
0x180003803  jnz     short loc_1800037FA
0x180003805  mov     [rdi+rcx*2-4], ax
0x18000380a  mov     r15d, 1
0x180003810  mov     [r13+0], rdi
0x180003814  xor     edi, edi
0x180003816  jmp     loc_18000374B
0x18000381b  sub     rax, rdi
0x18000381e  sar     rax, 1
0x180003821  mov     [r14], eax
0x180003824  jmp     loc_180003701
```
