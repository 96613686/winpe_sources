# OpenSystemPreferredAlgorithmProvider

- ea: `0x18000466c`
- end: `0x1800047f7`
- name: `OpenSystemPreferredAlgorithmProvider`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004800`
- `0x18000e2c4`

## callees

- `0x1800030a0`
- `0x18000466c`
- `0x180005b00`
- `0x1800070d0`
- `0x180007a7c`
- `0x18000d8e0`

## string_xrefs

- `0x180004771`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x1800047b4`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall OpenSystemPreferredAlgorithmProvider(BCRYPT_ALG_HANDLE *a1)
{
  PCRYPT_PROVIDER_REFS v1; // rbx
  const WCHAR *pszFunction; // rdx
  int v4; // edx
  NTSTATUS v5; // edi
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+80h] [rbp+30h] BYREF
  ULONG pcbBuffer; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  phAlgorithm = 0;
  ppBuffer = 0;
  pcbBuffer = 0;
  if ( !g_fLoadCNGDone )
    goto LABEL_2;
  v5 = BCryptResolveProviders(0, 6u, 0, 0, 1u, 0, &pcbBuffer, &ppBuffer);
  if ( v5 >= 0 )
  {
    v1 = ppBuffer;
    if ( !ppBuffer->cProviders )
    {
      v5 = -1073741595;
      goto LABEL_9;
    }
    if ( g_fLoadCNGDone )
    {
      pszFunction = (*ppBuffer->rgpProviders)->pszFunction;
LABEL_7:
      v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, pszFunction, 0, 0);
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v7,
            v8,
            (unsigned int)"Status",
            v5,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
            136);
      }
      else
      {
        v5 = 0;
        *a1 = phAlgorithm;
        phAlgorithm = 0;
      }
      goto LABEL_9;
    }
LABEL_2:
    pszFunction = L"RNG";
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v6,
      (unsigned int)"Status",
      v5,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
      109);
  v1 = ppBuffer;
LABEL_9:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v1 )
    BCryptFreeBuffer(v1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000466c  mov     [rsp-18h+arg_0], rbx
0x180004671  mov     [rsp-18h+arg_18], r9d
0x180004676  mov     [rsp-18h+arg_10], r8
0x18000467b  push    rbp
0x18000467c  push    rsi
0x18000467d  push    rdi
0x18000467e  mov     rbp, rsp
0x180004681  sub     rsp, 50h
0x180004685  xor     ebx, ebx
0x180004687  mov     [rbp+phAlgorithm], 0
0x18000468f  cmp     cs:g_fLoadCNGDone, ebx
0x180004695  mov     rsi, rcx
0x180004698  mov     [rbp+arg_10], rbx
0x18000469c  mov     [rbp+arg_18], ebx
0x18000469f  jnz     short loc_1800046AA
0x1800046a1  lea     rdx, aRng; "RNG"
0x1800046a8  jmp     short loc_180004704
0x1800046aa  lea     rax, [rbp+arg_10]
0x1800046ae  xor     r9d, r9d; pszProvider
0x1800046b1  mov     [rsp+50h+ppBuffer], rax; ppBuffer
0x1800046b6  xor     r8d, r8d; pszFunction
0x1800046b9  lea     rax, [rbp+arg_18]
0x1800046bd  xor     ecx, ecx; pszContext
0x1800046bf  mov     [rsp+50h+pcbBuffer], rax; pcbBuffer
0x1800046c4  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x1800046c8  lea     edx, [r9+6]; dwInterface
0x1800046cc  mov     [rsp+50h+dwMode], 1; dwMode
0x1800046d4  call    BCryptResolveProviders
0x1800046d9  mov     edi, eax
0x1800046db  test    eax, eax
0x1800046dd  js      loc_180004797
0x1800046e3  mov     rbx, [rbp+arg_10]
0x1800046e7  cmp     dword ptr [rbx], 1
0x1800046ea  jb      loc_1800047E1
0x1800046f0  cmp     cs:g_fLoadCNGDone, 0
0x1800046f7  jz      short loc_1800046A1
0x1800046f9  mov     rax, [rbx+8]
0x1800046fd  mov     rcx, [rax]
0x180004700  mov     rdx, [rcx+8]; pszAlgId
0x180004704  xor     r9d, r9d; dwFlags
0x180004707  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000470b  xor     r8d, r8d; pszImplementation
0x18000470e  call    BCryptOpenAlgorithmProvider
0x180004713  mov     edi, eax
0x180004715  test    eax, eax
0x180004717  js      short loc_180004754
0x180004719  mov     rax, [rbp+phAlgorithm]
0x18000471d  xor     edi, edi
0x18000471f  mov     [rsi], rax
0x180004722  mov     [rbp+phAlgorithm], 0
0x18000472a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000472e  test    rcx, rcx
0x180004731  jnz     loc_1800047EB
0x180004737  test    rbx, rbx
0x18000473a  jz      short loc_180004744
0x18000473c  mov     rcx, rbx; pvBuffer
0x18000473f  call    BCryptFreeBuffer
0x180004744  mov     rbx, [rsp+50h+arg_0]
0x180004749  mov     eax, edi
0x18000474b  add     rsp, 50h
0x18000474f  pop     rdi
0x180004750  pop     rsi
0x180004751  pop     rbp
0x180004752  retn
0x180004754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000475b  lea     rax, WPP_GLOBAL_Control
0x180004762  cmp     rcx, rax
0x180004765  jz      short loc_18000472A
0x180004767  test    byte ptr [rcx+1Ch], 1
0x18000476b  jz      short loc_18000472A
0x18000476d  mov     rcx, [rcx+10h]
0x180004771  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004778  mov     dword ptr [rsp+50h+pcbBuffer], 188h
0x180004780  lea     r9, aStatus; "Status"
0x180004787  mov     qword ptr [rsp+50h+dwFlags], rax
0x18000478c  mov     [rsp+50h+dwMode], edi
0x180004790  call    WPP_SF_sDsd
0x180004795  jmp     short loc_18000472A
0x180004797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000479e  lea     rax, WPP_GLOBAL_Control
0x1800047a5  cmp     rcx, rax
0x1800047a8  jz      short loc_1800047D8
0x1800047aa  test    byte ptr [rcx+1Ch], 1
0x1800047ae  jz      short loc_1800047D8
0x1800047b0  mov     rcx, [rcx+10h]
0x1800047b4  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800047bb  mov     dword ptr [rsp+50h+pcbBuffer], 16Dh
0x1800047c3  lea     r9, aStatus; "Status"
0x1800047ca  mov     qword ptr [rsp+50h+dwFlags], rax
0x1800047cf  mov     [rsp+50h+dwMode], edi
0x1800047d3  call    WPP_SF_sDsd
0x1800047d8  mov     rbx, [rbp+arg_10]
0x1800047dc  jmp     loc_18000472A
0x1800047e1  mov     edi, 0C00000E5h
0x1800047e6  jmp     loc_18000472A
0x1800047eb  xor     edx, edx; dwFlags
0x1800047ed  call    BCryptCloseAlgorithmProvider
0x1800047f2  jmp     loc_180004737
```
