# PCreateDLFont

- ea: `0x1800104a8`
- end: `0x1800107d3`
- name: `PCreateDLFont`
- size: `811`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b9a4`
- `0x18000ee40`

## callees

- `0x180010240`
- `0x1800104a8`
- `0x180010934`
- `0x18001112c`
- `0x1800111b0`
- `0x18001135c`
- `0x180029348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180010770`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180010770`
- `KERNEL32!LocalFree` at `0x180010662`
- `KERNEL32!LocalFree` at `0x1800107ac`
- `KERNEL32!LocalFree` at `0x1800107b5`
- `KERNEL32!LocalFree` at `0x180010662`
- `KERNEL32!LocalFree` at `0x1800107ac`
- `KERNEL32!LocalFree` at `0x1800107b5`
- `KERNEL32!LocalAlloc` at `0x1800104ff`
- `KERNEL32!LocalAlloc` at `0x180010628`
- `KERNEL32!LocalAlloc` at `0x18001074e`
- `KERNEL32!LocalAlloc` at `0x1800104ff`
- `KERNEL32!LocalAlloc` at `0x180010628`
- `KERNEL32!LocalAlloc` at `0x18001074e`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x1800105fd`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010643`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x1800105fd`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010643`
- `GDI32!FONTOBJ_pifi` at `0x1800104dc`
- `GDI32!FONTOBJ_pifi` at `0x1800104dc`

## pseudocode

```c
unsigned int *__fastcall PCreateDLFont(__int64 a1, int a2, unsigned int a3)
{
  IFIMETRICS *v6; // rsi
  IFIMETRICS *v7; // rax
  unsigned int *v8; // rax
  __int64 v9; // rdx
  unsigned int *v10; // rbx
  int v11; // r14d
  int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  ULONG AllGlyphHandles; // eax
  ULONG v16; // r14d
  HGLYPH *v17; // rax
  HGLYPH *v18; // r15
  __int64 v19; // rax
  HGLYPH v20; // edx
  char *v21; // rdx
  __int64 v22; // rsi
  _BYTE *v23; // rdx
  __int64 v24; // rax
  _BYTE *v25; // rcx
  _BYTE *v26; // rax
  unsigned int v27; // r8d
  unsigned int v28; // ecx
  unsigned int v29; // eax
  HLOCAL v30; // rax
  char *v31; // rax
  __int64 v32; // r8
  void *v33; // rcx

  if ( !a3 )
    return 0;
  v6 = *(IFIMETRICS **)(a1 + 3544);
  if ( !v6 )
  {
    v7 = FONTOBJ_pifi(*(FONTOBJ **)(a1 + 3536));
    *(_QWORD *)(a1 + 3544) = v7;
    v6 = v7;
    if ( !v7 )
      return 0;
  }
  v8 = (unsigned int *)LocalAlloc(0x40u, 0x1A8u);
  v10 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 1) = a1;
    v8[49] = a3;
    v11 = 1;
    v8[48] = 0;
    v12 = 0;
    if ( (*(_DWORD *)(a1 + 3564) & 0x4000) != 0 )
    {
      v10[48] = 8;
      v12 = 8;
    }
    if ( a2 )
      v10[48] = v12 | 0x10;
    *((_QWORD *)v10 + 51) = 0;
    v13 = PGetFontFile(a1, v9, v10);
    *((_QWORD *)v10 + 50) = v13;
    if ( !v13 && a3 - 6 <= 4 )
      v11 = 0;
    *((_QWORD *)v10 + 22) = ULGetUniqueId(a1, v10[49]);
    *((_QWORD *)v10 + 23) = 0;
    if ( a3 != 7 && a3 != 10
      || (v14 = ULGetFontFileClassUniqueID(a1, *((_QWORD *)v10 + 50)), (*((_QWORD *)v10 + 23) = v14) == 0) )
    {
      *((_QWORD *)v10 + 23) = *((_QWORD *)v10 + 22);
    }
    if ( v11 )
    {
      v10[97] = 65537;
      *((_QWORD *)v10 + 47) = 0;
      AllGlyphHandles = FONTOBJ_cGetAllGlyphHandles(*(FONTOBJ **)(a1 + 3536), 0);
      v16 = AllGlyphHandles;
      v10[92] = AllGlyphHandles;
      if ( v6->cjIfiExtra <= 8 || !v6[1].dpwszFamilyName )
      {
        v17 = (HGLYPH *)LocalAlloc(0x40u, 4LL * AllGlyphHandles);
        v18 = v17;
        if ( v17 )
        {
          v16 = 0;
          LODWORD(v19) = FONTOBJ_cGetAllGlyphHandles(*(FONTOBJ **)(a1 + 3536), v17);
          while ( (_DWORD)v19 )
          {
            v19 = (unsigned int)(v19 - 1);
            v20 = v18[v19];
            if ( v20 <= v16 )
              v20 = v16;
            v16 = v20;
          }
          LocalFree(v18);
        }
        v10[92] = v16 + 1;
      }
      v21 = (char *)v6 + v6->dpwszFaceName;
      v22 = 32;
      VCopyUnicodeStringToAnsi(v10 + 4, v21, 32);
      if ( *((_BYTE *)v10 + 16) == 64 )
      {
        v24 = 2147483646;
        v23 = (char *)v10 + 17;
        v25 = v10 + 4;
        do
        {
          if ( !v24 )
            break;
          if ( !*v23 )
            break;
          *v25++ = *v23++;
          --v24;
          --v22;
        }
        while ( v22 );
        v26 = v25 - 1;
        if ( v22 )
          v26 = v25;
        *v26 = 0;
      }
      v27 = v10[49];
      if ( v27 - 8 <= 2 )
      {
        v31 = strchr((const char *)v10 + 16, 95);
        if ( v31 )
          *v31 = 0;
        VGetPSName(a1, v10 + 12, v32, 1);
      }
      else
      {
        GeneratePSName(
          (_DWORD)v10 + 48,
          (_DWORD)v23,
          v27,
          *((_QWORD *)v10 + 22),
          *((_QWORD *)v10 + 23),
          *(_QWORD *)(a1 + 3536),
          a2);
        if ( !a2 && a3 != 7 && a3 != 10 )
        {
          v28 = v10[92];
          v29 = 512;
          if ( v28 > 0x7D0 )
            v29 = 0x3FFF;
          if ( v28 < v29 )
            v29 = v10[92];
          v10[96] = v29;
          v30 = LocalAlloc(0x40u, 2LL * v29);
          *((_QWORD *)v10 + 47) = v30;
          if ( !v30 )
            v10[96] = 0;
        }
      }
      *(_QWORD *)v10 = *(_QWORD *)(a1 + 3512);
      *(_QWORD *)(a1 + 3512) = v10;
    }
    else
    {
      v33 = (void *)*((_QWORD *)v10 + 47);
      if ( v33 )
        LocalFree(v33);
      LocalFree(v10);
      return 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800104a8  push    rbx
0x1800104aa  push    rbp
0x1800104ab  push    rsi
0x1800104ac  push    rdi
0x1800104ad  push    r12
0x1800104af  push    r14
0x1800104b1  push    r15
0x1800104b3  sub     rsp, 40h
0x1800104b7  mov     ebp, r8d
0x1800104ba  mov     r12d, edx
0x1800104bd  mov     rdi, rcx
0x1800104c0  test    r8d, r8d
0x1800104c3  jz      loc_1800107C2
0x1800104c9  mov     rsi, [rcx+0DD8h]
0x1800104d0  test    rsi, rsi
0x1800104d3  jnz     short loc_1800104F5
0x1800104d5  mov     rcx, [rcx+0DD0h]; pfo
0x1800104dc  call    cs:__imp_FONTOBJ_pifi
0x1800104e2  mov     [rdi+0DD8h], rax
0x1800104e9  mov     rsi, rax
0x1800104ec  test    rax, rax
0x1800104ef  jz      loc_1800107C2
0x1800104f5  mov     edx, 1A8h; uBytes
0x1800104fa  mov     ecx, 40h ; '@'; uFlags
0x1800104ff  call    cs:__imp_LocalAlloc
0x180010505  mov     rbx, rax
0x180010508  test    rax, rax
0x18001050b  jz      loc_1800107BD
0x180010511  mov     [rax+8], rdi
0x180010515  mov     r15d, 1
0x18001051b  mov     [rax+0C4h], ebp
0x180010521  mov     r14d, r15d
0x180010524  mov     dword ptr [rax+0C0h], 0
0x18001052e  xor     eax, eax
0x180010530  test    dword ptr [rdi+0DECh], 4000h
0x18001053a  lea     ecx, [rax+8]
0x18001053d  jz      short loc_180010547
0x18001053f  mov     [rbx+0C0h], ecx
0x180010545  mov     eax, ecx
0x180010547  test    r12d, r12d
0x18001054a  jz      short loc_180010555
0x18001054c  or      eax, 10h
0x18001054f  mov     [rbx+0C0h], eax
0x180010555  mov     r8, rbx
0x180010558  mov     qword ptr [rbx+198h], 0
0x180010563  mov     rcx, rdi
0x180010566  call    PGetFontFile
0x18001056b  mov     [rbx+190h], rax
0x180010572  test    rax, rax
0x180010575  jnz     short loc_180010581
0x180010577  lea     ecx, [rbp-6]
0x18001057a  cmp     ecx, 4
0x18001057d  cmovbe  r14d, eax
0x180010581  mov     edx, [rbx+0C4h]
0x180010587  mov     rcx, rdi
0x18001058a  call    ULGetUniqueId
0x18001058f  mov     [rbx+0B0h], rax
0x180010596  mov     qword ptr [rbx+0B8h], 0
0x1800105a1  cmp     ebp, 7
0x1800105a4  jz      short loc_1800105AB
0x1800105a6  cmp     ebp, 0Ah
0x1800105a9  jnz     short loc_1800105C8
0x1800105ab  mov     rdx, [rbx+190h]
0x1800105b2  mov     rcx, rdi
0x1800105b5  call    ULGetFontFileClassUniqueID
0x1800105ba  mov     eax, eax
0x1800105bc  mov     [rbx+0B8h], rax
0x1800105c3  test    rax, rax
0x1800105c6  jnz     short loc_1800105D6
0x1800105c8  mov     rax, [rbx+0B0h]
0x1800105cf  mov     [rbx+0B8h], rax
0x1800105d6  test    r14d, r14d
0x1800105d9  jz      loc_1800107A0
0x1800105df  mov     dword ptr [rbx+184h], 10001h
0x1800105e9  xor     edx, edx; phg
0x1800105eb  mov     qword ptr [rbx+178h], 0
0x1800105f6  mov     rcx, [rdi+0DD0h]; pfo
0x1800105fd  call    cs:__imp_FONTOBJ_cGetAllGlyphHandles
0x180010603  mov     r14d, eax
0x180010606  mov     [rbx+170h], r14d
0x18001060d  cmp     dword ptr [rsi+4], 8
0x180010611  jbe     short loc_18001061C
0x180010613  cmp     dword ptr [rsi+0C8h], 0
0x18001061a  jnz     short loc_180010678
0x18001061c  mov     rdx, r14
0x18001061f  mov     ecx, 40h ; '@'; uFlags
0x180010624  shl     rdx, 2; uBytes
0x180010628  call    cs:__imp_LocalAlloc
0x18001062e  mov     r15, rax
0x180010631  test    rax, rax
0x180010634  jz      short loc_180010668
0x180010636  mov     rcx, [rdi+0DD0h]; pfo
0x18001063d  xor     r14d, r14d
0x180010640  mov     rdx, rax; phg
0x180010643  call    cs:__imp_FONTOBJ_cGetAllGlyphHandles
0x180010649  jmp     short loc_18001065B
0x18001064b  dec     eax
0x18001064d  mov     edx, [r15+rax*4]
0x180010651  cmp     edx, r14d
0x180010654  cmovbe  edx, r14d
0x180010658  mov     r14d, edx
0x18001065b  test    eax, eax
0x18001065d  jnz     short loc_18001064B
0x18001065f  mov     rcx, r15; hMem
0x180010662  call    cs:__imp_LocalFree
0x180010668  lea     eax, [r14+1]
0x18001066c  mov     r15d, 1
0x180010672  mov     [rbx+170h], eax
0x180010678  movsxd  rdx, dword ptr [rsi+10h]
0x18001067c  lea     r14, [rbx+10h]
0x180010680  add     rdx, rsi
0x180010683  mov     rcx, r14
0x180010686  mov     esi, 20h ; ' '
0x18001068b  mov     r8d, esi
0x18001068e  call    VCopyUnicodeStringToAnsi
0x180010693  cmp     byte ptr [r14], 40h ; '@'
0x180010697  jnz     short loc_1800106D1
0x180010699  mov     eax, 7FFFFFFEh
0x18001069e  lea     rdx, [r14+1]
0x1800106a2  mov     rcx, r14
0x1800106a5  test    rax, rax
0x1800106a8  jz      short loc_1800106C3
0x1800106aa  mov     r8b, [rdx]
0x1800106ad  test    r8b, r8b
0x1800106b0  jz      short loc_1800106C3
0x1800106b2  mov     [rcx], r8b
0x1800106b5  add     rdx, r15
0x1800106b8  add     rcx, r15
0x1800106bb  sub     rax, r15
0x1800106be  sub     rsi, r15
0x1800106c1  jnz     short loc_1800106A5
0x1800106c3  test    rsi, rsi
0x1800106c6  lea     rax, [rcx-1]
0x1800106ca  cmovnz  rax, rcx
0x1800106ce  mov     byte ptr [rax], 0
0x1800106d1  mov     r8d, [rbx+0C4h]
0x1800106d8  lea     eax, [r8-8]
0x1800106dc  cmp     eax, 2
0x1800106df  jbe     loc_180010768
0x1800106e5  mov     rax, [rdi+0DD0h]
0x1800106ec  lea     rcx, [rbx+30h]
0x1800106f0  mov     r9, [rbx+0B0h]
0x1800106f7  mov     [rsp+78h+var_48], r12d
0x1800106fc  mov     [rsp+78h+var_50], rax
0x180010701  mov     rax, [rbx+0B8h]
0x180010708  mov     [rsp+78h+var_58], rax
0x18001070d  call    GeneratePSName
0x180010712  test    r12d, r12d
0x180010715  jnz     short loc_18001078D
0x180010717  cmp     ebp, 7
0x18001071a  jz      short loc_18001078D
0x18001071c  cmp     ebp, 0Ah
0x18001071f  jz      short loc_18001078D
0x180010721  mov     ecx, [rbx+170h]
0x180010727  mov     eax, 200h
0x18001072c  cmp     ecx, 7D0h
0x180010732  jbe     short loc_180010739
0x180010734  mov     eax, 3FFFh
0x180010739  cmp     ecx, eax
0x18001073b  cmovb   eax, ecx
0x18001073e  mov     ecx, 40h ; '@'; uFlags
0x180010743  mov     edx, eax
0x180010745  add     rdx, rdx; uBytes
0x180010748  mov     [rbx+180h], eax
0x18001074e  call    cs:__imp_LocalAlloc
0x180010754  mov     [rbx+178h], rax
0x18001075b  test    rax, rax
0x18001075e  jnz     short loc_18001078D
0x180010760  mov     [rbx+180h], eax
0x180010766  jmp     short loc_18001078D
0x180010768  mov     edx, 5Fh ; '_'; Val
0x18001076d  mov     rcx, r14; Str
0x180010770  call    cs:__imp_strchr
0x180010776  test    rax, rax
0x180010779  jz      short loc_18001077E
0x18001077b  mov     byte ptr [rax], 0
0x18001077e  lea     rdx, [rbx+30h]
0x180010782  mov     r9d, r15d
0x180010785  mov     rcx, rdi
0x180010788  call    VGetPSName
0x18001078d  mov     rax, [rdi+0DB8h]
0x180010794  mov     [rbx], rax
0x180010797  mov     [rdi+0DB8h], rbx
0x18001079e  jmp     short loc_1800107BD
0x1800107a0  mov     rcx, [rbx+178h]; hMem
0x1800107a7  test    rcx, rcx
0x1800107aa  jz      short loc_1800107B2
0x1800107ac  call    cs:__imp_LocalFree
0x1800107b2  mov     rcx, rbx; hMem
0x1800107b5  call    cs:__imp_LocalFree
0x1800107bb  xor     ebx, ebx
0x1800107bd  mov     rax, rbx
0x1800107c0  jmp     short loc_1800107C4
0x1800107c2  xor     eax, eax
0x1800107c4  add     rsp, 40h
0x1800107c8  pop     r15
0x1800107ca  pop     r14
0x1800107cc  pop     r12
0x1800107ce  pop     rdi
0x1800107cf  pop     rsi
0x1800107d0  pop     rbp
0x1800107d1  pop     rbx
0x1800107d2  retn
```
