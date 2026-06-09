# ExportLegacyDhKey

- ea: `0x18000f1fc`
- end: `0x18000f4b1`
- name: `ExportLegacyDhKey`
- size: `693`
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
- `0x18000f1fc`
- `0x180017828`
- `0x180017980`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x18000f24f`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000f338`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000f490`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ExportLegacyDhKey(
        __int64 (__fastcall *a1)(__int64, __int64, const wchar_t *, __int64, _DWORD, _DWORD *, _DWORD),
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8)
{
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  void *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rdx
  _DWORD v24[14]; // [rsp+40h] [rbp-38h] BYREF

  v24[0] = 0;
  if ( !a8 )
  {
    if ( !wcscmp_0(a4, L"CAPIDHPUBLICBLOB") )
    {
      v13 = a1(a2, a3, L"DHPUBLICBLOB", 0, 0, v24, 0);
      v12 = v13;
      if ( v13 )
      {
        v14 = 2542;
LABEL_8:
        v15 = v13;
LABEL_29:
        DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c", v14);
        return v12;
      }
      v16 = SafeAllocaAllocateFromHeap(v24[0]);
      v17 = (void *)v16;
      if ( !v16 )
      {
        v14 = 2550;
LABEL_11:
        v12 = -1073741801;
        v15 = 3221225495LL;
        goto LABEL_29;
      }
      v18 = a1(a2, a3, L"DHPUBLICBLOB", v16, v24[0], v24, 0);
      v12 = v18;
      if ( v18 )
      {
        v20 = 2564;
LABEL_14:
        DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c", v20);
LABEL_27:
        MSCryptFree(v17);
        return v12;
      }
      v18 = ConvertDhPublicBlobToLegacy(v17, v19, a5, a6, a7);
      v12 = v18;
      if ( v18 )
      {
        v20 = 2582;
        goto LABEL_14;
      }
    }
    else
    {
      if ( wcscmp_0(a4, L"CAPIDHPRIVATEBLOB") )
      {
        v12 = -1073741595;
        v14 = 2649;
        v15 = 3221225701LL;
        goto LABEL_29;
      }
      v13 = a1(a2, a3, L"DHPRIVATEBLOB", 0, 0, v24, 0);
      v12 = v13;
      if ( v13 )
      {
        v14 = 2602;
        goto LABEL_8;
      }
      v21 = SafeAllocaAllocateFromHeap(v24[0]);
      v17 = (void *)v21;
      if ( !v21 )
      {
        v14 = 2610;
        goto LABEL_11;
      }
      v18 = a1(a2, a3, L"DHPRIVATEBLOB", v21, v24[0], v24, 0);
      v12 = v18;
      if ( v18 )
      {
        v20 = 2624;
        goto LABEL_14;
      }
      v18 = ConvertDhPrivateBlobToLegacy(v17, v22, a5, a6, a7);
      v12 = v18;
      if ( v18 )
      {
        v20 = 2642;
        goto LABEL_14;
      }
    }
    v12 = 0;
    goto LABEL_27;
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
      218);
  return v12;
}

```

## disassembly

```asm
0x18000f1fc  push    rbx
0x18000f1fe  push    rbp
0x18000f1ff  push    rsi
0x18000f200  push    rdi
0x18000f201  push    r14
0x18000f203  sub     rsp, 50h
0x18000f207  cmp     [rsp+78h+arg_38], 0
0x18000f20f  mov     rbx, r9
0x18000f212  mov     rsi, r8
0x18000f215  mov     [rsp+78h+var_38], 0
0x18000f21d  mov     rbp, rdx
0x18000f220  mov     r14, rcx
0x18000f223  jz      short loc_18000F27C
0x18000f225  mov     ebx, 0C000000Dh
0x18000f22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f231  lea     rax, WPP_GLOBAL_Control
0x18000f238  cmp     rcx, rax
0x18000f23b  jz      loc_18000F4A3
0x18000f241  test    byte ptr [rcx+1Ch], 1
0x18000f245  jz      loc_18000F4A3
0x18000f24b  mov     rcx, [rcx+10h]
0x18000f24f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f256  mov     [rsp+78h+var_48], 9DAh
0x18000f25e  lea     r9, aStatus; "Status"
0x18000f265  mov     [rsp+78h+var_50], r8
0x18000f26a  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18000f272  call    WPP_SF_sDsd
0x18000f277  jmp     loc_18000F4A3
0x18000f27c  lea     rdx, aCapidhpublicbl; "CAPIDHPUBLICBLOB"
0x18000f283  mov     rcx, rbx; String1
0x18000f286  call    wcscmp_0
0x18000f28b  test    eax, eax
0x18000f28d  jnz     loc_18000F389
0x18000f293  mov     [rsp+78h+var_48], eax
0x18000f297  lea     r8, aDhpublicblob; "DHPUBLICBLOB"
0x18000f29e  lea     rax, [rsp+78h+var_38]
0x18000f2a3  xor     r9d, r9d
0x18000f2a6  mov     [rsp+78h+var_50], rax
0x18000f2ab  mov     rdx, rsi
0x18000f2ae  mov     rax, r14
0x18000f2b1  mov     dword ptr [rsp+78h+var_58], 0
0x18000f2b9  mov     rcx, rbp
0x18000f2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c1  mov     ebx, eax
0x18000f2c3  test    eax, eax
0x18000f2c5  jz      short loc_18000F2D4
0x18000f2c7  mov     r9d, 9EEh
0x18000f2cd  mov     ecx, eax
0x18000f2cf  jmp     loc_18000F490
0x18000f2d4  mov     ecx, [rsp+78h+var_38]
0x18000f2d8  call    SafeAllocaAllocateFromHeap
0x18000f2dd  mov     rdi, rax
0x18000f2e0  test    rax, rax
0x18000f2e3  jnz     short loc_18000F2FA
0x18000f2e5  mov     r9d, 9F6h
0x18000f2eb  mov     ebx, 0C0000017h
0x18000f2f0  mov     ecx, 0C0000017h
0x18000f2f5  jmp     loc_18000F490
0x18000f2fa  lea     rax, [rsp+78h+var_38]
0x18000f2ff  mov     [rsp+78h+var_48], 0
0x18000f307  mov     [rsp+78h+var_50], rax
0x18000f30c  lea     r8, aDhpublicblob; "DHPUBLICBLOB"
0x18000f313  mov     eax, [rsp+78h+var_38]
0x18000f317  mov     r9, rdi
0x18000f31a  mov     dword ptr [rsp+78h+var_58], eax
0x18000f31e  mov     rdx, rsi
0x18000f321  mov     rax, r14
0x18000f324  mov     rcx, rbp
0x18000f327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f32c  mov     ebx, eax
0x18000f32e  test    eax, eax
0x18000f330  jz      short loc_18000F352
0x18000f332  mov     r9d, 0A04h
0x18000f338  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f33f  mov     ecx, eax
0x18000f341  lea     rdx, aStatus; "Status"
0x18000f348  call    DebugTraceError
0x18000f34d  jmp     loc_18000F476
0x18000f352  mov     rax, [rsp+78h+arg_30]
0x18000f35a  mov     rcx, rdi
0x18000f35d  mov     r9d, [rsp+78h+arg_28]
0x18000f365  mov     r8, [rsp+78h+arg_20]
0x18000f36d  mov     [rsp+78h+var_58], rax
0x18000f372  call    ConvertDhPublicBlobToLegacy
0x18000f377  mov     ebx, eax
0x18000f379  test    eax, eax
0x18000f37b  jz      loc_18000F474
0x18000f381  mov     r9d, 0A16h
0x18000f387  jmp     short loc_18000F338
0x18000f389  lea     rdx, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x18000f390  mov     rcx, rbx; String1
0x18000f393  call    wcscmp_0
0x18000f398  test    eax, eax
0x18000f39a  jnz     loc_18000F480
0x18000f3a0  mov     [rsp+78h+var_48], eax
0x18000f3a4  lea     r8, aDhprivateblob; "DHPRIVATEBLOB"
0x18000f3ab  lea     rax, [rsp+78h+var_38]
0x18000f3b0  xor     r9d, r9d
0x18000f3b3  mov     [rsp+78h+var_50], rax
0x18000f3b8  mov     rdx, rsi
0x18000f3bb  mov     rax, r14
0x18000f3be  mov     dword ptr [rsp+78h+var_58], 0
0x18000f3c6  mov     rcx, rbp
0x18000f3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3ce  mov     ebx, eax
0x18000f3d0  test    eax, eax
0x18000f3d2  jz      short loc_18000F3DF
0x18000f3d4  mov     r9d, 0A2Ah
0x18000f3da  jmp     loc_18000F2CD
0x18000f3df  mov     ecx, [rsp+78h+var_38]
0x18000f3e3  call    SafeAllocaAllocateFromHeap
0x18000f3e8  mov     rdi, rax
0x18000f3eb  test    rax, rax
0x18000f3ee  jnz     short loc_18000F3FB
0x18000f3f0  mov     r9d, 0A32h
0x18000f3f6  jmp     loc_18000F2EB
0x18000f3fb  lea     rax, [rsp+78h+var_38]
0x18000f400  mov     [rsp+78h+var_48], 0
0x18000f408  mov     [rsp+78h+var_50], rax
0x18000f40d  lea     r8, aDhprivateblob; "DHPRIVATEBLOB"
0x18000f414  mov     eax, [rsp+78h+var_38]
0x18000f418  mov     r9, rdi
0x18000f41b  mov     dword ptr [rsp+78h+var_58], eax
0x18000f41f  mov     rdx, rsi
0x18000f422  mov     rax, r14
0x18000f425  mov     rcx, rbp
0x18000f428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f42d  mov     ebx, eax
0x18000f42f  test    eax, eax
0x18000f431  jz      short loc_18000F43E
0x18000f433  mov     r9d, 0A40h
0x18000f439  jmp     loc_18000F338
0x18000f43e  mov     rax, [rsp+78h+arg_30]
0x18000f446  mov     rcx, rdi
0x18000f449  mov     r9d, [rsp+78h+arg_28]
0x18000f451  mov     r8, [rsp+78h+arg_20]
0x18000f459  mov     [rsp+78h+var_58], rax
0x18000f45e  call    ConvertDhPrivateBlobToLegacy
0x18000f463  mov     ebx, eax
0x18000f465  test    eax, eax
0x18000f467  jz      short loc_18000F474
0x18000f469  mov     r9d, 0A52h
0x18000f46f  jmp     loc_18000F338
0x18000f474  xor     ebx, ebx
0x18000f476  mov     rcx, rdi
0x18000f479  call    MSCryptFree
0x18000f47e  jmp     short loc_18000F4A3
0x18000f480  mov     ebx, 0C00000E5h
0x18000f485  mov     r9d, 0A59h
0x18000f48b  mov     ecx, 0C00000E5h
0x18000f490  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f497  lea     rdx, aStatus; "Status"
0x18000f49e  call    DebugTraceError
0x18000f4a3  mov     eax, ebx
0x18000f4a5  add     rsp, 50h
0x18000f4a9  pop     r14
0x18000f4ab  pop     rdi
0x18000f4ac  pop     rsi
0x18000f4ad  pop     rbp
0x18000f4ae  pop     rbx
0x18000f4af  retn
```
