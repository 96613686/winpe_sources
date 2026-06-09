# IURLQualifyWithContext(ushort const *,ulong,ulong,ushort *,int *,int *,ISearchContext *)

- ea: `0x180025484`
- end: `0x1800257c6`
- name: `?IURLQualifyWithContext@@YAJPEBGKKPEAGPEAH2PEAUISearchContext@@@Z`
- size: `834`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, int *, int *, struct ISearchContext *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180023cb0`
- `0x180026bd4`

## callees

- `0x180023bfc`
- `0x1800243b0`
- `0x180025484`
- `0x18013f7d0`
- `0x1801e100c`
- `0x1801e1768`

## import_xrefs

- `SHLWAPI!PathIsURLW` at `0x1800254e2`
- `SHLWAPI!PathIsURLW` at `0x1800254e2`
- `SHLWAPI!UrlApplySchemeW` at `0x180025707`
- `SHLWAPI!UrlApplySchemeW` at `0x180025766`
- `SHLWAPI!UrlApplySchemeW` at `0x180025707`
- `SHLWAPI!UrlApplySchemeW` at `0x180025766`
- `SHLWAPI!UrlCreateFromPathW` at `0x18002555a`
- `SHLWAPI!UrlCreateFromPathW` at `0x1800257af`
- `SHLWAPI!UrlCreateFromPathW` at `0x18002555a`
- `SHLWAPI!UrlCreateFromPathW` at `0x1800257af`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002553b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002553b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002567e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002568e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002567e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002568e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800255e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800255e7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180025526`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180025526`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IURLQualifyWithContext(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 *a4,
        int *a5,
        int *a6,
        struct ISearchContext *a7)
{
  unsigned __int64 v8; // r12
  struct ISearchContext *v10; // r15
  HRESULT v11; // ebx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  PWSTR v14; // rdx
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rax
  WCHAR *v18; // r15
  unsigned int v19; // eax
  unsigned int i; // r14d
  unsigned int v22; // ebx
  unsigned __int16 *v23; // r14
  int v24; // eax
  size_t cchPathOut[4]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v26[68]; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR pszPathOut; // [rsp+C8h] [rbp-38h]
  unsigned int v28[4]; // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  v8 = a3;
  v10 = a7;
  cchPathOut[0] = (size_t)a7;
  v26[0] = 0;
  pszPathOut = v26;
  v28[0] = 65;
  if ( PathIsURLW(a1) )
  {
    if ( a4 == a1 )
      v11 = 1;
    else
      v11 = StringCchCopyW(a4, v8, a1);
    goto LABEL_22;
  }
  if ( a1[1] == 58 || a1[1] == 124 || *a1 == 92 )
  {
    v11 = ShStrW::SetSize((ShStrW *)v26, 0x104u);
    if ( v11 < 0 )
      goto LABEL_22;
    LODWORD(cchPathOut[0]) = v28[0];
    GetCurrentDirectoryW(0x104u, Buffer);
    v11 = PathCchCombine(pszPathOut, LODWORD(cchPathOut[0]), Buffer, a1);
    if ( v11 < 0 )
      goto LABEL_22;
    v11 = UrlCreateFromPathW(pszPathOut, pszPathOut, (DWORD *)cchPathOut, 0);
    if ( v11 == -2147467261 )
    {
      v11 = ShStrW::SetSize((ShStrW *)v26, cchPathOut[0]);
      if ( v11 < 0 )
        goto LABEL_22;
      LODWORD(cchPathOut[0]) = v28[0];
      v11 = UrlCreateFromPathW(pszPathOut, pszPathOut, (DWORD *)cchPathOut, 0);
    }
    goto LABEL_6;
  }
  v11 = 0;
  v19 = v28[0];
  for ( i = v28[0]; (unsigned int)v8 > i; i *= 4 )
    ;
  if ( i != v28[0] )
  {
    if ( !is_mul_ok(i, 2u) )
    {
      v11 = -2147024362;
      goto LABEL_22;
    }
    v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * i);
    v18 = v17;
    v11 = v17 == 0 ? 0x8007000E : 0;
    if ( !v17 )
      goto LABEL_22;
    v11 = StringCchCopyW(v17, i, pszPathOut);
    if ( pszPathOut != v26 )
      LocalFree(pszPathOut);
    v26[0] = 0;
    v19 = i;
    v28[0] = i;
    pszPathOut = v18;
    v10 = (struct ISearchContext *)cchPathOut[0];
  }
  if ( v11 < 0 )
    goto LABEL_22;
  LODWORD(cchPathOut[0]) = v19;
  v11 = UrlApplySchemeW(a1, pszPathOut, (DWORD *)cchPathOut, 2u);
  if ( v11 != 1 )
  {
LABEL_6:
    if ( v11 < 0 )
      goto LABEL_22;
    goto LABEL_7;
  }
  v22 = v28[0];
  v23 = pszPathOut;
  if ( !g_hdpaHooks )
    InitURLSearchHooks();
  v24 = TryURLSearchHooks(a1, v23, v22, v10);
  v11 = v24;
  if ( v24 < 0 || v24 == 1 )
  {
    LODWORD(cchPathOut[0]) = v28[0];
    v11 = UrlApplySchemeW(a1, pszPathOut, (DWORD *)cchPathOut, 1u);
    if ( v11 == 1 )
    {
      v11 = -2147217407;
      goto LABEL_22;
    }
    goto LABEL_6;
  }
LABEL_7:
  v12 = v8;
  if ( (_DWORD)v8 )
  {
    if ( v8 > 0x7FFFFFFF )
    {
      *a4 = 0;
    }
    else
    {
      v13 = 2147483646;
      v14 = pszPathOut;
      do
      {
        if ( !v13 )
          break;
        v15 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *a4++ = v15;
        --v13;
        --v12;
      }
      while ( v12 );
      v16 = a4 - 1;
      if ( v12 )
        v16 = a4;
      *v16 = 0;
    }
  }
LABEL_22:
  if ( pszPathOut != v26 )
    LocalFree(pszPathOut);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180025484  mov     [rsp-8+arg_8], rbx
0x180025489  push    rbp
0x18002548a  push    rsi
0x18002548b  push    rdi
0x18002548c  push    r12
0x18002548e  push    r13
0x180025490  push    r14
0x180025492  push    r15
0x180025494  lea     rbp, [rsp-200h]
0x18002549c  sub     rsp, 300h
0x1800254a3  mov     rax, cs:__security_cookie
0x1800254aa  xor     rax, rsp
0x1800254ad  mov     [rbp+230h+var_40], rax
0x1800254b4  mov     rdi, r9
0x1800254b7  mov     r12d, r8d
0x1800254ba  mov     rsi, rcx
0x1800254bd  mov     r15, [rbp+230h+arg_30]
0x1800254c4  mov     [rsp+330h+cchPathOut], r15
0x1800254c9  xor     r13d, r13d
0x1800254cc  mov     [rsp+330h+var_2F0], r13w
0x1800254d2  lea     rax, [rsp+330h+var_2F0]
0x1800254d7  mov     [rbp+230h+pszPathOut], rax
0x1800254db  mov     [rbp+230h+var_260], 41h ; 'A'
0x1800254e2  call    cs:__imp_PathIsURLW
0x1800254e8  test    eax, eax
0x1800254ea  jnz     loc_180025696
0x1800254f0  cmp     word ptr [rsi+2], 3Ah ; ':'
0x1800254f5  jnz     loc_1800256DA
0x1800254fb  mov     r14d, 104h
0x180025501  mov     edx, r14d; unsigned int
0x180025504  lea     rcx, [rsp+330h+var_2F0]; this
0x180025509  call    ?SetSize@ShStrW@@QEAAJK@Z; ShStrW::SetSize(ulong)
0x18002550e  mov     ebx, eax
0x180025510  test    eax, eax
0x180025512  js      loc_180025644
0x180025518  mov     eax, [rbp+230h+var_260]
0x18002551b  mov     dword ptr [rsp+330h+cchPathOut], eax
0x18002551f  lea     rdx, [rbp+230h+Buffer]; lpBuffer
0x180025523  mov     ecx, r14d; nBufferLength
0x180025526  call    cs:__imp_GetCurrentDirectoryW
0x18002552c  mov     edx, dword ptr [rsp+330h+cchPathOut]; cchPathOut
0x180025530  mov     r9, rsi; pszMore
0x180025533  lea     r8, [rbp+230h+Buffer]; pszPathIn
0x180025537  mov     rcx, [rbp+230h+pszPathOut]; pszPathOut
0x18002553b  call    cs:__imp_PathCchCombine
0x180025541  mov     ebx, eax
0x180025543  test    eax, eax
0x180025545  js      loc_180025644
0x18002554b  mov     rcx, [rbp+230h+pszPathOut]; pszPath
0x18002554f  xor     r9d, r9d; dwFlags
0x180025552  lea     r8, [rsp+330h+cchPathOut]; pcchUrl
0x180025557  mov     rdx, rcx; pszUrl
0x18002555a  call    cs:__imp_UrlCreateFromPathW
0x180025560  mov     ebx, eax
0x180025562  cmp     eax, 80004003h
0x180025567  jz      loc_180025781
0x18002556d  test    ebx, ebx
0x18002556f  js      loc_180025644
0x180025575  mov     rax, r12
0x180025578  test    r12d, r12d
0x18002557b  jz      loc_180025644
0x180025581  cmp     rax, 7FFFFFFFh
0x180025587  ja      loc_1800257BC
0x18002558d  mov     ecx, 7FFFFFFEh
0x180025592  mov     rdx, [rbp+230h+pszPathOut]
0x180025596  test    rcx, rcx
0x180025599  jz      short loc_1800255BA
0x18002559b  movzx   r8d, word ptr [rdx]
0x18002559f  test    r8w, r8w
0x1800255a3  jz      short loc_1800255BA
0x1800255a5  add     rdx, 2
0x1800255a9  mov     [rdi], r8w
0x1800255ad  add     rdi, 2
0x1800255b1  dec     rcx
0x1800255b4  sub     rax, 1
0x1800255b8  jnz     short loc_180025596
0x1800255ba  lea     rcx, [rdi-2]
0x1800255be  test    rax, rax
0x1800255c1  cmovnz  rcx, rdi
0x1800255c5  mov     [rcx], r13w
0x1800255c9  jmp     short loc_180025644
0x1800255cb  mov     r13d, r14d
0x1800255ce  mov     eax, 2
0x1800255d3  mul     r13
0x1800255d6  test    rdx, rdx
0x1800255d9  jnz     loc_180025687
0x1800255df  mov     rdx, rax; uBytes
0x1800255e2  mov     ecx, 40h ; '@'; uFlags
0x1800255e7  call    cs:__imp_LocalAlloc
0x1800255ed  mov     r15, rax
0x1800255f0  mov     rcx, rax
0x1800255f3  neg     rcx
0x1800255f6  sbb     ebx, ebx
0x1800255f8  not     ebx
0x1800255fa  and     ebx, 8007000Eh
0x180025600  test    rax, rax
0x180025603  jz      short loc_180025644
0x180025605  mov     r8, [rbp+230h+pszPathOut]; unsigned __int16 *
0x180025609  mov     edx, r13d; unsigned __int64
0x18002560c  mov     rcx, rax; unsigned __int16 *
0x18002560f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025614  mov     ebx, eax
0x180025616  lea     rax, [rsp+330h+var_2F0]
0x18002561b  mov     rcx, [rbp+230h+pszPathOut]; hMem
0x18002561f  cmp     rcx, rax
0x180025622  jnz     short loc_18002568E
0x180025624  xor     r13d, r13d
0x180025627  mov     [rsp+330h+var_2F0], r13w
0x18002562d  mov     eax, r14d
0x180025630  mov     [rbp+230h+var_260], eax
0x180025633  mov     [rbp+230h+pszPathOut], r15
0x180025637  mov     r15, [rsp+330h+cchPathOut]
0x18002563c  test    ebx, ebx
0x18002563e  jns     loc_1800256F1
0x180025644  lea     rax, [rsp+330h+var_2F0]
0x180025649  mov     rcx, [rbp+230h+pszPathOut]; hMem
0x18002564d  cmp     rcx, rax
0x180025650  jnz     short loc_18002567E
0x180025652  mov     eax, ebx
0x180025654  mov     rcx, [rbp+230h+var_40]
0x18002565b  xor     rcx, rsp; StackCookie
0x18002565e  call    __security_check_cookie
0x180025663  mov     rbx, [rsp+330h+arg_8]
0x18002566b  add     rsp, 300h
0x180025672  pop     r15
0x180025674  pop     r14
0x180025676  pop     r13
0x180025678  pop     r12
0x18002567a  pop     rdi
0x18002567b  pop     rsi
0x18002567c  pop     rbp
0x18002567d  retn
0x18002567e  call    cs:__imp_LocalFree
0x180025684  nop
0x180025685  jmp     short loc_180025652
0x180025687  mov     ebx, 80070216h
0x18002568c  jmp     short loc_180025644
0x18002568e  call    cs:__imp_LocalFree
0x180025694  jmp     short loc_180025624
0x180025696  cmp     rdi, rsi
0x180025699  jnz     short loc_1800256C5
0x18002569b  mov     ebx, 1
0x1800256a0  jmp     short loc_180025644
0x1800256a2  mov     ebx, r13d
0x1800256a5  mov     eax, [rbp+230h+var_260]
0x1800256a8  mov     r14d, eax
0x1800256ab  cmp     r12d, eax
0x1800256ae  ja      short loc_1800256BA
0x1800256b0  cmp     r14d, eax
0x1800256b3  jz      short loc_18002563C
0x1800256b5  jmp     loc_1800255CB
0x1800256ba  shl     r14d, 2
0x1800256be  cmp     r12d, r14d
0x1800256c1  jbe     short loc_1800256B0
0x1800256c3  jmp     short loc_1800256BA
0x1800256c5  mov     rdx, r12; unsigned __int64
0x1800256c8  mov     r8, rsi; unsigned __int16 *
0x1800256cb  mov     rcx, rdi; unsigned __int16 *
0x1800256ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800256d3  mov     ebx, eax
0x1800256d5  jmp     loc_180025644
0x1800256da  cmp     word ptr [rsi+2], 7Ch ; '|'
0x1800256df  jz      loc_1800254FB
0x1800256e5  cmp     word ptr [rsi], 5Ch ; '\'
0x1800256e9  jz      loc_1800254FB
0x1800256ef  jmp     short loc_1800256A2
0x1800256f1  mov     dword ptr [rsp+330h+cchPathOut], eax
0x1800256f5  mov     r9d, 2; dwFlags
0x1800256fb  lea     r8, [rsp+330h+cchPathOut]; pcchOut
0x180025700  mov     rdx, [rbp+230h+pszPathOut]; pszOut
0x180025704  mov     rcx, rsi; pszIn
0x180025707  call    cs:__imp_UrlApplySchemeW
0x18002570d  mov     ebx, eax
0x18002570f  cmp     eax, 1
0x180025712  jnz     loc_18002556D
0x180025718  mov     ebx, [rbp+230h+var_260]
0x18002571b  mov     r14, [rbp+230h+pszPathOut]
0x18002571f  cmp     cs:?g_hdpaHooks@@3PEAU_DPA@@EA, r13; _DPA * g_hdpaHooks
0x180025726  jnz     short loc_18002572D
0x180025728  call    ?InitURLSearchHooks@@YAXXZ; InitURLSearchHooks(void)
0x18002572d  mov     r9, r15; struct ISearchContext *
0x180025730  mov     r8d, ebx; unsigned int
0x180025733  mov     rdx, r14; unsigned __int16 *
0x180025736  mov     rcx, rsi; unsigned __int16 *
0x180025739  call    ?TryURLSearchHooks@@YAJPEBGPEAGIPEAUISearchContext@@@Z; TryURLSearchHooks(ushort const *,ushort *,uint,ISearchContext *)
0x18002573e  mov     ebx, eax
0x180025740  test    eax, eax
0x180025742  js      short loc_18002574D
0x180025744  cmp     eax, 1
0x180025747  jnz     loc_180025575
0x18002574d  mov     eax, [rbp+230h+var_260]
0x180025750  mov     dword ptr [rsp+330h+cchPathOut], eax
0x180025754  mov     r9d, 1; dwFlags
0x18002575a  lea     r8, [rsp+330h+cchPathOut]; pcchOut
0x18002575f  mov     rdx, [rbp+230h+pszPathOut]; pszOut
0x180025763  mov     rcx, rsi; pszIn
0x180025766  call    cs:__imp_UrlApplySchemeW
0x18002576c  mov     ebx, eax
0x18002576e  cmp     eax, 1
0x180025771  jnz     loc_18002556D
0x180025777  mov     ebx, 80041001h
0x18002577c  jmp     loc_180025644
0x180025781  mov     edx, dword ptr [rsp+330h+cchPathOut]; unsigned int
0x180025785  lea     rcx, [rsp+330h+var_2F0]; this
0x18002578a  call    ?SetSize@ShStrW@@QEAAJK@Z; ShStrW::SetSize(ulong)
0x18002578f  mov     ebx, eax
0x180025791  test    eax, eax
0x180025793  js      loc_180025644
0x180025799  mov     eax, [rbp+230h+var_260]
0x18002579c  mov     dword ptr [rsp+330h+cchPathOut], eax
0x1800257a0  mov     rcx, [rbp+230h+pszPathOut]; pszPath
0x1800257a4  xor     r9d, r9d; dwFlags
0x1800257a7  lea     r8, [rsp+330h+cchPathOut]; pcchUrl
0x1800257ac  mov     rdx, rcx; pszUrl
0x1800257af  call    cs:__imp_UrlCreateFromPathW
0x1800257b5  mov     ebx, eax
0x1800257b7  jmp     loc_18002556D
0x1800257bc  mov     [rdi], r13w
0x1800257c0  jmp     loc_180025644
```
