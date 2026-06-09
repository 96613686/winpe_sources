# CreateVsmKeyAttestationClaim(void *,void *,ulong,_BCryptrBufferDesc *,uchar *,ulong,ulong *,ulong,ulong)

- ea: `0x140012ee8`
- end: `0x14001311c`
- name: `?CreateVsmKeyAttestationClaim@@YAJPEAX0KPEAU_BCryptrBufferDesc@@PEAEKPEAKKK@Z`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, int, struct _BCryptrBufferDesc *, unsigned __int8 *, SIZE_T, unsigned int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000e510`

## callees

- `0x14001212c`
- `0x1400123a4`
- `0x140012be0`
- `0x140012d24`
- `0x140012ee8`
- `0x140013124`
- `0x140013700`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400130fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400130fb`

## string_xrefs

- `0x1400130eb`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`
- `0x140012f49`: `CreateVsmKeyAttestationClaim`

## pseudocode

```c
__int64 __fastcall CreateVsmKeyAttestationClaim(
        _QWORD *a1,
        _QWORD *a2,
        int a3,
        struct _BCryptrBufferDesc *a4,
        unsigned __int8 *a5,
        SIZE_T a6,
        unsigned int *a7,
        unsigned int a8,
        unsigned int a9)
{
  unsigned int *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // r8
  int RootClaimBufferParams; // eax
  unsigned int v16; // ebx
  unsigned __int8 *v17; // rsi
  int v18; // edi
  bool v19; // cl
  int VsmKeyAttestationRootClaim; // eax
  HLOCAL *p_hMem; // rdx
  SIZE_T uBytes; // [rsp+28h] [rbp-48h]
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v25[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v26; // [rsp+68h] [rbp-8h]
  unsigned int v28; // [rsp+A8h] [rbp+38h] BYREF

  v26 = 0;
  hMem = 0;
  v28 = 0;
  memset(v25, 0, sizeof(v25));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids,
      "CreateVsmKeyAttestationClaim");
  v12 = a7;
  *a7 = 0;
  if ( a2 )
  {
    if ( (a9 & 0x20) == 0 || (a9 & 0x7FFFFFDB) != 0 )
    {
      v13 = 2148073483LL;
      v14 = 1403;
      goto LABEL_40;
    }
    if ( ((*(_DWORD *)(a2[1] + 36LL) - 3) & 0xFFFFFFFD) != 0 )
    {
      v13 = 2148073483LL;
      v14 = 1412;
LABEL_40:
      v16 = v13;
      goto LABEL_41;
    }
  }
  if ( (a8 & 0xFFFFFFE0) != 0 )
  {
    v14 = 1421;
LABEL_39:
    v13 = 3221225485LL;
    goto LABEL_40;
  }
  if ( a3 == 5 )
    RootClaimBufferParams = BCryptIumGetRootClaimBufferParams(a4, v25);
  else
    RootClaimBufferParams = BCryptIumGetIdentityClaimBufferParams(a4, v25);
  v16 = RootClaimBufferParams;
  if ( RootClaimBufferParams < 0 )
  {
    v14 = 1431;
LABEL_17:
    v13 = v16;
LABEL_41:
    VBS_ATTEST_TRACE_ERROR_IN(
      v13,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v14);
    goto LABEL_42;
  }
  if ( (unsigned int)(*(_DWORD *)(a1[1] + 36LL) - 3) > 2 )
  {
    v16 = -1073741637;
    v14 = 1441;
    goto LABEL_17;
  }
  v17 = a5;
  v18 = a6;
  v19 = !a5 || !(_DWORD)a6;
  if ( a3 == 5 )
  {
    VsmKeyAttestationRootClaim = BCryptIumBuildClaimAttributes(a1, &hMem, &v28, a8);
    v16 = VsmKeyAttestationRootClaim;
    if ( VsmKeyAttestationRootClaim < 0 )
    {
      v14 = 1457;
LABEL_27:
      v13 = (unsigned int)VsmKeyAttestationRootClaim;
      goto LABEL_41;
    }
    VsmKeyAttestationRootClaim = CreateVsmKeyAttestationRootClaim(v25, hMem, v28, v17, v18, v12);
    v16 = VsmKeyAttestationRootClaim;
    if ( VsmKeyAttestationRootClaim < 0 )
    {
      v14 = 1469;
      goto LABEL_27;
    }
  }
  else
  {
    if ( a3 != 6 )
    {
      v14 = 1504;
      goto LABEL_39;
    }
    p_hMem = &hMem;
    if ( v19 )
      p_hMem = 0;
    VsmKeyAttestationRootClaim = BCryptIumBuildClaimAttributes(a1, p_hMem, &v28, a8);
    v16 = VsmKeyAttestationRootClaim;
    if ( VsmKeyAttestationRootClaim < 0 )
    {
      v14 = 1483;
      goto LABEL_27;
    }
    LODWORD(uBytes) = v18;
    VsmKeyAttestationRootClaim = CreateVsmKeyAttestationIdentityClaim(a2, (__int64)v17, uBytes, (__int64)v12);
    v16 = VsmKeyAttestationRootClaim;
    if ( VsmKeyAttestationRootClaim < 0 )
    {
      v14 = 1496;
      goto LABEL_27;
    }
  }
  v16 = 0;
LABEL_42:
  LocalFree(hMem);
  return v16;
}

```

## disassembly

```asm
0x140012ee8  mov     [rsp-28h+arg_10], rbx
0x140012eed  mov     [rsp-28h+arg_18], rsi
0x140012ef2  mov     [rsp-28h+arg_0], rcx
0x140012ef7  push    rbp
0x140012ef8  push    rdi
0x140012ef9  push    r13
0x140012efb  push    r14
0x140012efd  push    r15
0x140012eff  mov     rbp, rsp
0x140012f02  sub     rsp, 70h
0x140012f06  xor     eax, eax
0x140012f08  xorps   xmm0, xmm0
0x140012f0b  xor     edi, edi
0x140012f0d  mov     [rbp+var_8], rax
0x140012f11  mov     [rbp+hMem], rdi
0x140012f15  mov     rbx, r9
0x140012f18  mov     [rbp+arg_8], edi
0x140012f1b  mov     r15d, r8d
0x140012f1e  mov     r13, rdx
0x140012f21  movups  [rbp+var_28], xmm0
0x140012f25  movups  [rbp+var_18], xmm0
0x140012f29  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f30  lea     rax, WPP_GLOBAL_Control
0x140012f37  cmp     rcx, rax
0x140012f3a  jz      short loc_140012F5C
0x140012f3c  test    byte ptr [rcx+1Ch], 4
0x140012f40  jz      short loc_140012F5C
0x140012f42  mov     rcx, [rcx+10h]
0x140012f46  lea     edx, [rdi+0Dh]
0x140012f49  lea     r9, aCreatevsmkeyat_0; "CreateVsmKeyAttestationClaim"
0x140012f50  lea     r8, WPP_9b7bb3a056503060c4cc3cbe91885dc2_Traceguids
0x140012f57  call    WPP_SF_s
0x140012f5c  mov     r14, [rbp+arg_30]
0x140012f60  mov     [r14], edi
0x140012f63  test    r13, r13
0x140012f66  jz      short loc_140012FA9
0x140012f68  test    byte ptr [rbp+arg_40], 20h
0x140012f6c  jz      short loc_140012F99
0x140012f6e  test    [rbp+arg_40], 7FFFFFDBh
0x140012f75  jnz     short loc_140012F99
0x140012f77  mov     rax, [r13+8]
0x140012f7b  mov     ecx, [rax+24h]
0x140012f7e  sub     ecx, 3
0x140012f81  test    ecx, 0FFFFFFFDh
0x140012f87  jz      short loc_140012FA9
0x140012f89  mov     ecx, 8009000Bh
0x140012f8e  mov     r8d, 584h
0x140012f94  jmp     loc_1400130E9
0x140012f99  mov     ecx, 8009000Bh
0x140012f9e  mov     r8d, 57Bh
0x140012fa4  jmp     loc_1400130E9
0x140012fa9  test    [rbp+arg_38], 0FFFFFFE0h
0x140012fb0  jz      short loc_140012FBD
0x140012fb2  mov     r8d, 58Dh
0x140012fb8  jmp     loc_1400130E4
0x140012fbd  lea     rdx, [rbp+var_28]
0x140012fc1  mov     rcx, rbx
0x140012fc4  cmp     r15d, 5
0x140012fc8  jnz     short loc_140012FD1
0x140012fca  call    BCryptIumGetRootClaimBufferParams
0x140012fcf  jmp     short loc_140012FD6
0x140012fd1  call    BCryptIumGetIdentityClaimBufferParams
0x140012fd6  mov     ebx, eax
0x140012fd8  test    eax, eax
0x140012fda  jns     short loc_140012FE9
0x140012fdc  mov     r8d, 597h
0x140012fe2  mov     ecx, ebx
0x140012fe4  jmp     loc_1400130EB
0x140012fe9  mov     r10, [rbp+arg_0]
0x140012fed  mov     rax, [r10+8]
0x140012ff1  mov     ecx, [rax+24h]
0x140012ff4  sub     ecx, 3
0x140012ff7  cmp     ecx, 2
0x140012ffa  jbe     short loc_140013009
0x140012ffc  mov     ebx, 0C00000BBh
0x140013001  mov     r8d, 5A1h
0x140013007  jmp     short loc_140012FE2
0x140013009  mov     rsi, [rbp+arg_20]
0x14001300d  mov     edi, dword ptr [rbp+arg_28]
0x140013010  test    rsi, rsi
0x140013013  jz      short loc_14001301D
0x140013015  test    edi, edi
0x140013017  jz      short loc_14001301D
0x140013019  xor     cl, cl
0x14001301b  jmp     short loc_14001301F
0x14001301d  mov     cl, 1
0x14001301f  cmp     r15d, 5
0x140013023  jnz     short loc_140013077
0x140013025  mov     r9d, [rbp+arg_38]
0x140013029  lea     r8, [rbp+arg_8]
0x14001302d  lea     rdx, [rbp+hMem]
0x140013031  mov     rcx, r10
0x140013034  call    BCryptIumBuildClaimAttributes
0x140013039  mov     ebx, eax
0x14001303b  test    eax, eax
0x14001303d  jns     short loc_14001304C
0x14001303f  mov     r8d, 5B1h
0x140013045  mov     ecx, eax
0x140013047  jmp     loc_1400130EB
0x14001304c  mov     r8d, [rbp+arg_8]
0x140013050  lea     rcx, [rbp+var_28]
0x140013054  mov     rdx, [rbp+hMem]
0x140013058  mov     r9, rsi
0x14001305b  mov     [rsp+70h+uBytes], r14
0x140013060  mov     dword ptr [rsp+70h+var_50], edi
0x140013064  call    CreateVsmKeyAttestationRootClaim
0x140013069  mov     ebx, eax
0x14001306b  test    eax, eax
0x14001306d  jns     short loc_1400130DA
0x14001306f  mov     r8d, 5BDh
0x140013075  jmp     short loc_140013045
0x140013077  cmp     r15d, 6
0x14001307b  jnz     short loc_1400130DE
0x14001307d  mov     r9d, [rbp+arg_38]
0x140013081  lea     rdx, [rbp+hMem]
0x140013085  xor     eax, eax
0x140013087  lea     r8, [rbp+arg_8]
0x14001308b  test    cl, cl
0x14001308d  mov     rcx, r10
0x140013090  cmovnz  rdx, rax
0x140013094  call    BCryptIumBuildClaimAttributes
0x140013099  mov     ebx, eax
0x14001309b  test    eax, eax
0x14001309d  jns     short loc_1400130A7
0x14001309f  mov     r8d, 5CBh
0x1400130a5  jmp     short loc_140013045
0x1400130a7  mov     r9d, [rbp+arg_8]
0x1400130ab  lea     rdx, [rbp+var_28]
0x1400130af  mov     r8, [rbp+hMem]
0x1400130b3  mov     rcx, r13; hKey
0x1400130b6  mov     [rsp+70h+var_40], r14; __int64
0x1400130bb  mov     dword ptr [rsp+70h+uBytes], edi; uBytes
0x1400130bf  mov     [rsp+70h+var_50], rsi; __int64
0x1400130c4  call    CreateVsmKeyAttestationIdentityClaim
0x1400130c9  mov     ebx, eax
0x1400130cb  test    eax, eax
0x1400130cd  jns     short loc_1400130DA
0x1400130cf  mov     r8d, 5D8h
0x1400130d5  jmp     loc_140013045
0x1400130da  xor     ebx, ebx
0x1400130dc  jmp     short loc_1400130F7
0x1400130de  mov     r8d, 5E0h
0x1400130e4  mov     ecx, 0C000000Dh
0x1400130e9  mov     ebx, ecx
0x1400130eb  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400130f2  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400130f7  mov     rcx, [rbp+hMem]; hMem
0x1400130fb  call    cs:__imp_LocalFree
0x140013101  lea     r11, [rsp+70h+var_s0]
0x140013106  mov     eax, ebx
0x140013108  mov     rbx, [r11+40h]
0x14001310c  mov     rsi, [r11+48h]
0x140013110  mov     rsp, r11
0x140013113  pop     r15
0x140013115  pop     r14
0x140013117  pop     r13
0x140013119  pop     rdi
0x14001311a  pop     rbp
0x14001311b  retn
```
