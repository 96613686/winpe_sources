# CPrintAbstractHelper::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)

- ea: `0x180032250`
- end: `0x18003253f`
- name: `?SetOptionInternal@CPrintAbstractHelper@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z`
- size: `751`
- prototype: `int(CPrintAbstractHelper *__hidden this, const char *, const char *, struct CPrintCoreConfig *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002d220`

## callees

- `0x18002fac0`
- `0x18002fb5c`
- `0x180032250`
- `0x180032cb0`
- `0x180032d10`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::SetOptionInternal(
        CPrintAbstractHelper *this,
        const char *a2,
        const char *a3,
        struct CPrintCoreConfig *a4)
{
  struct _UIINFO *UIInfo; // rbp
  const char *v10; // rax
  unsigned int v11; // ebx
  int v12; // r8d
  int v13; // ecx
  _DWORD *v14; // rax
  __int64 KeywordMatchFeature; // rax
  __int64 v16; // rdi
  bool v17; // zf
  char *v18; // rax
  __int64 i; // r15
  const char *v20; // rcx
  const char *v21; // r8
  int v22; // edx
  int v23; // eax
  const char **j; // rdi
  const char *v25; // r8
  int v26; // edx
  int v27; // ecx
  const char *v28; // rax
  __int64 v29; // rax
  char *v30; // r14
  __int64 v31; // rbp
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  int v35; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v36[21]; // [rsp+34h] [rbp-54h] BYREF

  v35 = 0;
  v36[0] = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a4);
  if ( !UIInfo )
    return 2147549183LL;
  v10 = "%FormTrayCheck";
  v11 = 0;
  do
  {
    v12 = (unsigned __int8)v10[a2 - "%FormTrayCheck"];
    v13 = *(unsigned __int8 *)v10 - v12;
    if ( v13 )
      break;
    ++v10;
  }
  while ( v12 );
  if ( v13 )
  {
    KeywordMatchFeature = PInternalGetKeywordMatchFeature(UIInfo, a2, 0, &v35);
    v16 = KeywordMatchFeature;
    if ( !KeywordMatchFeature )
    {
      for ( i = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, struct CPrintCoreConfig *))(*(_QWORD *)this + 72LL))(
                  this,
                  a4); i; i += 24 )
      {
        v20 = *(const char **)i;
        if ( !*(_QWORD *)i )
          break;
        v21 = (const char *)(a2 - v20);
        do
        {
          v22 = (unsigned __int8)v21[(_QWORD)v20];
          v23 = *(unsigned __int8 *)v20 - v22;
          if ( v23 )
            break;
          ++v20;
        }
        while ( v22 );
        if ( !v23 )
        {
          for ( j = *(const char ***)(i + 16); ; j += 4 )
          {
            v28 = *j;
            if ( !*j )
              break;
            v25 = (const char *)(a3 - v28);
            do
            {
              v26 = (unsigned __int8)v25[(_QWORD)v28];
              v27 = *(unsigned __int8 *)v28 - v26;
              if ( v27 )
                break;
              ++v28;
            }
            while ( v26 );
            if ( !v27 )
            {
              if ( !*(_DWORD *)(i + 8) && (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) == 0
                || *(_DWORD *)(i + 8) == 1 && (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 4) == 0 )
              {
                return (unsigned int)-2147467259;
              }
              v29 = *((_QWORD *)a4 + 2);
              v30 = (char *)a4 + 8;
              if ( v29 || (v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 48LL))(*(_QWORD *)a4)) != 0 )
                v31 = v29 + *(unsigned __int16 *)(v29 + 68);
              else
                v31 = 0;
              if ( *(_QWORD *)a4 )
                v32 = (*(__int64 (**)(void))(*(_QWORD *)v30 + 40LL))();
              else
                v32 = 0;
              if ( !*(_DWORD *)(i + 8) )
                v32 = v31;
              do
              {
                v33 = *((_DWORD *)j + 6);
                if ( v33 )
                {
                  switch ( v33 )
                  {
                    case 1:
                      *(_WORD *)&j[2][v32] = *((_WORD *)j + 6);
                      break;
                    case 2:
                      *(_DWORD *)&j[2][v32] |= *((_DWORD *)j + 3);
                      break;
                    case 3:
                      *(_DWORD *)&j[2][v32] &= ~*((_DWORD *)j + 3);
                      break;
                  }
                }
                else
                {
                  *(_DWORD *)&j[2][v32] = *((_DWORD *)j + 3);
                }
                v34 = *((_DWORD *)j + 2);
                j += 4;
              }
              while ( (v34 & 2) != 0 );
              return v11;
            }
            while ( ((_BYTE)j[1] & 2) != 0 )
              j += 4;
          }
        }
      }
      return (unsigned int)-2147467259;
    }
    if ( *(_DWORD *)(KeywordMatchFeature + 44) < 2u )
    {
      v17 = (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) == 0;
    }
    else
    {
      if ( (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 4) != 0 )
        goto LABEL_16;
      v17 = *(_DWORD *)(v16 + 44) == 2;
    }
    if ( v17 )
      return (unsigned int)-2147467259;
LABEL_16:
    if ( PInternalGetKeywordMatchOption((_DWORD)UIInfo, v16, (_DWORD)a3, 0, (__int64)v36) )
    {
      if ( *((_QWORD *)a4 + 2) )
        v18 = (char *)a4 + 28;
      else
        v18 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a4 + 1) + 8LL))(*(_QWORD *)a4, 0);
      if ( v18 )
        v18[2 * v35] = v36[0];
      else
        v11 = -2147467259;
      if ( *(_DWORD *)(v16 + 28) == 1 )
        (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 134) + 88LL))(*(_QWORD *)a4);
      return v11;
    }
    return (unsigned int)-2147467259;
  }
  if ( !strcmp("Disabled", a3) )
  {
    v14 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 64LL))(*(_QWORD *)a4);
    if ( v14 )
      *v14 |= 0x200u;
    return v11;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180032250  push    rbx
0x180032252  push    rbp
0x180032253  push    rsi
0x180032254  push    rdi
0x180032255  push    r12
0x180032257  push    r13
0x180032259  push    r14
0x18003225b  push    r15
0x18003225d  sub     rsp, 48h
0x180032261  mov     r14, rcx
0x180032264  xor     r15d, r15d
0x180032267  mov     rcx, r9; this
0x18003226a  mov     [rsp+88h+var_58], r15d
0x18003226f  mov     [rsp+88h+var_54], r15d
0x180032274  mov     rsi, r9
0x180032277  mov     r12, r8
0x18003227a  mov     r13, rdx
0x18003227d  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x180032282  mov     rbp, rax
0x180032285  test    rax, rax
0x180032288  jnz     short loc_180032294
0x18003228a  mov     eax, 8000FFFFh
0x18003228f  jmp     loc_1800324B1
0x180032294  lea     rax, aFormtraycheck; "%FormTrayCheck"
0x18003229b  mov     rdx, r13
0x18003229e  sub     rdx, rax
0x1800322a1  mov     ebx, r15d
0x1800322a4  movzx   ecx, byte ptr [rax]
0x1800322a7  movzx   r8d, byte ptr [rax+rdx]
0x1800322ac  sub     ecx, r8d
0x1800322af  jnz     short loc_1800322B9
0x1800322b1  inc     rax
0x1800322b4  test    r8d, r8d
0x1800322b7  jnz     short loc_1800322A4
0x1800322b9  test    ecx, ecx
0x1800322bb  jnz     short loc_180032304
0x1800322bd  lea     rax, aDisabled; "Disabled"
0x1800322c4  sub     r12, rax
0x1800322c7  movzx   ecx, byte ptr [rax]
0x1800322ca  movzx   edx, byte ptr [rax+r12]
0x1800322cf  sub     ecx, edx
0x1800322d1  jnz     short loc_1800322DA
0x1800322d3  inc     rax
0x1800322d6  test    edx, edx
0x1800322d8  jnz     short loc_1800322C7
0x1800322da  test    ecx, ecx
0x1800322dc  jnz     loc_1800324AA
0x1800322e2  mov     rax, [rsi+8]
0x1800322e6  mov     rcx, [rsi]
0x1800322e9  mov     rax, [rax+40h]
0x1800322ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322f2  test    rax, rax
0x1800322f5  jz      loc_1800324AF
0x1800322fb  bts     dword ptr [rax], 9
0x1800322ff  jmp     loc_1800324AF
0x180032304  lea     r9, [rsp+88h+var_58]
0x180032309  xor     r8d, r8d
0x18003230c  mov     rdx, r13
0x18003230f  mov     rcx, rbp
0x180032312  call    PInternalGetKeywordMatchFeature
0x180032317  mov     rdi, rax
0x18003231a  test    rax, rax
0x18003231d  jz      loc_1800323C3
0x180032323  cmp     dword ptr [rax+2Ch], 2
0x180032327  mov     rcx, rsi; this
0x18003232a  jb      short loc_18003233B
0x18003232c  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180032331  test    al, 4
0x180032333  jnz     short loc_180032348
0x180032335  cmp     dword ptr [rdi+2Ch], 2
0x180032339  jmp     short loc_180032342
0x18003233b  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180032340  test    al, 1
0x180032342  jz      loc_1800324AA
0x180032348  lea     rax, [rsp+88h+var_54]
0x18003234d  xor     r9d, r9d
0x180032350  mov     r8, r12
0x180032353  mov     [rsp+88h+var_68], rax
0x180032358  mov     rdx, rdi
0x18003235b  mov     rcx, rbp
0x18003235e  call    PInternalGetKeywordMatchOption
0x180032363  test    rax, rax
0x180032366  jz      loc_1800324AA
0x18003236c  cmp     [rsi+10h], r15
0x180032370  jz      short loc_180032378
0x180032372  lea     rax, [rsi+1Ch]
0x180032376  jmp     short loc_18003238A
0x180032378  mov     rax, [rsi+8]
0x18003237c  xor     edx, edx
0x18003237e  mov     rcx, [rsi]
0x180032381  mov     rax, [rax+8]
0x180032385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003238a  test    rax, rax
0x18003238d  jz      short loc_18003239C
0x18003238f  mov     edx, [rsp+88h+var_58]
0x180032393  mov     cl, byte ptr [rsp+88h+var_54]
0x180032397  mov     [rax+rdx*2], cl
0x18003239a  jmp     short loc_1800323A1
0x18003239c  mov     ebx, 80004005h
0x1800323a1  cmp     dword ptr [rdi+1Ch], 1
0x1800323a5  jnz     loc_1800324AF
0x1800323ab  mov     rax, [r14+430h]
0x1800323b2  mov     rcx, [rsi]
0x1800323b5  mov     rax, [rax+58h]
0x1800323b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323be  jmp     loc_1800324AF
0x1800323c3  mov     rax, [r14]
0x1800323c6  mov     rdx, rsi
0x1800323c9  mov     rcx, r14
0x1800323cc  mov     ebp, r15d
0x1800323cf  mov     rax, [rax+48h]
0x1800323d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323d8  mov     r15, rax
0x1800323db  test    rax, rax
0x1800323de  jz      loc_1800324AA
0x1800323e4  mov     rcx, [r15]
0x1800323e7  test    rcx, rcx
0x1800323ea  jz      loc_1800324AA
0x1800323f0  mov     r8, r13
0x1800323f3  sub     r8, rcx
0x1800323f6  movzx   eax, byte ptr [rcx]
0x1800323f9  movzx   edx, byte ptr [rcx+r8]
0x1800323fe  sub     eax, edx
0x180032400  jnz     short loc_180032409
0x180032402  inc     rcx
0x180032405  test    edx, edx
0x180032407  jnz     short loc_1800323F6
0x180032409  test    eax, eax
0x18003240b  jnz     loc_1800324A0
0x180032411  mov     rdi, [r15+10h]
0x180032415  lea     ebp, [rax+1]
0x180032418  jmp     short loc_180032494
0x18003241a  mov     r8, r12
0x18003241d  sub     r8, rax
0x180032420  movzx   ecx, byte ptr [rax]
0x180032423  movzx   edx, byte ptr [rax+r8]
0x180032428  sub     ecx, edx
0x18003242a  jnz     short loc_180032433
0x18003242c  inc     rax
0x18003242f  test    edx, edx
0x180032431  jnz     short loc_180032420
0x180032433  test    ecx, ecx
0x180032435  jnz     short loc_18003248A
0x180032437  cmp     [r15+8], ebx
0x18003243b  jnz     short loc_18003244A
0x18003243d  mov     rcx, rsi; this
0x180032440  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180032445  test    bpl, al
0x180032448  jz      short loc_1800324AA
0x18003244a  cmp     [r15+8], ebp
0x18003244e  jnz     short loc_18003245C
0x180032450  mov     rcx, rsi; this
0x180032453  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180032458  test    al, 4
0x18003245a  jz      short loc_1800324AA
0x18003245c  mov     rax, [rsi+10h]
0x180032460  lea     r14, [rsi+8]
0x180032464  test    rax, rax
0x180032467  jnz     short loc_18003247D
0x180032469  mov     rax, [r14]
0x18003246c  mov     rcx, [rsi]
0x18003246f  mov     rax, [rax+30h]
0x180032473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032478  test    rax, rax
0x18003247b  jz      short loc_1800324C2
0x18003247d  movzx   ebp, word ptr [rax+44h]
0x180032481  add     rbp, rax
0x180032484  jmp     short loc_1800324C4
0x180032486  add     rdi, 20h ; ' '
0x18003248a  test    byte ptr [rdi+8], 2
0x18003248e  jnz     short loc_180032486
0x180032490  add     rdi, 20h ; ' '
0x180032494  mov     rax, [rdi]
0x180032497  test    rax, rax
0x18003249a  jnz     loc_18003241A
0x1800324a0  add     r15, 18h
0x1800324a4  jnz     loc_1800323E4
0x1800324aa  mov     ebx, 80004005h
0x1800324af  mov     eax, ebx
0x1800324b1  add     rsp, 48h
0x1800324b5  pop     r15
0x1800324b7  pop     r14
0x1800324b9  pop     r13
0x1800324bb  pop     r12
0x1800324bd  pop     rdi
0x1800324be  pop     rsi
0x1800324bf  pop     rbp
0x1800324c0  pop     rbx
0x1800324c1  retn
0x1800324c2  xor     ebp, ebp
0x1800324c4  mov     rcx, [rsi]
0x1800324c7  test    rcx, rcx
0x1800324ca  jz      short loc_1800324DD
0x1800324cc  mov     rax, [r14]
0x1800324cf  mov     rax, [rax+28h]
0x1800324d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324d8  mov     rdx, rax
0x1800324db  jmp     short loc_1800324DF
0x1800324dd  xor     edx, edx
0x1800324df  cmp     [r15+8], ebx
0x1800324e3  cmovz   rdx, rbp
0x1800324e7  mov     eax, [rdi+18h]
0x1800324ea  test    eax, eax
0x1800324ec  jnz     short loc_1800324FA
0x1800324ee  mov     rcx, [rdi+10h]
0x1800324f2  mov     eax, [rdi+0Ch]
0x1800324f5  mov     [rdx+rcx], eax
0x1800324f8  jmp     short loc_18003252F
0x1800324fa  cmp     eax, 1
0x1800324fd  jnz     short loc_18003250D
0x1800324ff  mov     rcx, [rdi+10h]
0x180032503  movzx   eax, word ptr [rdi+0Ch]
0x180032507  mov     [rdx+rcx], ax
0x18003250b  jmp     short loc_18003252F
0x18003250d  cmp     eax, 2
0x180032510  jnz     short loc_18003251E
0x180032512  mov     rcx, [rdi+10h]
0x180032516  mov     eax, [rdi+0Ch]
0x180032519  or      [rcx+rdx], eax
0x18003251c  jmp     short loc_18003252F
0x18003251e  cmp     eax, 3
0x180032521  jnz     short loc_18003252F
0x180032523  mov     eax, [rdi+0Ch]
0x180032526  mov     rcx, [rdi+10h]
0x18003252a  not     eax
0x18003252c  and     [rcx+rdx], eax
0x18003252f  mov     eax, [rdi+8]
0x180032532  add     rdi, 20h ; ' '
0x180032536  test    al, 2
0x180032538  jnz     short loc_1800324E7
0x18003253a  jmp     loc_1800324AF
```
