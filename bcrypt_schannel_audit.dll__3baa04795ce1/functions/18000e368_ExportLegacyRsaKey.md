# ExportLegacyRsaKey

- ea: `0x18000e368`
- end: `0x18000e61f`
- name: `ExportLegacyRsaKey`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180009ba0`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000b824`
- `0x18000e368`
- `0x180018460`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x18000e3bb`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000e4a2`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000e5fe`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ExportLegacyRsaKey(
        __int64 (__fastcall *a1)(__int64, __int64, const wchar_t *, __int64, int, int *, _DWORD),
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  _DWORD *v16; // rdi
  unsigned int v17; // eax
  int v18; // edx
  __int64 v19; // rax
  int v21[14]; // [rsp+40h] [rbp-38h] BYREF

  v21[0] = 0;
  if ( !a8 )
  {
    if ( !wcscmp_0(a4, L"CAPIPUBLICBLOB") )
    {
      v13 = a1(a2, a3, L"RSAPUBLICBLOB", 0, 0, v21, 0);
      v12 = v13;
      if ( v13 )
      {
LABEL_7:
        v14 = v13;
LABEL_22:
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
        return v12;
      }
      v15 = SafeAllocaAllocateFromHeap((unsigned int)v21[0]);
      v16 = (_DWORD *)v15;
      if ( !v15 )
      {
LABEL_9:
        v12 = -1073741801;
        v14 = 3221225495LL;
        goto LABEL_22;
      }
      v17 = a1(a2, a3, L"RSAPUBLICBLOB", v15, v21[0], v21, 0);
      v12 = v17;
      if ( v17 )
        goto LABEL_11;
      v17 = ConvertRsaPublicBlobToLegacy((_DWORD)v16, v18, a5, a6, (__int64)a7);
      v12 = v17;
      if ( v17 )
        goto LABEL_11;
    }
    else
    {
      if ( wcscmp_0(a4, L"CAPIPRIVATEBLOB") )
      {
        v12 = -1073741595;
        v14 = 3221225701LL;
        goto LABEL_22;
      }
      v13 = a1(a2, a3, L"RSAPRIVATEBLOB", 0, 0, v21, 0);
      v12 = v13;
      if ( v13 )
        goto LABEL_7;
      v19 = SafeAllocaAllocateFromHeap((unsigned int)v21[0]);
      v16 = (_DWORD *)v19;
      if ( !v19 )
        goto LABEL_9;
      v17 = a1(a2, a3, L"RSAPRIVATEBLOB", v19, v21[0], v21, 0);
      v12 = v17;
      if ( v17 || (v17 = ConvertRsaPrivateBlobToLegacy(v16, v21[0], a5, a6, a7), (v12 = v17) != 0) )
      {
LABEL_11:
        DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
LABEL_20:
        MSCryptFree(v16);
        return v12;
      }
    }
    v12 = 0;
    goto LABEL_20;
  }
  v12 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      99);
  return v12;
}

```

## disassembly

```asm
0x18000e368  push    rbx
0x18000e36a  push    rbp
0x18000e36b  push    rsi
0x18000e36c  push    rdi
0x18000e36d  push    r14
0x18000e36f  sub     rsp, 50h
0x18000e373  cmp     [rsp+78h+arg_38], 0
0x18000e37b  mov     rbx, r9
0x18000e37e  mov     rsi, r8
0x18000e381  mov     [rsp+78h+var_38], 0
0x18000e389  mov     rbp, rdx
0x18000e38c  mov     r14, rcx
0x18000e38f  jz      short loc_18000E3E8
0x18000e391  mov     ebx, 0C000000Dh
0x18000e396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e39d  lea     rax, WPP_GLOBAL_Control
0x18000e3a4  cmp     rcx, rax
0x18000e3a7  jz      loc_18000E611
0x18000e3ad  test    byte ptr [rcx+1Ch], 1
0x18000e3b1  jz      loc_18000E611
0x18000e3b7  mov     rcx, [rcx+10h]
0x18000e3bb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e3c2  mov     [rsp+78h+var_48], 63h ; 'c'
0x18000e3ca  lea     r9, aStatus; "Status"
0x18000e3d1  mov     [rsp+78h+var_50], r8
0x18000e3d6  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18000e3de  call    WPP_SF_sDsd
0x18000e3e3  jmp     loc_18000E611
0x18000e3e8  lea     rdx, aCapipublicblob; "CAPIPUBLICBLOB"
0x18000e3ef  mov     rcx, rbx; String1
0x18000e3f2  call    wcscmp_0
0x18000e3f7  test    eax, eax
0x18000e3f9  jnz     loc_18000E4F3
0x18000e3ff  mov     [rsp+78h+var_48], eax
0x18000e403  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18000e40a  lea     rax, [rsp+78h+var_38]
0x18000e40f  xor     r9d, r9d
0x18000e412  mov     [rsp+78h+var_50], rax
0x18000e417  mov     rdx, rsi
0x18000e41a  mov     rax, r14
0x18000e41d  mov     dword ptr [rsp+78h+var_58], 0
0x18000e425  mov     rcx, rbp
0x18000e428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42d  mov     ebx, eax
0x18000e42f  test    eax, eax
0x18000e431  jz      short loc_18000E440
0x18000e433  mov     r9d, 77h ; 'w'
0x18000e439  mov     ecx, eax
0x18000e43b  jmp     loc_18000E5FE
0x18000e440  mov     ecx, [rsp+78h+var_38]
0x18000e444  call    SafeAllocaAllocateFromHeap
0x18000e449  mov     rdi, rax
0x18000e44c  test    rax, rax
0x18000e44f  jnz     short loc_18000E464
0x18000e451  lea     r9d, [rax+7Fh]
0x18000e455  mov     ebx, 0C0000017h
0x18000e45a  mov     ecx, 0C0000017h
0x18000e45f  jmp     loc_18000E5FE
0x18000e464  lea     rax, [rsp+78h+var_38]
0x18000e469  mov     [rsp+78h+var_48], 0
0x18000e471  mov     [rsp+78h+var_50], rax
0x18000e476  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18000e47d  mov     eax, [rsp+78h+var_38]
0x18000e481  mov     r9, rdi
0x18000e484  mov     dword ptr [rsp+78h+var_58], eax
0x18000e488  mov     rdx, rsi
0x18000e48b  mov     rax, r14
0x18000e48e  mov     rcx, rbp
0x18000e491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e496  mov     ebx, eax
0x18000e498  test    eax, eax
0x18000e49a  jz      short loc_18000E4BC
0x18000e49c  mov     r9d, 8Dh
0x18000e4a2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e4a9  mov     ecx, eax
0x18000e4ab  lea     rdx, aStatus; "Status"
0x18000e4b2  call    DebugTraceError
0x18000e4b7  jmp     loc_18000E5E4
0x18000e4bc  mov     rax, [rsp+78h+arg_30]
0x18000e4c4  mov     rcx, rdi
0x18000e4c7  mov     r9d, [rsp+78h+arg_28]
0x18000e4cf  mov     r8, [rsp+78h+arg_20]
0x18000e4d7  mov     [rsp+78h+var_58], rax
0x18000e4dc  call    ConvertRsaPublicBlobToLegacy
0x18000e4e1  mov     ebx, eax
0x18000e4e3  test    eax, eax
0x18000e4e5  jz      loc_18000E5E2
0x18000e4eb  mov     r9d, 0A0h
0x18000e4f1  jmp     short loc_18000E4A2
0x18000e4f3  lea     rdx, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x18000e4fa  mov     rcx, rbx; String1
0x18000e4fd  call    wcscmp_0
0x18000e502  test    eax, eax
0x18000e504  jnz     loc_18000E5EE
0x18000e50a  mov     [rsp+78h+var_48], eax
0x18000e50e  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18000e515  lea     rax, [rsp+78h+var_38]
0x18000e51a  xor     r9d, r9d
0x18000e51d  mov     [rsp+78h+var_50], rax
0x18000e522  mov     rdx, rsi
0x18000e525  mov     rax, r14
0x18000e528  mov     dword ptr [rsp+78h+var_58], 0
0x18000e530  mov     rcx, rbp
0x18000e533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e538  mov     ebx, eax
0x18000e53a  test    eax, eax
0x18000e53c  jz      short loc_18000E549
0x18000e53e  mov     r9d, 0B4h
0x18000e544  jmp     loc_18000E439
0x18000e549  mov     ecx, [rsp+78h+var_38]
0x18000e54d  call    SafeAllocaAllocateFromHeap
0x18000e552  mov     rdi, rax
0x18000e555  test    rax, rax
0x18000e558  jnz     short loc_18000E565
0x18000e55a  mov     r9d, 0BCh
0x18000e560  jmp     loc_18000E455
0x18000e565  lea     rax, [rsp+78h+var_38]
0x18000e56a  mov     [rsp+78h+var_48], 0
0x18000e572  mov     [rsp+78h+var_50], rax
0x18000e577  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18000e57e  mov     eax, [rsp+78h+var_38]
0x18000e582  mov     r9, rdi
0x18000e585  mov     dword ptr [rsp+78h+var_58], eax
0x18000e589  mov     rdx, rsi
0x18000e58c  mov     rax, r14
0x18000e58f  mov     rcx, rbp
0x18000e592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e597  mov     ebx, eax
0x18000e599  test    eax, eax
0x18000e59b  jz      short loc_18000E5A8
0x18000e59d  mov     r9d, 0CAh
0x18000e5a3  jmp     loc_18000E4A2
0x18000e5a8  mov     rax, [rsp+78h+arg_30]
0x18000e5b0  mov     rcx, rdi
0x18000e5b3  mov     r9d, [rsp+78h+arg_28]
0x18000e5bb  mov     r8, [rsp+78h+arg_20]
0x18000e5c3  mov     edx, [rsp+78h+var_38]
0x18000e5c7  mov     [rsp+78h+var_58], rax
0x18000e5cc  call    ConvertRsaPrivateBlobToLegacy
0x18000e5d1  mov     ebx, eax
0x18000e5d3  test    eax, eax
0x18000e5d5  jz      short loc_18000E5E2
0x18000e5d7  mov     r9d, 0DDh
0x18000e5dd  jmp     loc_18000E4A2
0x18000e5e2  xor     ebx, ebx
0x18000e5e4  mov     rcx, rdi
0x18000e5e7  call    MSCryptFree
0x18000e5ec  jmp     short loc_18000E611
0x18000e5ee  mov     ebx, 0C00000E5h
0x18000e5f3  mov     r9d, 0E4h
0x18000e5f9  mov     ecx, 0C00000E5h
0x18000e5fe  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e605  lea     rdx, aStatus; "Status"
0x18000e60c  call    DebugTraceError
0x18000e611  mov     eax, ebx
0x18000e613  add     rsp, 50h
0x18000e617  pop     r14
0x18000e619  pop     rdi
0x18000e61a  pop     rsi
0x18000e61b  pop     rbp
0x18000e61c  pop     rbx
0x18000e61d  retn
```
