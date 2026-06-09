# VsmLoadInterface

- ea: `0x18001a61c`
- end: `0x18001a991`
- name: `VsmLoadInterface`
- size: `885`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014f98`

## callees

- `0x180005060`
- `0x18000b094`
- `0x18001a3cc`
- `0x18001a554`
- `0x18001a61c`
- `0x18001aa70`
- `0x18001c010`

## string_xrefs

- `0x18001a68b`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18001a6a9`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall VsmLoadInterface(unsigned int a1, __int64 a2, unsigned int a3, _OWORD *a4)
{
  char TrustedEnvironment; // al
  HMODULE v5; // r13
  int LinkedInterfaceProvider; // eax
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  int v18; // ebx
  __int64 v19; // r9
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  _OWORD *v24; // rax
  __int64 v25; // rdx
  __int128 v26; // xmm1
  _OWORD *v28; // [rsp+30h] [rbp-28h] BYREF
  __int64 (__fastcall *v29)(const WCHAR *, __int64, _OWORD **, _QWORD); // [rsp+38h] [rbp-20h] BYREF
  HMODULE v30; // [rsp+40h] [rbp-18h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  v5 = 0;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 0x18) != 0 )
  {
    LinkedInterfaceProvider = VsmGetLinkedInterfaceProvider(a1, &v29);
  }
  else
  {
    LinkedInterfaceProvider = VsmGetInterfaceProviderFromLibrary(a1, (FARPROC *)&v29, &v30);
    v5 = v30;
  }
  v11 = LinkedInterfaceProvider;
  if ( LinkedInterfaceProvider < 0 )
  {
    v12 = 2348;
    v13 = (unsigned int)LinkedInterfaceProvider;
LABEL_8:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v12);
    goto LABEL_50;
  }
  if ( a1 > 6 )
  {
    v20 = a1 - 7;
    if ( !v20 )
    {
      v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2117;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2130;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    v22 = v21 - 65529;
    if ( !v22 )
    {
      v18 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v29)(L"Microsoft Primitive Provider", &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2142;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v18 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v29)(L"Microsoft Primitive Provider", &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2166;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    if ( v23 == 2 )
    {
      v18 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v29)(L"Microsoft Primitive Provider", &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2154;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
    goto LABEL_33;
  }
  if ( a1 == 6 )
  {
    v18 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v29)(L"Microsoft Primitive Provider", &v28, a3);
    if ( v18 < 0 )
    {
      v19 = 2104;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  v14 = a1 - 1;
  if ( !v14 )
  {
    v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
    if ( v18 < 0 )
    {
      v19 = 2040;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
    if ( v18 < 0 )
    {
      v19 = 2053;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
    if ( v18 < 0 )
    {
      v19 = 2066;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 == 1 )
    {
      v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
      if ( v18 < 0 )
      {
        v19 = 2092;
LABEL_44:
        DebugTraceError(
          (unsigned int)v18,
          "ntStatus",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          v19);
        v11 = v18;
        goto LABEL_46;
      }
      goto LABEL_45;
    }
LABEL_33:
    v11 = -1073741637;
    v18 = -1073741637;
    DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 2172);
LABEL_46:
    v12 = 2361;
    v13 = (unsigned int)v18;
    goto LABEL_8;
  }
  v18 = v29(L"Microsoft Primitive Provider", a2, &v28, a3);
  if ( v18 < 0 )
  {
    v19 = 2079;
    goto LABEL_44;
  }
LABEL_45:
  v11 = v18;
  v24 = v28;
  v25 = 3;
  do
  {
    *a4 = *v24;
    a4[1] = v24[1];
    a4[2] = v24[2];
    a4[3] = v24[3];
    a4[4] = v24[4];
    a4[5] = v24[5];
    a4[6] = v24[6];
    v26 = v24[7];
    v24 += 8;
    a4[7] = v26;
    a4 += 8;
    --v25;
  }
  while ( v25 );
  *(_QWORD *)a4 = *(_QWORD *)v24;
LABEL_50:
  if ( v5 )
    FreeImage(v5);
  return v11;
}

```

## disassembly

```asm
0x18001a61c  push    rbp
0x18001a61e  push    rbx
0x18001a61f  push    rsi
0x18001a620  push    rdi
0x18001a621  push    r12
0x18001a623  push    r13
0x18001a625  push    r14
0x18001a627  push    r15
0x18001a629  mov     rbp, rsp
0x18001a62c  sub     rsp, 58h
0x18001a630  mov     eax, cs:g_TrustedEnvironment
0x18001a636  xor     r13d, r13d
0x18001a639  mov     [rbp+var_20], 0
0x18001a641  mov     r15, r9
0x18001a644  mov     [rbp+var_28], 0
0x18001a64c  mov     r14d, r8d
0x18001a64f  mov     [rbp+var_18], r13
0x18001a653  mov     r12, rdx
0x18001a656  mov     ebx, ecx
0x18001a658  test    eax, eax
0x18001a65a  jnz     short loc_18001A661
0x18001a65c  call    GetTrustedEnvironment
0x18001a661  lea     rdx, [rbp+var_20]
0x18001a665  mov     ecx, ebx
0x18001a667  test    al, 18h
0x18001a669  jz      short loc_18001A672
0x18001a66b  call    VsmGetLinkedInterfaceProvider
0x18001a670  jmp     short loc_18001A67F
0x18001a672  lea     r8, [rbp+var_18]
0x18001a676  call    VsmGetInterfaceProviderFromLibrary
0x18001a67b  mov     r13, [rbp+var_18]
0x18001a67f  mov     edi, eax
0x18001a681  test    eax, eax
0x18001a683  jns     short loc_18001A6A5
0x18001a685  mov     r9d, 92Ch
0x18001a68b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a692  mov     ecx, eax
0x18001a694  lea     rdx, aStatus; "Status"
0x18001a69b  call    DebugTraceError
0x18001a6a0  jmp     loc_18001A970
0x18001a6a5  mov     rax, [rbp+var_20]
0x18001a6a9  lea     rsi, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a6b0  cmp     ebx, 6
0x18001a6b3  ja      loc_18001A7E3
0x18001a6b9  jz      loc_18001A7BB
0x18001a6bf  sub     ebx, 1
0x18001a6c2  jz      loc_18001A790
0x18001a6c8  sub     ebx, 1
0x18001a6cb  jz      loc_18001A765
0x18001a6d1  sub     ebx, 1
0x18001a6d4  jz      short loc_18001A73A
0x18001a6d6  sub     ebx, 1
0x18001a6d9  jz      short loc_18001A70F
0x18001a6db  cmp     ebx, 1
0x18001a6de  jnz     loc_18001A807
0x18001a6e4  mov     r9d, r14d
0x18001a6e7  lea     r8, [rbp+var_28]
0x18001a6eb  mov     rdx, r12
0x18001a6ee  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6fa  mov     ebx, eax
0x18001a6fc  test    eax, eax
0x18001a6fe  jns     loc_18001A8F6
0x18001a704  mov     r9d, 82Ch
0x18001a70a  jmp     loc_18001A8E1
0x18001a70f  mov     r9d, r14d
0x18001a712  lea     r8, [rbp+var_28]
0x18001a716  mov     rdx, r12
0x18001a719  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a725  mov     ebx, eax
0x18001a727  test    eax, eax
0x18001a729  jns     loc_18001A8F6
0x18001a72f  mov     r9d, 81Fh
0x18001a735  jmp     loc_18001A8E1
0x18001a73a  mov     r9d, r14d
0x18001a73d  lea     r8, [rbp+var_28]
0x18001a741  mov     rdx, r12
0x18001a744  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a750  mov     ebx, eax
0x18001a752  test    eax, eax
0x18001a754  jns     loc_18001A8F6
0x18001a75a  mov     r9d, 812h
0x18001a760  jmp     loc_18001A8E1
0x18001a765  mov     r9d, r14d
0x18001a768  lea     r8, [rbp+var_28]
0x18001a76c  mov     rdx, r12
0x18001a76f  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a77b  mov     ebx, eax
0x18001a77d  test    eax, eax
0x18001a77f  jns     loc_18001A8F6
0x18001a785  mov     r9d, 805h
0x18001a78b  jmp     loc_18001A8E1
0x18001a790  mov     r9d, r14d
0x18001a793  lea     r8, [rbp+var_28]
0x18001a797  mov     rdx, r12
0x18001a79a  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a6  mov     ebx, eax
0x18001a7a8  test    eax, eax
0x18001a7aa  jns     loc_18001A8F6
0x18001a7b0  mov     r9d, 7F8h
0x18001a7b6  jmp     loc_18001A8E1
0x18001a7bb  mov     r8d, r14d
0x18001a7be  lea     rdx, [rbp+var_28]
0x18001a7c2  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ce  mov     ebx, eax
0x18001a7d0  test    eax, eax
0x18001a7d2  jns     loc_18001A8F6
0x18001a7d8  mov     r9d, 838h
0x18001a7de  jmp     loc_18001A8E1
0x18001a7e3  sub     ebx, 7
0x18001a7e6  jz      loc_18001A8BF
0x18001a7ec  sub     ebx, 1
0x18001a7ef  jz      loc_18001A89B
0x18001a7f5  sub     ebx, 0FFF9h
0x18001a7fb  jz      short loc_18001A87A
0x18001a7fd  sub     ebx, 1
0x18001a800  jz      short loc_18001A855
0x18001a802  cmp     ebx, 2
0x18001a805  jz      short loc_18001A82D
0x18001a807  mov     edi, 0C00000BBh
0x18001a80c  lea     rdx, aNtstatus; "ntStatus"
0x18001a813  mov     r9d, 87Ch
0x18001a819  mov     r8, rsi
0x18001a81c  mov     ecx, 0C00000BBh
0x18001a821  mov     ebx, edi
0x18001a823  call    DebugTraceError
0x18001a828  jmp     loc_18001A8FC
0x18001a82d  mov     r8d, r14d
0x18001a830  lea     rdx, [rbp+var_28]
0x18001a834  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a840  mov     ebx, eax
0x18001a842  test    eax, eax
0x18001a844  jns     loc_18001A8F6
0x18001a84a  mov     r9d, 86Ah
0x18001a850  jmp     loc_18001A8E1
0x18001a855  mov     r8d, r14d
0x18001a858  lea     rdx, [rbp+var_28]
0x18001a85c  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a868  mov     ebx, eax
0x18001a86a  test    eax, eax
0x18001a86c  jns     loc_18001A8F6
0x18001a872  mov     r9d, 876h
0x18001a878  jmp     short loc_18001A8E1
0x18001a87a  mov     r8d, r14d
0x18001a87d  lea     rdx, [rbp+var_28]
0x18001a881  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a88d  mov     ebx, eax
0x18001a88f  test    eax, eax
0x18001a891  jns     short loc_18001A8F6
0x18001a893  mov     r9d, 85Eh
0x18001a899  jmp     short loc_18001A8E1
0x18001a89b  mov     r9d, r14d
0x18001a89e  lea     r8, [rbp+var_28]
0x18001a8a2  mov     rdx, r12
0x18001a8a5  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b1  mov     ebx, eax
0x18001a8b3  test    eax, eax
0x18001a8b5  jns     short loc_18001A8F6
0x18001a8b7  mov     r9d, 852h
0x18001a8bd  jmp     short loc_18001A8E1
0x18001a8bf  mov     r9d, r14d
0x18001a8c2  lea     r8, [rbp+var_28]
0x18001a8c6  mov     rdx, r12
0x18001a8c9  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18001a8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d5  mov     ebx, eax
0x18001a8d7  test    eax, eax
0x18001a8d9  jns     short loc_18001A8F6
0x18001a8db  mov     r9d, 845h
0x18001a8e1  mov     r8, rsi
0x18001a8e4  lea     rdx, aNtstatus; "ntStatus"
0x18001a8eb  mov     ecx, ebx
0x18001a8ed  call    DebugTraceError
0x18001a8f2  mov     edi, ebx
0x18001a8f4  jmp     short loc_18001A8FC
0x18001a8f6  mov     edi, ebx
0x18001a8f8  test    ebx, ebx
0x18001a8fa  jns     short loc_18001A90C
0x18001a8fc  mov     r9d, 939h
0x18001a902  mov     r8, rsi
0x18001a905  mov     ecx, ebx
0x18001a907  jmp     loc_18001A694
0x18001a90c  mov     rax, [rbp+var_28]
0x18001a910  mov     edx, 3
0x18001a915  lea     ecx, [rdx+7Dh]
0x18001a918  movups  xmm0, xmmword ptr [rax]
0x18001a91b  movups  xmmword ptr [r15], xmm0
0x18001a91f  movups  xmm1, xmmword ptr [rax+10h]
0x18001a923  movups  xmmword ptr [r15+10h], xmm1
0x18001a928  movups  xmm0, xmmword ptr [rax+20h]
0x18001a92c  movups  xmmword ptr [r15+20h], xmm0
0x18001a931  movups  xmm1, xmmword ptr [rax+30h]
0x18001a935  movups  xmmword ptr [r15+30h], xmm1
0x18001a93a  movups  xmm0, xmmword ptr [rax+40h]
0x18001a93e  movups  xmmword ptr [r15+40h], xmm0
0x18001a943  movups  xmm1, xmmword ptr [rax+50h]
0x18001a947  movups  xmmword ptr [r15+50h], xmm1
0x18001a94c  movups  xmm0, xmmword ptr [rax+60h]
0x18001a950  movups  xmmword ptr [r15+60h], xmm0
0x18001a955  movups  xmm1, xmmword ptr [rax+70h]
0x18001a959  add     rax, rcx
0x18001a95c  movups  xmmword ptr [r15+70h], xmm1
0x18001a961  add     r15, rcx
0x18001a964  sub     rdx, 1
0x18001a968  jnz     short loc_18001A918
0x18001a96a  mov     rax, [rax]
0x18001a96d  mov     [r15], rax
0x18001a970  test    r13, r13
0x18001a973  jz      short loc_18001A97D
0x18001a975  mov     rcx, r13
0x18001a978  call    _FreeImage
0x18001a97d  mov     eax, edi
0x18001a97f  add     rsp, 58h
0x18001a983  pop     r15
0x18001a985  pop     r14
0x18001a987  pop     r13
0x18001a989  pop     r12
0x18001a98b  pop     rdi
0x18001a98c  pop     rsi
0x18001a98d  pop     rbx
0x18001a98e  pop     rbp
0x18001a98f  retn
```
