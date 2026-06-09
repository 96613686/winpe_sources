# QuirksGetNextQuirkAndQuirkTagId

- ea: `0x140002a00`
- end: `0x140002d32`
- name: `QuirksGetNextQuirkAndQuirkTagId`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400021a0`

## callees

- `0x140002a00`
- `0x140002d38`
- `0x1400040e4`
- `0x14003c444`
- `0x14003d820`
- `0x14003e364`

## string_xrefs

- `0x140002cc4`: `QuirksReadData on Pdb failed: 0x%x`
- `0x140002cd3`: `QuirksReadData on StubPdb failed: 0x%x`

## pseudocode

```c
__int64 __fastcall QuirksGetNextQuirkAndQuirkTagId(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        __int64 a8,
        __int64 *a9,
        unsigned int *a10,
        __int64 *a11)
{
  __int64 v13; // rbp
  unsigned int v15; // esi
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // r8
  int Data; // eax
  const char *v20; // r9
  __int64 v21; // r8
  unsigned int v22; // edx
  unsigned int v23; // ebx
  __int64 v24; // r8
  unsigned int v25; // edx
  unsigned int v26; // ebx
  __int64 v27; // rsi
  unsigned int v29; // [rsp+78h] [rbp+10h]
  unsigned int v30; // [rsp+80h] [rbp+18h]
  unsigned int v32; // [rsp+A0h] [rbp+38h]

  v29 = a2;
  v13 = a4;
  v30 = *a3;
  if ( a7 )
    v15 = *a7;
  else
    v15 = 0;
  v32 = v15;
  if ( !*a10 )
  {
    if ( (_DWORD)a2 && !*a3 )
      *a3 = SdbFindFirstTag(a1, a2, 28715);
    if ( a6 && a7 && !*a7 )
      *a7 = SdbFindFirstTag(a5, a6, 28715);
  }
  v16 = *a9;
  if ( *a9 )
  {
    v17 = *a10;
    if ( *a10 )
    {
      if ( v16 == a1 )
      {
        v18 = *a3;
        if ( (_DWORD)v18 == v17 )
        {
          *a3 = SdbFindNextTag(a1, v29, v18);
          goto LABEL_18;
        }
        Data = -1073741811;
        v20 = "TagQuirkPdb invalid: 0x%x";
        v21 = 346;
      }
      else if ( v16 == a5 )
      {
        if ( a7 )
        {
          v24 = *a7;
          if ( (_DWORD)v24 == v17 )
          {
            *a7 = SdbFindNextTag(a5, a6, v24);
            goto LABEL_18;
          }
        }
        Data = -1073741811;
        v20 = "TagQuirkStubPdb invalid: 0x%x";
        v21 = 355;
      }
      else
      {
        Data = -1073741811;
        v20 = "CurrentPdb invalid: 0x%x";
        v21 = 363;
      }
      goto LABEL_61;
    }
  }
  while ( 1 )
  {
LABEL_18:
    v22 = *a3;
    if ( !*a3 )
    {
      if ( !a7 || !*a7 )
        return (unsigned int)-2147483622;
      goto LABEL_31;
    }
    if ( !v13 )
      break;
    if ( !a7 || !*a7 )
      goto LABEL_33;
LABEL_31:
    if ( !a8 )
    {
      v20 = "TagQuirkStubPdb or QuirkStubPdb invalid: 0x%x";
      v21 = 377;
      goto LABEL_60;
    }
    if ( v22 )
    {
LABEL_33:
      if ( v22 != v30 )
      {
        Data = QuirksReadData(a1, v22, v13);
        v23 = Data;
        if ( Data < 0 )
        {
          v20 = "QuirksReadData on Pdb failed: 0x%x";
          v21 = 390;
          goto LABEL_62;
        }
        v30 = *a3;
      }
    }
    if ( a7 )
    {
      v25 = *a7;
      if ( *a7 )
      {
        if ( v25 != v15 )
        {
          Data = QuirksReadData(a5, v25, a8);
          v23 = Data;
          if ( Data < 0 )
          {
            v20 = "QuirksReadData on StubPdb failed: 0x%x";
            v21 = 402;
            goto LABEL_62;
          }
          v32 = *a7;
        }
      }
    }
    v26 = *a3;
    if ( *a3 )
    {
      if ( !a7 || !*a7 || *(_DWORD *)(v13 + 276) <= *(_DWORD *)(a8 + 276) )
      {
        v27 = a1;
        if ( !a8 || !(unsigned int)QuirksIsEntryIdAvailableInOtherDb(a1, a5, v26) )
        {
LABEL_47:
          *a9 = v27;
          *a10 = v26;
          v23 = 0;
          *a11 = v13;
          return v23;
        }
LABEL_52:
        *a3 = SdbFindNextTag(a1, v29, *a3);
        goto LABEL_54;
      }
    }
    else if ( !a7 )
    {
      goto LABEL_58;
    }
    v26 = *a7;
    if ( !*a7 )
    {
LABEL_58:
      v20 = "Next quirk wasn't in Pdb or StubPdb: 0x%x";
      v21 = 461;
      goto LABEL_60;
    }
    v27 = a5;
    v13 = a8;
    if ( !(unsigned int)SdbFindFirstTag(a5, v26, 4120) )
      goto LABEL_47;
    if ( a5 == a1 )
      goto LABEL_52;
    *a7 = SdbFindNextTag(a5, a6, *a7);
LABEL_54:
    v13 = a4;
    v15 = v32;
  }
  v20 = "QuirkPdb invalid: 0x%x";
  v21 = 372;
LABEL_60:
  Data = -1073740768;
LABEL_61:
  v23 = Data;
LABEL_62:
  AslLogCallPrintf(1, "QuirksGetNextQuirkAndQuirkTagId", v21, v20, Data);
  return v23;
}

```

## disassembly

```asm
0x140002a00  mov     [rsp+arg_0], rbx
0x140002a05  mov     [rsp+arg_18], r9
0x140002a0a  mov     [rsp+arg_8], edx
0x140002a0e  push    rbp
0x140002a0f  push    rsi
0x140002a10  push    rdi
0x140002a11  push    r12
0x140002a13  push    r13
0x140002a15  push    r14
0x140002a17  push    r15
0x140002a19  sub     rsp, 30h
0x140002a1d  mov     rdi, [rsp+68h+arg_30]
0x140002a25  mov     r13, rcx
0x140002a28  mov     ecx, [r8]
0x140002a2b  mov     rbp, r9
0x140002a2e  mov     [rsp+68h+arg_10], ecx
0x140002a35  mov     r14, r8
0x140002a38  mov     eax, edx
0x140002a3a  test    rdi, rdi
0x140002a3d  jz      short loc_140002A43
0x140002a3f  mov     esi, [rdi]
0x140002a41  jmp     short loc_140002A45
0x140002a43  xor     esi, esi
0x140002a45  mov     r15, [rsp+68h+arg_48]
0x140002a4d  mov     r12, [rsp+68h+arg_20]
0x140002a55  mov     ebx, [rsp+68h+arg_28]
0x140002a5c  mov     dword ptr [rsp+68h+arg_30], esi
0x140002a63  cmp     dword ptr [r15], 0
0x140002a67  jnz     short loc_140002AA2
0x140002a69  test    eax, eax
0x140002a6b  jz      short loc_140002A82
0x140002a6d  test    ecx, ecx
0x140002a6f  jnz     short loc_140002A82
0x140002a71  mov     r8d, 702Bh
0x140002a77  mov     rcx, r13
0x140002a7a  call    SdbFindFirstTag
0x140002a7f  mov     [r14], eax
0x140002a82  test    ebx, ebx
0x140002a84  jz      short loc_140002AA2
0x140002a86  test    rdi, rdi
0x140002a89  jz      short loc_140002AA2
0x140002a8b  cmp     dword ptr [rdi], 0
0x140002a8e  jnz     short loc_140002AA2
0x140002a90  mov     r8d, 702Bh
0x140002a96  mov     edx, ebx
0x140002a98  mov     rcx, r12
0x140002a9b  call    SdbFindFirstTag
0x140002aa0  mov     [rdi], eax
0x140002aa2  mov     rax, [rsp+68h+arg_40]
0x140002aaa  mov     rax, [rax]
0x140002aad  test    rax, rax
0x140002ab0  jz      short loc_140002AEC
0x140002ab2  mov     ecx, [r15]
0x140002ab5  test    ecx, ecx
0x140002ab7  jz      short loc_140002AEC
0x140002ab9  cmp     rax, r13
0x140002abc  jnz     short loc_140002B0E
0x140002abe  mov     r8d, [r14]
0x140002ac1  cmp     r8d, ecx
0x140002ac4  jz      short loc_140002ADD
0x140002ac6  mov     eax, 0C000000Dh
0x140002acb  lea     r9, aTagquirkpdbInv; "TagQuirkPdb invalid: 0x%x"
0x140002ad2  mov     r8d, 15Ah
0x140002ad8  jmp     loc_140002D03
0x140002add  mov     edx, [rsp+68h+arg_8]
0x140002ae1  mov     rcx, r13
0x140002ae4  call    SdbFindNextTag
0x140002ae9  mov     [r14], eax
0x140002aec  mov     r15, [rsp+68h+arg_38]
0x140002af4  mov     edx, [r14]
0x140002af7  test    edx, edx
0x140002af9  jnz     short loc_140002B5C
0x140002afb  test    rdi, rdi
0x140002afe  jz      short loc_140002B04
0x140002b00  cmp     [rdi], edx
0x140002b02  jnz     short loc_140002B6F
0x140002b04  mov     ebx, 8000001Ah
0x140002b09  jmp     loc_140002D1A
0x140002b0e  cmp     rax, r12
0x140002b11  jnz     short loc_140002B45
0x140002b13  test    rdi, rdi
0x140002b16  jz      short loc_140002B2E
0x140002b18  mov     r8d, [rdi]
0x140002b1b  cmp     r8d, ecx
0x140002b1e  jnz     short loc_140002B2E
0x140002b20  mov     edx, ebx
0x140002b22  mov     rcx, r12
0x140002b25  call    SdbFindNextTag
0x140002b2a  mov     [rdi], eax
0x140002b2c  jmp     short loc_140002AEC
0x140002b2e  mov     eax, 0C000000Dh
0x140002b33  lea     r9, aTagquirkstubpd; "TagQuirkStubPdb invalid: 0x%x"
0x140002b3a  mov     r8d, 163h
0x140002b40  jmp     loc_140002D03
0x140002b45  mov     eax, 0C000000Dh
0x140002b4a  lea     r9, aCurrentpdbInva; "CurrentPdb invalid: 0x%x"
0x140002b51  mov     r8d, 16Bh
0x140002b57  jmp     loc_140002D03
0x140002b5c  test    rbp, rbp
0x140002b5f  jz      loc_140002CF1
0x140002b65  test    rdi, rdi
0x140002b68  jz      short loc_140002B7C
0x140002b6a  cmp     dword ptr [rdi], 0
0x140002b6d  jz      short loc_140002B7C
0x140002b6f  test    r15, r15
0x140002b72  jz      loc_140002CB5
0x140002b78  test    edx, edx
0x140002b7a  jz      short loc_140002BA4
0x140002b7c  cmp     edx, [rsp+68h+arg_10]
0x140002b83  jz      short loc_140002BA4
0x140002b85  mov     r8, rbp
0x140002b88  mov     rcx, r13
0x140002b8b  call    QuirksReadData
0x140002b90  mov     ebx, eax
0x140002b92  test    eax, eax
0x140002b94  js      loc_140002CC4
0x140002b9a  mov     eax, [r14]
0x140002b9d  mov     [rsp+68h+arg_10], eax
0x140002ba4  test    rdi, rdi
0x140002ba7  jz      short loc_140002BD1
0x140002ba9  mov     edx, [rdi]
0x140002bab  test    edx, edx
0x140002bad  jz      short loc_140002BD1
0x140002baf  cmp     edx, esi
0x140002bb1  jz      short loc_140002BD1
0x140002bb3  mov     r8, r15
0x140002bb6  mov     rcx, r12
0x140002bb9  call    QuirksReadData
0x140002bbe  mov     ebx, eax
0x140002bc0  test    eax, eax
0x140002bc2  js      loc_140002CD3
0x140002bc8  mov     eax, [rdi]
0x140002bca  mov     dword ptr [rsp+68h+arg_30], eax
0x140002bd1  mov     ebx, [r14]
0x140002bd4  test    ebx, ebx
0x140002bd6  jz      short loc_140002C47
0x140002bd8  test    rdi, rdi
0x140002bdb  jz      short loc_140002C06
0x140002bdd  cmp     dword ptr [rdi], 0
0x140002be0  jz      short loc_140002C06
0x140002be2  movzx   eax, word ptr [r15+116h]
0x140002bea  cmp     [rbp+116h], ax
0x140002bf1  jb      short loc_140002C06
0x140002bf3  jnz     short loc_140002C50
0x140002bf5  movzx   eax, word ptr [r15+114h]
0x140002bfd  cmp     [rbp+114h], ax
0x140002c04  ja      short loc_140002C50
0x140002c06  mov     rsi, r13
0x140002c09  test    r15, r15
0x140002c0c  jz      short loc_140002C20
0x140002c0e  mov     r8d, ebx
0x140002c11  mov     rdx, r12
0x140002c14  mov     rcx, r13
0x140002c17  call    QuirksIsEntryIdAvailableInOtherDb
0x140002c1c  test    eax, eax
0x140002c1e  jnz     short loc_140002C79
0x140002c20  mov     rax, [rsp+68h+arg_40]
0x140002c28  mov     [rax], rsi
0x140002c2b  mov     rax, [rsp+68h+arg_48]
0x140002c33  mov     [rax], ebx
0x140002c35  xor     ebx, ebx
0x140002c37  mov     rax, [rsp+68h+arg_50]
0x140002c3f  mov     [rax], rbp
0x140002c42  jmp     loc_140002D1A
0x140002c47  test    rdi, rdi
0x140002c4a  jz      loc_140002CE2
0x140002c50  mov     ebx, [rdi]
0x140002c52  test    ebx, ebx
0x140002c54  jz      loc_140002CE2
0x140002c5a  mov     r8d, 1018h
0x140002c60  mov     edx, ebx
0x140002c62  mov     rcx, r12
0x140002c65  mov     rsi, r12
0x140002c68  mov     rbp, r15
0x140002c6b  call    SdbFindFirstTag
0x140002c70  test    eax, eax
0x140002c72  jz      short loc_140002C20
0x140002c74  cmp     r12, r13
0x140002c77  jnz     short loc_140002C8D
0x140002c79  mov     r8d, [r14]
0x140002c7c  mov     rcx, r13
0x140002c7f  mov     edx, [rsp+68h+arg_8]
0x140002c83  call    SdbFindNextTag
0x140002c88  mov     [r14], eax
0x140002c8b  jmp     short loc_140002CA1
0x140002c8d  mov     r8d, [rdi]
0x140002c90  mov     rcx, r12
0x140002c93  mov     edx, [rsp+68h+arg_28]
0x140002c9a  call    SdbFindNextTag
0x140002c9f  mov     [rdi], eax
0x140002ca1  mov     rbp, [rsp+68h+arg_18]
0x140002ca9  mov     esi, dword ptr [rsp+68h+arg_30]
0x140002cb0  jmp     loc_140002AF4
0x140002cb5  lea     r9, aTagquirkstubpd_0; "TagQuirkStubPdb or QuirkStubPdb invalid"...
0x140002cbc  mov     r8d, 179h
0x140002cc2  jmp     short loc_140002CFE
0x140002cc4  lea     r9, aQuirksreaddata_0; "QuirksReadData on Pdb failed: 0x%x"
0x140002ccb  mov     r8d, 186h
0x140002cd1  jmp     short loc_140002D05
0x140002cd3  lea     r9, aQuirksreaddata; "QuirksReadData on StubPdb failed: 0x%x"
0x140002cda  mov     r8d, 192h
0x140002ce0  jmp     short loc_140002D05
0x140002ce2  lea     r9, aNextQuirkWasnT; "Next quirk wasn't in Pdb or StubPdb: 0x"...
0x140002ce9  mov     r8d, 1CDh
0x140002cef  jmp     short loc_140002CFE
0x140002cf1  lea     r9, aQuirkpdbInvali; "QuirkPdb invalid: 0x%x"
0x140002cf8  mov     r8d, 174h
0x140002cfe  mov     eax, 0C0000420h
0x140002d03  mov     ebx, eax
0x140002d05  lea     rdx, aQuirksgetnextq; "QuirksGetNextQuirkAndQuirkTagId"
0x140002d0c  mov     [rsp+68h+var_48], eax
0x140002d10  mov     ecx, 1
0x140002d15  call    AslLogCallPrintf
0x140002d1a  mov     eax, ebx
0x140002d1c  mov     rbx, [rsp+68h+arg_0]
0x140002d21  add     rsp, 30h
0x140002d25  pop     r15
0x140002d27  pop     r14
0x140002d29  pop     r13
0x140002d2b  pop     r12
0x140002d2d  pop     rdi
0x140002d2e  pop     rsi
0x140002d2f  pop     rbp
0x140002d30  retn
```
