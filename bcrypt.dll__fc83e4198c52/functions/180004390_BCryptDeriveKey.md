# BCryptDeriveKey

- ea: `0x180004390`
- end: `0x18000463f`
- name: `BCryptDeriveKey`
- size: `687`
- prototype: `NTSTATUS __stdcall(BCRYPT_SECRET_HANDLE hSharedSecret, LPCWSTR pwszKDF, BCryptBufferDesc *pParameterList, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004390`
- `0x180004648`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000b680`
- `0x1800154e0`
- `0x18001c010`

## string_xrefs

- `0x1800044b6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004505`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000454f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004586`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800045f8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKey(
        BCRYPT_SECRET_HANDLE hSharedSecret,
        LPCWSTR pwszKDF,
        BCryptBufferDesc *pParameterList,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  BCryptBufferDesc *v7; // rbx
  _QWORD *v12; // r10
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // r8d
  __int64 v16; // r10
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 (__fastcall *v19)(_QWORD, LPCWSTR, BCryptBufferDesc *, PUCHAR, ULONG, ULONG *, ULONG); // r14
  int v20; // eax
  NTSTATUS v21; // esi
  int v23; // edx
  int v24; // r8d
  PBCryptBuffer pBuffers; // rcx
  BCryptBufferDesc *v26; // [rsp+50h] [rbp-38h] BYREF

  v7 = 0;
  v26 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qSqqDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)pParameterList,
      (_DWORD)hSharedSecret,
      (__int64)pwszKDF,
      (char)pParameterList,
      (char)pbDerivedKey,
      cbDerivedKey,
      (char)pcbResult,
      dwFlags);
    v12 = WPP_GLOBAL_Control;
  }
  if ( pcbResult )
  {
    v13 = ValidateBaseSecretHandle(hSharedSecret);
    v17 = v13;
    if ( v13 )
    {
      v18 = *(_QWORD *)(v13 + 8);
      if ( *(_DWORD *)(v18 + 36) == 4 )
      {
        v19 = *(__int64 (__fastcall **)(_QWORD, LPCWSTR, BCryptBufferDesc *, PUCHAR, ULONG, ULONG *, ULONG))(v18 + 96);
        if ( pParameterList )
        {
          v21 = ProcessBufferDescParameters(pParameterList, &v26);
          if ( v21 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v23,
                v24,
                (unsigned int)"Status",
                v21,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
                14);
            v7 = v26;
            goto LABEL_10;
          }
          v7 = v26;
        }
        v20 = v19(*(_QWORD *)(v17 + 16), pwszKDF, v7, pbDerivedKey, cbDerivedKey, pcbResult, dwFlags);
        v21 = v20;
        if ( v20 < 0 )
          DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5404);
LABEL_10:
        if ( v7 && pParameterList != v7 )
        {
          pBuffers = v7->pBuffers;
          if ( pBuffers )
            MSCryptFree(pBuffers);
          MSCryptFree(v7);
        }
        return v21;
      }
      v21 = -1073741637;
      if ( v16 != v14 && (*(_BYTE *)(v16 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v16 + 16),
          v14,
          v15,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          2);
    }
    else
    {
      v21 = -1073741816;
      if ( v16 != v14 && (*(_BYTE *)(v16 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v16 + 16),
          v14,
          v15,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          244);
    }
  }
  else
  {
    v21 = -1073741811;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v12[2],
        (unsigned int)&WPP_GLOBAL_Control,
        (_DWORD)pParameterList,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        236);
  }
  return v21;
}

```

## disassembly

```asm
0x180004390  mov     [rsp+arg_8], rbx
0x180004395  mov     [rsp+arg_10], rbp
0x18000439a  push    rsi
0x18000439b  push    rdi
0x18000439c  push    r12
0x18000439e  push    r13
0x1800043a0  push    r15
0x1800043a2  sub     rsp, 60h
0x1800043a6  xor     ebx, ebx
0x1800043a8  mov     r12, r9
0x1800043ab  mov     [rsp+88h+var_38], rbx
0x1800043b0  mov     r15, r8
0x1800043b3  mov     r13, rdx
0x1800043b6  mov     rdi, rcx
0x1800043b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800043c0  lea     rdx, WPP_GLOBAL_Control
0x1800043c7  mov     rbp, [rsp+88h+pcbResult]
0x1800043cf  cmp     r10, rdx
0x1800043d2  jz      short loc_1800043DF
0x1800043d4  test    byte ptr [r10+1Ch], 4
0x1800043d9  jnz     loc_18000459F
0x1800043df  test    rbp, rbp
0x1800043e2  jz      loc_1800044E4
0x1800043e8  mov     rcx, rdi
0x1800043eb  call    ValidateBaseSecretHandle
0x1800043f0  mov     rdi, rax
0x1800043f3  test    rax, rax
0x1800043f6  jz      loc_180004565
0x1800043fc  mov     rax, [rax+8]
0x180004400  cmp     dword ptr [rax+24h], 4
0x180004404  jnz     loc_18000452E
0x18000440a  mov     [rsp+88h+arg_0], r14
0x180004412  mov     r14, [rax+60h]
0x180004416  test    r15, r15
0x180004419  jnz     short loc_180004482
0x18000441b  mov     eax, [rsp+88h+dwFlags]
0x180004422  mov     r9, r12
0x180004425  mov     rcx, [rdi+10h]
0x180004429  mov     r8, rbx
0x18000442c  mov     dword ptr [rsp+88h+var_58], eax
0x180004430  mov     rdx, r13
0x180004433  mov     eax, [rsp+88h+cbDerivedKey]
0x18000443a  mov     [rsp+88h+var_60], rbp
0x18000443f  mov     dword ptr [rsp+88h+var_68], eax
0x180004443  mov     rax, r14
0x180004446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444b  mov     esi, eax
0x18000444d  test    eax, eax
0x18000444f  js      loc_1800045F2
0x180004455  mov     r14, [rsp+88h+arg_0]
0x18000445d  test    rbx, rbx
0x180004460  jnz     loc_180004612
0x180004466  lea     r11, [rsp+88h+var_28]
0x18000446b  mov     eax, esi
0x18000446d  mov     rbx, [r11+38h]
0x180004471  mov     rbp, [r11+40h]
0x180004475  mov     rsp, r11
0x180004478  pop     r15
0x18000447a  pop     r13
0x18000447c  pop     r12
0x18000447e  pop     rdi
0x18000447f  pop     rsi
0x180004480  retn
0x180004482  lea     rdx, [rsp+88h+var_38]
0x180004487  mov     rcx, r15
0x18000448a  call    _ProcessBufferDescParameters
0x18000448f  mov     esi, eax
0x180004491  test    eax, eax
0x180004493  jz      loc_1800045E8
0x180004499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a0  lea     rax, WPP_GLOBAL_Control
0x1800044a7  cmp     rcx, rax
0x1800044aa  jz      short loc_1800044DA
0x1800044ac  test    byte ptr [rcx+1Ch], 1
0x1800044b0  jz      short loc_1800044DA
0x1800044b2  mov     rcx, [rcx+10h]
0x1800044b6  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800044bd  mov     dword ptr [rsp+88h+var_58], 150Eh
0x1800044c5  lea     r9, aStatus; "Status"
0x1800044cc  mov     [rsp+88h+var_60], rax
0x1800044d1  mov     dword ptr [rsp+88h+var_68], esi
0x1800044d5  call    WPP_SF_sDsd
0x1800044da  mov     rbx, [rsp+88h+var_38]
0x1800044df  jmp     loc_180004455
0x1800044e4  mov     esi, 0C000000Dh
0x1800044e9  cmp     r10, rdx
0x1800044ec  jz      loc_180004466
0x1800044f2  test    byte ptr [r10+1Ch], 1
0x1800044f7  jz      loc_180004466
0x1800044fd  mov     dword ptr [rsp+88h+var_58], 14ECh
0x180004505  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000450c  mov     [rsp+88h+var_60], rax
0x180004511  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180004519  mov     rcx, [r10+10h]
0x18000451d  lea     r9, aStatus; "Status"
0x180004524  call    WPP_SF_sDsd
0x180004529  jmp     loc_180004466
0x18000452e  mov     esi, 0C00000BBh
0x180004533  cmp     r10, rdx
0x180004536  jz      loc_180004466
0x18000453c  test    byte ptr [r10+1Ch], 1
0x180004541  jz      loc_180004466
0x180004547  mov     dword ptr [rsp+88h+var_58], 1502h
0x18000454f  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004556  mov     [rsp+88h+var_60], rax
0x18000455b  mov     dword ptr [rsp+88h+var_68], 0C00000BBh
0x180004563  jmp     short loc_180004519
0x180004565  mov     esi, 0C0000008h
0x18000456a  cmp     r10, rdx
0x18000456d  jz      loc_180004466
0x180004573  test    byte ptr [r10+1Ch], 1
0x180004578  jz      loc_180004466
0x18000457e  mov     dword ptr [rsp+88h+var_58], 14F4h
0x180004586  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000458d  mov     [rsp+88h+var_60], rax
0x180004592  mov     dword ptr [rsp+88h+var_68], 0C0000008h
0x18000459a  jmp     loc_180004519
0x18000459f  mov     eax, [rsp+88h+dwFlags]
0x1800045a6  mov     r9, rdi
0x1800045a9  mov     rcx, [r10+10h]
0x1800045ad  mov     [rsp+88h+var_40], eax
0x1800045b1  mov     eax, [rsp+88h+cbDerivedKey]
0x1800045b8  mov     [rsp+88h+var_48], rbp
0x1800045bd  mov     [rsp+88h+var_50], eax
0x1800045c1  mov     [rsp+88h+var_58], r12
0x1800045c6  mov     [rsp+88h+var_60], r15
0x1800045cb  mov     [rsp+88h+var_68], r13
0x1800045d0  call    WPP_SF_qSqqDqD
0x1800045d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800045dc  lea     rdx, WPP_GLOBAL_Control
0x1800045e3  jmp     loc_1800043DF
0x1800045e8  mov     rbx, [rsp+88h+var_38]
0x1800045ed  jmp     loc_18000441B
0x1800045f2  mov     r9d, 151Ch
0x1800045f8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800045ff  lea     rdx, aStatus; "Status"
0x180004606  mov     ecx, eax
0x180004608  call    DebugTraceError
0x18000460d  jmp     loc_180004455
0x180004612  cmp     r15, rbx
0x180004615  jz      loc_180004466
0x18000461b  test    rbx, rbx
0x18000461e  jz      loc_180004466
0x180004624  mov     rcx, [rbx+8]
0x180004628  test    rcx, rcx
0x18000462b  jz      short loc_180004632
0x18000462d  call    MSCryptFree
0x180004632  mov     rcx, rbx
0x180004635  call    MSCryptFree
0x18000463a  jmp     loc_180004466
```
