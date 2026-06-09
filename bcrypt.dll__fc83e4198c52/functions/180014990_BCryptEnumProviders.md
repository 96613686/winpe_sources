# BCryptEnumProviders

- ea: `0x180014990`
- end: `0x180014cbc`
- name: `BCryptEnumProviders`
- size: `812`
- prototype: `NTSTATUS __stdcall(LPCWSTR pszAlgId, ULONG *pImplCount, BCRYPT_PROVIDER_NAME **ppImplList, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800030a0`
- `0x180004200`
- `0x180005060`
- `0x18000cae4`
- `0x180014990`
- `0x1800153d4`
- `0x18001b785`
- `0x18001b79d`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x180014c55`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptEnumProviders(
        LPCWSTR pszAlgId,
        ULONG *pImplCount,
        BCRYPT_PROVIDER_NAME **ppImplList,
        ULONG dwFlags)
{
  struct _CRYPT_PROVIDER_REFS *p_ppBuffer; // rdi
  ULONG v9; // r13d
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  _DWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  ULONG cProviders; // r8d
  int v22; // r9d
  ULONG v23; // edx
  __int64 v24; // rax
  unsigned int v25; // ebx
  __int64 v26; // rdx
  BCRYPT_PROVIDER_NAME *v27; // rsi
  __int64 v28; // r8
  ULONG v29; // eax
  __int64 v30; // r9
  WCHAR *v31; // r14
  __int64 v32; // rax
  size_t v33; // rbx
  __int64 v35; // [rsp+0h] [rbp-40h] BYREF
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+40h] [rbp+0h] BYREF
  ULONG pcbBuffer; // [rsp+48h] [rbp+8h] BYREF
  _BYTE v38[512]; // [rsp+50h] [rbp+10h] BYREF

  p_ppBuffer = (struct _CRYPT_PROVIDER_REFS *)v38;
  pcbBuffer = 512;
  ppBuffer = (PCRYPT_PROVIDER_REFS)v38;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SqqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)pImplCount,
      (_DWORD)ppImplList,
      (_DWORD)pszAlgId,
      (char)pImplCount,
      (char)ppImplList,
      dwFlags);
  v9 = 0;
  if ( !pszAlgId || !*pszAlgId || !pImplCount || !ppImplList || dwFlags )
  {
    v11 = -1073741811;
    v19 = 3221225485LL;
    v20 = 2759;
    goto LABEL_43;
  }
  *pImplCount = 0;
  *ppImplList = 0;
  while ( 1 )
  {
    v10 = BCryptResolveProviders(0, 0, pszAlgId, 0, 1u, 2u, &pcbBuffer, &ppBuffer);
    v11 = v10;
    if ( v10 != -1073741789 )
      break;
    if ( ppBuffer != (PCRYPT_PROVIDER_REFS)v38 && ppBuffer && LODWORD(ppBuffer[-1].rgpProviders) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    v12 = pcbBuffer;
    p_ppBuffer = 0;
    if ( !pcbBuffer )
      goto LABEL_51;
    if ( pcbBuffer > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_51;
    v13 = pcbBuffer + g_ulAdditionalProbeSize + 8;
    if ( v13 < pcbBuffer || !(unsigned int)VerifyStackAvailable(v13) )
      goto LABEL_51;
    v14 = v12 + 23;
    if ( v12 + 23 <= v12 + 8 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    p_ppBuffer = (struct _CRYPT_PROVIDER_REFS *)&ppBuffer;
    if ( &v35 == (__int64 *)-64LL
      || (LODWORD(ppBuffer) = 1801679955, (p_ppBuffer = (struct _CRYPT_PROVIDER_REFS *)&pcbBuffer) == 0) )
    {
LABEL_51:
      if ( v12 + 8 >= v12 )
      {
        v18 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_ppBuffer = (struct _CRYPT_PROVIDER_REFS *)v18;
        if ( v18 )
        {
          *v18 = 1885431112;
          p_ppBuffer = (struct _CRYPT_PROVIDER_REFS *)(v18 + 2);
        }
      }
    }
    ppBuffer = p_ppBuffer;
    if ( !p_ppBuffer )
    {
      v11 = -1073741801;
LABEL_29:
      v19 = v11;
      v20 = 2816;
      goto LABEL_43;
    }
  }
  p_ppBuffer = ppBuffer;
  if ( v10 < 0 )
    goto LABEL_29;
  cProviders = ppBuffer->cProviders;
  v22 = 0;
  if ( ppBuffer->cProviders )
  {
    v23 = 0;
    do
    {
      v24 = -1;
      do
        ++v24;
      while ( ppBuffer->rgpProviders[v23]->pszProvider[v24] );
      ++v23;
      v22 += 2 * v24 + 2;
    }
    while ( v23 < cProviders );
  }
  v25 = cProviders;
  v27 = (BCRYPT_PROVIDER_NAME *)SafeAllocaAllocateFromHeap(8 * cProviders + v22);
  if ( !v27 )
  {
    v11 = -1073741801;
    v19 = 3221225495LL;
    v20 = 2841;
LABEL_43:
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
    goto LABEL_44;
  }
  v29 = p_ppBuffer->cProviders;
  v30 = 0;
  v31 = (WCHAR *)&v27[v25];
  if ( p_ppBuffer->cProviders )
  {
    do
    {
      v32 = -1;
      do
        ++v32;
      while ( p_ppBuffer->rgpProviders[v9]->pszProvider[v32] );
      v27[v9].pszProviderName = v31;
      v33 = 2LL * (unsigned int)(v32 + 1);
      memcpy_0(v31, p_ppBuffer->rgpProviders[v9]->pszProvider, v33);
      v29 = p_ppBuffer->cProviders;
      v31 = (WCHAR *)((char *)v31 + v33);
      ++v9;
      v30 = 0;
    }
    while ( v9 < p_ppBuffer->cProviders );
  }
  *pImplCount = v29;
  v11 = 0;
  *ppImplList = v27;
LABEL_44:
  if ( p_ppBuffer
    && p_ppBuffer != (struct _CRYPT_PROVIDER_REFS *)v38
    && LODWORD(p_ppBuffer[-1].rgpProviders) == 1885431112 )
  {
    ((void (__fastcall *)(PCRYPT_PROVIDER_REF **, __int64, __int64, __int64))g_pfnFree)(
      &p_ppBuffer[-1].rgpProviders,
      v26,
      v28,
      v30);
  }
  return v11;
}

```

## disassembly

```asm
0x180014990  push    rbp
0x180014992  push    rsi
0x180014993  push    rdi
0x180014994  push    r12
0x180014996  push    r13
0x180014998  push    r14
0x18001499a  push    r15
0x18001499c  sub     rsp, 260h
0x1800149a3  lea     rbp, [rsp+40h]
0x1800149a8  mov     [rbp+250h+arg_18], rbx
0x1800149af  mov     rax, cs:__security_cookie
0x1800149b6  xor     rax, rbp
0x1800149b9  mov     [rbp+250h+var_40], rax
0x1800149c0  lea     rdi, [rbp+250h+var_240]
0x1800149c4  mov     [rbp+250h+var_248], 200h
0x1800149cb  mov     [rbp+250h+var_250], rdi
0x1800149cf  mov     ebx, r9d
0x1800149d2  mov     r12, r8
0x1800149d5  mov     r15, rdx
0x1800149d8  mov     rsi, rcx
0x1800149db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149e2  lea     rax, WPP_GLOBAL_Control
0x1800149e9  cmp     rcx, rax
0x1800149ec  jz      short loc_180014A0E
0x1800149ee  test    byte ptr [rcx+1Ch], 4
0x1800149f2  jz      short loc_180014A0E
0x1800149f4  mov     rcx, [rcx+10h]
0x1800149f8  mov     r9, rsi
0x1800149fb  mov     dword ptr [rsp+290h+pcbBuffer], ebx
0x1800149ff  mov     qword ptr [rsp+290h+dwFlags], r8
0x180014a04  mov     qword ptr [rsp+290h+dwMode], rdx
0x180014a09  call    WPP_SF_SqqD
0x180014a0e  xor     r13d, r13d
0x180014a11  mov     r14d, 70616548h
0x180014a17  test    rsi, rsi
0x180014a1a  jz      loc_180014C45
0x180014a20  cmp     [rsi], r13w
0x180014a24  jz      loc_180014C45
0x180014a2a  test    r15, r15
0x180014a2d  jz      loc_180014C45
0x180014a33  test    r12, r12
0x180014a36  jz      loc_180014C45
0x180014a3c  test    ebx, ebx
0x180014a3e  jnz     loc_180014C45
0x180014a44  mov     [r15], r13d
0x180014a47  mov     [r12], r13
0x180014a4b  lea     rax, [rbp+250h+var_250]
0x180014a4f  xor     r9d, r9d; pszProvider
0x180014a52  mov     [rsp+290h+ppBuffer], rax; ppBuffer
0x180014a57  mov     r8, rsi; pszFunction
0x180014a5a  lea     rax, [rbp+250h+var_248]
0x180014a5e  xor     edx, edx; dwInterface
0x180014a60  mov     [rsp+290h+pcbBuffer], rax; pcbBuffer
0x180014a65  xor     ecx, ecx; pszContext
0x180014a67  mov     [rsp+290h+dwFlags], 2; dwFlags
0x180014a6f  mov     [rsp+290h+dwMode], 1; dwMode
0x180014a77  call    BCryptResolveProviders
0x180014a7c  mov     ebx, eax
0x180014a7e  cmp     eax, 0C0000023h
0x180014a83  jnz     loc_180014B54
0x180014a89  mov     rax, [rbp+250h+var_250]
0x180014a8d  lea     rcx, [rbp+250h+var_240]
0x180014a91  cmp     rax, rcx
0x180014a94  jz      short loc_180014AB0
0x180014a96  test    rax, rax
0x180014a99  jz      short loc_180014AB0
0x180014a9b  lea     rcx, [rax-8]
0x180014a9f  cmp     [rcx], r14d
0x180014aa2  jnz     short loc_180014AB0
0x180014aa4  mov     rax, cs:g_pfnFree
0x180014aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab0  mov     ebx, [rbp+250h+var_248]
0x180014ab3  mov     rdi, r13
0x180014ab6  test    rbx, rbx
0x180014ab9  jz      short loc_180014B1C
0x180014abb  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180014ac2  ja      short loc_180014B1C
0x180014ac4  mov     rcx, cs:g_ulAdditionalProbeSize
0x180014acb  add     rcx, 8
0x180014acf  add     rcx, rbx
0x180014ad2  cmp     rcx, rbx
0x180014ad5  jb      short loc_180014B1C
0x180014ad7  call    VerifyStackAvailable
0x180014adc  test    eax, eax
0x180014ade  jz      short loc_180014B1C
0x180014ae0  lea     rax, [rbx+8]
0x180014ae4  lea     rcx, [rax+0Fh]
0x180014ae8  cmp     rcx, rax
0x180014aeb  ja      short loc_180014AF7
0x180014aed  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180014af7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180014afb  mov     rax, rcx
0x180014afe  call    __chkstk_0
0x180014b03  sub     rsp, rcx
0x180014b06  lea     rdi, [rsp+290h+var_250]
0x180014b0b  test    rdi, rdi
0x180014b0e  jz      short loc_180014B1C
0x180014b10  mov     dword ptr [rdi], 6B637453h
0x180014b16  add     rdi, 8
0x180014b1a  jnz     short loc_180014B40
0x180014b1c  lea     rcx, [rbx+8]
0x180014b20  cmp     rcx, rbx
0x180014b23  jb      short loc_180014B40
0x180014b25  mov     rax, cs:g_pfnAllocate
0x180014b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b31  mov     rdi, rax
0x180014b34  test    rax, rax
0x180014b37  jz      short loc_180014B40
0x180014b39  mov     [rax], r14d
0x180014b3c  add     rdi, 8
0x180014b40  mov     [rbp+250h+var_250], rdi
0x180014b44  test    rdi, rdi
0x180014b47  jnz     loc_180014A4B
0x180014b4d  mov     ebx, 0C0000017h
0x180014b52  jmp     short loc_180014B5C
0x180014b54  mov     rdi, [rbp+250h+var_250]
0x180014b58  test    eax, eax
0x180014b5a  jns     short loc_180014B69
0x180014b5c  mov     ecx, ebx
0x180014b5e  mov     r9d, 0B00h
0x180014b64  jmp     loc_180014C55
0x180014b69  mov     r8d, [rdi]
0x180014b6c  mov     r9d, r13d
0x180014b6f  test    r8d, r8d
0x180014b72  jz      short loc_180014BA2
0x180014b74  mov     r11, [rdi+8]
0x180014b78  mov     edx, r13d
0x180014b7b  mov     eax, edx
0x180014b7d  mov     rcx, [r11+rax*8]
0x180014b81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014b85  mov     r10, [rcx+10h]
0x180014b89  inc     rax
0x180014b8c  cmp     [r10+rax*2], r13w
0x180014b91  jnz     short loc_180014B89
0x180014b93  lea     r9d, [r9+rax*2]
0x180014b97  inc     edx
0x180014b99  add     r9d, 2
0x180014b9d  cmp     edx, r8d
0x180014ba0  jb      short loc_180014B7B
0x180014ba2  lea     ebx, ds:0[r8*8]
0x180014baa  lea     ecx, [rbx+r9]
0x180014bae  call    SafeAllocaAllocateFromHeap
0x180014bb3  mov     rsi, rax
0x180014bb6  test    rax, rax
0x180014bb9  jnz     short loc_180014BD0
0x180014bbb  mov     ebx, 0C0000017h
0x180014bc0  mov     ecx, 0C0000017h
0x180014bc5  mov     r9d, 0B19h
0x180014bcb  jmp     loc_180014C55
0x180014bd0  mov     eax, [rdi]
0x180014bd2  xor     r9d, r9d
0x180014bd5  mov     r14d, ebx
0x180014bd8  add     r14, rsi
0x180014bdb  test    eax, eax
0x180014bdd  jz      short loc_180014C30
0x180014bdf  mov     rax, [rdi+8]
0x180014be3  mov     edx, r13d
0x180014be6  mov     rcx, [rax+rdx*8]
0x180014bea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014bee  mov     r8, [rcx+10h]
0x180014bf2  inc     rax
0x180014bf5  cmp     [r8+rax*2], r9w
0x180014bfa  jnz     short loc_180014BF2
0x180014bfc  mov     [rsi+rdx*8], r14
0x180014c00  lea     ebx, [rax+1]
0x180014c03  mov     rax, [rdi+8]
0x180014c07  add     rbx, rbx
0x180014c0a  mov     r8, rbx; Size
0x180014c0d  mov     rcx, r14; void *
0x180014c10  mov     rdx, [rax+rdx*8]
0x180014c14  mov     rdx, [rdx+10h]; Src
0x180014c18  call    memcpy_0
0x180014c1d  mov     eax, [rdi]
0x180014c1f  add     r14, rbx
0x180014c22  inc     r13d
0x180014c25  mov     r9d, 0
0x180014c2b  cmp     r13d, eax
0x180014c2e  jb      short loc_180014BDF
0x180014c30  xor     r13d, r13d
0x180014c33  mov     [r15], eax
0x180014c36  mov     ebx, r13d
0x180014c39  mov     [r12], rsi
0x180014c3d  mov     r14d, 70616548h
0x180014c43  jmp     short loc_180014C68
0x180014c45  mov     ebx, 0C000000Dh
0x180014c4a  mov     ecx, 0C000000Dh
0x180014c4f  mov     r9d, 0AC7h
0x180014c55  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014c5c  lea     rdx, aStatus; "Status"
0x180014c63  call    DebugTraceError
0x180014c68  test    rdi, rdi
0x180014c6b  jz      short loc_180014C90
0x180014c6d  lea     rax, [rbp+250h+var_240]
0x180014c71  cmp     rdi, rax
0x180014c74  jz      short loc_180014C90
0x180014c76  test    rdi, rdi
0x180014c79  jz      short loc_180014C90
0x180014c7b  lea     rcx, [rdi-8]
0x180014c7f  cmp     [rcx], r14d
0x180014c82  jnz     short loc_180014C90
0x180014c84  mov     rax, cs:g_pfnFree
0x180014c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c90  mov     eax, ebx
0x180014c92  mov     rcx, [rbp+250h+var_40]
0x180014c99  xor     rcx, rbp; StackCookie
0x180014c9c  call    __security_check_cookie
0x180014ca1  mov     rbx, [rbp+250h+arg_18]
0x180014ca8  lea     rsp, [rbp+220h]
0x180014caf  pop     r15
0x180014cb1  pop     r14
0x180014cb3  pop     r13
0x180014cb5  pop     r12
0x180014cb7  pop     rdi
0x180014cb8  pop     rsi
0x180014cb9  pop     rbp
0x180014cba  retn
```
