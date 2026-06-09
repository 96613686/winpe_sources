# I_BCryptPrimitiveHash

- ea: `0x180016af4`
- end: `0x180016d1f`
- name: `I_BCryptPrimitiveHash`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18007e5c8`
- `0x18007e870`

## callees

- `0x18000ecb0`
- `0x18000ed00`
- `0x18000ee60`
- `0x180013b70`
- `0x180016af4`
- `0x180017240`
- `0x1800173f0`
- `0x18006319c`
- `0x18006cfdc`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x180016c09`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`
- `0x180016c7e`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall I_BCryptPrimitiveHash(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  unsigned int v7; // r15d
  int *v8; // rbx
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  int *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  int MultiHash; // eax
  __int64 v20; // r9
  int v21; // eax
  __int64 v23; // [rsp+0h] [rbp-40h] BYREF
  size_t Size; // [rsp+30h] [rbp-10h]
  int v25[2]; // [rsp+40h] [rbp+0h] BYREF
  __int64 v26[2]; // [rsp+48h] [rbp+8h] BYREF

  v7 = 0;
  v8 = 0;
  v26[0] = a1;
  *(_QWORD *)v25 = 0;
  v12 = *(unsigned int *)(a5 + 8);
  if ( *(_DWORD *)(a5 + 8)
    && v12 <= g_ulMaxStackAllocSize
    && v12 + g_ulAdditionalProbeSize + 8 >= v12
    && (unsigned int)VerifyStackAvailable() )
  {
    v13 = v12 + 23;
    if ( v12 + 23 <= v12 + 8 )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
    v15 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
    v8 = v25;
    if ( &v23 != (__int64 *)-64LL )
    {
      v25[0] = 1801679955;
      v8 = (int *)v26;
      if ( v26 )
        goto LABEL_13;
    }
  }
  if ( v12 + 8 >= v12 )
  {
    v16 = (int *)((__int64 (*)(void))g_pfnAllocate)();
    v8 = v16;
    if ( !v16 )
      goto LABEL_27;
    *v16 = 1885431112;
    v8 = v16 + 2;
  }
  if ( v8 )
  {
LABEL_13:
    v17 = *(_DWORD *)(a5 + 8);
    v18 = *(_QWORD *)a5;
    LODWORD(Size) = 0;
    MultiHash = MSCryptCreateMultiHash(v18, (__int64 *)v25, 0, (__int64)v8, v17, 0, Size, 0);
    if ( MultiHash < 0 )
    {
      v20 = 306;
LABEL_15:
      DebugTraceError((unsigned int)MultiHash, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", v20);
      goto LABEL_27;
    }
    MultiHash = MSCryptHashData(*(__int64 *)v25, v26[0], a2, 0);
    if ( MultiHash < 0 )
    {
      v20 = 318;
      goto LABEL_15;
    }
    if ( a3 && a4 && (v21 = MSCryptHashData(*(__int64 *)v25, a3, a4, 0), v21 < 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c",
          (unsigned int)"Status",
          v21,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c",
          76);
    }
    else
    {
      MultiHash = MSCryptFinishHash(*(_QWORD *)v25, a6, a7, 0);
      if ( MultiHash < 0 )
      {
        v20 = 345;
        goto LABEL_15;
      }
      v7 = 1;
    }
  }
LABEL_27:
  if ( *(_QWORD *)v25 )
    MSCryptDestroyHash();
  if ( v8 && *(v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v7;
}

```

## disassembly

```asm
0x180016af4  push    rbp
0x180016af6  push    rbx
0x180016af7  push    rsi
0x180016af8  push    rdi
0x180016af9  push    r12
0x180016afb  push    r13
0x180016afd  push    r14
0x180016aff  push    r15
0x180016b01  sub     rsp, 68h
0x180016b05  lea     rbp, [rsp+40h]
0x180016b0a  mov     rax, cs:__security_cookie
0x180016b11  xor     rax, rbp
0x180016b14  mov     [rbp+60h+var_48], rax
0x180016b18  mov     r12, [rbp+60h+arg_20]
0x180016b1f  xor     r15d, r15d
0x180016b22  xor     ebx, ebx
0x180016b24  mov     [rbp+60h+var_58], rcx
0x180016b28  mov     esi, r9d
0x180016b2b  mov     qword ptr [rbp+60h+var_60], r15
0x180016b2f  mov     r14, r8
0x180016b32  mov     r13d, edx
0x180016b35  mov     edi, [r12+8]
0x180016b3a  test    rdi, rdi
0x180016b3d  jz      short loc_180016BA0
0x180016b3f  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180016b46  ja      short loc_180016BA0
0x180016b48  mov     rcx, cs:g_ulAdditionalProbeSize
0x180016b4f  add     rcx, 8
0x180016b53  add     rcx, rdi
0x180016b56  cmp     rcx, rdi
0x180016b59  jb      short loc_180016BA0
0x180016b5b  call    VerifyStackAvailable
0x180016b60  test    eax, eax
0x180016b62  jz      short loc_180016BA0
0x180016b64  lea     rax, [rdi+8]
0x180016b68  lea     rcx, [rax+0Fh]
0x180016b6c  cmp     rcx, rax
0x180016b6f  ja      short loc_180016B7B
0x180016b71  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180016b7b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180016b7f  mov     rax, rcx
0x180016b82  call    __chkstk_0
0x180016b87  sub     rsp, rcx
0x180016b8a  lea     rbx, [rsp+0A0h+var_60]
0x180016b8f  test    rbx, rbx
0x180016b92  jz      short loc_180016BA0
0x180016b94  mov     dword ptr [rbx], 6B637453h
0x180016b9a  add     rbx, 8
0x180016b9e  jnz     short loc_180016BD4
0x180016ba0  lea     rcx, [rdi+8]
0x180016ba4  cmp     rcx, rdi
0x180016ba7  jb      short loc_180016BCB
0x180016ba9  mov     rax, cs:g_pfnAllocate
0x180016bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bb5  mov     rbx, rax
0x180016bb8  test    rax, rax
0x180016bbb  jz      loc_180016CD3
0x180016bc1  mov     dword ptr [rax], 70616548h
0x180016bc7  add     rbx, 8
0x180016bcb  test    rbx, rbx
0x180016bce  jz      loc_180016CD3
0x180016bd4  mov     eax, [r12+8]
0x180016bd9  lea     rdx, [rbp+60h+var_60]; int
0x180016bdd  mov     rcx, [r12]; int
0x180016be1  mov     r9, rbx; int
0x180016be4  mov     [rsp+0A0h+var_68], r15d; int
0x180016be9  xor     r8d, r8d; int
0x180016bec  mov     dword ptr [rsp+0A0h+Size], r15d; Size
0x180016bf1  mov     [rsp+0A0h+Src], r15; Src
0x180016bf6  mov     [rsp+0A0h+var_80], eax; int
0x180016bfa  call    MSCryptCreateMultiHash
0x180016bff  test    eax, eax
0x180016c01  jns     short loc_180016C23
0x180016c03  mov     r9d, 132h
0x180016c09  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016c10  mov     ecx, eax
0x180016c12  lea     rdx, aStatus; "Status"
0x180016c19  call    DebugTraceError
0x180016c1e  jmp     loc_180016CD3
0x180016c23  mov     rdx, [rbp+60h+var_58]
0x180016c27  xor     r9d, r9d
0x180016c2a  mov     rcx, qword ptr [rbp+60h+var_60]
0x180016c2e  mov     r8d, r13d
0x180016c31  call    MSCryptHashData
0x180016c36  test    eax, eax
0x180016c38  jns     short loc_180016C42
0x180016c3a  mov     r9d, 13Eh
0x180016c40  jmp     short loc_180016C09
0x180016c42  test    r14, r14
0x180016c45  jz      short loc_180016CA4
0x180016c47  test    esi, esi
0x180016c49  jz      short loc_180016CA4
0x180016c4b  mov     rcx, qword ptr [rbp+60h+var_60]
0x180016c4f  xor     r9d, r9d
0x180016c52  mov     r8d, esi
0x180016c55  mov     rdx, r14
0x180016c58  call    MSCryptHashData
0x180016c5d  test    eax, eax
0x180016c5f  jns     short loc_180016CA4
0x180016c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c68  lea     rdx, WPP_GLOBAL_Control
0x180016c6f  cmp     rcx, rdx
0x180016c72  jz      short loc_180016CD3
0x180016c74  test    byte ptr [rcx+1Ch], 1
0x180016c78  jz      short loc_180016CD3
0x180016c7a  mov     rcx, [rcx+10h]
0x180016c7e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016c85  mov     dword ptr [rsp+0A0h+Size], 14Ch
0x180016c8d  lea     r9, aStatus; "Status"
0x180016c94  mov     [rsp+0A0h+Src], r8
0x180016c99  mov     [rsp+0A0h+var_80], eax
0x180016c9d  call    WPP_SF_sDsd
0x180016ca2  jmp     short loc_180016CD3
0x180016ca4  mov     r8d, [rbp+60h+arg_30]
0x180016cab  xor     r9d, r9d
0x180016cae  mov     rdx, [rbp+60h+arg_28]
0x180016cb5  mov     rcx, qword ptr [rbp+60h+var_60]
0x180016cb9  call    MSCryptFinishHash
0x180016cbe  test    eax, eax
0x180016cc0  jns     short loc_180016CCD
0x180016cc2  mov     r9d, 159h
0x180016cc8  jmp     loc_180016C09
0x180016ccd  mov     r15d, 1
0x180016cd3  mov     rcx, qword ptr [rbp+60h+var_60]
0x180016cd7  test    rcx, rcx
0x180016cda  jz      short loc_180016CE1
0x180016cdc  call    MSCryptDestroyHash
0x180016ce1  test    rbx, rbx
0x180016ce4  jz      short loc_180016CFE
0x180016ce6  lea     rcx, [rbx-8]
0x180016cea  cmp     dword ptr [rcx], 70616548h
0x180016cf0  jnz     short loc_180016CFE
0x180016cf2  mov     rax, cs:g_pfnFree
0x180016cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cfe  mov     eax, r15d
0x180016d01  mov     rcx, [rbp+60h+var_48]
0x180016d05  xor     rcx, rbp; StackCookie
0x180016d08  call    __security_check_cookie
0x180016d0d  lea     rsp, [rbp+28h]
0x180016d11  pop     r15
0x180016d13  pop     r14
0x180016d15  pop     r13
0x180016d17  pop     r12
0x180016d19  pop     rdi
0x180016d1a  pop     rsi
0x180016d1b  pop     rbx
0x180016d1c  pop     rbp
0x180016d1d  retn
```
