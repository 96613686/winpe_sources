# CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)

- ea: `0x1800483bc`
- end: `0x1800487d4`
- name: `?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z`
- size: `1048`
- prototype: `__int64 __fastcall(CommandLineBase *__hidden this, const wchar_t **, unsigned __int64, const wchar_t **, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180048d58`

## callees

- `0x1800483bc`
- `0x1800487dc`
- `0x180056500`
- `0x18005c410`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004858c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004858c`

## pseudocode

```c
__int64 __fastcall CommandLineBase::Parse(
        CommandLineBase *this,
        const wchar_t **a2,
        unsigned __int64 a3,
        const wchar_t **a4)
{
  const wchar_t **v6; // r14
  CommandLineBase *v7; // r13
  unsigned __int64 v8; // rcx
  __int64 result; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // rdi
  struct CommandLineArg *v12; // rcx
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  const wchar_t *v16; // r12
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // r15
  __int64 v19; // rdx
  const WCHAR *v20; // r14
  WCHAR v21; // ax
  const wchar_t **v22; // rdx
  __int64 cchCount2; // r13
  wchar_t *v24; // rax
  __int64 v25; // rdi
  struct CommandLineArg *v26; // rdx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rdx
  struct CommandLineArg *v29; // rcx
  __int64 v30; // r14
  int v31; // eax
  unsigned __int64 v32; // r15
  __int64 v33; // r8
  _DWORD *i; // r9
  int v35; // [rsp+50h] [rbp-51h]
  unsigned __int64 v37; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-39h]
  PCNZWCH lpString2; // [rsp+70h] [rbp-31h]
  PCNZWCH lpString1; // [rsp+78h] [rbp-29h]
  PCNZWCH *v41; // [rsp+80h] [rbp-21h]
  unsigned __int64 v42; // [rsp+88h] [rbp-19h]
  __int64 v43; // [rsp+90h] [rbp-11h]
  unsigned __int64 v44; // [rsp+98h] [rbp-9h]
  CommandLineBase *v45; // [rsp+A0h] [rbp-1h]
  struct CommandLineArg *v46; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int64 v47; // [rsp+B0h] [rbp+Fh] BYREF

  v38 = a3;
  v45 = this;
  v6 = a2;
  v7 = this;
  if ( a4 )
    *a4 = 0;
  v46 = 0;
  v47 = 0;
  (**(void (__fastcall ***)(CommandLineBase *, struct CommandLineArg **, unsigned __int64 *))this)(this, &v46, &v47);
  v8 = v47;
  if ( v47 > 0x40 )
    return 2147942456LL;
  v10 = 0;
  if ( v47 )
  {
    v11 = 0;
    do
    {
      v12 = v46;
      if ( (*(_DWORD *)((_BYTE *)v46 + v11 + 48) & 4) == 0 )
      {
        memset(
          (char *)v7 + *(_QWORD *)((char *)v46 + v11 + 8),
          0,
          *(_QWORD *)((char *)v46 + v11 + 16) * *(_QWORD *)((char *)v46 + v11 + 24));
        v12 = v46;
      }
      *(_QWORD *)((char *)v12 + v11 + 32) = 0;
      ++v10;
      v8 = v47;
      v11 += 56;
    }
    while ( v10 < v47 );
  }
  v37 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
  {
    v26 = v46;
    goto LABEL_56;
  }
  v15 = 0;
  v44 = 0;
  do
  {
    v16 = v6[v15];
    if ( (*(unsigned __int8 (__fastcall **)(CommandLineBase *, _QWORD))(*(_QWORD *)v7 + 8LL))(v7, *v16) )
    {
      v17 = v47;
      v18 = 0;
      if ( v47 )
      {
        v19 = 0;
        v43 = 0;
        while ( 1 )
        {
          v20 = *(const WCHAR **)((char *)v46 + v19);
          if ( v20 )
          {
            v21 = *v20;
            if ( *v20 )
              break;
          }
LABEL_27:
          v19 += 56;
          ++v18;
          v43 = v19;
          if ( v18 >= v17 )
            goto LABEL_28;
        }
        v42 = v14 + 1;
        v35 = 1;
        lpString1 = v16 + 1;
        v22 = &a2[v44 + 1];
        while ( 1 )
        {
          LODWORD(cchCount2) = -1;
          v41 = v22;
          if ( v21 == 32 )
          {
            do
              ++v20;
            while ( *v20 == 32 );
          }
          lpString2 = v20;
          v24 = wcschr(v20, 0x20u);
          v20 = v24;
          if ( v24 && (cchCount2 = v24 - lpString2, (unsigned __int64)(cchCount2 + 0x80000000LL) > 0xFFFFFFFF)
            || CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, cchCount2) != 2 )
          {
LABEL_26:
            v17 = v47;
            v19 = v43;
            goto LABEL_27;
          }
          if ( (_DWORD)cchCount2 == -1 )
            break;
          if ( v42 >= v38 )
            goto LABEL_26;
          ++v35;
          v22 = v41 + 1;
          lpString1 = *v41;
          v21 = *v20;
          ++v42;
        }
        v25 = 56 * v18;
        if ( *((_QWORD *)v46 + 7 * v18 + 4) && (*((_BYTE *)v46 + v25 + 48) & 0x18) == 0 )
        {
          if ( a4 )
            *a4 = v16;
          return 2147942485LL;
        }
        v6 = a2;
        v7 = v45;
        result = CommandLineBase::ParseArg(v45, &v37, v35, a2, v38, v18, v46, v47, v16, a4);
        if ( (int)result < 0 )
          return result;
        v8 = v47;
        if ( v18 < v47 )
        {
          v26 = v46;
          if ( (*((_BYTE *)v46 + v25 + 48) & 0x20) == 0 )
          {
            v27 = v37;
            goto LABEL_50;
          }
          break;
        }
      }
LABEL_28:
      if ( a4 )
        *a4 = v16;
      return 2147942422LL;
    }
    v28 = v47;
    if ( v13 >= v47 )
      goto LABEL_28;
    v29 = v46;
    v30 = 56 * v13;
    while ( 1 )
    {
      v31 = *(_DWORD *)((char *)v29 + v30 + 48);
      if ( (v31 & 1) == 0 || *(_QWORD *)((char *)v29 + v30 + 32) && (v31 & 0x10) == 0 )
        goto LABEL_45;
      v32 = v14;
      result = CommandLineBase::ParseArg(
                 v7,
                 &v37,
                 0,
                 a2,
                 v38,
                 v13,
                 v29,
                 v28,
                 *(const wchar_t **)((char *)v29 + v30),
                 a4);
      if ( (int)result < 0 )
        return result;
      v14 = v37;
      if ( v37 > v32 )
        break;
      v29 = v46;
      v28 = v47;
LABEL_45:
      ++v13;
      v30 += 56;
      if ( v13 >= v28 )
        goto LABEL_28;
    }
    v8 = v47;
    v27 = v37 - 1;
    if ( v13 >= v47 )
      goto LABEL_28;
    v26 = v46;
    v6 = a2;
    if ( (*((_BYTE *)v46 + 56 * v13 + 48) & 0x10) == 0 )
      ++v13;
LABEL_50:
    v14 = v27 + 1;
    v15 = v14;
    v37 = v14;
    v44 = v14;
  }
  while ( v14 < v38 );
LABEL_56:
  v33 = 0;
  if ( !v8 )
    return 0;
  for ( i = (_DWORD *)((char *)v26 + 48); *((_QWORD *)i - 2) || (*i & 2) == 0; i += 14 )
  {
    if ( ++v33 >= v8 )
      return 0;
  }
  if ( a4 )
    *a4 = (const wchar_t *)*((_QWORD *)v26 + 7 * v33);
  return 2147942560LL;
}

```

## disassembly

```asm
0x1800483bc  mov     [rsp-8+arg_10], rbx
0x1800483c1  push    rbp
0x1800483c2  push    rsi
0x1800483c3  push    rdi
0x1800483c4  push    r12
0x1800483c6  push    r13
0x1800483c8  push    r14
0x1800483ca  push    r15
0x1800483cc  lea     rbp, [rsp-1Fh]
0x1800483d1  sub     rsp, 0C0h
0x1800483d8  mov     rax, cs:__security_cookie
0x1800483df  xor     rax, rsp
0x1800483e2  mov     [rbp+4Fh+var_38], rax
0x1800483e6  xor     eax, eax
0x1800483e8  mov     [rbp+4Fh+var_88], r8
0x1800483ec  mov     [rbp+4Fh+var_98], rdx
0x1800483f0  mov     rbx, r9
0x1800483f3  mov     [rbp+4Fh+var_50], rcx
0x1800483f7  mov     r15, r8
0x1800483fa  mov     r14, rdx
0x1800483fd  mov     r13, rcx
0x180048400  test    r9, r9
0x180048403  jz      short loc_180048408
0x180048405  mov     [r9], rax
0x180048408  mov     [rbp+4Fh+var_48], rax
0x18004840c  lea     r8, [rbp+4Fh+var_40]
0x180048410  mov     [rbp+4Fh+var_40], rax
0x180048414  lea     rdx, [rbp+4Fh+var_48]
0x180048418  mov     rax, [rcx]
0x18004841b  mov     rax, [rax]
0x18004841e  call    _guard_dispatch_icall
0x180048423  mov     rcx, [rbp+4Fh+var_40]
0x180048427  cmp     rcx, 40h ; '@'
0x18004842b  jbe     short loc_180048437
0x18004842d  mov     eax, 80070038h
0x180048432  jmp     loc_180048796
0x180048437  xor     r10d, r10d
0x18004843a  mov     esi, r10d
0x18004843d  test    rcx, rcx
0x180048440  jz      short loc_180048487
0x180048442  mov     edi, r10d
0x180048445  mov     rcx, [rbp+4Fh+var_48]
0x180048449  mov     eax, [rdi+rcx+30h]
0x18004844d  test    al, 4
0x18004844f  jnz     short loc_180048472
0x180048451  mov     r8, [rdi+rcx+18h]
0x180048456  xor     edx, edx; Val
0x180048458  imul    r8, [rdi+rcx+10h]; Size
0x18004845e  mov     rcx, [rdi+rcx+8]
0x180048463  add     rcx, r13; void *
0x180048466  call    memset
0x18004846b  mov     rcx, [rbp+4Fh+var_48]
0x18004846f  xor     r10d, r10d
0x180048472  mov     [rdi+rcx+20h], r10
0x180048477  inc     rsi
0x18004847a  mov     rcx, [rbp+4Fh+var_40]
0x18004847e  add     rdi, 38h ; '8'
0x180048482  cmp     rsi, rcx
0x180048485  jb      short loc_180048445
0x180048487  mov     [rbp+4Fh+var_90], r10
0x18004848b  mov     rsi, r10
0x18004848e  mov     rdi, r10
0x180048491  test    r15, r15
0x180048494  jz      loc_18004876B
0x18004849a  mov     rax, r10
0x18004849d  mov     [rbp+4Fh+var_58], rax
0x1800484a1  mov     r12, [r14+rax*8]
0x1800484a5  mov     rcx, r13
0x1800484a8  mov     rax, [r13+0]
0x1800484ac  movzx   edx, word ptr [r12]
0x1800484b1  mov     rax, [rax+8]
0x1800484b5  call    _guard_dispatch_icall
0x1800484ba  xor     r10d, r10d
0x1800484bd  test    al, al
0x1800484bf  jz      loc_18004868A
0x1800484c5  mov     rcx, [rbp+4Fh+var_40]
0x1800484c9  mov     r15d, r10d
0x1800484cc  test    rcx, rcx
0x1800484cf  jz      loc_1800485E8
0x1800484d5  mov     edx, r10d
0x1800484d8  mov     [rbp+4Fh+var_60], rdx
0x1800484dc  mov     rax, [rbp+4Fh+var_48]
0x1800484e0  mov     r14, [rdx+rax]
0x1800484e4  test    r14, r14
0x1800484e7  jz      loc_1800485D4
0x1800484ed  movzx   eax, word ptr [r14]
0x1800484f1  cmp     r10w, ax
0x1800484f5  jz      loc_1800485D4
0x1800484fb  mov     rdx, [rbp+4Fh+var_98]
0x1800484ff  lea     rcx, [rdi+1]
0x180048503  mov     [rbp+4Fh+var_68], rcx
0x180048507  lea     r8, [r12+2]
0x18004850c  mov     rcx, [rbp+4Fh+var_58]
0x180048510  mov     [rbp+4Fh+var_A0], 1
0x180048517  mov     [rbp+4Fh+lpString1], r8
0x18004851b  lea     rdx, [rdx+rcx*8]
0x18004851f  add     rdx, 8
0x180048523  or      r13d, 0FFFFFFFFh
0x180048527  mov     [rbp+4Fh+var_70], rdx
0x18004852b  lea     ecx, [r13+21h]
0x18004852f  cmp     cx, ax
0x180048532  jnz     short loc_18004853E
0x180048534  add     r14, 2
0x180048538  cmp     cx, [r14]
0x18004853c  jz      short loc_180048534
0x18004853e  mov     edx, ecx; Ch
0x180048540  mov     [rbp+4Fh+var_80], r14
0x180048544  mov     rcx, r14; Str
0x180048547  call    wcschr
0x18004854c  mov     rcx, [rbp+4Fh+var_80]
0x180048550  mov     r14, rax
0x180048553  test    rax, rax
0x180048556  jz      short loc_180048573
0x180048558  mov     r13, rax
0x18004855b  mov     edx, 0FFFFFFFFh
0x180048560  sub     r13, rcx
0x180048563  mov     eax, 80000000h
0x180048568  sar     r13, 1
0x18004856b  add     rax, r13
0x18004856e  cmp     rax, rdx
0x180048571  ja      short loc_1800485C9
0x180048573  mov     r8, [rbp+4Fh+lpString1]; lpString1
0x180048577  or      r9d, 0FFFFFFFFh; cchCount1
0x18004857b  mov     [rsp+0F0h+cchCount2], r13d; cchCount2
0x180048580  mov     [rsp+0F0h+lpString2], rcx; lpString2
0x180048585  lea     edx, [r9+2]; dwCmpFlags
0x180048589  lea     ecx, [rdx+7Eh]; Locale
0x18004858c  call    cs:__imp_CompareStringW
0x180048592  cmp     eax, 2
0x180048595  jnz     short loc_1800485C9
0x180048597  cmp     r13d, 0FFFFFFFFh
0x18004859b  jz      short loc_1800485FA
0x18004859d  mov     rcx, [rbp+4Fh+var_68]
0x1800485a1  cmp     rcx, [rbp+4Fh+var_88]
0x1800485a5  jnb     short loc_1800485C9
0x1800485a7  mov     rdx, [rbp+4Fh+var_70]
0x1800485ab  inc     [rbp+4Fh+var_A0]
0x1800485ae  mov     rax, [rdx]
0x1800485b1  add     rdx, 8
0x1800485b5  inc     rcx
0x1800485b8  mov     [rbp+4Fh+lpString1], rax
0x1800485bc  movzx   eax, word ptr [r14]
0x1800485c0  mov     [rbp+4Fh+var_68], rcx
0x1800485c4  jmp     loc_180048523
0x1800485c9  mov     rcx, [rbp+4Fh+var_40]
0x1800485cd  xor     r10d, r10d
0x1800485d0  mov     rdx, [rbp+4Fh+var_60]
0x1800485d4  add     rdx, 38h ; '8'
0x1800485d8  inc     r15
0x1800485db  mov     [rbp+4Fh+var_60], rdx
0x1800485df  cmp     r15, rcx
0x1800485e2  jb      loc_1800484DC
0x1800485e8  test    rbx, rbx
0x1800485eb  jz      short loc_1800485F0
0x1800485ed  mov     [rbx], r12
0x1800485f0  mov     eax, 80070016h
0x1800485f5  jmp     loc_180048796
0x1800485fa  mov     rcx, [rbp+4Fh+var_48]
0x1800485fe  imul    rdi, r15, 38h ; '8'
0x180048602  cmp     qword ptr [rdi+rcx+20h], 0
0x180048608  jbe     short loc_180048615
0x18004860a  test    byte ptr [rdi+rcx+30h], 18h
0x18004860f  jz      loc_18004875C
0x180048615  mov     rax, [rbp+4Fh+var_40]
0x180048619  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x18004861d  mov     r14, [rbp+4Fh+var_98]
0x180048621  mov     r13, [rbp+4Fh+var_50]
0x180048625  mov     r9, r14; wchar_t **
0x180048628  movsxd  r8, [rbp+4Fh+var_A0]; unsigned __int64
0x18004862c  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x180048631  mov     [rsp+0F0h+var_B0], r12; wchar_t *
0x180048636  mov     [rsp+0F0h+var_B8], rax; unsigned __int64
0x18004863b  mov     rax, [rbp+4Fh+var_88]
0x18004863f  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x180048644  mov     rcx, r13; this
0x180048647  mov     qword ptr [rsp+0F0h+cchCount2], r15; unsigned __int64
0x18004864c  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x180048651  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x180048656  xor     r10d, r10d
0x180048659  test    eax, eax
0x18004865b  js      loc_180048796
0x180048661  mov     rcx, [rbp+4Fh+var_40]
0x180048665  cmp     r15, rcx
0x180048668  jnb     loc_1800485E8
0x18004866e  mov     rdx, [rbp+4Fh+var_48]
0x180048672  lea     r8d, [r10+20h]
0x180048676  test    [rdi+rdx+30h], r8b
0x18004867b  jnz     loc_18004876F
0x180048681  mov     rdi, [rbp+4Fh+var_90]
0x180048685  jmp     loc_180048742
0x18004868a  mov     rdx, [rbp+4Fh+var_40]
0x18004868e  cmp     rsi, rdx
0x180048691  jnb     loc_1800485E8
0x180048697  mov     rcx, [rbp+4Fh+var_48]
0x18004869b  imul    r14, rsi, 38h ; '8'
0x18004869f  mov     eax, [r14+rcx+30h]
0x1800486a4  test    al, 1
0x1800486a6  jz      short loc_18004870B
0x1800486a8  cmp     [r14+rcx+20h], r10
0x1800486ad  jbe     short loc_1800486B3
0x1800486af  test    al, 10h
0x1800486b1  jz      short loc_18004870B
0x1800486b3  mov     rax, [r14+rcx]
0x1800486b7  xor     r8d, r8d; unsigned __int64
0x1800486ba  mov     r9, [rbp+4Fh+var_98]; wchar_t **
0x1800486be  mov     r15, rdi
0x1800486c1  mov     [rsp+0F0h+var_A8], rbx; wchar_t **
0x1800486c6  mov     [rsp+0F0h+var_B0], rax; wchar_t *
0x1800486cb  mov     rax, [rbp+4Fh+var_88]
0x1800486cf  mov     [rsp+0F0h+var_B8], rdx; unsigned __int64
0x1800486d4  lea     rdx, [rbp+4Fh+var_90]; unsigned __int64 *
0x1800486d8  mov     [rsp+0F0h+var_C0], rcx; struct CommandLineArg *
0x1800486dd  mov     rcx, r13; this
0x1800486e0  mov     qword ptr [rsp+0F0h+cchCount2], rsi; unsigned __int64
0x1800486e5  mov     [rsp+0F0h+lpString2], rax; unsigned __int64
0x1800486ea  call    ?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z; CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)
0x1800486ef  xor     r10d, r10d
0x1800486f2  test    eax, eax
0x1800486f4  js      loc_180048796
0x1800486fa  mov     rdi, [rbp+4Fh+var_90]
0x1800486fe  cmp     rdi, r15
0x180048701  ja      short loc_18004871C
0x180048703  mov     rcx, [rbp+4Fh+var_48]
0x180048707  mov     rdx, [rbp+4Fh+var_40]
0x18004870b  inc     rsi
0x18004870e  add     r14, 38h ; '8'
0x180048712  cmp     rsi, rdx
0x180048715  jb      short loc_18004869F
0x180048717  jmp     loc_1800485E8
0x18004871c  mov     rcx, [rbp+4Fh+var_40]
0x180048720  dec     rdi
0x180048723  cmp     rsi, rcx
0x180048726  jnb     loc_1800485E8
0x18004872c  mov     rdx, [rbp+4Fh+var_48]
0x180048730  mov     r14, [rbp+4Fh+var_98]
0x180048734  imul    rax, rsi, 38h ; '8'
0x180048738  test    byte ptr [rax+rdx+30h], 10h
0x18004873d  jnz     short loc_180048742
0x18004873f  inc     rsi
0x180048742  inc     rdi
0x180048745  mov     rax, rdi
0x180048748  mov     [rbp+4Fh+var_90], rdi
0x18004874c  mov     [rbp+4Fh+var_58], rax
0x180048750  cmp     rdi, [rbp+4Fh+var_88]
0x180048754  jb      loc_1800484A1
0x18004875a  jmp     short loc_18004876F
0x18004875c  test    rbx, rbx
0x18004875f  jz      short loc_180048764
0x180048761  mov     [rbx], r12
0x180048764  mov     eax, 80070055h
0x180048769  jmp     short loc_180048796
0x18004876b  mov     rdx, [rbp+4Fh+var_48]
0x18004876f  mov     r8, r10
0x180048772  test    rcx, rcx
0x180048775  jz      short loc_180048794
0x180048777  lea     r9, [rdx+30h]
0x18004877b  cmp     [r9-10h], r10
0x18004877f  ja      short loc_180048788
0x180048781  mov     eax, [r9]
0x180048784  test    al, 2
0x180048786  jnz     short loc_1800487BD
0x180048788  inc     r8
0x18004878b  add     r9, 38h ; '8'
0x18004878f  cmp     r8, rcx
0x180048792  jb      short loc_18004877B
0x180048794  xor     eax, eax
0x180048796  mov     rcx, [rbp+4Fh+var_38]
0x18004879a  xor     rcx, rsp; StackCookie
0x18004879d  call    __security_check_cookie
0x1800487a2  mov     rbx, [rsp+0F0h+arg_10]
0x1800487aa  add     rsp, 0C0h
0x1800487b1  pop     r15
0x1800487b3  pop     r14
0x1800487b5  pop     r13
0x1800487b7  pop     r12
0x1800487b9  pop     rdi
0x1800487ba  pop     rsi
0x1800487bb  pop     rbp
0x1800487bc  retn
0x1800487bd  test    rbx, rbx
0x1800487c0  jz      short loc_1800487CD
0x1800487c2  imul    rax, r8, 38h ; '8'
0x1800487c6  mov     rcx, [rax+rdx]
0x1800487ca  mov     [rbx], rcx
0x1800487cd  mov     eax, 800700A0h
0x1800487d2  jmp     short loc_180048796
```
