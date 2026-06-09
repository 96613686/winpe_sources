# IsMatchingToken(wchar_t const *,wchar_t const *,unsigned __int64,wchar_t const *,unsigned __int64,int,int,int *,uint *,int *,int *,int *,ulong)

- ea: `0x1800298f4`
- end: `0x180029d3b`
- name: `?IsMatchingToken@@YAHPEB_W0_K01HHPEAHPEAI222K@Z`
- size: `1095`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64, int, int, int *, unsigned int *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180029570`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x180029064`
- `0x180029534`
- `0x1800298f4`
- `0x180029d44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180029b00`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180029b00`

## pseudocode

```c
__int64 __fastcall IsMatchingToken(
        const wchar_t *a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        const wchar_t *a4,
        unsigned __int64 a5,
        int a6,
        int a7,
        int *a8,
        unsigned int *a9,
        int *a10,
        int *a11,
        int *a12)
{
  unsigned __int64 v12; // rbx
  const wchar_t *v13; // rsi
  const wchar_t *v14; // r12
  int v15; // r13d
  int v16; // r15d
  signed int v17; // ebx
  unsigned __int64 v18; // rcx
  WCHAR *v19; // rax
  const wchar_t *v20; // r8
  __int64 v21; // rdx
  WCHAR *v22; // rcx
  const WCHAR *v23; // r14
  WCHAR *lpString2; // rsi
  const WCHAR *v25; // rbp
  const WCHAR *v26; // rbx
  int v27; // edi
  bool v28; // zf
  __int16 v29; // r8
  bool v30; // zf
  const wchar_t *v31; // r12
  __int64 v32; // r14
  int v33; // esi
  unsigned int *v34; // rbx
  int v35; // ebp
  unsigned int i; // ecx
  const wchar_t *v37; // rdi
  int v38; // eax
  unsigned int v39; // ecx
  unsigned int *v40; // r10
  int v41; // eax
  int *v42; // rcx
  unsigned int v44; // [rsp+50h] [rbp-2C8h]
  unsigned __int16 v45; // [rsp+54h] [rbp-2C4h]
  wchar_t v46[4]; // [rsp+58h] [rbp-2C0h] BYREF
  const wchar_t *v47; // [rsp+60h] [rbp-2B8h]
  int *v48; // [rsp+68h] [rbp-2B0h]
  unsigned int *v49; // [rsp+70h] [rbp-2A8h]
  const wchar_t *v50; // [rsp+78h] [rbp-2A0h]
  const wchar_t *v51; // [rsp+80h] [rbp-298h]
  __int64 v52; // [rsp+88h] [rbp-290h]
  const wchar_t *v53; // [rsp+90h] [rbp-288h]
  unsigned __int64 v54; // [rsp+98h] [rbp-280h]
  int *v55; // [rsp+A0h] [rbp-278h]
  int *v56; // [rsp+A8h] [rbp-270h]
  int *v57; // [rsp+B0h] [rbp-268h]
  WCHAR String2[256]; // [rsp+C0h] [rbp-258h] BYREF

  v12 = a3;
  v48 = a8;
  v13 = a2;
  v14 = a4;
  v55 = a10;
  v15 = 0;
  v16 = 0;
  v56 = a11;
  v57 = a12;
  v52 = 0;
  v47 = a4;
  v54 = a3;
  v51 = a2;
  v53 = a1;
  v49 = a9;
  v50 = a4;
  v44 = 0;
  do
  {
    memset_0(String2, 0, 0x1F4u);
    if ( v12 <= 0x7FFFFFFE )
    {
      v18 = v12;
      v19 = String2;
      v20 = v13;
      v21 = 250;
      do
      {
        if ( !v18 )
          break;
        if ( !*v20 )
          break;
        *v19++ = *v20++;
        --v18;
        --v21;
      }
      while ( v21 );
      v22 = v19 - 1;
      if ( v21 )
        v22 = v19;
      v17 = v21 == 0 ? 0x8007007A : 0;
      *v22 = 0;
    }
    else
    {
      v17 = -2147024809;
    }
    v46[0] = String2[0];
    v46[1] = 0;
    v45 = DetermineStringEALangId(v46);
    if ( v17 < 0 || !v14 || !*v14 )
      break;
    v23 = 0;
    lpString2 = String2;
    v25 = v14;
    v26 = v14;
    v27 = 0;
    while ( 1 )
    {
      v28 = *lpString2 == 0;
      if ( !*lpString2 )
        break;
      if ( *lpString2 == 32 )
      {
        ++lpString2;
      }
      else
      {
        if ( *v26 == 32 )
          goto LABEL_31;
        if ( (unsigned int)IsJPNChar(*lpString2)
          || (unsigned __int16)(*lpString2 - 19968) <= 0x51A5u
          || (unsigned __int16)(*lpString2 + 21504) <= 0x2BA4u )
        {
          v30 = CompareStringEx(0, 0x30012u, v26, 1, lpString2, 1, 0, 0, 0) == 2;
        }
        else
        {
          v30 = v29 == (__int16)*lpString2;
        }
        if ( v30 )
        {
          if ( !v23 )
            v23 = v26;
          ++v27;
          ++lpString2;
        }
        else
        {
          if ( (unsigned int)IsSkippableCharacter(*v26) )
          {
LABEL_31:
            ++v26;
            if ( v27 )
              ++v27;
            goto LABEL_33;
          }
          v26 = v25;
          lpString2 = String2;
          ++v25;
          v23 = 0;
          v27 = 0;
        }
        ++v26;
      }
LABEL_33:
      if ( !*v26 )
      {
        v28 = *lpString2 == 0;
        break;
      }
    }
    v31 = v50;
    if ( !v28 || !v23 )
    {
      v27 = 0;
      v23 = 0;
    }
    v16 = v27;
    if ( !v23 )
      break;
    v32 = v23 - v50;
    if ( (_DWORD)v32 == -1 )
      break;
    v15 = v32 + v50 - v47;
    v52 = v51 - v53;
    v33 = a7 + v15;
    if ( v15 >= a6 )
      v33 = v32 + v50 - v47 - a6;
    if ( a6 > 0 && !v15 )
    {
      v33 = a7;
      if ( v27 > a6 + a7 )
        v15 = -1;
    }
    v34 = v49;
    v35 = 0;
    for ( i = 0; i < *v49; ++i )
    {
      v16 = v27;
      if ( v48[i] == v33 )
        v35 = 1;
    }
    v37 = v47;
    if ( !v15 )
    {
      if ( !v35 )
      {
        v48[*v49] = v33;
        ++*v34;
      }
      goto LABEL_62;
    }
    if ( v15 <= 0 )
    {
LABEL_63:
      v41 = v44;
    }
    else
    {
      v38 = IsSkippableCharacter(v47[v15 - 1]);
      v39 = 0;
      while ( v37[v15 - 1] != *((_WORD *)&g_szDelims_Text + v39) )
      {
        if ( ++v39 >= 4 )
        {
          if ( !v38 && v15 != a6 && !v45 )
            goto LABEL_63;
          break;
        }
      }
      if ( !v35 )
      {
        v40 = v49;
        v48[*v49] = v33;
        ++*v40;
      }
LABEL_62:
      v41 = 1;
      v44 = 1;
    }
    if ( v41 )
      break;
    v14 = &v31[(int)v32 + 1];
    v50 = v14;
    if ( !*v14 )
      break;
    v12 = v54;
    v13 = v51;
  }
  while ( v14 - v37 < a5 );
  v42 = v57;
  *v55 = v15;
  *v56 = v16;
  *v42 = v52;
  return v44;
}

```

## disassembly

```asm
0x1800298f4  push    rbx
0x1800298f6  push    rbp
0x1800298f7  push    rsi
0x1800298f8  push    rdi
0x1800298f9  push    r12
0x1800298fb  push    r13
0x1800298fd  push    r14
0x1800298ff  push    r15
0x180029901  sub     rsp, 2D8h
0x180029908  mov     rax, cs:__security_cookie
0x18002990f  xor     rax, rsp
0x180029912  mov     [rsp+318h+var_58], rax
0x18002991a  mov     rax, [rsp+318h+arg_38]
0x180029922  xor     ebp, ebp
0x180029924  mov     r10, [rsp+318h+arg_40]
0x18002992c  mov     rbx, r8
0x18002992f  mov     [rsp+318h+var_2B0], rax
0x180029934  mov     rsi, rdx
0x180029937  mov     rax, [rsp+318h+arg_48]
0x18002993f  mov     r12, r9
0x180029942  mov     [rsp+318h+var_278], rax
0x18002994a  mov     r13d, ebp
0x18002994d  mov     rax, [rsp+318h+arg_50]
0x180029955  mov     r15d, ebp
0x180029958  mov     [rsp+318h+var_270], rax
0x180029960  mov     rax, [rsp+318h+arg_58]
0x180029968  mov     [rsp+318h+var_268], rax
0x180029970  mov     eax, ebp
0x180029972  mov     [rsp+318h+var_290], rax
0x18002997a  mov     [rsp+318h+var_2B8], r9
0x18002997f  mov     [rsp+318h+var_280], rbx
0x180029987  mov     [rsp+318h+var_298], rdx
0x18002998f  mov     [rsp+318h+var_288], rcx
0x180029997  mov     [rsp+318h+var_2A8], r10
0x18002999c  mov     [rsp+318h+var_2A0], r9
0x1800299a1  mov     [rsp+318h+var_2C8], ebp
0x1800299a5  xor     edx, edx; Val
0x1800299a7  lea     rcx, [rsp+318h+String2]; void *
0x1800299af  mov     r8d, 1F4h; Size
0x1800299b5  call    memset_0
0x1800299ba  cmp     rbx, 7FFFFFFEh
0x1800299c1  jbe     short loc_1800299CA
0x1800299c3  mov     ebx, 80070057h
0x1800299c8  jmp     short loc_180029A1C
0x1800299ca  mov     rcx, rbx
0x1800299cd  lea     rax, [rsp+318h+String2]
0x1800299d5  mov     r8, rsi
0x1800299d8  mov     edx, 0FAh
0x1800299dd  test    rcx, rcx
0x1800299e0  jz      short loc_180029A01
0x1800299e2  movzx   r9d, word ptr [r8]
0x1800299e6  test    r9w, r9w
0x1800299ea  jz      short loc_180029A01
0x1800299ec  mov     [rax], r9w
0x1800299f0  add     r8, 2
0x1800299f4  add     rax, 2
0x1800299f8  dec     rcx
0x1800299fb  sub     rdx, 1
0x1800299ff  jnz     short loc_1800299DD
0x180029a01  test    rdx, rdx
0x180029a04  lea     rcx, [rax-2]
0x180029a08  cmovnz  rcx, rax
0x180029a0c  neg     rdx
0x180029a0f  sbb     ebx, ebx
0x180029a11  not     ebx
0x180029a13  and     ebx, 8007007Ah
0x180029a19  mov     [rcx], bp
0x180029a1c  movzx   eax, [rsp+318h+String2]
0x180029a24  lea     rcx, [rsp+318h+var_2C0]; wchar_t *
0x180029a29  mov     [rsp+318h+var_2C0], ax
0x180029a2e  mov     [rsp+318h+var_2BE], bp
0x180029a33  call    ?DetermineStringEALangId@@YAGPEB_W@Z; DetermineStringEALangId(wchar_t const *)
0x180029a38  mov     [rsp+318h+var_2C4], ax
0x180029a3d  test    ebx, ebx
0x180029a3f  js      loc_180029CEB
0x180029a45  test    r12, r12
0x180029a48  jz      loc_180029CEB
0x180029a4e  cmp     [r12], bp
0x180029a53  jz      loc_180029CEB
0x180029a59  mov     r14, rbp
0x180029a5c  lea     rsi, [rsp+318h+String2]
0x180029a64  mov     rbp, r12
0x180029a67  mov     rbx, r12
0x180029a6a  xor     r12d, r12d
0x180029a6d  mov     edi, r12d
0x180029a70  cmp     [rsi], r12w
0x180029a74  jz      loc_180029B59
0x180029a7a  cmp     word ptr [rsi], 20h ; ' '
0x180029a7e  jnz     short loc_180029A89
0x180029a80  add     rsi, 2
0x180029a84  jmp     loc_180029B4B
0x180029a89  movzx   r8d, word ptr [rbx]
0x180029a8d  cmp     r8w, 20h ; ' '
0x180029a92  jz      loc_180029B41
0x180029a98  movzx   ecx, word ptr [rsi]; wchar_t
0x180029a9b  call    ?IsJPNChar@@YAH_W@Z; IsJPNChar(wchar_t)
0x180029aa0  test    eax, eax
0x180029aa2  jnz     short loc_180029AD4
0x180029aa4  movzx   eax, word ptr [rsi]
0x180029aa7  mov     ecx, 4E00h
0x180029aac  sub     ax, cx
0x180029aaf  mov     ecx, 51A5h
0x180029ab4  cmp     ax, cx
0x180029ab7  jbe     short loc_180029AD4
0x180029ab9  movzx   eax, word ptr [rsi]
0x180029abc  mov     ecx, 5400h
0x180029ac1  add     ax, cx
0x180029ac4  mov     ecx, 2BA4h
0x180029ac9  cmp     ax, cx
0x180029acc  jbe     short loc_180029AD4
0x180029ace  cmp     r8w, [rsi]
0x180029ad2  jmp     short loc_180029B09
0x180029ad4  mov     [rsp+318h+lParam], r12; lParam
0x180029ad9  mov     r9d, 1; cchCount1
0x180029adf  mov     [rsp+318h+lpReserved], r12; lpReserved
0x180029ae4  mov     r8, rbx; lpString1
0x180029ae7  mov     [rsp+318h+lpVersionInformation], r12; lpVersionInformation
0x180029aec  mov     edx, 30012h; dwCmpFlags
0x180029af1  mov     [rsp+318h+cchCount2], 1; cchCount2
0x180029af9  xor     ecx, ecx; lpLocaleName
0x180029afb  mov     [rsp+318h+lpString2], rsi; lpString2
0x180029b00  call    cs:__imp_CompareStringEx
0x180029b06  cmp     eax, 2
0x180029b09  jnz     short loc_180029B1A
0x180029b0b  test    r14, r14
0x180029b0e  cmovz   r14, rbx
0x180029b12  inc     edi
0x180029b14  add     rsi, 2
0x180029b18  jmp     short loc_180029B3B
0x180029b1a  movzx   ecx, word ptr [rbx]; wchar_t
0x180029b1d  call    ?IsSkippableCharacter@@YAH_W@Z; IsSkippableCharacter(wchar_t)
0x180029b22  test    eax, eax
0x180029b24  jnz     short loc_180029B41
0x180029b26  mov     rbx, rbp
0x180029b29  lea     rsi, [rsp+318h+String2]
0x180029b31  add     rbp, 2
0x180029b35  mov     r14, r12
0x180029b38  mov     edi, r12d
0x180029b3b  add     rbx, 2
0x180029b3f  jmp     short loc_180029B4B
0x180029b41  add     rbx, 2
0x180029b45  test    edi, edi
0x180029b47  jz      short loc_180029B4B
0x180029b49  inc     edi
0x180029b4b  cmp     [rbx], r12w
0x180029b4f  jnz     loc_180029A70
0x180029b55  cmp     [rsi], r12w
0x180029b59  mov     r12, [rsp+318h+var_2A0]
0x180029b5e  jnz     short loc_180029B6A
0x180029b60  xor     r8d, r8d
0x180029b63  test    r14, r14
0x180029b66  jz      short loc_180029B6D
0x180029b68  jmp     short loc_180029B73
0x180029b6a  xor     r8d, r8d
0x180029b6d  mov     edi, r8d
0x180029b70  mov     r14, r8
0x180029b73  mov     r15d, edi
0x180029b76  test    r14, r14
0x180029b79  jz      loc_180029CEB
0x180029b7f  sub     r14, r12
0x180029b82  sar     r14, 1
0x180029b85  cmp     r14d, 0FFFFFFFFh
0x180029b89  jz      loc_180029CEB
0x180029b8f  mov     edx, [rsp+318h+arg_28]
0x180029b96  mov     r13, r12
0x180029b99  sub     r13, [rsp+318h+var_2B8]
0x180029b9e  mov     rax, [rsp+318h+var_298]
0x180029ba6  sub     rax, [rsp+318h+var_288]
0x180029bae  mov     ecx, [rsp+318h+arg_30]
0x180029bb5  sar     rax, 1
0x180029bb8  sar     r13, 1
0x180029bbb  add     r13d, r14d
0x180029bbe  mov     [rsp+318h+var_290], rax
0x180029bc6  mov     eax, r13d
0x180029bc9  sub     eax, edx
0x180029bcb  cmp     r13d, edx
0x180029bce  lea     esi, [rcx+r13]
0x180029bd2  cmovge  esi, eax
0x180029bd5  test    edx, edx
0x180029bd7  jle     short loc_180029BEB
0x180029bd9  test    r13d, r13d
0x180029bdc  jnz     short loc_180029BEB
0x180029bde  lea     eax, [rdx+rcx]
0x180029be1  mov     esi, ecx
0x180029be3  cmp     edi, eax
0x180029be5  jle     short loc_180029BEB
0x180029be7  or      r13d, 0FFFFFFFFh
0x180029beb  mov     rbx, [rsp+318h+var_2A8]
0x180029bf0  mov     ebp, r8d
0x180029bf3  mov     rdx, [rsp+318h+var_2B0]
0x180029bf8  mov     ecx, r8d
0x180029bfb  mov     r9d, 1
0x180029c01  cmp     [rbx], r8d
0x180029c04  jbe     short loc_180029C19
0x180029c06  mov     eax, ecx
0x180029c08  mov     r15d, edi
0x180029c0b  cmp     [rdx+rax*4], esi
0x180029c0e  cmovz   ebp, r9d
0x180029c12  add     ecx, r9d
0x180029c15  cmp     ecx, [rbx]
0x180029c17  jb      short loc_180029C06
0x180029c19  mov     rdi, [rsp+318h+var_2B8]
0x180029c1e  test    r13d, r13d
0x180029c21  jnz     short loc_180029C31
0x180029c23  test    ebp, ebp
0x180029c25  jnz     short loc_180029C9A
0x180029c27  mov     eax, [rbx]
0x180029c29  mov     [rdx+rax*4], esi
0x180029c2c  add     [rbx], r9d
0x180029c2f  jmp     short loc_180029C9A
0x180029c31  jle     short loc_180029CA3
0x180029c33  movsxd  rbx, r13d
0x180029c36  movzx   ecx, word ptr [rdi+rbx*2-2]; wchar_t
0x180029c3b  call    ?IsSkippableCharacter@@YAH_W@Z; IsSkippableCharacter(wchar_t)
0x180029c40  movzx   edx, word ptr [rdi+rbx*2-2]
0x180029c45  xor     r10d, r10d
0x180029c48  mov     ecx, r10d
0x180029c4b  mov     r8d, eax
0x180029c4e  lea     r9, ?g_szDelims_Text@@3QB_WB; wchar_t const near * const g_szDelims_Text
0x180029c55  mov     eax, ecx
0x180029c57  cmp     dx, [r9+rax*2]
0x180029c5c  mov     r9d, 1
0x180029c62  jz      short loc_180029C83
0x180029c64  add     ecx, r9d
0x180029c67  cmp     ecx, 4
0x180029c6a  jb      short loc_180029C4E
0x180029c6c  test    r8d, r8d
0x180029c6f  jnz     short loc_180029C83
0x180029c71  cmp     r13d, [rsp+318h+arg_28]
0x180029c79  jz      short loc_180029C83
0x180029c7b  cmp     [rsp+318h+var_2C4], r10w
0x180029c81  jz      short loc_180029CA3
0x180029c83  test    ebp, ebp
0x180029c85  jnz     short loc_180029C9A
0x180029c87  mov     r10, [rsp+318h+var_2A8]
0x180029c8c  mov     rcx, [rsp+318h+var_2B0]
0x180029c91  mov     eax, [r10]
0x180029c94  mov     [rcx+rax*4], esi
0x180029c97  add     [r10], r9d
0x180029c9a  mov     eax, r9d
0x180029c9d  mov     [rsp+318h+var_2C8], eax
0x180029ca1  jmp     short loc_180029CA7
0x180029ca3  mov     eax, [rsp+318h+var_2C8]
0x180029ca7  xor     ebp, ebp
0x180029ca9  test    eax, eax
0x180029cab  jnz     short loc_180029CEB
0x180029cad  movsxd  rax, r14d
0x180029cb0  lea     r12, [r12+rax*2]
0x180029cb4  add     r12, 2
0x180029cb8  mov     [rsp+318h+var_2A0], r12
0x180029cbd  cmp     [r12], bp
0x180029cc2  jz      short loc_180029CEB
0x180029cc4  mov     rbx, [rsp+318h+var_280]
0x180029ccc  mov     rcx, r12
0x180029ccf  mov     rsi, [rsp+318h+var_298]
0x180029cd7  sub     rcx, rdi
0x180029cda  sar     rcx, 1
0x180029cdd  cmp     rcx, [rsp+318h+arg_20]
0x180029ce5  jb      loc_1800299A5
0x180029ceb  mov     rax, [rsp+318h+var_278]
0x180029cf3  mov     rcx, [rsp+318h+var_268]
0x180029cfb  mov     [rax], r13d
0x180029cfe  mov     rax, [rsp+318h+var_270]
0x180029d06  mov     [rax], r15d
0x180029d09  mov     rax, [rsp+318h+var_290]
0x180029d11  mov     [rcx], eax
0x180029d13  mov     eax, [rsp+318h+var_2C8]
0x180029d17  mov     rcx, [rsp+318h+var_58]
0x180029d1f  xor     rcx, rsp; StackCookie
0x180029d22  call    __security_check_cookie
0x180029d27  add     rsp, 2D8h
0x180029d2e  pop     r15
0x180029d30  pop     r14
0x180029d32  pop     r13
0x180029d34  pop     r12
0x180029d36  pop     rdi
0x180029d37  pop     rsi
0x180029d38  pop     rbp
0x180029d39  pop     rbx
0x180029d3a  retn
```
